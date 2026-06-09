# CMFPropHandlerBase::InternalGetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18003d820`
- end: `0x18003da70`
- name: `?InternalGetValue@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `592`
- prototype: `int(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002cac0`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002b460`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003d820`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18003d8b5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18003d8b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d8d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d9b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d8d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d9b1`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::InternalGetValue(
        CMFPropHandlerBase *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  HRESULT v8; // ebx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  _BYTE v18[4]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-3Ch] BYREF
  const PROPVARIANT *v20; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v21[16]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v22; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+60h] [rbp-10h]

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v18, "CMFPropHandlerBase::InternalGetValue", 735);
  v20 = 0;
  v23 = 0;
  v6 = *(_QWORD *)this;
  v19 = 0;
  v22 = 0;
  (*(void (__fastcall **)(CMFPropHandlerBase *, const struct _tagpropertykey *, __int128 *))(v6 + 96))(this, a2, &v22);
  if ( (unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Find((char *)this + 48, &v22, &v20, v21) )
  {
    v8 = PropVariantCopy(a3, v20 + 4);
    if ( v8 < 0 )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::InternalGetValue", 747, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 59;
LABEL_26:
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v8);
      }
    }
  }
  else if ( (*(int (__fastcall **)(CMFPropHandlerBase *, __int128 *, struct tagPROPVARIANT *, unsigned int *))(*(_QWORD *)this + 104LL))(
              this,
              &v22,
              a3,
              &v19) >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(CMFPropHandlerBase *, __int128 *, struct tagPROPVARIANT *, _QWORD, _DWORD))(*(_QWORD *)this + 40LL))(
           this,
           &v22,
           a3,
           v19,
           0);
    if ( v8 < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != v8 )
          CallStackContext::TraceFailure(v16, "CMFPropHandlerBase::InternalGetValue", 762, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 60;
        goto LABEL_26;
      }
    }
  }
  else
  {
    v8 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003d820  mov     [rsp-18h+arg_18], rbx
0x18003d825  push    rbp
0x18003d826  push    rsi
0x18003d827  push    rdi
0x18003d828  mov     rbp, rsp
0x18003d82b  sub     rsp, 70h
0x18003d82f  mov     rax, cs:__security_cookie
0x18003d836  xor     rax, rsp
0x18003d839  mov     [rbp+var_8], rax
0x18003d83d  mov     rsi, r8
0x18003d840  mov     rbx, rdx
0x18003d843  mov     rdi, rcx
0x18003d846  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x18003d84d  mov     r8d, 2DFh; int
0x18003d853  lea     rcx, [rbp+var_40]; this
0x18003d857  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003d85c  xor     eax, eax
0x18003d85e  mov     [rbp+var_38], 0
0x18003d866  mov     [rbp+var_10], eax
0x18003d869  lea     r8, [rbp+var_20]
0x18003d86d  mov     rax, [rdi]
0x18003d870  xorps   xmm0, xmm0
0x18003d873  mov     rdx, rbx
0x18003d876  mov     [rbp+var_3C], 0
0x18003d87d  mov     rcx, rdi
0x18003d880  movups  [rbp+var_20], xmm0
0x18003d884  mov     rax, [rax+60h]
0x18003d888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d88d  lea     rcx, [rdi+30h]
0x18003d891  lea     r9, [rbp+var_30]
0x18003d895  lea     r8, [rbp+var_38]
0x18003d899  lea     rdx, [rbp+var_20]
0x18003d89d  call    ?Find@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Find(_tagpropertykey const &,CMFProperty * &,CTBucketHash<_tagpropertykey,CMFProperty *>::_POSITION &)
0x18003d8a2  test    eax, eax
0x18003d8a4  jz      loc_18003D954
0x18003d8aa  mov     rdx, [rbp+var_38]
0x18003d8ae  mov     rcx, rsi; pvarDest
0x18003d8b1  add     rdx, 60h ; '`'; pvarSrc
0x18003d8b5  call    cs:__imp_PropVariantCopy
0x18003d8bb  mov     ebx, eax
0x18003d8bd  test    eax, eax
0x18003d8bf  jns     loc_18003DA49
0x18003d8c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d8cc  test    rcx, rcx
0x18003d8cf  jnz     short loc_18003D912
0x18003d8d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d8d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d8de  mov     rcx, rax
0x18003d8e1  test    rax, rax
0x18003d8e4  jz      short loc_18003D904
0x18003d8e6  mov     rax, [rax]
0x18003d8e9  mov     edx, 7F0h
0x18003d8ee  mov     rax, [rax+8]
0x18003d8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8f7  test    eax, eax
0x18003d8f9  jz      short loc_18003D904
0x18003d8fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d902  jmp     short loc_18003D912
0x18003d904  lea     rcx, qword_18006EB20; this
0x18003d90b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d912  cmp     byte ptr [rcx+8], 0
0x18003d916  jz      short loc_18003D93D
0x18003d918  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d91d  cmp     [rax+7CCh], ebx
0x18003d923  jz      short loc_18003D93D
0x18003d925  mov     r9d, ebx; int
0x18003d928  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x18003d92f  mov     r8d, 2EBh; int
0x18003d935  mov     rcx, rax; this
0x18003d938  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d93d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003d942  cmp     al, 1
0x18003d944  jb      loc_18003DA49
0x18003d94a  mov     edx, 3Bh ; ';'
0x18003d94f  jmp     loc_18003DA2B
0x18003d954  mov     rax, [rdi]
0x18003d957  lea     r9, [rbp+var_3C]
0x18003d95b  mov     r8, rsi
0x18003d95e  lea     rdx, [rbp+var_20]
0x18003d962  mov     rcx, rdi
0x18003d965  mov     rax, [rax+68h]
0x18003d969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d96e  test    eax, eax
0x18003d970  jns     short loc_18003D979
0x18003d972  xor     ebx, ebx
0x18003d974  jmp     loc_18003DA49
0x18003d979  mov     rax, [rdi]
0x18003d97c  lea     rdx, [rbp+var_20]
0x18003d980  mov     r9d, [rbp+var_3C]
0x18003d984  mov     r8, rsi
0x18003d987  mov     rcx, rdi
0x18003d98a  mov     [rsp+70h+var_50], 0
0x18003d992  mov     rax, [rax+28h]
0x18003d996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d99b  mov     ebx, eax
0x18003d99d  test    eax, eax
0x18003d99f  jns     loc_18003DA49
0x18003d9a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9ac  test    rcx, rcx
0x18003d9af  jnz     short loc_18003D9F2
0x18003d9b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d9b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9be  mov     rcx, rax
0x18003d9c1  test    rax, rax
0x18003d9c4  jz      short loc_18003D9E4
0x18003d9c6  mov     rax, [rax]
0x18003d9c9  mov     edx, 7F0h
0x18003d9ce  mov     rax, [rax+8]
0x18003d9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9d7  test    eax, eax
0x18003d9d9  jz      short loc_18003D9E4
0x18003d9db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9e2  jmp     short loc_18003D9F2
0x18003d9e4  lea     rcx, qword_18006EB20; this
0x18003d9eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d9f2  cmp     byte ptr [rcx+8], 0
0x18003d9f6  jz      short loc_18003DA1D
0x18003d9f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d9fd  cmp     [rax+7CCh], ebx
0x18003da03  jz      short loc_18003DA1D
0x18003da05  mov     r9d, ebx; int
0x18003da08  lea     rdx, aCmfprophandler_18; "CMFPropHandlerBase::InternalGetValue"
0x18003da0f  mov     r8d, 2FAh; int
0x18003da15  mov     rcx, rax; this
0x18003da18  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003da1d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003da22  cmp     al, 1
0x18003da24  jb      short loc_18003DA49
0x18003da26  mov     edx, 3Ch ; '<'
0x18003da2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003da32  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003da39  mov     r9, rdi
0x18003da3c  mov     [rsp+70h+var_50], ebx
0x18003da40  mov     rcx, [rcx+10h]
0x18003da44  call    WPP_SF_qd
0x18003da49  lea     rcx, [rbp+var_40]; this
0x18003da4d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003da52  mov     eax, ebx
0x18003da54  mov     rcx, [rbp+var_8]
0x18003da58  xor     rcx, rsp; StackCookie
0x18003da5b  call    __security_check_cookie
0x18003da60  mov     rbx, [rsp+70h+arg_18]
0x18003da68  add     rsp, 70h
0x18003da6c  pop     rdi
0x18003da6d  pop     rsi
0x18003da6e  pop     rbp
0x18003da6f  retn
```
