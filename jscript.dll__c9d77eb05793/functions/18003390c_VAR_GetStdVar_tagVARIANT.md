# VAR::GetStdVar(tagVARIANT *)

- ea: `0x18003390c`
- end: `0x180033abc`
- name: `?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z`
- size: `432`
- prototype: `int(VAR *__hidden this, struct tagVARIANT *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180013350`
- `0x180026230`
- `0x180032b50`
- `0x180033328`
- `0x180062fe8`
- `0x18008a0a0`

## callees

- `0x18000afa4`
- `0x18003390c`
- `0x180033c30`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180033ab1`
- `OLEAUT32!__imp_VariantCopy` at `0x180033ab1`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800339dd`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800339dd`

## pseudocode

```c
int __fastcall VAR::GetStdVar(VAR *this, struct tagVARIANT *a2)
{
  VARIANTARG *v3; // rax
  VARIANTARG *v4; // rdi
  unsigned int vt; // edx
  unsigned int v6; // edx
  LONGLONG llVal; // rcx
  int result; // eax
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // edx
  IRecordInfo *pRecInfo; // xmm1_8
  bool v15; // zf
  VARIANT pvarDest; // [rsp+20h] [rbp-28h] BYREF

  if ( !a2 )
    return -2147024809;
  v3 = (VARIANTARG *)VAR::PvarCutAll(this);
  v4 = v3;
  vt = v3->vt;
  if ( vt > 0xA )
  {
    if ( vt != 11 && vt != 14 && vt != 16 && vt != 17 && vt != 18 && vt != 19 && vt != 22 )
    {
      v15 = vt == 23;
      goto LABEL_36;
    }
LABEL_5:
    if ( (vt & 0x4000) == 0 )
    {
      *(_OWORD *)&a2->vt = *(_OWORD *)&v3->vt;
      a2->pRecInfo = v3->pRecInfo;
      return 0;
    }
    goto LABEL_8;
  }
  if ( vt == 10 || !v3->vt || vt == 1 || vt == 2 || vt == 3 || vt == 4 || vt == 5 || vt == 6 )
    goto LABEL_5;
  v15 = vt == 7;
LABEL_36:
  if ( v15 || (vt & 0x4000) != 0 )
    goto LABEL_5;
LABEL_8:
  v6 = vt - 9;
  if ( !v6 )
    goto LABEL_9;
  v9 = v6 - 120;
  if ( !v9 )
    goto LABEL_9;
  v10 = v9 - 1;
  if ( !v10 )
    goto LABEL_39;
  v11 = v10 - 4;
  if ( !v11 || (v12 = v11 - 1) == 0 )
  {
LABEL_9:
    a2->vt = 9;
    llVal = v3->llVal;
    a2->llVal = llVal;
    if ( llVal )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)llVal + 8LL))(llVal);
    return 0;
  }
  v13 = v12 - 8;
  if ( v13 )
  {
    if ( v13 != 1 )
    {
      pvarDest.vt = 0;
      result = VariantCopyInd(&pvarDest, v3);
      pRecInfo = pvarDest.pRecInfo;
      *(_OWORD *)&a2->vt = *(_OWORD *)&pvarDest.vt;
      a2->pRecInfo = pRecInfo;
      return result;
    }
    goto LABEL_9;
  }
  result = VAR::ConvertASTRtoBSTR((VAR *)v3);
  if ( result >= 0 )
  {
LABEL_39:
    pvarDest.vt = 8;
    pvarDest.llVal = v4->llVal;
    a2->vt = 0;
    return VariantCopy(a2, &pvarDest);
  }
  return result;
}

