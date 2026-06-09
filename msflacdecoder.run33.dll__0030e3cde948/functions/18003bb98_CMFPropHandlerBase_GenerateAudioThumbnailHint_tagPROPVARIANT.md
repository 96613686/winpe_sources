# CMFPropHandlerBase::GenerateAudioThumbnailHint(tagPROPVARIANT *)

- ea: `0x18003bb98`
- end: `0x18003bfa5`
- name: `?GenerateAudioThumbnailHint@CMFPropHandlerBase@@IEAAJPEAUtagPROPVARIANT@@@Z`
- size: `1037`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003bfb0`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002a16c`
- `0x18002b460`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003a894`
- `0x18003b194`
- `0x18003bb98`
- `0x18003e470`
- `0x18003ee98`
- `0x18003f1ac`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003be91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003be91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bc60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bd31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bdd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bede`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bc60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bd31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bdd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003bede`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::GenerateAudioThumbnailHint(CMFPropHandlerBase *this, struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdx
  int v6; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  unsigned __int128 v20; // rax
  const unsigned __int16 *v21; // r15
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // r14
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned __int16 **v28; // [rsp+20h] [rbp-69h]
  unsigned __int64 *v29; // [rsp+28h] [rbp-61h]
  unsigned int v30; // [rsp+30h] [rbp-59h]
  _BYTE v31[16]; // [rsp+40h] [rbp-49h] BYREF
  int v32; // [rsp+50h] [rbp-39h] BYREF
  __int64 v33; // [rsp+54h] [rbp-35h]
  int v34; // [rsp+5Ch] [rbp-2Dh]
  __int64 v35; // [rsp+60h] [rbp-29h]
  _BYTE v36[24]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v37[96]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v38; // [rsp+F0h] [rbp+67h] BYREF

  v38 = 0;
  CMFBaseStringT<unsigned short>::CMFBaseStringT<unsigned short>(v37, L"AlbumArt_");
  CMFBaseStringT<unsigned short>::CMFBaseStringT<unsigned short>(v36, L"_Large.jpg");
  v32 &= 0xFFFFFFF8;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  if ( !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find(
                        (char *)this + 48,
                        &PKEY_Media_CollectionID,
                        &v38,
                        v31)
    || (v4 = v38, *(_WORD *)(v38 + 96) != 31) )
  {
    *(_OWORD *)&a2->vt = 0;
    a2->bstrblobVal.pData = 0;
    v6 = 0;
    goto LABEL_57;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v38,
    "CMFPropHandlerBase::GenerateAudioThumbnailHint",
    1113);
  v6 = CMFBaseStringT<unsigned short>::Append(&v32, v37);
  if ( v6 >= 0 )
  {
    v11 = *(_QWORD *)(v4 + 104);
    if ( v11 && (v6 = CMFBaseStringT<unsigned short>::_Append(&v32, v11, 38), v6 < 0) )
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFPropHandlerBase::GenerateAudioThumbnailHint",
            1114,
            v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_15;
      v10 = 83;
    }
    else
    {
      v6 = CMFBaseStringT<unsigned short>::Append(&v32, v36);
      if ( v6 >= 0 )
      {
        *(_OWORD *)&a2->vt = 0;
        a2->bstrblobVal.pData = 0;
        *(_QWORD *)&v20 = CMFBaseStringT<unsigned short>::PContents(&v32);
        v21 = (const unsigned __int16 *)v20;
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v20 + 2 * v22) );
        v23 = v22 + 1;
        if ( v22 + 1 >= v22 && (v20 = v23 * (unsigned __int128)2uLL, is_mul_ok(v23, 2u)) )
        {
          *(_QWORD *)&v20 = CoTaskMemAlloc(2 * v23);
          a2->hVal.QuadPart = v20;
          v6 = (_QWORD)v20 == 0 ? 0x8007000E : 0;
          if ( (_QWORD)v20 )
          {
            StringCchCopyNExW((unsigned __int16 *)v20, v22 + 1, v21, v22, v28, v29, v30);
            a2->vt = 31;
            goto LABEL_15;
          }
        }
        else
        {
          v6 = -2147024362;
        }
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, *((_QWORD *)&v20 + 1));
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != v6 )
            CallStackContext::TraceFailure(v26, "CMFPropHandlerBase::GenerateAudioThumbnailHint", 1120, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v6);
        goto LABEL_15;
      }
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v6 )
          CallStackContext::TraceFailure(v19, "CMFPropHandlerBase::GenerateAudioThumbnailHint", 1115, v6);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_15;
      v10 = 84;
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != v6 )
        CallStackContext::TraceFailure(v9, "CMFPropHandlerBase::GenerateAudioThumbnailHint", 1113, v6);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_15;
    v10 = 82;
  }
  WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v6);
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
LABEL_57:
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(&v32);
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(v36);
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(v37);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003bb98  push    rbp
0x18003bb9a  push    rbx
0x18003bb9b  push    rsi
0x18003bb9c  push    rdi
0x18003bb9d  push    r12
0x18003bb9f  push    r13
0x18003bba1  push    r14
0x18003bba3  push    r15
0x18003bba5  lea     rbp, [rsp-1Fh]
0x18003bbaa  sub     rsp, 0A8h
0x18003bbb1  mov     rsi, rdx
0x18003bbb4  mov     r13, rcx
0x18003bbb7  xor     r12d, r12d
0x18003bbba  lea     rdx, aAlbumart; "AlbumArt_"
0x18003bbc1  lea     rcx, [rbp+57h+var_60]
0x18003bbc5  mov     [rbp+57h+arg_0], r12
0x18003bbc9  call    ??0?$CMFBaseStringT@G@@QEAA@PEBGJ@Z; CMFBaseStringT<ushort>::CMFBaseStringT<ushort>(ushort const *,long)
0x18003bbce  lea     rdx, aLargeJpg; "_Large.jpg"
0x18003bbd5  lea     rcx, [rbp+57h+var_78]
0x18003bbd9  call    ??0?$CMFBaseStringT@G@@QEAA@PEBGJ@Z; CMFBaseStringT<ushort>::CMFBaseStringT<ushort>(ushort const *,long)
0x18003bbde  and     [rbp+57h+var_90], 0FFFFFFF8h
0x18003bbe2  lea     rcx, [r13+30h]
0x18003bbe6  lea     r9, [rbp+57h+var_A0]
0x18003bbea  mov     [rbp+57h+var_8C], r12
0x18003bbee  lea     r8, [rbp+57h+arg_0]
0x18003bbf2  mov     [rbp+57h+var_80], r12
0x18003bbf6  lea     rdx, PKEY_Media_CollectionID
0x18003bbfd  mov     [rbp+57h+var_84], r12d
0x18003bc01  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x18003bc06  test    eax, eax
0x18003bc08  jz      loc_18003BF65
0x18003bc0e  mov     rdi, [rbp+57h+arg_0]
0x18003bc12  lea     eax, [r12+1Fh]
0x18003bc17  cmp     [rdi+60h], ax
0x18003bc1b  jnz     loc_18003BF65
0x18003bc21  mov     r14d, 459h
0x18003bc27  lea     r15, aCmfprophandler_3; "CMFPropHandlerBase::GenerateAudioThumbn"...
0x18003bc2e  mov     r8d, r14d; int
0x18003bc31  lea     rcx, [rbp+57h+arg_0]; this
0x18003bc35  mov     rdx, r15; char *
0x18003bc38  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003bc3d  lea     rdx, [rbp+57h+var_60]
0x18003bc41  lea     rcx, [rbp+57h+var_90]
0x18003bc45  call    ?Append@?$CMFBaseStringT@G@@QEAAJAEAV1@@Z; CMFBaseStringT<ushort>::Append(CMFBaseStringT<ushort> &)
0x18003bc4a  mov     ebx, eax
0x18003bc4c  test    eax, eax
0x18003bc4e  jns     loc_18003BCFF
0x18003bc54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bc5b  test    rcx, rcx
0x18003bc5e  jnz     short loc_18003BCA1
0x18003bc60  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bc66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bc6d  mov     rcx, rax
0x18003bc70  test    rax, rax
0x18003bc73  jz      short loc_18003BC93
0x18003bc75  mov     rax, [rax]
0x18003bc78  mov     edx, 7F0h
0x18003bc7d  mov     rax, [rax+8]
0x18003bc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc86  test    eax, eax
0x18003bc88  jz      short loc_18003BC93
0x18003bc8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bc91  jmp     short loc_18003BCA1
0x18003bc93  lea     rcx, qword_18006EB20; this
0x18003bc9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bca1  cmp     [rcx+8], r12b
0x18003bca5  jz      short loc_18003BCC5
0x18003bca7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bcac  cmp     [rax+7CCh], ebx
0x18003bcb2  jz      short loc_18003BCC5
0x18003bcb4  mov     r9d, ebx; int
0x18003bcb7  mov     r8d, r14d; int
0x18003bcba  mov     rdx, r15; char *
0x18003bcbd  mov     rcx, rax; this
0x18003bcc0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bcc5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003bcca  cmp     al, 1
0x18003bccc  jb      short loc_18003BCF1
0x18003bcce  mov     edx, 52h ; 'R'
0x18003bcd3  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18003bcd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcde  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003bce5  mov     r9, r13
0x18003bce8  mov     rcx, [rcx+10h]
0x18003bcec  call    WPP_SF_qd
0x18003bcf1  lea     rcx, [rbp+57h+arg_0]; this
0x18003bcf5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003bcfa  jmp     loc_18003BF74
0x18003bcff  mov     rdx, [rdi+68h]
0x18003bd03  test    rdx, rdx
0x18003bd06  jz      loc_18003BDB0
0x18003bd0c  mov     r8d, 26h ; '&'
0x18003bd12  lea     rcx, [rbp+57h+var_90]
0x18003bd16  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x18003bd1b  mov     ebx, eax
0x18003bd1d  test    eax, eax
0x18003bd1f  jns     loc_18003BDB0
0x18003bd25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bd2c  test    rcx, rcx
0x18003bd2f  jnz     short loc_18003BD72
0x18003bd31  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bd37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bd3e  mov     rcx, rax
0x18003bd41  test    rax, rax
0x18003bd44  jz      short loc_18003BD64
0x18003bd46  mov     rax, [rax]
0x18003bd49  mov     edx, 7F0h
0x18003bd4e  mov     rax, [rax+8]
0x18003bd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd57  test    eax, eax
0x18003bd59  jz      short loc_18003BD64
0x18003bd5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bd62  jmp     short loc_18003BD72
0x18003bd64  lea     rcx, qword_18006EB20; this
0x18003bd6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bd72  cmp     [rcx+8], r12b
0x18003bd76  jz      short loc_18003BD99
0x18003bd78  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bd7d  cmp     [rax+7CCh], ebx
0x18003bd83  jz      short loc_18003BD99
0x18003bd85  mov     r9d, ebx; int
0x18003bd88  mov     r8d, 45Ah; int
0x18003bd8e  mov     rdx, r15; char *
0x18003bd91  mov     rcx, rax; this
0x18003bd94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bd99  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003bd9e  cmp     al, 1
0x18003bda0  jb      loc_18003BCF1
0x18003bda6  mov     edx, 53h ; 'S'
0x18003bdab  jmp     loc_18003BCD3
0x18003bdb0  lea     rdx, [rbp+57h+var_78]
0x18003bdb4  lea     rcx, [rbp+57h+var_90]
0x18003bdb8  call    ?Append@?$CMFBaseStringT@G@@QEAAJAEAV1@@Z; CMFBaseStringT<ushort>::Append(CMFBaseStringT<ushort> &)
0x18003bdbd  mov     ebx, eax
0x18003bdbf  test    eax, eax
0x18003bdc1  jns     loc_18003BE52
0x18003bdc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bdce  test    rcx, rcx
0x18003bdd1  jnz     short loc_18003BE14
0x18003bdd3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bdd9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bde0  mov     rcx, rax
0x18003bde3  test    rax, rax
0x18003bde6  jz      short loc_18003BE06
0x18003bde8  mov     rax, [rax]
0x18003bdeb  mov     edx, 7F0h
0x18003bdf0  mov     rax, [rax+8]
0x18003bdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdf9  test    eax, eax
0x18003bdfb  jz      short loc_18003BE06
0x18003bdfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003be04  jmp     short loc_18003BE14
0x18003be06  lea     rcx, qword_18006EB20; this
0x18003be0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003be14  cmp     [rcx+8], r12b
0x18003be18  jz      short loc_18003BE3B
0x18003be1a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003be1f  cmp     [rax+7CCh], ebx
0x18003be25  jz      short loc_18003BE3B
0x18003be27  mov     r9d, ebx; int
0x18003be2a  mov     r8d, 45Bh; int
0x18003be30  mov     rdx, r15; char *
0x18003be33  mov     rcx, rax; this
0x18003be36  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003be3b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003be40  cmp     al, 1
0x18003be42  jb      loc_18003BCF1
0x18003be48  mov     edx, 54h ; 'T'
0x18003be4d  jmp     loc_18003BCD3
0x18003be52  xor     eax, eax
0x18003be54  lea     rcx, [rbp+57h+var_90]
0x18003be58  xorps   xmm0, xmm0
0x18003be5b  movups  xmmword ptr [rsi], xmm0
0x18003be5e  mov     [rsi+10h], rax
0x18003be62  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18003be67  mov     r15, rax
0x18003be6a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003be6e  inc     rdi
0x18003be71  cmp     [rax+rdi*2], r12w
0x18003be76  jnz     short loc_18003BE6E
0x18003be78  lea     r14, [rdi+1]
0x18003be7c  cmp     r14, rdi
0x18003be7f  jb      short loc_18003BECB
0x18003be81  mov     eax, 2
0x18003be86  mul     r14
0x18003be89  test    rdx, rdx
0x18003be8c  jnz     short loc_18003BECB
0x18003be8e  mov     rcx, rax; cb
0x18003be91  call    cs:__imp_CoTaskMemAlloc
0x18003be97  mov     rcx, rax
0x18003be9a  mov     [rsi+8], rax
0x18003be9e  neg     rcx
0x18003bea1  sbb     ebx, ebx
0x18003bea3  not     ebx
0x18003bea5  and     ebx, 8007000Eh
0x18003beab  test    rax, rax
0x18003beae  jz      short loc_18003BED0
0x18003beb0  mov     r9, rdi; unsigned __int64
0x18003beb3  mov     r8, r15; unsigned __int16 *
0x18003beb6  mov     rdx, r14; unsigned __int64
0x18003beb9  mov     rcx, rax; unsigned __int16 *
0x18003bebc  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18003bec1  mov     word ptr [rsi], 1Fh
0x18003bec6  jmp     loc_18003BCF1
0x18003becb  mov     ebx, 80070216h
0x18003bed0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bed7  mov     edi, ebx
0x18003bed9  test    rcx, rcx
0x18003bedc  jnz     short loc_18003BF1F
0x18003bede  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003bee4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003beeb  mov     rcx, rax
0x18003beee  test    rax, rax
0x18003bef1  jz      short loc_18003BF11
0x18003bef3  mov     rax, [rax]
0x18003bef6  mov     edx, 7F0h
0x18003befb  mov     rax, [rax+8]
0x18003beff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf04  test    eax, eax
0x18003bf06  jz      short loc_18003BF11
0x18003bf08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bf0f  jmp     short loc_18003BF1F
0x18003bf11  lea     rcx, qword_18006EB20; this
0x18003bf18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003bf1f  cmp     [rcx+8], r12b
0x18003bf23  jz      short loc_18003BF4A
0x18003bf25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003bf2a  cmp     [rax+7CCh], edi
0x18003bf30  jz      short loc_18003BF4A
0x18003bf32  mov     r9d, edi; int
0x18003bf35  lea     rdx, aCmfprophandler_3; "CMFPropHandlerBase::GenerateAudioThumbn"...
0x18003bf3c  mov     r8d, 460h; int
0x18003bf42  mov     rcx, rax; this
0x18003bf45  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003bf4a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003bf4f  cmp     al, 1
0x18003bf51  jb      loc_18003BCF1
0x18003bf57  mov     edx, 55h ; 'U'
0x18003bf5c  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18003bf60  jmp     loc_18003BCD7
0x18003bf65  xorps   xmm0, xmm0
0x18003bf68  xor     eax, eax
0x18003bf6a  movups  xmmword ptr [rsi], xmm0
0x18003bf6d  mov     [rsi+10h], rax
0x18003bf71  mov     ebx, r12d
0x18003bf74  lea     rcx, [rbp+57h+var_90]
0x18003bf78  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18003bf7d  lea     rcx, [rbp+57h+var_78]
0x18003bf81  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18003bf86  lea     rcx, [rbp+57h+var_60]
0x18003bf8a  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18003bf8f  mov     eax, ebx
0x18003bf91  add     rsp, 0A8h
0x18003bf98  pop     r15
0x18003bf9a  pop     r14
0x18003bf9c  pop     r13
0x18003bf9e  pop     r12
0x18003bfa0  pop     rdi
0x18003bfa1  pop     rsi
0x18003bfa2  pop     rbx
0x18003bfa3  pop     rbp
0x18003bfa4  retn
```
