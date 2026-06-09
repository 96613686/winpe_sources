# CWMProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x180072a80`
- end: `0x18007300e`
- name: `?SetShellValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1422`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800722f0`
- `0x180073020`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18005fed8`
- `0x180072a80`
- `0x180073704`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180072c0f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180072e63`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180072c0f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180072e63`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072ab7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072b62`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072ab7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180072b62`
- `PROPSYS!StgSerializePropVariant` at `0x180072ce0`
- `PROPSYS!StgSerializePropVariant` at `0x180072ce0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072ad9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072b84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072c31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072d02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072dc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072e85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072f57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072ad9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072b84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072c31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072d02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072dc6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072e85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072f57`

## pseudocode

```c
__int64 __fastcall CWMProperty::SetShellValue(CWMProperty *this, const struct tagPROPVARIANT *a2)
{
  __int64 v4; // rdx
  HRESULT v5; // ebx
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
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  struct _GUID v50; // [rsp+30h] [rbp-58h] BYREF
  struct _GUID v51; // [rsp+40h] [rbp-48h] BYREF
  int v52; // [rsp+90h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v52, "CWMProperty::SetShellValue", 89);
  v5 = PropVariantClear((PROPVARIANT *)this + 4);
  if ( v5 >= 0 )
  {
    v5 = PropVariantClear((PROPVARIANT *)this + 5);
    if ( v5 >= 0 )
    {
      v5 = PropVariantCopy((PROPVARIANT *)this + 4, a2);
      if ( v5 >= 0 )
      {
        if ( (unsigned int)MFGetAttributeUINT32(this, MF_MD_EXTENDEDPROP, 0) )
        {
          *((_WORD *)this + 60) = 65;
          v5 = StgSerializePropVariant(a2, (SERIALIZEDPROPERTYVALUE **)this + 17, (ULONG *)this + 32);
          if ( v5 < 0 )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
              CallStackTracing::s_wpInstance = v28;
              if ( v28
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
              {
                v27 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v27 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v27 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(ThreadRelativeContext, "CWMProperty::SetShellValue", 108, v5);
            }
            if ( g_wppLevels )
            {
              v11 = 13;
              goto LABEL_80;
            }
          }
        }
        else
        {
          v30 = *(_QWORD *)this;
          v52 = 0;
          v5 = (*(__int64 (__fastcall **)(CWMProperty *, __int128 *, int *))(v30 + 56))(this, &MF_MD_FSDKTYPE, &v52);
          if ( v5 >= 0 )
          {
            if ( a2->vt == (_WORD)v52 )
            {
              v5 = PropVariantCopy((PROPVARIANT *)this + 5, a2);
              if ( v5 < 0 )
              {
                v40 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
                  CallStackTracing::s_wpInstance = v41;
                  if ( v41
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                  {
                    v40 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v40 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                  }
                }
                if ( *((_BYTE *)v40 + 8) )
                {
                  v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                  if ( *((_DWORD *)v42 + 499) != v5 )
                    CallStackContext::TraceFailure(v42, "CWMProperty::SetShellValue", 127, v5);
                }
                if ( g_wppLevels )
                {
                  v11 = 15;
                  goto LABEL_80;
                }
              }
            }
            else
            {
              v50 = (struct _GUID)MF_MD_FSDKMULTI;
              v51 = (struct _GUID)MF_MD_FSDKTYPE;
              v5 = CWMProperty::TranslateValue(
                     this,
                     (const struct tagPROPVARIANT *)this + 4,
                     (struct tagPROPVARIANT *)this + 5,
                     &v51,
                     &v50);
              if ( v5 < 0 )
              {
                v46 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
                  CallStackTracing::s_wpInstance = v47;
                  if ( v47
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
                  {
                    v46 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v46 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                  }
                }
                if ( *((_BYTE *)v46 + 8) )
                {
                  v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
                  if ( *((_DWORD *)v48 + 499) != v5 )
                    CallStackContext::TraceFailure(v48, "CWMProperty::SetShellValue", 131, v5);
                }
                if ( g_wppLevels )
                {
                  v11 = 16;
                  goto LABEL_80;
                }
              }
            }
          }
          else
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
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
              if ( *((_DWORD *)v36 + 499) != v5 )
                CallStackContext::TraceFailure(v36, "CWMProperty::SetShellValue", 120, v5);
            }
            if ( g_wppLevels )
            {
              v11 = 14;
              goto LABEL_80;
            }
          }
        }
      }
      else
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v5 )
            CallStackContext::TraceFailure(v23, "CWMProperty::SetShellValue", 92, v5);
        }
        if ( g_wppLevels )
        {
          v11 = 12;
          goto LABEL_80;
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
          CallStackContext::TraceFailure(v17, "CWMProperty::SetShellValue", 90, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 11;
        goto LABEL_80;
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
        CallStackContext::TraceFailure(v10, "CWMProperty::SetShellValue", 89, v5);
    }
    if ( g_wppLevels )
    {
      v11 = 10;
LABEL_80:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_560f6a261fab31c223ee22ea268b0035_Traceguids, this, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v52);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180072a80  mov     rax, rsp
0x180072a83  push    rbx
0x180072a84  push    rbp
0x180072a85  push    rsi
0x180072a86  push    rdi
0x180072a87  push    r12
0x180072a89  push    r14
0x180072a8b  sub     rsp, 58h
0x180072a8f  mov     rbp, rdx
0x180072a92  lea     r12, aCwmpropertySet_0; "CWMProperty::SetShellValue"
0x180072a99  mov     rdi, rcx
0x180072a9c  mov     esi, 59h ; 'Y'
0x180072aa1  mov     r8d, esi; int
0x180072aa4  lea     rcx, [rax+8]; this
0x180072aa8  mov     rdx, r12; char *
0x180072aab  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180072ab0  lea     r14, [rdi+60h]
0x180072ab4  mov     rcx, r14; pvar
0x180072ab7  call    cs:__imp_PropVariantClear
0x180072abe  nop     dword ptr [rax+rax+00h]
0x180072ac3  mov     ebx, eax
0x180072ac5  test    eax, eax
0x180072ac7  jns     loc_180072B5B
0x180072acd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072ad4  test    rcx, rcx
0x180072ad7  jnz     short loc_180072B20
0x180072ad9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072ae0  nop     dword ptr [rax+rax+00h]
0x180072ae5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072aec  mov     rcx, rax
0x180072aef  test    rax, rax
0x180072af2  jz      short loc_180072B12
0x180072af4  mov     rax, [rax]
0x180072af7  mov     edx, 7F0h
0x180072afc  mov     rax, [rax+8]
0x180072b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b05  test    eax, eax
0x180072b07  jz      short loc_180072B12
0x180072b09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072b10  jmp     short loc_180072B20
0x180072b12  lea     rcx, qword_1800DBF70; this
0x180072b19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072b20  cmp     byte ptr [rcx+8], 0
0x180072b24  jz      short loc_180072B44
0x180072b26  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072b2b  cmp     [rax+7CCh], ebx
0x180072b31  jz      short loc_180072B44
0x180072b33  mov     r9d, ebx; int
0x180072b36  mov     r8d, esi; int
0x180072b39  mov     rdx, r12; char *
0x180072b3c  mov     rcx, rax; this
0x180072b3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072b44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072b4b  jb      loc_180072FF1
0x180072b51  mov     edx, 0Ah
0x180072b56  jmp     loc_180072FD3
0x180072b5b  lea     rsi, [rdi+78h]
0x180072b5f  mov     rcx, rsi; pvar
0x180072b62  call    cs:__imp_PropVariantClear
0x180072b69  nop     dword ptr [rax+rax+00h]
0x180072b6e  mov     ebx, eax
0x180072b70  test    eax, eax
0x180072b72  jns     loc_180072C09
0x180072b78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072b7f  test    rcx, rcx
0x180072b82  jnz     short loc_180072BCB
0x180072b84  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072b8b  nop     dword ptr [rax+rax+00h]
0x180072b90  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072b97  mov     rcx, rax
0x180072b9a  test    rax, rax
0x180072b9d  jz      short loc_180072BBD
0x180072b9f  mov     rax, [rax]
0x180072ba2  mov     edx, 7F0h
0x180072ba7  mov     rax, [rax+8]
0x180072bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072bb0  test    eax, eax
0x180072bb2  jz      short loc_180072BBD
0x180072bb4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072bbb  jmp     short loc_180072BCB
0x180072bbd  lea     rcx, qword_1800DBF70; this
0x180072bc4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072bcb  cmp     byte ptr [rcx+8], 0
0x180072bcf  jz      short loc_180072BF2
0x180072bd1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072bd6  cmp     [rax+7CCh], ebx
0x180072bdc  jz      short loc_180072BF2
0x180072bde  mov     r9d, ebx; int
0x180072be1  mov     r8d, 5Ah ; 'Z'; int
0x180072be7  mov     rdx, r12; char *
0x180072bea  mov     rcx, rax; this
0x180072bed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072bf2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072bf9  jb      loc_180072FF1
0x180072bff  mov     edx, 0Bh
0x180072c04  jmp     loc_180072FD3
0x180072c09  mov     rdx, rbp; pvarSrc
0x180072c0c  mov     rcx, r14; pvarDest
0x180072c0f  call    cs:__imp_PropVariantCopy
0x180072c16  nop     dword ptr [rax+rax+00h]
0x180072c1b  mov     ebx, eax
0x180072c1d  test    eax, eax
0x180072c1f  jns     loc_180072CB6
0x180072c25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072c2c  test    rcx, rcx
0x180072c2f  jnz     short loc_180072C78
0x180072c31  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072c38  nop     dword ptr [rax+rax+00h]
0x180072c3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072c44  mov     rcx, rax
0x180072c47  test    rax, rax
0x180072c4a  jz      short loc_180072C6A
0x180072c4c  mov     rax, [rax]
0x180072c4f  mov     edx, 7F0h
0x180072c54  mov     rax, [rax+8]
0x180072c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c5d  test    eax, eax
0x180072c5f  jz      short loc_180072C6A
0x180072c61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072c68  jmp     short loc_180072C78
0x180072c6a  lea     rcx, qword_1800DBF70; this
0x180072c71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072c78  cmp     byte ptr [rcx+8], 0
0x180072c7c  jz      short loc_180072C9F
0x180072c7e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072c83  cmp     [rax+7CCh], ebx
0x180072c89  jz      short loc_180072C9F
0x180072c8b  mov     r9d, ebx; int
0x180072c8e  mov     r8d, 5Ch ; '\'; int
0x180072c94  mov     rdx, r12; char *
0x180072c97  mov     rcx, rax; this
0x180072c9a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072c9f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072ca6  jb      loc_180072FF1
0x180072cac  mov     edx, 0Ch
0x180072cb1  jmp     loc_180072FD3
0x180072cb6  xor     r8d, r8d
0x180072cb9  lea     rdx, MF_MD_EXTENDEDPROP
0x180072cc0  mov     rcx, rdi
0x180072cc3  call    MFGetAttributeUINT32
0x180072cc8  test    eax, eax
0x180072cca  jz      loc_180072D87
0x180072cd0  lea     r8, [rsi+8]; pcb
0x180072cd4  mov     word ptr [rsi], 41h ; 'A'
0x180072cd9  lea     rdx, [r8+8]; ppProp
0x180072cdd  mov     rcx, rbp; ppropvar
0x180072ce0  call    cs:__imp_StgSerializePropVariant
0x180072ce7  nop     dword ptr [rax+rax+00h]
0x180072cec  mov     ebx, eax
0x180072cee  test    eax, eax
0x180072cf0  jns     loc_180072FF1
0x180072cf6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072cfd  test    rcx, rcx
0x180072d00  jnz     short loc_180072D49
0x180072d02  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072d09  nop     dword ptr [rax+rax+00h]
0x180072d0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072d15  mov     rcx, rax
0x180072d18  test    rax, rax
0x180072d1b  jz      short loc_180072D3B
0x180072d1d  mov     rax, [rax]
0x180072d20  mov     edx, 7F0h
0x180072d25  mov     rax, [rax+8]
0x180072d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d2e  test    eax, eax
0x180072d30  jz      short loc_180072D3B
0x180072d32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072d39  jmp     short loc_180072D49
0x180072d3b  lea     rcx, qword_1800DBF70; this
0x180072d42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072d49  cmp     byte ptr [rcx+8], 0
0x180072d4d  jz      short loc_180072D70
0x180072d4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072d54  cmp     [rax+7CCh], ebx
0x180072d5a  jz      short loc_180072D70
0x180072d5c  mov     r9d, ebx; int
0x180072d5f  mov     r8d, 6Ch ; 'l'; int
0x180072d65  mov     rdx, r12; char *
0x180072d68  mov     rcx, rax; this
0x180072d6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072d70  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072d77  jb      loc_180072FF1
0x180072d7d  mov     edx, 0Dh
0x180072d82  jmp     loc_180072FD3
0x180072d87  mov     rax, [rdi]
0x180072d8a  lea     r8, [rsp+88h+arg_0]
0x180072d92  lea     rdx, MF_MD_FSDKTYPE
0x180072d99  mov     [rsp+88h+arg_0], 0
0x180072da4  mov     rcx, rdi
0x180072da7  mov     rax, [rax+38h]
0x180072dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072db0  mov     ebx, eax
0x180072db2  test    eax, eax
0x180072db4  jns     loc_180072E4B
0x180072dba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072dc1  test    rcx, rcx
0x180072dc4  jnz     short loc_180072E0D
0x180072dc6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072dcd  nop     dword ptr [rax+rax+00h]
0x180072dd2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072dd9  mov     rcx, rax
0x180072ddc  test    rax, rax
0x180072ddf  jz      short loc_180072DFF
0x180072de1  mov     rax, [rax]
0x180072de4  mov     edx, 7F0h
0x180072de9  mov     rax, [rax+8]
0x180072ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072df2  test    eax, eax
0x180072df4  jz      short loc_180072DFF
0x180072df6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072dfd  jmp     short loc_180072E0D
0x180072dff  lea     rcx, qword_1800DBF70; this
0x180072e06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072e0d  cmp     byte ptr [rcx+8], 0
0x180072e11  jz      short loc_180072E34
0x180072e13  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072e18  cmp     [rax+7CCh], ebx
0x180072e1e  jz      short loc_180072E34
0x180072e20  mov     r9d, ebx; int
0x180072e23  mov     r8d, 78h ; 'x'; int
0x180072e29  mov     rdx, r12; char *
0x180072e2c  mov     rcx, rax; this
0x180072e2f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072e34  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072e3b  jb      loc_180072FF1
0x180072e41  mov     edx, 0Eh
0x180072e46  jmp     loc_180072FD3
0x180072e4b  movzx   eax, word ptr [rsp+88h+arg_0]
0x180072e53  cmp     [rbp+0], ax
0x180072e57  jnz     loc_180072F0A
0x180072e5d  mov     rdx, rbp; pvarSrc
0x180072e60  mov     rcx, rsi; pvarDest
0x180072e63  call    cs:__imp_PropVariantCopy
0x180072e6a  nop     dword ptr [rax+rax+00h]
0x180072e6f  mov     ebx, eax
0x180072e71  test    eax, eax
0x180072e73  jns     loc_180072FF1
0x180072e79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072e80  test    rcx, rcx
0x180072e83  jnz     short loc_180072ECC
0x180072e85  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072e8c  nop     dword ptr [rax+rax+00h]
0x180072e91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072e98  mov     rcx, rax
0x180072e9b  test    rax, rax
0x180072e9e  jz      short loc_180072EBE
0x180072ea0  mov     rax, [rax]
0x180072ea3  mov     edx, 7F0h
0x180072ea8  mov     rax, [rax+8]
0x180072eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072eb1  test    eax, eax
0x180072eb3  jz      short loc_180072EBE
0x180072eb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072ebc  jmp     short loc_180072ECC
0x180072ebe  lea     rcx, qword_1800DBF70; this
0x180072ec5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072ecc  cmp     byte ptr [rcx+8], 0
0x180072ed0  jz      short loc_180072EF3
0x180072ed2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180072ed7  cmp     [rax+7CCh], ebx
0x180072edd  jz      short loc_180072EF3
0x180072edf  mov     r9d, ebx; int
0x180072ee2  mov     r8d, 7Fh; int
0x180072ee8  mov     rdx, r12; char *
0x180072eeb  mov     rcx, rax; this
0x180072eee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072ef3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072efa  jb      loc_180072FF1
0x180072f00  mov     edx, 0Fh
0x180072f05  jmp     loc_180072FD3
0x180072f0a  movups  xmm0, cs:MF_MD_FSDKMULTI
0x180072f11  lea     rax, [rsp+88h+var_58]
0x180072f16  mov     r8, rsi; struct tagPROPVARIANT *
0x180072f19  movups  xmm1, cs:MF_MD_FSDKTYPE
0x180072f20  lea     r9, [rsp+88h+var_48]; struct _GUID
0x180072f25  mov     [rsp+88h+var_68], rax; struct _GUID
0x180072f2a  mov     rdx, r14; struct tagPROPVARIANT *
0x180072f2d  mov     rcx, rdi; this
0x180072f30  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x180072f36  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x180072f3c  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x180072f41  mov     ebx, eax
0x180072f43  test    eax, eax
0x180072f45  jns     loc_180072FF1
0x180072f4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072f52  test    rcx, rcx
0x180072f55  jnz     short loc_180072F9E
0x180072f57  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072f5e  nop     dword ptr [rax+rax+00h]
0x180072f63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072f6a  mov     rcx, rax
0x180072f6d  test    rax, rax
0x180072f70  jz      short loc_180072F90
0x180072f72  mov     rax, [rax]
0x180072f75  mov     edx, 7F0h
0x180072f7a  mov     rax, [rax+8]
0x180072f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072f83  test    eax, eax
0x180072f85  jz      short loc_180072F90
0x180072f87  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
