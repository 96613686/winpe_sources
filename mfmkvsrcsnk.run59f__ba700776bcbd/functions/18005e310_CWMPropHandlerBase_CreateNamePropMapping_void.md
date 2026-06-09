# CWMPropHandlerBase::CreateNamePropMapping(void)

- ea: `0x18005e310`
- end: `0x18005e61b`
- name: `?CreateNamePropMapping@CWMPropHandlerBase@@MEAAJXZ`
- size: `779`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting`

## callees

- `0x180001fb0`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18004ed70`
- `0x180053c24`
- `0x18005404c`
- `0x1800540bc`
- `0x180056aac`
- `0x180056f7c`
- `0x18005e310`
- `0x18005f188`
- `0x18005f2b4`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e54a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005e54a`

## string_xrefs

- `0x18005e32a`: `CWMPropHandlerBase::CreateNamePropMapping`
- `0x18005e5a7`: `CWMPropHandlerBase::CreateNamePropMapping`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::CreateNamePropMapping(CWMPropHandlerBase *this)
{
  int v2; // edi
  char v3; // cl
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 i; // rsi
  CMFProperty *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  CMFProperty *v11; // rax
  CMFProperty *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v20[32]; // [rsp+30h] [rbp-48h] BYREF
  CMFProperty *v21; // [rsp+80h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v21,
    "CWMPropHandlerBase::CreateNamePropMapping",
    766);
  v2 = 0;
  v3 = 0;
  v4 = 124;
  do
  {
    ++v3;
    v4 >>= 1;
  }
  while ( v4 );
  v5 = 1 << v3;
  CTBucketHash<CMFBaseStringT<unsigned short>,CMFProperty *>::Initialize((char *)this + 928, (unsigned int)(1 << v3));
  CTBucketHash<_tagpropertykey,CMFProperty *>::Initialize((char *)this + 1304, v5);
  for ( i = 0; (unsigned int)i < 0x7C; i = (unsigned int)(i + 1) )
  {
    CMFBaseStringT<unsigned short>::CMFBaseStringT<unsigned short>(v20, *((_QWORD *)&krgPKeyWMMap + 5 * i + 2));
    v7 = (CMFProperty *)operator new(0x78u);
    if ( !v7
      || (v11 = CMFProperty::CMFProperty(v7, *((const struct _tagpropertykey **)&krgPKeyWMMap + 5 * i)),
          v21 = v11,
          (v12 = v11) == 0) )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      v2 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CWMPropHandlerBase::CreateNamePropMapping",
            795,
            -2147024882);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
          this,
          -2147024882);
      CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(v20);
      break;
    }
    (*(void (__fastcall **)(CMFProperty *, __int128 *, _QWORD))(*(_QWORD *)v11 + 168LL))(
      v11,
      &MF_MD_SHELLMULTI,
      *((unsigned __int8 *)&krgPKeyWMMap + 40 * i + 10));
    (*(void (__fastcall **)(CMFProperty *, __int128 *, _QWORD))(*(_QWORD *)v12 + 168LL))(
      v12,
      &MF_MD_FSDKMULTI,
      *((unsigned __int8 *)&krgPKeyWMMap + 40 * i + 26));
    (*(void (__fastcall **)(CMFProperty *, __int128 *, _QWORD))(*(_QWORD *)v12 + 168LL))(
      v12,
      &MF_MD_SHELLTYPE,
      *((unsigned __int16 *)&krgPKeyWMMap + 20 * i + 4));
    (*(void (__fastcall **)(CMFProperty *, __int128 *, _QWORD))(*(_QWORD *)v12 + 168LL))(
      v12,
      &MF_MD_FSDKTYPE,
      *((unsigned __int16 *)&krgPKeyWMMap + 20 * i + 12));
    (*(void (__fastcall **)(CMFProperty *, void *, _QWORD))(*(_QWORD *)v12 + 168LL))(
      v12,
      &MF_MD_ACCESSTYPE,
      *((unsigned int *)&krgPKeyWMMap + 10 * i + 7));
    (*(void (__fastcall **)(CMFProperty *, void *, _QWORD))(*(_QWORD *)v12 + 168LL))(
      v12,
      &MF_MD_PKEY_EXCEPTIONAL,
      *((unsigned __int8 *)&krgPKeyWMMap + 40 * i + 32));
    v13 = *((_QWORD *)&krgPKeyWMMap + 5 * i);
    *(_OWORD *)((char *)v12 + 76) = *(_OWORD *)v13;
    *((_DWORD *)v12 + 23) = *(_DWORD *)(v13 + 16);
    v14 = CMFBaseStringT<unsigned short>::PContents(v20, *(_QWORD *)v12);
    (*(void (__fastcall **)(CMFProperty *, void *, __int64))(v15 + 200))(v12, &MF_MD_NAME, v14);
    v2 = CTBucketHash<CMFBaseStringT<unsigned short>,CMFProperty *>::Insert((char *)this + 928, v20, &v21);
    if ( v2 >= 0 )
    {
      (*(void (__fastcall **)(CMFProperty *))(*(_QWORD *)v12 + 8LL))(v12);
      v2 = CTBucketHash<_tagpropertykey,CMFProperty *>::Insert((char *)this + 1304, (char *)v12 + 76, &v21);
      if ( v2 >= 0 )
        (*(void (__fastcall **)(CMFProperty *))(*(_QWORD *)v12 + 8LL))(v12);
    }
    (*(void (__fastcall **)(CMFProperty *))(*(_QWORD *)v12 + 16LL))(v12);
    CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(v20);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005e310  mov     rax, rsp
0x18005e313  mov     [rax+10h], rbx
0x18005e317  mov     [rax+18h], rbp
0x18005e31b  push    rsi
0x18005e31c  push    rdi
0x18005e31d  push    r13
0x18005e31f  push    r14
0x18005e321  push    r15
0x18005e323  sub     rsp, 50h
0x18005e327  mov     rbp, rcx
0x18005e32a  lea     rdx, aCwmprophandler_1; "CWMPropHandlerBase::CreateNamePropMappi"...
0x18005e331  lea     rcx, [rax+8]; this
0x18005e335  mov     r8d, 2FEh; int
0x18005e33b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005e340  xor     edi, edi
0x18005e342  xor     ecx, ecx
0x18005e344  lea     eax, [rdi+7Ch]
0x18005e347  inc     ecx
0x18005e349  shr     eax, 1
0x18005e34b  jnz     short loc_18005E347
0x18005e34d  mov     ebx, 1
0x18005e352  lea     r15, [rbp+3A0h]
0x18005e359  shl     ebx, cl
0x18005e35b  mov     rcx, r15
0x18005e35e  mov     edx, ebx
0x18005e360  call    ?Initialize@?$CTBucketHash@V?$CMFBaseStringT@G@@PEAVCMFProperty@@@@QEAAJKK@Z; CTBucketHash<CMFBaseStringT<ushort>,CMFProperty *>::Initialize(ulong,ulong)
0x18005e365  lea     r14, [rbp+518h]
0x18005e36c  mov     edx, ebx
0x18005e36e  mov     rcx, r14
0x18005e371  call    ?Initialize@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAJKK@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Initialize(ulong,ulong)
0x18005e376  xor     esi, esi
0x18005e378  lea     r13, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x18005e37f  cmp     esi, 7Ch ; '|'
0x18005e382  jnb     loc_18005E5F2
0x18005e388  lea     rdi, [rsi+rsi*4]
0x18005e38c  mov     rdx, [r13+rdi*8+10h]
0x18005e391  lea     rcx, [rsp+78h+var_48]
0x18005e396  call    ??0?$CMFBaseStringT@G@@QEAA@PEBGJ@Z; CMFBaseStringT<ushort>::CMFBaseStringT<ushort>(ushort const *,long)
0x18005e39b  mov     ecx, 78h ; 'x'; Size
0x18005e3a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005e3a5  test    rax, rax
0x18005e3a8  jz      loc_18005E539
0x18005e3ae  mov     rdx, [r13+rdi*8+0]; struct _tagpropertykey *
0x18005e3b3  mov     rcx, rax; this
0x18005e3b6  call    ??0CMFProperty@@QEAA@AEBU_tagpropertykey@@@Z; CMFProperty::CMFProperty(_tagpropertykey const &)
0x18005e3bb  mov     [rsp+78h+arg_0], rax
0x18005e3c3  mov     rbx, rax
0x18005e3c6  test    rax, rax
0x18005e3c9  jz      loc_18005E539
0x18005e3cf  mov     rax, [rax]
0x18005e3d2  lea     rdx, MF_MD_SHELLMULTI
0x18005e3d9  movzx   r8d, byte ptr [r13+rdi*8+0Ah]
0x18005e3df  mov     rcx, rbx
0x18005e3e2  mov     rax, [rax+0A8h]
0x18005e3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3ee  mov     rax, [rbx]
0x18005e3f1  lea     rdx, MF_MD_FSDKMULTI
0x18005e3f8  movzx   r8d, byte ptr [r13+rdi*8+1Ah]
0x18005e3fe  mov     rcx, rbx
0x18005e401  mov     rax, [rax+0A8h]
0x18005e408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e40d  mov     rax, [rbx]
0x18005e410  lea     rdx, MF_MD_SHELLTYPE
0x18005e417  movzx   r8d, word ptr [r13+rdi*8+8]
0x18005e41d  mov     rcx, rbx
0x18005e420  mov     rax, [rax+0A8h]
0x18005e427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e42c  mov     rax, [rbx]
0x18005e42f  lea     rdx, MF_MD_FSDKTYPE
0x18005e436  movzx   r8d, word ptr [r13+rdi*8+18h]
0x18005e43c  mov     rcx, rbx
0x18005e43f  mov     rax, [rax+0A8h]
0x18005e446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e44b  mov     rax, [rbx]
0x18005e44e  lea     rdx, MF_MD_ACCESSTYPE
0x18005e455  mov     r8d, [r13+rdi*8+1Ch]
0x18005e45a  mov     rcx, rbx
0x18005e45d  mov     rax, [rax+0A8h]
0x18005e464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e469  mov     rax, [rbx]
0x18005e46c  lea     rdx, MF_MD_PKEY_EXCEPTIONAL
0x18005e473  movzx   r8d, byte ptr [r13+rdi*8+20h]
0x18005e479  mov     rcx, rbx
0x18005e47c  mov     rax, [rax+0A8h]
0x18005e483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e488  lea     rax, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x18005e48f  mov     rax, [rax+rdi*8]
0x18005e493  lea     rcx, [rsp+78h+var_48]
0x18005e498  movups  xmm0, xmmword ptr [rax]
0x18005e49b  movups  xmmword ptr [rbx+4Ch], xmm0
0x18005e49f  mov     eax, [rax+10h]
0x18005e4a2  mov     [rbx+5Ch], eax
0x18005e4a5  mov     rdx, [rbx]
0x18005e4a8  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18005e4ad  mov     r8, rax
0x18005e4b0  mov     rcx, rbx
0x18005e4b3  mov     rax, [rdx+0C8h]
0x18005e4ba  lea     rdx, MF_MD_NAME
0x18005e4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4c6  lea     r8, [rsp+78h+arg_0]
0x18005e4ce  mov     rcx, r15
0x18005e4d1  lea     rdx, [rsp+78h+var_48]
0x18005e4d6  call    ?Insert@?$CTBucketHash@V?$CMFBaseStringT@G@@PEAVCMFProperty@@@@QEAAJAEBV?$CMFBaseStringT@G@@AEBQEAVCMFProperty@@@Z; CTBucketHash<CMFBaseStringT<ushort>,CMFProperty *>::Insert(CMFBaseStringT<ushort> const &,CMFProperty * const &)
0x18005e4db  mov     edi, eax
0x18005e4dd  test    eax, eax
0x18005e4df  js      short loc_18005E519
0x18005e4e1  mov     rax, [rbx]
0x18005e4e4  mov     rcx, rbx
0x18005e4e7  mov     rax, [rax+8]
0x18005e4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4f0  lea     r8, [rsp+78h+arg_0]
0x18005e4f8  mov     rcx, r14
0x18005e4fb  lea     rdx, [rbx+4Ch]
0x18005e4ff  call    ?Insert@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAJAEBU_tagpropertykey@@AEBQEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Insert(_tagpropertykey const &,CMFProperty * const &)
0x18005e504  mov     edi, eax
0x18005e506  test    eax, eax
0x18005e508  js      short loc_18005E519
0x18005e50a  mov     rax, [rbx]
0x18005e50d  mov     rcx, rbx
0x18005e510  mov     rax, [rax+8]
0x18005e514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e519  mov     rax, [rbx]
0x18005e51c  mov     rcx, rbx
0x18005e51f  mov     rax, [rax+10h]
0x18005e523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e528  lea     rcx, [rsp+78h+var_48]
0x18005e52d  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18005e532  inc     esi
0x18005e534  jmp     loc_18005E378
0x18005e539  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e540  mov     edi, 8007000Eh
0x18005e545  test    rcx, rcx
0x18005e548  jnz     short loc_18005E591
0x18005e54a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005e551  nop     dword ptr [rax+rax+00h]
0x18005e556  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e55d  mov     rcx, rax
0x18005e560  test    rax, rax
0x18005e563  jz      short loc_18005E583
0x18005e565  mov     rax, [rax]
0x18005e568  mov     edx, 7F0h
0x18005e56d  mov     rax, [rax+8]
0x18005e571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e576  test    eax, eax
0x18005e578  jz      short loc_18005E583
0x18005e57a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e581  jmp     short loc_18005E591
0x18005e583  lea     rcx, qword_1800DBF70; this
0x18005e58a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005e591  cmp     byte ptr [rcx+8], 0
0x18005e595  jz      short loc_18005E5BC
0x18005e597  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005e59c  cmp     [rax+7CCh], edi
0x18005e5a2  jz      short loc_18005E5BC
0x18005e5a4  mov     r9d, edi; int
0x18005e5a7  lea     rdx, aCwmprophandler_1; "CWMPropHandlerBase::CreateNamePropMappi"...
0x18005e5ae  mov     r8d, 31Bh; int
0x18005e5b4  mov     rcx, rax; this
0x18005e5b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005e5bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005e5c3  jb      short loc_18005E5E8
0x18005e5c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e5cc  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005e5d3  mov     edx, 45h ; 'E'
0x18005e5d8  mov     [rsp+78h+var_58], edi
0x18005e5dc  mov     r9, rbp
0x18005e5df  mov     rcx, [rcx+10h]
0x18005e5e3  call    WPP_SF_qD
0x18005e5e8  lea     rcx, [rsp+78h+var_48]
0x18005e5ed  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18005e5f2  lea     rcx, [rsp+78h+arg_0]; this
0x18005e5fa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005e5ff  lea     r11, [rsp+78h+var_28]
0x18005e604  mov     eax, edi
0x18005e606  mov     rbx, [r11+38h]
0x18005e60a  mov     rbp, [r11+40h]
0x18005e60e  mov     rsp, r11
0x18005e611  pop     r15
0x18005e613  pop     r14
0x18005e615  pop     r13
0x18005e617  pop     rdi
0x18005e618  pop     rsi
0x18005e619  retn
```
