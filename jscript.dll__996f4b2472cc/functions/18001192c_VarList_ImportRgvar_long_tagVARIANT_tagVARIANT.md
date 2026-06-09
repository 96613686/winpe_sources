# VarList::ImportRgvar(long,tagVARIANT *,tagVARIANT *)

- ea: `0x18001192c`
- end: `0x180011a5a`
- name: `?ImportRgvar@VarList@@QEAAJJPEAUtagVARIANT@@0@Z`
- size: `302`
- prototype: `int __fastcall(VarList *this, struct VAR **, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180002ba8`
- `0x180013574`
- `0x1800624f0`

## callees

- `0x18000eea4`
- `0x18001192c`
- `0x180011a60`
- `0x180011a88`
- `0x1800134b0`
- `0x180043128`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x1800119d4`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800119d4`

## pseudocode

```c
int __fastcall VarList::ImportRgvar(VarList *this, struct VAR **a2, struct tagVARIANT *a3, struct tagVARIANT *a4)
{
  __int64 v4; // rsi
  unsigned int v8; // r14d
  VarStack *v9; // rcx
  VARIANT **v10; // rdi
  VarStack *VarStack; // rax
  VarStack *v12; // r15
  int result; // eax
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
    result = VAR::Import(*v10, *(struct CSession **)this);
  }
  while ( result >= 0 );
  return result;
}

```

## disassembly

```asm
0x18001192c  push    rbx
0x18001192e  push    rbp
0x18001192f  push    rsi
0x180011930  push    rdi
0x180011931  push    r12
0x180011933  push    r14
0x180011935  push    r15
0x180011937  sub     rsp, 20h
0x18001193b  movsxd  rsi, edx
0x18001193e  mov     rbp, r9
0x180011941  mov     r12, r8
0x180011944  mov     rbx, rcx
0x180011947  test    edx, edx
0x180011949  js      loc_180011A3F
0x18001194f  xor     eax, eax
0x180011951  test    r9, r9
0x180011954  setnz   al
0x180011957  lea     r14d, [rax+rsi]
0x18001195b  cmp     r14d, esi
0x18001195e  jb      loc_180011A46
0x180011964  mov     rcx, [rcx+8]; this
0x180011968  lea     rdi, [rbx+10h]
0x18001196c  test    rcx, rcx
0x18001196f  jnz     loc_180011A03
0x180011975  test    r14d, r14d
0x180011978  jz      loc_180011A4D
0x18001197e  mov     rcx, [rbx]; this
0x180011981  call    ?GetVarStack@CSession@@QEAAPEAVVarStack@@XZ; CSession::GetVarStack(void)
0x180011986  mov     r15, rax
0x180011989  test    rax, rax
0x18001198c  jz      loc_180011A46
0x180011992  mov     r8, rdi; struct VAR **
0x180011995  mov     edx, r14d; int
0x180011998  mov     rcx, rax; this
0x18001199b  call    ?SetMasterSp@VarStack@@QEAAJJPEAPEAVVAR@@@Z; VarStack::SetMasterSp(long,VAR * *)
0x1800119a0  test    eax, eax
0x1800119a2  js      loc_180011A51
0x1800119a8  mov     [rbx+8], r15
0x1800119ac  test    rbp, rbp
0x1800119af  jnz     short loc_180011A24
0x1800119b1  lea     rcx, [rsi+rsi*2]
0x1800119b5  lea     rsi, [r12+rcx*8]
0x1800119b9  xor     eax, eax
0x1800119bb  cmp     rsi, r12
0x1800119be  jbe     short loc_1800119F3
0x1800119c0  add     qword ptr [rdi], 0FFFFFFFFFFFFFFE8h
0x1800119c4  sub     rsi, 18h
0x1800119c8  mov     rcx, [rdi]
0x1800119cb  mov     rdx, rsi; pvargSrc
0x1800119ce  mov     [rcx], ax
0x1800119d1  mov     rcx, [rdi]; pvarDest
0x1800119d4  call    cs:__imp_VariantCopyInd
0x1800119db  nop     dword ptr [rax+rax+00h]
0x1800119e0  test    eax, eax
0x1800119e2  js      short loc_1800119F3
0x1800119e4  mov     rdx, [rbx]; struct CSession *
0x1800119e7  mov     rcx, [rdi]; this
0x1800119ea  call    ?Import@VAR@@QEAAJPEAVCSession@@@Z; VAR::Import(CSession *)
0x1800119ef  test    eax, eax
0x1800119f1  jns     short loc_1800119B9
0x1800119f3  add     rsp, 20h
0x1800119f7  pop     r15
0x1800119f9  pop     r14
0x1800119fb  pop     r12
0x1800119fd  pop     rdi
0x1800119fe  pop     rsi
0x1800119ff  pop     rbp
0x180011a00  pop     rbx
0x180011a01  retn
0x180011a03  call    ?PopMasterSp@VarStack@@QEAAXPEAPEAVVAR@@@Z; VarStack::PopMasterSp(VAR * *)
0x180011a08  mov     qword ptr [rbx+8], 0
0x180011a10  mov     qword ptr [rdi], 0
0x180011a17  mov     qword ptr [rbx+18h], 0
0x180011a1f  jmp     loc_180011975
0x180011a24  mov     rdx, rbp; struct tagVARIANT *
0x180011a27  mov     rcx, rbx; this
0x180011a2a  call    ?ImportVar@VarList@@IEAAJPEAUtagVARIANT@@@Z; VarList::ImportVar(tagVARIANT *)
0x180011a2f  test    eax, eax
0x180011a31  js      short loc_1800119F3
0x180011a33  mov     rax, [rdi]
0x180011a36  mov     [rbx+18h], rax
0x180011a3a  jmp     loc_1800119B1
0x180011a3f  mov     eax, 80070057h
0x180011a44  jmp     short loc_1800119F3
0x180011a46  mov     eax, 80004005h
0x180011a4b  jmp     short loc_1800119F3
0x180011a4d  xor     eax, eax
0x180011a4f  jmp     short loc_1800119F3
0x180011a51  mov     qword ptr [rdi], 0
0x180011a58  jmp     short loc_1800119F3
```
