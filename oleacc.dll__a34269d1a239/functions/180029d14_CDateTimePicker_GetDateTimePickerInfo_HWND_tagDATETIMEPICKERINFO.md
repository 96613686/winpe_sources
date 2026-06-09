# CDateTimePicker::GetDateTimePickerInfo(HWND__ *,tagDATETIMEPICKERINFO *)

- ea: `0x180029d14`
- end: `0x180029e1f`
- name: `?GetDateTimePickerInfo@CDateTimePicker@@AEAAJPEAUHWND__@@PEAUtagDATETIMEPICKERINFO@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(CDateTimePicker *__hidden this, HWND, struct tagDATETIMEPICKERINFO *lpBuffer)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180029f60`
- `0x18002a160`
- `0x18002a320`
- `0x18002a610`
- `0x18002a9a0`

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x180029d14`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180029de7`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180029de7`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180029d78`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180029d78`

## pseudocode

```c
__int64 __fastcall CDateTimePicker::GetDateTimePickerInfo(
        CDateTimePicker *this,
        HWND a2,
        struct tagDATETIMEPICKERINFO *lpBuffer)
{
  void *v6; // rax
  void *v7; // rdi
  int v8; // ebx
  HANDLE hProcess; // [rsp+80h] [rbp+18h] BYREF
  __int64 v11; // [rsp+88h] [rbp+20h] BYREF

  hProcess = 0;
  lpBuffer->cbSize = 72;
  v6 = SharedAlloc(0x48u, a2, &hProcess);
  v7 = v6;
  if ( v6 )
  {
    v8 = -2147467259;
    if ( WriteProcessMemory(hProcess, v6, lpBuffer, 0x48u, 0) )
    {
      v11 = 0;
      v8 = CAccessible::AccSendMessageTimeout(this, 0, a2, 0x100Eu, 0, (__int64)v7, &v11);
      if ( v8 >= 0 && v11 && ReadProcessMemory(hProcess, v7, lpBuffer, 0x48u, 0) )
        v8 = 0;
    }
    SharedFree(v7, hProcess);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180029d14  mov     rax, rsp
0x180029d17  mov     [rax+8], rbx
0x180029d1b  push    rbp
0x180029d1c  push    rdi
0x180029d1d  push    r13
0x180029d1f  push    r14
0x180029d21  push    r15
0x180029d23  sub     rsp, 40h
0x180029d27  mov     r13d, 48h ; 'H'
0x180029d2d  mov     qword ptr [rax+18h], 0
0x180029d35  mov     [r8], r13d
0x180029d38  mov     r14, r8
0x180029d3b  mov     r15, rcx
0x180029d3e  lea     r8, [rax+18h]; void **
0x180029d42  mov     ecx, r13d; dwSize
0x180029d45  mov     rbp, rdx
0x180029d48  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x180029d4d  mov     rdi, rax
0x180029d50  test    rax, rax
0x180029d53  jz      loc_180029E06
0x180029d59  mov     rcx, [rsp+68h+hProcess]; hProcess
0x180029d61  mov     r9d, r13d; nSize
0x180029d64  mov     r8, r14; lpBuffer
0x180029d67  mov     [rsp+68h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x180029d70  mov     rdx, rax; lpBaseAddress
0x180029d73  mov     ebx, 80004005h
0x180029d78  call    cs:__imp_WriteProcessMemory
0x180029d7e  test    eax, eax
0x180029d80  jz      short loc_180029DF4
0x180029d82  lea     rax, [rsp+68h+arg_18]
0x180029d8a  mov     [rsp+68h+arg_18], 0
0x180029d96  mov     [rsp+68h+var_38], rax; __int64 *
0x180029d9b  mov     r9d, 100Eh; unsigned int
0x180029da1  mov     [rsp+68h+var_40], rdi; __int64
0x180029da6  mov     r8, rbp; HWND
0x180029da9  xor     edx, edx; bool
0x180029dab  mov     [rsp+68h+lpNumberOfBytesWritten], 0; unsigned __int64
0x180029db4  mov     rcx, r15; this
0x180029db7  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x180029dbc  mov     ebx, eax
0x180029dbe  test    eax, eax
0x180029dc0  js      short loc_180029DF4
0x180029dc2  cmp     [rsp+68h+arg_18], 0
0x180029dcb  jz      short loc_180029DF4
0x180029dcd  mov     rcx, [rsp+68h+hProcess]; hProcess
0x180029dd5  mov     r9d, r13d; nSize
0x180029dd8  mov     r8, r14; lpBuffer
0x180029ddb  mov     [rsp+68h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x180029de4  mov     rdx, rdi; lpBaseAddress
0x180029de7  call    cs:__imp_ReadProcessMemory
0x180029ded  xor     ecx, ecx
0x180029def  test    eax, eax
0x180029df1  cmovnz  ebx, ecx
0x180029df4  mov     rdx, [rsp+68h+hProcess]; hProcess
0x180029dfc  mov     rcx, rdi; lpAddress
0x180029dff  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180029e04  jmp     short loc_180029E0B
0x180029e06  mov     ebx, 8007000Eh
0x180029e0b  mov     eax, ebx
0x180029e0d  mov     rbx, [rsp+68h+arg_0]
0x180029e12  add     rsp, 40h
0x180029e16  pop     r15
0x180029e18  pop     r14
0x180029e1a  pop     r13
0x180029e1c  pop     rdi
0x180029e1d  pop     rbp
0x180029e1e  retn
```
