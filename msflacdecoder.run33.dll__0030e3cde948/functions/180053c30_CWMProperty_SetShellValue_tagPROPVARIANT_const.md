# CWMProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x180053c30`
- end: `0x180054175`
- name: `?SetShellValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1349`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180053510`
- `0x180054180`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fa8c`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180053c30`
- `0x180054820`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053da7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053fdd`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053da7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180053fdd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053c67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053d06`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053c67`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053d06`
- `PROPSYS!StgSerializePropVariant` at `0x180053e6c`
- `PROPSYS!StgSerializePropVariant` at `0x180053e6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053c83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053d22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053e88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053f46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053ff9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800540c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053c83`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053d22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053dc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053e88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053f46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053ff9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800540c5`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetShellValue(CWMProperty *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  struct _GUID v36; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v37; // [rsp+40h] [rbp-48h] BYREF
  int v38; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v38, "CWMProperty::SetShellValue", 89);
  v5 = PropVariantClear((PROPVARIANT *)this + 4);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear((PROPVARIANT *)this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy((PROPVARIANT *)this + 4, a2);
      if ( v5 >= 0 )
      {
        if ( (unsigned int)MFGetAttributeUINT32(this, &MF_MD_EXTENDEDPROP, 0) )
        {
          *((_WORD *)this + 60) = 65;
          v5 = StgSerializePropVariant(a2, (SERIALIZEDPROPERTYVALUE **)this + 17, (ULONG *)this + 32);
          if ( v5 < 0 )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
              CallStackTracing::s_wpInstance = v20;
              if ( v20
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
              {
                v19 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v19 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetShellValue", 108, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 13;
              goto LABEL_80;
            }
          }
        }
        else
        {
          v22 = *(_QWORD *)this;
          v38 = 0;
          v5 = (*(__int64 (__fastcall **)(CWMProperty *, __int128 *, int *))(v22 + 56))(this, &MF_MD_FSDKTYPE, &v38);
          if ( v5 >= 0 )
          {
            if ( a2->vt == (_WORD)v38 )
            {
              v5 = PropVariantCopy((PROPVARIANT *)this + 5, a2);
              if ( v5 < 0 )
              {
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
                  v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                  if ( *((_DWORD *)v30 + 499) != v5 )
                    CallStackContext::TraceFailure(v30, "CWMProperty::SetShellValue", 127, v5);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v9 = 15;
                  goto LABEL_80;
                }
              }
            }
            else
            {
              v36 = (struct _GUID)MF_MD_FSDKMULTI;
              v37 = (struct _GUID)MF_MD_FSDKTYPE;
              v5 = CWMProperty::TranslateValue(
                     this,
                     (const struct tagPROPVARIANT *)this + 4,
                     (struct tagPROPVARIANT *)this + 5,
                     &v37,
                     &v36);
              if ( v5 < 0 )
              {
                v32 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
                  CallStackTracing::s_wpInstance = v33;
                  if ( v33
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
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
                  if ( *((_DWORD *)v34 + 499) != v5 )
                    CallStackContext::TraceFailure(v34, "CWMProperty::SetShellValue", 131, v5);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v9 = 16;
                  goto LABEL_80;
                }
              }
            }
          }
          else
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
              if ( *((_DWORD *)v26 + 499) != v5 )
                CallStackContext::TraceFailure(v26, "CWMProperty::SetShellValue", 120, v5);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 14;
              goto LABEL_80;
            }
          }
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v5 )
            CallStackContext::TraceFailure(v17, "CWMProperty::SetShellValue", 92, v5);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 12;
          goto LABEL_80;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v5 )
          CallStackContext::TraceFailure(v13, "CWMProperty::SetShellValue", 90, v5);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 11;
        goto LABEL_80;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CWMProperty::SetShellValue", 89, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 10;
