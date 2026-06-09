# CWMProperty::SetShellValue(tagPROPVARIANT const &)

- ea: `0x18006fa60`
- end: `0x18006ffa5`
- name: `?SetShellValue@CWMProperty@@UEAAJAEBUtagPROPVARIANT@@@Z`
- size: `1349`
- prototype: `int(CWMProperty *__hidden this, const struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006f320`
- `0x18006ffb0`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18005d6f4`
- `0x18006fa60`
- `0x18007064c`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006fbd7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006fe0d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006fbd7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18006fe0d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006fa97`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006fb36`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006fa97`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18006fb36`
- `PROPSYS!StgSerializePropVariant` at `0x18006fc9c`
- `PROPSYS!StgSerializePropVariant` at `0x18006fc9c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fab3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fb52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fbf3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fcb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fd76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fe29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fef5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fab3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fb52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fbf3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fcb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fd76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fe29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006fef5`

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
                v27 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                    v40 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                    v46 = &qword_1800D6F70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v34 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v21 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18006fa60  mov     rax, rsp
0x18006fa63  push    rbx
0x18006fa64  push    rbp
0x18006fa65  push    rsi
0x18006fa66  push    rdi
0x18006fa67  push    r12
0x18006fa69  push    r14
0x18006fa6b  sub     rsp, 58h
0x18006fa6f  mov     rbp, rdx
0x18006fa72  lea     r12, aCwmpropertySet_0; "CWMProperty::SetShellValue"
0x18006fa79  mov     rdi, rcx
0x18006fa7c  mov     esi, 59h ; 'Y'
0x18006fa81  mov     r8d, esi; int
0x18006fa84  lea     rcx, [rax+8]; this
0x18006fa88  mov     rdx, r12; char *
0x18006fa8b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006fa90  lea     r14, [rdi+60h]
0x18006fa94  mov     rcx, r14; pvar
0x18006fa97  call    cs:__imp_PropVariantClear
0x18006fa9d  mov     ebx, eax
0x18006fa9f  test    eax, eax
0x18006faa1  jns     loc_18006FB2F
0x18006faa7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006faae  test    rcx, rcx
0x18006fab1  jnz     short loc_18006FAF4
0x18006fab3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006fab9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fac0  mov     rcx, rax
0x18006fac3  test    rax, rax
0x18006fac6  jz      short loc_18006FAE6
0x18006fac8  mov     rax, [rax]
0x18006facb  mov     edx, 7F0h
0x18006fad0  mov     rax, [rax+8]
0x18006fad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fad9  test    eax, eax
0x18006fadb  jz      short loc_18006FAE6
0x18006fadd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fae4  jmp     short loc_18006FAF4
0x18006fae6  lea     rcx, qword_1800D6F70; this
0x18006faed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006faf4  cmp     byte ptr [rcx+8], 0
0x18006faf8  jz      short loc_18006FB18
0x18006fafa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006faff  cmp     [rax+7CCh], ebx
0x18006fb05  jz      short loc_18006FB18
0x18006fb07  mov     r9d, ebx; int
0x18006fb0a  mov     r8d, esi; int
0x18006fb0d  mov     rdx, r12; char *
0x18006fb10  mov     rcx, rax; this
0x18006fb13  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006fb18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fb1f  jb      loc_18006FF89
0x18006fb25  mov     edx, 0Ah
0x18006fb2a  jmp     loc_18006FF6B
0x18006fb2f  lea     rsi, [rdi+78h]
0x18006fb33  mov     rcx, rsi; pvar
0x18006fb36  call    cs:__imp_PropVariantClear
0x18006fb3c  mov     ebx, eax
0x18006fb3e  test    eax, eax
0x18006fb40  jns     loc_18006FBD1
0x18006fb46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fb4d  test    rcx, rcx
0x18006fb50  jnz     short loc_18006FB93
0x18006fb52  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006fb58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fb5f  mov     rcx, rax
0x18006fb62  test    rax, rax
0x18006fb65  jz      short loc_18006FB85
0x18006fb67  mov     rax, [rax]
0x18006fb6a  mov     edx, 7F0h
0x18006fb6f  mov     rax, [rax+8]
0x18006fb73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb78  test    eax, eax
0x18006fb7a  jz      short loc_18006FB85
0x18006fb7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fb83  jmp     short loc_18006FB93
0x18006fb85  lea     rcx, qword_1800D6F70; this
0x18006fb8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fb93  cmp     byte ptr [rcx+8], 0
0x18006fb97  jz      short loc_18006FBBA
0x18006fb99  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006fb9e  cmp     [rax+7CCh], ebx
0x18006fba4  jz      short loc_18006FBBA
0x18006fba6  mov     r9d, ebx; int
0x18006fba9  mov     r8d, 5Ah ; 'Z'; int
0x18006fbaf  mov     rdx, r12; char *
0x18006fbb2  mov     rcx, rax; this
0x18006fbb5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006fbba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fbc1  jb      loc_18006FF89
0x18006fbc7  mov     edx, 0Bh
0x18006fbcc  jmp     loc_18006FF6B
0x18006fbd1  mov     rdx, rbp; pvarSrc
0x18006fbd4  mov     rcx, r14; pvarDest
0x18006fbd7  call    cs:__imp_PropVariantCopy
0x18006fbdd  mov     ebx, eax
0x18006fbdf  test    eax, eax
0x18006fbe1  jns     loc_18006FC72
0x18006fbe7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fbee  test    rcx, rcx
0x18006fbf1  jnz     short loc_18006FC34
0x18006fbf3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006fbf9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fc00  mov     rcx, rax
0x18006fc03  test    rax, rax
0x18006fc06  jz      short loc_18006FC26
0x18006fc08  mov     rax, [rax]
0x18006fc0b  mov     edx, 7F0h
0x18006fc10  mov     rax, [rax+8]
0x18006fc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc19  test    eax, eax
0x18006fc1b  jz      short loc_18006FC26
0x18006fc1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fc24  jmp     short loc_18006FC34
0x18006fc26  lea     rcx, qword_1800D6F70; this
0x18006fc2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fc34  cmp     byte ptr [rcx+8], 0
0x18006fc38  jz      short loc_18006FC5B
0x18006fc3a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006fc3f  cmp     [rax+7CCh], ebx
0x18006fc45  jz      short loc_18006FC5B
0x18006fc47  mov     r9d, ebx; int
0x18006fc4a  mov     r8d, 5Ch ; '\'; int
0x18006fc50  mov     rdx, r12; char *
0x18006fc53  mov     rcx, rax; this
0x18006fc56  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006fc5b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fc62  jb      loc_18006FF89
0x18006fc68  mov     edx, 0Ch
0x18006fc6d  jmp     loc_18006FF6B
0x18006fc72  xor     r8d, r8d
0x18006fc75  lea     rdx, MF_MD_EXTENDEDPROP
0x18006fc7c  mov     rcx, rdi
0x18006fc7f  call    MFGetAttributeUINT32
0x18006fc84  test    eax, eax
0x18006fc86  jz      loc_18006FD37
0x18006fc8c  lea     r8, [rsi+8]; pcb
0x18006fc90  mov     word ptr [rsi], 41h ; 'A'
0x18006fc95  lea     rdx, [r8+8]; ppProp
0x18006fc99  mov     rcx, rbp; ppropvar
0x18006fc9c  call    cs:__imp_StgSerializePropVariant
0x18006fca2  mov     ebx, eax
0x18006fca4  test    eax, eax
0x18006fca6  jns     loc_18006FF89
0x18006fcac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fcb3  test    rcx, rcx
0x18006fcb6  jnz     short loc_18006FCF9
0x18006fcb8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006fcbe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fcc5  mov     rcx, rax
0x18006fcc8  test    rax, rax
0x18006fccb  jz      short loc_18006FCEB
0x18006fccd  mov     rax, [rax]
0x18006fcd0  mov     edx, 7F0h
0x18006fcd5  mov     rax, [rax+8]
0x18006fcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fcde  test    eax, eax
0x18006fce0  jz      short loc_18006FCEB
0x18006fce2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fce9  jmp     short loc_18006FCF9
0x18006fceb  lea     rcx, qword_1800D6F70; this
0x18006fcf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fcf9  cmp     byte ptr [rcx+8], 0
0x18006fcfd  jz      short loc_18006FD20
0x18006fcff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006fd04  cmp     [rax+7CCh], ebx
0x18006fd0a  jz      short loc_18006FD20
0x18006fd0c  mov     r9d, ebx; int
0x18006fd0f  mov     r8d, 6Ch ; 'l'; int
0x18006fd15  mov     rdx, r12; char *
0x18006fd18  mov     rcx, rax; this
0x18006fd1b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006fd20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fd27  jb      loc_18006FF89
0x18006fd2d  mov     edx, 0Dh
0x18006fd32  jmp     loc_18006FF6B
0x18006fd37  mov     rax, [rdi]
0x18006fd3a  lea     r8, [rsp+88h+arg_0]
0x18006fd42  lea     rdx, MF_MD_FSDKTYPE
0x18006fd49  mov     [rsp+88h+arg_0], 0
0x18006fd54  mov     rcx, rdi
0x18006fd57  mov     rax, [rax+38h]
0x18006fd5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd60  mov     ebx, eax
0x18006fd62  test    eax, eax
0x18006fd64  jns     loc_18006FDF5
0x18006fd6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fd71  test    rcx, rcx
0x18006fd74  jnz     short loc_18006FDB7
0x18006fd76  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006fd7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fd83  mov     rcx, rax
0x18006fd86  test    rax, rax
0x18006fd89  jz      short loc_18006FDA9
0x18006fd8b  mov     rax, [rax]
0x18006fd8e  mov     edx, 7F0h
0x18006fd93  mov     rax, [rax+8]
0x18006fd97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd9c  test    eax, eax
0x18006fd9e  jz      short loc_18006FDA9
0x18006fda0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fda7  jmp     short loc_18006FDB7
0x18006fda9  lea     rcx, qword_1800D6F70; this
0x18006fdb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fdb7  cmp     byte ptr [rcx+8], 0
0x18006fdbb  jz      short loc_18006FDDE
0x18006fdbd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006fdc2  cmp     [rax+7CCh], ebx
0x18006fdc8  jz      short loc_18006FDDE
0x18006fdca  mov     r9d, ebx; int
0x18006fdcd  mov     r8d, 78h ; 'x'; int
0x18006fdd3  mov     rdx, r12; char *
0x18006fdd6  mov     rcx, rax; this
0x18006fdd9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006fdde  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fde5  jb      loc_18006FF89
0x18006fdeb  mov     edx, 0Eh
0x18006fdf0  jmp     loc_18006FF6B
0x18006fdf5  movzx   eax, word ptr [rsp+88h+arg_0]
0x18006fdfd  cmp     [rbp+0], ax
0x18006fe01  jnz     loc_18006FEA8
0x18006fe07  mov     rdx, rbp; pvarSrc
0x18006fe0a  mov     rcx, rsi; pvarDest
0x18006fe0d  call    cs:__imp_PropVariantCopy
0x18006fe13  mov     ebx, eax
0x18006fe15  test    eax, eax
0x18006fe17  jns     loc_18006FF89
0x18006fe1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fe24  test    rcx, rcx
0x18006fe27  jnz     short loc_18006FE6A
0x18006fe29  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006fe2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fe36  mov     rcx, rax
0x18006fe39  test    rax, rax
0x18006fe3c  jz      short loc_18006FE5C
0x18006fe3e  mov     rax, [rax]
0x18006fe41  mov     edx, 7F0h
0x18006fe46  mov     rax, [rax+8]
0x18006fe4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe4f  test    eax, eax
0x18006fe51  jz      short loc_18006FE5C
0x18006fe53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fe5a  jmp     short loc_18006FE6A
0x18006fe5c  lea     rcx, qword_1800D6F70; this
0x18006fe63  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fe6a  cmp     byte ptr [rcx+8], 0
0x18006fe6e  jz      short loc_18006FE91
0x18006fe70  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006fe75  cmp     [rax+7CCh], ebx
0x18006fe7b  jz      short loc_18006FE91
0x18006fe7d  mov     r9d, ebx; int
0x18006fe80  mov     r8d, 7Fh; int
0x18006fe86  mov     rdx, r12; char *
0x18006fe89  mov     rcx, rax; this
0x18006fe8c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006fe91  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006fe98  jb      loc_18006FF89
0x18006fe9e  mov     edx, 0Fh
0x18006fea3  jmp     loc_18006FF6B
0x18006fea8  movups  xmm0, cs:MF_MD_FSDKMULTI
0x18006feaf  lea     rax, [rsp+88h+var_58]
0x18006feb4  mov     r8, rsi; struct tagPROPVARIANT *
0x18006feb7  movups  xmm1, cs:MF_MD_FSDKTYPE
0x18006febe  lea     r9, [rsp+88h+var_48]; struct _GUID
0x18006fec3  mov     [rsp+88h+var_68], rax; struct _GUID
0x18006fec8  mov     rdx, r14; struct tagPROPVARIANT *
0x18006fecb  mov     rcx, rdi; this
0x18006fece  movdqu  xmmword ptr [rsp+88h+var_58.Data1], xmm0
0x18006fed4  movdqu  xmmword ptr [rsp+88h+var_48.Data1], xmm1
0x18006feda  call    ?TranslateValue@CWMProperty@@IEAAJAEBUtagPROPVARIANT@@PEAU2@U_GUID@@2@Z; CWMProperty::TranslateValue(tagPROPVARIANT const &,tagPROPVARIANT *,_GUID,_GUID)
0x18006fedf  mov     ebx, eax
0x18006fee1  test    eax, eax
0x18006fee3  jns     loc_18006FF89
0x18006fee9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006fef0  test    rcx, rcx
0x18006fef3  jnz     short loc_18006FF36
0x18006fef5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006fefb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ff02  mov     rcx, rax
0x18006ff05  test    rax, rax
0x18006ff08  jz      short loc_18006FF28
0x18006ff0a  mov     rax, [rax]
0x18006ff0d  mov     edx, 7F0h
0x18006ff12  mov     rax, [rax+8]
0x18006ff16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ff1b  test    eax, eax
0x18006ff1d  jz      short loc_18006FF28
0x18006ff1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ff26  jmp     short loc_18006FF36
0x18006ff28  lea     rcx, qword_1800D6F70; this
0x18006ff2f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006ff36  cmp     byte ptr [rcx+8], 0
0x18006ff3a  jz      short loc_18006FF5D
0x18006ff3c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006ff41  cmp     [rax+7CCh], ebx
0x18006ff47  jz      short loc_18006FF5D
0x18006ff49  mov     r9d, ebx; int
0x18006ff4c  mov     r8d, 83h; int
0x18006ff52  mov     rdx, r12; char *
0x18006ff55  mov     rcx, rax; this
  ... truncated ...
```
