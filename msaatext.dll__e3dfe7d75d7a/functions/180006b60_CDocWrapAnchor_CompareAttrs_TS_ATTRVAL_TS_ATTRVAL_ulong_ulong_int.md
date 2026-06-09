# CDocWrapAnchor::CompareAttrs(TS_ATTRVAL *,TS_ATTRVAL *,ulong,ulong &,int)

- ea: `0x180006b60`
- end: `0x180006dd1`
- name: `?CompareAttrs@CDocWrapAnchor@@AEAAJPEAUTS_ATTRVAL@@0KAEAKH@Z`
- size: `625`
- prototype: `__int64 __fastcall(CDocWrapAnchor *__hidden this, struct TS_ATTRVAL *, struct TS_ATTRVAL *, unsigned int, unsigned int *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007810`
- `0x18000ab80`

## callees

- `0x180006b60`
- `0x180012af6`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180006ca3`
- `OLEAUT32!__imp_VariantClear` at `0x180006cc1`
- `OLEAUT32!__imp_VariantClear` at `0x180006ca3`
- `OLEAUT32!__imp_VariantClear` at `0x180006cc1`
- `OLEAUT32!__imp_VariantCopy` at `0x180006be4`
- `OLEAUT32!__imp_VariantCopy` at `0x180006c0b`
- `OLEAUT32!__imp_VariantCopy` at `0x180006be4`
- `OLEAUT32!__imp_VariantCopy` at `0x180006c0b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180006d8e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180006d9a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180006dac`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180006d8e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180006d9a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180006dac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDocWrapAnchor::CompareAttrs(
        CDocWrapAnchor *this,
        struct TS_ATTRVAL *a2,
        struct TS_ATTRVAL *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  struct TS_ATTRVAL *v7; // r8
  unsigned int v8; // edi
  __int64 v10; // rsi
  __int64 v11; // rcx
  struct TS_ATTRVAL *v12; // rdx
  __int64 v13; // r14
  HRESULT v14; // eax
  HRESULT lVal; // edx
  bool v16; // zf
  char v17; // bl
  __int64 v18; // rax
  __int64 v19; // rcx
  bool v21; // zf
  UINT v22; // ebx
  UINT v23; // eax
  VARIANTARG pvargDest; // [rsp+20h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-20h] BYREF

  v7 = a2;
  v8 = a4;
  if ( !a4 )
    v8 = *((_DWORD *)this + 46);
  v10 = 0;
  if ( v8 )
  {
    while ( 1 )
    {
      v11 = 0;
      v12 = &v7[v10];
      while ( 1 )
      {
        v13 = v11;
        if ( *(_QWORD *)&v12->idAttr.Data1 == *(_QWORD *)&a3[v11].idAttr.Data1
          && *(_QWORD *)v12->idAttr.Data4 == *(_QWORD *)a3[v13].idAttr.Data4 )
        {
          break;
        }
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= v8 )
          goto LABEL_35;
      }
      pvargDest.vt = 0;
      v14 = VariantCopy(&pvargDest, &v12->varValue);
      if ( v14 < 0 )
      {
        pvargDest.lVal = v14;
        pvargDest.vt = 10;
      }
      pvarg.vt = 0;
      lVal = VariantCopy(&pvarg, &a3[v13].varValue);
      if ( lVal >= 0 )
      {
        lVal = pvarg.lVal;
      }
      else
      {
        pvarg.lVal = lVal;
        pvarg.vt = 10;
      }
      if ( pvargDest.vt != pvarg.vt )
      {
LABEL_25:
        v17 = 0;
        goto LABEL_26;
      }
      if ( pvargDest.vt > 0x11u )
      {
        if ( pvargDest.vt != 4095 )
          goto LABEL_25;
        goto LABEL_49;
      }
      if ( pvargDest.vt == 17 )
      {
        v21 = pvargDest.bVal == pvarg.bVal;
        goto LABEL_46;
      }
      if ( pvargDest.vt > 5u )
        break;
      if ( pvargDest.vt == 5 )
      {
        v16 = pvargDest.dblVal == pvarg.dblVal;
        goto LABEL_51;
      }
      if ( pvargDest.vt && pvargDest.vt != 1 )
      {
        if ( pvargDest.vt == 2 )
          goto LABEL_45;
        if ( pvargDest.vt == 3 )
          goto LABEL_37;
        if ( pvargDest.vt != 4 )
          goto LABEL_25;
        v16 = pvargDest.fltVal == pvarg.fltVal;
        goto LABEL_51;
      }
LABEL_52:
      v17 = 1;
LABEL_26:
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      VariantClear(&pvarg);
      if ( pvargDest.vt == 4095 )
        pvargDest.vt = 8;
      VariantClear(&pvargDest);
      if ( !v17 )
      {
        if ( a6 )
        {
          v18 = *((_QWORD *)this + 25);
          v19 = 6LL * *a5;
          *(TS_ATTRID *)(v18 + 8 * v19) = a3[v13].idAttr;
          *(_OWORD *)(v18 + 8 * v19 + 16) = *(_OWORD *)&a3[v13].dwOverlapId;
          *(_OWORD *)(v18 + 8 * v19 + 32) = *(_OWORD *)&a3[v13].varValue.decVal.Lo32;
        }
        ++*a5;
      }
      v7 = a2;
LABEL_35:
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= v8 )
        return 0;
    }
    if ( pvargDest.vt != 8 )
    {
      switch ( pvargDest.vt )
      {
        case 9u:
          goto LABEL_44;
        case 0xAu:
LABEL_37:
          v21 = pvargDest.lVal == lVal;
          break;
        case 0xBu:
LABEL_45:
          v21 = pvargDest.iVal == pvarg.iVal;
          break;
        case 0xDu:
LABEL_44:
          v21 = pvargDest.llVal == pvarg.llVal;
          break;
        default:
          goto LABEL_25;
      }
LABEL_46:
      v17 = v21;
      goto LABEL_26;
    }
LABEL_49:
    v22 = SysStringByteLen(pvarg.bstrVal);
    if ( SysStringByteLen(pvargDest.bstrVal) != v22 )
      goto LABEL_25;
    v23 = SysStringByteLen(pvargDest.bstrVal);
    v16 = memcmp_0(pvargDest.bstrVal, pvarg.bstrVal, v23) == 0;
LABEL_51:
    if ( !v16 )
      goto LABEL_25;
    goto LABEL_52;
  }
  return 0;
}

```

