# CTSThread::internalThreadWaitForMultipleObjects(ulong,void * const *,ITSEventFilter *,ulong,uint *)

- ea: `0x180028934`
- end: `0x180028b81`
- name: `?internalThreadWaitForMultipleObjects@CTSThread@@IEAAJKPEBQEAXPEAVITSEventFilter@@KPEAI@Z`
- size: `589`
- prototype: `__int64 __fastcall(CTSThread **this, unsigned int, void *const *, struct ITSEventFilter *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180027620`
- `0x180027810`

## callees

- `0x180001f98`
- `0x1800144c8`
- `0x180017330`
- `0x18001d114`
- `0x180025fcc`
- `0x180026168`
- `0x180026b30`
- `0x180027b6c`
- `0x180027b98`
- `0x180028514`
- `0x180028934`
- `0x18002a1c4`

## string_xrefs

- `0x180028b06`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180028af0`: `internalThreadWaitForMultipleObjects`

## pseudocode

```c
__int64 __fastcall CTSThread::internalThreadWaitForMultipleObjects(
        CTSThread **this,
        unsigned int a2,
        void *const *a3,
        struct ITSEventFilter *a4,
        unsigned int a5,
        unsigned int *a6)
{
  CTSReaderWriterLock *v10; // rbx
  int v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int ActivityIdPrefix; // eax
  int v16; // eax
  CTSThread *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // r11d
  int v26; // [rsp+28h] [rbp-48h]
  int v27; // [rsp+28h] [rbp-48h]
  int v28; // [rsp+50h] [rbp-20h] BYREF
  int v29; // [rsp+54h] [rbp-1Ch] BYREF
  const char *v30; // [rsp+58h] [rbp-18h] BYREF
  const char *v31; // [rsp+60h] [rbp-10h] BYREF
  const char *v32; // [rsp+68h] [rbp-8h] BYREF
  int v33; // [rsp+B8h] [rbp+48h] BYREF

  if ( a4 )
  {
    v10 = (CTSReaderWriterLock *)((char *)this + 164);
    CTSReaderWriterLock::WriteLock((CTSReaderWriterLock *)((char *)this + 164));
    v11 = CTSThread::PushEventFilter((CTSThread *)this, a4);
    CTSReaderWriterLock::WriteUnlock(v10);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12, v13, v14);
        v26 = v11;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          89,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"Unable to push new event filter",
          v26);
      }
LABEL_17:
      CTSReaderWriterLock::WriteLock((CTSReaderWriterLock *)((char *)this + 164));
      CTSThread::PopEventFilter((CTSThread *)this, a4);
      CTSReaderWriterLock::WriteUnlock((CTSReaderWriterLock *)((char *)this + 164));
      if ( v24 < 0 && (unsigned int)dword_180044008 > 2 )
      {
        v33 = v24;
        v30 = "internalThreadWaitForMultipleObjects";
        v28 = 1754;
        v31 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v32 = "Fail to POP event filter! hr = 0x%x";
        v29 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_180044008,
          (__int64)byte_18003F8AD,
          v22,
          v23,
          (const unsigned __int16 **)&v32,
          (__int64)&v29,
          (const unsigned __int16 **)&v31,
          (__int64)&v28,
          (const unsigned __int16 **)&v30,
          (__int64)&v33);
      }
      return (unsigned int)v11;
    }
  }
  v16 = CTSThread::internalThreadMsgLoop((CTSThread *)this, a2, a3, a5, a6);
  v11 = v16;
  if ( *((_DWORD *)this + 45) )
  {
    v11 = -2092629996;
  }
  else if ( v16 >= 0 )
  {
    CTSCriticalSection::Lock((CTSCriticalSection *)(this + 13));
    v17 = this[16];
    CTSCriticalSection::UnLock((CTSCriticalSection *)(this + 13));
    if ( v17 != (CTSThread *)(this + 16) )
    {
      v11 = CTSThread::SignalEventQueue((CTSThread *)this);
      if ( v11 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v18, v19, v20);
        v27 = v11;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          v21,
          (__int64)"Failed to Signal Event Queue",
          v27);
      }
    }
  }
  if ( a4 )
    goto LABEL_17;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180028934  mov     [rsp-28h+arg_0], rbx
