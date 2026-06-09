# PsmSrvGetSessionInfo

- ea: `0x18002a4f0`
- end: `0x18002a5df`
- name: `PsmSrvGetSessionInfo`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18002a4f0`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x18002a556`
- `ntdll!NtDuplicateObject` at `0x18002a556`
- `ntdll!NtClose` at `0x18002a5b8`
- `ntdll!NtClose` at `0x18002a5c7`
- `ntdll!NtClose` at `0x18002a5b8`
- `ntdll!NtClose` at `0x18002a5c7`
- `ntdll!NtOpenProcessTokenEx` at `0x18002a577`
- `ntdll!NtOpenProcessTokenEx` at `0x18002a577`
- `ntdll!NtQueryInformationToken` at `0x18002a59e`
- `ntdll!NtQueryInformationToken` at `0x18002a59e`

## pseudocode

```c
__int64 __fastcall PsmSrvGetSessionInfo(__int64 a1, void *a2, _DWORD *a3)
{
  NTSTATUS v5; // ebx
  void *v6; // rcx
  void *TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  void *TargetHandle; // [rsp+48h] [rbp-8h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+20h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp+28h] BYREF

  TargetHandle = 0;
  TokenInformation = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  if ( !a3 )
    return 3221225713LL;
  v5 = NtDuplicateObject(*(HANDLE *)(a1 + 16), a2, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &TargetHandle, 0x101000u, 0, 0);
  if ( v5 >= 0 )
  {
    v6 = TargetHandle;
    *a3 = 0;
    v5 = NtOpenProcessTokenEx(v6, 8u, 0, &TokenHandle);
    if ( v5 >= 0 )
    {
      v5 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
      if ( v5 >= 0 )
        *a3 = TokenInformation;
    }
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( TargetHandle )
    NtClose(TargetHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a4f0  mov     [rsp-8+arg_0], rbx
0x18002a4f5  mov     [rsp-8+arg_8], rdi
0x18002a4fa  push    rbp
0x18002a4fb  mov     rbp, rsp
0x18002a4fe  sub     rsp, 50h
0x18002a502  mov     [rbp+TargetHandle], 0
0x18002a50a  mov     rdi, r8
0x18002a50d  mov     [rbp+TokenInformation], 0
0x18002a514  mov     [rbp+TokenHandle], 0
0x18002a51c  mov     [rbp+ReturnLength], 0
0x18002a523  test    r8, r8
0x18002a526  jnz     short loc_18002A532
0x18002a528  mov     eax, 0C00000F1h
0x18002a52d  jmp     loc_18002A5CF
0x18002a532  mov     rcx, [rcx+10h]; SourceProcessHandle
0x18002a536  lea     r9, [rbp+TargetHandle]; TargetHandle
0x18002a53a  mov     [rsp+50h+Options], 0; Options
0x18002a542  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x18002a546  mov     [rsp+50h+HandleAttributes], 0; HandleAttributes
0x18002a54e  mov     [rsp+50h+DesiredAccess], 101000h; DesiredAccess
0x18002a556  call    cs:__imp_NtDuplicateObject
0x18002a55c  mov     ebx, eax
0x18002a55e  test    eax, eax
0x18002a560  js      short loc_18002A5AF
0x18002a562  mov     rcx, [rbp+TargetHandle]; ProcessHandle
0x18002a566  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002a56a  xor     r8d, r8d; HandleAttributes
0x18002a56d  mov     dword ptr [rdi], 0
0x18002a573  lea     edx, [r8+8]; DesiredAccess
0x18002a577  call    cs:__imp_NtOpenProcessTokenEx
0x18002a57d  mov     ebx, eax
0x18002a57f  test    eax, eax
0x18002a581  js      short loc_18002A5AF
0x18002a583  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002a587  lea     rax, [rbp+ReturnLength]
0x18002a58b  mov     r9d, 4; TokenInformationLength
0x18002a591  mov     qword ptr [rsp+50h+DesiredAccess], rax; ReturnLength
0x18002a596  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002a59a  lea     edx, [r9+8]; TokenInformationClass
0x18002a59e  call    cs:__imp_NtQueryInformationToken
0x18002a5a4  mov     ebx, eax
0x18002a5a6  test    eax, eax
0x18002a5a8  js      short loc_18002A5AF
0x18002a5aa  mov     eax, [rbp+TokenInformation]
0x18002a5ad  mov     [rdi], eax
0x18002a5af  mov     rcx, [rbp+TokenHandle]; Handle
0x18002a5b3  test    rcx, rcx
0x18002a5b6  jz      short loc_18002A5BE
0x18002a5b8  call    cs:__imp_NtClose
0x18002a5be  mov     rcx, [rbp+TargetHandle]; Handle
0x18002a5c2  test    rcx, rcx
0x18002a5c5  jz      short loc_18002A5CD
0x18002a5c7  call    cs:__imp_NtClose
0x18002a5cd  mov     eax, ebx
0x18002a5cf  mov     rbx, [rsp+50h+arg_0]
0x18002a5d4  mov     rdi, [rsp+50h+arg_8]
0x18002a5d9  add     rsp, 50h
0x18002a5dd  pop     rbp
0x18002a5de  retn
```
