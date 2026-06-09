# CTSThread::ThreadWaitForMultipleObjects(ulong,void * const *,TSWaitType,ulong,uint *)

- ea: `0x180027810`
- end: `0x180027b20`
- name: `?ThreadWaitForMultipleObjects@CTSThread@@UEAAJKPEBQEAXW4TSWaitType@@KPEAI@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180027b30`

## callees

- `0x18000160c`
- `0x18000f068`
- `0x18000f08c`
- `0x1800144c8`
- `0x180017330`
- `0x18001d114`
- `0x180023aa0`
- `0x180023b54`
- `0x1800241e8`
- `0x180026b30`
- `0x180027810`
- `0x180028934`
- `0x180028c98`
- `0x18002a1c4`

## string_xrefs

- `0x180027a25`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18002794d`: `Unable to create blocking filter`
- `0x1800278e9`: `Unable to create allow all filter`
- `0x180027a0c`: `ThreadWaitForMultipleObjects`
- `0x180027a37`: `internalThreadWaitForMultipleObjects failed`

## pseudocode

```c
__int64 __fastcall CTSThread::ThreadWaitForMultipleObjects(
        __int64 a1,
        unsigned int a2,
        void *const *a3,
        int a4,
        unsigned int a5,
        unsigned int *a6)
{
  struct ITSEventFilter *v6; // rbx
  struct ITSEventFilter **v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  int BlockAllFilter; // r14d
  int ActivityIdPrefix; // eax
  int v16; // edx
  const char *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned int *v35; // [rsp+28h] [rbp-58h]
  int v36; // [rsp+50h] [rbp-30h] BYREF
  struct ITSEventFilter *v37; // [rsp+58h] [rbp-28h] BYREF
  const char *v38; // [rsp+60h] [rbp-20h] BYREF
  const char *v39; // [rsp+68h] [rbp-18h] BYREF
  const char *v40; // [rsp+70h] [rbp-10h] BYREF
  int v41; // [rsp+C8h] [rbp+48h] BYREF

  v6 = 0;
  v37 = 0;
  switch ( a4 )
  {
    case 1:
      v10 = (struct ITSEventFilter **)(a1 + 712);
      if ( *(_QWORD *)(a1 + 712) )
        goto LABEL_28;
      BlockAllFilter = CTSEventFilterFactory::CreateBlockAllFilter((struct ITSEventFilter **)(a1 + 712));
      if ( BlockAllFilter >= 0 )
        goto LABEL_27;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v21, v22, v23);
      v16 = 81;
LABEL_20:
      v17 = "Unable to create blocking filter";
      goto LABEL_39;
    case 2:
      v10 = (struct ITSEventFilter **)(a1 + 720);
      if ( *(_QWORD *)(a1 + 720) )
        goto LABEL_28;
      BlockAllFilter = CTSEventFilterFactory::CreateSyncOnlyFilter((struct ITSEventFilter **)(a1 + 720));
      if ( BlockAllFilter >= 0 )
        goto LABEL_27;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v18, v19, v20);
      v16 = 82;
      goto LABEL_20;
    case 3:
      v10 = (struct ITSEventFilter **)(a1 + 728);
      if ( *(_QWORD *)(a1 + 728) )
        goto LABEL_28;
      BlockAllFilter = CTSEventFilterFactory::CreateAllowAllFilter((struct ITSEventFilter **)(a1 + 728));
      if ( BlockAllFilter < 0 )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_40;
        }
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v11, v12, v13);
        v16 = 83;
        v17 = "Unable to create allow all filter";
LABEL_39:
        LODWORD(v35) = BlockAllFilter;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v16,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)v17,
          v35);
        goto LABEL_40;
      }
LABEL_27:
      if ( !*v10 )
        goto LABEL_29;
LABEL_28:
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v37);
      v6 = *v10;
      v37 = *v10;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v37);
      goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
