# CWMMCDIProperty::SetNativeValue(tagPROPVARIANT const &)

- ea: `0x180071050`
- end: `0x180071426`
- name: `?SetNativeValue@CWMMCDIProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `982`
- prototype: `int(CWMMCDIProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006e70`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180071050`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007114a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18007114a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800711fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800711fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071068`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007109c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180071068`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007109c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800710be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007116c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071224`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800712d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071374`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800710be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007116c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071224`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800712d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180071374`

## pseudocode

```c
__int64 __fastcall CWMMCDIProperty::SetNativeValue(PROPVARIANT *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  char v38; // [rsp+70h] [rbp+8h] BYREF

  PropVariantClear(this + 4);
  if ( a2->vt == 65 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMMCDIProperty::SetNativeValue", 423);
    v5 = PropVariantClear(this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy(this + 5, a2);
      if ( v5 >= 0 )
      {
        this[4].vt = 31;
        v18 = (unsigned __int16 *)CoTaskMemAlloc(a2->ulVal);
        this[4].hVal.QuadPart = (LONGLONG)v18;
        if ( v18 )
        {
          v5 = StringCchCopyW(v18, (unsigned __int64)a2->ulVal >> 1, a2->caui.pElems);
          if ( v5 < 0 )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMMCDIProperty::SetNativeValue", 446, v5);
            }
            if ( g_wppLevels )
            {
              v11 = 38;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v24, "CWMMCDIProperty::SetNativeValue", 438, -2147024882);
          }
          if ( g_wppLevels )
          {
            v11 = 37;
            goto LABEL_56;
          }
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CWMMCDIProperty::SetNativeValue", 425, v5);
        }
        if ( g_wppLevels )
        {
          v11 = 36;
          goto LABEL_56;
        }
      }
    }
    else
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)v10 + 499) != v5 )
          CallStackContext::TraceFailure(v10, "CWMMCDIProperty::SetNativeValue", 423, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 35;
LABEL_56:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
      }
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMMCDIProperty::SetNativeValue", 451);
    v34 = (__int64 *)CallStackTracing::s_wpInstance;
    v5 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v36 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v36, "CWMMCDIProperty::SetNativeValue", 451, -2147418113);
    }
    if ( g_wppLevels )
    {
      v11 = 39;
      goto LABEL_56;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180071050  push    rbp
0x180071052  push    rsi
0x180071053  push    rdi
0x180071054  push    r12
0x180071056  push    r14
0x180071058  push    r15
0x18007105a  sub     rsp, 38h
0x18007105e  mov     rbp, rcx
0x180071061  mov     rsi, rdx
0x180071064  add     rcx, 60h ; '`'; pvar
0x180071068  call    cs:__imp_PropVariantClear
0x18007106f  nop     dword ptr [rax+rax+00h]
0x180071074  cmp     word ptr [rsi], 41h ; 'A'
0x180071078  lea     r14, aCwmmcdipropert_0; "CWMMCDIProperty::SetNativeValue"
0x18007107f  mov     rdx, r14; char *
0x180071082  lea     rcx, [rsp+68h+arg_0]; this
0x180071087  jnz     loc_180071356
0x18007108d  mov     r8d, 1A7h; int
0x180071093  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071098  lea     rcx, [rbp+78h]; pvar
0x18007109c  call    cs:__imp_PropVariantClear
0x1800710a3  nop     dword ptr [rax+rax+00h]
0x1800710a8  mov     edi, eax
0x1800710aa  test    eax, eax
0x1800710ac  jns     loc_180071143
0x1800710b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710b9  test    rcx, rcx
0x1800710bc  jnz     short loc_180071105
0x1800710be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800710c5  nop     dword ptr [rax+rax+00h]
0x1800710ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710d1  mov     rcx, rax
0x1800710d4  test    rax, rax
0x1800710d7  jz      short loc_1800710F7
0x1800710d9  mov     rax, [rax]
0x1800710dc  mov     edx, 7F0h
0x1800710e1  mov     rax, [rax+8]
0x1800710e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800710ea  test    eax, eax
0x1800710ec  jz      short loc_1800710F7
0x1800710ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800710f5  jmp     short loc_180071105
0x1800710f7  lea     rcx, qword_1800DBF70; this
0x1800710fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071105  cmp     byte ptr [rcx+8], 0
0x180071109  jz      short loc_18007112C
0x18007110b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071110  cmp     [rax+7CCh], edi
0x180071116  jz      short loc_18007112C
0x180071118  mov     r9d, edi; int
0x18007111b  mov     r8d, 1A7h; int
0x180071121  mov     rdx, r14; char *
0x180071124  mov     rcx, rax; this
0x180071127  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007112c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071133  jb      loc_18007140B
0x180071139  mov     edx, 23h ; '#'
0x18007113e  jmp     loc_1800713ED
0x180071143  mov     rdx, rsi; pvarSrc
0x180071146  lea     rcx, [rbp+78h]; pvarDest
0x18007114a  call    cs:__imp_PropVariantCopy
0x180071151  nop     dword ptr [rax+rax+00h]
0x180071156  mov     edi, eax
0x180071158  test    eax, eax
0x18007115a  jns     loc_1800711F1
0x180071160  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071167  test    rcx, rcx
0x18007116a  jnz     short loc_1800711B3
0x18007116c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180071173  nop     dword ptr [rax+rax+00h]
0x180071178  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007117f  mov     rcx, rax
0x180071182  test    rax, rax
0x180071185  jz      short loc_1800711A5
0x180071187  mov     rax, [rax]
0x18007118a  mov     edx, 7F0h
0x18007118f  mov     rax, [rax+8]
0x180071193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071198  test    eax, eax
0x18007119a  jz      short loc_1800711A5
0x18007119c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711a3  jmp     short loc_1800711B3
0x1800711a5  lea     rcx, qword_1800DBF70; this
0x1800711ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800711b3  cmp     byte ptr [rcx+8], 0
0x1800711b7  jz      short loc_1800711DA
0x1800711b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800711be  cmp     [rax+7CCh], edi
0x1800711c4  jz      short loc_1800711DA
0x1800711c6  mov     r9d, edi; int
0x1800711c9  mov     r8d, 1A9h; int
0x1800711cf  mov     rdx, r14; char *
0x1800711d2  mov     rcx, rax; this
0x1800711d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800711da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800711e1  jb      loc_18007140B
0x1800711e7  mov     edx, 24h ; '$'
0x1800711ec  jmp     loc_1800713ED
0x1800711f1  mov     word ptr [rbp+60h], 1Fh
0x1800711f7  mov     ecx, [rsi+8]; cb
0x1800711fa  call    cs:__imp_CoTaskMemAlloc
0x180071201  nop     dword ptr [rax+rax+00h]
0x180071206  mov     [rbp+68h], rax
0x18007120a  test    rax, rax
0x18007120d  jnz     loc_1800712A9
0x180071213  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007121a  mov     edi, 8007000Eh
0x18007121f  test    rcx, rcx
0x180071222  jnz     short loc_18007126B
0x180071224  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007122b  nop     dword ptr [rax+rax+00h]
0x180071230  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071237  mov     rcx, rax
0x18007123a  test    rax, rax
0x18007123d  jz      short loc_18007125D
0x18007123f  mov     rax, [rax]
0x180071242  mov     edx, 7F0h
0x180071247  mov     rax, [rax+8]
0x18007124b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071250  test    eax, eax
0x180071252  jz      short loc_18007125D
0x180071254  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007125b  jmp     short loc_18007126B
0x18007125d  lea     rcx, qword_1800DBF70; this
0x180071264  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007126b  cmp     byte ptr [rcx+8], 0
0x18007126f  jz      short loc_180071292
0x180071271  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071276  cmp     [rax+7CCh], edi
0x18007127c  jz      short loc_180071292
0x18007127e  mov     r9d, edi; int
0x180071281  mov     r8d, 1B6h; int
0x180071287  mov     rdx, r14; char *
0x18007128a  mov     rcx, rax; this
0x18007128d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180071292  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071299  jb      loc_18007140B
0x18007129f  mov     edx, 25h ; '%'
0x1800712a4  jmp     loc_1800713ED
0x1800712a9  mov     edx, [rsi+8]
0x1800712ac  mov     rcx, rax; unsigned __int16 *
0x1800712af  mov     r8, [rsi+10h]; unsigned __int16 *
0x1800712b3  shr     rdx, 1; unsigned __int64
0x1800712b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800712bb  mov     edi, eax
0x1800712bd  test    eax, eax
0x1800712bf  jns     loc_18007140B
0x1800712c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800712cc  test    rcx, rcx
0x1800712cf  jnz     short loc_180071318
0x1800712d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800712d8  nop     dword ptr [rax+rax+00h]
0x1800712dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800712e4  mov     rcx, rax
0x1800712e7  test    rax, rax
0x1800712ea  jz      short loc_18007130A
0x1800712ec  mov     rax, [rax]
0x1800712ef  mov     edx, 7F0h
0x1800712f4  mov     rax, [rax+8]
0x1800712f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712fd  test    eax, eax
0x1800712ff  jz      short loc_18007130A
0x180071301  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180071308  jmp     short loc_180071318
0x18007130a  lea     rcx, qword_1800DBF70; this
0x180071311  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180071318  cmp     byte ptr [rcx+8], 0
0x18007131c  jz      short loc_18007133F
0x18007131e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180071323  cmp     [rax+7CCh], edi
0x180071329  jz      short loc_18007133F
0x18007132b  mov     r9d, edi; int
0x18007132e  mov     r8d, 1BEh; int
0x180071334  mov     rdx, r14; char *
0x180071337  mov     rcx, rax; this
0x18007133a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007133f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071346  jb      loc_18007140B
0x18007134c  mov     edx, 26h ; '&'
0x180071351  jmp     loc_1800713ED
0x180071356  mov     esi, 1C3h
0x18007135b  mov     r8d, esi; int
0x18007135e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180071363  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007136a  mov     edi, 8000FFFFh
0x18007136f  test    rcx, rcx
0x180071372  jnz     short loc_1800713BB
0x180071374  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007137b  nop     dword ptr [rax+rax+00h]
0x180071380  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180071387  mov     rcx, rax
0x18007138a  test    rax, rax
0x18007138d  jz      short loc_1800713AD
0x18007138f  mov     rax, [rax]
0x180071392  mov     edx, 7F0h
0x180071397  mov     rax, [rax+8]
0x18007139b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713a0  test    eax, eax
0x1800713a2  jz      short loc_1800713AD
0x1800713a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800713ab  jmp     short loc_1800713BB
0x1800713ad  lea     rcx, qword_1800DBF70; this
0x1800713b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800713bb  cmp     byte ptr [rcx+8], 0
0x1800713bf  jz      short loc_1800713DF
0x1800713c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800713c6  cmp     [rax+7CCh], edi
0x1800713cc  jz      short loc_1800713DF
0x1800713ce  mov     r9d, edi; int
0x1800713d1  mov     r8d, esi; int
0x1800713d4  mov     rdx, r14; char *
0x1800713d7  mov     rcx, rax; this
0x1800713da  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800713df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800713e6  jb      short loc_18007140B
0x1800713e8  mov     edx, 27h ; '''
0x1800713ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800713f4  lea     r8, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids
0x1800713fb  mov     r9, rbp
0x1800713fe  mov     [rsp+68h+var_48], edi
0x180071402  mov     rcx, [rcx+10h]
0x180071406  call    WPP_SF_qD
0x18007140b  lea     rcx, [rsp+68h+arg_0]; this
0x180071410  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180071415  mov     eax, edi
0x180071417  add     rsp, 38h
0x18007141b  pop     r15
0x18007141d  pop     r14
0x18007141f  pop     r12
0x180071421  pop     rdi
0x180071422  pop     rsi
0x180071423  pop     rbp
0x180071424  retn
```