LABEL_80:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180053c30  mov     rax, rsp
0x180053c33  push    rbx
0x180053c34  push    rbp
0x180053c35  push    rsi
0x180053c36  push    rdi
0x180053c37  push    r12
0x180053c39  push    r14
0x180053c3b  sub     rsp, 58h
0x180053c3f  mov     rbp, rdx
0x180053c42  lea     r12, aCwmpropertySet_0; "CWMProperty::SetShellValue"
0x180053c49  mov     rdi, rcx
0x180053c4c  mov     esi, 59h ; 'Y'
0x180053c51  mov     r8d, esi; int
0x180053c54  lea     rcx, [rax+8]; this
0x180053c58  mov     rdx, r12; char *
0x180053c5b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180053c60  lea     r14, [rdi+60h]
0x180053c64  mov     rcx, r14; pvar
0x180053c67  call    cs:__imp_PropVariantClear
0x180053c6d  mov     ebx, eax
0x180053c6f  test    eax, eax
0x180053c71  jns     loc_180053CFF
0x180053c77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053c7e  test    rcx, rcx
0x180053c81  jnz     short loc_180053CC4
0x180053c83  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053c89  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053c90  mov     rcx, rax
0x180053c93  test    rax, rax
0x180053c96  jz      short loc_180053CB6
0x180053c98  mov     rax, [rax]
0x180053c9b  mov     edx, 7F0h
0x180053ca0  mov     rax, [rax+8]
0x180053ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ca9  test    eax, eax
0x180053cab  jz      short loc_180053CB6
0x180053cad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053cb4  jmp     short loc_180053CC4
0x180053cb6  lea     rcx, qword_18006EB20; this
0x180053cbd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053cc4  cmp     byte ptr [rcx+8], 0
0x180053cc8  jz      short loc_180053CE8
0x180053cca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053ccf  cmp     [rax+7CCh], ebx
0x180053cd5  jz      short loc_180053CE8
0x180053cd7  mov     r9d, ebx; int
0x180053cda  mov     r8d, esi; int
0x180053cdd  mov     rdx, r12; char *
0x180053ce0  mov     rcx, rax; this
0x180053ce3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053ce8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053ced  cmp     al, 1
0x180053cef  jb      loc_180054159
0x180053cf5  mov     edx, 0Ah
0x180053cfa  jmp     loc_18005413B
0x180053cff  lea     rsi, [rdi+78h]
0x180053d03  mov     rcx, rsi; pvar
0x180053d06  call    cs:__imp_PropVariantClear
0x180053d0c  mov     ebx, eax
0x180053d0e  test    eax, eax
0x180053d10  jns     loc_180053DA1
0x180053d16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053d1d  test    rcx, rcx
0x180053d20  jnz     short loc_180053D63
0x180053d22  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053d28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053d2f  mov     rcx, rax
0x180053d32  test    rax, rax
0x180053d35  jz      short loc_180053D55
0x180053d37  mov     rax, [rax]
0x180053d3a  mov     edx, 7F0h
0x180053d3f  mov     rax, [rax+8]
0x180053d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d48  test    eax, eax
0x180053d4a  jz      short loc_180053D55
0x180053d4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053d53  jmp     short loc_180053D63
0x180053d55  lea     rcx, qword_18006EB20; this
0x180053d5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053d63  cmp     byte ptr [rcx+8], 0
0x180053d67  jz      short loc_180053D8A
0x180053d69  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053d6e  cmp     [rax+7CCh], ebx
0x180053d74  jz      short loc_180053D8A
0x180053d76  mov     r9d, ebx; int
0x180053d79  mov     r8d, 5Ah ; 'Z'; int
0x180053d7f  mov     rdx, r12; char *
0x180053d82  mov     rcx, rax; this
0x180053d85  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053d8a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053d8f  cmp     al, 1
0x180053d91  jb      loc_180054159
0x180053d97  mov     edx, 0Bh
0x180053d9c  jmp     loc_18005413B
0x180053da1  mov     rdx, rbp; pvarSrc
0x180053da4  mov     rcx, r14; pvarDest
0x180053da7  call    cs:__imp_PropVariantCopy
0x180053dad  mov     ebx, eax
0x180053daf  test    eax, eax
0x180053db1  jns     loc_180053E42
0x180053db7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053dbe  test    rcx, rcx
0x180053dc1  jnz     short loc_180053E04
0x180053dc3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053dc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053dd0  mov     rcx, rax
0x180053dd3  test    rax, rax
0x180053dd6  jz      short loc_180053DF6
0x180053dd8  mov     rax, [rax]
0x180053ddb  mov     edx, 7F0h
0x180053de0  mov     rax, [rax+8]
0x180053de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053de9  test    eax, eax
0x180053deb  jz      short loc_180053DF6
0x180053ded  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053df4  jmp     short loc_180053E04
0x180053df6  lea     rcx, qword_18006EB20; this
0x180053dfd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053e04  cmp     byte ptr [rcx+8], 0
0x180053e08  jz      short loc_180053E2B
0x180053e0a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053e0f  cmp     [rax+7CCh], ebx
0x180053e15  jz      short loc_180053E2B
0x180053e17  mov     r9d, ebx; int
0x180053e1a  mov     r8d, 5Ch ; '\'; int
0x180053e20  mov     rdx, r12; char *
0x180053e23  mov     rcx, rax; this
0x180053e26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053e2b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053e30  cmp     al, 1
0x180053e32  jb      loc_180054159
0x180053e38  mov     edx, 0Ch
0x180053e3d  jmp     loc_18005413B
0x180053e42  xor     r8d, r8d
0x180053e45  lea     rdx, MF_MD_EXTENDEDPROP
0x180053e4c  mov     rcx, rdi
0x180053e4f  call    MFGetAttributeUINT32
0x180053e54  test    eax, eax
0x180053e56  jz      loc_180053F07
0x180053e5c  lea     r8, [rsi+8]; pcb
0x180053e60  mov     word ptr [rsi], 41h ; 'A'
0x180053e65  lea     rdx, [r8+8]; ppProp
0x180053e69  mov     rcx, rbp; ppropvar
0x180053e6c  call    cs:__imp_StgSerializePropVariant
0x180053e72  mov     ebx, eax
0x180053e74  test    eax, eax
0x180053e76  jns     loc_180054159
0x180053e7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053e83  test    rcx, rcx
0x180053e86  jnz     short loc_180053EC9
0x180053e88  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053e8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053e95  mov     rcx, rax
0x180053e98  test    rax, rax
0x180053e9b  jz      short loc_180053EBB
0x180053e9d  mov     rax, [rax]
0x180053ea0  mov     edx, 7F0h
0x180053ea5  mov     rax, [rax+8]
0x180053ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053eae  test    eax, eax
0x180053eb0  jz      short loc_180053EBB
0x180053eb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053eb9  jmp     short loc_180053EC9
0x180053ebb  lea     rcx, qword_18006EB20; this
0x180053ec2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053ec9  cmp     byte ptr [rcx+8], 0
0x180053ecd  jz      short loc_180053EF0
0x180053ecf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053ed4  cmp     [rax+7CCh], ebx
0x180053eda  jz      short loc_180053EF0
0x180053edc  mov     r9d, ebx; int
0x180053edf  mov     r8d, 6Ch ; 'l'; int
0x180053ee5  mov     rdx, r12; char *
0x180053ee8  mov     rcx, rax; this
0x180053eeb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053ef0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053ef5  cmp     al, 1
0x180053ef7  jb      loc_180054159
0x180053efd  mov     edx, 0Dh
0x180053f02  jmp     loc_18005413B
0x180053f07  mov     rax, [rdi]
0x180053f0a  lea     r8, [rsp+88h+arg_0]
0x180053f12  lea     rdx, MF_MD_FSDKTYPE
0x180053f19  mov     [rsp+88h+arg_0], 0
0x180053f24  mov     rcx, rdi
0x180053f27  mov     rax, [rax+38h]
0x180053f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f30  mov     ebx, eax
0x180053f32  test    eax, eax
0x180053f34  jns     loc_180053FC5
0x180053f3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053f41  test    rcx, rcx
0x180053f44  jnz     short loc_180053F87
0x180053f46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053f4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053f53  mov     rcx, rax
0x180053f56  test    rax, rax
0x180053f59  jz      short loc_180053F79
0x180053f5b  mov     rax, [rax]
0x180053f5e  mov     edx, 7F0h
0x180053f63  mov     rax, [rax+8]
0x180053f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f6c  test    eax, eax
0x180053f6e  jz      short loc_180053F79
0x180053f70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053f77  jmp     short loc_180053F87
0x180053f79  lea     rcx, qword_18006EB20; this
0x180053f80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053f87  cmp     byte ptr [rcx+8], 0
0x180053f8b  jz      short loc_180053FAE
0x180053f8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053f92  cmp     [rax+7CCh], ebx
0x180053f98  jz      short loc_180053FAE
0x180053f9a  mov     r9d, ebx; int
0x180053f9d  mov     r8d, 78h ; 'x'; int
0x180053fa3  mov     rdx, r12; char *
0x180053fa6  mov     rcx, rax; this
0x180053fa9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053fae  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180053fb3  cmp     al, 1
0x180053fb5  jb      loc_180054159
0x180053fbb  mov     edx, 0Eh
0x180053fc0  jmp     loc_18005413B
0x180053fc5  movzx   eax, word ptr [rsp+88h+arg_0]
0x180053fcd  cmp     [rbp+0], ax
0x180053fd1  jnz     loc_180054078
0x180053fd7  mov     rdx, rbp; pvarSrc
0x180053fda  mov     rcx, rsi; pvarDest
0x180053fdd  call    cs:__imp_PropVariantCopy
0x180053fe3  mov     ebx, eax
0x180053fe5  test    eax, eax
0x180053fe7  jns     loc_180054159
0x180053fed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053ff4  test    rcx, rcx
0x180053ff7  jnz     short loc_18005403A
0x180053ff9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053fff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054006  mov     rcx, rax
0x180054009  test    rax, rax
0x18005400c  jz      short loc_18005402C
0x18005400e  mov     rax, [rax]
0x180054011  mov     edx, 7F0h
0x180054016  mov     rax, [rax+8]
0x18005401a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005401f  test    eax, eax
0x180054021  jz      short loc_18005402C
0x180054023  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005402a  jmp     short loc_18005403A
0x18005402c  lea     rcx, qword_18006EB20; this
0x180054033  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005403a  cmp     byte ptr [rcx+8], 0
0x18005403e  jz      short loc_180054061
0x180054040  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054045  cmp     [rax+7CCh], ebx
0x18005404b  jz      short loc_180054061
0x18005404d  mov     r9d, ebx; int
0x180054050  mov     r8d, 7Fh; int
0x180054056  mov     rdx, r12; char *
0x180054059  mov     rcx, rax; this
0x18005405c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054061  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180054066  cmp     al, 1
0x180054068  jb      loc_180054159
0x18005406e  mov     edx, 0Fh
0x180054073  jmp     loc_18005413B
0x180054078  movups  xmm0, cs:MF_MD_FSDKMULTI
0x18005407f  lea     rax, [rsp+88h+var_58]
0x180054084  mov     r8, rsi; struct tagPROPVARIANT *
0x180054087  movups  xmm1, cs:MF_MD_FSDKTYPE
0x18005408e  lea     r9, [rsp+88h+var_48]; struct _GUID
0x180054093  mov     [rsp+88h+var_68], rax; struct _GUID
0x180054098  mov     rdx, r14; struct tagPROPVARIANT *
0x18005409b  mov     rcx, rdi; this
0x18005409e  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x1800540a4  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x1800540aa  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x1800540af  mov     ebx, eax
0x1800540b1  test    eax, eax
0x1800540b3  jns     loc_180054159
0x1800540b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800540c0  test    rcx, rcx
0x1800540c3  jnz     short loc_180054106
0x1800540c5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800540cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800540d2  mov     rcx, rax
0x1800540d5  test    rax, rax
0x1800540d8  jz      short loc_1800540F8
0x1800540da  mov     rax, [rax]
0x1800540dd  mov     edx, 7F0h
0x1800540e2  mov     rax, [rax+8]
0x1800540e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540eb  test    eax, eax
0x1800540ed  jz      short loc_1800540F8
0x1800540ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800540f6  jmp     short loc_180054106
0x1800540f8  lea     rcx, qword_18006EB20; this
0x1800540ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054106  cmp     byte ptr [rcx+8], 0
0x18005410a  jz      short loc_18005412D
0x18005410c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
