# CASFReaderCallback::AllocateForOutput(ulong,ulong,INSSBuffer * *,void *)

- ea: `0x1800083d0`
- end: `0x1800085cd`
- name: `?AllocateForOutput@CASFReaderCallback@@UEAAJKKPEAPEAUINSSBuffer@@PEAX@Z`
- size: `509`
- prototype: `__int64 __fastcall(CASFReaderCallback *this, int, unsigned int, struct INSSBuffer **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001020`
- `0x180001460`
- `0x180007104`
- `0x1800071e8`
- `0x180007210`
- `0x180007e14`
- `0x1800083d0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReaderCallback::AllocateForOutput(
        CASFReaderCallback *this,
        int a2,
        unsigned int a3,
        struct INSSBuffer **a4)
{
  __int64 v4; // rcx
  __int64 v8; // rcx
  __int64 v9; // rbx
  int v10; // edi
  int v11; // eax
  struct IMediaSample *v12; // rcx
  CWMReadSample *v13; // rax
  struct INSSBuffer *v14; // rax
  struct _AMMediaType *pv; // [rsp+30h] [rbp-51h] BYREF
  struct IMediaSample *v16; // [rsp+38h] [rbp-49h] BYREF
  struct _AMMediaType v17; // [rsp+40h] [rbp-41h] BYREF

  v4 = *((_QWORD *)this + 1);
  if ( !*(_DWORD *)(v4 + 448) )
    return 2147500033LL;
  v8 = *(_QWORD *)(v4 + 280);
  if ( !v8 )
    return 2147500037LL;
  do
  {
    v9 = *(_QWORD *)(v8 + 16);
    if ( *(_DWORD *)(v9 + 304) == a2 )
      break;
    v8 = *(_QWORD *)(v8 + 8);
  }
  while ( v8 );
  if ( !*(_QWORD *)(v9 + 48) )
    return 2147500037LL;
  v16 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, struct IMediaSample **, _QWORD, _QWORD, _DWORD))(**(_QWORD **)(v9 + 216)
                                                                                          + 56LL))(
          *(_QWORD *)(v9 + 216),
          &v16,
          0,
          0,
          0);
  if ( v10 < 0 )
    goto LABEL_21;
  pv = 0;
  ((void (__fastcall *)(struct IMediaSample *, struct _AMMediaType **))v16->lpVtbl->GetMediaType)(v16, &pv);
  if ( pv )
  {
    CopyMediaType(&v17, pv);
    (*(void (__fastcall **)(__int64, struct _AMMediaType *))(*(_QWORD *)v9 + 72LL))(v9, &v17);
    DeleteMediaType(pv);
    FreeMediaType(&v17);
    if ( v16 )
      ((void (__fastcall *)(struct IMediaSample *))v16->lpVtbl->Release)(v16);
    return 3222077505LL;
  }
  v11 = ((__int64 (__fastcall *)(struct IMediaSample *))v16->lpVtbl->GetSize)(v16);
  v12 = v16;
  if ( v11 < 0 )
    goto LABEL_15;
  ((void (__fastcall *)(struct IMediaSample *))v16->lpVtbl->GetSize)(v16);
  if ( ((unsigned int (__fastcall *)(struct IMediaSample *))v16->lpVtbl->GetSize)(v16) < a3 )
  {
    v12 = v16;
LABEL_15:
    if ( v12 )
      ((void (__fastcall *)(struct IMediaSample *))v12->lpVtbl->Release)(v12);
    return 2147549183LL;
  }
  v13 = (CWMReadSample *)operator new(0x50u);
  if ( !v13 )
  {
    *a4 = 0;
    goto LABEL_25;
  }
  v14 = (struct INSSBuffer *)CWMReadSample::CWMReadSample(v13, v16);
  *a4 = v14;
  if ( !v14 )
  {
LABEL_25:
    v10 = -2147024882;
    goto LABEL_21;
  }
  ((void (__fastcall *)(struct INSSBuffer *))v14->lpVtbl->AddRef)(v14);
  ((void (__fastcall *)(struct IMediaSample *, _QWORD))v16->lpVtbl->SetActualDataLength)(v16, a3);
LABEL_21:
  if ( v16 )
    ((void (__fastcall *)(struct IMediaSample *))v16->lpVtbl->Release)(v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800083d0  push    rbp
0x1800083d2  push    rbx
0x1800083d3  push    rsi
0x1800083d4  push    rdi
0x1800083d5  push    r14
0x1800083d7  lea     rbp, [rsp-2Fh]
0x1800083dc  sub     rsp, 0B0h
0x1800083e3  mov     rax, cs:__security_cookie
0x1800083ea  xor     rax, rsp
0x1800083ed  mov     [rbp+4Fh+var_30], rax
0x1800083f1  mov     rcx, [rcx+8]
0x1800083f5  mov     rsi, r9
0x1800083f8  mov     r14d, r8d
0x1800083fb  cmp     dword ptr [rcx+1C0h], 0
0x180008402  jnz     short loc_18000840E
0x180008404  mov     eax, 80004001h
0x180008409  jmp     loc_1800085B3
0x18000840e  mov     rcx, [rcx+118h]
0x180008415  test    rcx, rcx
0x180008418  jz      loc_1800085AE
0x18000841e  mov     rbx, [rcx+10h]
0x180008422  cmp     [rbx+130h], edx
0x180008428  jz      short loc_180008436
0x18000842a  mov     rax, [rcx+8]
0x18000842e  mov     rcx, rax
0x180008431  test    rax, rax
0x180008434  jnz     short loc_18000841E
0x180008436  cmp     qword ptr [rbx+30h], 0
0x18000843b  jz      loc_1800085AE
0x180008441  mov     [rbp+4Fh+var_98], 0
0x180008449  lea     rdx, [rbp+4Fh+var_98]
0x18000844d  mov     rcx, [rbx+0D8h]
0x180008454  xor     r9d, r9d
0x180008457  xor     r8d, r8d
0x18000845a  mov     [rsp+0D0h+var_B0], 0
0x180008462  mov     rax, [rcx]
0x180008465  mov     rax, [rax+38h]
0x180008469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846e  mov     edi, eax
0x180008470  test    eax, eax
0x180008472  js      loc_180008587
0x180008478  mov     rcx, [rbp+4Fh+var_98]
0x18000847c  mov     [rbp+4Fh+pv], 0
0x180008484  mov     rdx, [rcx]
0x180008487  mov     rax, [rdx+68h]
0x18000848b  lea     rdx, [rbp+4Fh+pv]
0x18000848f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008494  mov     rdx, [rbp+4Fh+pv]; struct _AMMediaType *
0x180008498  test    rdx, rdx
0x18000849b  jz      short loc_1800084EA
0x18000849d  lea     rcx, [rbp+4Fh+var_90]; struct _AMMediaType *
0x1800084a1  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x1800084a6  mov     rax, [rbx]
0x1800084a9  lea     rdx, [rbp+4Fh+var_90]
0x1800084ad  mov     rcx, rbx
0x1800084b0  mov     rax, [rax+48h]
0x1800084b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084b9  mov     rcx, [rbp+4Fh+pv]; pv
0x1800084bd  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1800084c2  lea     rcx, [rbp+4Fh+var_90]; struct _AMMediaType *
0x1800084c6  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800084cb  mov     rcx, [rbp+4Fh+var_98]
0x1800084cf  test    rcx, rcx
0x1800084d2  jz      short loc_1800084E0
0x1800084d4  mov     rax, [rcx]
0x1800084d7  mov     rax, [rax+10h]
0x1800084db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e0  mov     eax, 0C00D0041h
0x1800084e5  jmp     loc_1800085B3
0x1800084ea  mov     rcx, [rbp+4Fh+var_98]
0x1800084ee  mov     rax, [rcx]
0x1800084f1  mov     rax, [rax+20h]
0x1800084f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084fa  mov     rcx, [rbp+4Fh+var_98]
0x1800084fe  test    eax, eax
0x180008500  js      short loc_180008527
0x180008502  mov     rax, [rcx]
0x180008505  mov     rax, [rax+20h]
0x180008509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000850e  mov     rcx, [rbp+4Fh+var_98]
0x180008512  mov     rax, [rcx]
0x180008515  mov     rax, [rax+20h]
0x180008519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000851e  cmp     eax, r14d
0x180008521  jnb     short loc_18000853F
0x180008523  mov     rcx, [rbp+4Fh+var_98]
0x180008527  test    rcx, rcx
0x18000852a  jz      short loc_180008538
0x18000852c  mov     rax, [rcx]
0x18000852f  mov     rax, [rax+10h]
0x180008533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008538  mov     eax, 8000FFFFh
0x18000853d  jmp     short loc_1800085B3
0x18000853f  mov     ecx, 50h ; 'P'; Size
0x180008544  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008549  test    rax, rax
0x18000854c  jz      short loc_1800085A0
0x18000854e  mov     rdx, [rbp+4Fh+var_98]; struct IMediaSample *
0x180008552  mov     rcx, rax; this
0x180008555  call    ??0CWMReadSample@@QEAA@PEAUIMediaSample@@@Z; CWMReadSample::CWMReadSample(IMediaSample *)
0x18000855a  mov     [rsi], rax
0x18000855d  mov     r8, rax
0x180008560  test    rax, rax
0x180008563  jz      short loc_1800085A7
0x180008565  mov     rcx, [rax]
0x180008568  mov     rax, [rcx+8]
0x18000856c  mov     rcx, r8
0x18000856f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008574  mov     rcx, [rbp+4Fh+var_98]
0x180008578  mov     edx, r14d
0x18000857b  mov     rax, [rcx]
0x18000857e  mov     rax, [rax+60h]
0x180008582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008587  mov     rcx, [rbp+4Fh+var_98]
0x18000858b  test    rcx, rcx
0x18000858e  jz      short loc_18000859C
0x180008590  mov     rax, [rcx]
0x180008593  mov     rax, [rax+10h]
0x180008597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000859c  mov     eax, edi
0x18000859e  jmp     short loc_1800085B3
0x1800085a0  mov     qword ptr [rsi], 0
0x1800085a7  mov     edi, 8007000Eh
0x1800085ac  jmp     short loc_180008587
0x1800085ae  mov     eax, 80004005h
0x1800085b3  mov     rcx, [rbp+4Fh+var_30]
0x1800085b7  xor     rcx, rsp; StackCookie
0x1800085ba  call    __security_check_cookie
0x1800085bf  add     rsp, 0B0h
0x1800085c6  pop     r14
0x1800085c8  pop     rdi
0x1800085c9  pop     rsi
0x1800085ca  pop     rbx
0x1800085cb  pop     rbp
0x1800085cc  retn
```
