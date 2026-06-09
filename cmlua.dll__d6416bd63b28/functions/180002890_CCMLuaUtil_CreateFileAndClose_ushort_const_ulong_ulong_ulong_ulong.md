# CCMLuaUtil::CreateFileAndClose(ushort const *,ulong,ulong,ulong,ulong)

- ea: `0x180002890`
- end: `0x1800028f7`
- name: `?CreateFileAndClose@CCMLuaUtil@@UEAAJPEBGKKKK@Z`
- size: `103`
- prototype: `__int64 __fastcall(CCMLuaUtil *this, const unsigned __int16 *, DWORD, DWORD, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180002890`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800028c1`
- `KERNEL32!CreateFileW` at `0x1800028c1`
- `KERNEL32!GetLastError` at `0x1800028da`
- `KERNEL32!GetLastError` at `0x1800028da`
- `KERNEL32!CloseHandle` at `0x1800028d2`
- `KERNEL32!CloseHandle` at `0x1800028d2`

## pseudocode

```c
__int64 __fastcall CCMLuaUtil::CreateFileAndClose(
        CCMLuaUtil *this,
        const unsigned __int16 *a2,
        DWORD a3,
        DWORD a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  HANDLE FileW; // rax
  unsigned int v7; // ebx
  signed int LastError; // eax

  FileW = CreateFileW(a2, a3, a4, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v7 = 0;
    CloseHandle(FileW);
  }
  return v7;
}

```

## disassembly

```asm
0x180002890  push    rbx
0x180002892  sub     rsp, 40h
0x180002896  mov     eax, [rsp+48h+arg_28]
0x18000289a  mov     r10d, r9d
0x18000289d  mov     r11d, r8d
0x1800028a0  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800028a9  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800028ad  mov     rcx, rdx; lpFileName
0x1800028b0  mov     eax, [rsp+48h+arg_20]
0x1800028b4  mov     r8d, r10d; dwShareMode
0x1800028b7  mov     edx, r11d; dwDesiredAccess
0x1800028ba  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x1800028be  xor     r9d, r9d; lpSecurityAttributes
0x1800028c1  call    cs:__imp_CreateFileW
0x1800028c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800028cb  jz      short loc_1800028DA
0x1800028cd  xor     ebx, ebx
0x1800028cf  mov     rcx, rax; hObject
0x1800028d2  call    cs:__imp_CloseHandle
0x1800028d8  jmp     short loc_1800028EF
0x1800028da  call    cs:__imp_GetLastError
0x1800028e0  mov     ebx, eax
0x1800028e2  test    eax, eax
0x1800028e4  jle     short loc_1800028EF
0x1800028e6  movzx   ebx, ax
0x1800028e9  or      ebx, 80070000h
0x1800028ef  mov     eax, ebx
0x1800028f1  add     rsp, 40h
0x1800028f5  pop     rbx
0x1800028f6  retn
```
