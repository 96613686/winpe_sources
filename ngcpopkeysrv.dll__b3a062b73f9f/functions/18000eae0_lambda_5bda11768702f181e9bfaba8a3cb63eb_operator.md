# _lambda_5bda11768702f181e9bfaba8a3cb63eb_::operator()

- ea: `0x18000eae0`
- end: `0x18000edad`
- name: `_lambda_5bda11768702f181e9bfaba8a3cb63eb_::operator()`
- size: `717`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000d57c`

## callees

- `0x18000b0fc`
- `0x18000d470`
- `0x18000d944`
- `0x18000d9d4`
- `0x18000dad8`
- `0x18000db18`
- `0x18000db34`
- `0x18000eae0`
- `0x18001070c`
- `0x180012a08`
- `0x180012ff8`

## string_xrefs

- `0x18000eb1a`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`
- `0x18000ed49`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall lambda_5bda11768702f181e9bfaba8a3cb63eb_::operator()(__int64 a1)
{
  unsigned __int8 *v2; // rcx
  __int64 v3; // rdx
  int SymmetricKeyBlob; // ebx
  unsigned int v5; // edx
  __int64 v6; // rax
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-79h]
  int v10; // [rsp+20h] [rbp-79h]
  unsigned __int8 *v11; // [rsp+90h] [rbp-9h] BYREF
  __int64 *v12; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int8 *v13; // [rsp+A0h] [rbp+7h] BYREF
  char v14; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  unsigned int v16; // [rsp+100h] [rbp+67h] BYREF
  unsigned int v17; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v18; // [rsp+110h] [rbp+77h] BYREF
  struct NgcSymmetricPopKey *v19; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = **(unsigned __int8 ***)a1;
  if ( !v2 )
  {
    v3 = 1531;
LABEL_3:
    SymmetricKeyBlob = -2146893785;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)SymmetricKeyBlob,
      v9);
    return (unsigned int)SymmetricKeyBlob;
  }
  v5 = **(_DWORD **)(a1 + 8);
  if ( !v5 )
  {
    v3 = 1532;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 16) )
  {
    v3 = 1533;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 24) )
  {
    v3 = 1534;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 32) )
  {
    v3 = 1535;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 40) )
  {
    v3 = 1536;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 48) )
  {
    v3 = 1537;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 56) )
  {
    v3 = 1538;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 64) )
  {
    v3 = 1539;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 72) )
  {
    v3 = 1540;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 80) )
  {
    v3 = 1541;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 88) )
  {
    v3 = 1542;
    goto LABEL_3;
  }
  v16 = 0;
  v17 = 0;
  v11 = 0;
  SymmetricKeyBlob = ValidateAndGetSymmetricKeyBlob(v2, v5, (enum _NGC_POP_KEY_TYPE *)&v16, &v11, &v17);
  if ( SymmetricKeyBlob < 0 )
  {
    v3 = 1554;
    goto LABEL_4;
  }
  v19 = 0;
  if ( v16 == 2 )
    v6 = std::make_unique<TpmSymmetricPopKey,,0>(&v16);
  else
    v6 = std::make_unique<SoftwareSymmetricPopKey,,0>(&v16);
  std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(&v19, v6);
  std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(&v16);
  v16 = 0;
  v18 = 0;
  v12 = &v18;
  v13 = 0;
  v14 = 1;
  SymmetricKeyBlob = DecryptWithSymmetricGcmPopKeyLocal(
                       v19,
                       v11,
                       v17,
                       **(unsigned __int8 ***)(a1 + 96),
                       **(_DWORD **)(a1 + 104),
                       **(unsigned __int8 ***)(a1 + 112),
                       **(_DWORD **)(a1 + 120),
                       **(unsigned __int8 ***)(a1 + 32),
                       **(_DWORD **)(a1 + 40),
                       **(unsigned __int8 ***)(a1 + 48),
                       **(_DWORD **)(a1 + 56),
                       **(unsigned __int8 ***)(a1 + 64),
                       **(_DWORD **)(a1 + 72),
                       **(unsigned __int8 ***)(a1 + 16),
                       **(_DWORD **)(a1 + 24),
                       &v13,
                       &v16);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v12);
  if ( SymmetricKeyBlob >= 0 )
  {
    v7 = v18;
    v18 = 0;
    ***(_QWORD ***)(a1 + 80) = v7;
    ***(_DWORD ***)(a1 + 88) = v16;
    SymmetricKeyBlob = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x631,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\ngcpopkeyrpc.cpp",
      (const char *)(unsigned int)SymmetricKeyBlob,
      v10);
  }
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v18, 0);
  std::unique_ptr<NgcSymmetricPopKey>::~unique_ptr<NgcSymmetricPopKey>(&v19);
  return (unsigned int)SymmetricKeyBlob;
}

