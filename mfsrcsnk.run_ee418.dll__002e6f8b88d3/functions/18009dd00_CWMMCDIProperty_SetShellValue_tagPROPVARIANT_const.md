# CWMMCDIProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x18009dd00`
- end: `0x18009e195`
- name: `?SetShellValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1173`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x180012a20`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x180074054`
- `0x18009dd00`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009dd79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009de22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009decf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009df82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e035`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e0e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009dd79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009de22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009decf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009df82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e035`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e0e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009df60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009df60`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009de03`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18009de03`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009dd3a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009dd5d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009dd3a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18009dd5d`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetShellValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  unsigned int v4; // r13d
  __int64 v5; // rdx
  HRESULT v6; // esi
  __int64 v7; // r8
  __int64 v8; // r9
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  unsigned int v25; // eax
  unsigned __int16 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  int v32; // edi
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  char v48; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int64 v49; // [rsp+80h] [rbp+50h] BYREF

  v49 = 0;
  if ( a2->vt == 31 )
  {
    v4 = 0;
    PropVariantClear(this + 5);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v48, "CWMMCDIProperty::SetShellValue", 372);
    v6 = PropVariantClear(this + 4);
    if ( v6 >= 0 )
    {
      v6 = PropVariantCopy(this + 4, a2);
      if ( v6 >= 0 )
      {
        this[5].vt = 65;
        v6 = StringCchLengthW(a2->bstrVal, 0x7FFFFFFFu, &v49);
        if ( v6 >= 0 )
        {
          v25 = 2 * v49 + 2;
          this[5].lVal = v25;
          v26 = (unsigned __int16 *)CoTaskMemAlloc(v25);
          this[5].bstrblobVal.pData = (BYTE *)v26;
          if ( v26 )
          {
            v32 = StringCchCopyW(v26, (unsigned __int64)this[5].ulVal >> 1, a2->bstrVal);
            if ( v32 >= 0 )
              goto LABEL_69;
            v38 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
              CallStackTracing::s_wpInstance = v39;
              if ( v39
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
              {
                v38 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v38 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v38 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v32 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetShellValue", 398, v32);
            }
            if ( !g_wppLevels )
              goto LABEL_69;
            v34 = 33;
          }
          else
          {
            v30 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
              CallStackTracing::s_wpInstance = v31;
              if ( v31
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
              {
                v30 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v30 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            v32 = -2147024882;
            if ( *((_BYTE *)v30 + 8) )
            {
              v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
              if ( *((_DWORD *)v33 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v33, "CWMMCDIProperty::SetShellValue", 390, -2147024882);
            }
            if ( !g_wppLevels )
              goto LABEL_69;
            v34 = 32;
          }
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v34,
            &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
            this,
            v32);
          goto LABEL_69;
        }
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          {
            v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v22 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
          if ( *((_DWORD *)v24 + 499) != v6 )
            CallStackContext::TraceFailure(v24, "CWMMCDIProperty::SetShellValue", 386, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 31;
          goto LABEL_13;
        }
      }
      else
      {
        v16 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != v6 )
            CallStackContext::TraceFailure(v18, "CWMMCDIProperty::SetShellValue", 374, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 30;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != v6 )
          CallStackContext::TraceFailure(v11, "CWMMCDIProperty::SetShellValue", 372, v6);
      }
      if ( g_wppLevels )
      {
        v12 = 29;
LABEL_13:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v6);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v48, "CWMMCDIProperty::SetShellValue", 403);
    v44 = (wchar_t *)CallStackTracing::s_wpInstance;
    v4 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
      CallStackTracing::s_wpInstance = v45;
      if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
      {
        v44 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v44 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v44 + 8) )
    {
      v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
      if ( *((_DWORD *)v46 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v46, "CWMMCDIProperty::SetShellValue", 403, -2147418113);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids,
        this,
        -2147418113);
  }
LABEL_69:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v48);
  return v4;
}

