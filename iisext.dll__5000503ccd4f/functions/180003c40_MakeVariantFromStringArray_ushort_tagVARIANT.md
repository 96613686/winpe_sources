# MakeVariantFromStringArray(ushort *,tagVARIANT *)

- ea: `0x180003c40`
- end: `0x180003ddf`
- name: `?MakeVariantFromStringArray@@YAJPEAGPEAUtagVARIANT@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(OLECHAR *psz, VARIANTARG *pvarg)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009650`
- `0x180009700`
- `0x1800097b0`
- `0x180009950`

## callees

- `0x180003c40`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003d19`
- `OLEAUT32!__imp_SysAllocString` at `0x180003d19`
- `OLEAUT32!__imp_VariantInit` at `0x180003cfc`
- `OLEAUT32!__imp_VariantInit` at `0x180003d82`
- `OLEAUT32!__imp_VariantInit` at `0x180003cfc`
- `OLEAUT32!__imp_VariantInit` at `0x180003d82`
- `OLEAUT32!__imp_VariantClear` at `0x180003d4f`
- `OLEAUT32!__imp_VariantClear` at `0x180003d4f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180003ccd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180003dc8`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180003ccd`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180003dc8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180003db0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180003db0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180003d43`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180003d43`

## pseudocode

```c
__int64 __fastcall MakeVariantFromStringArray(OLECHAR *psz, VARIANTARG *pvarg)
{
  OLECHAR *v3; // rdi
  OLECHAR v4; // cx
  OLECHAR v5; // dx
  OLECHAR *v6; // rax
  signed int v7; // esi
  SAFEARRAY *v8; // r14
  HRESULT v9; // ebx
  __int64 v10; // rax
  __int64 result; // rax
  VARIANTARG pvarga; // [rsp+20h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+70h] [rbp+30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+80h] [rbp+40h] BYREF

  v3 = psz;
  if ( psz )
  {
    v4 = *psz;
    rgIndices = 0;
    if ( v4 )
      v5 = v4;
    else
      v5 = v3[1];
    v6 = v3 + 1;
    v7 = v4 == 0;
    if ( v4 )
      v6 = v3;
    if ( v5 )
    {
      if ( !*v6 )
        goto LABEL_10;
      do
      {
        do
          ++v6;
        while ( *v6 );
LABEL_10:
        ++v6;
        ++v7;
      }
      while ( *v6 );
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = v7;
    v8 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v8 )
    {
      rgIndices = 0;
      if ( v7 > 0 )
      {
        while ( 1 )
        {
          memset(&pvarga, 0, sizeof(pvarga));
          VariantInit(&pvarga);
          pvarga.vt = 8;
          if ( v3 )
          {
            pvarga.llVal = (LONGLONG)SysAllocString(v3);
            v9 = pvarga.llVal == 0 ? 0x8007000E : 0;
            if ( !pvarga.llVal )
              break;
          }
          else
          {
            pvarga.llVal = 0;
          }
          v9 = SafeArrayPutElement(v8, &rgIndices, &pvarga);
          VariantClear(&pvarga);
          if ( v9 < 0 )
            break;
          v10 = -1;
          do
            ++v10;
          while ( v3[v10] );
          v3 += v10 + 1;
          if ( ++rgIndices >= v7 )
            goto LABEL_20;
        }
        SafeArrayDestroy(v8);
        return (unsigned int)v9;
      }
LABEL_20:
      VariantInit(pvarg);
      pvarg->vt = 8204;
      result = 0;
      pvarg->llVal = (LONGLONG)v8;
      return result;
    }
  }
  else
  {
    rgsabound = 0;
    v8 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v8 )
      goto LABEL_20;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180003c40  mov     [rsp-28h+arg_8], rbx
0x180003c45  mov     [rsp-28h+arg_18], rsi
0x180003c4a  push    rbp
0x180003c4b  push    rdi
0x180003c4c  push    r12
0x180003c4e  push    r14
0x180003c50  push    r15
0x180003c52  mov     rbp, rsp
0x180003c55  sub     rsp, 40h
0x180003c59  xor     r12d, r12d
0x180003c5c  mov     r15, rdx
0x180003c5f  mov     rdi, rcx
0x180003c62  test    rcx, rcx
0x180003c65  jz      loc_180003DB8
0x180003c6b  movzx   ecx, word ptr [rcx]
0x180003c6e  mov     [rbp+rgIndices], r12d
0x180003c72  test    cx, cx
0x180003c75  jnz     short loc_180003C7D
0x180003c77  movzx   edx, word ptr [rdi+2]
0x180003c7b  jmp     short loc_180003C80
0x180003c7d  movzx   edx, cx
0x180003c80  test    cx, cx
0x180003c83  lea     rax, [rdi+2]
0x180003c87  mov     esi, r12d
0x180003c8a  setz    sil
0x180003c8e  test    cx, cx
0x180003c91  cmovnz  rax, rdi
0x180003c95  test    dx, dx
0x180003c98  jz      short loc_180003CBA
0x180003c9a  movzx   ecx, word ptr [rax]
0x180003c9d  test    cx, cx
0x180003ca0  jz      short loc_180003CAC
0x180003ca2  add     rax, 2
0x180003ca6  cmp     [rax], r12w
0x180003caa  jnz     short loc_180003CA2
0x180003cac  add     rax, 2
0x180003cb0  inc     esi
0x180003cb2  movzx   ecx, word ptr [rax]
0x180003cb5  test    cx, cx
0x180003cb8  jnz     short loc_180003CA2
0x180003cba  mov     ecx, 0Ch; vt
0x180003cbf  mov     [rbp+rgsabound.lLbound], r12d
0x180003cc3  lea     r8, [rbp+rgsabound]; rgsabound
0x180003cc7  mov     [rbp+rgsabound.cElements], esi
0x180003cca  lea     edx, [rcx-0Bh]; cDims
0x180003ccd  call    cs:__imp_SafeArrayCreate
0x180003cd3  mov     r14, rax
0x180003cd6  test    rax, rax
0x180003cd9  jz      loc_180003DD6
0x180003cdf  mov     [rbp+rgIndices], r12d
0x180003ce3  test    esi, esi
0x180003ce5  jle     loc_180003D7F
0x180003ceb  xorps   xmm0, xmm0
0x180003cee  lea     rcx, [rbp+pvarg]; pvarg
0x180003cf2  xor     eax, eax
0x180003cf4  movups  xmmword ptr [rbp+pvarg], xmm0
0x180003cf8  mov     qword ptr [rbp+pvarg+10h], rax
0x180003cfc  call    cs:__imp_VariantInit
0x180003d02  mov     eax, 8
0x180003d07  mov     word ptr [rbp+pvarg], ax
0x180003d0b  test    rdi, rdi
0x180003d0e  jnz     short loc_180003D16
0x180003d10  mov     qword ptr [rbp+pvarg+8], r12
0x180003d14  jmp     short loc_180003D38
0x180003d16  mov     rcx, rdi; psz
0x180003d19  call    cs:__imp_SysAllocString
0x180003d1f  mov     rcx, rax
0x180003d22  mov     qword ptr [rbp+pvarg+8], rax
0x180003d26  neg     rcx
0x180003d29  sbb     ebx, ebx
0x180003d2b  not     ebx
0x180003d2d  and     ebx, 8007000Eh
0x180003d33  test    rax, rax
0x180003d36  jz      short loc_180003DAD
0x180003d38  lea     r8, [rbp+pvarg]; pv
0x180003d3c  mov     rcx, r14; psa
0x180003d3f  lea     rdx, [rbp+rgIndices]; rgIndices
0x180003d43  call    cs:__imp_SafeArrayPutElement
0x180003d49  lea     rcx, [rbp+pvarg]; pvarg
0x180003d4d  mov     ebx, eax
0x180003d4f  call    cs:__imp_VariantClear
0x180003d55  test    ebx, ebx
0x180003d57  js      short loc_180003DAD
0x180003d59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d5d  inc     rax
0x180003d60  cmp     [rdi+rax*2], r12w
0x180003d65  jnz     short loc_180003D5D
0x180003d67  lea     rdi, [rdi+rax*2]
0x180003d6b  mov     eax, [rbp+rgIndices]
0x180003d6e  inc     eax
0x180003d70  add     rdi, 2
0x180003d74  mov     [rbp+rgIndices], eax
0x180003d77  cmp     eax, esi
0x180003d79  jl      loc_180003CEB
0x180003d7f  mov     rcx, r15; pvarg
0x180003d82  call    cs:__imp_VariantInit
0x180003d88  mov     word ptr [r15], 200Ch
0x180003d8e  xor     eax, eax
0x180003d90  mov     [r15+8], r14
0x180003d94  lea     r11, [rsp+40h+var_s0]
0x180003d99  mov     rbx, [r11+38h]
0x180003d9d  mov     rsi, [r11+48h]
0x180003da1  mov     rsp, r11
0x180003da4  pop     r15
0x180003da6  pop     r14
0x180003da8  pop     r12
0x180003daa  pop     rdi
0x180003dab  pop     rbp
0x180003dac  retn
0x180003dad  mov     rcx, r14; psa
0x180003db0  call    cs:__imp_SafeArrayDestroy
0x180003db6  jmp     short loc_180003DDB
0x180003db8  mov     ecx, 0Ch; vt
0x180003dbd  mov     qword ptr [rbp+rgsabound.cElements], r12
0x180003dc1  lea     r8, [rbp+rgsabound]; rgsabound
0x180003dc5  lea     edx, [rcx-0Bh]; cDims
0x180003dc8  call    cs:__imp_SafeArrayCreate
0x180003dce  mov     r14, rax
0x180003dd1  test    rax, rax
0x180003dd4  jnz     short loc_180003D7F
0x180003dd6  mov     ebx, 8007000Eh
0x180003ddb  mov     eax, ebx
0x180003ddd  jmp     short loc_180003D94
```
