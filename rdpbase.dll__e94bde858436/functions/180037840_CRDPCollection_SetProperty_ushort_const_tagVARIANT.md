# CRDPCollection::SetProperty(ushort const *,tagVARIANT *)

- ea: `0x180037840`
- end: `0x180037a68`
- name: `?SetProperty@CRDPCollection@@UEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `552`
- prototype: `int(CRDPCollection *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180037840`
- `0x180037a70`
- `0x1800787d4`
- `0x180078820`
- `0x1800795c4`
- `0x180162010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800379f9`
- `OLEAUT32!__imp_VariantInit` at `0x1800379f9`
- `OLEAUT32!__imp_VariantCopy` at `0x1800378b0`
- `OLEAUT32!__imp_VariantCopy` at `0x1800378c0`
- `OLEAUT32!__imp_VariantCopy` at `0x1800378b0`
- `OLEAUT32!__imp_VariantCopy` at `0x1800378c0`

## pseudocode

```c
__int64 __fastcall CRDPCollection::SetProperty(CRDPCollection *this, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  const unsigned __int16 *v4; // r14
  char *v6; // r12
  unsigned int v7; // esi
  HRESULT v8; // ebx
  __int64 v9; // rax
  CRDPAPICollectionImplItem *v10; // rbx
  _WORD *v11; // rdx
  _WORD *v13; // rcx
  void *v14; // rcx
  unsigned int v15; // edx
  unsigned __int64 v16; // rsi
  _WORD *v17; // rax
  _WORD *v18; // r15
  __int64 v19; // rax
  VARIANTARG *v20; // rax
  VARIANTARG *v21; // rdi
  __int64 v22; // rax

  v4 = a2;
  if ( !a2 )
    return (unsigned int)-2147467261;
  v6 = (char *)this + 72;
  v7 = 0;
  v8 = 1;
  while ( 1 )
  {
    if ( v7 >= *((_DWORD *)this + 23) )
    {
      if ( !a3 )
        return (unsigned int)v8;
      v20 = (VARIANTARG *)operator new(0x20u);
      v21 = v20;
      if ( !v20 )
        return (unsigned int)-2147024882;
      *(_QWORD *)&v20[1].vt = 0;
      VariantInit(v20);
      if ( !*v4 )
      {
        v8 = -2147024809;
        goto LABEL_17;
      }
      v22 = -1;
      do
        ++v22;
      while ( v4[v22] );
      v16 = (unsigned int)(v22 + 1);
      v17 = operator new(saturated_mul(v16, 2u));
      v18 = v17;
      if ( !v17 )
      {
        v8 = -2147024882;
        goto LABEL_16;
      }
      if ( v16 )
      {
        if ( v16 > 0x7FFFFFFF )
        {
          *v17 = 0;
          v8 = -2147024809;
          goto LABEL_15;
        }
        v19 = 2147483646;
        v11 = v18;
        do
        {
          if ( !v19 )
            break;
          if ( !*v4 )
            break;
          *v11++ = *v4++;
          --v19;
          --v16;
        }
        while ( v16 );
        v13 = v11 - 1;
        if ( v16 )
          v13 = v11;
        v8 = v16 == 0 ? 0x8007007A : 0;
        *v13 = 0;
      }
      else
      {
        v8 = -2147024809;
      }
      if ( v8 >= 0 )
      {
        v14 = *(void **)&v21[1].vt;
        if ( v14 )
          operator delete(v14);
        *(_QWORD *)&v21[1].vt = v18;
LABEL_16:
        if ( v8 >= 0 )
        {
          v8 = VariantCopy(v21, a3);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(char *, VARIANTARG *))(*(_QWORD *)v6 + 8LL))(v6, v21);
            if ( v8 >= 0 )
              return (unsigned int)v8;
          }
        }
LABEL_17:
        CRDPAPICollectionImplItem::`scalar deleting destructor'((CRDPAPICollectionImplItem *)v21, (unsigned int)v11);
        return (unsigned int)v8;
      }
LABEL_15:
      operator delete(v18);
      goto LABEL_16;
    }
    if ( !wcsicmp(v4, *(const wchar_t **)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v7) + 24LL)) )
      break;
    ++v7;
  }
  v9 = *((_QWORD *)this + 10);
  v10 = *(CRDPAPICollectionImplItem **)(v9 + 8LL * v7);
  if ( a3 )
  {
    return (unsigned int)VariantCopy(*(VARIANTARG **)(v9 + 8LL * v7), a3);
  }
  else
  {
    (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v6 + 16LL))(v6, *(_QWORD *)(v9 + 8LL * v7));
    if ( v10 )
      CRDPAPICollectionImplItem::`scalar deleting destructor'(v10, v15);
    return 0;
  }
}

