# CrackVarArgList(tagVARIANT * *,tagVARIANT *,char *,uint *)

- ea: `0x1800ef6d4`
- end: `0x1800ef7f4`
- name: `?CrackVarArgList@@YAJPEAPEAUtagVARIANT@@PEAU1@PEADPEAI@Z`
- size: `288`
- prototype: `HRESULT __fastcall(tagVARIANT **ppva, tagVARIANT *pvaStart, char *args, unsigned int *pcArgs)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800efac0`

## callees

- `0x1800ef6d4`
- `0x180188010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800ef7af`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ef7af`
- `OLEAUT32!__imp_VariantInit` at `0x1800ef769`
- `OLEAUT32!__imp_VariantInit` at `0x1800ef769`
- `OLEAUT32!__imp_VariantCopy` at `0x1800ef775`
- `OLEAUT32!__imp_VariantCopy` at `0x1800ef775`

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
0x1800ef6d4  push    rbx
0x1800ef6d6  push    rbp
0x1800ef6d7  push    rsi
0x1800ef6d8  push    rdi
0x1800ef6d9  push    r12
0x1800ef6db  push    r13
0x1800ef6dd  push    r14
0x1800ef6df  push    r15
0x1800ef6e1  sub     rsp, 28h
0x1800ef6e5  xor     r13d, r13d
0x1800ef6e8  mov     r15, pcArgs
0x1800ef6eb  mov     ebp, r13d
0x1800ef6ee  mov     [pcArgs], r13d
0x1800ef6f1  mov     rbx, args
0x1800ef6f4  mov     r12, pvaStart
0x1800ef6f7  mov     r14, ppva
0x1800ef6fa  movzx   eax, word ptr [rbx]
0x1800ef6fd  test    ax, ax
0x1800ef700  jz      loc_1800EF7DE
0x1800ef706  add     qword ptr [r14], 0FFFFFFFFFFFFFFE8h
0x1800ef70a  mov     rdi, [r14]
0x1800ef70d  cmp     rdi, r12
0x1800ef710  jz      loc_1800EF7D7
0x1800ef716  add     rbx, 8
0x1800ef71a  mov     [rdi], ax
0x1800ef71d  mov     ecx, eax
0x1800ef71f  mov     rsi, rbx
0x1800ef722  sub     ecx, 2
0x1800ef725  jz      loc_1800EF7C5
0x1800ef72b  sub     ecx, 1
0x1800ef72e  jz      short loc_1800EF75F
0x1800ef730  sub     ecx, 5
0x1800ef733  jz      short loc_1800EF79F
0x1800ef735  sub     ecx, 1
0x1800ef738  jz      short loc_1800EF781
0x1800ef73a  sub     ecx, 2
0x1800ef73d  jz      loc_1800EF7C5
0x1800ef743  sub     ecx, 1
0x1800ef746  jz      short loc_1800EF766
0x1800ef748  sub     ecx, 1
0x1800ef74b  jz      short loc_1800EF781
0x1800ef74d  cmp     ecx, 9
0x1800ef750  jz      short loc_1800EF75A
0x1800ef752  add     qword ptr [r14], 18h
0x1800ef756  dec     ebp
0x1800ef758  jmp     short loc_1800EF7D0
0x1800ef75a  mov     word ptr [rdi], 3
0x1800ef75f  mov     eax, [rsi]
0x1800ef761  mov     [rdi+8], eax
0x1800ef764  jmp     short loc_1800EF7CC
0x1800ef766  mov     ppva, rdi; pvarg
0x1800ef769  call    cs:__imp_VariantInit
0x1800ef76f  mov     pvaStart, [rbx]; pvargSrc
0x1800ef772  mov     ppva, rdi; pvargDest
0x1800ef775  call    cs:__imp_VariantCopy
0x1800ef77b  test    eax, eax
0x1800ef77d  js      short loc_1800EF7E3
0x1800ef77f  jmp     short loc_1800EF7CC
0x1800ef781  mov     ppva, [rsi]
0x1800ef784  add     rbx, 8
0x1800ef788  mov     [rdi+8], ppva
0x1800ef78c  test    ppva, ppva
0x1800ef78f  jz      short loc_1800EF7D0
0x1800ef791  mov     rax, [ppva]
0x1800ef794  mov     rax, [rax+8]
0x1800ef798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef79d  jmp     short loc_1800EF7D0
0x1800ef79f  mov     ppva, [rsi]; psz
0x1800ef7a2  add     rbx, 8
0x1800ef7a6  mov     [rdi+8], ppva
0x1800ef7aa  test    ppva, ppva
0x1800ef7ad  jz      short loc_1800EF7D0
0x1800ef7af  call    cs:__imp_SysAllocString
0x1800ef7b5  mov     [rdi+8], rax
0x1800ef7b9  test    rax, rax
0x1800ef7bc  jnz     short loc_1800EF7D0
0x1800ef7be  mov     eax, 8007000Eh
0x1800ef7c3  jmp     short loc_1800EF7E3
0x1800ef7c5  movzx   eax, word ptr [rsi]
0x1800ef7c8  mov     [rdi+8], ax
0x1800ef7cc  add     rbx, 8
0x1800ef7d0  inc     ebp
0x1800ef7d2  jmp     loc_1800EF6FA
0x1800ef7d7  mov     eax, 80004005h
0x1800ef7dc  jmp     short loc_1800EF7E3
0x1800ef7de  mov     [r15], ebp
0x1800ef7e1  xor     eax, eax
0x1800ef7e3  add     rsp, 28h
0x1800ef7e7  pop     r15
0x1800ef7e9  pop     r14
0x1800ef7eb  pop     r13
0x1800ef7ed  pop     r12
0x1800ef7ef  pop     rdi
0x1800ef7f0  pop     rsi
0x1800ef7f1  pop     rbp
0x1800ef7f2  pop     rbx
0x1800ef7f3  retn
```
