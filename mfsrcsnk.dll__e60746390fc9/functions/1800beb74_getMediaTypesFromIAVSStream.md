# getMediaTypesFromIAVSStream

- ea: `0x1800beb74`
- end: `0x1800bef08`
- name: `getMediaTypesFromIAVSStream`
- size: `916`
- prototype: `__int64 __fastcall(struct DVINFO *, _QWORD *, __int64, __int64, int, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180074b70`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x18008299c`
- `0x1800beb74`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bec13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800beccb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bed79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bec13`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800beccb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bed79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bebe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800beca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bebe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800beca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bee20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bee31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800beeac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800beebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bee20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bee31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800beeac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800beebe`

## pseudocode

```c
__int64 __fastcall getMediaTypesFromIAVSStream(
        struct DVINFO *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        _QWORD *a6,
        _QWORD *a7)
{
  unsigned int v9; // ebx
  void *v10; // rax
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  _OWORD *v13; // rdi
  int v14; // esi
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  unsigned int i; // ebx
  DWORD v27; // edx
  LPVOID v28; // rcx
  _BYTE v30[8]; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-28h] BYREF
  Tag_DVAudInfo v32; // [rsp+48h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v30, "getMediaTypesFromIAVSStream", 541);
  *a2 = 0;
  v9 = 0;
  *a6 = 0;
  *a7 = 0;
  *(_OWORD *)pv = 0;
  v32 = 0;
  while ( v9 < 2 )
  {
    v10 = CoTaskMemAlloc(0x12u);
    pv[v9] = v10;
    if ( !v10 )
    {
      v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      v13 = 0;
      v14 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v12 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "getMediaTypesFromIAVSStream", 557, -2147024882);
      }
      if ( g_wppLevels )
      {
        v17 = 20;
        goto LABEL_15;
      }
      goto LABEL_38;
    }
    ++v9;
  }
  v13 = CoTaskMemAlloc(0x28u);
  if ( v13 )
  {
    v14 = BuildDVAudInfo(a1, (struct tWAVEFORMATEX **)pv, &v32);
    if ( v14 < 0 )
    {
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v14 )
          CallStackContext::TraceFailure(v25, "getMediaTypesFromIAVSStream", 564, v14);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_5224a96d17d9340ab54e8ef26ba7231d_Traceguids, 0, v14);
      goto LABEL_38;
    }
    *v13 = 0;
    v13[1] = 0;
    *((_QWORD *)v13 + 4) = 0;
    *(_DWORD *)v13 = 40;
    v27 = a1->dwDVVAuxSrc & 0x200000;
    *((_DWORD *)v13 + 2) = v27 != 0 ? 576 : 480;
    *((_DWORD *)v13 + 5) = v27 != 0 ? 144000 : 120000;
    *((_DWORD *)v13 + 1) = 720;
    *((_DWORD *)v13 + 3) = 1572865;
    *((_DWORD *)v13 + 4) = 1685288548;
    if ( v32.bNumAudPin )
    {
      if ( v32.bNumAudPin != 1 )
      {
        if ( v32.bNumAudPin != 2 )
        {
LABEL_48:
          *a2 = v13;
          goto LABEL_49;
        }
        v28 = pv[1];
LABEL_47:
        *a6 = pv[0];
        *a7 = v28;
        goto LABEL_48;
      }
    }
    else
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
    CoTaskMemFree(pv[1]);
    v28 = 0;
    pv[1] = 0;
    goto LABEL_47;
  }
  v19 = (wchar_t *)CallStackTracing::s_wpInstance;
  v14 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
    CallStackTracing::s_wpInstance = v20;
    if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
    {
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v19 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v19 + 8) )
  {
    v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
    if ( *((_DWORD *)v21 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v21, "getMediaTypesFromIAVSStream", 561, -2147024882);
  }
  if ( g_wppLevels )
  {
    v17 = 21;
LABEL_15:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_5224a96d17d9340ab54e8ef26ba7231d_Traceguids, 0, -2147024882);
  }