LABEL_29:
  v24 = CTSThread::internalThreadWaitForMultipleObjects((CTSThread **)a1, a2, a3, v6, a5, a6);
  BlockAllFilter = v24;
  if ( (int)(v24 + 0x80000000) >= 0 && v24 != -2092630012 && (unsigned int)dword_180044008 > 2 )
  {
    v41 = 1568;
    v38 = "ThreadWaitForMultipleObjects";
    v36 = -2147467259;
    v39 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    v40 = "internalThreadWaitForMultipleObjects failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0x80000000LL,
      (__int64)byte_18003F943,
      v25,
      v26,
      (const unsigned __int16 **)&v40,
      (__int64)&v36,
      (const unsigned __int16 **)&v39,
      (__int64)&v41,
      (const unsigned __int16 **)&v38);
  }
  CTSCriticalSection::Lock((CTSCriticalSection *)(a1 + 104));
  v27 = *(_QWORD *)(a1 + 128);
  CTSCriticalSection::UnLock((CTSCriticalSection *)(a1 + 104));
  if ( v27 != a1 + 128 )
  {
    BlockAllFilter = CTSThread::SignalEventQueue(a1, v28, v29, v30);
    if ( BlockAllFilter < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v31, v32, v33);
      v16 = 85;
      v17 = "Failed to Signal Event Queue";
      goto LABEL_39;
    }
  }
LABEL_40:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v37);
  return (unsigned int)BlockAllFilter;
}

