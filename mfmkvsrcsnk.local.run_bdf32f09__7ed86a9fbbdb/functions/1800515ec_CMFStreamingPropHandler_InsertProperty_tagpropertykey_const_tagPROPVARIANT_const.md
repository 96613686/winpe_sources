# CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x1800515ec`
- end: `0x1800518ea`
- name: `?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000fe50`
- `0x18004f524`
- `0x18004fbe0`
- `0x180050454`
- `0x1800507a8`
- `0x180050fac`

## callees

- `0x1800097f0`
- `0x18004f4a0`
- `0x1800515ec`
- `0x180071330`
- `0x180071524`
- `0x1800af010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18005164f`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18005164f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051710`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800517ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051860`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051710`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800517ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051860`

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
          v31 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v25 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v20 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800515ec  mov     [rsp-18h+arg_0], rbx
0x1800515f1  mov     [rsp-18h+arg_8], rsi
0x1800515f6  push    rbp
0x1800515f7  push    rdi
0x1800515f8  push    r14
0x1800515fa  mov     rbp, rsp
0x1800515fd  sub     rsp, 50h
0x180051601  mov     rsi, rdx
0x180051604  xor     eax, eax
0x180051606  mov     r14, rcx
0x180051609  mov     qword ptr [rbp+pvar+10h], rax
0x18005160d  xorps   xmm0, xmm0
0x180051610  lea     rdx, PKEY_ThumbnailStream
0x180051617  mov     rcx, rsi
0x18005161a  mov     rdi, r8
0x18005161d  movups  xmmword ptr [rbp+pvar], xmm0
0x180051621  xor     bl, bl
0x180051623  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180051628  test    eax, eax
0x18005162a  jz      loc_180051831
0x180051630  mov     ecx, 42h ; 'B'
0x180051635  cmp     [r8], cx
0x180051639  jz      loc_180051831
0x18005163f  mov     word ptr [rbp+pvar], cx
0x180051643  xor     edx, edx; cbInit
0x180051645  xor     ecx, ecx; pInit
0x180051647  mov     [rbp+arg_18], 0
0x18005164f  call    cs:__imp_SHCreateMemStream
0x180051655  mov     qword ptr [rbp+pvar+8], rax
0x180051659  mov     rcx, rax
0x18005165c  test    rax, rax
0x18005165f  jnz     short loc_1800516D9
0x180051661  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051668  mov     ebx, 8007000Eh
0x18005166d  test    rcx, rcx
0x180051670  jnz     short loc_1800516B3
0x180051672  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051678  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005167f  mov     rcx, rax
0x180051682  test    rax, rax
0x180051685  jz      short loc_1800516A5
0x180051687  mov     rax, [rax]
0x18005168a  mov     edx, 7F0h
0x18005168f  mov     rax, [rax+8]
0x180051693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051698  test    eax, eax
0x18005169a  jz      short loc_1800516A5
0x18005169c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800516a3  jmp     short loc_1800516B3
0x1800516a5  lea     rcx, qword_1800D6F70; this
0x1800516ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800516b3  cmp     byte ptr [rcx+8], 0
0x1800516b7  jz      loc_1800518CC
0x1800516bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800516c2  cmp     [rax+7CCh], ebx
0x1800516c8  jz      loc_1800518CC
0x1800516ce  mov     r8d, 44h ; 'D'
0x1800516d4  jmp     loc_1800518BA
0x1800516d9  cmp     word ptr [rdi], 41h ; 'A'
0x1800516dd  jnz     loc_180051777
0x1800516e3  mov     rax, [rax]
0x1800516e6  xor     r9d, r9d
0x1800516e9  mov     r8d, [rdi+8]
0x1800516ed  mov     rdx, [rdi+10h]
0x1800516f1  mov     rax, [rax+20h]
0x1800516f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516fa  mov     ebx, eax
0x1800516fc  test    eax, eax
0x1800516fe  jns     loc_180051815
0x180051704  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005170b  test    rcx, rcx
0x18005170e  jnz     short loc_180051751
0x180051710  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051716  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005171d  mov     rcx, rax
0x180051720  test    rax, rax
0x180051723  jz      short loc_180051743
0x180051725  mov     rax, [rax]
0x180051728  mov     edx, 7F0h
0x18005172d  mov     rax, [rax+8]
0x180051731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051736  test    eax, eax
0x180051738  jz      short loc_180051743
0x18005173a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051741  jmp     short loc_180051751
0x180051743  lea     rcx, qword_1800D6F70; this
0x18005174a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051751  cmp     byte ptr [rcx+8], 0
0x180051755  jz      loc_1800518CC
0x18005175b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051760  cmp     [rax+7CCh], ebx
0x180051766  jz      loc_1800518CC
0x18005176c  mov     r8d, 47h ; 'G'
0x180051772  jmp     loc_1800518BA
0x180051777  mov     eax, 1011h
0x18005177c  cmp     [rdi], ax
0x18005177f  jnz     loc_180051831
0x180051785  mov     rax, [rcx]
0x180051788  xor     r9d, r9d
0x18005178b  mov     r8d, [rdi+8]
0x18005178f  mov     rdx, [rdi+10h]
0x180051793  mov     rax, [rax+20h]
0x180051797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005179c  mov     ebx, eax
0x18005179e  test    eax, eax
0x1800517a0  jns     short loc_180051815
0x1800517a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800517a9  test    rcx, rcx
0x1800517ac  jnz     short loc_1800517EF
0x1800517ae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800517b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800517bb  mov     rcx, rax
0x1800517be  test    rax, rax
0x1800517c1  jz      short loc_1800517E1
0x1800517c3  mov     rax, [rax]
0x1800517c6  mov     edx, 7F0h
0x1800517cb  mov     rax, [rax+8]
0x1800517cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517d4  test    eax, eax
0x1800517d6  jz      short loc_1800517E1
0x1800517d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800517df  jmp     short loc_1800517EF
0x1800517e1  lea     rcx, qword_1800D6F70; this
0x1800517e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800517ef  cmp     byte ptr [rcx+8], 0
0x1800517f3  jz      loc_1800518CC
0x1800517f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800517fe  cmp     [rax+7CCh], ebx
0x180051804  jz      loc_1800518CC
0x18005180a  mov     r8d, 4Dh ; 'M'
0x180051810  jmp     loc_1800518BA
0x180051815  mov     rcx, qword ptr [rbp+pvar+8]
0x180051819  xor     r9d, r9d
0x18005181c  mov     rdx, [rbp+arg_18]
0x180051820  xor     r8d, r8d
0x180051823  mov     rax, [rcx]
0x180051826  mov     rax, [rax+28h]
0x18005182a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005182f  mov     bl, 1
0x180051831  mov     rcx, [r14+18h]
0x180051835  lea     r8, [rbp+pvar]
0x180051839  test    bl, bl
0x18005183b  mov     rdx, rsi
0x18005183e  cmovz   r8, rdi
0x180051842  mov     rax, [rcx]
0x180051845  mov     rax, [rax+30h]
0x180051849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005184e  mov     ebx, eax
0x180051850  test    eax, eax
0x180051852  jns     short loc_1800518CC
0x180051854  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005185b  test    rcx, rcx
0x18005185e  jnz     short loc_1800518A1
0x180051860  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051866  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005186d  mov     rcx, rax
0x180051870  test    rax, rax
0x180051873  jz      short loc_180051893
0x180051875  mov     rax, [rax]
0x180051878  mov     edx, 7F0h
0x18005187d  mov     rax, [rax+8]
0x180051881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051886  test    eax, eax
0x180051888  jz      short loc_180051893
0x18005188a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051891  jmp     short loc_1800518A1
0x180051893  lea     rcx, qword_1800D6F70; this
0x18005189a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800518a1  cmp     byte ptr [rcx+8], 0
0x1800518a5  jz      short loc_1800518CC
0x1800518a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800518ac  cmp     [rax+7CCh], ebx
0x1800518b2  jz      short loc_1800518CC
0x1800518b4  mov     r8d, 53h ; 'S'; int
0x1800518ba  mov     r9d, ebx; int
0x1800518bd  lea     rdx, aCmfstreamingpr; "CMFStreamingPropHandler::InsertProperty"
0x1800518c4  mov     rcx, rax; this
0x1800518c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800518cc  lea     rcx, [rbp+pvar]; pvar
0x1800518d0  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800518d5  mov     rsi, [rsp+50h+arg_8]
0x1800518da  mov     eax, ebx
0x1800518dc  mov     rbx, [rsp+50h+arg_0]
0x1800518e1  add     rsp, 50h
0x1800518e5  pop     r14
0x1800518e7  pop     rdi
0x1800518e8  pop     rbp
0x1800518e9  retn
```
