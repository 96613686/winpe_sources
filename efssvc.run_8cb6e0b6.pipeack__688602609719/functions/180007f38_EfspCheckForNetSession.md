# EfspCheckForNetSession

- ea: `0x180007f38`
- end: `0x1800080bb`
- name: `EfspCheckForNetSession`
- size: `387`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800059a0`
- `0x180005d00`
- `0x1800060c0`
- `0x1800069d0`
- `0x180006d80`
- `0x1800070d0`
- `0x1800072b0`
- `0x180007530`
- `0x1800080c4`

## callees

- `0x180007f38`
- `0x18000d1c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000804c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000804c`
- `ntdll!NtQueryInformationToken` at `0x180007fbc`
- `ntdll!NtQueryInformationToken` at `0x18000801c`
- `ntdll!NtQueryInformationToken` at `0x180007fbc`
- `ntdll!NtQueryInformationToken` at `0x18000801c`
- `ntdll!RtlAllocateHeap` at `0x180007feb`
- `ntdll!RtlAllocateHeap` at `0x180007feb`
- `ntdll!RtlFreeHeap` at `0x180008079`
- `ntdll!RtlFreeHeap` at `0x180008079`
- `ntdll!NtClose` at `0x18000808f`
- `ntdll!NtClose` at `0x18000808f`
- `ntdll!NtOpenThreadToken` at `0x180007f89`
- `ntdll!NtOpenThreadToken` at `0x180007f89`

## pseudocode

```c
__int64 EfspCheckForNetSession()
{
  unsigned int v0; // esi
  NTSTATUS v1; // eax
  PVOID Heap; // rbx
  int *v3; // r14
  int v4; // edi
  ULONG TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE TokenInformation[1024]; // [rsp+40h] [rbp-C0h] BYREF

  v0 = 1;
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle) >= 0 )
  {
    v1 = NtQueryInformationToken(TokenHandle, TokenGroups, TokenInformation, 0x400u, &TokenInformationLength);
    if ( v1 >= 0 )
    {
      Heap = 0;
      v3 = (int *)TokenInformation;
    }
    else
    {
      if ( v1 != -1073741789 )
        goto LABEL_14;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TokenInformationLength);
      if ( !Heap )
        goto LABEL_14;
      if ( NtQueryInformationToken(TokenHandle, TokenGroups, Heap, TokenInformationLength, &TokenInformationLength) < 0 )
      {
LABEL_13:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        goto LABEL_14;
      }
      v3 = (int *)Heap;
    }
    v4 = *v3;
    while ( --v4 >= 0 )
    {
      if ( IsWellKnownSid(*(PSID *)&v3[4 * v4 + 2], WinNetworkSid) )
        goto LABEL_12;
    }
    v0 = 0;
LABEL_12:
    if ( Heap )
      goto LABEL_13;
  }
