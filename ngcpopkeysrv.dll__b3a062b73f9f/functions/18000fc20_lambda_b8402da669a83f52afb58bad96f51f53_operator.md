# _lambda_b8402da669a83f52afb58bad96f51f53_::operator()

- ea: `0x18000fc20`
- end: `0x18000fe20`
- name: `_lambda_b8402da669a83f52afb58bad96f51f53_::operator()`
- size: `512`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000d6d8`

## callees

- `0x18000b0fc`
- `0x18000d470`
- `0x18000d944`
- `0x18000d9d4`
- `0x18000dad8`
- `0x18000db18`
- `0x18000db34`
- `0x18000fc20`
- `0x18001070c`
- `0x180012ef0`
- `0x180012ff8`

## string_xrefs

- `0x18000fc4b`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`
- `0x18000fce2`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`
- `0x18000fdca`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall lambda_b8402da669a83f52afb58bad96f51f53_::operator()(__int64 a1)
{
  unsigned __int8 *v2; // rcx
  __int64 v3; // rdx
  unsigned int v5; // edx
  int SymmetricKeyBlob; // eax
  int v7; // edi
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-29h]
  int v11; // [rsp+20h] [rbp-29h]
  int v12; // [rsp+20h] [rbp-29h]
  unsigned __int8 *v13; // [rsp+60h] [rbp+17h] BYREF
  __int64 *v14; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned __int8 *v15; // [rsp+70h] [rbp+27h] BYREF
  char v16; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  unsigned int v18; // [rsp+B0h] [rbp+67h] BYREF
  unsigned int v19; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v20; // [rsp+C0h] [rbp+77h] BYREF
  struct NgcSymmetricPopKey *v21; // [rsp+C8h] [rbp+7Fh] BYREF

  v2 = **(unsigned __int8 ***)a1;
  if ( !v2 )
  {
    v3 = 1038;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)0x80090027LL,
      v10);
    return 2148073511LL;
  }
  v5 = **(_DWORD **)(a1 + 8);
  if ( !v5 )
  {
    v3 = 1039;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 16) )
  {
    v3 = 1040;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 24) )
  {
    v3 = 1041;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 32) )
  {
    v3 = 1042;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 40) )
  {
    v3 = 1043;
    goto LABEL_3;
  }
  v18 = 0;
  v19 = 0;
  v13 = 0;
  SymmetricKeyBlob = ValidateAndGetSymmetricKeyBlob(v2, v5, (enum _NGC_POP_KEY_TYPE *)&v18, &v13, &v19);
  v7 = SymmetricKeyBlob;
  if ( SymmetricKeyBlob >= 0 )
  {
    v21 = 0;
    if ( v18 == 2 )
      v8 = std::make_unique<TpmSymmetricPopKey,,0>(&v18);
    else
      v8 = std::make_unique<SoftwareSymmetricPopKey,,0>(&v18);
    std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(
      &v21,
      v8);
    std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(&v18);
    v18 = 0;
    v20 = 0;
    v14 = &v20;
    v15 = 0;
    v16 = 1;
    v7 = SignWithSymmetricPopKeyLocal(
           v21,
           v13,
           v19,
           **(unsigned __int8 ***)(a1 + 48),
           **(_DWORD **)(a1 + 56),
           **(unsigned __int8 ***)(a1 + 64),
           **(_DWORD **)(a1 + 72),
           **(unsigned __int8 ***)(a1 + 16),
           **(_DWORD **)(a1 + 24),
           &v15,
           &v18);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v14);
    if ( v7 >= 0 )
    {
      v9 = v20;
      v20 = 0;
      ***(_QWORD ***)(a1 + 32) = v9;
      ***(_DWORD ***)(a1 + 40) = v18;
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44A,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
        (const char *)(unsigned int)v7,
        v12);
    }
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v20, 0);
    std::unique_ptr<NgcSymmetricPopKey>::~unique_ptr<NgcSymmetricPopKey>(&v21);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)SymmetricKeyBlob,
      v11);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fc20  push    rbp
0x18000fc22  push    rbx
0x18000fc23  push    rsi
0x18000fc24  push    rdi
0x18000fc25  lea     rbp, [rsp-3Fh]
0x18000fc2a  sub     rsp, 88h
0x18000fc31  mov     rbx, rcx
0x18000fc34  mov     rax, [rcx]
0x18000fc37  mov     rcx, [rax]; unsigned __int8 *
0x18000fc3a  xor     esi, esi
0x18000fc3c  test    rcx, rcx
0x18000fc3f  jnz     short loc_18000FC65
0x18000fc41  mov     edx, 40Eh; void *
0x18000fc46  mov     ebx, 80090027h
0x18000fc4b  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18000fc52  mov     r9d, ebx; char *
0x18000fc55  mov     rcx, [rbp+5Fh]; this
0x18000fc59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc5e  mov     eax, ebx
0x18000fc60  jmp     loc_18000FE14
0x18000fc65  mov     rax, [rbx+8]
0x18000fc69  mov     edx, [rax]; unsigned int
0x18000fc6b  test    edx, edx
0x18000fc6d  jnz     short loc_18000FC76
0x18000fc6f  mov     edx, 40Fh
0x18000fc74  jmp     short loc_18000FC46
0x18000fc76  mov     rax, [rbx+10h]
0x18000fc7a  cmp     [rax], rsi
0x18000fc7d  jnz     short loc_18000FC86
0x18000fc7f  mov     edx, 410h
0x18000fc84  jmp     short loc_18000FC46
0x18000fc86  mov     rax, [rbx+18h]
0x18000fc8a  cmp     [rax], esi
0x18000fc8c  jnz     short loc_18000FC95
0x18000fc8e  mov     edx, 411h
0x18000fc93  jmp     short loc_18000FC46
0x18000fc95  mov     rax, [rbx+20h]
0x18000fc99  cmp     [rax], rsi
0x18000fc9c  jnz     short loc_18000FCA5
0x18000fc9e  mov     edx, 412h
0x18000fca3  jmp     short loc_18000FC46
0x18000fca5  mov     rax, [rbx+28h]
0x18000fca9  cmp     [rax], rsi
0x18000fcac  jnz     short loc_18000FCB5
0x18000fcae  mov     edx, 413h
0x18000fcb3  jmp     short loc_18000FC46
0x18000fcb5  mov     [rbp+57h+arg_0], esi
0x18000fcb8  mov     [rbp+57h+arg_8], esi
0x18000fcbb  mov     [rbp+57h+var_40], rsi
0x18000fcbf  lea     rax, [rbp+57h+arg_8]
0x18000fcc3  mov     [rsp+0A0h+var_80], rax; int
0x18000fcc8  lea     r9, [rbp+57h+var_40]; unsigned __int8 **
0x18000fccc  lea     r8, [rbp+57h+arg_0]; enum _NGC_POP_KEY_TYPE *
0x18000fcd0  call    ?ValidateAndGetSymmetricKeyBlob@@YAJPEAEKPEAW4_NGC_POP_KEY_TYPE@@PEAPEAEPEAK@Z; ValidateAndGetSymmetricKeyBlob(uchar *,ulong,_NGC_POP_KEY_TYPE *,uchar * *,ulong *)
0x18000fcd5  mov     edi, eax
0x18000fcd7  test    eax, eax
0x18000fcd9  jns     short loc_18000FCF8
0x18000fcdb  mov     rcx, [rbp+5Fh]; this
0x18000fcdf  mov     r9d, eax; char *
0x18000fce2  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18000fce9  mov     edx, 41Fh; void *
0x18000fcee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fcf3  jmp     loc_18000FE12
0x18000fcf8  mov     [rbp+57h+arg_18], rsi
0x18000fcfc  lea     rcx, [rbp+57h+arg_0]
0x18000fd00  cmp     [rbp+57h+arg_0], 2
0x18000fd04  jnz     short loc_18000FD22
0x18000fd06  call    ??$make_unique@VTpmSymmetricPopKey@@$$V$0A@@std@@YA?AV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@0@XZ; std::make_unique<TpmSymmetricPopKey,,0>(void)
0x18000fd0b  mov     rdx, rax
0x18000fd0e  lea     rcx, [rbp+57h+arg_18]
0x18000fd12  call    ??$?4VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@$0A@@?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@1@@Z; std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(std::unique_ptr<TpmSymmetricPopKey> &&)
0x18000fd17  lea     rcx, [rbp+57h+arg_0]
0x18000fd1b  call    ??1?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(void)
0x18000fd20  jmp     short loc_18000FD3C
0x18000fd22  call    ??$make_unique@VSoftwareSymmetricPopKey@@$$V$0A@@std@@YA?AV?$unique_ptr@VSoftwareSymmetricPopKey@@U?$default_delete@VSoftwareSymmetricPopKey@@@std@@@0@XZ; std::make_unique<SoftwareSymmetricPopKey,,0>(void)
0x18000fd27  mov     rdx, rax
0x18000fd2a  lea     rcx, [rbp+57h+arg_18]
0x18000fd2e  call    ??$?4VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@$0A@@?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@1@@Z; std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(std::unique_ptr<TpmSymmetricPopKey> &&)
0x18000fd33  lea     rcx, [rbp+57h+arg_0]
0x18000fd37  call    ??1?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(void)
0x18000fd3c  mov     [rbp+57h+arg_0], esi
0x18000fd3f  mov     [rbp+57h+arg_10], rsi
0x18000fd43  lea     rax, [rbp+57h+arg_10]
0x18000fd47  mov     [rbp+57h+var_38], rax
0x18000fd4b  mov     [rbp+57h+var_30], rsi
0x18000fd4f  mov     [rbp+57h+var_28], 1
0x18000fd53  mov     rax, [rbx+18h]
0x18000fd57  mov     rcx, [rbx+10h]
0x18000fd5b  mov     rdx, [rbx+48h]
0x18000fd5f  mov     r8, [rbx+40h]
0x18000fd63  mov     r10, [rbx+38h]
0x18000fd67  mov     r9, [rbx+30h]
0x18000fd6b  lea     r11, [rbp+57h+arg_0]
0x18000fd6f  mov     [rsp+0A0h+var_50], r11; unsigned int *
0x18000fd74  lea     r11, [rbp+57h+var_30]
0x18000fd78  mov     [rsp+0A0h+var_58], r11; unsigned __int8 **
0x18000fd7d  mov     eax, [rax]
0x18000fd7f  mov     [rsp+0A0h+var_60], eax; unsigned int
0x18000fd83  mov     rax, [rcx]
0x18000fd86  mov     [rsp+0A0h+var_68], rax; unsigned __int8 *
0x18000fd8b  mov     eax, [rdx]
0x18000fd8d  mov     [rsp+0A0h+var_70], eax; unsigned int
0x18000fd91  mov     rax, [r8]
0x18000fd94  mov     [rsp+0A0h+var_78], rax; unsigned __int8 *
0x18000fd99  mov     eax, [r10]
0x18000fd9c  mov     dword ptr [rsp+0A0h+var_80], eax; int
0x18000fda0  mov     r9, [r9]; unsigned __int8 *
0x18000fda3  mov     r8d, [rbp+57h+arg_8]; unsigned int
0x18000fda7  mov     rdx, [rbp+57h+var_40]; unsigned __int8 *
0x18000fdab  mov     rcx, [rbp+57h+arg_18]; struct NgcSymmetricPopKey *
0x18000fdaf  call    ?SignWithSymmetricPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1KPEAPEAEPEAK@Z; SignWithSymmetricPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18000fdb4  mov     edi, eax
0x18000fdb6  lea     rcx, [rbp+57h+var_38]
0x18000fdba  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18000fdbf  test    edi, edi
0x18000fdc1  jns     short loc_18000FDDD
0x18000fdc3  mov     rcx, [rbp+5Fh]; this
0x18000fdc7  mov     r9d, edi; char *
0x18000fdca  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18000fdd1  mov     edx, 44Ah; void *
0x18000fdd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fddb  jmp     short loc_18000FDFD
0x18000fddd  mov     rdx, [rbp+57h+arg_10]
0x18000fde1  mov     [rbp+57h+arg_10], rsi
0x18000fde5  mov     rax, [rbx+20h]
0x18000fde9  mov     rcx, [rax]
0x18000fdec  mov     [rcx], rdx
0x18000fdef  mov     rax, [rbx+28h]
0x18000fdf3  mov     rcx, [rax]
0x18000fdf6  mov     eax, [rbp+57h+arg_0]
0x18000fdf9  mov     [rcx], eax
0x18000fdfb  mov     edi, esi
0x18000fdfd  xor     edx, edx
0x18000fdff  lea     rcx, [rbp+57h+arg_10]
0x18000fe03  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18000fe08  nop
0x18000fe09  lea     rcx, [rbp+57h+arg_18]
0x18000fe0d  call    ??1?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcSymmetricPopKey>::~unique_ptr<NgcSymmetricPopKey>(void)
0x18000fe12  mov     eax, edi
0x18000fe14  add     rsp, 88h
0x18000fe1b  pop     rdi
0x18000fe1c  pop     rsi
0x18000fe1d  pop     rbx
0x18000fe1e  pop     rbp
0x18000fe1f  retn
```
