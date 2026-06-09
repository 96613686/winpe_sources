# _lambda_0777c056401d5fa7da1ccdfb87aa96b5_::operator()

- ea: `0x18000dc78`
- end: `0x18000dea6`
- name: `_lambda_0777c056401d5fa7da1ccdfb87aa96b5_::operator()`
- size: `558`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000d4a4`

## callees

- `0x18000b0fc`
- `0x18000d470`
- `0x18000d944`
- `0x18000d9d4`
- `0x18000dad8`
- `0x18000db18`
- `0x18000db34`
- `0x18000dc78`
- `0x18001070c`
- `0x180012dc8`
- `0x180012ff8`

## string_xrefs

- `0x18000dcad`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`
- `0x18000de4d`: `onecore\ds\security\ngc\ngcpopkey\lib\ngcpopkeyrpc.cpp`

## pseudocode

```c
__int64 __fastcall lambda_0777c056401d5fa7da1ccdfb87aa96b5_::operator()(__int64 a1)
{
  unsigned __int8 *v2; // rcx
  __int64 v3; // rdx
  int SymmetricKeyBlob; // ebx
  unsigned int v5; // edx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-39h]
  int v10; // [rsp+20h] [rbp-39h]
  unsigned __int8 *v11; // [rsp+70h] [rbp+17h] BYREF
  __int64 *v12; // [rsp+78h] [rbp+1Fh] BYREF
  unsigned __int8 *v13; // [rsp+80h] [rbp+27h] BYREF
  char v14; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v16; // [rsp+C0h] [rbp+67h] BYREF
  unsigned int v17; // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v18; // [rsp+D0h] [rbp+77h] BYREF
  struct NgcSymmetricPopKey *v19; // [rsp+D8h] [rbp+7Fh] BYREF

  v2 = **(unsigned __int8 ***)a1;
  if ( !v2 )
  {
    v3 = 1227;
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
    v3 = 1228;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 16) )
  {
    v3 = 1229;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 24) )
  {
    v3 = 1230;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 32) )
  {
    v3 = 1231;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 40) )
  {
    v3 = 1232;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 48) )
  {
    v3 = 1233;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 56) )
  {
    v3 = 1234;
    goto LABEL_3;
  }
  LODWORD(v16) = 0;
  v17 = 0;
  v11 = 0;
  SymmetricKeyBlob = ValidateAndGetSymmetricKeyBlob(v2, v5, (enum _NGC_POP_KEY_TYPE *)&v16, &v11, &v17);
  if ( SymmetricKeyBlob < 0 )
  {
    v3 = 1246;
    goto LABEL_4;
  }
  v19 = 0;
  if ( (_DWORD)v16 == 2 )
    v6 = (_QWORD *)std::make_unique<TpmSymmetricPopKey,,0>(&v16);
  else
    v6 = std::make_unique<SoftwareSymmetricPopKey,,0>(&v16);
  std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(&v19, v6);
  std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(&v16);
  LODWORD(v16) = 0;
  v18 = 0;
  v12 = &v18;
  v13 = 0;
  v14 = 1;
  SymmetricKeyBlob = EncryptWithSymmetricPopKeyLocal(
                       v19,
                       v11,
                       v17,
                       **(unsigned __int8 ***)(a1 + 64),
                       **(_DWORD **)(a1 + 72),
                       **(unsigned __int8 ***)(a1 + 80),
                       **(_DWORD **)(a1 + 88),
                       **(unsigned __int8 ***)(a1 + 32),
                       **(_DWORD **)(a1 + 40),
                       **(unsigned __int8 ***)(a1 + 16),
                       **(_DWORD **)(a1 + 24),
                       &v13,
                       (unsigned int *)&v16);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v12);
  if ( SymmetricKeyBlob >= 0 )
  {
    v7 = v18;
    v18 = 0;
    ***(_QWORD ***)(a1 + 48) = v7;
    ***(_DWORD ***)(a1 + 56) = v16;
    SymmetricKeyBlob = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50B,
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
0x18000dc78  push    rbp
0x18000dc7a  push    rbx
0x18000dc7b  push    rsi
0x18000dc7c  push    rdi
0x18000dc7d  push    r14
0x18000dc7f  lea     rbp, [rsp-37h]
0x18000dc84  sub     rsp, 90h
0x18000dc8b  mov     rdi, rcx
0x18000dc8e  mov     rax, [rcx]
0x18000dc91  mov     rcx, [rax]; unsigned __int8 *
0x18000dc94  xor     r14d, r14d
0x18000dc97  test    rcx, rcx
0x18000dc9a  jnz     short loc_18000DCBE
0x18000dc9c  mov     edx, 4CBh; void *
0x18000dca1  mov     ebx, 80090027h
0x18000dca6  mov     rcx, [rbp+5Fh]; this
0x18000dcaa  mov     r9d, ebx; char *
0x18000dcad  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18000dcb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcb9  jmp     loc_18000DE96
0x18000dcbe  mov     rax, [rdi+8]
0x18000dcc2  mov     edx, [rax]; unsigned int
0x18000dcc4  test    edx, edx
0x18000dcc6  jnz     short loc_18000DCCF
0x18000dcc8  mov     edx, 4CCh
0x18000dccd  jmp     short loc_18000DCA1
0x18000dccf  mov     rax, [rdi+10h]
0x18000dcd3  cmp     [rax], r14
0x18000dcd6  jnz     short loc_18000DCDF
0x18000dcd8  mov     edx, 4CDh
0x18000dcdd  jmp     short loc_18000DCA1
0x18000dcdf  mov     rax, [rdi+18h]
0x18000dce3  cmp     [rax], r14d
0x18000dce6  jnz     short loc_18000DCEF
0x18000dce8  mov     edx, 4CEh
0x18000dced  jmp     short loc_18000DCA1
0x18000dcef  mov     rax, [rdi+20h]
0x18000dcf3  cmp     [rax], r14
0x18000dcf6  jnz     short loc_18000DCFF
0x18000dcf8  mov     edx, 4CFh
0x18000dcfd  jmp     short loc_18000DCA1
0x18000dcff  mov     rax, [rdi+28h]
0x18000dd03  cmp     [rax], r14d
0x18000dd06  jnz     short loc_18000DD0F
0x18000dd08  mov     edx, 4D0h
0x18000dd0d  jmp     short loc_18000DCA1
0x18000dd0f  mov     rax, [rdi+30h]
0x18000dd13  cmp     [rax], r14
0x18000dd16  jnz     short loc_18000DD1F
0x18000dd18  mov     edx, 4D1h
0x18000dd1d  jmp     short loc_18000DCA1
0x18000dd1f  mov     rax, [rdi+38h]
0x18000dd23  cmp     [rax], r14
0x18000dd26  jnz     short loc_18000DD32
0x18000dd28  mov     edx, 4D2h
0x18000dd2d  jmp     loc_18000DCA1
0x18000dd32  mov     dword ptr [rbp+57h+arg_0], r14d
0x18000dd36  mov     [rbp+57h+arg_8], r14d
0x18000dd3a  mov     [rbp+57h+var_40], r14
0x18000dd3e  lea     rax, [rbp+57h+arg_8]
0x18000dd42  mov     [rsp+0B0h+var_90], rax; unsigned int *
0x18000dd47  lea     r9, [rbp+57h+var_40]; unsigned __int8 **
0x18000dd4b  lea     r8, [rbp+57h+arg_0]; enum _NGC_POP_KEY_TYPE *
0x18000dd4f  call    ?ValidateAndGetSymmetricKeyBlob@@YAJPEAEKPEAW4_NGC_POP_KEY_TYPE@@PEAPEAEPEAK@Z; ValidateAndGetSymmetricKeyBlob(uchar *,ulong,_NGC_POP_KEY_TYPE *,uchar * *,ulong *)
0x18000dd54  mov     ebx, eax
0x18000dd56  test    eax, eax
0x18000dd58  jns     short loc_18000DD64
0x18000dd5a  mov     edx, 4DEh
0x18000dd5f  jmp     loc_18000DCA6
0x18000dd64  mov     [rbp+57h+arg_18], r14
0x18000dd68  lea     rcx, [rbp+57h+arg_0]
0x18000dd6c  cmp     dword ptr [rbp+57h+arg_0], 2
0x18000dd70  jnz     short loc_18000DD8E
0x18000dd72  call    ??$make_unique@VTpmSymmetricPopKey@@$$V$0A@@std@@YA?AV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@0@XZ; std::make_unique<TpmSymmetricPopKey,,0>(void)
0x18000dd77  mov     rdx, rax
0x18000dd7a  lea     rcx, [rbp+57h+arg_18]
0x18000dd7e  call    ??$?4VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@$0A@@?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@1@@Z; std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(std::unique_ptr<TpmSymmetricPopKey> &&)
0x18000dd83  lea     rcx, [rbp+57h+arg_0]
0x18000dd87  call    ??1?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(void)
0x18000dd8c  jmp     short loc_18000DDA8
0x18000dd8e  call    ??$make_unique@VSoftwareSymmetricPopKey@@$$V$0A@@std@@YA?AV?$unique_ptr@VSoftwareSymmetricPopKey@@U?$default_delete@VSoftwareSymmetricPopKey@@@std@@@0@XZ; std::make_unique<SoftwareSymmetricPopKey,,0>(void)
0x18000dd93  mov     rdx, rax
0x18000dd96  lea     rcx, [rbp+57h+arg_18]
0x18000dd9a  call    ??$?4VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@$0A@@?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@1@@Z; std::unique_ptr<NgcSymmetricPopKey>::operator=<TpmSymmetricPopKey,std::default_delete<TpmSymmetricPopKey>,0>(std::unique_ptr<TpmSymmetricPopKey> &&)
0x18000dd9f  lea     rcx, [rbp+57h+arg_0]
0x18000dda3  call    ??1?$unique_ptr@VTpmSymmetricPopKey@@U?$default_delete@VTpmSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<TpmSymmetricPopKey>::~unique_ptr<TpmSymmetricPopKey>(void)
0x18000dda8  mov     dword ptr [rbp+57h+arg_0], r14d
0x18000ddac  mov     [rbp+57h+arg_10], r14
0x18000ddb0  lea     rax, [rbp+57h+arg_10]
0x18000ddb4  mov     [rbp+57h+var_38], rax
0x18000ddb8  mov     [rbp+57h+var_30], r14
0x18000ddbc  mov     [rbp+57h+var_28], 1
0x18000ddc0  mov     rax, [rdi+18h]
0x18000ddc4  mov     rcx, [rdi+10h]
0x18000ddc8  mov     rdx, [rdi+28h]
0x18000ddcc  mov     r8, [rdi+20h]
0x18000ddd0  mov     r10, [rdi+58h]
0x18000ddd4  mov     r11, [rdi+50h]
0x18000ddd8  mov     rbx, [rdi+48h]
0x18000dddc  mov     r9, [rdi+40h]
0x18000dde0  lea     rsi, [rbp+57h+arg_0]
0x18000dde4  mov     [rsp+0B0h+var_50], rsi; unsigned int *
0x18000dde9  lea     rsi, [rbp+57h+var_30]
0x18000dded  mov     [rsp+0B0h+var_58], rsi; unsigned __int8 **
0x18000ddf2  mov     eax, [rax]
0x18000ddf4  mov     [rsp+0B0h+var_60], eax; unsigned int
0x18000ddf8  mov     rax, [rcx]
0x18000ddfb  mov     [rsp+0B0h+var_68], rax; unsigned __int8 *
0x18000de00  mov     eax, [rdx]
0x18000de02  mov     [rsp+0B0h+var_70], eax; unsigned int
0x18000de06  mov     rax, [r8]
0x18000de09  mov     [rsp+0B0h+var_78], rax; unsigned __int8 *
0x18000de0e  mov     eax, [r10]
0x18000de11  mov     [rsp+0B0h+var_80], eax; unsigned int
0x18000de15  mov     rax, [r11]
0x18000de18  mov     [rsp+0B0h+var_88], rax; unsigned __int8 *
0x18000de1d  mov     eax, [rbx]
0x18000de1f  mov     dword ptr [rsp+0B0h+var_90], eax; int
0x18000de23  mov     r9, [r9]; unsigned __int8 *
0x18000de26  mov     r8d, [rbp+57h+arg_8]; unsigned int
0x18000de2a  mov     rdx, [rbp+57h+var_40]; unsigned __int8 *
0x18000de2e  mov     rcx, [rbp+57h+arg_18]; struct NgcSymmetricPopKey *
0x18000de32  call    ?EncryptWithSymmetricPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1K1KPEAPEAEPEAK@Z; EncryptWithSymmetricPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18000de37  mov     ebx, eax
0x18000de39  lea     rcx, [rbp+57h+var_38]
0x18000de3d  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18000de42  test    ebx, ebx
0x18000de44  jns     short loc_18000DE60
0x18000de46  mov     rcx, [rbp+5Fh]; this
0x18000de4a  mov     r9d, ebx; char *
0x18000de4d  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18000de54  mov     edx, 50Bh; void *
0x18000de59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de5e  jmp     short loc_18000DE81
0x18000de60  mov     rdx, [rbp+57h+arg_10]
0x18000de64  mov     [rbp+57h+arg_10], r14
0x18000de68  mov     rax, [rdi+30h]
0x18000de6c  mov     rcx, [rax]
0x18000de6f  mov     [rcx], rdx
0x18000de72  mov     rax, [rdi+38h]
0x18000de76  mov     rcx, [rax]
0x18000de79  mov     eax, dword ptr [rbp+57h+arg_0]
0x18000de7c  mov     [rcx], eax
0x18000de7e  mov     ebx, r14d
0x18000de81  xor     edx, edx
0x18000de83  lea     rcx, [rbp+57h+arg_10]
0x18000de87  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18000de8c  nop
0x18000de8d  lea     rcx, [rbp+57h+arg_18]
0x18000de91  call    ??1?$unique_ptr@VNgcSymmetricPopKey@@U?$default_delete@VNgcSymmetricPopKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcSymmetricPopKey>::~unique_ptr<NgcSymmetricPopKey>(void)
0x18000de96  mov     eax, ebx
0x18000de98  add     rsp, 90h
0x18000de9f  pop     r14
0x18000dea1  pop     rdi
0x18000dea2  pop     rsi
0x18000dea3  pop     rbx
0x18000dea4  pop     rbp
0x18000dea5  retn
```
