# CWMPropHandlerBase::CreateNamePropMapping(void)

- ea: `0x18005bbe0`
- end: `0x18005bee4`
- name: `?CreateNamePropMapping@CWMPropHandlerBase@@MEAAJXZ`
- size: `772`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting`

## callees

- `0x180001f90`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18004cd9c`
- `0x1800518f0`
- `0x180051ce4`
- `0x180051d54`
- `0x18005469c`
- `0x180054b50`
- `0x18005bbe0`
- `0x18005ca00`
- `0x18005cb28`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005be1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005be1a`

## string_xrefs

- `0x18005bbfa`: `CWMPropHandlerBase::CreateNamePropMapping`
- `0x18005be71`: `CWMPropHandlerBase::CreateNamePropMapping`

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
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
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
    (*(void (__fastcall **)(CMFProperty *, __int64 *, _QWORD))(*(_QWORD *)v12 + 168LL))(
      v12,
      MF_MD_ACCESSTYPE,
      *((unsigned int *)&krgPKeyWMMap + 10 * i + 7));
    (*(void (__fastcall **)(CMFProperty *, __int64 *, _QWORD))(*(_QWORD *)v12 + 168LL))(
      v12,
      MF_MD_PKEY_EXCEPTIONAL,
      *((unsigned __int8 *)&krgPKeyWMMap + 40 * i + 32));
    v13 = *((_QWORD *)&krgPKeyWMMap + 5 * i);
    *(_OWORD *)((char *)v12 + 76) = *(_OWORD *)v13;
    *((_DWORD *)v12 + 23) = *(_DWORD *)(v13 + 16);
    v14 = CMFBaseStringT<unsigned short>::PContents(v20, *(_QWORD *)v12);
    (*(void (__fastcall **)(CMFProperty *, __int64 *, __int64))(v15 + 200))(v12, MF_MD_NAME, v14);
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
0x18005bbe0  mov     rax, rsp
0x18005bbe3  mov     [rax+10h], rbx
0x18005bbe7  mov     [rax+18h], rbp
0x18005bbeb  push    rsi
0x18005bbec  push    rdi
0x18005bbed  push    r13
0x18005bbef  push    r14
0x18005bbf1  push    r15
0x18005bbf3  sub     rsp, 50h
0x18005bbf7  mov     rbp, rcx
0x18005bbfa  lea     rdx, aCwmprophandler_1; "CWMPropHandlerBase::CreateNamePropMappi"...
0x18005bc01  lea     rcx, [rax+8]; this
0x18005bc05  mov     r8d, 2FEh; int
0x18005bc0b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005bc10  xor     edi, edi
0x18005bc12  xor     ecx, ecx
0x18005bc14  lea     eax, [rdi+7Ch]
0x18005bc17  inc     ecx
0x18005bc19  shr     eax, 1
0x18005bc1b  jnz     short loc_18005BC17
0x18005bc1d  mov     ebx, 1
0x18005bc22  lea     r15, [rbp+3A0h]
0x18005bc29  shl     ebx, cl
0x18005bc2b  mov     rcx, r15
0x18005bc2e  mov     edx, ebx
0x18005bc30  call    ?Initialize@?$CTBucketHash@V?$CMFBaseStringT@G@@PEAVCMFProperty@@@@QEAAJKK@Z; CTBucketHash<CMFBaseStringT<ushort>,CMFProperty *>::Initialize(ulong,ulong)
0x18005bc35  lea     r14, [rbp+518h]
0x18005bc3c  mov     edx, ebx
0x18005bc3e  mov     rcx, r14
0x18005bc41  call    ?Initialize@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAJKK@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Initialize(ulong,ulong)
0x18005bc46  xor     esi, esi
0x18005bc48  lea     r13, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x18005bc4f  cmp     esi, 7Ch ; '|'
0x18005bc52  jnb     loc_18005BEBC
0x18005bc58  lea     rdi, [rsi+rsi*4]
0x18005bc5c  mov     rdx, [r13+rdi*8+10h]
0x18005bc61  lea     rcx, [rsp+78h+var_48]
0x18005bc66  call    ??0?$CMFBaseStringT@G@@QEAA@PEBGJ@Z; CMFBaseStringT<ushort>::CMFBaseStringT<ushort>(ushort const *,long)
0x18005bc6b  mov     ecx, 78h ; 'x'; Size
0x18005bc70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005bc75  test    rax, rax
0x18005bc78  jz      loc_18005BE09
0x18005bc7e  mov     rdx, [r13+rdi*8+0]; struct _tagpropertykey *
0x18005bc83  mov     rcx, rax; this
0x18005bc86  call    ??0CMFProperty@@QEAA@AEBU_tagpropertykey@@@Z; CMFProperty::CMFProperty(_tagpropertykey const &)
0x18005bc8b  mov     [rsp+78h+arg_0], rax
0x18005bc93  mov     rbx, rax
0x18005bc96  test    rax, rax
0x18005bc99  jz      loc_18005BE09
0x18005bc9f  mov     rax, [rax]
0x18005bca2  lea     rdx, MF_MD_SHELLMULTI
0x18005bca9  movzx   r8d, byte ptr [r13+rdi*8+0Ah]
0x18005bcaf  mov     rcx, rbx
0x18005bcb2  mov     rax, [rax+0A8h]
0x18005bcb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcbe  mov     rax, [rbx]
0x18005bcc1  lea     rdx, MF_MD_FSDKMULTI
0x18005bcc8  movzx   r8d, byte ptr [r13+rdi*8+1Ah]
0x18005bcce  mov     rcx, rbx
0x18005bcd1  mov     rax, [rax+0A8h]
0x18005bcd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcdd  mov     rax, [rbx]
0x18005bce0  lea     rdx, MF_MD_SHELLTYPE
0x18005bce7  movzx   r8d, word ptr [r13+rdi*8+8]
0x18005bced  mov     rcx, rbx
0x18005bcf0  mov     rax, [rax+0A8h]
0x18005bcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcfc  mov     rax, [rbx]
0x18005bcff  lea     rdx, MF_MD_FSDKTYPE
0x18005bd06  movzx   r8d, word ptr [r13+rdi*8+18h]
0x18005bd0c  mov     rcx, rbx
0x18005bd0f  mov     rax, [rax+0A8h]
0x18005bd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd1b  mov     rax, [rbx]
0x18005bd1e  lea     rdx, MF_MD_ACCESSTYPE
0x18005bd25  mov     r8d, [r13+rdi*8+1Ch]
0x18005bd2a  mov     rcx, rbx
0x18005bd2d  mov     rax, [rax+0A8h]
0x18005bd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd39  mov     rax, [rbx]
0x18005bd3c  lea     rdx, MF_MD_PKEY_EXCEPTIONAL
0x18005bd43  movzx   r8d, byte ptr [r13+rdi*8+20h]
0x18005bd49  mov     rcx, rbx
0x18005bd4c  mov     rax, [rax+0A8h]
0x18005bd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd58  lea     rax, ?krgPKeyWMMap@@3QBUPKEY_TO_WM_MAP@@B; PKEY_TO_WM_MAP const near * const krgPKeyWMMap
0x18005bd5f  mov     rax, [rax+rdi*8]
0x18005bd63  lea     rcx, [rsp+78h+var_48]
0x18005bd68  movups  xmm0, xmmword ptr [rax]
0x18005bd6b  movups  xmmword ptr [rbx+4Ch], xmm0
0x18005bd6f  mov     eax, [rax+10h]
0x18005bd72  mov     [rbx+5Ch], eax
0x18005bd75  mov     rdx, [rbx]
0x18005bd78  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18005bd7d  mov     r8, rax
0x18005bd80  mov     rcx, rbx
0x18005bd83  mov     rax, [rdx+0C8h]
0x18005bd8a  lea     rdx, MF_MD_NAME
0x18005bd91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd96  lea     r8, [rsp+78h+arg_0]
0x18005bd9e  mov     rcx, r15
0x18005bda1  lea     rdx, [rsp+78h+var_48]
0x18005bda6  call    ?Insert@?$CTBucketHash@V?$CMFBaseStringT@G@@PEAVCMFProperty@@@@QEAAJAEBV?$CMFBaseStringT@G@@AEBQEAVCMFProperty@@@Z; CTBucketHash<CMFBaseStringT<ushort>,CMFProperty *>::Insert(CMFBaseStringT<ushort> const &,CMFProperty * const &)
0x18005bdab  mov     edi, eax
0x18005bdad  test    eax, eax
0x18005bdaf  js      short loc_18005BDE9
0x18005bdb1  mov     rax, [rbx]
0x18005bdb4  mov     rcx, rbx
0x18005bdb7  mov     rax, [rax+8]
0x18005bdbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdc0  lea     r8, [rsp+78h+arg_0]
0x18005bdc8  mov     rcx, r14
0x18005bdcb  lea     rdx, [rbx+4Ch]
0x18005bdcf  call    ?Insert@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAJAEBU_tagpropertykey@@AEBQEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Insert(_tagpropertykey const &,CMFProperty * const &)
0x18005bdd4  mov     edi, eax
0x18005bdd6  test    eax, eax
0x18005bdd8  js      short loc_18005BDE9
0x18005bdda  mov     rax, [rbx]
0x18005bddd  mov     rcx, rbx
0x18005bde0  mov     rax, [rax+8]
0x18005bde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bde9  mov     rax, [rbx]
0x18005bdec  mov     rcx, rbx
0x18005bdef  mov     rax, [rax+10h]
0x18005bdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdf8  lea     rcx, [rsp+78h+var_48]
0x18005bdfd  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18005be02  inc     esi
0x18005be04  jmp     loc_18005BC48
0x18005be09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005be10  mov     edi, 8007000Eh
0x18005be15  test    rcx, rcx
0x18005be18  jnz     short loc_18005BE5B
0x18005be1a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005be20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005be27  mov     rcx, rax
0x18005be2a  test    rax, rax
0x18005be2d  jz      short loc_18005BE4D
0x18005be2f  mov     rax, [rax]
0x18005be32  mov     edx, 7F0h
0x18005be37  mov     rax, [rax+8]
0x18005be3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be40  test    eax, eax
0x18005be42  jz      short loc_18005BE4D
0x18005be44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005be4b  jmp     short loc_18005BE5B
0x18005be4d  lea     rcx, qword_1800D6F70; this
0x18005be54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005be5b  cmp     byte ptr [rcx+8], 0
0x18005be5f  jz      short loc_18005BE86
0x18005be61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005be66  cmp     [rax+7CCh], edi
0x18005be6c  jz      short loc_18005BE86
0x18005be6e  mov     r9d, edi; int
0x18005be71  lea     rdx, aCwmprophandler_1; "CWMPropHandlerBase::CreateNamePropMappi"...
0x18005be78  mov     r8d, 31Bh; int
0x18005be7e  mov     rcx, rax; this
0x18005be81  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005be86  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005be8d  jb      short loc_18005BEB2
0x18005be8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be96  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005be9d  mov     edx, 45h ; 'E'
0x18005bea2  mov     [rsp+78h+var_58], edi
0x18005bea6  mov     r9, rbp
0x18005bea9  mov     rcx, [rcx+10h]
0x18005bead  call    WPP_SF_qD
0x18005beb2  lea     rcx, [rsp+78h+var_48]
0x18005beb7  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18005bebc  lea     rcx, [rsp+78h+arg_0]; this
0x18005bec4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005bec9  lea     r11, [rsp+78h+var_28]
0x18005bece  mov     eax, edi
0x18005bed0  mov     rbx, [r11+38h]
0x18005bed4  mov     rbp, [r11+40h]
0x18005bed8  mov     rsp, r11
0x18005bedb  pop     r15
0x18005bedd  pop     r14
0x18005bedf  pop     r13
0x18005bee1  pop     rdi
0x18005bee2  pop     rsi
0x18005bee3  retn
```
