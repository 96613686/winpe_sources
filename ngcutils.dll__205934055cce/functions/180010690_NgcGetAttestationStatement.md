# NgcGetAttestationStatement

- ea: `0x180010690`
- end: `0x180010868`
- name: `NgcGetAttestationStatement`
- size: `472`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a5b4`
- `0x180010690`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001076d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001076d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800107f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800107f2`
- `ncrypt!NCryptCreateClaim` at `0x180010749`
- `ncrypt!NCryptCreateClaim` at `0x1800107ca`
- `ncrypt!NCryptCreateClaim` at `0x180010749`
- `ncrypt!NCryptCreateClaim` at `0x1800107ca`

## string_xrefs

- `0x1800106cc`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x1800106fe`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x180010831`: `onecore\ds\security\ngc\utils\common\dll\entrypoints.cpp`
- `0x1800107de`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180010818`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcGetAttestationStatement(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  int Claim; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rdx
  HLOCAL v13; // rdi
  int v14; // eax
  int v15; // [rsp+20h] [rbp-48h]
  int v16; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v15);
    return 2147500035LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
      (const char *)0x80004003LL,
      v15);
    return 2147500035LL;
  }
  *a4 = 0;
  Claim = NCryptCreateClaim(a1, a2, 2, a3);
  v10 = Claim;
  if ( Claim < 0 )
  {
    v11 = (unsigned int)Claim;
    v12 = 507;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)v11,
      0);
    goto LABEL_13;
  }
  v13 = LocalAlloc(0, 0);
  if ( !v13 )
  {
    v10 = -2147024882;
    v11 = 2147942414LL;
    v12 = 510;
    goto LABEL_12;
  }
  v14 = NCryptCreateClaim(a1, a2, 2, a3);
  v10 = v14;
  if ( v14 >= 0 )
  {
    *a4 = v13;
    *a5 = 0;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x208,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
    (const char *)(unsigned int)v14,
    (int)v13);
  LocalFree(v13);
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE5,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\dll\\entrypoints.cpp",
    (const char *)v10,
    v16);
  return v10;
}

```

## disassembly

```asm
0x180010690  mov     [rsp+arg_8], rbx
0x180010695  mov     [rsp+arg_10], rsi
0x18001069a  mov     [rsp+arg_0], rcx
0x18001069f  push    rdi
0x1800106a0  push    r12
0x1800106a2  push    r13
0x1800106a4  push    r14
0x1800106a6  push    r15
0x1800106a8  sub     rsp, 40h
0x1800106ac  mov     rsi, r9
0x1800106af  mov     r12, r8
0x1800106b2  mov     r13, rdx
0x1800106b5  mov     rax, rcx
0x1800106b8  xor     edx, edx
0x1800106ba  test    r9, r9
0x1800106bd  jnz     short loc_1800106E4
0x1800106bf  mov     rcx, [rsp+68h]; this
0x1800106c4  mov     ebx, 80004003h
0x1800106c9  mov     r9d, ebx; char *
0x1800106cc  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800106d3  mov     edx, 0DEh; void *
0x1800106d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106dd  mov     eax, ebx
0x1800106df  jmp     loc_18001084D
0x1800106e4  mov     r14, [rsp+68h+arg_20]
0x1800106ec  test    r14, r14
0x1800106ef  jnz     short loc_180010716
0x1800106f1  mov     rcx, [rsp+68h]; this
0x1800106f6  mov     ebx, 80004003h
0x1800106fb  mov     r9d, ebx; char *
0x1800106fe  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010705  mov     edx, 0DFh; void *
0x18001070a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001070f  mov     eax, ebx
0x180010711  jmp     loc_18001084D
0x180010716  mov     [r9], rdx
0x180010719  mov     dword ptr [rsp+68h+uBytes], edx
0x180010720  mov     [rsp+68h+var_30], edx
0x180010724  lea     rcx, [rsp+68h+uBytes]
0x18001072c  mov     [rsp+68h+var_38], rcx
0x180010731  mov     [rsp+68h+var_40], edx
0x180010735  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001073a  mov     r9, r12
0x18001073d  mov     r8d, 2
0x180010743  mov     rdx, r13
0x180010746  mov     rcx, rax
0x180010749  call    cs:__imp_NCryptCreateClaim
0x18001074f  mov     ebx, eax
0x180010751  test    eax, eax
0x180010753  jns     short loc_180010762
0x180010755  mov     r9d, eax
0x180010758  mov     edx, 1FBh
0x18001075d  jmp     loc_180010818
0x180010762  mov     ebx, dword ptr [rsp+68h+uBytes]
0x180010769  mov     edx, ebx; uBytes
0x18001076b  xor     ecx, ecx; uFlags
0x18001076d  call    cs:__imp_LocalAlloc
0x180010773  mov     rdi, rax
0x180010776  test    rax, rax
0x180010779  jz      loc_18001080B
0x18001077f  lea     rcx, [rbx+rax]
0x180010783  cmp     rax, rcx
0x180010786  jz      short loc_180010794
0x180010788  xor     edx, edx
0x18001078a  mov     [rax], dl
0x18001078c  inc     rax
0x18001078f  cmp     rax, rcx
0x180010792  jnz     short loc_180010788
0x180010794  mov     eax, dword ptr [rsp+68h+uBytes]
0x18001079b  mov     [rsp+68h+var_30], 0
0x1800107a3  lea     rcx, [rsp+68h+uBytes]
0x1800107ab  mov     [rsp+68h+var_38], rcx
0x1800107b0  mov     [rsp+68h+var_40], eax
0x1800107b4  mov     qword ptr [rsp+68h+var_48], rdi; int
0x1800107b9  mov     r9, r12
0x1800107bc  mov     r8d, 2
0x1800107c2  mov     rdx, r13
0x1800107c5  mov     rcx, [rsp+68h+arg_0]
0x1800107ca  call    cs:__imp_NCryptCreateClaim
0x1800107d0  mov     ebx, eax
0x1800107d2  test    eax, eax
0x1800107d4  jns     short loc_1800107FA
0x1800107d6  mov     rcx, [rsp+68h]; this
0x1800107db  mov     r9d, eax; char *
0x1800107de  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800107e5  mov     edx, 208h; void *
0x1800107ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107ef  mov     rcx, rdi; hMem
0x1800107f2  call    cs:__imp_LocalFree
0x1800107f8  jmp     short loc_180010829
0x1800107fa  mov     eax, dword ptr [rsp+68h+uBytes]
0x180010801  mov     [rsi], rdi
0x180010804  mov     [r14], eax
0x180010807  xor     eax, eax
0x180010809  jmp     short loc_18001084D
0x18001080b  mov     ebx, 8007000Eh
0x180010810  mov     r9d, ebx; char *
0x180010813  mov     edx, 1FEh; void *
0x180010818  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001081f  mov     rcx, [rsp+68h]; this
0x180010824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010829  mov     rcx, [rsp+68h]; this
0x18001082e  mov     r9d, ebx; char *
0x180010831  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180010838  mov     edx, 0E5h; void *
0x18001083d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010842  mov     eax, ebx
0x180010844  jmp     short loc_18001084D
0x180010846  mov     eax, dword ptr [rsp+68h+uBytes]
0x18001084d  lea     r11, [rsp+68h+var_28]
0x180010852  mov     rbx, [r11+38h]
0x180010856  mov     rsi, [r11+40h]
0x18001085a  mov     rsp, r11
0x18001085d  pop     r15
0x18001085f  pop     r14
0x180010861  pop     r13
0x180010863  pop     r12
0x180010865  pop     rdi
0x180010866  retn
```
