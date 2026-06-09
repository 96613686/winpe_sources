# AppContainerRegistrationHelper::IsFileOrFolderPresent(ushort const *,_GUID const *,int *)

- ea: `0x18000a3e4`
- end: `0x18000a4cf`
- name: `?IsFileOrFolderPresent@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@PEAH@Z`
- size: `235`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004250`
- `0x180009a34`
- `0x180014bd0`

## callees

- `0x18000a3e4`
- `0x18000a540`
- `0x18000f440`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a41a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a41a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a447`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4be`

## string_xrefs

- `0x18000a48b`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::IsFileOrFolderPresent(WCHAR *a1, const struct _GUID *a2, int *a3)
{
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    *a3 = 1;
    if ( FileW )
      CloseHandle(FileW);
    return 0;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( (unsigned int)(LastError - 2) <= 1 )
  {
    *a3 = 0;
    return 0;
  }
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  else
    v10 = LastError;
  AppContainerRegistrationHelper::LogFailureWithContext(&AppModelAppContainerVerifyFolderFailure, a1, v10, a2);
  if ( !v9 )
    return 0;
  return wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x3EA,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
           (const char *)v9,
           (unsigned int)"Name %ls",
           (const char *)a1);
}

```

## disassembly

```asm
0x18000a3e4  push    rbx
0x18000a3e6  push    rbp
0x18000a3e7  push    rsi
0x18000a3e8  push    rdi
0x18000a3e9  sub     rsp, 48h
0x18000a3ed  mov     rdi, r8
0x18000a3f0  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000a3f9  mov     r8d, 3; dwShareMode
0x18000a3ff  mov     [rsp+68h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000a407  mov     rbp, rdx
0x18000a40a  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000a40f  xor     r9d, r9d; lpSecurityAttributes
0x18000a412  mov     edx, 80000000h; dwDesiredAccess
0x18000a417  mov     rsi, rcx
0x18000a41a  call    cs:__imp_CreateFileW
0x18000a421  nop     dword ptr [rax+rax+00h]
0x18000a426  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a42a  jz      short loc_18000A447
0x18000a42c  mov     dword ptr [rdi], 1
0x18000a432  test    rax, rax
0x18000a435  jnz     loc_18000A4BB
0x18000a43b  xor     eax, eax
0x18000a43d  add     rsp, 48h
0x18000a441  pop     rdi
0x18000a442  pop     rsi
0x18000a443  pop     rbp
0x18000a444  pop     rbx
0x18000a445  retn
0x18000a447  call    cs:__imp_GetLastError
0x18000a44e  nop     dword ptr [rax+rax+00h]
0x18000a453  mov     ebx, eax
0x18000a455  lea     ecx, [rax-2]
0x18000a458  cmp     ecx, 1
0x18000a45b  jbe     short loc_18000A4B3
0x18000a45d  test    eax, eax
0x18000a45f  jg      short loc_18000A4A6
0x18000a461  mov     r8d, eax; int
0x18000a464  mov     r9, rbp; struct _GUID *
0x18000a467  lea     rcx, AppModelAppContainerVerifyFolderFailure; struct _EVENT_DESCRIPTOR *
0x18000a46e  mov     rdx, rsi; unsigned __int16 *
0x18000a471  call    ?LogFailureWithContext@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@PEBGJPEBU_GUID@@@Z; AppContainerRegistrationHelper::LogFailureWithContext(_EVENT_DESCRIPTOR const *,ushort const *,long,_GUID const *)
0x18000a476  test    ebx, ebx
0x18000a478  jz      short loc_18000A43B
0x18000a47a  mov     rcx, [rsp+68h]; this
0x18000a47f  lea     rax, aNameLs; "Name %ls"
0x18000a486  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi; char *
0x18000a48b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a492  mov     r9d, ebx; char *
0x18000a495  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; unsigned int
0x18000a49a  mov     edx, 3EAh; void *
0x18000a49f  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000a4a4  jmp     short loc_18000A43D
0x18000a4a6  movzx   r8d, bx
0x18000a4aa  or      r8d, 80070000h
0x18000a4b1  jmp     short loc_18000A464
0x18000a4b3  mov     dword ptr [rdi], 0
0x18000a4b9  jmp     short loc_18000A43B
0x18000a4bb  mov     rcx, rax; hObject
0x18000a4be  call    cs:__imp_CloseHandle
0x18000a4c5  nop     dword ptr [rax+rax+00h]
0x18000a4ca  jmp     loc_18000A43B
```
