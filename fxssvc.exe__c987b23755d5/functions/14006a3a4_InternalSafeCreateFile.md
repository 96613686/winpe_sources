# InternalSafeCreateFile

- ea: `0x14006a3a4`
- end: `0x14006a466`
- name: `InternalSafeCreateFile`
- size: `194`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, __int64, DWORD dwCreationDisposition, int)`
- caller_count: `17`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400064f0`
- `0x14000b8f4`
- `0x14000d79c`
- `0x14001c720`
- `0x14001cf70`
- `0x140020f80`
- `0x140021530`
- `0x140027a58`
- `0x140027f80`
- `0x140034ae4`
- `0x140036eb4`
- `0x14003a754`
- `0x1400507f4`
- `0x14006d8b0`
- `0x14006dddc`
- `0x14006e6dc`
- `0x140071d04`

## callees

- `0x140004b30`
- `0x14006a3a4`

## import_xrefs

- `KERNEL32!GetFileType` at `0x14006a432`
- `KERNEL32!GetFileType` at `0x14006a432`
- `KERNEL32!CreateFileW` at `0x14006a418`
- `KERNEL32!CreateFileW` at `0x14006a418`
- `KERNEL32!SetLastError` at `0x14006a44b`
- `KERNEL32!SetLastError` at `0x14006a44b`
- `KERNEL32!CloseHandle` at `0x14006a440`
- `KERNEL32!CloseHandle` at `0x14006a440`

## pseudocode

```c
__int64 __fastcall InternalSafeCreateFile(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        __int64 a4,
        DWORD dwCreationDisposition,
        int a6)
{
  HANDLE FileW; // rax
  void *v10; // rbx

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  }
  FileW = CreateFileW(lpFileName, dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, a6 | 0x102000u, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return -1;
  if ( GetFileType(FileW) != 1 )
  {
    CloseHandle(v10);
    SetLastError(0x65Eu);
    return -1;
  }
  return (__int64)v10;
}

```

## disassembly

```asm
0x14006a3a4  mov     [rsp+arg_0], rbx
0x14006a3a9  mov     [rsp+arg_8], rsi
0x14006a3ae  push    rdi
0x14006a3af  sub     rsp, 40h
0x14006a3b3  mov     ebx, r8d
0x14006a3b6  mov     edi, edx
0x14006a3b8  mov     rsi, rcx
0x14006a3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a3c2  lea     rax, WPP_GLOBAL_Control
0x14006a3c9  cmp     rcx, rax
0x14006a3cc  jz      short loc_14006A3EF
0x14006a3ce  test    byte ptr [rcx+1Ch], 2
0x14006a3d2  jz      short loc_14006A3EF
0x14006a3d4  cmp     byte ptr [rcx+19h], 5
0x14006a3d8  jb      short loc_14006A3EF
0x14006a3da  mov     rcx, [rcx+10h]
0x14006a3de  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006a3e5  mov     edx, 4Ah ; 'J'
0x14006a3ea  call    WPP_SF_
0x14006a3ef  mov     eax, [rsp+48h+arg_28]
0x14006a3f3  xor     r9d, r9d; lpSecurityAttributes
0x14006a3f6  or      eax, 102000h
0x14006a3fb  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14006a404  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14006a408  mov     r8d, ebx; dwShareMode
0x14006a40b  mov     eax, [rsp+48h+arg_20]
0x14006a40f  mov     edx, edi; dwDesiredAccess
0x14006a411  mov     rcx, rsi; lpFileName
0x14006a414  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x14006a418  call    cs:__imp_CreateFileW
0x14006a41e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14006a422  mov     rbx, rax
0x14006a425  cmp     rax, rdi
0x14006a428  jnz     short loc_14006A42F
0x14006a42a  mov     rax, rdi
0x14006a42d  jmp     short loc_14006A456
0x14006a42f  mov     rcx, rbx; hFile
0x14006a432  call    cs:__imp_GetFileType
0x14006a438  cmp     eax, 1
0x14006a43b  jz      short loc_14006A453
0x14006a43d  mov     rcx, rbx; hObject
0x14006a440  call    cs:__imp_CloseHandle
0x14006a446  mov     ecx, 65Eh; dwErrCode
0x14006a44b  call    cs:__imp_SetLastError
0x14006a451  jmp     short loc_14006A42A
0x14006a453  mov     rax, rbx
0x14006a456  mov     rbx, [rsp+48h+arg_0]
0x14006a45b  mov     rsi, [rsp+48h+arg_8]
0x14006a460  add     rsp, 40h
0x14006a464  pop     rdi
0x14006a465  retn
```