```

## disassembly

```asm
0x18009dd00  mov     [rsp-38h+arg_0], rbx
0x18009dd05  push    rbp
0x18009dd06  push    rsi
0x18009dd07  push    rdi
0x18009dd08  push    r12
0x18009dd0a  push    r13
0x18009dd0c  push    r14
0x18009dd0e  push    r15
0x18009dd10  mov     rbp, rsp
0x18009dd13  sub     rsp, 30h
0x18009dd17  mov     eax, 1Fh
0x18009dd1c  mov     [rbp+arg_10], 0
0x18009dd24  mov     rdi, rdx
0x18009dd27  mov     rbx, rcx
0x18009dd2a  cmp     [rdx], ax
0x18009dd2d  jnz     loc_18009E0B4
0x18009dd33  add     rcx, 78h ; 'x'; pvar
0x18009dd37  xor     r13d, r13d
0x18009dd3a  call    cs:__imp_PropVariantClear
0x18009dd40  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x18009dd47  mov     r8d, 174h; int
0x18009dd4d  mov     rdx, r14; char *
0x18009dd50  lea     rcx, [rbp+arg_8]; this
0x18009dd54  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009dd59  lea     rcx, [rbx+60h]; pvar
0x18009dd5d  call    cs:__imp_PropVariantClear
0x18009dd63  mov     esi, eax
0x18009dd65  test    eax, eax
0x18009dd67  jns     loc_18009DDFC
0x18009dd6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009dd74  test    rcx, rcx
0x18009dd77  jnz     short loc_18009DDBA
0x18009dd79  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009dd7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009dd86  mov     rcx, rax
0x18009dd89  test    rax, rax
0x18009dd8c  jz      short loc_18009DDAC
0x18009dd8e  mov     rax, [rax]
0x18009dd91  mov     edx, 7F0h
0x18009dd96  mov     rax, [rax+8]
0x18009dd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dd9f  test    eax, eax
0x18009dda1  jz      short loc_18009DDAC
0x18009dda3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ddaa  jmp     short loc_18009DDBA
0x18009ddac  lea     rcx, qword_1801B07E0; this
0x18009ddb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ddba  cmp     [rcx+8], r13b
0x18009ddbe  jz      short loc_18009DDE1
0x18009ddc0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009ddc5  cmp     [rax+7CCh], esi
0x18009ddcb  jz      short loc_18009DDE1
0x18009ddcd  mov     r9d, esi; int
0x18009ddd0  mov     r8d, 174h; int
0x18009ddd6  mov     rdx, r14; char *
0x18009ddd9  mov     rcx, rax; this
0x18009dddc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009dde1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009dde8  jb      loc_18009E174
0x18009ddee  mov     edx, 1Dh
0x18009ddf3  mov     [rsp+30h+var_10], esi
0x18009ddf7  jmp     loc_18009E15A
0x18009ddfc  mov     rdx, rdi; pvarSrc
0x18009ddff  lea     rcx, [rbx+60h]; pvarDest
0x18009de03  call    cs:__imp_PropVariantCopy
0x18009de09  xor     r15d, r15d
0x18009de0c  mov     esi, eax
0x18009de0e  test    eax, eax
0x18009de10  jns     loc_18009DEA1
0x18009de16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009de1d  test    rcx, rcx
0x18009de20  jnz     short loc_18009DE63
0x18009de22  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009de28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009de2f  mov     rcx, rax
0x18009de32  test    rax, rax
0x18009de35  jz      short loc_18009DE55
0x18009de37  mov     rax, [rax]
0x18009de3a  mov     edx, 7F0h
0x18009de3f  mov     rax, [rax+8]
0x18009de43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009de48  test    eax, eax
0x18009de4a  jz      short loc_18009DE55
0x18009de4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009de53  jmp     short loc_18009DE63
0x18009de55  lea     rcx, qword_1801B07E0; this
0x18009de5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009de63  cmp     [rcx+8], r15b
0x18009de67  jz      short loc_18009DE8A
0x18009de69  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009de6e  cmp     [rax+7CCh], esi
0x18009de74  jz      short loc_18009DE8A
0x18009de76  mov     r9d, esi; int
0x18009de79  mov     r8d, 176h; int
0x18009de7f  mov     rdx, r14; char *
0x18009de82  mov     rcx, rax; this
0x18009de85  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009de8a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009de91  jb      loc_18009E174
0x18009de97  mov     edx, 1Eh
0x18009de9c  jmp     loc_18009DDF3
0x18009dea1  mov     word ptr [rbx+78h], 41h ; 'A'
0x18009dea7  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x18009deab  mov     rcx, [rdi+8]; unsigned __int16 *
0x18009deaf  mov     edx, 7FFFFFFFh; unsigned __int64
0x18009deb4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009deb9  mov     esi, eax
0x18009debb  test    eax, eax
0x18009debd  jns     loc_18009DF4E
0x18009dec3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009deca  test    rcx, rcx
0x18009decd  jnz     short loc_18009DF10
0x18009decf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009ded5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009dedc  mov     rcx, rax
0x18009dedf  test    rax, rax
0x18009dee2  jz      short loc_18009DF02
0x18009dee4  mov     rax, [rax]
0x18009dee7  mov     edx, 7F0h
0x18009deec  mov     rax, [rax+8]
0x18009def0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009def5  test    eax, eax
0x18009def7  jz      short loc_18009DF02
0x18009def9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009df00  jmp     short loc_18009DF10
0x18009df02  lea     rcx, qword_1801B07E0; this
0x18009df09  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009df10  cmp     [rcx+8], r15b
0x18009df14  jz      short loc_18009DF37
0x18009df16  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009df1b  cmp     [rax+7CCh], esi
0x18009df21  jz      short loc_18009DF37
0x18009df23  mov     r9d, esi; int
0x18009df26  mov     r8d, 182h; int
0x18009df2c  mov     rdx, r14; char *
0x18009df2f  mov     rcx, rax; this
0x18009df32  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009df37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009df3e  jb      loc_18009E174
0x18009df44  mov     edx, 1Fh
0x18009df49  jmp     loc_18009DDF3
0x18009df4e  mov     eax, dword ptr [rbp+arg_10]
0x18009df51  lea     eax, ds:2[rax*2]
0x18009df58  mov     ecx, eax; cb
0x18009df5a  mov     [rbx+80h], eax
0x18009df60  call    cs:__imp_CoTaskMemAlloc
0x18009df66  mov     [rbx+88h], rax
0x18009df6d  test    rax, rax
0x18009df70  jnz     loc_18009E00A
0x18009df76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009df7d  test    rcx, rcx
0x18009df80  jnz     short loc_18009DFC3
0x18009df82  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009df88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009df8f  mov     rcx, rax
0x18009df92  test    rax, rax
0x18009df95  jz      short loc_18009DFB5
0x18009df97  mov     rax, [rax]
0x18009df9a  mov     edx, 7F0h
0x18009df9f  mov     rax, [rax+8]
0x18009dfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dfa8  test    eax, eax
0x18009dfaa  jz      short loc_18009DFB5
0x18009dfac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009dfb3  jmp     short loc_18009DFC3
0x18009dfb5  lea     rcx, qword_1801B07E0; this
0x18009dfbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009dfc3  mov     edi, 8007000Eh
0x18009dfc8  cmp     [rcx+8], r15b
0x18009dfcc  jz      short loc_18009DFEF
0x18009dfce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009dfd3  cmp     [rax+7CCh], edi
0x18009dfd9  jz      short loc_18009DFEF
0x18009dfdb  mov     r9d, edi; int
0x18009dfde  mov     r8d, 186h; int
0x18009dfe4  mov     rdx, r14; char *
0x18009dfe7  mov     rcx, rax; this
0x18009dfea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009dfef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009dff6  jb      loc_18009E174
0x18009dffc  mov     edx, 20h ; ' '
0x18009e001  mov     [rsp+30h+var_10], edi
0x18009e005  jmp     loc_18009E15A
0x18009e00a  mov     edx, [rbx+80h]
0x18009e010  mov     rcx, rax; unsigned __int16 *
0x18009e013  mov     r8, [rdi+8]; unsigned __int16 *
0x18009e017  shr     rdx, 1; unsigned __int64
0x18009e01a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009e01f  mov     edi, eax
0x18009e021  test    eax, eax
0x18009e023  jns     loc_18009E174
0x18009e029  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e030  test    rcx, rcx
0x18009e033  jnz     short loc_18009E076
0x18009e035  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e03b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e042  mov     rcx, rax
0x18009e045  test    rax, rax
0x18009e048  jz      short loc_18009E068
0x18009e04a  mov     rax, [rax]
0x18009e04d  mov     edx, 7F0h
0x18009e052  mov     rax, [rax+8]
0x18009e056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e05b  test    eax, eax
0x18009e05d  jz      short loc_18009E068
0x18009e05f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e066  jmp     short loc_18009E076
0x18009e068  lea     rcx, qword_1801B07E0; this
0x18009e06f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e076  cmp     [rcx+8], r15b
0x18009e07a  jz      short loc_18009E09D
0x18009e07c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e081  cmp     [rax+7CCh], edi
0x18009e087  jz      short loc_18009E09D
0x18009e089  mov     r9d, edi; int
0x18009e08c  mov     r8d, 18Eh; int
0x18009e092  mov     rdx, r14; char *
0x18009e095  mov     rcx, rax; this
0x18009e098  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e09d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e0a4  jb      loc_18009E174
0x18009e0aa  mov     edx, 21h ; '!'
0x18009e0af  jmp     loc_18009E001
0x18009e0b4  mov     edi, 193h
0x18009e0b9  lea     r14, aCwmmcdipropert; "CWMMCDIProperty::SetShellValue"
0x18009e0c0  mov     r8d, edi; int
0x18009e0c3  lea     rcx, [rbp+arg_8]; this
0x18009e0c7  mov     rdx, r14; char *
0x18009e0ca  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009e0cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e0d6  mov     r13d, 8000FFFFh
0x18009e0dc  test    rcx, rcx
0x18009e0df  jnz     short loc_18009E122
0x18009e0e1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e0e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e0ee  mov     rcx, rax
0x18009e0f1  test    rax, rax
0x18009e0f4  jz      short loc_18009E114
0x18009e0f6  mov     rax, [rax]
0x18009e0f9  mov     edx, 7F0h
0x18009e0fe  mov     rax, [rax+8]
0x18009e102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e107  test    eax, eax
0x18009e109  jz      short loc_18009E114
0x18009e10b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e112  jmp     short loc_18009E122
0x18009e114  lea     rcx, qword_1801B07E0; this
0x18009e11b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e122  cmp     byte ptr [rcx+8], 0
0x18009e126  jz      short loc_18009E147
0x18009e128  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009e12d  cmp     [rax+7CCh], r13d
0x18009e134  jz      short loc_18009E147
0x18009e136  mov     r9d, r13d; int
0x18009e139  mov     r8d, edi; int
0x18009e13c  mov     rdx, r14; char *
0x18009e13f  mov     rcx, rax; this
0x18009e142  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e147  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e14e  jb      short loc_18009E174
0x18009e150  mov     edx, 22h ; '"'
0x18009e155  mov     [rsp+30h+var_10], r13d
0x18009e15a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e161  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x18009e168  mov     r9, rbx
0x18009e16b  mov     rcx, [rcx+10h]
0x18009e16f  call    WPP_SF_qD
0x18009e174  lea     rcx, [rbp+arg_8]; this
0x18009e178  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009e17d  mov     rbx, [rsp+30h+arg_0]
0x18009e182  mov     eax, r13d
0x18009e185  add     rsp, 30h
0x18009e189  pop     r15
0x18009e18b  pop     r14
0x18009e18d  pop     r13
0x18009e18f  pop     r12
0x18009e191  pop     rdi
0x18009e192  pop     rsi
0x18009e193  pop     rbp
0x18009e194  retn
```
