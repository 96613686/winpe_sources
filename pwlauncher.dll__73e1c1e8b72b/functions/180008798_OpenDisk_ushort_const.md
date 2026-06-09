# OpenDisk(ushort const *)

- ea: `0x180008798`
- end: `0x180008864`
- name: `?OpenDisk@@YAPEAXPEBG@Z`
- size: `204`
- prototype: `HANDLE __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005638`

## callees

- `0x180008798`
- `0x180008ac8`
- `0x180008cf0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008815`
- `KERNEL32!GetLastError` at `0x180008815`
- `KERNEL32!CreateFileW` at `0x1800087fa`
- `KERNEL32!CreateFileW` at `0x1800087fa`

## pseudocode

```c
HANDLE __fastcall OpenDisk(LPCWSTR lpFileName)
{
  HANDLE FileW; // rbx
  int v3; // r8d
  int v4; // r9d
  const char *v5; // rcx
  char hTemplateFile; // [rsp+30h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    hTemplateFile = GetLastError();
    v5 = "Success";
    if ( !FileW )
      v5 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, v3, v4, 182, (__int64)v5, hTemplateFile);
  }
  return FileW;
}

```

## disassembly

```asm
0x180008798  mov     [rsp+arg_0], rbx
0x18000879d  push    rdi
0x18000879e  sub     rsp, 40h
0x1800087a2  mov     rbx, rcx
0x1800087a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087ac  lea     rdi, WPP_GLOBAL_Control
0x1800087b3  cmp     rcx, rdi
0x1800087b6  jz      short loc_1800087D3
0x1800087b8  test    byte ptr [rcx+1Ch], 8
0x1800087bc  jz      short loc_1800087D3
0x1800087be  mov     rcx, [rcx+10h]
0x1800087c2  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800087c9  mov     edx, 59h ; 'Y'
0x1800087ce  call    WPP_SF_
0x1800087d3  mov     qword ptr [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800087dc  mov     r8d, 3; dwShareMode
0x1800087e2  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800087ea  xor     r9d, r9d; lpSecurityAttributes
0x1800087ed  mov     edx, 80000000h; dwDesiredAccess
0x1800087f2  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800087f7  mov     rcx, rbx; lpFileName
0x1800087fa  call    cs:__imp_CreateFileW
0x180008800  mov     rbx, rax
0x180008803  mov     rax, cs:WPP_GLOBAL_Control
0x18000880a  cmp     rax, rdi
0x18000880d  jz      short loc_180008856
0x18000880f  test    byte ptr [rax+1Ch], 4
0x180008813  jz      short loc_180008856
0x180008815  call    cs:__imp_GetLastError
0x18000881b  lea     rdx, aFailure; "Failure"
0x180008822  mov     dword ptr [rsp+48h+hTemplateFile], eax
0x180008826  test    rbx, rbx
0x180008829  lea     rcx, aSuccess; "Success"
0x180008830  cmovz   rcx, rdx
0x180008834  mov     edx, 5Ah ; 'Z'
0x180008839  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rcx
0x18000883e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008845  mov     [rsp+48h+dwCreationDisposition], 4B6h
0x18000884d  mov     rcx, [rcx+10h]
0x180008851  call    WPP_SF_sdsd
0x180008856  mov     rax, rbx
0x180008859  mov     rbx, [rsp+48h+arg_0]
0x18000885e  add     rsp, 40h
0x180008862  pop     rdi
0x180008863  retn
```
