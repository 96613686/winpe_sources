# CsrGetProcessLuid

- ea: `0x180006700`
- end: `0x180006812`
- name: `CsrGetProcessLuid`
- size: `274`
- prototype: `NTSTATUS __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180006700`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180006754`
- `ntdll!NtOpenProcessToken` at `0x180006754`
- `ntdll!NtQueryInformationToken` at `0x18000678b`
- `ntdll!NtQueryInformationToken` at `0x18000678b`
- `ntdll!NtClose` at `0x18000679e`
- `ntdll!NtClose` at `0x18000679e`
- `ntdll!NtOpenThreadToken` at `0x1800067eb`
- `ntdll!NtOpenThreadToken` at `0x1800067eb`

## pseudocode

```c
NTSTATUS __fastcall CsrGetProcessLuid(__int64 a1, _QWORD *a2)
{
  NTSTATUS result; // eax
  NTSTATUS v4; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-58h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-50h] BYREF
  _OWORD TokenInformation[3]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v8; // [rsp+70h] [rbp-18h]

  TokenHandle = (void *)-1LL;
  v8 = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( a1 )
  {
LABEL_2:
    result = NtOpenProcessToken((HANDLE)a1, 8u, &TokenHandle);
    if ( result < 0 )
      return result;
    goto LABEL_3;
  }
  result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( result < 0 )
  {
    if ( result != -1073741700 )
      return result;
    a1 = -1;
    goto LABEL_2;
  }
LABEL_3:
  v4 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
  NtClose(TokenHandle);
  if ( v4 >= 0 )
    *a2 = *((_QWORD *)&TokenInformation[0] + 1);
  return v4;
}

```

## disassembly

```asm
0x180006700  push    rdi
0x180006702  sub     rsp, 80h
0x180006709  mov     rax, cs:__security_cookie
0x180006710  xor     rax, rsp
0x180006713  mov     [rsp+88h+var_10], rax
0x180006718  xor     eax, eax
0x18000671a  mov     [rsp+88h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180006723  mov     [rsp+88h+var_18], rax
0x180006728  xorps   xmm0, xmm0
0x18000672b  mov     [rsp+88h+var_50], eax
0x18000672f  mov     rdi, rdx
0x180006732  movups  [rsp+88h+TokenInformation], xmm0
0x180006737  movups  [rsp+88h+var_38], xmm0
0x18000673c  movups  [rsp+88h+var_28], xmm0
0x180006741  test    rcx, rcx
0x180006744  jz      loc_1800067D7
0x18000674a  lea     r8, [rsp+88h+TokenHandle]; TokenHandle
0x18000674f  mov     edx, 8; DesiredAccess
0x180006754  call    cs:__imp_NtOpenProcessToken
0x18000675b  nop     dword ptr [rax+rax+00h]
0x180006760  test    eax, eax
0x180006762  js      short loc_1800067C0
0x180006764  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x180006769  lea     rax, [rsp+88h+var_50]
0x18000676e  mov     r9d, 38h ; '8'; TokenInformationLength
0x180006774  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x180006779  lea     r8, [rsp+88h+TokenInformation]; TokenInformation
0x18000677e  mov     [rsp+88h+arg_10], rbx
0x180006786  mov     edx, 0Ah; TokenInformationClass
0x18000678b  call    cs:__imp_NtQueryInformationToken
0x180006792  nop     dword ptr [rax+rax+00h]
0x180006797  mov     rcx, [rsp+88h+TokenHandle]; Handle
0x18000679c  mov     ebx, eax
0x18000679e  call    cs:__imp_NtClose
0x1800067a5  nop     dword ptr [rax+rax+00h]
0x1800067aa  test    ebx, ebx
0x1800067ac  js      short loc_1800067B6
0x1800067ae  mov     rax, qword ptr [rsp+88h+TokenInformation+8]
0x1800067b3  mov     [rdi], rax
0x1800067b6  mov     eax, ebx
0x1800067b8  mov     rbx, [rsp+88h+arg_10]
0x1800067c0  mov     rcx, [rsp+88h+var_10]
0x1800067c5  xor     rcx, rsp; StackCookie
0x1800067c8  call    __security_check_cookie
0x1800067cd  add     rsp, 80h
0x1800067d4  pop     rdi
0x1800067d5  retn
0x1800067d7  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x1800067dc  xor     r8d, r8d; OpenAsSelf
0x1800067df  mov     edx, 8; DesiredAccess
0x1800067e4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800067eb  call    cs:__imp_NtOpenThreadToken
0x1800067f2  nop     dword ptr [rax+rax+00h]
0x1800067f7  test    eax, eax
0x1800067f9  jns     loc_180006764
0x1800067ff  cmp     eax, 0C000007Ch
0x180006804  jnz     short loc_1800067C0
0x180006806  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000680d  jmp     loc_18000674A
```