```

## disassembly

```asm
0x180037840  push    rbx
0x180037842  push    rbp
0x180037843  push    rsi
0x180037844  push    rdi
0x180037845  push    r12
0x180037847  push    r13
0x180037849  push    r14
0x18003784b  push    r15
0x18003784d  sub     rsp, 28h
0x180037851  xor     r13d, r13d
0x180037854  mov     rbp, r8
0x180037857  mov     r14, rdx
0x18003785a  mov     rdi, rcx
0x18003785d  test    rdx, rdx
0x180037860  jz      loc_180037A5E
0x180037866  lea     r12, [rcx+48h]
0x18003786a  mov     esi, r13d
0x18003786d  lea     ebx, [r13+1]
0x180037871  cmp     esi, [rdi+5Ch]
0x180037874  jnb     loc_1800379D7
0x18003787a  mov     rax, [rdi+50h]
0x18003787e  mov     rcx, r14; String1
0x180037881  mov     r15d, esi
0x180037884  mov     rdx, [rax+r15*8]
0x180037888  mov     rdx, [rdx+18h]; String2
0x18003788c  call    _wcsicmp
0x180037891  test    eax, eax
0x180037893  jz      short loc_180037899
0x180037895  add     esi, ebx
0x180037897  jmp     short loc_180037871
0x180037899  mov     rax, [rdi+50h]
0x18003789d  mov     rbx, [rax+r15*8]
0x1800378a1  test    rbp, rbp
0x1800378a4  jz      loc_180037941
0x1800378aa  mov     rdx, rbp; pvargSrc
0x1800378ad  mov     rcx, rbx; pvargDest
0x1800378b0  call    cs:__imp_VariantCopy
0x1800378b6  mov     ebx, eax
0x1800378b8  jmp     short loc_1800378E5
0x1800378ba  mov     rdx, rbp; pvargSrc
0x1800378bd  mov     rcx, rdi; pvargDest
0x1800378c0  call    cs:__imp_VariantCopy
0x1800378c6  mov     ebx, eax
0x1800378c8  test    eax, eax
0x1800378ca  js      short loc_180037924
0x1800378cc  mov     rax, [r12]
0x1800378d0  mov     rdx, rdi
0x1800378d3  mov     rcx, r12
0x1800378d6  mov     rax, [rax+8]
0x1800378da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378df  mov     ebx, eax
0x1800378e1  test    eax, eax
0x1800378e3  js      short loc_180037924
0x1800378e5  mov     eax, ebx
0x1800378e7  add     rsp, 28h
0x1800378eb  pop     r15
0x1800378ed  pop     r14
0x1800378ef  pop     r13
0x1800378f1  pop     r12
0x1800378f3  pop     rdi
0x1800378f4  pop     rsi
0x1800378f5  pop     rbp
0x1800378f6  pop     rbx
0x1800378f7  retn
0x1800378f8  test    rsi, rsi
0x1800378fb  lea     rcx, [rdx-2]
0x1800378ff  cmovnz  rcx, rdx
0x180037903  neg     rsi
0x180037906  sbb     ebx, ebx
0x180037908  not     ebx
0x18003790a  and     ebx, 8007007Ah
0x180037910  mov     [rcx], r13w
0x180037914  test    ebx, ebx
0x180037916  jns     short loc_18003792E
0x180037918  mov     rcx, r15; Block
0x18003791b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037920  test    ebx, ebx
0x180037922  jns     short loc_1800378BA
0x180037924  mov     rcx, rdi; this
0x180037927  call    ??_GCRDPAPICollectionImplItem@@QEAAPEAXI@Z; CRDPAPICollectionImplItem::`scalar deleting destructor'(uint)
0x18003792c  jmp     short loc_1800378E5
0x18003792e  mov     rcx, [rdi+18h]; Block
0x180037932  test    rcx, rcx
0x180037935  jnz     loc_180037A4A
0x18003793b  mov     [rdi+18h], r15
0x18003793f  jmp     short loc_180037920
0x180037941  mov     rax, [r12]
0x180037945  mov     rdx, rbx
0x180037948  mov     rcx, r12
0x18003794b  mov     rax, [rax+10h]
0x18003794f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037954  test    rbx, rbx
0x180037957  jnz     loc_180037A25
0x18003795d  mov     ebx, r13d
0x180037960  jmp     short loc_1800378E5
0x180037962  lea     esi, [rax+1]
0x180037965  mov     eax, 2
0x18003796a  mul     rsi
0x18003796d  cmovb   rax, rcx
0x180037971  mov     rcx, rax; Size
0x180037974  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037979  mov     r15, rax
0x18003797c  test    rax, rax
0x18003797f  jz      short loc_1800379CD
0x180037981  test    rsi, rsi
0x180037984  jz      loc_180037A40
0x18003798a  cmp     rsi, 7FFFFFFFh
0x180037991  ja      loc_180037A32
0x180037997  mov     eax, 7FFFFFFEh
0x18003799c  mov     rdx, r15
0x18003799f  test    rax, rax
0x1800379a2  jz      loc_1800378F8
0x1800379a8  movzx   ecx, word ptr [r14]
0x1800379ac  test    cx, cx
0x1800379af  jz      loc_1800378F8
0x1800379b5  mov     [rdx], cx
0x1800379b8  add     r14, 2
0x1800379bc  add     rdx, 2
0x1800379c0  sub     rax, rbx
0x1800379c3  sub     rsi, rbx
0x1800379c6  jnz     short loc_18003799F
0x1800379c8  jmp     loc_1800378F8
0x1800379cd  mov     ebx, 8007000Eh
0x1800379d2  jmp     loc_180037920
0x1800379d7  test    rbp, rbp
0x1800379da  jz      loc_1800378E5
0x1800379e0  mov     ecx, 20h ; ' '; Size
0x1800379e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800379ea  mov     rdi, rax
0x1800379ed  test    rax, rax
0x1800379f0  jz      short loc_180037A1B
0x1800379f2  mov     rcx, rax; pvarg
0x1800379f5  mov     [rax+18h], r13
0x1800379f9  call    cs:__imp_VariantInit
0x1800379ff  cmp     [r14], r13w
0x180037a03  jz      short loc_180037A54
0x180037a05  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180037a09  mov     rax, rcx
0x180037a0c  inc     rax
0x180037a0f  cmp     [r14+rax*2], r13w
0x180037a14  jnz     short loc_180037A0C
0x180037a16  jmp     loc_180037962
0x180037a1b  mov     ebx, 8007000Eh
0x180037a20  jmp     loc_1800378E5
0x180037a25  mov     rcx, rbx; this
0x180037a28  call    ??_GCRDPAPICollectionImplItem@@QEAAPEAXI@Z; CRDPAPICollectionImplItem::`scalar deleting destructor'(uint)
0x180037a2d  jmp     loc_18003795D
0x180037a32  mov     [rax], r13w
0x180037a36  mov     ebx, 80070057h
0x180037a3b  jmp     loc_180037918
0x180037a40  mov     ebx, 80070057h
0x180037a45  jmp     loc_180037914
0x180037a4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037a4f  jmp     loc_18003793B
0x180037a54  mov     ebx, 80070057h
0x180037a59  jmp     loc_180037924
0x180037a5e  mov     ebx, 80004003h
0x180037a63  jmp     loc_1800378E5
```
