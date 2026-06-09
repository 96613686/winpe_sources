# ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::StartSession(wchar_t const *,wchar_t const *,_GUID const &,int)

- ea: `0x18009b858`
- end: `0x18009ba8a`
- name: `?StartSession@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@QEAAXPEB_W0AEBU_GUID@@H@Z`
- size: `562`
- prototype: `void __fastcall(char *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800ed290`

## callees

- `0x18000e190`
- `0x18008e780`
- `0x18009b858`
- `0x18009badc`
- `0x18009bb90`
- `0x1800a88a0`
- `0x1800a959c`
- `0x1800a9738`
- `0x1800a9744`
- `0x1800ea3a0`
- `0x1800eb8dc`
- `0x180149010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18009b9c1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18009b9c1`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18009b935`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18009b935`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18009b8e6`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18009b944`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18009b8e6`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18009b944`

## string_xrefs

- `0x18009ba67`: `ctEtwReader::StartSession is called while a session is already started`
- `0x18009ba58`: `	ctEtwReader::StartSession is called while a session is already started\n`
- `0x18009b952`: `	ctEtwReader::StartSession - StartTrace failed with error 0x%x\n`
- `0x18009b8f8`: `	ctEtwReader::StartSession - session with the name %s is already running - stopping/restarting that session\n`
- `0x18009b961`: `ctEtwReader::StartSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::StartSession(
        char *a1)
{
  ULONG64 *v2; // rsi
  struct _EVENT_TRACE_PROPERTIES *v3; // r14
  ULONG started; // ebx
  void *v5; // rax
  WCHAR *v6; // rbx
  bool v7; // [rsp+20h] [rbp-E0h]
  std::_Ref_count_base *v8[2]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_TRACE_LOGFILEW v10; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+220h] [rbp+120h] BYREF

  v2 = (ULONG64 *)(a1 + 160);
  if ( *((_QWORD *)a1 + 20) || *((_QWORD *)a1 + 21) != -1 || *((_QWORD *)a1 + 22) )
  {
    (*(void (__fastcall **)(const wchar_t *))a1)(L"\tctEtwReader::StartSession is called while a session is already started\n");
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "ctEtwReader::StartSession is called while a session is already started");
    throw (std::runtime_error *)pExceptionObject;
  }
  *(_OWORD *)(a1 + 184) = xmmword_180183700;
  pExceptionObject[0] = 0;
  v3 = (struct _EVENT_TRACE_PROPERTIES *)ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::BuildEventTraceProperties(
                                           a1,
                                           pExceptionObject);
  started = StartTraceW(v2, L"EstatsEtwSession", v3);
  if ( started == 183 )
  {
    (*(void (**)(const wchar_t *, ...))a1)(
      L"\tctEtwReader::StartSession - session with the name %s is already running - stopping/restarting that session\n",
      L"EstatsEtwSession");
    memset_0(&Properties.Wnode.ProviderId, 0, 0x74u);
    Properties.Wnode.BufferSize = 120;
    ControlTraceW(0, L"EstatsEtwSession", &Properties, 1u);
    started = StartTraceW(v2, L"EstatsEtwSession", v3);
  }
  if ( started )
  {
    (*(void (**)(const wchar_t *, ...))a1)(
      L"\tctEtwReader::StartSession - StartTrace failed with error 0x%x\n",
      started);
    ctl::ctException::ctException(
      (ctl::ctException *)&Properties,
      started,
      L"StartTrace",
      L"ctEtwReader::StartSession",
      v7);
    throw (ctl::ctException *)&Properties;
  }
  *(_OWORD *)v8 = 0;
  v5 = operator new[](0x22u);
  std::shared_ptr<wchar_t [0]>::shared_ptr<wchar_t [0]>(v8, v5);
  v6 = (WCHAR *)v8[0];
  _o_wcscpy_s(v8[0], 17, L"EstatsEtwSession");
  v6[16] = 0;
  memset_0(&v10, 0, sizeof(v10));
  v10.LoggerName = v6;
  v10.LogFileMode = 268435712;
  v10.BufferCallback = 0;
  v10.EventCallback = (PEVENT_CALLBACK)ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::EventRecordCallback;
  v10.Context = a1;
  ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::OpenTraceImpl(
    (__int64)a1,
    &v10);
  if ( v8[1] )
    std::_Ref_count_base::_Decref(v8[1]);
  if ( *((_QWORD *)&pExceptionObject[0] + 1) )
    std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&pExceptionObject[0] + 1));
}

```