```

## disassembly

```asm
0x18000eae0  push    rbp
0x18000eae2  push    rbx
0x18000eae3  push    rsi
0x18000eae4  push    rdi
0x18000eae5  push    r12
0x18000eae7  push    r13
0x18000eae9  push    r14
0x18000eaeb  push    r15
0x18000eaed  lea     rbp, [rsp-1Fh]
0x18000eaf2  sub     rsp, 0B8h
0x18000eaf9  mov     r12, rcx
0x18000eafc  mov     rax, [rcx]
0x18000eaff  mov     rcx, [rax]; unsigned __int8 *
0x18000eb02  xor     edi, edi
0x18000eb04  test    rcx, rcx
0x18000eb07  jnz     short loc_18000EB2B
0x18000eb09  mov     edx, 5FBh; void *
0x18000eb0e  mov     ebx, 80090027h
0x18000eb13  mov     rcx, [rbp+5Fh]; this
0x18000eb17  mov     r9d, ebx; char *
0x18000eb1a  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18000eb21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb26  jmp     loc_18000ED97
0x18000eb2b  mov     rax, [r12+8]
0x18000eb30  mov     edx, [rax]; unsigned int
0x18000eb32  test    edx, edx
0x18000eb34  jnz     short loc_18000EB3D
0x18000eb36  mov     edx, 5FCh
0x18000eb3b  jmp     short loc_18000EB0E
0x18000eb3d  mov     rax, [r12+10h]
0x18000eb42  cmp     [rax], rdi
0x18000eb45  jnz     short loc_18000EB4E
0x18000eb47  mov     edx, 5FDh
0x18000eb4c  jmp     short loc_18000EB0E
0x18000eb4e  mov     rax, [r12+18h]
0x18000eb53  cmp     [rax], edi
0x18000eb55  jnz     short loc_18000EB5E
0x18000eb57  mov     edx, 5FEh
0x18000eb5c  jmp     short loc_18000EB0E
0x18000eb5e  mov     rax, [r12+20h]
0x18000eb63  cmp     [rax], rdi
0x18000eb66  jnz     short loc_18000EB6F
0x18000eb68  mov     edx, 5FFh
0x18000eb6d  jmp     short loc_18000EB0E
0x18000eb6f  mov     rax, [r12+28h]
0x18000eb74  cmp     [rax], edi
0x18000eb76  jnz     short loc_18000EB7F
0x18000eb78  mov     edx, 600h
0x18000eb7d  jmp     short loc_18000EB0E
0x18000eb7f  mov     rax, [r12+30h]
0x18000eb84  cmp     [rax], rdi
0x18000eb87  jnz     short loc_18000EB93
0x18000eb89  mov     edx, 601h
0x18000eb8e  jmp     loc_18000EB0E
0x18000eb93  mov     rax, [r12+38h]
0x18000eb98  cmp     [rax], edi
0x18000eb9a  jnz     short loc_18000EBA6
0x18000eb9c  mov     edx, 602h
0x18000eba1  jmp     loc_18000EB0E
0x18000eba6  mov     rax, [r12+40h]
0x18000ebab  cmp     [rax], rdi
0x18000ebae  jnz     short loc_18000EBBA
0x18000ebb0  mov     edx, 603h
0x18000ebb5  jmp     loc_18000EB0E
0x18000ebba  mov     rax, [r12+48h]
0x18000ebbf  cmp     [rax], edi
0x18000ebc1  jnz     short loc_18000EBCD
0x18000ebc3  mov     edx, 604h
0x18000ebc8  jmp     loc_18000EB0E
0x18000ebcd  mov     rax, [r12+50h]
0x18000ebd2  cmp     [rax], rdi
0x18000ebd5  jnz     short loc_18000EBE1
0x18000ebd7  mov     edx, 605h
0x18000ebdc  jmp     loc_18000EB0E
0x18000ebe1  mov     rax, [r12+58h]
0x18000ebe6  cmp     [rax], rdi
0x18000ebe9  jnz     short loc_18000EBF5
0x18000ebeb  mov     edx, 606h
0x18000ebf0  jmp     loc_18000EB0E
0x18000ebf5  mov     [rbp+57h+arg_0], edi
0x18000ebf8  mov     [rbp+57h+arg_8], edi
0x18000ebfb  mov     [rbp+57h+var_60], rdi
0x18000ebff  lea     rax, [rbp+57h+arg_8]
0x18000ec03  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18000ec08  lea     r9, [rbp+57h+var_60]; unsigned __int8 **
0x18000ec0c  lea     r8, [rbp+57h+arg_0]; enum _NGC_POP_KEY_TYPE *
0x18000ec10  call    ?ValidateAndGetSymmetricKeyBlob@@YAJPEAEKPEAW4_NGC_POP_KEY_TYPE@@PEAPEAEPEAK@Z; ValidateAndGetSymmetricKeyBlob(uchar *,ulong,_NGC_POP_KEY_TYPE *,uchar * *,ulong *)
0x18000ec15  mov     ebx, eax
0x18000ec17  test    eax, eax
0x18000ec19  jns     short loc_18000EC25
0x18000ec1b  mov     edx, 612h
0x18000ec20  jmp     loc_18000EB13
0x18000ec25  mov     [rbp+57h+arg_18], rdi
0x18000ec29  lea     rcx, [rbp+57h+arg_0]
0x18000ec2d  cmp     [rbp+57h+arg_0], 2
0x18000ec31  jnz     short loc_18000EC4F
0x18000ec33  call    ??$make_unique@VTpmSymmetricPopKey@@$$V$0A@@std@@YA?AV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@0@XZ; std::make_unique<TpmSymmetricPopKey,,0>(void)
0x18000ec38  mov     rdx, rax
0x18000ec3b  lea     rcx, [rbp+57h+arg_18]
0x18000ec3f  call    ??$?4VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@$0A@@?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@1@@Z; std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(std::unique_ptr<TpmSymmetricPopKey> &&)
0x18000ec44  lea     rcx, [rbp+57h+arg_0]
0x18000ec48  call    ??1?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(void)
0x18000ec4d  jmp     short loc_18000EC69
0x18000ec4f  call    ??$make_unique@VSoftwareSymmetricPopKey@@$$V$0A@@std@@YA?AV?$unique_ptr@VSoftwareSymmetricPopKey@@U?$default_delete@VSoftwareSymmetricPopKey@@@std@@@0@XZ; std::make_unique<SoftwareSymmetricPopKey,,0>(void)
0x18000ec54  mov     rdx, rax
0x18000ec57  lea     rcx, [rbp+57h+arg_18]
0x18000ec5b  call    ??$?4VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@$0A@@?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@1@@Z; std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(std::unique_ptr<TpmSymmetricPopKey> &&)
0x18000ec60  lea     rcx, [rbp+57h+arg_0]
0x18000ec64  call    ??1?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(void)
0x18000ec69  mov     [rbp+57h+arg_0], edi
0x18000ec6c  mov     [rbp+57h+arg_10], rdi
0x18000ec70  lea     rax, [rbp+57h+arg_10]
0x18000ec74  mov     [rbp+57h+var_58], rax
0x18000ec78  mov     [rbp+57h+var_50], rdi
0x18000ec7c  mov     [rbp+57h+var_48], 1
0x18000ec80  mov     rax, [r12+18h]
0x18000ec85  mov     rcx, [r12+10h]
0x18000ec8a  mov     rdx, [r12+48h]
0x18000ec8f  mov     r8, [r12+40h]
0x18000ec94  mov     r10, [r12+38h]
0x18000ec99  mov     r11, [r12+30h]
0x18000ec9e  mov     rbx, [r12+28h]
0x18000eca3  mov     rdi, [r12+20h]
0x18000eca8  mov     rsi, [r12+78h]
0x18000ecad  mov     r14, [r12+70h]
0x18000ecb2  mov     r15, [r12+68h]
0x18000ecb7  mov     r9, [r12+60h]
0x18000ecbc  lea     r13, [rbp+57h+arg_0]
0x18000ecc0  mov     [rsp+0F0h+var_70], r13; unsigned int *
0x18000ecc8  lea     r13, [rbp+57h+var_50]
0x18000eccc  mov     [rsp+0F0h+var_78], r13; unsigned __int8 **
0x18000ecd1  mov     eax, [rax]
0x18000ecd3  mov     [rsp+0F0h+var_80], eax; unsigned int
0x18000ecd7  mov     rax, [rcx]
0x18000ecda  mov     [rsp+0F0h+var_88], rax; unsigned __int8 *
0x18000ecdf  mov     eax, [rdx]
0x18000ece1  mov     [rsp+0F0h+var_90], eax; unsigned int
0x18000ece5  mov     rax, [r8]
0x18000ece8  mov     [rsp+0F0h+var_98], rax; unsigned __int8 *
0x18000eced  mov     eax, [r10]
0x18000ecf0  mov     [rsp+0F0h+var_A0], eax; unsigned int
0x18000ecf4  mov     rax, [r11]
0x18000ecf7  mov     [rsp+0F0h+var_A8], rax; unsigned __int8 *
0x18000ecfc  mov     eax, [rbx]
0x18000ecfe  mov     [rsp+0F0h+var_B0], eax; unsigned int
0x18000ed02  mov     rax, [rdi]
0x18000ed05  mov     [rsp+0F0h+var_B8], rax; unsigned __int8 *
0x18000ed0a  mov     eax, [rsi]
0x18000ed0c  mov     [rsp+0F0h+var_C0], eax; unsigned int
0x18000ed10  mov     rax, [r14]
0x18000ed13  mov     [rsp+0F0h+var_C8], rax; unsigned __int8 *
0x18000ed18  mov     eax, [r15]
0x18000ed1b  mov     dword ptr [rsp+0F0h+var_D0], eax; int
0x18000ed1f  mov     r9, [r9]; unsigned __int8 *
0x18000ed22  mov     r8d, [rbp+57h+arg_8]; unsigned int
0x18000ed26  mov     rdx, [rbp+57h+var_60]; unsigned __int8 *
0x18000ed2a  mov     rcx, [rbp+57h+arg_18]; this
0x18000ed2e  call    ?DecryptWithSymmetricGcmPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1K1K1K1KPEAPEAEPEAK@Z; DecryptWithSymmetricGcmPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18000ed33  mov     ebx, eax
0x18000ed35  lea     rcx, [rbp+57h+var_58]
0x18000ed39  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18000ed3e  test    ebx, ebx
0x18000ed40  jns     short loc_18000ED5C
0x18000ed42  mov     rcx, [rbp+5Fh]; this
0x18000ed46  mov     r9d, ebx; char *
0x18000ed49  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18000ed50  mov     edx, 631h; void *
0x18000ed55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ed5a  jmp     short loc_18000ED82
0x18000ed5c  mov     rdx, [rbp+57h+arg_10]
0x18000ed60  mov     [rbp+57h+arg_10], 0
0x18000ed68  mov     rax, [r12+50h]
0x18000ed6d  mov     rcx, [rax]
0x18000ed70  mov     [rcx], rdx
0x18000ed73  mov     rax, [r12+58h]
0x18000ed78  mov     rcx, [rax]
0x18000ed7b  mov     eax, [rbp+57h+arg_0]
0x18000ed7e  mov     [rcx], eax
0x18000ed80  xor     ebx, ebx
0x18000ed82  xor     edx, edx
0x18000ed84  lea     rcx, [rbp+57h+arg_10]
0x18000ed88  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18000ed8d  nop
0x18000ed8e  lea     rcx, [rbp+57h+arg_18]
0x18000ed92  call    ??1?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcSymmetricPopKey>::~unique_ptr<NgcSymmetricPopKey>(void)
0x18000ed97  mov     eax, ebx
0x18000ed99  add     rsp, 0B8h
0x18000eda0  pop     r15
0x18000eda2  pop     r14
0x18000eda4  pop     r13
0x18000eda6  pop     r12
0x18000eda8  pop     rdi
0x18000eda9  pop     rsi
0x18000edaa  pop     rbx
0x18000edab  pop     rbp
0x18000edac  retn
```
