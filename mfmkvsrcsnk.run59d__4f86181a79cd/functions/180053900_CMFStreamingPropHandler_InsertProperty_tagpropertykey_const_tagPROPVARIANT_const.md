# CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x180053900`
- end: `0x180053c1d`
- name: `?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180010540`
- `0x180051754`
- `0x180051e30`
- `0x1800526dc`
- `0x180052a48`
- `0x18005328c`

## callees

- `0x180009b04`
- `0x1800516c8`
- `0x180053900`
- `0x1800744d8`
- `0x1800746f8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180053963`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180053963`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005398c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053a30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053ad4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053b8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005398c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053a30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053ad4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053b8c`

## pseudocode

```c
__int64 __fastcall CMFStreamingPropHandler::InsertProperty(
        CMFStreamingPropHandler *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  char v6; // bl
  _WORD *v7; // r8
  IStream *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  int v13; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  PROPVARIANT *p_pvar; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  PROPVARIANT pvar; // [rsp+30h] [rbp-20h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  v6 = 0;
  if ( !(unsigned int)operator==(a2, &PKEY_ThumbnailStream) || *v7 == 66 )
  {
LABEL_33:
    p_pvar = &pvar;
    if ( !v6 )
      p_pvar = a3;
    v13 = (*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(**((_QWORD **)this + 3)
                                                                                           + 48LL))(
            *((_QWORD *)this + 3),
            a2,
            p_pvar);
    if ( v13 < 0 )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
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
      if ( *((_BYTE *)v31 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
        {
          v16 = 83;
          goto LABEL_44;
        }
      }
    }
    goto LABEL_45;
  }
  pvar.vt = 66;
  v8 = SHCreateMemStream(0, 0);
  pvar.hVal.QuadPart = (LONGLONG)v8;
  if ( !v8 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    v13 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
      {
        v16 = 68;
LABEL_44:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFStreamingPropHandler::InsertProperty", v16, v13);
        goto LABEL_45;
      }
    }
    goto LABEL_45;
  }
  if ( a3->vt != 65 )
  {
    if ( a3->vt != 4113 )
      goto LABEL_33;
    v13 = ((__int64 (__fastcall *)(IStream *, BYTE *, _QWORD, _QWORD))v8->lpVtbl->Write)(
            v8,
            a3->bstrblobVal.pData,
            a3->ulVal,
            0);
    if ( v13 < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
        {
          v16 = 77;
          goto LABEL_44;
        }
      }
      goto LABEL_45;
    }
    goto LABEL_32;
  }
  v13 = ((__int64 (__fastcall *)(IStream *, BYTE *, _QWORD, _QWORD))v8->lpVtbl->Write)(
          v8,
          a3->bstrblobVal.pData,
          a3->ulVal,
          0);
  if ( v13 >= 0 )
  {
LABEL_32:
    (*((void (__fastcall **)(LARGE_INTEGER, _QWORD, _QWORD, _QWORD))*pvar.pbstrVal + 5))(pvar.hVal, 0, 0, 0);
    v6 = 1;
    goto LABEL_33;
  }
  v20 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
    CallStackTracing::s_wpInstance = v21;
    if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v20 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v20 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
    {
      v16 = 71;
      goto LABEL_44;
    }
  }
LABEL_45:
  CMFPropVariant::Clear(&pvar);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180053900  mov     [rsp-18h+arg_0], rbx
0x180053905  mov     [rsp-18h+arg_8], rsi
0x18005390a  push    rbp
0x18005390b  push    rdi
0x18005390c  push    r14
0x18005390e  mov     rbp, rsp
0x180053911  sub     rsp, 50h
0x180053915  mov     rsi, rdx
0x180053918  xor     eax, eax
0x18005391a  mov     r14, rcx
0x18005391d  mov     qword ptr [rbp+pvar+10h], rax
0x180053921  xorps   xmm0, xmm0
0x180053924  lea     rdx, PKEY_ThumbnailStream
0x18005392b  mov     rcx, rsi
0x18005392e  mov     rdi, r8
0x180053931  movups  xmmword ptr [rbp+pvar], xmm0
0x180053935  xor     bl, bl
0x180053937  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18005393c  test    eax, eax
0x18005393e  jz      loc_180053B5D
0x180053944  mov     ecx, 42h ; 'B'
0x180053949  cmp     [r8], cx
0x18005394d  jz      loc_180053B5D
0x180053953  mov     word ptr [rbp+pvar], cx
0x180053957  xor     edx, edx; cbInit
0x180053959  xor     ecx, ecx; pInit
0x18005395b  mov     [rbp+arg_18], 0
0x180053963  call    cs:__imp_SHCreateMemStream
0x18005396a  nop     dword ptr [rax+rax+00h]
0x18005396f  mov     qword ptr [rbp+pvar+8], rax
0x180053973  mov     rcx, rax
0x180053976  test    rax, rax
0x180053979  jnz     short loc_1800539F9
0x18005397b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053982  mov     ebx, 8007000Eh
0x180053987  test    rcx, rcx
0x18005398a  jnz     short loc_1800539D3
0x18005398c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053993  nop     dword ptr [rax+rax+00h]
0x180053998  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005399f  mov     rcx, rax
0x1800539a2  test    rax, rax
0x1800539a5  jz      short loc_1800539C5
0x1800539a7  mov     rax, [rax]
0x1800539aa  mov     edx, 7F0h
0x1800539af  mov     rax, [rax+8]
0x1800539b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800539b8  test    eax, eax
0x1800539ba  jz      short loc_1800539C5
0x1800539bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800539c3  jmp     short loc_1800539D3
0x1800539c5  lea     rcx, qword_1800DBF70; this
0x1800539cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800539d3  cmp     byte ptr [rcx+8], 0
0x1800539d7  jz      loc_180053BFE
0x1800539dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800539e2  cmp     [rax+7CCh], ebx
0x1800539e8  jz      loc_180053BFE
0x1800539ee  mov     r8d, 44h ; 'D'
0x1800539f4  jmp     loc_180053BEC
0x1800539f9  cmp     word ptr [rdi], 41h ; 'A'
0x1800539fd  jnz     loc_180053A9D
0x180053a03  mov     rax, [rax]
0x180053a06  xor     r9d, r9d
0x180053a09  mov     r8d, [rdi+8]
0x180053a0d  mov     rdx, [rdi+10h]
0x180053a11  mov     rax, [rax+20h]
0x180053a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a1a  mov     ebx, eax
0x180053a1c  test    eax, eax
0x180053a1e  jns     loc_180053B41
0x180053a24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a2b  test    rcx, rcx
0x180053a2e  jnz     short loc_180053A77
0x180053a30  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053a37  nop     dword ptr [rax+rax+00h]
0x180053a3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a43  mov     rcx, rax
0x180053a46  test    rax, rax
0x180053a49  jz      short loc_180053A69
0x180053a4b  mov     rax, [rax]
0x180053a4e  mov     edx, 7F0h
0x180053a53  mov     rax, [rax+8]
0x180053a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a5c  test    eax, eax
0x180053a5e  jz      short loc_180053A69
0x180053a60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a67  jmp     short loc_180053A77
0x180053a69  lea     rcx, qword_1800DBF70; this
0x180053a70  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053a77  cmp     byte ptr [rcx+8], 0
0x180053a7b  jz      loc_180053BFE
0x180053a81  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053a86  cmp     [rax+7CCh], ebx
0x180053a8c  jz      loc_180053BFE
0x180053a92  mov     r8d, 47h ; 'G'
0x180053a98  jmp     loc_180053BEC
0x180053a9d  mov     eax, 1011h
0x180053aa2  cmp     [rdi], ax
0x180053aa5  jnz     loc_180053B5D
0x180053aab  mov     rax, [rcx]
0x180053aae  xor     r9d, r9d
0x180053ab1  mov     r8d, [rdi+8]
0x180053ab5  mov     rdx, [rdi+10h]
0x180053ab9  mov     rax, [rax+20h]
0x180053abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ac2  mov     ebx, eax
0x180053ac4  test    eax, eax
0x180053ac6  jns     short loc_180053B41
0x180053ac8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053acf  test    rcx, rcx
0x180053ad2  jnz     short loc_180053B1B
0x180053ad4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053adb  nop     dword ptr [rax+rax+00h]
0x180053ae0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053ae7  mov     rcx, rax
0x180053aea  test    rax, rax
0x180053aed  jz      short loc_180053B0D
0x180053aef  mov     rax, [rax]
0x180053af2  mov     edx, 7F0h
0x180053af7  mov     rax, [rax+8]
0x180053afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b00  test    eax, eax
0x180053b02  jz      short loc_180053B0D
0x180053b04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b0b  jmp     short loc_180053B1B
0x180053b0d  lea     rcx, qword_1800DBF70; this
0x180053b14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b1b  cmp     byte ptr [rcx+8], 0
0x180053b1f  jz      loc_180053BFE
0x180053b25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053b2a  cmp     [rax+7CCh], ebx
0x180053b30  jz      loc_180053BFE
0x180053b36  mov     r8d, 4Dh ; 'M'
0x180053b3c  jmp     loc_180053BEC
0x180053b41  mov     rcx, qword ptr [rbp+pvar+8]
0x180053b45  xor     r9d, r9d
0x180053b48  mov     rdx, [rbp+arg_18]
0x180053b4c  xor     r8d, r8d
0x180053b4f  mov     rax, [rcx]
0x180053b52  mov     rax, [rax+28h]
0x180053b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b5b  mov     bl, 1
0x180053b5d  mov     rcx, [r14+18h]
0x180053b61  lea     r8, [rbp+pvar]
0x180053b65  test    bl, bl
0x180053b67  mov     rdx, rsi
0x180053b6a  cmovz   r8, rdi
0x180053b6e  mov     rax, [rcx]
0x180053b71  mov     rax, [rax+30h]
0x180053b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b7a  mov     ebx, eax
0x180053b7c  test    eax, eax
0x180053b7e  jns     short loc_180053BFE
0x180053b80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b87  test    rcx, rcx
0x180053b8a  jnz     short loc_180053BD3
0x180053b8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053b93  nop     dword ptr [rax+rax+00h]
0x180053b98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053b9f  mov     rcx, rax
0x180053ba2  test    rax, rax
0x180053ba5  jz      short loc_180053BC5
0x180053ba7  mov     rax, [rax]
0x180053baa  mov     edx, 7F0h
0x180053baf  mov     rax, [rax+8]
0x180053bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bb8  test    eax, eax
0x180053bba  jz      short loc_180053BC5
0x180053bbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053bc3  jmp     short loc_180053BD3
0x180053bc5  lea     rcx, qword_1800DBF70; this
0x180053bcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053bd3  cmp     byte ptr [rcx+8], 0
0x180053bd7  jz      short loc_180053BFE
0x180053bd9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053bde  cmp     [rax+7CCh], ebx
0x180053be4  jz      short loc_180053BFE
0x180053be6  mov     r8d, 53h ; 'S'; int
0x180053bec  mov     r9d, ebx; int
0x180053bef  lea     rdx, aCmfstreamingpr; "CMFStreamingPropHandler::InsertProperty"
0x180053bf6  mov     rcx, rax; this
0x180053bf9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053bfe  lea     rcx, [rbp+pvar]; pvar
0x180053c02  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180053c07  mov     rsi, [rsp+50h+arg_8]
0x180053c0c  mov     eax, ebx
0x180053c0e  mov     rbx, [rsp+50h+arg_0]
0x180053c13  add     rsp, 50h
0x180053c17  pop     r14
0x180053c19  pop     rdi
0x180053c1a  pop     rbp
0x180053c1b  retn
```