0x180028939  mov     [rsp-28h+arg_8], rsi
0x18002893e  push    rbp
0x18002893f  push    rdi
0x180028940  push    r12
0x180028942  push    r14
0x180028944  push    r15
0x180028946  mov     rbp, rsp
0x180028949  sub     rsp, 70h
0x18002894d  mov     r12, r9
0x180028950  mov     rdi, r8
0x180028953  mov     esi, edx
0x180028955  mov     r15, rcx
0x180028958  test    r9, r9
0x18002895b  jz      loc_1800289F0
0x180028961  lea     rbx, [rcx+0A4h]
0x180028968  mov     rcx, rbx; this
0x18002896b  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180028970  mov     rdx, r12; struct ITSEventFilter *
0x180028973  mov     rcx, r15; this
0x180028976  call    ?PushEventFilter@CTSThread@@AEAAJPEAVITSEventFilter@@@Z; CTSThread::PushEventFilter(ITSEventFilter *)
0x18002897b  mov     rcx, rbx; this
0x18002897e  mov     r14d, eax
0x180028981  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x180028986  test    r14d, r14d
0x180028989  jns     short loc_1800289F0
0x18002898b  mov     rax, cs:WPP_GLOBAL_Control
0x180028992  lea     rcx, WPP_GLOBAL_Control
0x180028999  cmp     rax, rcx
0x18002899c  jz      loc_180028AB7
0x1800289a2  test    byte ptr [rax+1Ch], 8
0x1800289a6  jz      loc_180028AB7
0x1800289ac  cmp     byte ptr [rax+19h], 2
0x1800289b0  jb      loc_180028AB7
0x1800289b6  call    RdpX_GetActivityIdPrefix
0x1800289bb  lea     rcx, aUnableToPushNe; "Unable to push new event filter"
0x1800289c2  mov     dword ptr [rsp+70h+var_48], r14d
0x1800289c7  mov     [rsp+70h+var_50], rcx
0x1800289cc  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800289d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289da  mov     edx, 59h ; 'Y'
0x1800289df  mov     r9d, eax
0x1800289e2  mov     rcx, [rcx+10h]
0x1800289e6  call    WPP_SF_DsD
0x1800289eb  jmp     loc_180028AB7
0x1800289f0  mov     rax, [rbp+arg_28]
0x1800289f4  mov     r8, rdi; void **
0x1800289f7  mov     r9d, [rbp+arg_20]; unsigned int
0x1800289fb  mov     edx, esi; unsigned int
0x1800289fd  mov     rcx, r15; this
0x180028a00  mov     [rsp+70h+var_50], rax; unsigned int *
0x180028a05  call    ?internalThreadMsgLoop@CTSThread@@IEAAJKPEBQEAXKPEAI@Z; CTSThread::internalThreadMsgLoop(ulong,void * const *,ulong,uint *)
0x180028a0a  cmp     dword ptr [r15+0B4h], 0
0x180028a12  mov     r14d, eax
0x180028a15  jz      short loc_180028A22
0x180028a17  mov     r14d, 83450014h
0x180028a1d  jmp     loc_180028AAE
0x180028a22  test    eax, eax
0x180028a24  js      loc_180028AAE
0x180028a2a  lea     rcx, [r15+68h]; this
0x180028a2e  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180028a33  lea     rdi, [r15+80h]
0x180028a3a  mov     rbx, [rdi]
0x180028a3d  lea     rcx, [r15+68h]; this
0x180028a41  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180028a46  cmp     rbx, rdi
0x180028a49  jz      short loc_180028AAE
0x180028a4b  mov     rcx, r15; this
0x180028a4e  call    ?SignalEventQueue@CTSThread@@MEAAJXZ; CTSThread::SignalEventQueue(void)
0x180028a53  mov     r14d, eax
0x180028a56  test    eax, eax
0x180028a58  jns     short loc_180028AAE
0x180028a5a  mov     rax, cs:WPP_GLOBAL_Control
0x180028a61  lea     rcx, WPP_GLOBAL_Control
0x180028a68  cmp     rax, rcx
0x180028a6b  jz      short loc_180028AAE
0x180028a6d  test    byte ptr [rax+1Ch], 8
0x180028a71  jz      short loc_180028AAE
0x180028a73  cmp     byte ptr [rax+19h], 2
0x180028a77  jb      short loc_180028AAE
0x180028a79  call    RdpX_GetActivityIdPrefix
0x180028a7e  lea     rcx, aFailedToSignal_0; "Failed to Signal Event Queue"
0x180028a85  mov     dword ptr [rsp+70h+var_48], r14d
0x180028a8a  mov     [rsp+70h+var_50], rcx
0x180028a8f  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180028a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a9d  mov     edx, 5Ah ; 'Z'
0x180028aa2  mov     r9d, eax
0x180028aa5  mov     rcx, [rcx+10h]
0x180028aa9  call    WPP_SF_DsD
0x180028aae  test    r12, r12
0x180028ab1  jz      loc_180028B65
0x180028ab7  lea     rbx, [r15+0A4h]
0x180028abe  mov     rcx, rbx; this
0x180028ac1  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180028ac6  mov     rdx, r12; struct ITSEventFilter *
0x180028ac9  mov     rcx, r15; this
0x180028acc  call    ?PopEventFilter@CTSThread@@AEAAJPEAVITSEventFilter@@@Z; CTSThread::PopEventFilter(ITSEventFilter *)
0x180028ad1  mov     rcx, rbx; this
0x180028ad4  mov     r11d, eax
0x180028ad7  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x180028adc  test    r11d, r11d
0x180028adf  jns     loc_180028B65
0x180028ae5  mov     ecx, cs:dword_180044008
0x180028aeb  cmp     ecx, 2
0x180028aee  jbe     short loc_180028B65
0x180028af0  lea     rax, aInternalthread_0; "internalThreadWaitForMultipleObjects"
0x180028af7  mov     [rbp+arg_18], r11d
0x180028afb  mov     [rbp+var_18], rax
0x180028aff  lea     rdx, byte_18003F8AD
0x180028b06  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180028b0d  mov     [rbp+var_20], 6DAh
0x180028b14  mov     [rbp+var_10], rax
0x180028b18  lea     rax, aFailToPopEvent; "Fail to POP event filter! hr = 0x%x"
0x180028b1f  mov     [rbp+var_8], rax
0x180028b23  lea     rax, [rbp+arg_18]
0x180028b27  mov     [rsp+70h+var_28], rax
0x180028b2c  lea     rax, [rbp+var_18]
0x180028b30  mov     [rsp+70h+var_30], rax
0x180028b35  lea     rax, [rbp+var_20]
0x180028b39  mov     [rsp+70h+var_38], rax
0x180028b3e  lea     rax, [rbp+var_10]
0x180028b42  mov     [rsp+70h+var_40], rax
0x180028b47  lea     rax, [rbp+var_1C]
0x180028b4b  mov     [rsp+70h+var_48], rax
0x180028b50  lea     rax, [rbp+var_8]
0x180028b54  mov     [rsp+70h+var_50], rax
0x180028b59  mov     [rbp+var_1C], 80004005h
0x180028b60  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180028b65  lea     r11, [rsp+70h+var_s0]
0x180028b6a  mov     eax, r14d
0x180028b6d  mov     rbx, [r11+30h]
0x180028b71  mov     rsi, [r11+38h]
0x180028b75  mov     rsp, r11
0x180028b78  pop     r15
0x180028b7a  pop     r14
0x180028b7c  pop     r12
0x180028b7e  pop     rdi
0x180028b7f  pop     rbp
0x180028b80  retn
```
