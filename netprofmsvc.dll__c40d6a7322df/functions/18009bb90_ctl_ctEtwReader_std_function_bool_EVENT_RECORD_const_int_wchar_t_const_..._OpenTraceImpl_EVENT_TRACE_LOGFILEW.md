# ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::OpenTraceImpl(_EVENT_TRACE_LOGFILEW &)

- ea: `0x18009bb90`
- end: `0x18009bc83`
- name: `?OpenTraceImpl@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@AEAAXAEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(__int64, struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18009b858`

## callees

- `0x18009bb90`
- `0x1800a9744`
- `0x1800ea3a0`
- `0x1800f0a90`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bc29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009bc29`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009bc17`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009bc17`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18009bba0`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18009bba0`

## string_xrefs

- `0x18009bbcf`: `ctEtwReader::StartSession`
- `0x18009bc42`: `ctEtwReader::StartSession`
- `0x18009bbbe`: `	ctEtwReader::StartSession - OpenTrace failed with error 0x%x\n`
- `0x18009bc31`: `	ctEtwReader::StartSession - CreateThread failed with error 0x%x\n`
- `0x18009bbd8`: `OpenTrace`
- `0x18009bc4b`: `CreateThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::OpenTraceImpl(
        __int64 a1,
        struct _EVENT_TRACE_LOGFILEW *a2)
{
  TRACEHANDLE v3; // rax
  __int64 LastError; // rbx
  HANDLE Thread; // rax
  __int64 v6; // rbx
  bool dwCreationFlags; // [rsp+20h] [rbp-58h]
  bool dwCreationFlagsa; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[72]; // [rsp+30h] [rbp-48h] BYREF

  v3 = OpenTraceW(a2);
  *(_QWORD *)(a1 + 168) = v3;
  if ( v3 == -1 )
  {
    LastError = GetLastError();
    (*(void (**)(const wchar_t *, ...))a1)(
      L"\tctEtwReader::StartSession - OpenTrace failed with error 0x%x\n",
      LastError);
    ctl::ctException::ctException(
      (ctl::ctException *)pExceptionObject,
      LastError,
      L"OpenTrace",
      L"ctEtwReader::StartSession",
      dwCreationFlags);
    throw (ctl::ctException *)pExceptionObject;
  }
  Thread = CreateThread(
             0,
             0,
             ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::ProcessTraceThread,
             (LPVOID)(a1 + 168),
             0,
             0);
  *(_QWORD *)(a1 + 176) = Thread;
  if ( !Thread )
  {
    v6 = GetLastError();
    (*(void (**)(const wchar_t *, ...))a1)(L"\tctEtwReader::StartSession - CreateThread failed with error 0x%x\n", v6);
    ctl::ctException::ctException(
      (ctl::ctException *)pExceptionObject,
      v6,
      L"CreateThread",
      L"ctEtwReader::StartSession",
      dwCreationFlagsa);
    throw (ctl::ctException *)pExceptionObject;
  }
  return ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::VerifySession(a1);
}

```

## disassembly

```asm
0x18009bb90  mov     [rsp+arg_0], rbx
0x18009bb95  push    rdi
0x18009bb96  sub     rsp, 70h
0x18009bb9a  mov     rdi, rcx
0x18009bb9d  mov     rcx, rdx; Logfile
0x18009bba0  call    cs:__imp_OpenTraceW
0x18009bba6  lea     r9, [rdi+0A8h]; lpParameter
0x18009bbad  mov     [r9], rax
0x18009bbb0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009bbb4  jnz     short loc_18009BBFB
0x18009bbb6  call    cs:__imp_GetLastError
0x18009bbbc  mov     ebx, eax
0x18009bbbe  lea     rcx, aCtetwreaderSta_3; "\tctEtwReader::StartSession - OpenTrace"...
0x18009bbc5  mov     edx, eax
0x18009bbc7  mov     rax, [rdi]
0x18009bbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bbcf  lea     r9, aCtetwreaderSta_5; "ctEtwReader::StartSession"
0x18009bbd6  mov     edx, ebx; unsigned int
0x18009bbd8  lea     r8, aOpentrace; "OpenTrace"
0x18009bbdf  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18009bbe4  call    ??0ctException@ctl@@QEAA@KPEB_W0_N@Z; ctl::ctException::ctException(ulong,wchar_t const *,wchar_t const *,bool)
0x18009bbe9  lea     rdx, _TI2?AVctException@ctl@@; pThrowInfo
0x18009bbf0  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18009bbf5  call    _CxxThrowException_0
0x18009bbfb  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x18009bc04  lea     r8, ?ProcessTraceThread@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@CAKPEAX@Z; lpStartAddress
0x18009bc0b  xor     edx, edx; dwStackSize
0x18009bc0d  mov     dword ptr [rsp+78h+dwCreationFlags], 0; bool
0x18009bc15  xor     ecx, ecx; lpThreadAttributes
0x18009bc17  call    cs:__imp_CreateThread
0x18009bc1d  mov     [rdi+0B0h], rax
0x18009bc24  test    rax, rax
0x18009bc27  jnz     short loc_18009BC6E
0x18009bc29  call    cs:__imp_GetLastError
0x18009bc2f  mov     ebx, eax
0x18009bc31  lea     rcx, aCtetwreaderSta; "\tctEtwReader::StartSession - CreateThr"...
0x18009bc38  mov     edx, eax
0x18009bc3a  mov     rax, [rdi]
0x18009bc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bc42  lea     r9, aCtetwreaderSta_5; "ctEtwReader::StartSession"
0x18009bc49  mov     edx, ebx; unsigned int
0x18009bc4b  lea     r8, aCreatethread; "CreateThread"
0x18009bc52  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18009bc57  call    ??0ctException@ctl@@QEAA@KPEB_W0_N@Z; ctl::ctException::ctException(ulong,wchar_t const *,wchar_t const *,bool)
0x18009bc5c  lea     rdx, _TI2?AVctException@ctl@@; pThrowInfo
0x18009bc63  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18009bc68  call    _CxxThrowException_0
0x18009bc6e  mov     rcx, rdi
0x18009bc71  mov     rbx, [rsp+78h+arg_0]
0x18009bc79  add     rsp, 70h
0x18009bc7d  pop     rdi
0x18009bc7e  jmp     ?VerifySession@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@AEAAXXZ; ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::VerifySession(void)
```