```

## disassembly

```asm
0x180027810  mov     [rsp-28h+arg_0], rbx
0x180027815  mov     [rsp-28h+arg_8], rsi
0x18002781a  push    rbp
0x18002781b  push    rdi
0x18002781c  push    r12
0x18002781e  push    r14
0x180027820  push    r15
0x180027822  mov     rbp, rsp
0x180027825  sub     rsp, 80h
0x18002782c  xor     ebx, ebx
0x18002782e  mov     rsi, r8
0x180027831  mov     [rbp+var_28], rbx
0x180027835  mov     r12d, edx
0x180027838  mov     r15, rcx
0x18002783b  mov     r10d, r9d
0x18002783e  lea     rax, WPP_GLOBAL_Control
0x180027845  sub     r10d, 1
0x180027849  jz      loc_180027959
0x18002784f  sub     r10d, 1
0x180027853  jz      loc_1800278F5
0x180027859  cmp     r10d, 1
0x18002785d  jz      short loc_180027891
0x18002785f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027866  cmp     rcx, rax
0x180027869  jz      loc_1800279C9
0x18002786f  test    byte ptr [rcx+1Ch], 1
0x180027873  jz      loc_1800279C9
0x180027879  cmp     byte ptr [rcx+19h], 1
0x18002787d  jb      loc_1800279C9
0x180027883  mov     rcx, [rcx+10h]
0x180027887  call    WPP_SF_d
0x18002788c  jmp     loc_1800279C9
0x180027891  lea     rdi, [rcx+2D8h]
0x180027898  cmp     [rdi], rbx
0x18002789b  jnz     loc_1800279B0
0x1800278a1  mov     rcx, rdi; struct ITSEventFilter **
0x1800278a4  call    ?CreateAllowAllFilter@CTSEventFilterFactory@@SAJPEAPEAVITSEventFilter@@@Z; CTSEventFilterFactory::CreateAllowAllFilter(ITSEventFilter * *)
0x1800278a9  mov     r14d, eax
0x1800278ac  test    eax, eax
0x1800278ae  jns     loc_1800279AB
0x1800278b4  mov     rax, cs:WPP_GLOBAL_Control
0x1800278bb  lea     rcx, WPP_GLOBAL_Control
0x1800278c2  cmp     rax, rcx
0x1800278c5  jz      loc_180027AF8
0x1800278cb  test    byte ptr [rax+1Ch], 8
0x1800278cf  jz      loc_180027AF8
0x1800278d5  cmp     byte ptr [rax+19h], 2
0x1800278d9  jb      loc_180027AF8
0x1800278df  call    RdpX_GetActivityIdPrefix
0x1800278e4  mov     edx, 53h ; 'S'
0x1800278e9  lea     rcx, aUnableToCreate; "Unable to create allow all filter"
0x1800278f0  jmp     loc_180027AD4
0x1800278f5  lea     rdi, [rcx+2D0h]
0x1800278fc  cmp     [rdi], rbx
0x1800278ff  jnz     loc_1800279B0
0x180027905  mov     rcx, rdi; struct ITSEventFilter **
0x180027908  call    ?CreateSyncOnlyFilter@CTSEventFilterFactory@@SAJPEAPEAVITSEventFilter@@@Z; CTSEventFilterFactory::CreateSyncOnlyFilter(ITSEventFilter * *)
0x18002790d  mov     r14d, eax
0x180027910  test    eax, eax
0x180027912  jns     loc_1800279AB
0x180027918  mov     rax, cs:WPP_GLOBAL_Control
0x18002791f  lea     rcx, WPP_GLOBAL_Control
0x180027926  cmp     rax, rcx
0x180027929  jz      loc_180027AF8
0x18002792f  test    byte ptr [rax+1Ch], 8
0x180027933  jz      loc_180027AF8
0x180027939  cmp     byte ptr [rax+19h], 2
0x18002793d  jb      loc_180027AF8
0x180027943  call    RdpX_GetActivityIdPrefix
0x180027948  mov     edx, 52h ; 'R'
0x18002794d  lea     rcx, aUnableToCreate_0; "Unable to create blocking filter"
0x180027954  jmp     loc_180027AD4
0x180027959  lea     rdi, [rcx+2C8h]
0x180027960  cmp     [rdi], rbx
0x180027963  jnz     short loc_1800279B0
0x180027965  mov     rcx, rdi; struct ITSEventFilter **
0x180027968  call    ?CreateBlockAllFilter@CTSEventFilterFactory@@SAJPEAPEAVITSEventFilter@@@Z; CTSEventFilterFactory::CreateBlockAllFilter(ITSEventFilter * *)
0x18002796d  mov     r14d, eax
0x180027970  test    eax, eax
0x180027972  jns     short loc_1800279AB
0x180027974  mov     rax, cs:WPP_GLOBAL_Control
0x18002797b  lea     rcx, WPP_GLOBAL_Control
0x180027982  cmp     rax, rcx
0x180027985  jz      loc_180027AF8
0x18002798b  test    byte ptr [rax+1Ch], 8
0x18002798f  jz      loc_180027AF8
0x180027995  cmp     byte ptr [rax+19h], 2
0x180027999  jb      loc_180027AF8
0x18002799f  call    RdpX_GetActivityIdPrefix
0x1800279a4  mov     edx, 51h ; 'Q'
0x1800279a9  jmp     short loc_18002794D
0x1800279ab  cmp     [rdi], rbx
0x1800279ae  jz      short loc_1800279C9
0x1800279b0  lea     rcx, [rbp+var_28]
0x1800279b4  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800279b9  mov     rbx, [rdi]
0x1800279bc  lea     rcx, [rbp+var_28]
0x1800279c0  mov     [rbp+var_28], rbx
0x1800279c4  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800279c9  mov     rax, [rbp+arg_28]
0x1800279cd  mov     r9, rbx; struct ITSEventFilter *
0x1800279d0  mov     [rsp+80h+var_58], rax; unsigned int *
0x1800279d5  mov     r8, rsi; void **
0x1800279d8  mov     eax, [rbp+arg_20]
0x1800279db  mov     edx, r12d; unsigned int
0x1800279de  mov     rcx, r15; this
0x1800279e1  mov     [rsp+80h+var_60], eax; unsigned int
0x1800279e5  call    ?internalThreadWaitForMultipleObjects@CTSThread@@IEAAJKPEBQEAXPEAVITSEventFilter@@KPEAI@Z; CTSThread::internalThreadWaitForMultipleObjects(ulong,void * const *,ITSEventFilter *,ulong,uint *)
0x1800279ea  mov     ecx, 80000000h
0x1800279ef  mov     r14d, eax
0x1800279f2  add     eax, ecx
0x1800279f4  test    ecx, eax
0x1800279f6  jnz     short loc_180027A74
0x1800279f8  cmp     r14d, 83450004h
0x1800279ff  jz      short loc_180027A74
0x180027a01  mov     eax, cs:dword_180044008
0x180027a07  cmp     eax, 2
0x180027a0a  jbe     short loc_180027A74
0x180027a0c  lea     rax, aThreadwaitform; "ThreadWaitForMultipleObjects"
0x180027a13  mov     [rbp+arg_18], 620h
0x180027a1a  mov     [rbp+var_20], rax
0x180027a1e  lea     rdx, byte_18003F943
0x180027a25  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180027a2c  mov     [rbp+var_30], 80004005h
0x180027a33  mov     [rbp+var_18], rax
0x180027a37  lea     rax, aInternalthread; "internalThreadWaitForMultipleObjects fa"...
0x180027a3e  mov     [rbp+var_10], rax
0x180027a42  lea     rax, [rbp+var_20]
0x180027a46  mov     [rsp+80h+var_40], rax
0x180027a4b  lea     rax, [rbp+arg_18]
0x180027a4f  mov     [rsp+80h+var_48], rax
0x180027a54  lea     rax, [rbp+var_18]
0x180027a58  mov     [rsp+80h+var_50], rax
0x180027a5d  lea     rax, [rbp+var_30]
0x180027a61  mov     [rsp+80h+var_58], rax
0x180027a66  lea     rax, [rbp+var_10]
0x180027a6a  mov     qword ptr [rsp+80h+var_60], rax
0x180027a6f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180027a74  lea     rcx, [r15+68h]; this
0x180027a78  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180027a7d  lea     rdi, [r15+80h]
0x180027a84  mov     rbx, [rdi]
0x180027a87  lea     rcx, [r15+68h]; this
0x180027a8b  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180027a90  cmp     rbx, rdi
0x180027a93  jz      short loc_180027AF8
0x180027a95  mov     rcx, r15; this
0x180027a98  call    ?SignalEventQueue@CTSThread@@MEAAJXZ; CTSThread::SignalEventQueue(void)
0x180027a9d  mov     r14d, eax
0x180027aa0  test    eax, eax
0x180027aa2  jns     short loc_180027AF8
0x180027aa4  mov     rax, cs:WPP_GLOBAL_Control
0x180027aab  lea     rcx, WPP_GLOBAL_Control
0x180027ab2  cmp     rax, rcx
0x180027ab5  jz      short loc_180027AF8
0x180027ab7  test    byte ptr [rax+1Ch], 8
0x180027abb  jz      short loc_180027AF8
0x180027abd  cmp     byte ptr [rax+19h], 2
0x180027ac1  jb      short loc_180027AF8
0x180027ac3  call    RdpX_GetActivityIdPrefix
0x180027ac8  mov     edx, 55h ; 'U'
0x180027acd  lea     rcx, aFailedToSignal_0; "Failed to Signal Event Queue"
0x180027ad4  mov     dword ptr [rsp+80h+var_58], r14d
0x180027ad9  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180027ae0  mov     qword ptr [rsp+80h+var_60], rcx
0x180027ae5  mov     r9d, eax
0x180027ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180027aef  mov     rcx, [rcx+10h]
0x180027af3  call    WPP_SF_DsD
0x180027af8  lea     rcx, [rbp+var_28]
0x180027afc  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180027b01  lea     r11, [rsp+80h+var_s0]
0x180027b09  mov     eax, r14d
0x180027b0c  mov     rbx, [r11+30h]
0x180027b10  mov     rsi, [r11+38h]
0x180027b14  mov     rsp, r11
0x180027b17  pop     r15
0x180027b19  pop     r14
0x180027b1b  pop     r12
0x180027b1d  pop     rdi
0x180027b1e  pop     rbp
0x180027b1f  retn
```
