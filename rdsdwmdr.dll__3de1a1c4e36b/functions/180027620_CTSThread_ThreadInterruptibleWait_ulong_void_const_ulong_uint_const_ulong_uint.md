# CTSThread::ThreadInterruptibleWait(ulong,void * const *,ulong,uint const *,ulong,uint *)

- ea: `0x180027620`
- end: `0x1800277da`
- name: `?ThreadInterruptibleWait@CTSThread@@UEAAJKPEBQEAXKPEBIKPEAI@Z`
- size: `442`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, unsigned int, void *const *, unsigned int, const unsigned int *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000160c`
- `0x1800032d4`
- `0x18000f08c`
- `0x18001d114`
- `0x1800225e4`
- `0x180025500`
- `0x180027620`
- `0x180028934`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x180027704`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180027716`: `internalThreadWaitForMultipleObjects failed`
- `0x180027790`: `Unable to create allowed event list filter`
- `0x1800276eb`: `ThreadInterruptibleWait`

## pseudocode

```c
__int64 __fastcall CTSThread::ThreadInterruptibleWait(
        CTSThread **this,
        unsigned int a2,
        void *const *a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7)
{
  CTSEventFilterAllowSpecifiedEvents *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  CTSEventFilterAllowSpecifiedEvents *v15; // rax
  CTSEventFilterAllowSpecifiedEvents *v16; // rbx
  int v17; // edi
  __int64 v18; // r8
  __int64 v19; // r9
  int ActivityIdPrefix; // eax
  int v22; // [rsp+28h] [rbp-49h]
  int v23; // [rsp+50h] [rbp-21h] BYREF
  int v24; // [rsp+54h] [rbp-1Dh] BYREF
  CTSEventFilterAllowSpecifiedEvents *v25; // [rsp+58h] [rbp-19h] BYREF
  const char *v26; // [rsp+60h] [rbp-11h] BYREF
  const char *v27; // [rsp+68h] [rbp-9h] BYREF
  const char *v28; // [rsp+70h] [rbp-1h] BYREF

  v25 = 0;
  v11 = (CTSEventFilterAllowSpecifiedEvents *)operator new(0xC0u);
  if ( v11
    && (v15 = CTSEventFilterAllowSpecifiedEvents::CTSEventFilterAllowSpecifiedEvents(v11, a4, a5), (v16 = v15) != 0) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 + 5) + 8LL))(*((_QWORD *)v15 + 5));
    v17 = CTSEventFilterAllowSpecifiedEvents::Initialize((CTSEventFilterAllowSpecifiedEvents *)((char *)v16 + 16));
    if ( v17 >= 0 )
    {
      v25 = v16;
      v17 = CTSThread::internalThreadWaitForMultipleObjects(this, a2, a3, v16, a6, a7);
      if ( (int)(v17 + 0x80000000) >= 0 && v17 != -2092630012 && (unsigned int)dword_180044008 > 2 )
      {
        v23 = 1654;
        v26 = "ThreadInterruptibleWait";
        v24 = -2147467259;
        v27 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v28 = "internalThreadWaitForMultipleObjects failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)dword_180044008,
          (__int64)&word_18003F8FE,
          v18,
          v19,
          (const unsigned __int16 **)&v28,
          (__int64)&v24,
          (const unsigned __int16 **)&v27,
          (__int64)&v23,
          (const unsigned __int16 **)&v26);
      }
      goto LABEL_14;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 + 5) + 16LL))(*((_QWORD *)v16 + 5));
  }
  else
  {
    v17 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12, v13, v14);
    v22 = v17;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
      ActivityIdPrefix,
      (__int64)"Unable to create allowed event list filter",
      v22);
  }
LABEL_14:
  TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v25);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180027620  push    rbp
