# SetFilePathFullControlByTrustedAC(ushort const *,bool,ushort const *)

- ea: `0x180065880`
- end: `0x180065931`
- name: `?SetFilePathFullControlByTrustedAC@@YAJPEBG_N0@Z`
- size: `177`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callees

- `0x18004ae00`
- `0x180065880`
- `0x180065938`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065908`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065908`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065900`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065900`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800658b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800658b7`

## pseudocode

```c
__int64 __fastcall SetFilePathFullControlByTrustedAC(const unsigned __int16 *a1, char a2, const unsigned __int16 *a3)
{
  HANDLE FileW; // rdi
  int LastError; // ebx
  bool v8; // [rsp+20h] [rbp-28h]
  void *v9; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(a1, 0xE0000u, 0, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    v9 = 0;
    LastError = SetTrustedACSid(a2, a3, &v9);
    if ( !LastError )
      LastError = SetHandleAccessWithInheritance(FileW, SE_FILE_OBJECT, v9, 0x1F01FFu, v8);
    CloseHandle(FileW);
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180065880  mov     rax, rsp
0x180065883  mov     [rax+8], rbx
0x180065887  mov     [rax+10h], rsi
0x18006588b  push    rdi
0x18006588c  sub     rsp, 40h
0x180065890  mov     qword ptr [rax-18h], 0
0x180065898  mov     rbx, r8
0x18006589b  mov     sil, dl
0x18006589e  mov     dword ptr [rax-20h], 2000000h
0x1800658a5  xor     r8d, r8d; dwShareMode
0x1800658a8  mov     dword ptr [rax-28h], 3
0x1800658af  mov     edx, 0E0000h; dwDesiredAccess
0x1800658b4  xor     r9d, r9d; lpSecurityAttributes
0x1800658b7  call    cs:__imp_CreateFileW
0x1800658bd  mov     rdi, rax
0x1800658c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800658c4  jz      short loc_180065908
0x1800658c6  lea     r8, [rsp+48h+arg_18]
0x1800658cb  mov     [rsp+48h+arg_18], 0
0x1800658d4  mov     rdx, rbx
0x1800658d7  mov     cl, sil
0x1800658da  call    _SetTrustedACSid
0x1800658df  mov     ebx, eax
0x1800658e1  test    eax, eax
0x1800658e3  jnz     short loc_1800658FD
0x1800658e5  mov     r8, [rsp+48h+arg_18]; void *
0x1800658ea  lea     edx, [rax+1]; ObjectType
0x1800658ed  mov     r9d, 1F01FFh; unsigned int
0x1800658f3  mov     rcx, rdi; handle
0x1800658f6  call    SetHandleAccessWithInheritance
0x1800658fb  mov     ebx, eax
0x1800658fd  mov     rcx, rdi; hObject
0x180065900  call    cs:__imp_CloseHandle
0x180065906  jmp     short loc_180065910
0x180065908  call    cs:__imp_GetLastError
0x18006590e  mov     ebx, eax
0x180065910  test    ebx, ebx
0x180065912  jz      short loc_18006591F
0x180065914  jle     short loc_18006591F
0x180065916  movzx   ebx, bx
0x180065919  or      ebx, 80070000h
0x18006591f  mov     rsi, [rsp+48h+arg_8]
0x180065924  mov     eax, ebx
0x180065926  mov     rbx, [rsp+48h+arg_0]
0x18006592b  add     rsp, 40h
0x18006592f  pop     rdi
0x180065930  retn
```
