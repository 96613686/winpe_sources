# CWMProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x1800229e0`
- end: `0x180022f4b`
- name: `?SetShellValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1387`
- prototype: `__int64 __fastcall(CWMProperty *__hidden this, PROPVARIANT *pvarSrc)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009f3a0`
- `0x1800de7f0`
- `0x1800ff6c0`
- `0x180104a10`

## callees

- `0x180005cf4`
- `0x180012a3c`
- `0x18001c6c0`
- `0x18001cee0`
- `0x1800229e0`
- `0x180024890`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022aaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022b5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022c47`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022d03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022dbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022e8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022aaf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022b5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022c47`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022d03`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022dbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022e8c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180022b3a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180022d9c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180022b3a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180022d9c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180022a21`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180022a8d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180022a21`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180022a8d`
- `PROPSYS!StgSerializePropVariant` at `0x180022c25`
- `PROPSYS!StgSerializePropVariant` at `0x180022c25`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetShellValue(CWMProperty *this, PROPVARIANT *pvarSrc)
{
  int v4; // ebx
  CallStackTracing *v5; // rcx
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct _GUID v36; // [rsp+30h] [rbp-20h] BYREF
  struct _GUID v37; // [rsp+40h] [rbp-10h] BYREF
  int v38; // [rsp+80h] [rbp+30h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMProperty::SetShellValue", 89);
  v4 = PropVariantClear((PROPVARIANT *)this + 4);
  if ( v4 >= 0 )
  {
    v4 = PropVariantClear((PROPVARIANT *)this + 5);
    if ( v4 >= 0 )
    {
      v4 = PropVariantCopy((PROPVARIANT *)this + 4, pvarSrc);
      if ( v4 >= 0 )
      {
        v16 = *(_QWORD *)this;
        v38 = 0;
        if ( (*(int (__fastcall **)(CWMProperty *, __int64 *, int *))(v16 + 56))(this, MF_MD_EXTENDEDPROP, &v38) >= 0 )
          v17 = v38;
        else
          v17 = 0;
        if ( v17 )
        {
          *((_WORD *)this + 60) = 65;
          v4 = StgSerializePropVariant(pvarSrc, (SERIALIZEDPROPERTYVALUE **)this + 17, (ULONG *)this + 32);
          if ( v4 < 0 )
          {
            v19 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
              CallStackTracing::s_wpInstance = v20;
              if ( v20
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
              {
                v19 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v19 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetShellValue", 108, v4);
            }
            if ( g_wppLevels )
            {
              v7 = 13;
              goto LABEL_80;
            }
          }
        }
        else
        {
          v22 = *(_QWORD *)this;
          v38 = 0;
          v4 = (*(__int64 (__fastcall **)(CWMProperty *, __int128 *, int *))(v22 + 56))(this, &MF_MD_FSDKTYPE, &v38);
          if ( v4 >= 0 )
          {
            if ( pvarSrc->vt == (_WORD)v38 )
            {
              v4 = PropVariantCopy((PROPVARIANT *)this + 5, pvarSrc);
              if ( v4 < 0 )
              {
                v28 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                  CallStackTracing::s_wpInstance = v29;
                  if ( v29
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
                  {
                    v28 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v28 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v28 + 8) )
                {
                  v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                  if ( *((_DWORD *)v30 + 499) != v4 )
                    CallStackContext::TraceFailure(v30, "CWMProperty::SetShellValue", 127, v4);
                }
                if ( g_wppLevels )
                {
                  v7 = 15;
                  goto LABEL_80;
                }
              }
            }
            else
            {
              v36 = (struct _GUID)MF_MD_FSDKMULTI;
              v37 = (struct _GUID)MF_MD_FSDKTYPE;
              v4 = CWMProperty::TranslateValue(
                     this,
                     (struct tagPROPVARIANT *)this + 4,
                     (struct tagPROPVARIANT *)this + 5,
                     &v37,
                     &v36);
              if ( v4 < 0 )
              {
                v32 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
                  CallStackTracing::s_wpInstance = v33;
                  if ( v33
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
                  {
                    v32 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v32 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v32 + 8) )
                {
                  v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
                  if ( *((_DWORD *)v34 + 499) != v4 )
                    CallStackContext::TraceFailure(v34, "CWMProperty::SetShellValue", 131, v4);
                }
                if ( g_wppLevels )
                {
                  v7 = 16;
                  goto LABEL_80;
                }
              }
            }
          }
          else
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v24 + 8) )
            {
              v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( *((_DWORD *)v26 + 499) != v4 )
                CallStackContext::TraceFailure(v26, "CWMProperty::SetShellValue", 120, v4);
            }
            if ( g_wppLevels )
            {
              v7 = 14;
              goto LABEL_80;
            }
          }
        }
      }
      else
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)v15 + 499) != v4 )
            CallStackContext::TraceFailure(v15, "CWMProperty::SetShellValue", 92, v4);
        }
        if ( g_wppLevels )
        {
          v7 = 12;
          goto LABEL_80;
        }
      }
    }
    else
    {
      v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != v4 )
          CallStackContext::TraceFailure(v11, "CWMProperty::SetShellValue", 90, v4);
      }
      if ( g_wppLevels )
      {
        v7 = 11;
        goto LABEL_80;
      }
    }
  }
  else
  {
    v5 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v5 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)v6 + 499) != v4 )
        CallStackContext::TraceFailure(v6, "CWMProperty::SetShellValue", 89, v4);
    }
    if ( g_wppLevels )
    {
      v7 = 10;
LABEL_80:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v4);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800229e0  mov     [rsp-28h+arg_8], rbx
0x1800229e5  mov     [rsp-28h+arg_10], rsi
0x1800229ea  push    rbp
0x1800229eb  push    rdi
0x1800229ec  push    r13
0x1800229ee  push    r14
0x1800229f0  push    r15
0x1800229f2  mov     rbp, rsp
0x1800229f5  sub     rsp, 50h
0x1800229f9  mov     r14, rdx
0x1800229fc  lea     r13, aCwmpropertySet_0; "CWMProperty::SetShellValue"
0x180022a03  mov     rdi, rcx
0x180022a06  mov     esi, 59h ; 'Y'
0x180022a0b  mov     r8d, esi; int
0x180022a0e  lea     rcx, [rbp+arg_0]; this
0x180022a12  mov     rdx, r13; char *
0x180022a15  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180022a1a  lea     r15, [rdi+60h]
0x180022a1e  mov     rcx, r15; pvar
0x180022a21  call    cs:__imp_PropVariantClear
0x180022a28  nop     dword ptr [rax+rax+00h]
0x180022a2d  mov     ebx, eax
0x180022a2f  test    eax, eax
0x180022a31  jns     short loc_180022A86
0x180022a33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022a3a  test    rcx, rcx
0x180022a3d  jnz     short loc_180022A4B
0x180022a3f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180022a44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180022a4b  cmp     byte ptr [rcx+8], 0
0x180022a4f  jz      short loc_180022A6F
0x180022a51  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022a56  cmp     [rax+7CCh], ebx
0x180022a5c  jz      short loc_180022A6F
0x180022a5e  mov     r9d, ebx; int
0x180022a61  mov     r8d, esi; int
0x180022a64  mov     rdx, r13; char *
0x180022a67  mov     rcx, rax; this
0x180022a6a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022a6f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022a76  jb      loc_180022F26
0x180022a7c  mov     edx, 0Ah
0x180022a81  jmp     loc_180022F08
0x180022a86  lea     rsi, [rdi+78h]
0x180022a8a  mov     rcx, rsi; pvar
0x180022a8d  call    cs:__imp_PropVariantClear
0x180022a94  nop     dword ptr [rax+rax+00h]
0x180022a99  mov     ebx, eax
0x180022a9b  test    eax, eax
0x180022a9d  jns     loc_180022B34
0x180022aa3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022aaa  test    rcx, rcx
0x180022aad  jnz     short loc_180022AF6
0x180022aaf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022ab6  nop     dword ptr [rax+rax+00h]
0x180022abb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022ac2  mov     rcx, rax
0x180022ac5  test    rax, rax
0x180022ac8  jz      short loc_180022AE8
0x180022aca  mov     rax, [rax]
0x180022acd  mov     edx, 7F0h
0x180022ad2  mov     rax, [rax+8]
0x180022ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022adb  test    eax, eax
0x180022add  jz      short loc_180022AE8
0x180022adf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022ae6  jmp     short loc_180022AF6
0x180022ae8  lea     rcx, qword_1801B97E0; this
0x180022aef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022af6  cmp     byte ptr [rcx+8], 0
0x180022afa  jz      short loc_180022B1D
0x180022afc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022b01  cmp     [rax+7CCh], ebx
0x180022b07  jz      short loc_180022B1D
0x180022b09  mov     r9d, ebx; int
0x180022b0c  mov     r8d, 5Ah ; 'Z'; int
0x180022b12  mov     rdx, r13; char *
0x180022b15  mov     rcx, rax; this
0x180022b18  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022b1d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022b24  jb      loc_180022F26
0x180022b2a  mov     edx, 0Bh
0x180022b2f  jmp     loc_180022F08
0x180022b34  mov     rdx, r14; pvarSrc
0x180022b37  mov     rcx, r15; pvarDest
0x180022b3a  call    cs:__imp_PropVariantCopy
0x180022b41  nop     dword ptr [rax+rax+00h]
0x180022b46  mov     ebx, eax
0x180022b48  test    eax, eax
0x180022b4a  jns     loc_180022BE1
0x180022b50  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022b57  test    rcx, rcx
0x180022b5a  jnz     short loc_180022BA3
0x180022b5c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022b63  nop     dword ptr [rax+rax+00h]
0x180022b68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022b6f  mov     rcx, rax
0x180022b72  test    rax, rax
0x180022b75  jz      short loc_180022B95
0x180022b77  mov     rax, [rax]
0x180022b7a  mov     edx, 7F0h
0x180022b7f  mov     rax, [rax+8]
0x180022b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b88  test    eax, eax
0x180022b8a  jz      short loc_180022B95
0x180022b8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022b93  jmp     short loc_180022BA3
0x180022b95  lea     rcx, qword_1801B97E0; this
0x180022b9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022ba3  cmp     byte ptr [rcx+8], 0
0x180022ba7  jz      short loc_180022BCA
0x180022ba9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022bae  cmp     [rax+7CCh], ebx
0x180022bb4  jz      short loc_180022BCA
0x180022bb6  mov     r9d, ebx; int
0x180022bb9  mov     r8d, 5Ch ; '\'; int
0x180022bbf  mov     rdx, r13; char *
0x180022bc2  mov     rcx, rax; this
0x180022bc5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022bca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022bd1  jb      loc_180022F26
0x180022bd7  mov     edx, 0Ch
0x180022bdc  jmp     loc_180022F08
0x180022be1  mov     rax, [rdi]
0x180022be4  lea     r8, [rbp+arg_0]
0x180022be8  lea     rdx, MF_MD_EXTENDEDPROP
0x180022bef  mov     [rbp+arg_0], 0
0x180022bf6  mov     rcx, rdi
0x180022bf9  mov     rax, [rax+38h]
0x180022bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c02  test    eax, eax
0x180022c04  jns     short loc_180022C0A
0x180022c06  xor     eax, eax
0x180022c08  jmp     short loc_180022C0D
0x180022c0a  mov     eax, [rbp+arg_0]
0x180022c0d  test    eax, eax
0x180022c0f  jz      loc_180022CCC
0x180022c15  lea     r8, [rsi+8]; pcb
0x180022c19  mov     word ptr [rsi], 41h ; 'A'
0x180022c1e  lea     rdx, [r8+8]; ppProp
0x180022c22  mov     rcx, r14; ppropvar
0x180022c25  call    cs:__imp_StgSerializePropVariant
0x180022c2c  nop     dword ptr [rax+rax+00h]
0x180022c31  mov     ebx, eax
0x180022c33  test    eax, eax
0x180022c35  jns     loc_180022F26
0x180022c3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022c42  test    rcx, rcx
0x180022c45  jnz     short loc_180022C8E
0x180022c47  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022c4e  nop     dword ptr [rax+rax+00h]
0x180022c53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022c5a  mov     rcx, rax
0x180022c5d  test    rax, rax
0x180022c60  jz      short loc_180022C80
0x180022c62  mov     rax, [rax]
0x180022c65  mov     edx, 7F0h
0x180022c6a  mov     rax, [rax+8]
0x180022c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c73  test    eax, eax
0x180022c75  jz      short loc_180022C80
0x180022c77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022c7e  jmp     short loc_180022C8E
0x180022c80  lea     rcx, qword_1801B97E0; this
0x180022c87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022c8e  cmp     byte ptr [rcx+8], 0
0x180022c92  jz      short loc_180022CB5
0x180022c94  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022c99  cmp     [rax+7CCh], ebx
0x180022c9f  jz      short loc_180022CB5
0x180022ca1  mov     r9d, ebx; int
0x180022ca4  mov     r8d, 6Ch ; 'l'; int
0x180022caa  mov     rdx, r13; char *
0x180022cad  mov     rcx, rax; this
0x180022cb0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022cb5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022cbc  jb      loc_180022F26
0x180022cc2  mov     edx, 0Dh
0x180022cc7  jmp     loc_180022F08
0x180022ccc  mov     rax, [rdi]
0x180022ccf  lea     r8, [rbp+arg_0]
0x180022cd3  lea     rdx, MF_MD_FSDKTYPE
0x180022cda  mov     [rbp+arg_0], 0
0x180022ce1  mov     rcx, rdi
0x180022ce4  mov     rax, [rax+38h]
0x180022ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ced  mov     ebx, eax
0x180022cef  test    eax, eax
0x180022cf1  jns     loc_180022D88
0x180022cf7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022cfe  test    rcx, rcx
0x180022d01  jnz     short loc_180022D4A
0x180022d03  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022d0a  nop     dword ptr [rax+rax+00h]
0x180022d0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022d16  mov     rcx, rax
0x180022d19  test    rax, rax
0x180022d1c  jz      short loc_180022D3C
0x180022d1e  mov     rax, [rax]
0x180022d21  mov     edx, 7F0h
0x180022d26  mov     rax, [rax+8]
0x180022d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d2f  test    eax, eax
0x180022d31  jz      short loc_180022D3C
0x180022d33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022d3a  jmp     short loc_180022D4A
0x180022d3c  lea     rcx, qword_1801B97E0; this
0x180022d43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022d4a  cmp     byte ptr [rcx+8], 0
0x180022d4e  jz      short loc_180022D71
0x180022d50  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022d55  cmp     [rax+7CCh], ebx
0x180022d5b  jz      short loc_180022D71
0x180022d5d  mov     r9d, ebx; int
0x180022d60  mov     r8d, 78h ; 'x'; int
0x180022d66  mov     rdx, r13; char *
0x180022d69  mov     rcx, rax; this
0x180022d6c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022d71  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022d78  jb      loc_180022F26
0x180022d7e  mov     edx, 0Eh
0x180022d83  jmp     loc_180022F08
0x180022d88  movzx   eax, word ptr [rbp+arg_0]
0x180022d8c  cmp     [r14], ax
0x180022d90  jnz     loc_180022E43
0x180022d96  mov     rdx, r14; pvarSrc
0x180022d99  mov     rcx, rsi; pvarDest
0x180022d9c  call    cs:__imp_PropVariantCopy
0x180022da3  nop     dword ptr [rax+rax+00h]
0x180022da8  mov     ebx, eax
0x180022daa  test    eax, eax
0x180022dac  jns     loc_180022F26
0x180022db2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022db9  test    rcx, rcx
0x180022dbc  jnz     short loc_180022E05
0x180022dbe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022dc5  nop     dword ptr [rax+rax+00h]
0x180022dca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022dd1  mov     rcx, rax
0x180022dd4  test    rax, rax
0x180022dd7  jz      short loc_180022DF7
0x180022dd9  mov     rax, [rax]
0x180022ddc  mov     edx, 7F0h
0x180022de1  mov     rax, [rax+8]
0x180022de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dea  test    eax, eax
0x180022dec  jz      short loc_180022DF7
0x180022dee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022df5  jmp     short loc_180022E05
0x180022df7  lea     rcx, qword_1801B97E0; this
0x180022dfe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022e05  cmp     byte ptr [rcx+8], 0
0x180022e09  jz      short loc_180022E2C
0x180022e0b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022e10  cmp     [rax+7CCh], ebx
0x180022e16  jz      short loc_180022E2C
0x180022e18  mov     r9d, ebx; int
0x180022e1b  mov     r8d, 7Fh; int
0x180022e21  mov     rdx, r13; char *
0x180022e24  mov     rcx, rax; this
0x180022e27  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022e2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022e33  jb      loc_180022F26
0x180022e39  mov     edx, 0Fh
0x180022e3e  jmp     loc_180022F08
0x180022e43  movups  xmm0, cs:MF_MD_FSDKMULTI
0x180022e4a  lea     rax, [rbp+var_20]
0x180022e4e  mov     r8, rsi; struct tagPROPVARIANT *
0x180022e51  movups  xmm1, cs:MF_MD_FSDKTYPE
0x180022e58  lea     r9, [rbp+var_10]; struct _GUID
0x180022e5c  mov     [rsp+50h+var_30], rax; struct _GUID
0x180022e61  mov     rdx, r15; struct tagPROPVARIANT *
0x180022e64  mov     rcx, rdi; this
0x180022e67  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x180022e6c  movdqu  xmmword ptr [rbp+var_10.Data1], xmm1
0x180022e71  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x180022e76  mov     ebx, eax
0x180022e78  test    eax, eax
0x180022e7a  jns     loc_180022F26
0x180022e80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022e87  test    rcx, rcx
0x180022e8a  jnz     short loc_180022ED3
0x180022e8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022e93  nop     dword ptr [rax+rax+00h]
0x180022e98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022e9f  mov     rcx, rax
0x180022ea2  test    rax, rax
0x180022ea5  jz      short loc_180022EC5
0x180022ea7  mov     rax, [rax]
0x180022eaa  mov     edx, 7F0h
0x180022eaf  mov     rax, [rax+8]
0x180022eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022eb8  test    eax, eax
0x180022eba  jz      short loc_180022EC5
0x180022ebc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022ec3  jmp     short loc_180022ED3
0x180022ec5  lea     rcx, qword_1801B97E0; this
0x180022ecc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022ed3  cmp     byte ptr [rcx+8], 0
0x180022ed7  jz      short loc_180022EFA
  ... truncated ...
```
