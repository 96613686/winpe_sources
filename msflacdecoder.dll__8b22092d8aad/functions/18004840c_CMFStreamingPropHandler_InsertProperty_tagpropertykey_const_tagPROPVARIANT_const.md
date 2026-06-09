# CMFStreamingPropHandler::InsertProperty(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x18004840c`
- end: `0x18004870a`
- name: `?InsertProperty@CMFStreamingPropHandler@@QEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(CMFStreamingPropHandler *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800223b8`
- `0x180046384`
- `0x180046a04`
- `0x180047278`
- `0x1800475c8`
- `0x180047dcc`

## callees

- `0x180020c54`
- `0x180031bdc`
- `0x180034a04`
- `0x180039e60`
- `0x18004840c`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048492`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048530`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800485ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048680`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048492`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048530`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800485ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048680`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18004846f`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18004846f`

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
  __int64 *v10; // rcx
  int v11; // ebx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v14; // r8d
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  PROPVARIANT *p_pvar; // r8
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  PROPVARIANT pvar; // [rsp+30h] [rbp-20h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  v6 = 0;
  if ( !(unsigned int)operator==(a2, &PKEY_ThumbnailStream) || *v7 == 66 )
  {
LABEL_33:
    p_pvar = &pvar;
    if ( !v6 )
      p_pvar = a3;
    v11 = (*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(**((_QWORD **)this + 3)
                                                                                           + 48LL))(
            *((_QWORD *)this + 3),
            a2,
            p_pvar);
    if ( v11 < 0 )
    {
      v23 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        {
          v14 = 83;
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
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
      {
        v14 = 68;
LABEL_44:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFStreamingPropHandler::InsertProperty", v14, v11);
        goto LABEL_45;
      }
    }
    goto LABEL_45;
  }
  if ( a3->vt != 65 )
  {
    if ( a3->vt != 4113 )
      goto LABEL_33;
    v11 = ((__int64 (__fastcall *)(IStream *, BYTE *, _QWORD, _QWORD))v8->lpVtbl->Write)(
            v8,
            a3->bstrblobVal.pData,
            a3->ulVal,
            0);
    if ( v11 < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        {
          v14 = 77;
          goto LABEL_44;
        }
      }
      goto LABEL_45;
    }
    goto LABEL_32;
  }
  v11 = ((__int64 (__fastcall *)(IStream *, BYTE *, _QWORD, _QWORD))v8->lpVtbl->Write)(
          v8,
          a3->bstrblobVal.pData,
          a3->ulVal,
          0);
  if ( v11 >= 0 )
  {
LABEL_32:
    (*((void (__fastcall **)(LARGE_INTEGER, _QWORD, _QWORD, _QWORD))*pvar.pbstrVal + 5))(pvar.hVal, 0, 0, 0);
    v6 = 1;
    goto LABEL_33;
  }
  v16 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
    {
      v14 = 71;
      goto LABEL_44;
    }
  }
LABEL_45:
  CMFPropVariant::Clear(&pvar);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004840c  mov     [rsp-18h+arg_0], rbx
