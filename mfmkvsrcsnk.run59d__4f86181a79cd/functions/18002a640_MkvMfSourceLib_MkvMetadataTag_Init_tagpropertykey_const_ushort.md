# MkvMfSourceLib::MkvMetadataTag::Init(_tagpropertykey const *,ushort *)

- ea: `0x18002a640`
- end: `0x18002a9af`
- name: `?Init@MkvMetadataTag@MkvMfSourceLib@@QEAAJPEBU_tagpropertykey@@PEAG@Z`
- size: `879`
- prototype: `int(MkvMfSourceLib::MkvMetadataTag *__hidden this, const struct _tagpropertykey *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bb28`

## callees

- `0x180001fb0`
- `0x180003705`
- `0x180009b04`
- `0x180021240`
- `0x18002a640`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a865`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a694`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a761`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a7f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a896`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a92d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a694`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a761`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a7f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a896`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a92d`

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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v33 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v18 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v31 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v22 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18002a640  push    rbx
0x18002a642  push    rbp
0x18002a643  push    rsi
0x18002a644  push    rdi
0x18002a645  push    r14
0x18002a647  push    r15
0x18002a649  sub     rsp, 28h
0x18002a64d  mov     rdi, rcx
0x18002a650  mov     [rcx], rdx
0x18002a653  mov     ecx, 18h; Size
0x18002a658  mov     rbp, r8
0x18002a65b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a660  xor     r14d, r14d
0x18002a663  test    rax, rax
0x18002a666  jz      short loc_18002A676
0x18002a668  xorps   xmm0, xmm0
0x18002a66b  xor     ecx, ecx
0x18002a66d  movups  xmmword ptr [rax], xmm0
0x18002a670  mov     [rax+10h], rcx
0x18002a674  jmp     short loc_18002A679
0x18002a676  mov     rax, r14
0x18002a679  mov     [rdi+8], rax
0x18002a67d  mov     r15d, 8007000Eh
0x18002a683  test    rax, rax
0x18002a686  jnz     short loc_18002A702
0x18002a688  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a68f  test    rcx, rcx
0x18002a692  jnz     short loc_18002A6DB
0x18002a694  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a69b  nop     dword ptr [rax+rax+00h]
0x18002a6a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a6a7  mov     rcx, rax
0x18002a6aa  test    rax, rax
0x18002a6ad  jz      short loc_18002A6CD
0x18002a6af  mov     rax, [rax]
0x18002a6b2  mov     edx, 7F0h
0x18002a6b7  mov     rax, [rax+8]
0x18002a6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6c0  test    eax, eax
0x18002a6c2  jz      short loc_18002A6CD
0x18002a6c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a6cb  jmp     short loc_18002A6DB
0x18002a6cd  lea     rcx, qword_1800DBF70; this
0x18002a6d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a6db  cmp     [rcx+8], r14b
0x18002a6df  jz      loc_18002A909
0x18002a6e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a6ea  cmp     [rax+7CCh], r15d
0x18002a6f1  jz      loc_18002A909
0x18002a6f7  mov     r8d, 33h ; '3'
0x18002a6fd  jmp     loc_18002A8F7
0x18002a702  mov     byte ptr [rdi+10h], 1
0x18002a706  xor     ecx, ecx
0x18002a708  xorps   xmm0, xmm0
0x18002a70b  movups  xmmword ptr [rax], xmm0
0x18002a70e  mov     [rax+10h], rcx
0x18002a712  mov     rax, [rdi+8]
0x18002a716  mov     word ptr [rax], 1Fh
0x18002a71b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a71f  inc     rax
0x18002a722  cmp     [rbp+rax*2+0], r14w
0x18002a728  jnz     short loc_18002A71F
0x18002a72a  lea     rcx, [rax+1]; unsigned __int64
0x18002a72e  mov     esi, 80070216h
0x18002a733  cmp     rcx, rax
0x18002a736  jb      loc_18002A921
0x18002a73c  lea     r8, [rsp+58h+cb]; unsigned __int64 *
0x18002a741  mov     [rsp+58h+cb], rcx
0x18002a746  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a74b  mov     ebx, eax
0x18002a74d  test    eax, eax
0x18002a74f  jns     loc_18002A7DA
0x18002a755  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a75c  test    rcx, rcx
0x18002a75f  jnz     short loc_18002A7A8
0x18002a761  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a768  nop     dword ptr [rax+rax+00h]
0x18002a76d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a774  mov     rcx, rax
0x18002a777  test    rax, rax
0x18002a77a  jz      short loc_18002A79A
0x18002a77c  mov     rax, [rax]
0x18002a77f  mov     edx, 7F0h
0x18002a784  mov     rax, [rax+8]
0x18002a788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a78d  test    eax, eax
0x18002a78f  jz      short loc_18002A79A
0x18002a791  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a798  jmp     short loc_18002A7A8
0x18002a79a  lea     rcx, qword_1800DBF70; this
0x18002a7a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a7a8  cmp     [rcx+8], r14b
0x18002a7ac  jz      short loc_18002A7D3
0x18002a7ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a7b3  cmp     [rax+7CCh], ebx
0x18002a7b9  jz      short loc_18002A7D3
0x18002a7bb  mov     r9d, ebx; int
0x18002a7be  lea     rdx, aMkvmfsourcelib_82; "MkvMfSourceLib::MkvMetadataTag::Init"
0x18002a7c5  mov     r8d, 3Ch ; '<'; int
0x18002a7cb  mov     rcx, rax; this
0x18002a7ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a7d3  mov     eax, ebx
0x18002a7d5  jmp     loc_18002A9A1
0x18002a7da  mov     eax, 0FFFFFFFFh
0x18002a7df  cmp     [rsp+58h+cb], rax
0x18002a7e4  jbe     short loc_18002A85F
0x18002a7e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a7ed  test    rcx, rcx
0x18002a7f0  jnz     short loc_18002A839
0x18002a7f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a7f9  nop     dword ptr [rax+rax+00h]
0x18002a7fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a805  mov     rcx, rax
0x18002a808  test    rax, rax
0x18002a80b  jz      short loc_18002A82B
0x18002a80d  mov     rax, [rax]
0x18002a810  mov     edx, 7F0h
0x18002a815  mov     rax, [rax+8]
0x18002a819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a81e  test    eax, eax
0x18002a820  jz      short loc_18002A82B
0x18002a822  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a829  jmp     short loc_18002A839
0x18002a82b  lea     rcx, qword_1800DBF70; this
0x18002a832  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a839  cmp     [rcx+8], r14b
0x18002a83d  jz      loc_18002A99F
0x18002a843  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a848  cmp     [rax+7CCh], esi
0x18002a84e  jz      loc_18002A99F
0x18002a854  mov     r8d, 40h ; '@'
0x18002a85a  jmp     loc_18002A98D
0x18002a85f  mov     esi, dword ptr [rsp+58h+cb]
0x18002a863  mov     ecx, esi; cb
0x18002a865  call    cs:__imp_CoTaskMemAlloc
0x18002a86c  nop     dword ptr [rax+rax+00h]
0x18002a871  mov     rcx, [rdi+8]
0x18002a875  mov     [rcx+8], rax
0x18002a879  mov     rax, [rdi+8]
0x18002a87d  mov     rcx, [rax+8]; void *
0x18002a881  test    rcx, rcx
0x18002a884  jnz     loc_18002A911
0x18002a88a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a891  test    rcx, rcx
0x18002a894  jnz     short loc_18002A8DD
0x18002a896  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a89d  nop     dword ptr [rax+rax+00h]
0x18002a8a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8a9  mov     rcx, rax
0x18002a8ac  test    rax, rax
0x18002a8af  jz      short loc_18002A8CF
0x18002a8b1  mov     rax, [rax]
0x18002a8b4  mov     edx, 7F0h
0x18002a8b9  mov     rax, [rax+8]
0x18002a8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8c2  test    eax, eax
0x18002a8c4  jz      short loc_18002A8CF
0x18002a8c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8cd  jmp     short loc_18002A8DD
0x18002a8cf  lea     rcx, qword_1800DBF70; this
0x18002a8d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8dd  cmp     [rcx+8], r14b
0x18002a8e1  jz      short loc_18002A909
0x18002a8e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a8e8  cmp     [rax+7CCh], r15d
0x18002a8ef  jz      short loc_18002A909
0x18002a8f1  mov     r8d, 47h ; 'G'; int
0x18002a8f7  mov     r9d, r15d; int
0x18002a8fa  lea     rdx, aMkvmfsourcelib_82; "MkvMfSourceLib::MkvMetadataTag::Init"
0x18002a901  mov     rcx, rax; this
0x18002a904  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a909  mov     eax, r15d
0x18002a90c  jmp     loc_18002A9A1
0x18002a911  mov     r8, rsi; Size
0x18002a914  mov     rdx, rbp; Src
0x18002a917  call    memcpy_0
0x18002a91c  jmp     loc_18002A7D3
0x18002a921  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a928  test    rcx, rcx
0x18002a92b  jnz     short loc_18002A974
0x18002a92d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a934  nop     dword ptr [rax+rax+00h]
0x18002a939  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a940  mov     rcx, rax
0x18002a943  test    rax, rax
0x18002a946  jz      short loc_18002A966
0x18002a948  mov     rax, [rax]
0x18002a94b  mov     edx, 7F0h
0x18002a950  mov     rax, [rax+8]
0x18002a954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a959  test    eax, eax
0x18002a95b  jz      short loc_18002A966
0x18002a95d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a964  jmp     short loc_18002A974
0x18002a966  lea     rcx, qword_1800DBF70; this
0x18002a96d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a974  cmp     [rcx+8], r14b
0x18002a978  jz      short loc_18002A99F
0x18002a97a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002a97f  cmp     [rax+7CCh], esi
0x18002a985  jz      short loc_18002A99F
0x18002a987  mov     r8d, 3Bh ; ';'; int
0x18002a98d  mov     r9d, esi; int
0x18002a990  lea     rdx, aMkvmfsourcelib_82; "MkvMfSourceLib::MkvMetadataTag::Init"
0x18002a997  mov     rcx, rax; this
0x18002a99a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002a99f  mov     eax, esi
0x18002a9a1  add     rsp, 28h
0x18002a9a5  pop     r15
0x18002a9a7  pop     r14
0x18002a9a9  pop     rdi
0x18002a9aa  pop     rsi
0x18002a9ab  pop     rbp
0x18002a9ac  pop     rbx
0x18002a9ad  retn
```
