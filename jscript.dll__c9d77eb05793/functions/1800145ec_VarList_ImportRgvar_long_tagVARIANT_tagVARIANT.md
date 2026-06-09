# VarList::ImportRgvar(long,tagVARIANT *,tagVARIANT *)

- ea: `0x1800145ec`
- end: `0x180014713`
- name: `?ImportRgvar@VarList@@QEAAJJPEAUtagVARIANT@@0@Z`
- size: `295`
- prototype: `__int64 __fastcall(VarList *__hidden this, int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180032b50`
- `0x180033328`
- `0x1800612d0`

## callees

- `0x180011c70`
- `0x1800145ec`
- `0x18001471c`
- `0x180014740`
- `0x180016650`
- `0x180041d18`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x180014694`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180014694`

## pseudocode

```c
HRESULT __fastcall VarList::ImportRgvar(VarList *this, struct VAR **a2, struct tagVARIANT *a3, struct tagVARIANT *a4)
{
  __int64 v4; // rsi
  unsigned int v8; // r14d
  VarStack *v9; // rcx
  VARIANT **v10; // rdi
  VarStack *VarStack; // rax
  VarStack *v12; // r15
  HRESULT result; // eax
  const VARIANTARG *v14; // rsi

  v4 = (int)a2;
  if ( (int)a2 < 0 )
    return -2147024809;
  v8 = (a4 != 0) + (_DWORD)a2;
  if ( v8 < (unsigned int)a2 )
    return -2147467259;
  v9 = (VarStack *)*((_QWORD *)this + 1);
  v10 = (VARIANT **)((char *)this + 16);
  if ( v9 )
  {
    VarStack::PopMasterSp(v9, a2);
    *((_QWORD *)this + 1) = 0;
    *v10 = 0;
    *((_QWORD *)this + 3) = 0;
  }
  if ( !v8 )
    return 0;
  VarStack = CSession::GetVarStack(*(CSession **)this);
  v12 = VarStack;
  if ( !VarStack )
    return -2147467259;
  result = VarStack::SetMasterSp(VarStack, v8, (struct VAR **)this + 2);
  if ( result < 0 )
  {
    *v10 = 0;
    return result;
  }
  *((_QWORD *)this + 1) = v12;
  if ( a4 )
  {
    result = VarList::ImportVar(this, a4);
    if ( result < 0 )
      return result;
    *((_QWORD *)this + 3) = *v10;
  }
  v14 = &a3[v4];
  do
  {
    result = 0;
    if ( v14 <= a3 )
      break;
    --*v10;
    --v14;
    (*v10)->vt = 0;
    result = VariantCopyInd(*v10, v14);
    if ( result < 0 )
      break;
    result = VAR::Import((VAR *)*v10, *(struct CSession **)this);
  }
  while ( result >= 0 );
  return result;
}

```

## disassembly

```asm
0x1800145ec  push    rbx
0x1800145ee  push    rbp
0x1800145ef  push    rsi
0x1800145f0  push    rdi
0x1800145f1  push    r12
0x1800145f3  push    r14
0x1800145f5  push    r15
0x1800145f7  sub     rsp, 20h
0x1800145fb  movsxd  rsi, edx
0x1800145fe  mov     rbp, r9
0x180014601  mov     r12, r8
0x180014604  mov     rbx, rcx
0x180014607  test    edx, edx
0x180014609  js      loc_1800146F8
0x18001460f  xor     eax, eax
0x180014611  test    r9, r9
0x180014614  setnz   al
0x180014617  lea     r14d, [rax+rsi]
0x18001461b  cmp     r14d, esi
0x18001461e  jb      loc_1800146FF
0x180014624  mov     rcx, [rcx+8]; this
0x180014628  lea     rdi, [rbx+10h]
0x18001462c  test    rcx, rcx
0x18001462f  jnz     loc_1800146BC
0x180014635  test    r14d, r14d
0x180014638  jz      loc_180014706
0x18001463e  mov     rcx, [rbx]; this
0x180014641  call    ?GetVarStack@CSession@@QEAAPEAVVarStack@@XZ; CSession::GetVarStack(void)
0x180014646  mov     r15, rax
0x180014649  test    rax, rax
0x18001464c  jz      loc_1800146FF
0x180014652  mov     r8, rdi; struct VAR **
0x180014655  mov     edx, r14d; int
0x180014658  mov     rcx, rax; this
0x18001465b  call    ?SetMasterSp@VarStack@@QEAAJJPEAPEAVVAR@@@Z; VarStack::SetMasterSp(long,VAR * *)
0x180014660  test    eax, eax
0x180014662  js      loc_18001470A
0x180014668  mov     [rbx+8], r15
0x18001466c  test    rbp, rbp
0x18001466f  jnz     short loc_1800146DD
0x180014671  lea     rcx, [rsi+rsi*2]
0x180014675  lea     rsi, [r12+rcx*8]
0x180014679  xor     eax, eax
0x18001467b  cmp     rsi, r12
0x18001467e  jbe     short loc_1800146AD
0x180014680  add     qword ptr [rdi], 0FFFFFFFFFFFFFFE8h
0x180014684  sub     rsi, 18h
0x180014688  mov     rcx, [rdi]
0x18001468b  mov     rdx, rsi; pvargSrc
0x18001468e  mov     [rcx], ax
0x180014691  mov     rcx, [rdi]; pvarDest
0x180014694  call    cs:__imp_VariantCopyInd
0x18001469a  test    eax, eax
0x18001469c  js      short loc_1800146AD
0x18001469e  mov     rdx, [rbx]; struct CSession *
0x1800146a1  mov     rcx, [rdi]; this
0x1800146a4  call    ?Import@VAR@@QEAAJPEAVCSession@@@Z; VAR::Import(CSession *)
0x1800146a9  test    eax, eax
0x1800146ab  jns     short loc_180014679
0x1800146ad  add     rsp, 20h
0x1800146b1  pop     r15
0x1800146b3  pop     r14
0x1800146b5  pop     r12
0x1800146b7  pop     rdi
0x1800146b8  pop     rsi
0x1800146b9  pop     rbp
0x1800146ba  pop     rbx
0x1800146bb  retn
0x1800146bc  call    ?PopMasterSp@VarStack@@QEAAXPEAPEAVVAR@@@Z; VarStack::PopMasterSp(VAR * *)
0x1800146c1  mov     qword ptr [rbx+8], 0
0x1800146c9  mov     qword ptr [rdi], 0
0x1800146d0  mov     qword ptr [rbx+18h], 0
0x1800146d8  jmp     loc_180014635
0x1800146dd  mov     rdx, rbp; struct tagVARIANT *
0x1800146e0  mov     rcx, rbx; this
0x1800146e3  call    ?ImportVar@VarList@@IEAAJPEAUtagVARIANT@@@Z; VarList::ImportVar(tagVARIANT *)
0x1800146e8  test    eax, eax
0x1800146ea  js      short loc_1800146AD
0x1800146ec  mov     rax, [rdi]
0x1800146ef  mov     [rbx+18h], rax
0x1800146f3  jmp     loc_180014671
0x1800146f8  mov     eax, 80070057h
0x1800146fd  jmp     short loc_1800146AD
0x1800146ff  mov     eax, 80004005h
0x180014704  jmp     short loc_1800146AD
0x180014706  xor     eax, eax
0x180014708  jmp     short loc_1800146AD
0x18001470a  mov     qword ptr [rdi], 0
0x180014711  jmp     short loc_1800146AD
```
