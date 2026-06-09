# VAR::GetStdVar(tagVARIANT *)

- ea: `0x180004d40`
- end: `0x180004efd`
- name: `?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z`
- size: `445`
- prototype: `int __fastcall(VAR *this, struct tagVARIANT *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180002ba8`
- `0x1800105a0`
- `0x180013574`
- `0x180023440`
- `0x1800642e8`
- `0x18008c100`

## callees

- `0x180004d40`
- `0x180005070`
- `0x1800080c8`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180004eec`
- `OLEAUT32!__imp_VariantCopy` at `0x180004eec`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180004e12`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180004e12`

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
0x180004d40  mov     [rsp+arg_0], rbx
0x180004d45  mov     [rsp+arg_8], rsi
0x180004d4a  push    rdi
0x180004d4b  sub     rsp, 40h
0x180004d4f  mov     rbx, rdx
0x180004d52  test    rdx, rdx
0x180004d55  jz      short loc_180004DD2
0x180004d57  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x180004d5c  mov     rdi, rax
0x180004d5f  movzx   edx, word ptr [rax]
0x180004d62  cmp     edx, 0Ah
0x180004d65  jbe     loc_180004E33
0x180004d6b  mov     ecx, edx
0x180004d6d  sub     ecx, 0Bh
0x180004d70  jz      short loc_180004D7B
0x180004d72  sub     ecx, 3
0x180004d75  jnz     loc_180004E86
0x180004d7b  bt      dx, 0Eh
0x180004d80  jb      short loc_180004D9A
0x180004d82  movups  xmm0, xmmword ptr [rax]
0x180004d85  movups  xmmword ptr [rbx], xmm0
0x180004d88  movsd   xmm1, qword ptr [rax+10h]
0x180004d8d  movsd   qword ptr [rbx+10h], xmm1
0x180004d92  jmp     short loc_180004DBF
0x180004d94  bt      edx, 0Eh
0x180004d98  jb      short loc_180004D7B
0x180004d9a  mov     eax, 9
0x180004d9f  sub     edx, eax
0x180004da1  jnz     short loc_180004DD9
0x180004da3  mov     [rbx], ax
0x180004da6  mov     rcx, [rdi+8]
0x180004daa  mov     [rbx+8], rcx
0x180004dae  test    rcx, rcx
0x180004db1  jz      short loc_180004DBF
0x180004db3  mov     rax, [rcx]
0x180004db6  mov     rax, [rax+8]
0x180004dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dbf  xor     eax, eax
0x180004dc1  mov     rbx, [rsp+48h+arg_0]
0x180004dc6  mov     rsi, [rsp+48h+arg_8]
0x180004dcb  add     rsp, 40h
0x180004dcf  pop     rdi
0x180004dd0  retn
0x180004dd2  mov     eax, 80070057h
0x180004dd7  jmp     short loc_180004DC1
0x180004dd9  sub     edx, 78h ; 'x'
0x180004ddc  jz      short loc_180004DA3
0x180004dde  mov     esi, 8
0x180004de3  sub     edx, 1
0x180004de6  jz      loc_180004ED1
0x180004dec  sub     edx, 4
0x180004def  jz      short loc_180004DA3
0x180004df1  sub     edx, 1
0x180004df4  jz      short loc_180004DA3
0x180004df6  sub     edx, esi
0x180004df8  jz      loc_180004EC1
0x180004dfe  cmp     edx, 1
0x180004e01  jz      short loc_180004DA3
0x180004e03  xor     eax, eax
0x180004e05  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x180004e0a  mov     rdx, rdi; pvargSrc
0x180004e0d  mov     word ptr [rsp+48h+pvarDest], ax
0x180004e12  call    cs:__imp_VariantCopyInd
0x180004e19  nop     dword ptr [rax+rax+00h]
0x180004e1e  movups  xmm0, xmmword ptr [rsp+48h+pvarDest]
0x180004e23  movsd   xmm1, qword ptr [rsp+48h+pvarDest+10h]
0x180004e29  movups  xmmword ptr [rbx], xmm0
0x180004e2c  movsd   qword ptr [rbx+10h], xmm1
0x180004e31  jmp     short loc_180004DC1
0x180004e33  jz      loc_180004D7B
0x180004e39  mov     r8d, edx
0x180004e3c  test    edx, edx
0x180004e3e  jz      loc_180004D7B
0x180004e44  sub     r8d, 1
0x180004e48  jz      loc_180004D7B
0x180004e4e  sub     r8d, 1
0x180004e52  jz      loc_180004D7B
0x180004e58  sub     r8d, 1
0x180004e5c  jz      loc_180004D7B
0x180004e62  sub     r8d, 1
0x180004e66  jz      loc_180004D7B
0x180004e6c  sub     r8d, 1
0x180004e70  jz      loc_180004D7B
0x180004e76  sub     r8d, 1
0x180004e7a  jz      loc_180004D7B
0x180004e80  cmp     r8d, 1
0x180004e84  jmp     short loc_180004EB6
0x180004e86  sub     ecx, 2
0x180004e89  jz      loc_180004D7B
0x180004e8f  sub     ecx, 1
0x180004e92  jz      loc_180004D7B
0x180004e98  sub     ecx, 1
0x180004e9b  jz      loc_180004D7B
0x180004ea1  sub     ecx, 1
0x180004ea4  jz      loc_180004D7B
0x180004eaa  sub     ecx, 3
0x180004ead  jz      loc_180004D7B
0x180004eb3  cmp     ecx, 1
0x180004eb6  jz      loc_180004D7B
0x180004ebc  jmp     loc_180004D94
0x180004ec1  mov     rcx, rdi; this
0x180004ec4  call    ?ConvertASTRtoBSTR@VAR@@QEAAJXZ; VAR::ConvertASTRtoBSTR(void)
0x180004ec9  test    eax, eax
0x180004ecb  js      loc_180004DC1
0x180004ed1  mov     word ptr [rsp+48h+pvarDest], si
0x180004ed6  lea     rdx, [rsp+48h+pvarDest]; pvargSrc
0x180004edb  mov     rax, [rdi+8]
0x180004edf  mov     rcx, rbx; pvargDest
0x180004ee2  mov     qword ptr [rsp+48h+pvarDest+8], rax
0x180004ee7  xor     eax, eax
0x180004ee9  mov     [rbx], ax
0x180004eec  call    cs:__imp_VariantCopy
0x180004ef3  nop     dword ptr [rax+rax+00h]
0x180004ef8  jmp     loc_180004DC1
```
