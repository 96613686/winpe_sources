# CTraceController::CopyTraceFile(ushort const *)

- ea: `0x1800237a4`
- end: `0x180023823`
- name: `?CopyTraceFile@CTraceController@@QEAAJPEBG@Z`
- size: `127`
- prototype: `__int64 __fastcall(CTraceController *__hidden this, LPCWSTR lpNewFileName)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c478`
- `0x18000ec4c`
- `0x18001bfc0`

## callees

- `0x1800237a4`
- `0x1800239b0`
- `0x180023ac8`
- `0x18002f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800237f1`
- `KERNEL32!GetLastError` at `0x1800237f1`
- `KERNEL32!CopyFileW` at `0x1800237e7`
- `KERNEL32!CopyFileW` at `0x1800237e7`

## pseudocode

```c
__int64 __fastcall CTraceController::CopyTraceFile(CTraceController *this, LPCWSTR lpNewFileName)
{
  signed int v2; // ebx
  signed int v5; // edi
  const WCHAR *v6; // rax
  signed int LastError; // eax
  unsigned int v8; // eax

  v2 = *((_DWORD *)this + 6);
  if ( !v2 )
  {
    v5 = CTraceController::Stop(this);
    if ( v5 == 1 || (v2 = v5) == 0 )
    {
      v6 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this);
      if ( !CopyFileW(v6, lpNewFileName, 1) )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( !v5 )
      {
        v8 = CTraceController::Resume(this);
        if ( v2 >= 0 )
          return v8;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800237a4  push    rbx
0x1800237a6  push    rbp
0x1800237a7  push    rsi
0x1800237a8  push    rdi
0x1800237a9  sub     rsp, 28h
0x1800237ad  mov     ebx, [rcx+18h]
0x1800237b0  mov     rbp, rdx
0x1800237b3  mov     rsi, rcx
0x1800237b6  test    ebx, ebx
0x1800237b8  jnz     short loc_180023818
0x1800237ba  call    ?Stop@CTraceController@@QEAAJXZ; CTraceController::Stop(void)
0x1800237bf  mov     edi, eax
0x1800237c1  cmp     eax, 1
0x1800237c4  jz      short loc_1800237CC
0x1800237c6  mov     ebx, edi
0x1800237c8  test    edi, edi
0x1800237ca  jnz     short loc_180023818
0x1800237cc  mov     rcx, [rsi]
0x1800237cf  mov     rax, [rcx]
0x1800237d2  mov     rax, [rax+38h]
0x1800237d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237db  mov     rcx, rax; lpExistingFileName
0x1800237de  mov     r8d, 1; bFailIfExists
0x1800237e4  mov     rdx, rbp; lpNewFileName
0x1800237e7  call    cs:__imp_CopyFileW
0x1800237ed  test    eax, eax
0x1800237ef  jnz     short loc_180023806
0x1800237f1  call    cs:__imp_GetLastError
0x1800237f7  mov     ebx, eax
0x1800237f9  test    eax, eax
0x1800237fb  jle     short loc_180023806
0x1800237fd  movzx   ebx, ax
0x180023800  or      ebx, 80070000h
0x180023806  test    edi, edi
0x180023808  jnz     short loc_180023818
0x18002380a  mov     rcx, rsi; this
0x18002380d  call    ?Resume@CTraceController@@QEAAJXZ; CTraceController::Resume(void)
0x180023812  test    ebx, ebx
0x180023814  js      short loc_180023818
0x180023816  mov     ebx, eax
0x180023818  mov     eax, ebx
0x18002381a  add     rsp, 28h
0x18002381e  pop     rdi
0x18002381f  pop     rsi
0x180023820  pop     rbp
0x180023821  pop     rbx
0x180023822  retn
```