0x180048411  mov     [rsp-18h+arg_8], rsi
0x180048416  push    rbp
0x180048417  push    rdi
0x180048418  push    r14
0x18004841a  mov     rbp, rsp
0x18004841d  sub     rsp, 50h
0x180048421  mov     rsi, rdx
0x180048424  xor     eax, eax
0x180048426  mov     r14, rcx
0x180048429  mov     qword ptr [rbp+pvar+10h], rax
0x18004842d  xorps   xmm0, xmm0
0x180048430  lea     rdx, PKEY_ThumbnailStream
0x180048437  mov     rcx, rsi
0x18004843a  mov     rdi, r8
0x18004843d  movups  xmmword ptr [rbp+pvar], xmm0
0x180048441  xor     bl, bl
0x180048443  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180048448  test    eax, eax
0x18004844a  jz      loc_180048651
0x180048450  mov     ecx, 42h ; 'B'
0x180048455  cmp     [r8], cx
0x180048459  jz      loc_180048651
0x18004845f  mov     word ptr [rbp+pvar], cx
0x180048463  xor     edx, edx; cbInit
0x180048465  xor     ecx, ecx; pInit
0x180048467  mov     [rbp+arg_18], 0
0x18004846f  call    cs:__imp_SHCreateMemStream
0x180048475  mov     qword ptr [rbp+pvar+8], rax
0x180048479  mov     rcx, rax
0x18004847c  test    rax, rax
0x18004847f  jnz     short loc_1800484F9
0x180048481  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048488  mov     ebx, 8007000Eh
0x18004848d  test    rcx, rcx
0x180048490  jnz     short loc_1800484D3
0x180048492  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048498  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004849f  mov     rcx, rax
0x1800484a2  test    rax, rax
0x1800484a5  jz      short loc_1800484C5
0x1800484a7  mov     rax, [rax]
0x1800484aa  mov     edx, 7F0h
0x1800484af  mov     rax, [rax+8]
0x1800484b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484b8  test    eax, eax
0x1800484ba  jz      short loc_1800484C5
0x1800484bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800484c3  jmp     short loc_1800484D3
0x1800484c5  lea     rcx, qword_18006EB20; this
0x1800484cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800484d3  cmp     byte ptr [rcx+8], 0
0x1800484d7  jz      loc_1800486EC
0x1800484dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800484e2  cmp     [rax+7CCh], ebx
0x1800484e8  jz      loc_1800486EC
0x1800484ee  mov     r8d, 44h ; 'D'
0x1800484f4  jmp     loc_1800486DA
0x1800484f9  cmp     word ptr [rdi], 41h ; 'A'
0x1800484fd  jnz     loc_180048597
0x180048503  mov     rax, [rax]
0x180048506  xor     r9d, r9d
0x180048509  mov     r8d, [rdi+8]
0x18004850d  mov     rdx, [rdi+10h]
0x180048511  mov     rax, [rax+20h]
0x180048515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004851a  mov     ebx, eax
0x18004851c  test    eax, eax
0x18004851e  jns     loc_180048635
0x180048524  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004852b  test    rcx, rcx
0x18004852e  jnz     short loc_180048571
0x180048530  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048536  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004853d  mov     rcx, rax
0x180048540  test    rax, rax
0x180048543  jz      short loc_180048563
0x180048545  mov     rax, [rax]
0x180048548  mov     edx, 7F0h
0x18004854d  mov     rax, [rax+8]
0x180048551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048556  test    eax, eax
0x180048558  jz      short loc_180048563
0x18004855a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048561  jmp     short loc_180048571
0x180048563  lea     rcx, qword_18006EB20; this
0x18004856a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180048571  cmp     byte ptr [rcx+8], 0
0x180048575  jz      loc_1800486EC
0x18004857b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180048580  cmp     [rax+7CCh], ebx
0x180048586  jz      loc_1800486EC
0x18004858c  mov     r8d, 47h ; 'G'
0x180048592  jmp     loc_1800486DA
0x180048597  mov     eax, 1011h
0x18004859c  cmp     [rdi], ax
0x18004859f  jnz     loc_180048651
0x1800485a5  mov     rax, [rcx]
0x1800485a8  xor     r9d, r9d
0x1800485ab  mov     r8d, [rdi+8]
0x1800485af  mov     rdx, [rdi+10h]
0x1800485b3  mov     rax, [rax+20h]
0x1800485b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485bc  mov     ebx, eax
0x1800485be  test    eax, eax
0x1800485c0  jns     short loc_180048635
0x1800485c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800485c9  test    rcx, rcx
0x1800485cc  jnz     short loc_18004860F
0x1800485ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800485d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800485db  mov     rcx, rax
0x1800485de  test    rax, rax
0x1800485e1  jz      short loc_180048601
0x1800485e3  mov     rax, [rax]
0x1800485e6  mov     edx, 7F0h
0x1800485eb  mov     rax, [rax+8]
0x1800485ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485f4  test    eax, eax
0x1800485f6  jz      short loc_180048601
0x1800485f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800485ff  jmp     short loc_18004860F
0x180048601  lea     rcx, qword_18006EB20; this
0x180048608  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004860f  cmp     byte ptr [rcx+8], 0
0x180048613  jz      loc_1800486EC
0x180048619  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004861e  cmp     [rax+7CCh], ebx
0x180048624  jz      loc_1800486EC
0x18004862a  mov     r8d, 4Dh ; 'M'
0x180048630  jmp     loc_1800486DA
0x180048635  mov     rcx, qword ptr [rbp+pvar+8]
0x180048639  xor     r9d, r9d
0x18004863c  mov     rdx, [rbp+arg_18]
0x180048640  xor     r8d, r8d
0x180048643  mov     rax, [rcx]
0x180048646  mov     rax, [rax+28h]
0x18004864a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004864f  mov     bl, 1
0x180048651  mov     rcx, [r14+18h]
0x180048655  lea     r8, [rbp+pvar]
0x180048659  test    bl, bl
0x18004865b  mov     rdx, rsi
0x18004865e  cmovz   r8, rdi
0x180048662  mov     rax, [rcx]
0x180048665  mov     rax, [rax+30h]
0x180048669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004866e  mov     ebx, eax
0x180048670  test    eax, eax
0x180048672  jns     short loc_1800486EC
0x180048674  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004867b  test    rcx, rcx
0x18004867e  jnz     short loc_1800486C1
0x180048680  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048686  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004868d  mov     rcx, rax
0x180048690  test    rax, rax
0x180048693  jz      short loc_1800486B3
0x180048695  mov     rax, [rax]
0x180048698  mov     edx, 7F0h
0x18004869d  mov     rax, [rax+8]
0x1800486a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486a6  test    eax, eax
0x1800486a8  jz      short loc_1800486B3
0x1800486aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800486b1  jmp     short loc_1800486C1
0x1800486b3  lea     rcx, qword_18006EB20; this
0x1800486ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800486c1  cmp     byte ptr [rcx+8], 0
0x1800486c5  jz      short loc_1800486EC
0x1800486c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800486cc  cmp     [rax+7CCh], ebx
0x1800486d2  jz      short loc_1800486EC
0x1800486d4  mov     r8d, 53h ; 'S'; int
0x1800486da  mov     r9d, ebx; int
0x1800486dd  lea     rdx, aCmfstreamingpr; "CMFStreamingPropHandler::InsertProperty"
0x1800486e4  mov     rcx, rax; this
0x1800486e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800486ec  lea     rcx, [rbp+pvar]; pvar
0x1800486f0  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800486f5  mov     rsi, [rsp+50h+arg_8]
0x1800486fa  mov     eax, ebx
0x1800486fc  mov     rbx, [rsp+50h+arg_0]
0x180048701  add     rsp, 50h
0x180048705  pop     r14
0x180048707  pop     rdi
0x180048708  pop     rbp
0x180048709  retn
```
