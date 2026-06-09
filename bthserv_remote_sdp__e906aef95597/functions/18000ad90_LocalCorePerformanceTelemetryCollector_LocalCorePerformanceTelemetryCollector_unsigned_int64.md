# LocalCorePerformanceTelemetryCollector::LocalCorePerformanceTelemetryCollector(unsigned __int64)

- ea: `0x18000ad90`
- end: `0x18000af1b`
- name: `??0LocalCorePerformanceTelemetryCollector@@QEAA@_K@Z`
- size: `395`
- prototype: `LocalCorePerformanceTelemetryCollector *__fastcall(PVOID pv, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d498`

## callees

- `0x180009c50`
- `0x18000ad90`
- `0x180012004`
- `0x180012384`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ae24`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ae24`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18000aea9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18000aea9`

## pseudocode

```c
struct _TP_TIMER **__fastcall LocalCorePerformanceTelemetryCollector::LocalCorePerformanceTelemetryCollector(
        struct _TP_TIMER **pv,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER **v2; // rsi
  char v4; // bl
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v6; // rcx
  int v7; // edx
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  v2 = pv + 1;
  *pv = a2;
  pv[1] = 0;
  v4 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  ThreadpoolTimer = CreateThreadpoolTimer(
                      LocalCorePerformanceTelemetryCollector::CollectPerformanceTelemetryCallback,
                      pv,
                      0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    v2,
    ThreadpoolTimer);
  v6 = *v2;
  if ( *v2 )
  {
    pftDueTime = (struct _FILETIME)-36000000000LL;
    SetThreadpoolTimerEx(v6, &pftDueTime, 0x36EE80u, 0);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      v4 = 0;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v4;
      WPP_RECORDER_AND_TRACE_SF_si(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      v4 = 0;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  return pv;
}

```

## disassembly

```asm
0x18000ad90  mov     [rsp+arg_8], rbx
0x18000ad95  mov     [rsp+arg_10], rbp
0x18000ad9a  mov     [rsp+arg_18], rsi
0x18000ad9f  push    rdi
0x18000ada0  push    r14
0x18000ada2  push    r15
0x18000ada4  sub     rsp, 50h
0x18000ada8  lea     rsi, [rcx+8]
0x18000adac  mov     [rcx], rdx
0x18000adaf  and     qword ptr [rsi], 0
0x18000adb3  mov     rdi, rcx
0x18000adb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adbd  lea     r14, WPP_GLOBAL_Control
0x18000adc4  mov     bl, 1
0x18000adc6  cmp     rcx, r14
0x18000adc9  jz      short loc_18000ADD5
0x18000adcb  cmp     byte ptr [rcx+19h], 5
0x18000adcf  jb      short loc_18000ADD5
0x18000add1  mov     dl, bl
0x18000add3  jmp     short loc_18000ADD7
0x18000add5  xor     dl, dl
0x18000add7  lea     rbp, WPP_RECORDER_INITIALIZED
0x18000adde  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18000ade5  lea     r15, WPP_5e83cdb759c63b5e0899db4d3690f4b2_Traceguids
0x18000adec  setnz   r8b
0x18000adf0  test    dl, dl
0x18000adf2  jnz     short loc_18000ADF9
0x18000adf4  test    r8b, r8b
0x18000adf7  jz      short loc_18000AE17
0x18000adf9  mov     r9, [rcx+28h]
0x18000adfd  mov     rcx, [rcx+10h]
0x18000ae01  mov     [rsp+68h+var_20], rdi
0x18000ae06  mov     [rsp+68h+var_30], r15
0x18000ae0b  mov     [rsp+68h+var_38], 0Ah
0x18000ae12  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000ae17  xor     r8d, r8d; pcbe
0x18000ae1a  lea     rcx, ?CollectPerformanceTelemetryCallback@LocalCorePerformanceTelemetryCollector@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ae21  mov     rdx, rdi; pv
0x18000ae24  call    cs:__imp_CreateThreadpoolTimer
0x18000ae2b  nop     dword ptr [rax+rax+00h]
0x18000ae30  mov     rdx, rax
0x18000ae33  mov     rcx, rsi
0x18000ae36  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000ae3b  mov     rcx, [rsi]; pti
0x18000ae3e  test    rcx, rcx
0x18000ae41  jnz     short loc_18000AE8C
0x18000ae43  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae4a  cmp     rcx, r14
0x18000ae4d  jz      short loc_18000AE55
0x18000ae4f  cmp     byte ptr [rcx+19h], 3
0x18000ae53  jnb     short loc_18000AE57
0x18000ae55  xor     bl, bl
0x18000ae57  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18000ae5e  setnz   r8b
0x18000ae62  test    bl, bl
0x18000ae64  jnz     short loc_18000AE6F
0x18000ae66  test    r8b, r8b
0x18000ae69  jz      loc_18000AEFD
0x18000ae6f  mov     r9, [rcx+28h]
0x18000ae73  mov     dl, bl
0x18000ae75  mov     rcx, [rcx+10h]
0x18000ae79  mov     [rsp+68h+var_30], r15
0x18000ae7e  mov     [rsp+68h+var_38], 0Bh
0x18000ae85  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000ae8a  jmp     short loc_18000AEFD
0x18000ae8c  mov     rax, 0FFFFFFF79E3B9800h
0x18000ae96  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000ae9b  xor     r9d, r9d; msWindowLength
0x18000ae9e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000aea3  mov     r8d, 36EE80h; msPeriod
0x18000aea9  call    cs:__imp_SetThreadpoolTimerEx
0x18000aeb0  nop     dword ptr [rax+rax+00h]
0x18000aeb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aebc  cmp     rcx, r14
0x18000aebf  jz      short loc_18000AEC7
0x18000aec1  cmp     byte ptr [rcx+19h], 5
0x18000aec5  jnb     short loc_18000AEC9
0x18000aec7  xor     bl, bl
0x18000aec9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18000aed0  setnz   r8b
0x18000aed4  test    bl, bl
0x18000aed6  jnz     short loc_18000AEDD
0x18000aed8  test    r8b, r8b
0x18000aedb  jz      short loc_18000AEFD
0x18000aedd  mov     r9, [rcx+28h]
0x18000aee1  mov     dl, bl
0x18000aee3  mov     rcx, [rcx+10h]
0x18000aee7  mov     [rsp+68h+var_20], rdi
0x18000aeec  mov     [rsp+68h+var_30], r15
0x18000aef1  mov     [rsp+68h+var_38], 0Ch
0x18000aef8  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000aefd  lea     r11, [rsp+68h+var_18]
0x18000af02  mov     rax, rdi
0x18000af05  mov     rbx, [r11+28h]
0x18000af09  mov     rbp, [r11+30h]
0x18000af0d  mov     rsi, [r11+38h]
0x18000af11  mov     rsp, r11
0x18000af14  pop     r15
0x18000af16  pop     r14
0x18000af18  pop     rdi
0x18000af19  retn
```
