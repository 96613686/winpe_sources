# CrackVarArgList(tagVARIANT * *,tagVARIANT *,char *,uint *)

- ea: `0x1800f1ad4`
- end: `0x1800f1c0a`
- name: `?CrackVarArgList@@YAJPEAPEAUtagVARIANT@@PEAU1@PEADPEAI@Z`
- size: `310`
- prototype: `HRESULT __fastcall(tagVARIANT **ppva, tagVARIANT *pvaStart, char *args, unsigned int *pcArgs)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800f1ed0`

## callees

- `0x1800f1ad4`
- `0x18018c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800f1bbe`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f1bbe`
- `OLEAUT32!__imp_VariantInit` at `0x1800f1b6c`
- `OLEAUT32!__imp_VariantInit` at `0x1800f1b6c`
- `OLEAUT32!__imp_VariantCopy` at `0x1800f1b7e`
- `OLEAUT32!__imp_VariantCopy` at `0x1800f1b7e`

## pseudocode

```c
HRESULT __fastcall CrackVarArgList(tagVARIANT **ppva, tagVARIANT *pvaStart, char *args, unsigned int *pcArgs)
{
  unsigned int v5; // ebp
  int v9; // eax
  tagVARIANT *v10; // rdi
  char *v11; // rsi
  HRESULT result; // eax
  __int64 v13; // rcx
  const OLECHAR *v14; // rcx
  BSTR v15; // rax

  v5 = 0;
  *pcArgs = 0;
  while ( 1 )
  {
    v9 = *(unsigned __int16 *)args;
    if ( !(_WORD)v9 )
      break;
    v10 = --*ppva;
    if ( *ppva == pvaStart )
      return -2147467259;
    args += 8;
    v10->vt = v9;
    v11 = args;
    switch ( v9 )
    {
      case 2:
LABEL_22:
        v10->iVal = *(_WORD *)args;
        goto LABEL_23;
      case 3:
        goto LABEL_14;
      case 8:
        v14 = *(const OLECHAR **)args;
        args += 8;
        v10->llVal = *(_QWORD *)v11;
        if ( v14 )
        {
          v15 = SysAllocString(v14);
          v10->llVal = (__int64)v15;
          if ( !v15 )
            return -2147024882;
        }
        break;
      default:
        if ( v9 != 9 )
        {
          if ( v9 == 11 )
            goto LABEL_22;
          if ( v9 == 12 )
          {
            VariantInit(v10);
            result = VariantCopy(v10, *(const VARIANTARG **)args);
            if ( result < 0 )
              return result;
            goto LABEL_23;
          }
          if ( v9 != 13 )
          {
            if ( v9 != 22 )
            {
              ++*ppva;
              --v5;
              break;
            }
            v10->vt = 3;
LABEL_14:
            v10->decVal.Lo32 = *(_DWORD *)args;
LABEL_23:
            args += 8;
            break;
          }
        }
        v13 = *(_QWORD *)args;
        args += 8;
        v10->llVal = *(_QWORD *)v11;
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
        break;
    }
    ++v5;
  }
  *pcArgs = v5;
  return 0;
}

