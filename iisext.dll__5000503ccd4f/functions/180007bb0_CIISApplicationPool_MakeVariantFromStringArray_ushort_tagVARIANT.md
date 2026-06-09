# CIISApplicationPool::MakeVariantFromStringArray(ushort *,tagVARIANT *)

- ea: `0x180007bb0`
- end: `0x180007d6a`
- name: `?MakeVariantFromStringArray@CIISApplicationPool@@SAJPEAGPEAUtagVARIANT@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(OLECHAR *psz, VARIANTARG *pvarg)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800076d0`

## callees

- `0x180007bb0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007ca3`
- `OLEAUT32!__imp_SysAllocString` at `0x180007ca3`
- `OLEAUT32!__imp_VariantInit` at `0x180007c86`
- `OLEAUT32!__imp_VariantInit` at `0x180007d0d`
- `OLEAUT32!__imp_VariantInit` at `0x180007c86`
- `OLEAUT32!__imp_VariantInit` at `0x180007d0d`
- `OLEAUT32!__imp_VariantClear` at `0x180007cd9`
- `OLEAUT32!__imp_VariantClear` at `0x180007cd9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180007c56`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180007d53`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180007c56`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180007d53`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007d3b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007d3b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007ccd`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007ccd`

## pseudocode

```c
__int64 __fastcall CIISApplicationPool::MakeVariantFromStringArray(OLECHAR *psz, VARIANTARG *pvarg)
{
  OLECHAR *v3; // rdi
  __int64 v4; // rax
  OLECHAR v5; // cx
  OLECHAR v6; // dx
  OLECHAR *v7; // rax
  signed int v8; // r14d
  SAFEARRAY *v9; // rsi
  HRESULT v10; // ebx
  __int64 v11; // rax
  __int64 result; // rax
  VARIANTARG pvarga; // [rsp+20h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+70h] [rbp+30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+80h] [rbp+40h] BYREF

  v3 = psz;
  if ( !psz )
    goto LABEL_25;
  v4 = -1;
  do
    ++v4;
  while ( psz[v4] );
  if ( v4 )
  {
    v5 = *psz;
    rgIndices = 0;
    if ( v5 )
      v6 = v5;
    else
      v6 = v3[1];
    v7 = v3 + 1;
    v8 = v5 == 0;
    if ( v5 )
      v7 = v3;
    if ( v6 )
    {
      if ( !*v7 )
        goto LABEL_13;
      do
      {
        do
          ++v7;
        while ( *v7 );
LABEL_13:
        ++v7;
        ++v8;
      }
      while ( *v7 );
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = v8;
    v9 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v9 )
    {
      rgIndices = 0;
      if ( v8 > 0 )
      {
        while ( 1 )
        {
          memset(&pvarga, 0, sizeof(pvarga));
          VariantInit(&pvarga);
          pvarga.vt = 8;
          if ( v3 )
          {
            pvarga.llVal = (LONGLONG)SysAllocString(v3);
            v10 = pvarga.llVal == 0 ? 0x8007000E : 0;
            if ( !pvarga.llVal )
              break;
          }
          else
          {
            pvarga.llVal = 0;
          }
          v10 = SafeArrayPutElement(v9, &rgIndices, &pvarga);
          VariantClear(&pvarga);
          if ( v10 < 0 )
            break;
          v11 = -1;
          do
            ++v11;
          while ( v3[v11] );
          v3 += v11 + 1;
          if ( ++rgIndices >= v8 )
            goto LABEL_23;
        }
        SafeArrayDestroy(v9);
        return (unsigned int)v10;
      }
LABEL_23:
      VariantInit(pvarg);
      pvarg->vt = 8204;
      result = 0;
      pvarg->llVal = (LONGLONG)v9;
      return result;
    }
  }
  else
  {
LABEL_25:
    rgsabound = 0;
    v9 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v9 )
      goto LABEL_23;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180007bb0  mov     [rsp-28h+arg_8], rbx
0x180007bb5  mov     [rsp-28h+arg_18], rsi
0x180007bba  push    rbp
0x180007bbb  push    rdi
0x180007bbc  push    r12
0x180007bbe  push    r14
0x180007bc0  push    r15
0x180007bc2  mov     rbp, rsp
0x180007bc5  sub     rsp, 40h
0x180007bc9  xor     r12d, r12d
0x180007bcc  mov     r15, rdx
0x180007bcf  mov     rdi, rcx
0x180007bd2  test    rcx, rcx
0x180007bd5  jz      loc_180007D43
0x180007bdb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007bdf  inc     rax
0x180007be2  cmp     [rcx+rax*2], r12w
0x180007be7  jnz     short loc_180007BDF
0x180007be9  test    rax, rax
0x180007bec  jz      loc_180007D43
0x180007bf2  movzx   ecx, word ptr [rcx]
0x180007bf5  mov     [rbp+rgIndices], r12d
0x180007bf9  test    cx, cx
0x180007bfc  jnz     short loc_180007C04
0x180007bfe  movzx   edx, word ptr [rdi+2]
0x180007c02  jmp     short loc_180007C07
0x180007c04  movzx   edx, cx
0x180007c07  test    cx, cx
0x180007c0a  lea     rax, [rdi+2]
0x180007c0e  mov     r14d, r12d
0x180007c11  setz    r14b
0x180007c15  test    cx, cx
0x180007c18  cmovnz  rax, rdi
0x180007c1c  test    dx, dx
0x180007c1f  jz      short loc_180007C42
0x180007c21  movzx   ecx, word ptr [rax]
0x180007c24  test    cx, cx
0x180007c27  jz      short loc_180007C33
0x180007c29  add     rax, 2
0x180007c2d  cmp     [rax], r12w
0x180007c31  jnz     short loc_180007C29
0x180007c33  add     rax, 2
0x180007c37  inc     r14d
0x180007c3a  movzx   ecx, word ptr [rax]
0x180007c3d  test    cx, cx
0x180007c40  jnz     short loc_180007C29
0x180007c42  mov     ecx, 0Ch; vt
0x180007c47  mov     [rbp+rgsabound.lLbound], r12d
0x180007c4b  lea     r8, [rbp+rgsabound]; rgsabound
0x180007c4f  mov     [rbp+rgsabound.cElements], r14d
0x180007c53  lea     edx, [rcx-0Bh]; cDims
0x180007c56  call    cs:__imp_SafeArrayCreate
0x180007c5c  mov     rsi, rax
0x180007c5f  test    rax, rax
0x180007c62  jz      loc_180007D61
0x180007c68  mov     [rbp+rgIndices], r12d
0x180007c6c  test    r14d, r14d
0x180007c6f  jle     loc_180007D0A
0x180007c75  xorps   xmm0, xmm0
0x180007c78  lea     rcx, [rbp+pvarg]; pvarg
0x180007c7c  xor     eax, eax
0x180007c7e  movups  xmmword ptr [rbp+pvarg], xmm0
0x180007c82  mov     qword ptr [rbp+pvarg+10h], rax
0x180007c86  call    cs:__imp_VariantInit
0x180007c8c  mov     eax, 8
0x180007c91  mov     word ptr [rbp+pvarg], ax
0x180007c95  test    rdi, rdi
0x180007c98  jnz     short loc_180007CA0
0x180007c9a  mov     qword ptr [rbp+pvarg+8], r12
0x180007c9e  jmp     short loc_180007CC2
0x180007ca0  mov     rcx, rdi; psz
0x180007ca3  call    cs:__imp_SysAllocString
0x180007ca9  mov     rcx, rax
0x180007cac  mov     qword ptr [rbp+pvarg+8], rax
0x180007cb0  neg     rcx
0x180007cb3  sbb     ebx, ebx
0x180007cb5  not     ebx
0x180007cb7  and     ebx, 8007000Eh
0x180007cbd  test    rax, rax
0x180007cc0  jz      short loc_180007D38
0x180007cc2  lea     r8, [rbp+pvarg]; pv
0x180007cc6  mov     rcx, rsi; psa
0x180007cc9  lea     rdx, [rbp+rgIndices]; rgIndices
0x180007ccd  call    cs:__imp_SafeArrayPutElement
0x180007cd3  lea     rcx, [rbp+pvarg]; pvarg
0x180007cd7  mov     ebx, eax
0x180007cd9  call    cs:__imp_VariantClear
0x180007cdf  test    ebx, ebx
0x180007ce1  js      short loc_180007D38
0x180007ce3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007ce7  inc     rax
0x180007cea  cmp     [rdi+rax*2], r12w
0x180007cef  jnz     short loc_180007CE7
0x180007cf1  lea     rdi, [rdi+rax*2]
0x180007cf5  mov     eax, [rbp+rgIndices]
0x180007cf8  inc     eax
0x180007cfa  add     rdi, 2
0x180007cfe  mov     [rbp+rgIndices], eax
0x180007d01  cmp     eax, r14d
0x180007d04  jl      loc_180007C75
0x180007d0a  mov     rcx, r15; pvarg
0x180007d0d  call    cs:__imp_VariantInit
0x180007d13  mov     word ptr [r15], 200Ch
0x180007d19  xor     eax, eax
0x180007d1b  mov     [r15+8], rsi
0x180007d1f  lea     r11, [rsp+40h+var_s0]
0x180007d24  mov     rbx, [r11+38h]
0x180007d28  mov     rsi, [r11+48h]
0x180007d2c  mov     rsp, r11
0x180007d2f  pop     r15
0x180007d31  pop     r14
0x180007d33  pop     r12
0x180007d35  pop     rdi
0x180007d36  pop     rbp
0x180007d37  retn
0x180007d38  mov     rcx, rsi; psa
0x180007d3b  call    cs:__imp_SafeArrayDestroy
0x180007d41  jmp     short loc_180007D66
0x180007d43  mov     ecx, 0Ch; vt
0x180007d48  mov     qword ptr [rbp+rgsabound.cElements], r12
0x180007d4c  lea     r8, [rbp+rgsabound]; rgsabound
0x180007d50  lea     edx, [rcx-0Bh]; cDims
0x180007d53  call    cs:__imp_SafeArrayCreate
0x180007d59  mov     rsi, rax
0x180007d5c  test    rax, rax
0x180007d5f  jnz     short loc_180007D0A
0x180007d61  mov     ebx, 8007000Eh
0x180007d66  mov     eax, ebx
0x180007d68  jmp     short loc_180007D1F
```