## disassembly

```asm
0x18009b858  push    rbp
0x18009b85a  push    rbx
0x18009b85b  push    rsi
0x18009b85c  push    rdi
0x18009b85d  push    r12
0x18009b85f  push    r14
0x18009b861  lea     rbp, [rsp-1B8h]
0x18009b869  sub     rsp, 2B8h
0x18009b870  mov     rax, cs:__security_cookie
0x18009b877  xor     rax, rsp
0x18009b87a  mov     [rbp+1E0h+var_40], rax
0x18009b881  mov     rdi, rcx
0x18009b884  lea     rsi, [rcx+0A0h]
0x18009b88b  cmp     qword ptr [rsi], 0
0x18009b88f  jnz     loc_18009BA58
0x18009b895  cmp     qword ptr [rcx+0A8h], 0FFFFFFFFFFFFFFFFh
0x18009b89d  jnz     loc_18009BA58
0x18009b8a3  cmp     qword ptr [rcx+0B0h], 0
0x18009b8ab  jnz     loc_18009BA58
0x18009b8b1  movups  xmm0, cs:xmmword_180183700
0x18009b8b8  movdqu  xmmword ptr [rcx+0B8h], xmm0
0x18009b8c0  xorps   xmm1, xmm1
0x18009b8c3  movdqu  [rsp+2E0h+pExceptionObject], xmm1
0x18009b8c9  lea     rdx, [rsp+2E0h+pExceptionObject]
0x18009b8ce  call    ?BuildEventTraceProperties@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@AEAAPEAU_EVENT_TRACE_PROPERTIES@@AEAV?$shared_ptr@$$BY0A@E@std@@PEB_W1H@Z; ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::BuildEventTraceProperties(std::shared_ptr<uchar [0]> &,wchar_t const *,wchar_t const *,int)
0x18009b8d3  mov     r14, rax
0x18009b8d6  mov     r8, rax; Properties
0x18009b8d9  lea     r12, InstanceName; "EstatsEtwSession"
0x18009b8e0  mov     rdx, r12; InstanceName
0x18009b8e3  mov     rcx, rsi; TraceHandle
0x18009b8e6  call    cs:__imp_StartTraceW
0x18009b8ec  mov     ebx, eax
0x18009b8ee  cmp     eax, 0B7h
0x18009b8f3  jnz     short loc_18009B94C
0x18009b8f5  mov     rdx, r12
0x18009b8f8  lea     rcx, aCtetwreaderSta_4; "\tctEtwReader::StartSession - session w"...
0x18009b8ff  mov     rax, [rdi]
0x18009b902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b907  xor     edx, edx; Val
0x18009b909  lea     r8d, [rbx-43h]; Size
0x18009b90d  lea     rcx, [rbp+1E0h+Properties.Wnode.ProviderId]; void *
0x18009b914  call    memset_0
0x18009b919  mov     [rbp+1E0h+Properties.Wnode.BufferSize], 78h ; 'x'
0x18009b923  mov     r9d, 1; ControlCode
0x18009b929  lea     r8, [rbp+1E0h+Properties]; Properties
0x18009b930  mov     rdx, r12; InstanceName
0x18009b933  xor     ecx, ecx; TraceHandle
0x18009b935  call    cs:__imp_ControlTraceW
0x18009b93b  mov     r8, r14; Properties
0x18009b93e  mov     rdx, r12; InstanceName
0x18009b941  mov     rcx, rsi; TraceHandle
0x18009b944  call    cs:__imp_StartTraceW
0x18009b94a  mov     ebx, eax
0x18009b94c  test    ebx, ebx
0x18009b94e  jz      short loc_18009B991
0x18009b950  mov     edx, ebx
0x18009b952  lea     rcx, aCtetwreaderSta_1; "\tctEtwReader::StartSession - StartTrac"...
0x18009b959  mov     rax, [rdi]
0x18009b95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b961  lea     r9, aCtetwreaderSta_5; "ctEtwReader::StartSession"
0x18009b968  lea     r8, aStarttrace; "StartTrace"
0x18009b96f  mov     edx, ebx; unsigned int
0x18009b971  lea     rcx, [rbp+1E0h+Properties]; this
0x18009b978  call    ??0ctException@ctl@@QEAA@KPEB_W0_N@Z; ctl::ctException::ctException(ulong,wchar_t const *,wchar_t const *,bool)
0x18009b97d  lea     rdx, _TI2?AVctException@ctl@@; pThrowInfo
0x18009b984  lea     rcx, [rbp+1E0h+Properties]; pExceptionObject
0x18009b98b  call    _CxxThrowException_0
0x18009b991  xorps   xmm0, xmm0
0x18009b994  movups  xmmword ptr [rsp+2E0h+var_2B0], xmm0
0x18009b999  mov     ecx, 22h ; '"'; unsigned __int64
0x18009b99e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009b9a3  mov     rdx, rax
0x18009b9a6  lea     rcx, [rsp+2E0h+var_2B0]
0x18009b9ab  call    ??$?0_W$0A@@?$shared_ptr@$$BY0A@_W@std@@QEAA@PEA_W@Z; std::shared_ptr<wchar_t [0]>::shared_ptr<wchar_t [0]>(wchar_t *)
0x18009b9b0  nop
0x18009b9b1  mov     r8, r12
0x18009b9b4  mov     edx, 11h
0x18009b9b9  mov     rbx, [rsp+2E0h+var_2B0]
0x18009b9be  mov     rcx, rbx
0x18009b9c1  call    cs:__imp__o_wcscpy_s
0x18009b9c7  xor     eax, eax
0x18009b9c9  mov     [rbx+20h], ax
0x18009b9cd  xor     edx, edx; Val
0x18009b9cf  mov     r8d, 1C0h; Size
0x18009b9d5  lea     rcx, [rsp+2E0h+var_280]; void *
0x18009b9da  call    memset_0
0x18009b9df  mov     [rsp+2E0h+var_278], rbx
0x18009b9e4  mov     [rsp+2E0h+var_264], 10000100h
0x18009b9ec  mov     [rbp+1E0h+var_F0], 0
0x18009b9f7  lea     rax, ?EventRecordCallback@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@CAXPEAU_EVENT_RECORD@@@Z; ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::EventRecordCallback(_EVENT_RECORD *)
0x18009b9fe  mov     [rbp+1E0h+var_D8], rax
0x18009ba05  mov     [rbp+1E0h+var_C8], rdi
0x18009ba0c  lea     rdx, [rsp+2E0h+var_280]
0x18009ba11  mov     rcx, rdi
0x18009ba14  call    ?OpenTraceImpl@?$ctEtwReader@V?$function@$$A6A_NPEBU_EVENT_RECORD@@@Z@std@@P6AHPEB_WZZ@ctl@@AEAAXAEAU_EVENT_TRACE_LOGFILEW@@@Z; ctl::ctEtwReader<std::function<bool (_EVENT_RECORD const *)>,int (*)(wchar_t const *,...)>::OpenTraceImpl(_EVENT_TRACE_LOGFILEW &)
0x18009ba19  nop
0x18009ba1a  mov     rcx, [rsp+2E0h+var_2B0+8]; this
0x18009ba1f  test    rcx, rcx
0x18009ba22  jz      short loc_18009BA2A
0x18009ba24  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009ba29  nop
0x18009ba2a  mov     rcx, qword ptr [rsp+2E0h+pExceptionObject+8]; this
0x18009ba2f  test    rcx, rcx
0x18009ba32  jz      short loc_18009BA39
0x18009ba34  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18009ba39  mov     rcx, [rbp+1E0h+var_40]
0x18009ba40  xor     rcx, rsp; StackCookie
0x18009ba43  call    __security_check_cookie
0x18009ba48  add     rsp, 2B8h
0x18009ba4f  pop     r14
0x18009ba51  pop     r12
0x18009ba53  pop     rdi
0x18009ba54  pop     rsi
0x18009ba55  pop     rbx
0x18009ba56  pop     rbp
0x18009ba57  retn
0x18009ba58  lea     rcx, aCtetwreaderSta_2; "\tctEtwReader::StartSession is called w"...
0x18009ba5f  mov     rax, [rdi]
0x18009ba62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ba67  lea     rdx, aCtetwreaderSta_0; "ctEtwReader::StartSession is called whi"...
0x18009ba6e  lea     rcx, [rsp+2E0h+pExceptionObject]; this
0x18009ba73  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18009ba78  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18009ba7f  lea     rcx, [rsp+2E0h+pExceptionObject]; pExceptionObject
0x18009ba84  call    _CxxThrowException_0
```
