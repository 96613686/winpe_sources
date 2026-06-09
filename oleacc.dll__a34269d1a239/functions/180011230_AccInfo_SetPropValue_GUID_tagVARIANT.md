# AccInfo::SetPropValue(_GUID,tagVARIANT *)

- ea: `0x180011230`
- end: `0x180011337`
- name: `?SetPropValue@AccInfo@@QEAAHU_GUID@@PEAUtagVARIANT@@@Z`
- size: `263`
- prototype: `int(AccInfo *__hidden this, struct _GUID *__struct_ptr, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180010d94`

## callees

- `0x180011230`
- `0x180011f44`
- `0x180011f84`
- `0x18001dc10`
- `0x18001efc4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011249`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011249`
- `OLEAUT32!__imp_VariantCopy` at `0x180011288`
- `OLEAUT32!__imp_VariantCopy` at `0x180011288`

## pseudocode

```c
__int64 __fastcall AccInfo::SetPropValue(AccInfo *this, struct _GUID *a2, struct tagVARIANT *a3)
{
  char *v6; // rax
  char *v7; // rbx
  _QWORD *v8; // rdi
  IRecordInfo *pRecInfo; // xmm0_8
  __int64 v10; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // edx
  void *v15; // rcx
  struct _GUID v16; // [rsp+20h] [rbp-58h]
  VARIANTARG pvargDest; // [rsp+30h] [rbp-48h] BYREF
  char *v18; // [rsp+98h] [rbp+20h] BYREF

  v6 = (char *)LocalAlloc(0x40u, 0x40u);
  v7 = v6;
  if ( !v6 )
    return 0;
  memset_0(v6, 0, 0x40u);
  v18 = v7;
  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( VariantCopy(&pvargDest, a3) < 0 )
  {
    AutoDelete<AccInfo::PropInfo *>::~AutoDelete<AccInfo::PropInfo *>(&v18);
    return 0;
  }
  v8 = (_QWORD *)*((_QWORD *)this + 4);
  v16 = *a2;
  while ( v8 )
  {
    v12 = v8;
    v8 = (_QWORD *)*v8;
    v13 = v12[2] - *(_QWORD *)&v16.Data1;
    if ( !v13 )
      v13 = v12[3] - *(_QWORD *)v16.Data4;
    if ( !v13 )
    {
      LinkBase<AccInfo::PropInfo *>::Unlink(v12, (char *)this + 32);
      if ( v15 )
        AccInfo::PropInfo::`scalar deleting destructor'(v15, v14);
    }
  }
  *((struct _GUID *)v7 + 1) = *a2;
  v7[32] = 0;
  pRecInfo = pvargDest.pRecInfo;
  *(_OWORD *)(v7 + 40) = *(_OWORD *)&pvargDest.vt;
  *((_QWORD *)v7 + 7) = pRecInfo;
  *(_QWORD *)v7 = *((_QWORD *)this + 4);
  v10 = *((_QWORD *)this + 4);
  if ( v10 )
    *(_QWORD *)(v10 + 8) = v7;
  *((_QWORD *)this + 4) = v7;
  return 1;
}

```

## disassembly

```asm
0x180011230  push    rbx
0x180011232  push    rbp
0x180011233  push    rsi
0x180011234  push    rdi
0x180011235  sub     rsp, 58h
0x180011239  mov     rbp, rdx
0x18001123c  mov     rsi, rcx
0x18001123f  mov     edx, 40h ; '@'; uBytes
0x180011244  mov     rdi, r8
0x180011247  mov     ecx, edx; uFlags
0x180011249  call    cs:__imp_LocalAlloc
0x18001124f  mov     rbx, rax
0x180011252  test    rax, rax
0x180011255  jz      loc_18001132D
0x18001125b  xor     edx, edx; Val
0x18001125d  mov     rcx, rax; void *
0x180011260  lea     r8d, [rdx+40h]; Size
0x180011264  call    memset_0
0x180011269  xorps   xmm0, xmm0
0x18001126c  mov     [rsp+78h+arg_18], rbx
0x180011274  xor     eax, eax
0x180011276  lea     rcx, [rsp+78h+pvargDest]; pvargDest
0x18001127b  mov     rdx, rdi; pvargSrc
0x18001127e  mov     qword ptr [rsp+78h+pvargDest+10h], rax
0x180011283  movups  xmmword ptr [rsp+78h+pvargDest], xmm0
0x180011288  call    cs:__imp_VariantCopy
0x18001128e  test    eax, eax
0x180011290  js      loc_180011320
0x180011296  movaps  xmm0, xmmword ptr [rbp+0]
0x18001129a  mov     rdi, [rsi+20h]
0x18001129e  movdqa  [rsp+78h+var_58], xmm0
0x1800112a4  test    rdi, rdi
0x1800112a7  jnz     short loc_1800112EC
0x1800112a9  movaps  xmm0, xmmword ptr [rbp+0]
0x1800112ad  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800112b2  mov     [rbx+20h], dil
0x1800112b6  movups  xmm1, xmmword ptr [rsp+78h+pvargDest]
0x1800112bb  movsd   xmm0, qword ptr [rsp+78h+pvargDest+10h]
0x1800112c1  movups  xmmword ptr [rbx+28h], xmm1
0x1800112c5  movsd   qword ptr [rbx+38h], xmm0
0x1800112ca  mov     rax, [rsi+20h]
0x1800112ce  mov     [rbx], rax
0x1800112d1  mov     rax, [rsi+20h]
0x1800112d5  test    rax, rax
0x1800112d8  jnz     short loc_180011331
0x1800112da  mov     [rsi+20h], rbx
0x1800112de  mov     eax, 1
0x1800112e3  add     rsp, 58h
0x1800112e7  pop     rdi
0x1800112e8  pop     rsi
0x1800112e9  pop     rbp
0x1800112ea  pop     rbx
0x1800112eb  retn
0x1800112ec  mov     rcx, rdi
0x1800112ef  mov     rdi, [rdi]
0x1800112f2  mov     rax, [rcx+10h]
0x1800112f6  sub     rax, qword ptr [rsp+78h+var_58]
0x1800112fb  jnz     short loc_180011306
0x1800112fd  mov     rax, [rcx+18h]
0x180011301  sub     rax, qword ptr [rsp+78h+var_58+8]
0x180011306  test    rax, rax
0x180011309  jnz     short loc_1800112A4
0x18001130b  lea     rdx, [rsi+20h]
0x18001130f  call    ?Unlink@?$LinkBase@PEAVPropInfo@AccInfo@@@@QEAAXPEAPEAVPropInfo@AccInfo@@@Z; LinkBase<AccInfo::PropInfo *>::Unlink(AccInfo::PropInfo * *)
0x180011314  test    rcx, rcx
0x180011317  jz      short loc_1800112A4
0x180011319  call    ??_GPropInfo@AccInfo@@QEAAPEAXI@Z; AccInfo::PropInfo::`scalar deleting destructor'(uint)
0x18001131e  jmp     short loc_1800112A4
0x180011320  lea     rcx, [rsp+78h+arg_18]
0x180011328  call    ??1?$AutoDelete@PEAVPropInfo@AccInfo@@@@QEAA@XZ; AutoDelete<AccInfo::PropInfo *>::~AutoDelete<AccInfo::PropInfo *>(void)
0x18001132d  xor     eax, eax
0x18001132f  jmp     short loc_1800112E3
0x180011331  mov     [rax+8], rbx
0x180011335  jmp     short loc_1800112DA
```