```

## disassembly

```asm
0x18003390c  mov     [rsp+arg_0], rbx
0x180033911  mov     [rsp+arg_8], rsi
0x180033916  push    rdi
0x180033917  sub     rsp, 40h
0x18003391b  mov     rbx, rdx
0x18003391e  test    rdx, rdx
0x180033921  jz      short loc_18003399D
0x180033923  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x180033928  mov     rdi, rax
0x18003392b  movzx   edx, word ptr [rax]
0x18003392e  cmp     edx, 0Ah
0x180033931  jbe     loc_1800339F8
0x180033937  mov     ecx, edx
0x180033939  sub     ecx, 0Bh
0x18003393c  jz      short loc_180033947
0x18003393e  sub     ecx, 3
0x180033941  jnz     loc_180033A4B
0x180033947  bt      dx, 0Eh
0x18003394c  jb      short loc_180033966
0x18003394e  movups  xmm0, xmmword ptr [rax]
0x180033951  movups  xmmword ptr [rbx], xmm0
0x180033954  movsd   xmm1, qword ptr [rax+10h]
0x180033959  movsd   qword ptr [rbx+10h], xmm1
0x18003395e  jmp     short loc_18003398B
0x180033960  bt      edx, 0Eh
0x180033964  jb      short loc_180033947
0x180033966  mov     eax, 9
0x18003396b  sub     edx, eax
0x18003396d  jnz     short loc_1800339A4
0x18003396f  mov     [rbx], ax
0x180033972  mov     rcx, [rdi+8]
0x180033976  mov     [rbx+8], rcx
0x18003397a  test    rcx, rcx
0x18003397d  jz      short loc_18003398B
0x18003397f  mov     rax, [rcx]
0x180033982  mov     rax, [rax+8]
0x180033986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003398b  xor     eax, eax
0x18003398d  mov     rbx, [rsp+48h+arg_0]
0x180033992  mov     rsi, [rsp+48h+arg_8]
0x180033997  add     rsp, 40h
0x18003399b  pop     rdi
0x18003399c  retn
0x18003399d  mov     eax, 80070057h
0x1800339a2  jmp     short loc_18003398D
0x1800339a4  sub     edx, 78h ; 'x'
0x1800339a7  jz      short loc_18003396F
0x1800339a9  mov     esi, 8
0x1800339ae  sub     edx, 1
0x1800339b1  jz      loc_180033A96
0x1800339b7  sub     edx, 4
0x1800339ba  jz      short loc_18003396F
0x1800339bc  sub     edx, 1
0x1800339bf  jz      short loc_18003396F
0x1800339c1  sub     edx, esi
0x1800339c3  jz      loc_180033A86
0x1800339c9  cmp     edx, 1
0x1800339cc  jz      short loc_18003396F
0x1800339ce  xor     eax, eax
0x1800339d0  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x1800339d5  mov     rdx, rdi; pvargSrc
0x1800339d8  mov     word ptr [rsp+48h+pvarDest], ax
0x1800339dd  call    cs:__imp_VariantCopyInd
0x1800339e3  movups  xmm0, xmmword ptr [rsp+48h+pvarDest]
0x1800339e8  movsd   xmm1, qword ptr [rsp+48h+pvarDest+10h]
0x1800339ee  movups  xmmword ptr [rbx], xmm0
0x1800339f1  movsd   qword ptr [rbx+10h], xmm1
0x1800339f6  jmp     short loc_18003398D
0x1800339f8  jz      loc_180033947
0x1800339fe  mov     r8d, edx
0x180033a01  test    edx, edx
0x180033a03  jz      loc_180033947
0x180033a09  sub     r8d, 1
0x180033a0d  jz      loc_180033947
0x180033a13  sub     r8d, 1
0x180033a17  jz      loc_180033947
0x180033a1d  sub     r8d, 1
0x180033a21  jz      loc_180033947
0x180033a27  sub     r8d, 1
0x180033a2b  jz      loc_180033947
0x180033a31  sub     r8d, 1
0x180033a35  jz      loc_180033947
0x180033a3b  sub     r8d, 1
0x180033a3f  jz      loc_180033947
0x180033a45  cmp     r8d, 1
0x180033a49  jmp     short loc_180033A7B
0x180033a4b  sub     ecx, 2
0x180033a4e  jz      loc_180033947
0x180033a54  sub     ecx, 1
0x180033a57  jz      loc_180033947
0x180033a5d  sub     ecx, 1
0x180033a60  jz      loc_180033947
0x180033a66  sub     ecx, 1
0x180033a69  jz      loc_180033947
0x180033a6f  sub     ecx, 3
0x180033a72  jz      loc_180033947
0x180033a78  cmp     ecx, 1
0x180033a7b  jz      loc_180033947
0x180033a81  jmp     loc_180033960
0x180033a86  mov     rcx, rdi; this
0x180033a89  call    ?ConvertASTRtoBSTR@VAR@@QEAAJXZ; VAR::ConvertASTRtoBSTR(void)
0x180033a8e  test    eax, eax
0x180033a90  js      loc_18003398D
0x180033a96  mov     word ptr [rsp+48h+pvarDest], si
0x180033a9b  lea     rdx, [rsp+48h+pvarDest]; pvargSrc
0x180033aa0  mov     rax, [rdi+8]
0x180033aa4  mov     rcx, rbx; pvargDest
0x180033aa7  mov     qword ptr [rsp+48h+pvarDest+8], rax
0x180033aac  xor     eax, eax
0x180033aae  mov     [rbx], ax
0x180033ab1  call    cs:__imp_VariantCopy
0x180033ab7  jmp     loc_18003398D
```
