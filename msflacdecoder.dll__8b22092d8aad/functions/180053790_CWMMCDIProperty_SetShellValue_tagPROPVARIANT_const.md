# CWMMCDIProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x180053790`
- end: `0x180053c25`
- name: `?SetShellValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1173`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001b654`
- `0x18001ef50`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180053790`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053893`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800539f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800539f0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800537ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800537ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800537ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800537ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053809`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800538b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005395f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053a12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053ac5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053b71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053809`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800538b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005395f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053a12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053ac5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053b71`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetShellValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  unsigned int v4; // r13d
  __int64 v5; // rdx
  HRESULT v6; // esi
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int v19; // eax
  unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  int v24; // edi
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  char v36; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int64 v37; // [rsp+80h] [rbp+50h] BYREF

  v37 = 0;
  if ( a2->vt == 31 )
  {
    v4 = 0;
    PropVariantClear(this + 5);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v36, "CWMMCDIProperty::SetShellValue", 372);
    v6 = PropVariantClear(this + 4);
    if ( v6 >= 0 )
    {
      v6 = PropVariantCopy(this + 4, a2);
      if ( v6 >= 0 )
      {
        this[5].vt = 65;
        v6 = StringCchLengthW(a2->bstrVal, 0x7FFFFFFFu, &v37);
        if ( v6 >= 0 )
        {
          v19 = 2 * v37 + 2;
          this[5].lVal = v19;
          v20 = (unsigned __int16 *)CoTaskMemAlloc(v19);
          this[5].bstrblobVal.pData = (BYTE *)v20;
          if ( v20 )
          {
            v24 = StringCchCopyW(v20, (unsigned __int64)this[5].ulVal >> 1, a2->bstrVal);
            if ( v24 >= 0 )
              goto LABEL_69;
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v24 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetShellValue", 398, v24);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_69;
            v26 = 33;
          }
          else
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
              CallStackTracing::s_wpInstance = v23;
              if ( v23
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
              {
                v22 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v22 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            v24 = -2147024882;
            if ( *((_BYTE *)v22 + 8) )
            {
              v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
              if ( *((_DWORD *)v25 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v25, "CWMMCDIProperty::SetShellValue", 390, -2147024882);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_69;
            v26 = 32;
          }
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v26,
            WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            v24);
          goto LABEL_69;
        }
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != v6 )
            CallStackContext::TraceFailure(v18, "CWMMCDIProperty::SetShellValue", 386, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 31;
          goto LABEL_13;
        }
      }
      else
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
          if ( *((_DWORD *)v14 + 499) != v6 )
            CallStackContext::TraceFailure(v14, "CWMMCDIProperty::SetShellValue", 374, v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 30;
          goto LABEL_13;
        }
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
          CallStackContext::TraceFailure(v9, "CWMMCDIProperty::SetShellValue", 372, v6);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 29;
LABEL_13:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v6);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v36, "CWMMCDIProperty::SetShellValue", 403);
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    v4 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v34 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v34, "CWMMCDIProperty::SetShellValue", 403, -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -2147418113);
  }
LABEL_69:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v36);
  return v4;
}

