# CMsmqVssWriter::HandleRestore(void (*)(void))

- ea: `0x180090bb4`
- end: `0x180090d31`
- name: `?HandleRestore@CMsmqVssWriter@@AEAAJP6AXXZ@Z`
- size: `381`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, void (*)(void))`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180092410`

## callees

- `0x18000f35c`
- `0x180012ea8`
- `0x18002c61c`
- `0x180090bb4`
- `0x1800d08f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180090bf8`
- `KERNEL32!GetLastError` at `0x180090c91`
- `KERNEL32!GetLastError` at `0x180090cf1`
- `KERNEL32!GetLastError` at `0x180090bf8`
- `KERNEL32!GetLastError` at `0x180090c91`
- `KERNEL32!GetLastError` at `0x180090cf1`
- `KERNEL32!WaitForSingleObject` at `0x180090c61`
- `KERNEL32!WaitForSingleObject` at `0x180090c61`
- `KERNEL32!CreateThread` at `0x180090be5`
- `KERNEL32!CreateThread` at `0x180090be5`
- `KERNEL32!GetExitCodeThread` at `0x180090cba`
- `KERNEL32!GetExitCodeThread` at `0x180090cba`

## string_xrefs

- `0x180090d10`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMsmqVssWriter::HandleRestore(CMsmqVssWriter *this, void (*a2)(void))
{
  HANDLE Thread; // rbx
  signed int LastError; // eax
  signed int v4; // ebx
  unsigned __int16 v5; // r8
  signed int v6; // eax
  bool v7; // sf
  signed int v9; // eax
  void (*ExitCode)(void); // [rsp+48h] [rbp+10h] BYREF
  HANDLE v11; // [rsp+50h] [rbp+18h] BYREF

  ExitCode = a2;
  v11 = 0;
  Thread = CreateThread(0, 0, CMsmqVssWriter::HandleRestoreThread, this, 0, 0);
  v11 = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids,
        (unsigned int)v4);
    if ( v4 >= 0 )
      goto LABEL_28;
    v5 = 600;
    goto LABEL_27;
  }
  LODWORD(ExitCode) = 0;
  do
  {
    LODWORD(ExitCode) = WaitForSingleObject(Thread, 0x3E8u);
    LODWORD(qword_1801291DC) = qword_1801291DC + 1;
    HIDWORD(qword_1801291DC) = g_ServiceProgressTime;
    SetStatus();
  }
  while ( (_DWORD)ExitCode == 258 );
  if ( (_DWORD)ExitCode )
  {
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 >= 0 )
      goto LABEL_28;
    v5 = 640;
    goto LABEL_27;
  }
  if ( !GetExitCodeThread(Thread, (LPDWORD)&ExitCode) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    if ( v4 >= 0 )
      goto LABEL_28;
    v5 = 680;
    goto LABEL_27;
  }
  v4 = (int)ExitCode;
  v7 = (int)ExitCode < 0;
  if ( !(_DWORD)ExitCode )
  {
    CHandle::~CHandle((CHandle *)&v11);
    return 0;
  }
  if ( (int)ExitCode > 0 )
  {
    v4 = (unsigned __int16)ExitCode | 0x80070000;
    v7 = 1;
  }
  if ( v7 )
  {
    v5 = 660;
LABEL_27:
    LogMsgHR(v4, (wchar_t *)L"writer/mqwriter", v5);
  }