LABEL_14:
  if ( TokenHandle )
    NtClose(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x180007f38  push    rbp
0x180007f3a  push    rbx
0x180007f3b  push    rsi
0x180007f3c  push    rdi
0x180007f3d  push    r14
0x180007f3f  lea     rbp, [rsp-350h]
0x180007f47  sub     rsp, 450h
0x180007f4e  mov     rax, cs:__security_cookie
0x180007f55  xor     rax, rsp
0x180007f58  mov     [rbp+370h+var_30], rax
0x180007f5f  mov     esi, 1
0x180007f64  mov     [rsp+470h+TokenHandle], 0
0x180007f6d  lea     r9, [rsp+470h+TokenHandle]; TokenHandle
0x180007f72  mov     [rsp+470h+TokenInformationLength], 0
0x180007f7a  mov     r8b, sil; OpenAsSelf
0x180007f7d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180007f84  lea     ebx, [rsi+7]
0x180007f87  mov     edx, ebx; DesiredAccess
0x180007f89  call    cs:__imp_NtOpenThreadToken
0x180007f90  nop     dword ptr [rax+rax+00h]
0x180007f95  test    eax, eax
0x180007f97  js      loc_180008085
0x180007f9d  mov     rcx, [rsp+470h+TokenHandle]; TokenHandle
0x180007fa2  lea     rax, [rsp+470h+TokenInformationLength]
0x180007fa7  lea     edi, [rsi+1]
0x180007faa  mov     [rsp+470h+ReturnLength], rax; ReturnLength
0x180007faf  mov     edx, edi; TokenInformationClass
0x180007fb1  lea     r8, [rsp+470h+TokenInformation]; TokenInformation
0x180007fb6  mov     r9d, 400h; TokenInformationLength
0x180007fbc  call    cs:__imp_NtQueryInformationToken
0x180007fc3  nop     dword ptr [rax+rax+00h]
0x180007fc8  test    eax, eax
0x180007fca  jns     short loc_180008031
0x180007fcc  cmp     eax, 0C0000023h
0x180007fd1  jnz     loc_180008085
0x180007fd7  mov     rcx, gs:60h
0x180007fe0  mov     edx, ebx; Flags
0x180007fe2  mov     r8d, [rsp+470h+TokenInformationLength]; Size
0x180007fe7  mov     rcx, [rcx+30h]; HeapHandle
0x180007feb  call    cs:__imp_RtlAllocateHeap
0x180007ff2  nop     dword ptr [rax+rax+00h]
0x180007ff7  mov     rbx, rax
0x180007ffa  test    rax, rax
0x180007ffd  jz      loc_180008085
0x180008003  mov     r9d, [rsp+470h+TokenInformationLength]; TokenInformationLength
0x180008008  lea     rax, [rsp+470h+TokenInformationLength]
0x18000800d  mov     rcx, [rsp+470h+TokenHandle]; TokenHandle
0x180008012  mov     r8, rbx; TokenInformation
0x180008015  mov     edx, edi; TokenInformationClass
0x180008017  mov     [rsp+470h+ReturnLength], rax; ReturnLength
0x18000801c  call    cs:__imp_NtQueryInformationToken
0x180008023  nop     dword ptr [rax+rax+00h]
0x180008028  test    eax, eax
0x18000802a  js      short loc_180008067
0x18000802c  mov     r14, rbx
0x18000802f  jmp     short loc_180008038
0x180008031  xor     ebx, ebx
0x180008033  lea     r14, [rsp+470h+TokenInformation]
0x180008038  mov     edi, [r14]
0x18000803b  jmp     short loc_18000805C
0x18000803d  mov     ecx, edi
0x18000803f  mov     edx, 9; WellKnownSidType
0x180008044  add     rcx, rcx
0x180008047  mov     rcx, [r14+rcx*8+8]; pSid
0x18000804c  call    cs:__imp_IsWellKnownSid
0x180008053  nop     dword ptr [rax+rax+00h]
0x180008058  test    eax, eax
0x18000805a  jnz     short loc_180008062
0x18000805c  sub     edi, esi
0x18000805e  jns     short loc_18000803D
0x180008060  xor     esi, esi
0x180008062  test    rbx, rbx
0x180008065  jz      short loc_180008085
0x180008067  mov     rcx, gs:60h
0x180008070  mov     r8, rbx; P
0x180008073  xor     edx, edx; Flags
0x180008075  mov     rcx, [rcx+30h]; HeapHandle
0x180008079  call    cs:__imp_RtlFreeHeap
0x180008080  nop     dword ptr [rax+rax+00h]
0x180008085  mov     rcx, [rsp+470h+TokenHandle]; Handle
0x18000808a  test    rcx, rcx
0x18000808d  jz      short loc_18000809B
0x18000808f  call    cs:__imp_NtClose
0x180008096  nop     dword ptr [rax+rax+00h]
0x18000809b  mov     eax, esi
0x18000809d  mov     rcx, [rbp+370h+var_30]
0x1800080a4  xor     rcx, rsp; StackCookie
0x1800080a7  call    __security_check_cookie
0x1800080ac  add     rsp, 450h
0x1800080b3  pop     r14
0x1800080b5  pop     rdi
0x1800080b6  pop     rsi
0x1800080b7  pop     rbx
0x1800080b8  pop     rbp
0x1800080b9  retn
```
