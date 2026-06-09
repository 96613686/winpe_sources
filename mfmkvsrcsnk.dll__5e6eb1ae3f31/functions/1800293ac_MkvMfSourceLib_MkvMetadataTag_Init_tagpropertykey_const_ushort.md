# MkvMfSourceLib::MkvMetadataTag::Init(_tagpropertykey const *,ushort *)

- ea: `0x1800293ac`
- end: `0x1800296f2`
- name: `?Init@MkvMetadataTag@MkvMfSourceLib@@QEAAJPEBU_tagpropertykey@@PEAG@Z`
- size: `838`
- prototype: `int(MkvMfSourceLib::MkvMetadataTag *__hidden this, const struct _tagpropertykey *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a864`

## callees

- `0x180001f90`
- `0x1800036c5`
- `0x1800097f0`
- `0x1800203f0`
- `0x1800293ac`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800295bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800295bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029400`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800294c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002954e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800295e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029677`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029400`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800294c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002954e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800295e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029677`

## pseudocode

```c
__int64 __fastcall MkvMfSourceLib::MkvMetadataTag::Init(
        MkvMfSourceLib::MkvMetadataTag *this,
        const struct _tagpropertykey *a2,
        unsigned __int16 *a3)
{
  _QWORD *v5; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v12; // r8d
  unsigned __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // ebx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  int v25; // r8d
  size_t v26; // rsi
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  void *v30; // rcx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  SIZE_T cb; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)this = a2;
  v5 = operator new(0x18u);
  if ( v5 )
  {
    *(_OWORD *)v5 = 0;
    v5[2] = 0;
  }
  else
  {
    v5 = 0;
  }
  *((_QWORD *)this + 1) = v5;
  if ( !v5 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( !*((_BYTE *)v9 + 8) )
      return 2147942414LL;
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
    if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147024882 )
      return 2147942414LL;
    v12 = 51;
LABEL_44:
    CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::MkvMetadataTag::Init", v12, -2147024882);
    return 2147942414LL;
  }
  *((_BYTE *)this + 16) = 1;
  *(_OWORD *)v5 = 0;
  v5[2] = 0;
  **((_WORD **)this + 1) = 31;
  v13 = -1;
  do
    ++v13;
  while ( a3[v13] );
  if ( v13 + 1 < v13 )
  {
    v33 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v7, v8);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( !*((_BYTE *)v33 + 8) )
      return 2147942934LL;
    v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
    if ( *((_DWORD *)v24 + 499) == -2147024362 )
      return 2147942934LL;
    v25 = 59;
    goto LABEL_55;
  }
  cb = v13 + 1;
  v15 = ULongLongMult(v13 + 1, v6, &cb);
  if ( v15 < 0 )
  {
    v18 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v16, v17);
      CallStackTracing::s_wpInstance = v19;
      if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v18 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
      if ( *((_DWORD *)v20 + 499) != v15 )
        CallStackContext::TraceFailure(v20, "MkvMfSourceLib::MkvMetadataTag::Init", 60, v15);
    }
    return (unsigned int)v15;
  }
  if ( cb <= 0xFFFFFFFF )
  {
    v26 = (unsigned int)cb;
    *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = CoTaskMemAlloc((unsigned int)cb);
    v30 = *(void **)(*((_QWORD *)this + 1) + 8LL);
    if ( !v30 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( !*((_BYTE *)v31 + 8) )
        return 2147942414LL;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
      if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147024882 )
        return 2147942414LL;
      v12 = 71;
      goto LABEL_44;
    }
    memcpy_0(v30, a3, v26);
    return (unsigned int)v15;
  }
  v22 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v16, v17);
    CallStackTracing::s_wpInstance = v23;
    if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
    {
      v22 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v22 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v22 + 8) )
  {
    v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
    if ( *((_DWORD *)v24 + 499) != -2147024362 )
    {
      v25 = 64;
LABEL_55:
      CallStackContext::TraceFailure(v24, "MkvMfSourceLib::MkvMetadataTag::Init", v25, -2147024362);
    }
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x1800293ac  push    rbx
0x1800293ae  push    rbp
0x1800293af  push    rsi
0x1800293b0  push    rdi
0x1800293b1  push    r14
0x1800293b3  push    r15
0x1800293b5  sub     rsp, 28h
0x1800293b9  mov     rdi, rcx
0x1800293bc  mov     [rcx], rdx
0x1800293bf  mov     ecx, 18h; Size
0x1800293c4  mov     rbp, r8
0x1800293c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800293cc  xor     r14d, r14d
0x1800293cf  test    rax, rax
0x1800293d2  jz      short loc_1800293E2
0x1800293d4  xorps   xmm0, xmm0
0x1800293d7  xor     ecx, ecx
0x1800293d9  movups  xmmword ptr [rax], xmm0
0x1800293dc  mov     [rax+10h], rcx
0x1800293e0  jmp     short loc_1800293E5
0x1800293e2  mov     rax, r14
0x1800293e5  mov     [rdi+8], rax
0x1800293e9  mov     r15d, 8007000Eh
0x1800293ef  test    rax, rax
0x1800293f2  jnz     short loc_180029468
0x1800293f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800293fb  test    rcx, rcx
0x1800293fe  jnz     short loc_180029441
0x180029400  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180029406  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002940d  mov     rcx, rax
0x180029410  test    rax, rax
0x180029413  jz      short loc_180029433
0x180029415  mov     rax, [rax]
0x180029418  mov     edx, 7F0h
0x18002941d  mov     rax, [rax+8]
0x180029421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029426  test    eax, eax
0x180029428  jz      short loc_180029433
0x18002942a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029431  jmp     short loc_180029441
0x180029433  lea     rcx, qword_1800D6F70; this
0x18002943a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180029441  cmp     [rcx+8], r14b
0x180029445  jz      loc_180029653
0x18002944b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180029450  cmp     [rax+7CCh], r15d
0x180029457  jz      loc_180029653
0x18002945d  mov     r8d, 33h ; '3'
0x180029463  jmp     loc_180029641
0x180029468  mov     byte ptr [rdi+10h], 1
0x18002946c  xor     ecx, ecx
0x18002946e  xorps   xmm0, xmm0
0x180029471  movups  xmmword ptr [rax], xmm0
0x180029474  mov     [rax+10h], rcx
0x180029478  mov     rax, [rdi+8]
0x18002947c  mov     word ptr [rax], 1Fh
0x180029481  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029485  inc     rax
0x180029488  cmp     [rbp+rax*2+0], r14w
0x18002948e  jnz     short loc_180029485
0x180029490  lea     rcx, [rax+1]; unsigned __int64
0x180029494  mov     esi, 80070216h
0x180029499  cmp     rcx, rax
0x18002949c  jb      loc_18002966B
0x1800294a2  lea     r8, [rsp+58h+cb]; unsigned __int64 *
0x1800294a7  mov     [rsp+58h+cb], rcx
0x1800294ac  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800294b1  mov     ebx, eax
0x1800294b3  test    eax, eax
0x1800294b5  jns     short loc_180029536
0x1800294b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800294be  test    rcx, rcx
0x1800294c1  jnz     short loc_180029504
0x1800294c3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800294c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800294d0  mov     rcx, rax
0x1800294d3  test    rax, rax
0x1800294d6  jz      short loc_1800294F6
0x1800294d8  mov     rax, [rax]
0x1800294db  mov     edx, 7F0h
0x1800294e0  mov     rax, [rax+8]
0x1800294e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294e9  test    eax, eax
0x1800294eb  jz      short loc_1800294F6
0x1800294ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800294f4  jmp     short loc_180029504
0x1800294f6  lea     rcx, qword_1800D6F70; this
0x1800294fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180029504  cmp     [rcx+8], r14b
0x180029508  jz      short loc_18002952F
0x18002950a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002950f  cmp     [rax+7CCh], ebx
0x180029515  jz      short loc_18002952F
0x180029517  mov     r9d, ebx; int
0x18002951a  lea     rdx, aMkvmfsourcelib_82; "MkvMfSourceLib::MkvMetadataTag::Init"
0x180029521  mov     r8d, 3Ch ; '<'; int
0x180029527  mov     rcx, rax; this
0x18002952a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002952f  mov     eax, ebx
0x180029531  jmp     loc_1800296E5
0x180029536  mov     eax, 0FFFFFFFFh
0x18002953b  cmp     [rsp+58h+cb], rax
0x180029540  jbe     short loc_1800295B5
0x180029542  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029549  test    rcx, rcx
0x18002954c  jnz     short loc_18002958F
0x18002954e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180029554  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002955b  mov     rcx, rax
0x18002955e  test    rax, rax
0x180029561  jz      short loc_180029581
0x180029563  mov     rax, [rax]
0x180029566  mov     edx, 7F0h
0x18002956b  mov     rax, [rax+8]
0x18002956f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029574  test    eax, eax
0x180029576  jz      short loc_180029581
0x180029578  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002957f  jmp     short loc_18002958F
0x180029581  lea     rcx, qword_1800D6F70; this
0x180029588  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002958f  cmp     [rcx+8], r14b
0x180029593  jz      loc_1800296E3
0x180029599  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002959e  cmp     [rax+7CCh], esi
0x1800295a4  jz      loc_1800296E3
0x1800295aa  mov     r8d, 40h ; '@'
0x1800295b0  jmp     loc_1800296D1
0x1800295b5  mov     esi, dword ptr [rsp+58h+cb]
0x1800295b9  mov     ecx, esi; cb
0x1800295bb  call    cs:__imp_CoTaskMemAlloc
0x1800295c1  mov     rcx, [rdi+8]
0x1800295c5  mov     [rcx+8], rax
0x1800295c9  mov     rax, [rdi+8]
0x1800295cd  mov     rcx, [rax+8]; void *
0x1800295d1  test    rcx, rcx
0x1800295d4  jnz     loc_18002965B
0x1800295da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800295e1  test    rcx, rcx
0x1800295e4  jnz     short loc_180029627
0x1800295e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800295ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800295f3  mov     rcx, rax
0x1800295f6  test    rax, rax
0x1800295f9  jz      short loc_180029619
0x1800295fb  mov     rax, [rax]
0x1800295fe  mov     edx, 7F0h
0x180029603  mov     rax, [rax+8]
0x180029607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002960c  test    eax, eax
0x18002960e  jz      short loc_180029619
0x180029610  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029617  jmp     short loc_180029627
0x180029619  lea     rcx, qword_1800D6F70; this
0x180029620  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180029627  cmp     [rcx+8], r14b
0x18002962b  jz      short loc_180029653
0x18002962d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180029632  cmp     [rax+7CCh], r15d
0x180029639  jz      short loc_180029653
0x18002963b  mov     r8d, 47h ; 'G'; int
0x180029641  mov     r9d, r15d; int
0x180029644  lea     rdx, aMkvmfsourcelib_82; "MkvMfSourceLib::MkvMetadataTag::Init"
0x18002964b  mov     rcx, rax; this
0x18002964e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180029653  mov     eax, r15d
0x180029656  jmp     loc_1800296E5
0x18002965b  mov     r8, rsi; Size
0x18002965e  mov     rdx, rbp; Src
0x180029661  call    memcpy_0
0x180029666  jmp     loc_18002952F
0x18002966b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029672  test    rcx, rcx
0x180029675  jnz     short loc_1800296B8
0x180029677  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002967d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029684  mov     rcx, rax
0x180029687  test    rax, rax
0x18002968a  jz      short loc_1800296AA
0x18002968c  mov     rax, [rax]
0x18002968f  mov     edx, 7F0h
0x180029694  mov     rax, [rax+8]
0x180029698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002969d  test    eax, eax
0x18002969f  jz      short loc_1800296AA
0x1800296a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800296a8  jmp     short loc_1800296B8
0x1800296aa  lea     rcx, qword_1800D6F70; this
0x1800296b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800296b8  cmp     [rcx+8], r14b
0x1800296bc  jz      short loc_1800296E3
0x1800296be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800296c3  cmp     [rax+7CCh], esi
0x1800296c9  jz      short loc_1800296E3
0x1800296cb  mov     r8d, 3Bh ; ';'; int
0x1800296d1  mov     r9d, esi; int
0x1800296d4  lea     rdx, aMkvmfsourcelib_82; "MkvMfSourceLib::MkvMetadataTag::Init"
0x1800296db  mov     rcx, rax; this
0x1800296de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800296e3  mov     eax, esi
0x1800296e5  add     rsp, 28h
0x1800296e9  pop     r15
0x1800296eb  pop     r14
0x1800296ed  pop     rdi
0x1800296ee  pop     rsi
0x1800296ef  pop     rbp
0x1800296f0  pop     rbx
0x1800296f1  retn
```
