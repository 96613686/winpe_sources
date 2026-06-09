# CAsyncStatementTimeoutHandler::Init(void)

- ea: `0x1004e8c34`
- end: `0x1004e8cc0`
- name: `?Init@CAsyncStatementTimeoutHandler@@QEAAJXZ`
- size: `140`
- prototype: `__int64 __fastcall(CAsyncStatementTimeoutHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1004e7330`

## callees

- `0x10046c3c8`
- `0x1004e8c34`
- `0x100546a24`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1004e8c6e`
- `KERNEL32!CreateEventW` at `0x1004e8c6e`
- `KERNEL32!GetLastError` at `0x1004e8c7d`
- `KERNEL32!GetLastError` at `0x1004e8c7d`

## pseudocode

```c
__int64 __fastcall CAsyncStatementTimeoutHandler::Init(CAsyncStatementTimeoutHandler *this)
{
  unsigned int v2; // ebx
  __int64 v3; // r9
  HANDLE EventW; // rax
  signed int LastError; // eax

  *((_QWORD *)this + 7) = (char *)this + 48;
  *((_QWORD *)this + 6) = (char *)this + 48;
  v2 = 0;
  if ( !(unsigned int)MPInitializeCriticalSectionAndSpinCount((struct CCriticalSection **)this + 5) )
  {
    v2 = -2147024882;
LABEL_7:
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(0, 4009993, v2, v3);
    return v2;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 3) = EventW;
  if ( EventW )
  {
    *((_QWORD *)this + 2) = 0;
    return v2;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    v2 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v2 = LastError;
    goto LABEL_7;
  }
  return v2;
}

```

## disassembly

```asm
0x1004e8c34  mov     [rsp+arg_0], rbx
0x1004e8c39  push    rdi
0x1004e8c3a  sub     rsp, 20h
0x1004e8c3e  lea     rax, [rcx+30h]
0x1004e8c42  mov     rdi, rcx
0x1004e8c45  add     rcx, 28h ; '('; struct CCriticalSection **
0x1004e8c49  mov     [rax+8], rax
0x1004e8c4d  xor     edx, edx
0x1004e8c4f  mov     [rax], rax
0x1004e8c52  xor     ebx, ebx
0x1004e8c54  call    MPInitializeCriticalSectionAndSpinCount
0x1004e8c59  test    eax, eax
0x1004e8c5b  jnz     short loc_1004E8C64
0x1004e8c5d  mov     ebx, 8007000Eh
0x1004e8c62  jmp     short loc_1004E8C95
0x1004e8c64  xor     r9d, r9d; lpName
0x1004e8c67  xor     r8d, r8d; bInitialState
0x1004e8c6a  xor     edx, edx; bManualReset
0x1004e8c6c  xor     ecx, ecx; lpEventAttributes
0x1004e8c6e  call    cs:__imp_CreateEventW
0x1004e8c74  mov     [rdi+18h], rax
0x1004e8c78  test    rax, rax
0x1004e8c7b  jnz     short loc_1004E8CAF
0x1004e8c7d  call    cs:__imp_GetLastError
0x1004e8c83  test    eax, eax
0x1004e8c85  jz      short loc_1004E8CB3
0x1004e8c87  movzx   ebx, ax
0x1004e8c8a  or      ebx, 80070000h
0x1004e8c90  test    eax, eax
0x1004e8c92  cmovle  ebx, eax
0x1004e8c95  test    byte ptr cs:_bidGblFlags, 2
0x1004e8c9c  jz      short loc_1004E8CB3
0x1004e8c9e  mov     r8d, ebx
0x1004e8ca1  mov     edx, 3D3009h
0x1004e8ca6  xor     ecx, ecx
0x1004e8ca8  call    _bidTraceHR
0x1004e8cad  jmp     short loc_1004E8CB3
0x1004e8caf  mov     [rdi+10h], rbx
0x1004e8cb3  mov     eax, ebx
0x1004e8cb5  mov     rbx, [rsp+28h+arg_0]
0x1004e8cba  add     rsp, 20h
0x1004e8cbe  pop     rdi
0x1004e8cbf  retn
```
