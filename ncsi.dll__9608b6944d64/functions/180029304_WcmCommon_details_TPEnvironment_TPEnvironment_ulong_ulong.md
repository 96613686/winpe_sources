# WcmCommon::details::TPEnvironment::TPEnvironment(ulong,ulong)

- ea: `0x180029304`
- end: `0x1800293fd`
- name: `??0TPEnvironment@details@WcmCommon@@QEAA@KK@Z`
- size: `249`
- prototype: `WcmCommon::details::TPEnvironment *__fastcall(WcmCommon::details::TPEnvironment *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029228`
- `0x18006db64`

## callees

- `0x180029304`
- `0x180042b3c`
- `0x180047f78`
- `0x180055860`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002937e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002937e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800293b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1800293b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800293a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800293a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
WcmCommon::details::TPEnvironment *__fastcall WcmCommon::details::TPEnvironment::TPEnvironment(
        WcmCommon::details::TPEnvironment *this)
{
  PTP_POOL *v2; // rdi
  PTP_POOL Threadpool; // rax
  const char *v4; // r9
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  memset_0(this, 0, 0x48u);
  v2 = (PTP_POOL *)((char *)this + 72);
  *((_QWORD *)this + 9) = 0;
  *(_DWORD *)this = 3;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 1;
  *((_DWORD *)this + 16) = 72;
  Threadpool = CreateThreadpool(0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
    (char *)this + 72,
    Threadpool);
  if ( !*((_QWORD *)this + 9) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\net\\inc\\wcm_work_queue.h",
      v4);
  if ( !SetThreadpoolThreadMinimum(*v2, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\net\\inc\\wcm_work_queue.h",
      v5);
  SetThreadpoolThreadMaximum(*v2, 1u);
  *((_QWORD *)this + 1) = *v2;
  return this;
}

```

## disassembly

```asm
0x180029304  mov     [rsp+arg_8], rbx
0x180029309  mov     [rsp+arg_10], rsi
0x18002930e  mov     [rsp+arg_0], rcx
0x180029313  push    rdi
0x180029314  sub     rsp, 20h
0x180029318  mov     rbx, rcx
0x18002931b  mov     esi, 48h ; 'H'
0x180029320  mov     r8d, esi; Size
0x180029323  xor     edx, edx; Val
0x180029325  call    memset_0
0x18002932a  lea     rdi, [rbx+48h]
0x18002932e  mov     qword ptr [rdi], 0
0x180029335  mov     dword ptr [rbx], 3
0x18002933b  mov     qword ptr [rbx+8], 0
0x180029343  mov     qword ptr [rbx+10h], 0
0x18002934b  mov     qword ptr [rbx+18h], 0
0x180029353  mov     qword ptr [rbx+20h], 0
0x18002935b  mov     qword ptr [rbx+28h], 0
0x180029363  mov     qword ptr [rbx+30h], 0
0x18002936b  mov     dword ptr [rbx+38h], 0
0x180029372  mov     dword ptr [rbx+3Ch], 1
0x180029379  mov     [rbx+40h], esi
0x18002937c  xor     ecx, ecx; reserved
0x18002937e  call    cs:__imp_CreateThreadpool
0x180029384  mov     rdx, rax
0x180029387  mov     rcx, rdi
0x18002938a  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18002938f  mov     rcx, [rsp+28h]; this
0x180029394  cmp     qword ptr [rdi], 0
0x180029398  jz      short loc_1800293D6
0x18002939a  mov     rsi, [rsp+28h]
0x18002939f  xor     edx, edx; cthrdMic
0x1800293a1  mov     rcx, [rdi]; ptpp
0x1800293a4  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800293aa  test    eax, eax
0x1800293ac  jz      short loc_1800293E8
0x1800293ae  mov     edx, 1; cthrdMost
0x1800293b3  mov     rcx, [rdi]; ptpp
0x1800293b6  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800293bc  mov     rax, [rdi]
0x1800293bf  mov     [rbx+8], rax
0x1800293c3  mov     rax, rbx
0x1800293c6  mov     rbx, [rsp+28h+arg_8]
0x1800293cb  mov     rsi, [rsp+28h+arg_10]
0x1800293d0  add     rsp, 20h
0x1800293d4  pop     rdi
0x1800293d5  retn
0x1800293d6  lea     r8, aOnecoreNetIncW; "onecore\\net\\inc\\wcm_work_queue.h"
0x1800293dd  mov     edx, 6Ah ; 'j'; void *
0x1800293e2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800293e8  lea     r8, aOnecoreNetIncW; "onecore\\net\\inc\\wcm_work_queue.h"
0x1800293ef  mov     edx, 6Dh ; 'm'; void *
0x1800293f4  mov     rcx, rsi; this
0x1800293f7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