0x180027622  push    rbx
0x180027623  push    rsi
0x180027624  push    rdi
0x180027625  push    r14
0x180027627  push    r15
0x180027629  lea     rbp, [rsp-17h]
0x18002762e  sub     rsp, 88h
0x180027635  mov     ebx, r9d
0x180027638  mov     [rbp+3Fh+var_58], 0
0x180027640  mov     rsi, r8
0x180027643  mov     r14d, edx
0x180027646  mov     r15, rcx
0x180027649  mov     ecx, 0C0h; Size
0x18002764e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027653  test    rax, rax
0x180027656  jz      loc_180027767
0x18002765c  mov     r8, [rbp+3Fh+arg_20]; unsigned int *
0x180027660  mov     edx, ebx; unsigned int
0x180027662  mov     rcx, rax; this
0x180027665  call    ??0CTSEventFilterAllowSpecifiedEvents@@QEAA@KPEBI@Z; CTSEventFilterAllowSpecifiedEvents::CTSEventFilterAllowSpecifiedEvents(ulong,uint const *)
0x18002766a  mov     rbx, rax
0x18002766d  test    rax, rax
0x180027670  jz      loc_180027767
0x180027676  mov     rcx, [rax+28h]
0x18002767a  mov     rax, [rcx]
0x18002767d  mov     rax, [rax+8]
0x180027681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027686  lea     rcx, [rbx+10h]; this
0x18002768a  call    ?Initialize@CTSEventFilterAllowSpecifiedEvents@@UEAAJXZ; CTSEventFilterAllowSpecifiedEvents::Initialize(void)
0x18002768f  mov     edi, eax
0x180027691  test    eax, eax
0x180027693  js      loc_180027755
0x180027699  mov     rax, [rbp+3Fh+arg_30]
0x18002769d  mov     r9, rbx; struct ITSEventFilter *
0x1800276a0  mov     [rsp+0B0h+var_88], rax; unsigned int *
0x1800276a5  mov     r8, rsi; void **
0x1800276a8  mov     eax, [rbp+3Fh+arg_28]
0x1800276ab  mov     edx, r14d; unsigned int
0x1800276ae  mov     rcx, r15; this
0x1800276b1  mov     [rsp+0B0h+var_90], eax; unsigned int
0x1800276b5  mov     [rbp+3Fh+var_58], rbx
0x1800276b9  call    ?internalThreadWaitForMultipleObjects@CTSThread@@IEAAJKPEBQEAXPEAVITSEventFilter@@KPEAI@Z; CTSThread::internalThreadWaitForMultipleObjects(ulong,void * const *,ITSEventFilter *,ulong,uint *)
0x1800276be  mov     edi, eax
0x1800276c0  mov     eax, 80000000h
0x1800276c5  lea     ecx, [rdi+rax]
0x1800276c8  test    eax, ecx
0x1800276ca  jnz     loc_1800277BF
0x1800276d0  cmp     edi, 83450004h
0x1800276d6  jz      loc_1800277BF
0x1800276dc  mov     ecx, cs:dword_180044008
0x1800276e2  cmp     ecx, 2
0x1800276e5  jbe     loc_1800277BF
0x1800276eb  lea     rax, aThreadinterrup; "ThreadInterruptibleWait"
0x1800276f2  mov     [rbp+3Fh+var_60], 676h
0x1800276f9  mov     [rbp+3Fh+var_50], rax
0x1800276fd  lea     rdx, word_18003F8FE
0x180027704  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002770b  mov     [rbp+3Fh+var_5C], 80004005h
0x180027712  mov     [rbp+3Fh+var_48], rax
0x180027716  lea     rax, aInternalthread; "internalThreadWaitForMultipleObjects fa"...
0x18002771d  mov     [rbp+3Fh+var_40], rax
0x180027721  lea     rax, [rbp+3Fh+var_50]
0x180027725  mov     [rsp+0B0h+var_70], rax
0x18002772a  lea     rax, [rbp+3Fh+var_60]
0x18002772e  mov     [rsp+0B0h+var_78], rax
0x180027733  lea     rax, [rbp+3Fh+var_48]
0x180027737  mov     [rsp+0B0h+var_80], rax
0x18002773c  lea     rax, [rbp+3Fh+var_5C]
0x180027740  mov     [rsp+0B0h+var_88], rax
0x180027745  lea     rax, [rbp+3Fh+var_40]
0x180027749  mov     qword ptr [rsp+0B0h+var_90], rax
0x18002774e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180027753  jmp     short loc_1800277BF
0x180027755  mov     rcx, [rbx+28h]
0x180027759  mov     rax, [rcx]
0x18002775c  mov     rax, [rax+10h]
0x180027760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027765  jmp     short loc_18002776C
0x180027767  mov     edi, 8007000Eh
0x18002776c  mov     rax, cs:WPP_GLOBAL_Control
0x180027773  lea     rcx, WPP_GLOBAL_Control
0x18002777a  cmp     rax, rcx
0x18002777d  jz      short loc_1800277BF
0x18002777f  test    byte ptr [rax+1Ch], 8
0x180027783  jz      short loc_1800277BF
0x180027785  cmp     byte ptr [rax+19h], 2
0x180027789  jb      short loc_1800277BF
0x18002778b  call    RdpX_GetActivityIdPrefix
0x180027790  lea     rcx, aUnableToCreate_1; "Unable to create allowed event list fil"...
0x180027797  mov     dword ptr [rsp+0B0h+var_88], edi
0x18002779b  mov     qword ptr [rsp+0B0h+var_90], rcx
0x1800277a0  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x1800277a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277ae  mov     edx, 57h ; 'W'
0x1800277b3  mov     r9d, eax
0x1800277b6  mov     rcx, [rcx+10h]
0x1800277ba  call    WPP_SF_DsD
0x1800277bf  lea     rcx, [rbp+3Fh+var_58]
0x1800277c3  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800277c8  mov     eax, edi
0x1800277ca  add     rsp, 88h
0x1800277d1  pop     r15
0x1800277d3  pop     r14
0x1800277d5  pop     rdi
0x1800277d6  pop     rsi
0x1800277d7  pop     rbx
0x1800277d8  pop     rbp
0x1800277d9  retn
```
