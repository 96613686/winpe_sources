# KerbFreeData

- ea: `0x1800113f0`
- end: `0x18001150c`
- name: `KerbFreeData`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `73`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030fc`
- `0x180004a20`
- `0x1800088c4`
- `0x1800100d0`
- `0x180010c60`
- `0x180011064`
- `0x180014380`
- `0x180019678`
- `0x180021574`
- `0x180029ae4`
- `0x18002db10`
- `0x1800301ec`
- `0x18003c830`
- `0x18003d070`
- `0x18003d3f0`
- `0x18003e488`
- `0x18003e9d8`
- `0x18003eb80`
- `0x180041758`
- `0x180041ff0`
- `0x180042470`
- `0x1800428e4`
- `0x180042a40`
- `0x1800533e0`
- `0x180054c88`
- `0x1800566a8`
- `0x180057f58`
- `0x180059bc4`
- `0x180059e18`
- `0x18006bf30`
- `0x180078db0`
- `0x1800816e0`
- `0x1800819b0`
- `0x180082ef4`
- `0x180084b74`
- `0x18008587c`
- `0x180086258`
- `0x1800872a0`
- `0x180088424`
- `0x18008868c`
- `0x18008e4f4`
- `0x1800911f0`
- `0x18009a738`
- `0x18009c8cc`
- `0x18009d1c4`
- `0x1800a6410`
- `0x1800a7d98`
- `0x1800a7f18`
- `0x1800a7fc8`
- `0x1800a8194`

## callees

- `0x1800113f0`
- `0x18006ccec`

## import_xrefs

- `MSASN1!ASN1_CreateModule` at `0x180011475`
- `MSASN1!ASN1_CreateModule` at `0x180011475`
- `MSASN1!ASN1_CloseDecoder` at `0x1800114ba`
- `MSASN1!ASN1_CloseDecoder` at `0x1800114ba`
- `MSASN1!ASN1_CreateDecoder` at `0x180011495`
- `MSASN1!ASN1_CreateDecoder` at `0x180011495`
- `MSASN1!ASN1_FreeDecoded` at `0x1800114aa`
- `MSASN1!ASN1_FreeDecoded` at `0x1800114aa`

## pseudocode

```c
void __fastcall KerbFreeData(unsigned int a1, __int64 a2)
{
  __int64 Module; // rax
  unsigned int v5; // eax
  __int64 v6; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
  {
    v6 = 0;
    if ( fKRB5ModuleStarted )
    {
      Module = KRB5_Module;
    }
    else
    {
      fKRB5ModuleStarted = 1;
      Module = ASN1_CreateModule(
                 0x10000,
                 1024,
                 4096,
                 81,
                 off_1800F62D0,
                 off_1800F6040,
                 off_1800F6560,
                 qword_1800FE8B0,
                 895644267);
      KRB5_Module = Module;
    }
    v5 = ASN1_CreateDecoder(Module, &v6, 0, 0, 0);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v5);
    }
    else
    {
      ASN1_FreeDecoded(v6, a2, a1);
      if ( v6 )
        ASN1_CloseDecoder();
    }
  }
}

```

## disassembly

```asm
0x1800113f0  test    rdx, rdx
0x1800113f3  jnz     short loc_1800113F6
0x1800113f5  retn
0x1800113f6  mov     [rsp+arg_0], rbx
0x1800113fb  mov     [rsp+arg_10], rsi
0x180011400  push    rdi
0x180011401  sub     rsp, 50h
0x180011405  xor     esi, esi
0x180011407  mov     rbx, rdx
0x18001140a  cmp     cs:?fKRB5ModuleStarted@@3HA, esi; int fKRB5ModuleStarted
0x180011410  mov     edi, ecx
0x180011412  mov     [rsp+58h+arg_8], rsi
0x180011417  jnz     loc_1800114D0
0x18001141d  mov     [rsp+58h+var_18], 3562726Bh
0x180011425  lea     rax, qword_1800FE8B0
0x18001142c  mov     [rsp+58h+var_20], rax
0x180011431  mov     edx, 400h
0x180011436  lea     rax, off_1800F6560
0x18001143d  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180011447  mov     [rsp+58h+var_28], rax
0x18001144c  mov     ecx, 10000h
0x180011451  lea     rax, off_1800F6040
0x180011458  mov     r9d, 51h ; 'Q'
0x18001145e  mov     [rsp+58h+var_30], rax
0x180011463  mov     r8d, 1000h
0x180011469  lea     rax, off_1800F62D0
0x180011470  mov     [rsp+58h+var_38], rax
0x180011475  call    cs:__imp_ASN1_CreateModule
0x18001147b  mov     cs:KRB5_Module, rax
0x180011482  xor     r9d, r9d
0x180011485  mov     [rsp+58h+var_38], rsi
0x18001148a  xor     r8d, r8d
0x18001148d  lea     rdx, [rsp+58h+arg_8]
0x180011492  mov     rcx, rax
0x180011495  call    cs:__imp_ASN1_CreateDecoder
0x18001149b  test    eax, eax
0x18001149d  jnz     short loc_1800114D9
0x18001149f  mov     rcx, [rsp+58h+arg_8]
0x1800114a4  mov     r8d, edi
0x1800114a7  mov     rdx, rbx
0x1800114aa  call    cs:__imp_ASN1_FreeDecoded
0x1800114b0  mov     rcx, [rsp+58h+arg_8]
0x1800114b5  test    rcx, rcx
0x1800114b8  jz      short loc_1800114C0
0x1800114ba  call    cs:__imp_ASN1_CloseDecoder
0x1800114c0  mov     rbx, [rsp+58h+arg_0]
0x1800114c5  mov     rsi, [rsp+58h+arg_10]
0x1800114ca  add     rsp, 50h
0x1800114ce  pop     rdi
0x1800114cf  retn
0x1800114d0  mov     rax, cs:KRB5_Module
0x1800114d7  jmp     short loc_180011482
0x1800114d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114e0  lea     rdx, WPP_GLOBAL_Control
0x1800114e7  cmp     rcx, rdx
0x1800114ea  jz      short loc_1800114C0
0x1800114ec  test    byte ptr [rcx+1Ch], 1
0x1800114f0  jz      short loc_1800114C0
0x1800114f2  mov     rcx, [rcx+10h]
0x1800114f6  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800114fd  mov     edx, 24h ; '$'
0x180011502  mov     r9d, eax
0x180011505  call    WPP_SF_D
0x18001150a  jmp     short loc_1800114C0
```
