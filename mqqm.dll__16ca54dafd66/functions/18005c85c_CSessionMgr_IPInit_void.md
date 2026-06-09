# CSessionMgr::IPInit(void)

- ea: `0x18005c85c`
- end: `0x18005c915`
- name: `?IPInit@CSessionMgr@@CAXXZ`
- size: `185`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005b8dc`

## callees

- `0x180004d91`
- `0x18002c6c8`
- `0x18005c85c`
- `0x18005cda8`
- `0x1800cff60`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18005c8e3`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18005c8e3`
- `KERNEL32!GetLastError` at `0x18005c8b2`
- `KERNEL32!GetLastError` at `0x18005c8b2`
- `KERNEL32!CloseHandle` at `0x18005c90a`
- `KERNEL32!CloseHandle` at `0x18005c90a`
- `KERNEL32!CreateThread` at `0x18005c8a7`
- `KERNEL32!CreateThread` at `0x18005c8a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CSessionMgr::IPInit(void)
{
  HANDLE v0; // rax
  DWORD LastError; // eax
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF

  CSessionMgr::InitListeningSocket(1);
  if ( g_numSockDsc )
  {
    ThreadId = 0;
    v0 = CreateThread(0, 0, AcceptIPThread, 0, 0, &ThreadId);
    if ( !v0 )
    {
      LastError = GetLastError();
      if ( LastError )
        LogMsgNTStatus(LastError, (wchar_t *)L"sessmgr", 0xA0u);
      exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    CloseHandle(v0);
  }
  else
  {
    EvReport(0xC0000897);
  }
}

```

## disassembly

```asm
0x18005c85c  sub     rsp, 58h
0x18005c860  mov     cl, 1; bool
0x18005c862  call    ?InitListeningSocket@CSessionMgr@@SAX_N@Z; CSessionMgr::InitListeningSocket(bool)
0x18005c867  cmp     cs:?g_numSockDsc@@3HA, 0; int g_numSockDsc
0x18005c86e  jnz     short loc_18005C87F
0x18005c870  mov     ecx, 0C0000897h; unsigned int
0x18005c875  call    ?EvReport@@YAXK@Z; EvReport(ulong)
0x18005c87a  jmp     loc_18005C910
0x18005c87f  mov     [rsp+58h+ThreadId], 0
0x18005c887  lea     rax, [rsp+58h+ThreadId]
0x18005c88c  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18005c891  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18005c899  xor     r9d, r9d; lpParameter
0x18005c89c  lea     r8, AcceptIPThread; lpStartAddress
0x18005c8a3  xor     edx, edx; dwStackSize
0x18005c8a5  xor     ecx, ecx; lpThreadAttributes
0x18005c8a7  call    cs:__imp_CreateThread
0x18005c8ad  test    rax, rax
0x18005c8b0  jnz     short loc_18005C907
0x18005c8b2  call    cs:__imp_GetLastError
0x18005c8b8  test    eax, eax
0x18005c8ba  jz      short loc_18005C8D1
0x18005c8bc  mov     r8d, 0A0h; unsigned __int16
0x18005c8c2  lea     rdx, aSessmgr; "sessmgr"
0x18005c8c9  mov     ecx, eax; int
0x18005c8cb  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18005c8d0  nop
0x18005c8d1  mov     r8d, 1
0x18005c8d7  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18005c8de  lea     rcx, [rsp+58h+pExceptionObject]
0x18005c8e3  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18005c8e9  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18005c8f0  mov     [rsp+58h+pExceptionObject], rax
0x18005c8f5  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18005c8fc  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18005c901  call    _CxxThrowException_0
0x18005c907  mov     rcx, rax; hObject
0x18005c90a  call    cs:__imp_CloseHandle
0x18005c910  add     rsp, 58h
0x18005c914  retn
```