## disassembly

```asm
0x180006b60  mov     [rsp-40h+arg_8], rdx
0x180006b65  push    rbp
0x180006b66  push    rbx
0x180006b67  push    rsi
0x180006b68  push    rdi
0x180006b69  push    r12
0x180006b6b  push    r13
0x180006b6d  push    r14
0x180006b6f  push    r15
0x180006b71  mov     rbp, rsp
0x180006b74  sub     rsp, 58h
0x180006b78  mov     r15, r8
0x180006b7b  mov     r8, rdx
0x180006b7e  mov     edi, r9d
0x180006b81  mov     r13, rcx
0x180006b84  test    r9d, r9d
0x180006b87  jnz     short loc_180006B8F
0x180006b89  mov     edi, [rcx+0B8h]
0x180006b8f  xor     esi, esi
0x180006b91  test    edi, edi
0x180006b93  jz      loc_180006D19
0x180006b99  mov     r12, [rbp+arg_20]
0x180006b9d  mov     ebx, 0FFFh
0x180006ba2  lea     rdx, [rsi+rsi*2]
0x180006ba6  xor     ecx, ecx
0x180006ba8  shl     rdx, 4
0x180006bac  add     rdx, r8
0x180006baf  mov     rax, [rdx]
0x180006bb2  lea     r14, [rcx+rcx*2]
0x180006bb6  shl     r14, 4
0x180006bba  cmp     rax, [r14+r15]
0x180006bbe  jnz     short loc_180006BCB
0x180006bc0  mov     rax, [rdx+8]
0x180006bc4  cmp     rax, [r14+r15+8]
0x180006bc9  jz      short loc_180006BD6
0x180006bcb  inc     ecx
0x180006bcd  cmp     ecx, edi
0x180006bcf  jb      short loc_180006BAF
0x180006bd1  jmp     loc_180006D0F
0x180006bd6  xor     eax, eax
0x180006bd8  lea     rcx, [rbp+pvargDest]; pvargDest
0x180006bdc  add     rdx, 18h; pvargSrc
0x180006be0  mov     word ptr [rbp+pvargDest], ax
0x180006be4  call    cs:__imp_VariantCopy
0x180006bea  test    eax, eax
0x180006bec  jns     short loc_180006BFA
0x180006bee  mov     ecx, 0Ah
0x180006bf3  mov     dword ptr [rbp+pvargDest+8], eax
0x180006bf6  mov     word ptr [rbp+pvargDest], cx
0x180006bfa  xor     eax, eax
0x180006bfc  lea     rdx, [r15+18h]
0x180006c00  add     rdx, r14; pvargSrc
0x180006c03  mov     word ptr [rbp+pvarg], ax
0x180006c07  lea     rcx, [rbp+pvarg]; pvargDest
0x180006c0b  call    cs:__imp_VariantCopy
0x180006c11  mov     edx, eax
0x180006c13  test    eax, eax
0x180006c15  jns     short loc_180006C25
0x180006c17  mov     eax, 0Ah
0x180006c1c  mov     dword ptr [rbp+pvarg+8], edx
0x180006c1f  mov     word ptr [rbp+pvarg], ax
0x180006c23  jmp     short loc_180006C28
0x180006c25  mov     edx, dword ptr [rbp+pvarg+8]
0x180006c28  movzx   eax, word ptr [rbp+pvargDest]
0x180006c2c  cmp     ax, word ptr [rbp+pvarg]
0x180006c30  jnz     short loc_180006C89
0x180006c32  cmp     eax, 11h
0x180006c35  ja      loc_180006D81
0x180006c3b  jz      loc_180006D79
0x180006c41  cmp     eax, 5
0x180006c44  ja      loc_180006D40
0x180006c4a  jz      loc_180006D31
0x180006c50  mov     ecx, eax
0x180006c52  test    eax, eax
0x180006c54  jz      loc_180006DCA
0x180006c5a  sub     ecx, 1
0x180006c5d  jz      loc_180006DCA
0x180006c63  sub     ecx, 1
0x180006c66  jz      loc_180006D69
0x180006c6c  sub     ecx, 1
0x180006c6f  jz      loc_180006D2C
0x180006c75  cmp     ecx, 1
0x180006c78  jnz     short loc_180006C89
0x180006c7a  movss   xmm0, dword ptr [rbp+pvargDest+8]
0x180006c7f  ucomiss xmm0, dword ptr [rbp+pvarg+8]
0x180006c83  jnp     loc_180006DC4
0x180006c89  xor     bl, bl
0x180006c8b  mov     eax, 0FFFh
0x180006c90  cmp     word ptr [rbp+pvarg], ax
0x180006c94  jnz     short loc_180006C9F
0x180006c96  mov     eax, 8
0x180006c9b  mov     word ptr [rbp+pvarg], ax
0x180006c9f  lea     rcx, [rbp+pvarg]; pvarg
0x180006ca3  call    cs:__imp_VariantClear
0x180006ca9  mov     eax, 0FFFh
0x180006cae  cmp     word ptr [rbp+pvargDest], ax
0x180006cb2  jnz     short loc_180006CBD
0x180006cb4  mov     eax, 8
0x180006cb9  mov     word ptr [rbp+pvargDest], ax
0x180006cbd  lea     rcx, [rbp+pvargDest]; pvarg
0x180006cc1  call    cs:__imp_VariantClear
0x180006cc7  test    bl, bl
0x180006cc9  jnz     short loc_180006D06
0x180006ccb  cmp     [rbp+arg_28], 0
0x180006ccf  jz      short loc_180006D02
0x180006cd1  mov     eax, [r12]
0x180006cd5  movups  xmm0, xmmword ptr [r14+r15]
0x180006cda  lea     rcx, [rax+rax*2]
0x180006cde  mov     rax, [r13+0C8h]
0x180006ce5  add     rcx, rcx
0x180006ce8  movups  xmmword ptr [rax+rcx*8], xmm0
0x180006cec  movups  xmm1, xmmword ptr [r14+r15+10h]
0x180006cf2  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x180006cf7  movups  xmm0, xmmword ptr [r14+r15+20h]
0x180006cfd  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x180006d02  inc     dword ptr [r12]
0x180006d06  mov     r8, [rbp+arg_8]
0x180006d0a  mov     ebx, 0FFFh
0x180006d0f  inc     esi
0x180006d11  cmp     esi, edi
0x180006d13  jb      loc_180006BA2
0x180006d19  xor     eax, eax
0x180006d1b  add     rsp, 58h
0x180006d1f  pop     r15
0x180006d21  pop     r14
0x180006d23  pop     r13
0x180006d25  pop     r12
0x180006d27  pop     rdi
0x180006d28  pop     rsi
0x180006d29  pop     rbx
0x180006d2a  pop     rbp
0x180006d2b  retn
0x180006d2c  cmp     dword ptr [rbp+pvargDest+8], edx
0x180006d2f  jmp     short loc_180006D71
0x180006d31  movsd   xmm0, qword ptr [rbp+pvargDest+8]
0x180006d36  ucomisd xmm0, qword ptr [rbp+pvarg+8]
0x180006d3b  jmp     loc_180006C83
0x180006d40  mov     ecx, eax
0x180006d42  sub     ecx, 8
0x180006d45  jz      short loc_180006D8A
0x180006d47  sub     ecx, 1
0x180006d4a  jz      short loc_180006D5F
0x180006d4c  sub     ecx, 1
0x180006d4f  jz      short loc_180006D2C
0x180006d51  sub     ecx, 1
0x180006d54  jz      short loc_180006D69
0x180006d56  cmp     ecx, 2
0x180006d59  jnz     loc_180006C89
0x180006d5f  mov     rax, qword ptr [rbp+pvarg+8]
0x180006d63  cmp     qword ptr [rbp+pvargDest+8], rax
0x180006d67  jmp     short loc_180006D71
0x180006d69  movzx   eax, word ptr [rbp+pvarg+8]
0x180006d6d  cmp     word ptr [rbp+pvargDest+8], ax
0x180006d71  setz    bl
0x180006d74  jmp     loc_180006C8B
0x180006d79  mov     al, byte ptr [rbp+pvarg+8]
0x180006d7c  cmp     byte ptr [rbp+pvargDest+8], al
0x180006d7f  jmp     short loc_180006D71
0x180006d81  cmp     ax, bx
0x180006d84  jnz     loc_180006C89
0x180006d8a  mov     rcx, qword ptr [rbp+pvarg+8]; bstr
0x180006d8e  call    cs:__imp_SysStringByteLen
0x180006d94  mov     rcx, qword ptr [rbp+pvargDest+8]; bstr
0x180006d98  mov     ebx, eax
0x180006d9a  call    cs:__imp_SysStringByteLen
0x180006da0  cmp     eax, ebx
0x180006da2  jnz     loc_180006C89
0x180006da8  mov     rcx, qword ptr [rbp+pvargDest+8]; bstr
0x180006dac  call    cs:__imp_SysStringByteLen
0x180006db2  mov     rdx, qword ptr [rbp+pvarg+8]; Buf2
0x180006db6  mov     rcx, qword ptr [rbp+pvargDest+8]; Buf1
0x180006dba  mov     r8d, eax; Size
0x180006dbd  call    memcmp_0
0x180006dc2  test    eax, eax
0x180006dc4  jnz     loc_180006C89
0x180006dca  mov     bl, 1
0x180006dcc  jmp     loc_180006C8B
```
