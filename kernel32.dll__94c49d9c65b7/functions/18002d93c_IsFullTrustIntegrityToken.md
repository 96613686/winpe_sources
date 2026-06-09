# IsFullTrustIntegrityToken

- ea: `0x18002d93c`
- end: `0x18002dad2`
- name: `IsFullTrustIntegrityToken`
- size: `406`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ce30`

## callees

- `0x18002d93c`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18002da01`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002da01`
- `ntdll!NtQueryInformationToken` at `0x18002d9ab`
- `ntdll!NtQueryInformationToken` at `0x18002dab2`
- `ntdll!NtQueryInformationToken` at `0x18002d9ab`
- `ntdll!NtQueryInformationToken` at `0x18002dab2`
- `ntdll!RtlSubAuthoritySid` at `0x18002da11`
- `ntdll!RtlSubAuthoritySid` at `0x18002da11`
- `ntdll!NtOpenProcessToken` at `0x18002da55`
- `ntdll!NtOpenProcessToken` at `0x18002da55`
- `ntdll!NtClose` at `0x18002dac7`
- `ntdll!NtClose` at `0x18002dac7`
- `ntdll!RtlFreeHeap` at `0x18002da40`
- `ntdll!RtlFreeHeap` at `0x18002da40`
- `ntdll!RtlAllocateHeap` at `0x18002da81`
- `ntdll!RtlAllocateHeap` at `0x18002da81`

## pseudocode

```c
__int64 __fastcall IsFullTrustIntegrityToken(HANDLE TokenHandle, _BYTE *a2)
{
  PSID *Heap; // rbx
  HANDLE v5; // rdi
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  PUCHAR v9; // rax
  ULONG TokenInformationLength; // [rsp+30h] [rbp-39h] BYREF
  void *TokenHandlea; // [rsp+38h] [rbp-31h] BYREF
  _BYTE TokenInformation[96]; // [rsp+40h] [rbp-29h] BYREF

  Heap = 0;
  TokenHandlea = TokenHandle;
  TokenInformationLength = 0;
  v5 = TokenHandle;
  memset_0(TokenInformation, 0, 0x58u);
  *a2 = 0;
  if ( !v5 )
  {
    v7 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandlea);
    if ( v7 < 0 )
      goto LABEL_4;
    v5 = TokenHandlea;
  }
  v6 = NtQueryInformationToken(v5, TokenIntegrityLevel, TokenInformation, 0x58u, &TokenInformationLength);
  v7 = v6;
  if ( v6 >= 0 )
  {
    Heap = (PSID *)TokenInformation;
LABEL_9:
    v9 = RtlSubAuthorityCountSid(*Heap);
    if ( *RtlSubAuthoritySid(*Heap, (unsigned __int8)(*v9 - 1)) > 0x1000 )
      *a2 = 1;
    goto LABEL_4;
  }
  if ( v6 != -1073741789 )
    goto LABEL_4;
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
  if ( !Heap )
  {
    v7 = -1073741670;
    goto LABEL_4;
  }
  v7 = NtQueryInformationToken(TokenHandlea, TokenIntegrityLevel, Heap, TokenInformationLength, &TokenInformationLength);
  if ( v7 >= 0 )
    goto LABEL_9;
LABEL_4:
  if ( TokenHandlea != TokenHandle )
    NtClose(TokenHandlea);
  if ( Heap && Heap != (PSID *)TokenInformation )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002d93c  mov     [rsp-8+arg_10], rbx