LABEL_38:
  for ( i = 0; i < 2; ++i )
    CoTaskMemFree(pv[i]);
  CoTaskMemFree(v13);
LABEL_49:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800beb74  mov     [rsp-38h+arg_10], rbx
0x1800beb79  push    rbp
0x1800beb7a  push    rsi
0x1800beb7b  push    rdi
0x1800beb7c  push    r12
0x1800beb7e  push    r13
0x1800beb80  push    r14
0x1800beb82  push    r15
0x1800beb84  mov     rbp, rsp
0x1800beb87  sub     rsp, 60h
0x1800beb8b  mov     rax, cs:__security_cookie
0x1800beb92  xor     rax, rsp
0x1800beb95  mov     [rbp+var_8], rax
0x1800beb99  mov     r12, [rbp+arg_28]
0x1800beb9d  mov     r14, rdx
0x1800beba0  mov     r13, [rbp+arg_30]
0x1800beba4  lea     rdx, aGetmediatypesf; "getMediaTypesFromIAVSStream"
0x1800bebab  mov     r15, rcx
0x1800bebae  mov     r8d, 21Dh; int
0x1800bebb4  lea     rcx, [rbp+var_30]; this
0x1800bebb8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bebbd  xor     esi, esi
0x1800bebbf  xorps   xmm0, xmm0
0x1800bebc2  mov     [r14], rsi
0x1800bebc5  mov     ebx, esi
0x1800bebc7  mov     [r12], rsi
0x1800bebcb  mov     [r13+0], rsi
0x1800bebcf  movdqu  xmmword ptr [rbp+pv], xmm0
0x1800bebd4  movups  xmmword ptr [rbp+var_18.bAudStyle], xmm0
0x1800bebd8  cmp     ebx, 2
0x1800bebdb  jnb     loc_1800BEC9F
0x1800bebe1  mov     ecx, 12h; cb
0x1800bebe6  call    cs:__imp_CoTaskMemAlloc
0x1800bebec  movsxd  rcx, ebx
0x1800bebef  mov     [rbp+rcx*8+pv], rax
0x1800bebf4  test    rax, rax
0x1800bebf7  jz      short loc_1800BEBFD
0x1800bebf9  inc     ebx
0x1800bebfb  jmp     short loc_1800BEBD8
0x1800bebfd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bec04  mov     ebx, 8007000Eh
0x1800bec09  mov     rdi, rsi
0x1800bec0c  mov     esi, ebx
0x1800bec0e  test    rcx, rcx
0x1800bec11  jnz     short loc_1800BEC54
0x1800bec13  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bec19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bec20  mov     rcx, rax
0x1800bec23  test    rax, rax
0x1800bec26  jz      short loc_1800BEC46
0x1800bec28  mov     rax, [rax]
0x1800bec2b  mov     edx, 7F0h
0x1800bec30  mov     rax, [rax+8]
0x1800bec34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec39  test    eax, eax
0x1800bec3b  jz      short loc_1800BEC46
0x1800bec3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bec44  jmp     short loc_1800BEC54
0x1800bec46  lea     rcx, qword_1801B07E0; this
0x1800bec4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bec54  cmp     [rcx+8], dil
0x1800bec58  jz      short loc_1800BEC7F
0x1800bec5a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bec5f  cmp     [rax+7CCh], ebx
0x1800bec65  jz      short loc_1800BEC7F
0x1800bec67  mov     r9d, ebx; int
0x1800bec6a  lea     rdx, aGetmediatypesf; "getMediaTypesFromIAVSStream"
0x1800bec71  mov     r8d, 22Dh; int
0x1800bec77  mov     rcx, rax; this
0x1800bec7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bec7f  mov     r15d, 1
0x1800bec85  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800bec8c  jb      loc_1800BEE16
0x1800bec92  lea     edx, [r15+13h]
0x1800bec96  mov     [rsp+60h+var_40], ebx
0x1800bec9a  jmp     loc_1800BEDFC
0x1800bec9f  mov     ebx, 28h ; '('
0x1800beca4  mov     ecx, ebx; cb
0x1800beca6  call    cs:__imp_CoTaskMemAlloc
0x1800becac  mov     rdi, rax
0x1800becaf  test    rax, rax
0x1800becb2  jnz     loc_1800BED53
0x1800becb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800becbf  mov     ebx, 8007000Eh
0x1800becc4  mov     esi, ebx
0x1800becc6  test    rcx, rcx
0x1800becc9  jnz     short loc_1800BED0C
0x1800beccb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800becd1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800becd8  mov     rcx, rax
0x1800becdb  test    rax, rax
0x1800becde  jz      short loc_1800BECFE
0x1800bece0  mov     rax, [rax]
0x1800bece3  mov     edx, 7F0h
0x1800bece8  mov     rax, [rax+8]
0x1800becec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800becf1  test    eax, eax
0x1800becf3  jz      short loc_1800BECFE
0x1800becf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800becfc  jmp     short loc_1800BED0C
0x1800becfe  lea     rcx, qword_1801B07E0; this
0x1800bed05  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bed0c  cmp     byte ptr [rcx+8], 0
0x1800bed10  jz      short loc_1800BED37
0x1800bed12  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bed17  cmp     [rax+7CCh], ebx
0x1800bed1d  jz      short loc_1800BED37
0x1800bed1f  mov     r9d, ebx; int
0x1800bed22  lea     rdx, aGetmediatypesf; "getMediaTypesFromIAVSStream"
0x1800bed29  mov     r8d, 231h; int
0x1800bed2f  mov     rcx, rax; this
0x1800bed32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bed37  mov     r15d, 1
0x1800bed3d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800bed44  jb      loc_1800BEE16
0x1800bed4a  lea     edx, [r15+14h]
0x1800bed4e  jmp     loc_1800BEC96
0x1800bed53  lea     r8, [rbp+var_18]; struct Tag_DVAudInfo *
0x1800bed57  mov     rcx, r15; struct DVINFO *
0x1800bed5a  lea     rdx, [rbp+pv]; struct tWAVEFORMATEX **
0x1800bed5e  call    ?BuildDVAudInfo@@YAJPEAUDVINFO@@PEAPEAUtWAVEFORMATEX@@PEAUTag_DVAudInfo@@@Z; BuildDVAudInfo(DVINFO *,tWAVEFORMATEX * *,Tag_DVAudInfo *)
0x1800bed63  mov     esi, eax
0x1800bed65  test    eax, eax
0x1800bed67  jns     loc_1800BEE3C
0x1800bed6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bed74  test    rcx, rcx
0x1800bed77  jnz     short loc_1800BEDBA
0x1800bed79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bed7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bed86  mov     rcx, rax
0x1800bed89  test    rax, rax
0x1800bed8c  jz      short loc_1800BEDAC
0x1800bed8e  mov     rax, [rax]
0x1800bed91  mov     edx, 7F0h
0x1800bed96  mov     rax, [rax+8]
0x1800bed9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed9f  test    eax, eax
0x1800beda1  jz      short loc_1800BEDAC
0x1800beda3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bedaa  jmp     short loc_1800BEDBA
0x1800bedac  lea     rcx, qword_1801B07E0; this
0x1800bedb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bedba  cmp     byte ptr [rcx+8], 0
0x1800bedbe  jz      short loc_1800BEDE5
0x1800bedc0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bedc5  cmp     [rax+7CCh], esi
0x1800bedcb  jz      short loc_1800BEDE5
0x1800bedcd  mov     r9d, esi; int
0x1800bedd0  lea     rdx, aGetmediatypesf; "getMediaTypesFromIAVSStream"
0x1800bedd7  mov     r8d, 234h; int
0x1800beddd  mov     rcx, rax; this
0x1800bede0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bede5  mov     r15d, 1
0x1800bedeb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x1800bedf2  jb      short loc_1800BEE16
0x1800bedf4  lea     edx, [r15+15h]
0x1800bedf8  mov     [rsp+60h+var_40], esi
0x1800bedfc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bee03  lea     r8, WPP_5224a96d17d9340ab54e8ef26ba7231d_Traceguids
0x1800bee0a  xor     r9d, r9d
0x1800bee0d  mov     rcx, [rcx+10h]
0x1800bee11  call    WPP_SF_qD
0x1800bee16  xor     ebx, ebx
0x1800bee18  movsxd  rcx, ebx
0x1800bee1b  mov     rcx, [rbp+rcx*8+pv]; pv
0x1800bee20  call    cs:__imp_CoTaskMemFree
0x1800bee26  add     ebx, r15d
0x1800bee29  cmp     ebx, 2
0x1800bee2c  jb      short loc_1800BEE18
0x1800bee2e  mov     rcx, rdi; pv
0x1800bee31  call    cs:__imp_CoTaskMemFree
0x1800bee37  jmp     loc_1800BEED9
0x1800bee3c  xor     eax, eax
0x1800bee3e  xorps   xmm0, xmm0
0x1800bee41  movups  xmmword ptr [rdi], xmm0
0x1800bee44  movups  xmmword ptr [rdi+10h], xmm0
0x1800bee48  mov     [rdi+20h], rax
0x1800bee4c  mov     [rdi], ebx
0x1800bee4e  mov     edx, [r15+10h]
0x1800bee52  and     edx, 200000h
0x1800bee58  mov     eax, edx
0x1800bee5a  neg     eax
0x1800bee5c  sbb     ecx, ecx
0x1800bee5e  and     ecx, 60h
0x1800bee61  add     ecx, 1E0h
0x1800bee67  mov     [rdi+8], ecx
0x1800bee6a  neg     edx
0x1800bee6c  sbb     eax, eax
0x1800bee6e  and     eax, 5DC0h
0x1800bee73  add     eax, 1D4C0h
0x1800bee78  mov     [rdi+14h], eax
0x1800bee7b  mov     dword ptr [rdi+4], 2D0h
0x1800bee82  mov     dword ptr [rdi+0Ch], 180001h
0x1800bee89  mov     dword ptr [rdi+10h], 64737664h
0x1800bee90  movzx   ecx, [rbp+var_18.bNumAudPin]
0x1800bee94  test    ecx, ecx
0x1800bee96  jz      short loc_1800BEEA8
0x1800bee98  sub     ecx, 1
0x1800bee9b  jz      short loc_1800BEEBA
0x1800bee9d  cmp     ecx, 1
0x1800beea0  jnz     short loc_1800BEED6
0x1800beea2  mov     rcx, [rbp+pv+8]
0x1800beea6  jmp     short loc_1800BEECA
0x1800beea8  mov     rcx, [rbp+pv]; pv
0x1800beeac  call    cs:__imp_CoTaskMemFree
0x1800beeb2  mov     [rbp+pv], 0
0x1800beeba  mov     rcx, [rbp+pv+8]; pv
0x1800beebe  call    cs:__imp_CoTaskMemFree
0x1800beec4  xor     ecx, ecx
0x1800beec6  mov     [rbp+pv+8], rcx
0x1800beeca  mov     rax, [rbp+pv]
0x1800beece  mov     [r12], rax
0x1800beed2  mov     [r13+0], rcx
0x1800beed6  mov     [r14], rdi
0x1800beed9  lea     rcx, [rbp+var_30]; this
0x1800beedd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800beee2  mov     eax, esi
0x1800beee4  mov     rcx, [rbp+var_8]
0x1800beee8  xor     rcx, rsp; StackCookie
0x1800beeeb  call    __security_check_cookie
0x1800beef0  mov     rbx, [rsp+60h+arg_10]
0x1800beef8  add     rsp, 60h
0x1800beefc  pop     r15
0x1800beefe  pop     r14
0x1800bef00  pop     r13
0x1800bef02  pop     r12
0x1800bef04  pop     rdi
0x1800bef05  pop     rsi
0x1800bef06  pop     rbp
0x1800bef07  retn
```
