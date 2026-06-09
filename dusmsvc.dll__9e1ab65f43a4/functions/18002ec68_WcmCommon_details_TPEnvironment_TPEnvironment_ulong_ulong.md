# WcmCommon::details::TPEnvironment::TPEnvironment(ulong,ulong)

- ea: `0x18002ec68`
- end: `0x18002ed5d`
- name: `??0TPEnvironment@details@WcmCommon@@QEAA@KK@Z`
- size: `245`
- prototype: `WcmCommon::details::TPEnvironment *__fastcall(WcmCommon::details::TPEnvironment *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ed64`

## callees

- `0x180008704`
- `0x18002ec68`
- `0x18002ffe0`
- `0x1800302dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002ece2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002ece2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002ed18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002ed18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002ed3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002ed3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
      (unsigned int)"onecore\\internal\\net\\inc\\wcm\\wcm_work_queue.h",
      v4);
  if ( !SetThreadpoolThreadMinimum(*v2, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\internal\\net\\inc\\wcm\\wcm_work_queue.h",
      v5);
  SetThreadpoolThreadMaximum(*v2, 1u);
  *((_QWORD *)this + 1) = *v2;
  return this;
}

```

## disassembly

```asm
0x18002ec68  mov     [rsp+arg_8], rbx
0x18002ec6d  mov     [rsp+arg_10], rsi
0x18002ec72  mov     [rsp+arg_0], rcx
0x18002ec77  push    rdi
0x18002ec78  sub     rsp, 20h
0x18002ec7c  mov     rbx, rcx
0x18002ec7f  mov     esi, 48h ; 'H'
0x18002ec84  mov     r8d, esi; Size
0x18002ec87  xor     edx, edx; Val
0x18002ec89  call    memset_0
0x18002ec8e  lea     rdi, [rbx+48h]
0x18002ec92  mov     qword ptr [rdi], 0
0x18002ec99  mov     dword ptr [rbx], 3
0x18002ec9f  mov     qword ptr [rbx+8], 0
0x18002eca7  mov     qword ptr [rbx+10h], 0
0x18002ecaf  mov     qword ptr [rbx+18h], 0
0x18002ecb7  mov     qword ptr [rbx+20h], 0
0x18002ecbf  mov     qword ptr [rbx+28h], 0
0x18002ecc7  mov     qword ptr [rbx+30h], 0
0x18002eccf  mov     dword ptr [rbx+38h], 0
0x18002ecd6  mov     dword ptr [rbx+3Ch], 1
0x18002ecdd  mov     [rbx+40h], esi
0x18002ece0  xor     ecx, ecx; reserved
0x18002ece2  call    cs:__imp_CreateThreadpool
0x18002ece8  mov     rdx, rax
0x18002eceb  mov     rcx, rdi
0x18002ecee  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18002ecf3  mov     rcx, [rsp+28h]; this
0x18002ecf8  cmp     qword ptr [rdi], 0
0x18002ecfc  jnz     short loc_18002ED0E
0x18002ecfe  lea     r8, aOnecoreInterna_2; "onecore\\internal\\net\\inc\\wcm\\wcm_w"...
0x18002ed05  lea     edx, [rsi+22h]; void *
0x18002ed08  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002ed0e  mov     rsi, [rsp+28h]
0x18002ed13  xor     edx, edx; cthrdMic
0x18002ed15  mov     rcx, [rdi]; ptpp
0x18002ed18  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002ed1e  test    eax, eax
0x18002ed20  jnz     short loc_18002ED35
0x18002ed22  lea     r8, aOnecoreInterna_2; "onecore\\internal\\net\\inc\\wcm\\wcm_w"...
0x18002ed29  lea     edx, [rax+6Dh]; void *
0x18002ed2c  mov     rcx, rsi; this
0x18002ed2f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002ed35  mov     edx, 1; cthrdMost
0x18002ed3a  mov     rcx, [rdi]; ptpp
0x18002ed3d  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002ed43  mov     rax, [rdi]
0x18002ed46  mov     [rbx+8], rax
0x18002ed4a  mov     rax, rbx
0x18002ed4d  mov     rbx, [rsp+28h+arg_8]
0x18002ed52  mov     rsi, [rsp+28h+arg_10]
0x18002ed57  add     rsp, 20h
0x18002ed5b  pop     rdi
0x18002ed5c  retn
```