0x18002d941  mov     [rsp-8+arg_18], rsi
0x18002d946  push    rbp
0x18002d947  push    rdi
0x18002d948  push    r14
0x18002d94a  lea     rbp, [rsp-47h]
0x18002d94f  sub     rsp, 0B0h
0x18002d956  mov     rax, cs:__security_cookie
0x18002d95d  xor     rax, rsp
0x18002d960  mov     [rbp+57h+var_20], rax
0x18002d964  xor     ebx, ebx
0x18002d966  mov     [rbp+57h+TokenHandle], rcx
0x18002d96a  mov     r14, rdx
0x18002d96d  mov     [rbp+57h+TokenInformationLength], ebx
0x18002d970  mov     rsi, rcx
0x18002d973  mov     rdi, rcx
0x18002d976  xor     edx, edx; Val
0x18002d978  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18002d97c  lea     r8d, [rbx+58h]; Size
0x18002d980  call    memset_0
0x18002d985  mov     [r14], bl
0x18002d988  test    rdi, rdi
0x18002d98b  jz      loc_18002DA48
0x18002d991  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18002d997  lea     rax, [rbp+57h+TokenInformationLength]
0x18002d99b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002d99f  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002d9a4  mov     rcx, rdi; TokenHandle
0x18002d9a7  lea     edx, [r9-3Fh]; TokenInformationClass
0x18002d9ab  call    cs:__imp_NtQueryInformationToken
0x18002d9b1  mov     edi, eax
0x18002d9b3  test    eax, eax
0x18002d9b5  jns     short loc_18002D9FA
0x18002d9b7  cmp     eax, 0C0000023h
0x18002d9bc  jz      loc_18002DA6E
0x18002d9c2  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18002d9c6  cmp     rcx, rsi
0x18002d9c9  jnz     loc_18002DAC7
0x18002d9cf  test    rbx, rbx
0x18002d9d2  jnz     short loc_18002DA25
0x18002d9d4  mov     eax, edi
0x18002d9d6  mov     rcx, [rbp+57h+var_20]
0x18002d9da  xor     rcx, rsp; StackCookie
0x18002d9dd  call    __security_check_cookie
0x18002d9e2  lea     r11, [rsp+0C0h+var_10]
0x18002d9ea  mov     rbx, [r11+30h]
0x18002d9ee  mov     rsi, [r11+38h]
0x18002d9f2  mov     rsp, r11
0x18002d9f5  pop     r14
0x18002d9f7  pop     rdi
0x18002d9f8  pop     rbp
0x18002d9f9  retn
0x18002d9fa  lea     rbx, [rbp+57h+TokenInformation]
0x18002d9fe  mov     rcx, [rbx]; Sid
0x18002da01  call    cs:__imp_RtlSubAuthorityCountSid
0x18002da07  mov     cl, [rax]
0x18002da09  dec     cl
0x18002da0b  movzx   edx, cl; SubAuthority
0x18002da0e  mov     rcx, [rbx]; Sid
0x18002da11  call    cs:__imp_RtlSubAuthoritySid
0x18002da17  cmp     dword ptr [rax], 1000h
0x18002da1d  jbe     short loc_18002D9C2
0x18002da1f  mov     byte ptr [r14], 1
0x18002da23  jmp     short loc_18002D9C2
0x18002da25  lea     rax, [rbp+57h+TokenInformation]
0x18002da29  cmp     rbx, rax
0x18002da2c  jz      short loc_18002D9D4
0x18002da2e  mov     rcx, gs:60h
0x18002da37  mov     r8, rbx; P
0x18002da3a  xor     edx, edx; Flags
0x18002da3c  mov     rcx, [rcx+30h]; HeapHandle
0x18002da40  call    cs:__imp_RtlFreeHeap
0x18002da46  jmp     short loc_18002D9D4
0x18002da48  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18002da4c  mov     edx, 8; DesiredAccess
0x18002da51  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18002da55  call    cs:__imp_NtOpenProcessToken
0x18002da5b  mov     edi, eax
0x18002da5d  test    eax, eax
0x18002da5f  js      loc_18002D9C2
0x18002da65  mov     rdi, [rbp+57h+TokenHandle]
0x18002da69  jmp     loc_18002D991
0x18002da6e  mov     rcx, gs:60h
0x18002da77  xor     edx, edx; Flags
0x18002da79  mov     r8d, [rbp+57h+TokenInformationLength]; Size
0x18002da7d  mov     rcx, [rcx+30h]; HeapHandle
0x18002da81  call    cs:__imp_RtlAllocateHeap
0x18002da87  mov     rbx, rax
0x18002da8a  test    rax, rax
0x18002da8d  jnz     short loc_18002DA99
0x18002da8f  mov     edi, 0C000009Ah
0x18002da94  jmp     loc_18002D9C2
0x18002da99  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18002da9d  lea     rax, [rbp+57h+TokenInformationLength]
0x18002daa1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002daa5  mov     r8, rbx; TokenInformation
0x18002daa8  mov     edx, 19h; TokenInformationClass
0x18002daad  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18002dab2  call    cs:__imp_NtQueryInformationToken
0x18002dab8  mov     edi, eax
0x18002daba  test    eax, eax
0x18002dabc  js      loc_18002D9C2
0x18002dac2  jmp     loc_18002D9FE
0x18002dac7  call    cs:__imp_NtClose
0x18002dacd  jmp     loc_18002D9CF
```