LABEL_28:
  CHandle::~CHandle((CHandle *)&v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180090bb4  mov     rax, rsp
0x180090bb7  mov     [rax+10h], rdx
0x180090bbb  push    rbx
0x180090bbc  sub     rsp, 30h
0x180090bc0  mov     qword ptr [rax+18h], 0
0x180090bc8  mov     qword ptr [rax-10h], 0
0x180090bd0  mov     dword ptr [rax-18h], 0
0x180090bd7  mov     r9, rcx; lpParameter
0x180090bda  lea     r8, ?HandleRestoreThread@CMsmqVssWriter@@CAKPEAX@Z; lpStartAddress
0x180090be1  xor     edx, edx; dwStackSize
0x180090be3  xor     ecx, ecx; lpThreadAttributes
0x180090be5  call    cs:__imp_CreateThread
0x180090beb  mov     rbx, rax
0x180090bee  mov     [rsp+38h+arg_10], rax
0x180090bf3  test    rax, rax
0x180090bf6  jnz     short loc_180090C51
0x180090bf8  call    cs:__imp_GetLastError
0x180090bfe  mov     ebx, eax
0x180090c00  test    eax, eax
0x180090c02  jle     short loc_180090C0D
0x180090c04  movzx   ebx, ax
0x180090c07  or      ebx, 80070000h
0x180090c0d  lea     rax, WPP_GLOBAL_Control
0x180090c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180090c1b  cmp     rcx, rax
0x180090c1e  jz      short loc_180090C3E
0x180090c20  test    byte ptr [rcx+1Ch], 1
0x180090c24  jz      short loc_180090C3E
0x180090c26  mov     edx, 0Eh
0x180090c2b  mov     r9d, ebx
0x180090c2e  lea     r8, WPP_6af5f41940d83573eba81ec716aa4ffa_Traceguids
0x180090c35  mov     rcx, [rcx+10h]
0x180090c39  call    WPP_SF_d
0x180090c3e  test    ebx, ebx
0x180090c40  jns     loc_180090D1F
0x180090c46  mov     r8d, 258h
0x180090c4c  jmp     loc_180090D10
0x180090c51  mov     dword ptr [rsp+38h+ExitCode], 0
0x180090c59  mov     edx, 3E8h; dwMilliseconds
0x180090c5e  mov     rcx, rbx; hHandle
0x180090c61  call    cs:__imp_WaitForSingleObject
0x180090c67  mov     dword ptr [rsp+38h+ExitCode], eax
0x180090c6b  inc     dword ptr cs:qword_1801291DC
0x180090c71  mov     eax, cs:?g_ServiceProgressTime@@3KA; ulong g_ServiceProgressTime
0x180090c77  mov     dword ptr cs:qword_1801291DC+4, eax
0x180090c7d  call    ?SetStatus@@YAXXZ; SetStatus(void)
0x180090c82  mov     eax, dword ptr [rsp+38h+ExitCode]
0x180090c86  cmp     eax, 102h
0x180090c8b  jz      short loc_180090C59
0x180090c8d  test    eax, eax
0x180090c8f  jz      short loc_180090CB2
0x180090c91  call    cs:__imp_GetLastError
0x180090c97  mov     ebx, eax
0x180090c99  test    eax, eax
0x180090c9b  jle     short loc_180090CA6
0x180090c9d  movzx   ebx, ax
0x180090ca0  or      ebx, 80070000h
0x180090ca6  test    ebx, ebx
0x180090ca8  jns     short loc_180090D1F
0x180090caa  mov     r8d, 280h
0x180090cb0  jmp     short loc_180090D10
0x180090cb2  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x180090cb7  mov     rcx, rbx; hThread
0x180090cba  call    cs:__imp_GetExitCodeThread
0x180090cc0  test    eax, eax
0x180090cc2  jz      short loc_180090CF1
0x180090cc4  mov     ebx, dword ptr [rsp+38h+ExitCode]
0x180090cc8  test    ebx, ebx
0x180090cca  jz      short loc_180090CE3
0x180090ccc  jle     short loc_180090CD9
0x180090cce  movzx   ebx, bx
0x180090cd1  or      ebx, 80070000h
0x180090cd7  test    ebx, ebx
0x180090cd9  jns     short loc_180090D1F
0x180090cdb  mov     r8d, 294h
0x180090ce1  jmp     short loc_180090D10
0x180090ce3  lea     rcx, [rsp+38h+arg_10]; this
0x180090ce8  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180090ced  xor     eax, eax
0x180090cef  jmp     short loc_180090D2B
0x180090cf1  call    cs:__imp_GetLastError
0x180090cf7  mov     ebx, eax
0x180090cf9  test    eax, eax
0x180090cfb  jle     short loc_180090D06
0x180090cfd  movzx   ebx, ax
0x180090d00  or      ebx, 80070000h
0x180090d06  test    ebx, ebx
0x180090d08  jns     short loc_180090D1F
0x180090d0a  mov     r8d, 2A8h; unsigned __int16
0x180090d10  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180090d17  mov     ecx, ebx; int
0x180090d19  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180090d1e  nop
0x180090d1f  lea     rcx, [rsp+38h+arg_10]; this
0x180090d24  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180090d29  mov     eax, ebx
0x180090d2b  add     rsp, 30h
0x180090d2f  pop     rbx
0x180090d30  retn
```
