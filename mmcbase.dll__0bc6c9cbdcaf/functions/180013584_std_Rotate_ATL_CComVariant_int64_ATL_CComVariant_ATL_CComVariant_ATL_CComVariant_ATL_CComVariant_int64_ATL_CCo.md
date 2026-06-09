# std::_Rotate<ATL::CComVariant *,__int64,ATL::CComVariant>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,__int64 *,ATL::CComVariant *)

- ea: `0x180013584`
- end: `0x1800136d1`
- name: `??$_Rotate@PEAVCComVariant@ATL@@_JV12@@std@@YAXPEAVCComVariant@ATL@@00PEA_J0@Z`
- size: `333`
- prototype: `__int64 __fastcall(ATL::CComVariant *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800137ec`

## callees

- `0x180005728`
- `0x180013584`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180013670`
- `OLEAUT32!__imp_VariantClear` at `0x180013670`

## pseudocode

```c
int __fastcall std::_Rotate<ATL::CComVariant *,__int64,ATL::CComVariant>(VARIANTARG *this, __int64 a2, char *a3)
{
  __int64 v3; // rax
  signed __int64 v5; // rsi
  signed __int64 v6; // r9
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rt2
  __int64 v12; // r14
  VARIANTARG *v13; // r15
  VARIANTARG *v14; // rbx
  VARIANTARG *v15; // rbp
  signed __int64 v16; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-68h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+20h]

  LODWORD(v3) = -1431655765;
  v5 = 0xAAAAAAAAAAAAAAABuLL * ((a2 - (__int64)this) >> 3);
  v6 = 0xAAAAAAAAAAAAAAABuLL * ((a3 - (char *)this) >> 3);
  v8 = v5;
  v9 = v6;
  if ( v5 )
  {
    do
    {
      v10 = v9;
      v9 = v8;
      v11 = v10 % v8;
      v3 = v10 / v8;
      v8 = v11;
    }
    while ( v11 );
    v19 = v9;
    if ( v9 < v6 && v9 > 0 )
    {
      v12 = v5;
      do
      {
        v13 = &this[v9];
        v14 = &v13[v12];
        v15 = v13;
        if ( &v13[v12] == (VARIANTARG *)a3 )
          v14 = this;
        do
        {
          pvarg.vt = 0;
          ATL::CComVariant::InternalCopy(&pvarg, v15);
          ATL::CComVariant::InternalCopy(v15, v14);
          ATL::CComVariant::InternalCopy(v14, &pvarg);
          if ( pvarg.vt == 4095 )
            pvarg.vt = 8;
          LODWORD(v3) = VariantClear(&pvarg);
          v15 = v14;
          v16 = 0xAAAAAAAAAAAAAAABuLL * ((a3 - (char *)v14) >> 3);
          if ( v5 >= v16 )
          {
            LODWORD(v3) = 3 * (v5 - v16);
            v14 = &this[v5 - v16];
          }
          else
          {
            v14 = (VARIANTARG *)((char *)v14 + v12 * 24);
          }
        }
        while ( v14 != v13 );
        v9 = v19 - 1;
        v19 = v9;
      }
      while ( v9 > 0 );
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180013584  mov     [rsp+arg_18], r9
0x180013589  push    rbx
0x18001358a  push    rbp
0x18001358b  push    rsi
0x18001358c  push    rdi
0x18001358d  push    r12
0x18001358f  push    r13
0x180013591  push    r14
0x180013593  push    r15
0x180013595  sub     rsp, 48h
0x180013599  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800135a3  mov     rsi, rdx
0x1800135a6  sub     rsi, rcx
0x1800135a9  mov     r9, r8
0x1800135ac  sub     r9, rcx
0x1800135af  sar     rsi, 3
0x1800135b3  sar     r9, 3
0x1800135b7  mov     r12, rcx
0x1800135ba  imul    rsi, rax
0x1800135be  imul    r9, rax
0x1800135c2  mov     r13, r8
0x1800135c5  mov     rcx, rsi
0x1800135c8  mov     rdi, r9
0x1800135cb  test    rsi, rsi
0x1800135ce  jz      loc_1800136C0
0x1800135d4  mov     rax, rdi
0x1800135d7  mov     rdi, rcx
0x1800135da  cqo
0x1800135dc  idiv    rcx
0x1800135df  mov     rcx, rdx
0x1800135e2  test    rdx, rdx
0x1800135e5  jnz     short loc_1800135D4
0x1800135e7  mov     [rsp+88h+arg_18], rdi
0x1800135ef  cmp     rdi, r9
0x1800135f2  jge     loc_1800136C0
0x1800135f8  test    rdi, rdi
0x1800135fb  jle     loc_1800136C0
0x180013601  lea     r14, [rsi+rsi*2]
0x180013605  shl     r14, 3
0x180013609  lea     rax, [rdi+rdi*2]
0x18001360d  mov     rdi, 0AAAAAAAAAAAAAAABh
0x180013617  lea     r15, [r12+rax*8]
0x18001361b  lea     rbx, [r14+r15]
0x18001361f  mov     rbp, r15
0x180013622  cmp     rbx, r13
0x180013625  cmovz   rbx, r12
0x180013629  xor     eax, eax
0x18001362b  lea     rcx, [rsp+88h+pvarg]; this
0x180013630  mov     rdx, rbp; struct tagVARIANT *
0x180013633  mov     word ptr [rsp+88h+pvarg], ax
0x180013638  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18001363d  mov     rdx, rbx; struct tagVARIANT *
0x180013640  mov     rcx, rbp; this
0x180013643  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x180013648  lea     rdx, [rsp+88h+pvarg]; struct tagVARIANT *
0x18001364d  mov     rcx, rbx; this
0x180013650  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x180013655  mov     eax, 0FFFh
0x18001365a  cmp     word ptr [rsp+88h+pvarg], ax
0x18001365f  jnz     short loc_18001366B
0x180013661  mov     eax, 8
0x180013666  mov     word ptr [rsp+88h+pvarg], ax
0x18001366b  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180013670  call    cs:__imp_VariantClear
0x180013676  mov     rcx, r13
0x180013679  mov     rbp, rbx
0x18001367c  sub     rcx, rbx
0x18001367f  sar     rcx, 3
0x180013683  imul    rcx, rdi
0x180013687  cmp     rsi, rcx
0x18001368a  jge     short loc_180013691
0x18001368c  add     rbx, r14
0x18001368f  jmp     short loc_18001369F
0x180013691  mov     rax, rsi
0x180013694  sub     rax, rcx
0x180013697  lea     rax, [rax+rax*2]
0x18001369b  lea     rbx, [r12+rax*8]
0x18001369f  cmp     rbx, r15
0x1800136a2  jnz     short loc_180013629
0x1800136a4  mov     rdi, [rsp+88h+arg_18]
0x1800136ac  dec     rdi
0x1800136af  mov     [rsp+88h+arg_18], rdi
0x1800136b7  test    rdi, rdi
0x1800136ba  jg      loc_180013609
0x1800136c0  add     rsp, 48h
0x1800136c4  pop     r15
0x1800136c6  pop     r14
0x1800136c8  pop     r13
0x1800136ca  pop     r12
0x1800136cc  pop     rdi
0x1800136cd  pop     rsi
0x1800136ce  pop     rbp
0x1800136cf  pop     rbx
0x1800136d0  retn
```
