# DumpToken

- ea: `0x18011d8e0`
- end: `0x18011db08`
- name: `DumpToken`
- size: `552`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18011f734`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x18011d8e0`
- `0x1801218e8`
- `0x180166ee0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18011d972`
- `ntdll!NtQueryInformationToken` at `0x18011d9c1`
- `ntdll!NtQueryInformationToken` at `0x18011da14`
- `ntdll!NtQueryInformationToken` at `0x18011da7a`
- `ntdll!NtQueryInformationToken` at `0x18011dabc`
- `ntdll!NtQueryInformationToken` at `0x18011d972`
- `ntdll!NtQueryInformationToken` at `0x18011d9c1`
- `ntdll!NtQueryInformationToken` at `0x18011da14`
- `ntdll!NtQueryInformationToken` at `0x18011da7a`
- `ntdll!NtQueryInformationToken` at `0x18011dabc`
- `ntdll!NtOpenThreadToken` at `0x18011d92d`
- `ntdll!NtOpenThreadToken` at `0x18011d92d`
- `ntdll!RtlFreeHeap` at `0x18011d9a4`
- `ntdll!RtlFreeHeap` at `0x18011da57`
- `ntdll!RtlFreeHeap` at `0x18011d9a4`
- `ntdll!RtlFreeHeap` at `0x18011da57`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18011d987`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18011da3a`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18011d987`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18011da3a`
- `ntdll!NtClose` at `0x18011dade`
- `ntdll!NtClose` at `0x18011dade`

## pseudocode

```c
int __fastcall DumpToken(HANDLE TokenHandle)
{
  HANDLE v2; // rbx
  unsigned int *v3; // rax
  unsigned int *v4; // rbx
  unsigned int v5; // edi
  unsigned int *v6; // rbx
  ULONG TokenInformationLength; // [rsp+30h] [rbp-49h] BYREF
  void *TokenHandlea; // [rsp+38h] [rbp-41h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-39h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-29h] BYREF

  TokenInformationLength = 0;
  TokenHandlea = TokenHandle;
  v2 = TokenHandle;
  if ( TokenHandle == (HANDLE)-1LL )
  {
    LODWORD(v3) = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandlea);
    if ( (int)v3 < 0 )
      goto LABEL_21;
    v2 = TokenHandlea;
  }
  memset_0(TokenInformation, 0, 0x54u);
  TokenInformationLength = 84;
  UnicodeString = 0;
  if ( NtQueryInformationToken(v2, TokenUser, TokenInformation, 0x54u, &TokenInformationLength) >= 0
    && RtlConvertSidToUnicodeString(&UnicodeString, TokenInformation[0], 1u) >= 0 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UnicodeString.Buffer);
  }
  LODWORD(v3) = NtQueryInformationToken(TokenHandlea, TokenGroups, 0, 0, &TokenInformationLength);
  if ( (int)((_DWORD)v3 + 0x80000000) < 0 || (_DWORD)v3 == -1073741789 )
  {
    if ( TokenInformationLength )
    {
      v3 = (unsigned int *)THAlloc(TokenInformationLength);
      v4 = v3;
      if ( !v3 )
        goto LABEL_21;
      v5 = 0;
      if ( NtQueryInformationToken(TokenHandlea, TokenGroups, v3, TokenInformationLength, &TokenInformationLength) >= 0 )
      {
        while ( v5 < *v4 )
        {
          UnicodeString = 0;
          if ( RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)&v4[4 * v5 + 2], 1u) < 0 )
            break;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, UnicodeString.Buffer);
          ++v5;
        }
      }
    }
    LODWORD(v3) = NtQueryInformationToken(TokenHandlea, TokenPrivileges, 0, 0, &TokenInformationLength);
    if ( (((_DWORD)v3 + 0x80000000) & 0x80000000) != 0 || (_DWORD)v3 == -1073741789 )
    {
      LODWORD(v3) = TokenInformationLength;
      if ( TokenInformationLength )
      {
        v3 = (unsigned int *)THAlloc(TokenInformationLength);
        v6 = v3;
        if ( v3 )
        {
          LODWORD(v3) = NtQueryInformationToken(
                          TokenHandlea,
                          TokenPrivileges,
                          v3,
                          TokenInformationLength,
                          &TokenInformationLength);
          if ( (int)v3 >= 0 )
            LODWORD(v3) = PrintPrivileges(v6);
        }
      }
    }
  }
LABEL_21:
  if ( TokenHandlea != (void *)-1LL && TokenHandle == (HANDLE)-1LL )
    LODWORD(v3) = NtClose(TokenHandlea);
  return (int)v3;
}

```

