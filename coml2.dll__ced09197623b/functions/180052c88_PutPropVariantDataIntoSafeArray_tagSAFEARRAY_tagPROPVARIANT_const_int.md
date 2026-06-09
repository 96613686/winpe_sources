# PutPropVariantDataIntoSafeArray(tagSAFEARRAY *,tagPROPVARIANT const *,int)

- ea: `0x180052c88`
- end: `0x180052d4a`
- name: `?PutPropVariantDataIntoSafeArray@@YAJPEAUtagSAFEARRAY@@PEBUtagPROPVARIANT@@H@Z`
- size: `194`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, const struct tagPROPVARIANT *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180052378`

## callees

- `0x180052c88`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052d39`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052d39`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052caf`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180052caf`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180052d26`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180052d26`

## pseudocode

```c
__int64 __fastcall PutPropVariantDataIntoSafeArray(SAFEARRAY *psa, const PROPVARIANT *a2, LONG a3)
{
  VARTYPE v3; // bx
  HRESULT v5; // edi
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  PROPVARIANT *v13; // r8
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  PROPVARIANT pvarDest[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v21; // [rsp+30h] [rbp-18h]
  LONG rgIndices; // [rsp+80h] [rbp+38h] BYREF

  rgIndices = a3;
  v3 = *(_WORD *)a2;
  *(_OWORD *)pvarDest = 0;
  v21 = 0;
  v5 = PropVariantCopy(pvarDest, a2);
  if ( v5 >= 0 )
  {
    v6 = v3 & 0xFFF;
    if ( v6 > 0x47 )
      goto LABEL_22;
    if ( v6 != 71 )
    {
      if ( v6 > 0xA )
      {
        v14 = v6 - 11;
        if ( v14 )
        {
          v15 = v14 - 5;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              v17 = v16 - 1;
              if ( v17 )
              {
                v18 = v17 - 1;
                if ( v18 )
                {
                  if ( v18 - 1 > 1 )
                    goto LABEL_22;
                }
              }
            }
          }
        }
      }
      else if ( v6 != 10 )
      {
        v7 = v6 - 2;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( v10 )
              {
                v11 = v10 - 1;
                if ( v11 )
                {
                  v12 = v11 - 1;
                  if ( v12 )
                  {
                    if ( v12 == 1 )
                    {
                      v13 = (PROPVARIANT *)pvarDest[1];
LABEL_21:
                      v5 = SafeArrayPutElement(psa, &rgIndices, v13);
                      goto LABEL_23;
                    }
LABEL_22:
                    v5 = -2147352571;
                    goto LABEL_23;
                  }
                }
              }
            }
          }
        }
      }
    }
    v13 = &pvarDest[1];
    goto LABEL_21;
  }
LABEL_23:
  PropVariantClear(pvarDest);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180052c88  mov     [rsp-20h+rgIndices], r8d
0x180052c8d  push    rbp
0x180052c8e  push    rbx
0x180052c8f  push    rsi
0x180052c90  push    rdi
0x180052c91  mov     rbp, rsp
0x180052c94  sub     rsp, 48h
0x180052c98  movzx   ebx, word ptr [rdx]
0x180052c9b  mov     rsi, rcx
0x180052c9e  xorps   xmm0, xmm0
0x180052ca1  lea     rcx, [rbp+pvarDest]; pvarDest
0x180052ca5  xor     eax, eax
0x180052ca7  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180052cab  mov     [rbp+var_18], rax
0x180052caf  call    cs:__imp_PropVariantCopy
0x180052cb5  mov     edi, eax
0x180052cb7  test    eax, eax
0x180052cb9  js      short loc_180052D35
0x180052cbb  and     ebx, 0FFFh
0x180052cc1  cmp     ebx, 47h ; 'G'
0x180052cc4  ja      short loc_180052D30
0x180052cc6  jz      short loc_180052D1B
0x180052cc8  cmp     ebx, 0Ah
0x180052ccb  ja      short loc_180052CF8
0x180052ccd  jz      short loc_180052D1B
0x180052ccf  sub     ebx, 2
0x180052cd2  jz      short loc_180052D1B
0x180052cd4  sub     ebx, 1
0x180052cd7  jz      short loc_180052D1B
0x180052cd9  sub     ebx, 1
0x180052cdc  jz      short loc_180052D1B
0x180052cde  sub     ebx, 1
0x180052ce1  jz      short loc_180052D1B
0x180052ce3  sub     ebx, 1
0x180052ce6  jz      short loc_180052D1B
0x180052ce8  sub     ebx, 1
0x180052ceb  jz      short loc_180052D1B
0x180052ced  cmp     ebx, 1
0x180052cf0  jnz     short loc_180052D30
0x180052cf2  mov     r8, [rbp+pvarDest+8]
0x180052cf6  jmp     short loc_180052D1F
0x180052cf8  sub     ebx, 0Bh
0x180052cfb  jz      short loc_180052D1B
0x180052cfd  sub     ebx, 5
0x180052d00  jz      short loc_180052D1B
0x180052d02  sub     ebx, 1
0x180052d05  jz      short loc_180052D1B
0x180052d07  sub     ebx, 1
0x180052d0a  jz      short loc_180052D1B
0x180052d0c  sub     ebx, 1
0x180052d0f  jz      short loc_180052D1B
0x180052d11  sub     ebx, 1
0x180052d14  jz      short loc_180052D1B
0x180052d16  cmp     ebx, 1
0x180052d19  jnz     short loc_180052D30
0x180052d1b  lea     r8, [rbp+pvarDest+8]; pv
0x180052d1f  lea     rdx, [rbp+rgIndices]; rgIndices
0x180052d23  mov     rcx, rsi; psa
0x180052d26  call    cs:__imp_SafeArrayPutElement
0x180052d2c  mov     edi, eax
0x180052d2e  jmp     short loc_180052D35
0x180052d30  mov     edi, 80020005h
0x180052d35  lea     rcx, [rbp+pvarDest]; pvar
0x180052d39  call    cs:__imp_PropVariantClear
0x180052d3f  mov     eax, edi
0x180052d41  add     rsp, 48h
0x180052d45  pop     rdi
0x180052d46  pop     rsi
0x180052d47  pop     rbx
0x180052d48  pop     rbp
0x180052d49  retn
```