```

## disassembly

```asm
0x180053790  mov     [rsp-38h+arg_0], rbx
0x180053795  push    rbp
0x180053796  push    rsi
0x180053797  push    rdi
0x180053798  push    r12
0x18005379a  push    r13
0x18005379c  push    r14
0x18005379e  push    r15
0x1800537a0  mov     rbp, rsp
0x1800537a3  sub     rsp, 30h
0x1800537a7  mov     eax, 1Fh
0x1800537ac  mov     [rbp+arg_10], 0
0x1800537b4  mov     rdi, rdx
0x1800537b7  mov     rbx, rcx
0x1800537ba  cmp     [rdx], ax
0x1800537bd  jnz     loc_180053B44
0x1800537c3  add     rcx, 78h ; 'x'; pvar
0x1800537c7  xor     r13d, r13d
0x1800537ca  call    cs:__imp_PropVariantClear
0x1800537d0  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x1800537d7  mov     r8d, 174h; int
0x1800537dd  mov     rdx, r14; char *
0x1800537e0  lea     rcx, [rbp+arg_8]; this
0x1800537e4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800537e9  lea     rcx, [rbx+60h]; pvar
0x1800537ed  call    cs:__imp_PropVariantClear
0x1800537f3  mov     esi, eax
0x1800537f5  test    eax, eax
0x1800537f7  jns     loc_18005388C
0x1800537fd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053804  test    rcx, rcx
0x180053807  jnz     short loc_18005384A
0x180053809  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005380f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053816  mov     rcx, rax
0x180053819  test    rax, rax
0x18005381c  jz      short loc_18005383C
0x18005381e  mov     rax, [rax]
0x180053821  mov     edx, 7F0h
0x180053826  mov     rax, [rax+8]
0x18005382a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005382f  test    eax, eax
0x180053831  jz      short loc_18005383C
0x180053833  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005383a  jmp     short loc_18005384A
0x18005383c  lea     rcx, qword_18006EB20; this
0x180053843  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005384a  cmp     [rcx+8], r13b
0x18005384e  jz      short loc_180053871
0x180053850  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053855  cmp     [rax+7CCh], esi
0x18005385b  jz      short loc_180053871
0x18005385d  mov     r9d, esi; int
0x180053860  mov     r8d, 174h; int
0x180053866  mov     rdx, r14; char *
0x180053869  mov     rcx, rax; this
0x18005386c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053871  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053876  cmp     al, 1
0x180053878  jb      loc_180053C04
0x18005387e  mov     edx, 1Dh
0x180053883  mov     [rsp+30h+var_10], esi
0x180053887  jmp     loc_180053BEA
0x18005388c  mov     rdx, rdi; pvarSrc
0x18005388f  lea     rcx, [rbx+60h]; pvarDest
0x180053893  call    cs:__imp_PropVariantCopy
0x180053899  xor     r15d, r15d
0x18005389c  mov     esi, eax
0x18005389e  test    eax, eax
0x1800538a0  jns     loc_180053931
0x1800538a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538ad  test    rcx, rcx
0x1800538b0  jnz     short loc_1800538F3
0x1800538b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800538b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538bf  mov     rcx, rax
0x1800538c2  test    rax, rax
0x1800538c5  jz      short loc_1800538E5
0x1800538c7  mov     rax, [rax]
0x1800538ca  mov     edx, 7F0h
0x1800538cf  mov     rax, [rax+8]
0x1800538d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538d8  test    eax, eax
0x1800538da  jz      short loc_1800538E5
0x1800538dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538e3  jmp     short loc_1800538F3
0x1800538e5  lea     rcx, qword_18006EB20; this
0x1800538ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538f3  cmp     [rcx+8], r15b
0x1800538f7  jz      short loc_18005391A
0x1800538f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800538fe  cmp     [rax+7CCh], esi
0x180053904  jz      short loc_18005391A
0x180053906  mov     r9d, esi; int
0x180053909  mov     r8d, 176h; int
0x18005390f  mov     rdx, r14; char *
0x180053912  mov     rcx, rax; this
0x180053915  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005391a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18005391f  cmp     al, 1
0x180053921  jb      loc_180053C04
0x180053927  mov     edx, 1Eh
0x18005392c  jmp     loc_180053883
0x180053931  mov     word ptr [rbx+78h], 41h ; 'A'
0x180053937  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x18005393b  mov     rcx, [rdi+8]; unsigned __int16 *
0x18005393f  mov     edx, 7FFFFFFFh; unsigned __int64
0x180053944  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180053949  mov     esi, eax
0x18005394b  test    eax, eax
0x18005394d  jns     loc_1800539DE
0x180053953  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005395a  test    rcx, rcx
0x18005395d  jnz     short loc_1800539A0
0x18005395f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053965  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005396c  mov     rcx, rax
0x18005396f  test    rax, rax
0x180053972  jz      short loc_180053992
0x180053974  mov     rax, [rax]
0x180053977  mov     edx, 7F0h
0x18005397c  mov     rax, [rax+8]
0x180053980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053985  test    eax, eax
0x180053987  jz      short loc_180053992
0x180053989  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053990  jmp     short loc_1800539A0
0x180053992  lea     rcx, qword_18006EB20; this
0x180053999  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800539a0  cmp     [rcx+8], r15b
0x1800539a4  jz      short loc_1800539C7
0x1800539a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800539ab  cmp     [rax+7CCh], esi
0x1800539b1  jz      short loc_1800539C7
0x1800539b3  mov     r9d, esi; int
0x1800539b6  mov     r8d, 182h; int
0x1800539bc  mov     rdx, r14; char *
0x1800539bf  mov     rcx, rax; this
0x1800539c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800539c7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800539cc  cmp     al, 1
0x1800539ce  jb      loc_180053C04
0x1800539d4  mov     edx, 1Fh
0x1800539d9  jmp     loc_180053883
0x1800539de  mov     eax, dword ptr [rbp+arg_10]
0x1800539e1  lea     eax, ds:2[rax*2]
0x1800539e8  mov     ecx, eax; cb
0x1800539ea  mov     [rbx+80h], eax
0x1800539f0  call    cs:__imp_CoTaskMemAlloc
0x1800539f6  mov     [rbx+88h], rax
0x1800539fd  test    rax, rax
0x180053a00  jnz     loc_180053A9A
0x180053a06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a0d  test    rcx, rcx
0x180053a10  jnz     short loc_180053A53
0x180053a12  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053a18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a1f  mov     rcx, rax
0x180053a22  test    rax, rax
0x180053a25  jz      short loc_180053A45
0x180053a27  mov     rax, [rax]
0x180053a2a  mov     edx, 7F0h
0x180053a2f  mov     rax, [rax+8]
0x180053a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a38  test    eax, eax
0x180053a3a  jz      short loc_180053A45
0x180053a3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a43  jmp     short loc_180053A53
0x180053a45  lea     rcx, qword_18006EB20; this
0x180053a4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a53  mov     edi, 8007000Eh
0x180053a58  cmp     [rcx+8], r15b
0x180053a5c  jz      short loc_180053A7F
0x180053a5e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053a63  cmp     [rax+7CCh], edi
0x180053a69  jz      short loc_180053A7F
0x180053a6b  mov     r9d, edi; int
0x180053a6e  mov     r8d, 186h; int
0x180053a74  mov     rdx, r14; char *
0x180053a77  mov     rcx, rax; this
0x180053a7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053a7f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053a84  cmp     al, 1
0x180053a86  jb      loc_180053C04
0x180053a8c  mov     edx, 20h ; ' '
0x180053a91  mov     [rsp+30h+var_10], edi
0x180053a95  jmp     loc_180053BEA
0x180053a9a  mov     edx, [rbx+80h]
0x180053aa0  mov     rcx, rax; unsigned __int16 *
0x180053aa3  mov     r8, [rdi+8]; unsigned __int16 *
0x180053aa7  shr     rdx, 1; unsigned __int64
0x180053aaa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180053aaf  mov     edi, eax
0x180053ab1  test    eax, eax
0x180053ab3  jns     loc_180053C04
0x180053ab9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053ac0  test    rcx, rcx
0x180053ac3  jnz     short loc_180053B06
0x180053ac5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053acb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053ad2  mov     rcx, rax
0x180053ad5  test    rax, rax
0x180053ad8  jz      short loc_180053AF8
0x180053ada  mov     rax, [rax]
0x180053add  mov     edx, 7F0h
0x180053ae2  mov     rax, [rax+8]
0x180053ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aeb  test    eax, eax
0x180053aed  jz      short loc_180053AF8
0x180053aef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053af6  jmp     short loc_180053B06
0x180053af8  lea     rcx, qword_18006EB20; this
0x180053aff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b06  cmp     [rcx+8], r15b
0x180053b0a  jz      short loc_180053B2D
0x180053b0c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053b11  cmp     [rax+7CCh], edi
0x180053b17  jz      short loc_180053B2D
0x180053b19  mov     r9d, edi; int
0x180053b1c  mov     r8d, 18Eh; int
0x180053b22  mov     rdx, r14; char *
0x180053b25  mov     rcx, rax; this
0x180053b28  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053b2d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053b32  cmp     al, 1
0x180053b34  jb      loc_180053C04
0x180053b3a  mov     edx, 21h ; '!'
0x180053b3f  jmp     loc_180053A91
0x180053b44  mov     edi, 193h
0x180053b49  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x180053b50  mov     r8d, edi; int
0x180053b53  lea     rcx, [rbp+arg_8]; this
0x180053b57  mov     rdx, r14; char *
0x180053b5a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180053b5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b66  mov     r13d, 8000FFFFh
0x180053b6c  test    rcx, rcx
0x180053b6f  jnz     short loc_180053BB2
0x180053b71  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053b77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b7e  mov     rcx, rax
0x180053b81  test    rax, rax
0x180053b84  jz      short loc_180053BA4
0x180053b86  mov     rax, [rax]
0x180053b89  mov     edx, 7F0h
0x180053b8e  mov     rax, [rax+8]
0x180053b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b97  test    eax, eax
0x180053b99  jz      short loc_180053BA4
0x180053b9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053ba2  jmp     short loc_180053BB2
0x180053ba4  lea     rcx, qword_18006EB20; this
0x180053bab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053bb2  cmp     byte ptr [rcx+8], 0
0x180053bb6  jz      short loc_180053BD7
0x180053bb8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053bbd  cmp     [rax+7CCh], r13d
0x180053bc4  jz      short loc_180053BD7
0x180053bc6  mov     r9d, r13d; int
0x180053bc9  mov     r8d, edi; int
0x180053bcc  mov     rdx, r14; char *
0x180053bcf  mov     rcx, rax; this
0x180053bd2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053bd7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053bdc  cmp     al, 1
0x180053bde  jb      short loc_180053C04
0x180053be0  mov     edx, 22h ; '"'
0x180053be5  mov     [rsp+30h+var_10], r13d
0x180053bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180053bf1  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x180053bf8  mov     r9, rbx
0x180053bfb  mov     rcx, [rcx+10h]
0x180053bff  call    WPP_SF_qd
0x180053c04  lea     rcx, [rbp+arg_8]; this
0x180053c08  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180053c0d  mov     rbx, [rsp+30h+arg_0]
0x180053c12  mov     eax, r13d
0x180053c15  add     rsp, 30h
0x180053c19  pop     r15
0x180053c1b  pop     r14
0x180053c1d  pop     r13
0x180053c1f  pop     r12
0x180053c21  pop     rdi
0x180053c22  pop     rsi
0x180053c23  pop     rbp
0x180053c24  retn
```