## disassembly

```asm
0x18011d8e0  mov     [rsp-8+arg_8], rbx
0x18011d8e5  mov     [rsp-8+arg_10], rsi
0x18011d8ea  push    rbp
0x18011d8eb  push    rdi
0x18011d8ec  push    r15
0x18011d8ee  lea     rbp, [rsp-47h]
0x18011d8f3  sub     rsp, 0C0h
0x18011d8fa  mov     rax, cs:__security_cookie
0x18011d901  xor     rax, rsp
0x18011d904  mov     [rbp+57h+var_20], rax
0x18011d908  mov     [rbp+57h+TokenInformationLength], 0
0x18011d90f  mov     rsi, rcx
0x18011d912  mov     [rbp+57h+TokenHandle], rcx
0x18011d916  mov     rbx, rcx
0x18011d919  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18011d91d  jnz     short loc_18011D93F
0x18011d91f  lea     edx, [rcx+9]; DesiredAccess
0x18011d922  mov     r8b, 1; OpenAsSelf
0x18011d925  lea     rcx, [rbx-1]; ThreadHandle
0x18011d929  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18011d92d  call    cs:__imp_NtOpenThreadToken
0x18011d933  test    eax, eax
0x18011d935  js      loc_18011DACE
0x18011d93b  mov     rbx, [rbp+57h+TokenHandle]
0x18011d93f  mov     edi, 54h ; 'T'
0x18011d944  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18011d948  mov     r8d, edi; Size
0x18011d94b  xor     edx, edx; Val
0x18011d94d  call    memset_0
0x18011d952  xorps   xmm0, xmm0
0x18011d955  mov     [rbp+57h+TokenInformationLength], edi
0x18011d958  lea     rax, [rbp+57h+TokenInformationLength]
0x18011d95c  mov     r9d, edi; TokenInformationLength
0x18011d95f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18011d963  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18011d968  lea     edx, [rdi-53h]; TokenInformationClass
0x18011d96b  mov     rcx, rbx; TokenHandle
0x18011d96e  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18011d972  call    cs:__imp_NtQueryInformationToken
0x18011d978  test    eax, eax
0x18011d97a  js      short loc_18011D9AA
0x18011d97c  mov     rdx, [rbp+57h+TokenInformation]; Sid
0x18011d980  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18011d984  mov     r8b, 1; AllocateDestinationString
0x18011d987  call    cs:__imp_RtlConvertSidToUnicodeString
0x18011d98d  test    eax, eax
0x18011d98f  js      short loc_18011D9AA
0x18011d991  mov     rcx, gs:60h
0x18011d99a  xor     edx, edx; Flags
0x18011d99c  mov     r8, [rbp+57h+UnicodeString.Buffer]; P
0x18011d9a0  mov     rcx, [rcx+30h]; HeapHandle
0x18011d9a4  call    cs:__imp_RtlFreeHeap
0x18011d9aa  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18011d9ae  lea     rax, [rbp+57h+TokenInformationLength]
0x18011d9b2  xor     r9d, r9d; TokenInformationLength
0x18011d9b5  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18011d9ba  xor     r8d, r8d; TokenInformation
0x18011d9bd  lea     edx, [r9+2]; TokenInformationClass
0x18011d9c1  call    cs:__imp_NtQueryInformationToken
0x18011d9c7  mov     r15d, 80000000h
0x18011d9cd  lea     ecx, [rax+r15]
0x18011d9d1  test    r15d, ecx
0x18011d9d4  jnz     short loc_18011D9E1
0x18011d9d6  cmp     eax, 0C0000023h
0x18011d9db  jnz     loc_18011DACE
0x18011d9e1  mov     eax, [rbp+57h+TokenInformationLength]
0x18011d9e4  test    eax, eax
0x18011d9e6  jz      short loc_18011DA61
0x18011d9e8  mov     ecx, eax
0x18011d9ea  call    THAlloc
0x18011d9ef  mov     rbx, rax
0x18011d9f2  test    rax, rax
0x18011d9f5  jz      loc_18011DACE
0x18011d9fb  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18011d9ff  lea     rax, [rbp+57h+TokenInformationLength]
0x18011da03  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18011da07  xor     edi, edi
0x18011da09  mov     r8, rbx; TokenInformation
0x18011da0c  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18011da11  lea     edx, [rdi+2]; TokenInformationClass
0x18011da14  call    cs:__imp_NtQueryInformationToken
0x18011da1a  test    eax, eax
0x18011da1c  js      short loc_18011DA61
0x18011da1e  cmp     edi, [rbx]
0x18011da20  jnb     short loc_18011DA61
0x18011da22  xorps   xmm0, xmm0
0x18011da25  mov     edx, edi
0x18011da27  add     rdx, rdx
0x18011da2a  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18011da2e  mov     r8b, 1; AllocateDestinationString
0x18011da31  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x18011da35  mov     rdx, [rbx+rdx*8+8]; Sid
0x18011da3a  call    cs:__imp_RtlConvertSidToUnicodeString
0x18011da40  test    eax, eax
0x18011da42  js      short loc_18011DA61
0x18011da44  mov     rcx, gs:60h
0x18011da4d  xor     edx, edx; Flags
0x18011da4f  mov     r8, [rbp+57h+UnicodeString.Buffer]; P
0x18011da53  mov     rcx, [rcx+30h]; HeapHandle
0x18011da57  call    cs:__imp_RtlFreeHeap
0x18011da5d  inc     edi
0x18011da5f  jmp     short loc_18011DA1E
0x18011da61  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18011da65  lea     rax, [rbp+57h+TokenInformationLength]
0x18011da69  xor     r9d, r9d; TokenInformationLength
0x18011da6c  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18011da71  xor     r8d, r8d; TokenInformation
0x18011da74  lea     edi, [r9+3]
0x18011da78  mov     edx, edi; TokenInformationClass
0x18011da7a  call    cs:__imp_NtQueryInformationToken
0x18011da80  lea     ecx, [rax+r15]
0x18011da84  test    r15d, ecx
0x18011da87  jnz     short loc_18011DA90
0x18011da89  cmp     eax, 0C0000023h
0x18011da8e  jnz     short loc_18011DACE
0x18011da90  mov     eax, [rbp+57h+TokenInformationLength]
0x18011da93  test    eax, eax
0x18011da95  jz      short loc_18011DACE
0x18011da97  mov     ecx, eax
0x18011da99  call    THAlloc
0x18011da9e  mov     rbx, rax
0x18011daa1  test    rax, rax
0x18011daa4  jz      short loc_18011DACE
0x18011daa6  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18011daaa  lea     rax, [rbp+57h+TokenInformationLength]
0x18011daae  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18011dab2  mov     r8, rbx; TokenInformation
0x18011dab5  mov     edx, edi; TokenInformationClass
0x18011dab7  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18011dabc  call    cs:__imp_NtQueryInformationToken
0x18011dac2  test    eax, eax
0x18011dac4  js      short loc_18011DACE
0x18011dac6  mov     rcx, rbx
0x18011dac9  call    PrintPrivileges
0x18011dace  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18011dad2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18011dad6  jz      short loc_18011DAE4
0x18011dad8  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18011dadc  jnz     short loc_18011DAE4
0x18011dade  call    cs:__imp_NtClose
0x18011dae4  mov     rcx, [rbp+57h+var_20]
0x18011dae8  xor     rcx, rsp; StackCookie
0x18011daeb  call    __security_check_cookie
0x18011daf0  lea     r11, [rsp+0D0h+var_10]
0x18011daf8  mov     rbx, [r11+28h]
0x18011dafc  mov     rsi, [r11+30h]
0x18011db00  mov     rsp, r11
0x18011db03  pop     r15
0x18011db05  pop     rdi
0x18011db06  pop     rbp
0x18011db07  retn
```
