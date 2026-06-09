# DirectoryIsNotWritableBySid

- ea: `0x140009a08`
- end: `0x140009b49`
- name: `DirectoryIsNotWritableBySid`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140008f78`

## callees

- `0x140009a08`
- `0x14000a3b4`
- `0x14000aaf4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140009b2a`
- `KERNEL32!CloseHandle` at `0x140009b2a`
- `KERNEL32!LocalFree` at `0x140009b1b`
- `KERNEL32!LocalFree` at `0x140009b1b`
- `KERNEL32!CreateFileW` at `0x140009a3a`
- `KERNEL32!CreateFileW` at `0x140009a3a`
- `AUTHZ!AuthzFreeResourceManager` at `0x140009b0a`
- `AUTHZ!AuthzFreeResourceManager` at `0x140009b0a`
- `AUTHZ!AuthzFreeContext` at `0x140009af9`
- `AUTHZ!AuthzFreeContext` at `0x140009af9`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x140009acf`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x140009acf`
- `AUTHZ!AuthzInitializeResourceManager` at `0x140009a97`
- `AUTHZ!AuthzInitializeResourceManager` at `0x140009a97`

## pseudocode

```c
__int64 __fastcall DirectoryIsNotWritableBySid(const WCHAR *a1)
{
  HANDLE FileW; // rax
  void *v2; // rsi

  FileW = CreateFileW(a1, 0x20000u, 0, 0, 3u, 0x2000000u, 0);
  v2 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    GetSecurityDescriptor(FileW);
    CloseHandle(v2);
  }
  return 0;
}

```

## disassembly

```asm
0x140009a08  mov     rax, rsp
0x140009a0b  mov     [rax+8], rbp
0x140009a0f  mov     [rax+10h], rsi
0x140009a13  push    rdi
0x140009a14  sub     rsp, 50h
0x140009a18  mov     rbp, rdx
0x140009a1b  xor     edi, edi
0x140009a1d  mov     [rax-28h], rdi
0x140009a21  xor     r9d, r9d; lpSecurityAttributes
0x140009a24  mov     dword ptr [rax-30h], 2000000h
0x140009a2b  xor     r8d, r8d; dwShareMode
0x140009a2e  mov     edx, 20000h; dwDesiredAccess
0x140009a33  mov     dword ptr [rax-38h], 3
0x140009a3a  call    cs:__imp_CreateFileW
0x140009a41  nop     dword ptr [rax+rax+00h]
0x140009a46  mov     rsi, rax
0x140009a49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140009a4d  jz      loc_140009B36
0x140009a53  lea     rdx, [rsp+58h+hMem]
0x140009a58  mov     [rsp+58h+hMem], rdi
0x140009a5d  mov     rcx, rax; Handle
0x140009a60  call    GetSecurityDescriptor
0x140009a65  test    eax, eax
0x140009a67  js      loc_140009B27
0x140009a6d  cmp     [rsp+58h+hMem], rdi
0x140009a72  jz      loc_140009B27
0x140009a78  lea     rax, [rsp+58h+hAuthzResourceManager]
0x140009a7d  mov     [rsp+58h+hAuthzResourceManager], rdi
0x140009a82  mov     [rsp+58h+phAuthzResourceManager], rax; phAuthzResourceManager
0x140009a87  lea     ecx, [rdi+1]; Flags
0x140009a8a  xor     r9d, r9d; pfnFreeDynamicGroups
0x140009a8d  mov     [rsp+58h+szResourceManagerName], rdi; szResourceManagerName
0x140009a92  xor     r8d, r8d; pfnComputeDynamicGroups
0x140009a95  xor     edx, edx; pfnDynamicAccessCheck
0x140009a97  call    cs:__imp_AuthzInitializeResourceManager
0x140009a9e  nop     dword ptr [rax+rax+00h]
0x140009aa3  test    eax, eax
0x140009aa5  jz      short loc_140009B16
0x140009aa7  mov     r8, [rsp+58h+hAuthzResourceManager]; hAuthzResourceManager
0x140009aac  lea     rcx, [rsp+58h+hAuthzClientContext]
0x140009ab1  xor     eax, eax
0x140009ab3  mov     [rsp+58h+phAuthzClientContext], rcx; phAuthzClientContext
0x140009ab8  mov     [rsp+58h+phAuthzResourceManager], rax; DynamicGroupArgs
0x140009abd  xor     ecx, ecx; Flags
0x140009abf  xor     r9d, r9d; pExpirationTime
0x140009ac2  mov     [rsp+58h+szResourceManagerName], rax; Identifier
0x140009ac7  mov     rdx, rbp; UserSid
0x140009aca  mov     [rsp+58h+hAuthzClientContext], rax
0x140009acf  call    cs:__imp_AuthzInitializeContextFromSid
0x140009ad6  nop     dword ptr [rax+rax+00h]
0x140009adb  test    eax, eax
0x140009add  jz      short loc_140009B05
0x140009adf  mov     rdx, [rsp+58h+hMem]; pSecurityDescriptor
0x140009ae4  mov     rcx, [rsp+58h+hAuthzClientContext]; hAuthzClientContext
0x140009ae9  call    PrincipalHasWriteAccess
0x140009aee  mov     rcx, [rsp+58h+hAuthzClientContext]; hAuthzClientContext
0x140009af3  test    eax, eax
0x140009af5  setz    dil
0x140009af9  call    cs:__imp_AuthzFreeContext
0x140009b00  nop     dword ptr [rax+rax+00h]
0x140009b05  mov     rcx, [rsp+58h+hAuthzResourceManager]; hAuthzResourceManager
0x140009b0a  call    cs:__imp_AuthzFreeResourceManager
0x140009b11  nop     dword ptr [rax+rax+00h]
0x140009b16  mov     rcx, [rsp+58h+hMem]; hMem
0x140009b1b  call    cs:__imp_LocalFree
0x140009b22  nop     dword ptr [rax+rax+00h]
0x140009b27  mov     rcx, rsi; hObject
0x140009b2a  call    cs:__imp_CloseHandle
0x140009b31  nop     dword ptr [rax+rax+00h]
0x140009b36  mov     rbp, [rsp+58h+arg_0]
0x140009b3b  mov     eax, edi
0x140009b3d  mov     rsi, [rsp+58h+arg_8]
0x140009b42  add     rsp, 50h
0x140009b46  pop     rdi
0x140009b47  retn
```