```

## disassembly

```asm
0x1800f1ad4  push    rbx
0x1800f1ad6  push    rbp
0x1800f1ad7  push    rsi
0x1800f1ad8  push    rdi
0x1800f1ad9  push    r12
0x1800f1adb  push    r13
0x1800f1add  push    r14
0x1800f1adf  push    r15
0x1800f1ae1  sub     rsp, 28h
0x1800f1ae5  xor     r13d, r13d
0x1800f1ae8  mov     r15, pcArgs
0x1800f1aeb  mov     ebp, r13d
0x1800f1aee  mov     [pcArgs], r13d
0x1800f1af1  mov     rbx, args
0x1800f1af4  mov     r12, pvaStart
0x1800f1af7  mov     r14, ppva
0x1800f1afa  movzx   eax, word ptr [rbx]
0x1800f1afd  test    ax, ax
0x1800f1b00  jz      loc_1800F1BF3
0x1800f1b06  add     qword ptr [r14], 0FFFFFFFFFFFFFFE8h
0x1800f1b0a  mov     rdi, [r14]
0x1800f1b0d  cmp     rdi, r12
0x1800f1b10  jz      loc_1800F1BEC
0x1800f1b16  add     rbx, 8
0x1800f1b1a  mov     [rdi], ax
0x1800f1b1d  mov     ecx, eax
0x1800f1b1f  mov     rsi, rbx
0x1800f1b22  sub     ecx, 2
0x1800f1b25  jz      loc_1800F1BDA
0x1800f1b2b  sub     ecx, 1
0x1800f1b2e  jz      short loc_1800F1B62
0x1800f1b30  sub     ecx, 5
0x1800f1b33  jz      short loc_1800F1BAE
0x1800f1b35  sub     ecx, 1
0x1800f1b38  jz      short loc_1800F1B90
0x1800f1b3a  sub     ecx, 2
0x1800f1b3d  jz      loc_1800F1BDA
0x1800f1b43  sub     ecx, 1
0x1800f1b46  jz      short loc_1800F1B69
0x1800f1b48  sub     ecx, 1
0x1800f1b4b  jz      short loc_1800F1B90
0x1800f1b4d  cmp     ecx, 9
0x1800f1b50  jz      short loc_1800F1B5D
0x1800f1b52  add     qword ptr [r14], 18h
0x1800f1b56  dec     ebp
0x1800f1b58  jmp     loc_1800F1BE5
0x1800f1b5d  mov     word ptr [rdi], 3
0x1800f1b62  mov     eax, [rsi]
0x1800f1b64  mov     [rdi+8], eax
0x1800f1b67  jmp     short loc_1800F1BE1
0x1800f1b69  mov     ppva, rdi; pvarg
0x1800f1b6c  call    cs:__imp_VariantInit
0x1800f1b73  nop     dword ptr [rax+rax+00h]
0x1800f1b78  mov     pvaStart, [rbx]; pvargSrc
0x1800f1b7b  mov     ppva, rdi; pvargDest
0x1800f1b7e  call    cs:__imp_VariantCopy
0x1800f1b85  nop     dword ptr [rax+rax+00h]
0x1800f1b8a  test    eax, eax
0x1800f1b8c  js      short loc_1800F1BF8
0x1800f1b8e  jmp     short loc_1800F1BE1
0x1800f1b90  mov     ppva, [rsi]
0x1800f1b93  add     rbx, 8
0x1800f1b97  mov     [rdi+8], ppva
0x1800f1b9b  test    ppva, ppva
0x1800f1b9e  jz      short loc_1800F1BE5
0x1800f1ba0  mov     rax, [ppva]
0x1800f1ba3  mov     rax, [rax+8]
0x1800f1ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1bac  jmp     short loc_1800F1BE5
0x1800f1bae  mov     ppva, [rsi]; psz
0x1800f1bb1  add     rbx, 8
0x1800f1bb5  mov     [rdi+8], ppva
0x1800f1bb9  test    ppva, ppva
0x1800f1bbc  jz      short loc_1800F1BE5
0x1800f1bbe  call    cs:__imp_SysAllocString
0x1800f1bc5  nop     dword ptr [rax+rax+00h]
0x1800f1bca  mov     [rdi+8], rax
0x1800f1bce  test    rax, rax
0x1800f1bd1  jnz     short loc_1800F1BE5
0x1800f1bd3  mov     eax, 8007000Eh
0x1800f1bd8  jmp     short loc_1800F1BF8
0x1800f1bda  movzx   eax, word ptr [rsi]
0x1800f1bdd  mov     [rdi+8], ax
0x1800f1be1  add     rbx, 8
0x1800f1be5  inc     ebp
0x1800f1be7  jmp     loc_1800F1AFA
0x1800f1bec  mov     eax, 80004005h
0x1800f1bf1  jmp     short loc_1800F1BF8
0x1800f1bf3  mov     [r15], ebp
0x1800f1bf6  xor     eax, eax
0x1800f1bf8  add     rsp, 28h
0x1800f1bfc  pop     r15
0x1800f1bfe  pop     r14
0x1800f1c00  pop     r13
0x1800f1c02  pop     r12
0x1800f1c04  pop     rdi
0x1800f1c05  pop     rsi
0x1800f1c06  pop     rbp
0x1800f1c07  pop     rbx
0x1800f1c08  retn
```
