# _lambda_0cdd00fcf549bea2ee2c1016e52bb9ee_::operator()

- ea: `0x180002e10`
- end: `0x180003233`
- name: `_lambda_0cdd00fcf549bea2ee2c1016e52bb9ee_::operator()`
- size: `1059`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c944`

## callees

- `0x180002e10`
- `0x180004970`
- `0x180006538`
- `0x1800065c0`
- `0x180032fcc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003076`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003132`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002f89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003076`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003132`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003198`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031eb`
- `ncrypt!NCryptFreeObject` at `0x180002f7a`
- `ncrypt!NCryptFreeObject` at `0x180003156`
- `ncrypt!NCryptFreeObject` at `0x180002f7a`
- `ncrypt!NCryptFreeObject` at `0x180003156`
- `ncrypt!NCryptFreeBuffer` at `0x180002fe6`
- `ncrypt!NCryptFreeBuffer` at `0x1800030ab`
- `ncrypt!NCryptFreeBuffer` at `0x180003146`
- `ncrypt!NCryptFreeBuffer` at `0x1800031ac`
- `ncrypt!NCryptFreeBuffer` at `0x180002fe6`
- `ncrypt!NCryptFreeBuffer` at `0x1800030ab`
- `ncrypt!NCryptFreeBuffer` at `0x180003146`
- `ncrypt!NCryptFreeBuffer` at `0x1800031ac`
- `ncrypt!NCryptOpenStorageProvider` at `0x180002f4c`
- `ncrypt!NCryptOpenStorageProvider` at `0x180002f4c`
- `ncrypt!NCryptEnumKeys` at `0x180002fc5`
- `ncrypt!NCryptEnumKeys` at `0x1800030d4`
- `ncrypt!NCryptEnumKeys` at `0x180002fc5`
- `ncrypt!NCryptEnumKeys` at `0x1800030d4`

## string_xrefs

- `0x180002e3a`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180002e69`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180002e98`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180002ef1`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180002f5f`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180003087`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180003179`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x1800031cc`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18000320b`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_0cdd00fcf549bea2ee2c1016e52bb9ee_::operator()(__int64 a1)
{
  HLOCAL v3; // r15
  PVOID *v4; // r14
  char v5; // r12
  SECURITY_STATUS v6; // eax
  SECURITY_STATUS v7; // ebx
  NCRYPT_HANDLE v8; // rcx
  PVOID v9; // rcx
  int MatchedKey; // ebx
  PVOID v11; // rcx
  PVOID v12; // rcx
  HLOCAL v13; // rdx
  HLOCAL v14; // rcx
  PVOID v15; // rcx
  HLOCAL v16; // rcx
  PVOID v17; // rcx
  HLOCAL v18; // rcx
  int dwFlags; // [rsp+20h] [rbp-48h]
  int dwFlagsa; // [rsp+20h] [rbp-48h]
  int dwFlagsb; // [rsp+20h] [rbp-48h]
  HLOCAL hMem; // [rsp+40h] [rbp-28h] BYREF
  PVOID *p_pvInput; // [rsp+48h] [rbp-20h]
  NCryptKeyName *ppKeyName; // [rsp+50h] [rbp-18h] BYREF
  char v25; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  bool v27; // [rsp+B0h] [rbp+48h] BYREF
  PVOID pvInput; // [rsp+B8h] [rbp+50h] BYREF
  HLOCAL v29; // [rsp+C0h] [rbp+58h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+C8h] [rbp+60h] BYREF

  if ( !**(_QWORD **)a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x424,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  if ( !**(_QWORD **)(a1 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x425,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  if ( !**(_QWORD **)(a1 + 16) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x426,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, 24);
  v3 = hMem;
  if ( !hMem )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x429,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    return 2147942414LL;
  }
  v4 = ***(PVOID ****)(a1 + 16);
  if ( v4 )
  {
    if ( *(_DWORD *)v4 != 752403724 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x431,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)0x80090027LL,
        dwFlags);
      if ( v3 )
        LocalFree(v3);
      return 2148073511LL;
    }
    v5 = 0;
  }
  else
  {
    v5 = 1;
    v4 = (PVOID *)hMem;
    *(_DWORD *)hMem = 752403724;
  }
  ***(_QWORD ***)(a1 + 8) = 0;
  phProvider = 0;
  v6 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    pvInput = 0;
    v29 = 0;
    v27 = 0;
    p_pvInput = &pvInput;
    ppKeyName = 0;
    v25 = 1;
    v7 = NCryptEnumKeys(phProvider, 0, &ppKeyName, v4 + 1, 0);
    if ( v25 )
    {
      v9 = *p_pvInput;
      *p_pvInput = ppKeyName;
      if ( v9 )
      {
LABEL_23:
        NCryptFreeBuffer(v9);
        goto LABEL_24;
      }
    }
    while ( 1 )
    {
LABEL_24:
      if ( v7 == -2146893782 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x478,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)0x8009002ALL,
          dwFlagsa);
        v18 = v29;
        v29 = 0;
        if ( v18 )
          LocalFree(v18);
        v17 = pvInput;
        pvInput = 0;
        if ( v17 )
          goto LABEL_51;
        goto LABEL_52;
      }
      if ( v7 < 0 )
        break;
      p_pvInput = &v29;
      ppKeyName = 0;
      v25 = 1;
      MatchedKey = GetMatchedKey(
                     phProvider,
                     **(const unsigned __int16 ***)a1,
                     **(const unsigned __int16 ***)(a1 + 24),
                     **(const unsigned __int16 ***)(a1 + 32),
                     **(const unsigned __int16 ***)(a1 + 40),
                     *(const unsigned __int16 **)pvInput,
                     (struct _NGC_USER_ID_KEY_INFO **)&ppKeyName,
                     &v27);
      if ( v25 )
      {
        v11 = *p_pvInput;
        *p_pvInput = ppKeyName;
        if ( v11 )
          LocalFree(v11);
      }
      if ( MatchedKey < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x457,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)MatchedKey,
          dwFlagsb);
      if ( v27 )
      {
        v13 = v29;
        v29 = 0;
        ***(_QWORD ***)(a1 + 8) = v13;
        ***(_QWORD ***)(a1 + 16) = v4;
        if ( v5 )
          v3 = 0;
        v14 = v29;
        v29 = 0;
        if ( v14 )
          LocalFree(v14);
        v15 = pvInput;
        pvInput = 0;
        if ( v15 )
          NCryptFreeBuffer(v15);
        if ( phProvider )
          NCryptFreeObject(phProvider);
        if ( v3 )
          LocalFree(v3);
        return 0;
      }
      v12 = pvInput;
      pvInput = 0;
      if ( v12 )
        NCryptFreeBuffer(v12);
      p_pvInput = &pvInput;
      ppKeyName = 0;
      v25 = 1;
      v7 = NCryptEnumKeys(phProvider, 0, &ppKeyName, v4 + 1, 0);
      if ( v25 )
      {
        v9 = *p_pvInput;
        *p_pvInput = ppKeyName;
        if ( v9 )
          goto LABEL_23;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44C,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v7,
      dwFlagsa);
    v16 = v29;
    v29 = 0;
    if ( v16 )
      LocalFree(v16);
    v17 = pvInput;
    pvInput = 0;
    if ( v17 )
LABEL_51:
      NCryptFreeBuffer(v17);
LABEL_52:
    v8 = phProvider;
    if ( !phProvider )
      goto LABEL_18;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x43F,
    (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
    (const char *)(unsigned int)v6,
    dwFlags);
  v8 = phProvider;
  if ( phProvider )
LABEL_17:
    NCryptFreeObject(v8);
LABEL_18:
  if ( v3 )
    LocalFree(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002e10  push    rbp
0x180002e12  push    rbx
0x180002e13  push    rsi
0x180002e14  push    rdi
0x180002e15  push    r12
0x180002e17  push    r13
0x180002e19  push    r14
0x180002e1b  push    r15
0x180002e1d  mov     rbp, rsp
0x180002e20  sub     rsp, 68h
0x180002e24  mov     rdi, rcx
0x180002e27  mov     rax, [rcx]
0x180002e2a  cmp     qword ptr [rax], 0
0x180002e2e  jnz     short loc_180002E55
0x180002e30  mov     rcx, [rbp+40h]; this
0x180002e34  mov     r9d, 80090027h; char *
0x180002e3a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180002e41  mov     edx, 424h; void *
0x180002e46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e4b  mov     eax, 80090027h
0x180002e50  jmp     loc_180003222
0x180002e55  mov     rax, [rcx+8]
0x180002e59  cmp     qword ptr [rax], 0
0x180002e5d  jnz     short loc_180002E84
0x180002e5f  mov     rcx, [rbp+40h]; this
0x180002e63  mov     r9d, 80090027h; char *
0x180002e69  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180002e70  mov     edx, 425h; void *
0x180002e75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e7a  mov     eax, 80090027h
0x180002e7f  jmp     loc_180003222
0x180002e84  mov     rax, [rcx+10h]
0x180002e88  cmp     qword ptr [rax], 0
0x180002e8c  jnz     short loc_180002EB3
0x180002e8e  mov     rcx, [rbp+40h]; this
0x180002e92  mov     r9d, 80090027h; char *
0x180002e98  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180002e9f  mov     edx, 426h; void *
0x180002ea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002ea9  mov     eax, 80090027h
0x180002eae  jmp     loc_180003222
0x180002eb3  mov     edx, 18h
0x180002eb8  lea     rcx, [rbp+hMem]
0x180002ebc  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180002ec1  nop
0x180002ec2  mov     r15, [rbp+hMem]
0x180002ec6  test    r15, r15
0x180002ec9  jz      loc_180003201
0x180002ecf  mov     rax, [rdi+10h]
0x180002ed3  mov     rcx, [rax]
0x180002ed6  mov     r14, [rcx]
0x180002ed9  test    r14, r14
0x180002edc  jz      short loc_180002F20
0x180002ede  cmp     dword ptr [r14], 2CD8C50Ch
0x180002ee5  jz      short loc_180002F1B
0x180002ee7  mov     rcx, [rbp+40h]; this
0x180002eeb  mov     r9d, 80090027h; char *
0x180002ef1  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180002ef8  mov     edx, 431h; void *
0x180002efd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002f02  nop
0x180002f03  test    r15, r15
0x180002f06  jz      short loc_180002F11
0x180002f08  mov     rcx, r15; hMem
0x180002f0b  call    cs:__imp_LocalFree
0x180002f11  mov     eax, 80090027h
0x180002f16  jmp     loc_180003222
0x180002f1b  xor     r12b, r12b
0x180002f1e  jmp     short loc_180002F2D
0x180002f20  mov     r12b, 1
0x180002f23  mov     r14, r15
0x180002f26  mov     dword ptr [r15], 2CD8C50Ch
0x180002f2d  mov     rax, [rdi+8]
0x180002f31  mov     rcx, [rax]
0x180002f34  xor     r13d, r13d
0x180002f37  mov     [rcx], r13
0x180002f3a  mov     [rbp+phProvider], r13
0x180002f3e  xor     r8d, r8d; dwFlags
0x180002f41  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180002f48  lea     rcx, [rbp+phProvider]; phProvider
0x180002f4c  call    cs:__imp_NCryptOpenStorageProvider
0x180002f52  mov     ebx, eax
0x180002f54  test    eax, eax
0x180002f56  jns     short loc_180002F96
0x180002f58  mov     rcx, [rbp+40h]; this
0x180002f5c  mov     r9d, eax; char *
0x180002f5f  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180002f66  mov     edx, 43Fh; void *
0x180002f6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002f70  nop
0x180002f71  mov     rcx, [rbp+phProvider]; hObject
0x180002f75  test    rcx, rcx
0x180002f78  jz      short loc_180002F81
0x180002f7a  call    cs:__imp_NCryptFreeObject
0x180002f80  nop
0x180002f81  test    r15, r15
0x180002f84  jz      short loc_180002F8F
0x180002f86  mov     rcx, r15; hMem
0x180002f89  call    cs:__imp_LocalFree
0x180002f8f  mov     eax, ebx
0x180002f91  jmp     loc_180003222
0x180002f96  mov     [rbp+pvInput], r13
0x180002f9a  mov     [rbp+arg_10], r13
0x180002f9e  mov     [rbp+arg_0], 0
0x180002fa2  lea     rax, [rbp+pvInput]
0x180002fa6  mov     [rbp+var_20], rax
0x180002faa  mov     [rbp+ppKeyName], r13
0x180002fae  mov     [rbp+var_10], 1
0x180002fb2  mov     [rsp+68h+dwFlags], r13d; int
0x180002fb7  lea     r9, [r14+8]; ppEnumState
0x180002fbb  lea     r8, [rbp+ppKeyName]; ppKeyName
0x180002fbf  xor     edx, edx; pszScope
0x180002fc1  mov     rcx, [rbp+phProvider]; hProvider
0x180002fc5  call    cs:__imp_NCryptEnumKeys
0x180002fcb  mov     ebx, eax
0x180002fcd  cmp     [rbp+var_10], 0
0x180002fd1  jz      short loc_180002FF0
0x180002fd3  mov     r8, [rbp+var_20]
0x180002fd7  mov     rcx, [r8]; pvInput
0x180002fda  mov     rdx, [rbp+ppKeyName]
0x180002fde  mov     [r8], rdx
0x180002fe1  test    rcx, rcx
0x180002fe4  jz      short loc_180002FF0
0x180002fe6  call    cs:__imp_NCryptFreeBuffer
0x180002fec  nop     dword ptr [rax+00h]
0x180002ff0  cmp     ebx, 8009002Ah
0x180002ff6  jz      loc_1800031C5
0x180002ffc  test    ebx, ebx
0x180002ffe  js      loc_180003172
0x180003004  lea     rax, [rbp+arg_10]
0x180003008  mov     [rbp+var_20], rax
0x18000300c  mov     [rbp+ppKeyName], r13
0x180003010  mov     [rbp+var_10], 1
0x180003014  mov     r11, [rdi+28h]
0x180003018  mov     r9, [rdi+20h]
0x18000301c  mov     r8, [rdi+18h]
0x180003020  mov     rdx, [rdi]
0x180003023  lea     rax, [rbp+arg_0]
0x180003027  mov     [rsp+68h+var_30], rax; bool *
0x18000302c  lea     rax, [rbp+ppKeyName]
0x180003030  mov     [rsp+68h+var_38], rax; struct _NGC_USER_ID_KEY_INFO **
0x180003035  mov     rax, [rbp+pvInput]
0x180003039  mov     r10, [rax]
0x18000303c  mov     [rsp+68h+var_40], r10; unsigned __int16 *
0x180003041  mov     rax, [r11]
0x180003044  mov     qword ptr [rsp+68h+dwFlags], rax; int
0x180003049  mov     r9, [r9]; unsigned __int16 *
0x18000304c  mov     r8, [r8]; unsigned __int16 *
0x18000304f  mov     rdx, [rdx]; unsigned __int16 *
0x180003052  mov     rcx, [rbp+phProvider]; hProvider
0x180003056  call    ?GetMatchedKey@@YAJ_KPEBG1111PEAPEAU_NGC_USER_ID_KEY_INFO@@PEA_N@Z; GetMatchedKey(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_NGC_USER_ID_KEY_INFO * *,bool *)
0x18000305b  mov     ebx, eax
0x18000305d  cmp     [rbp+var_10], 0
0x180003061  jz      short loc_18000307C
0x180003063  mov     r8, [rbp+var_20]
0x180003067  mov     rcx, [r8]; hMem
0x18000306a  mov     rdx, [rbp+ppKeyName]
0x18000306e  mov     [r8], rdx
0x180003071  test    rcx, rcx
0x180003074  jz      short loc_18000307C
0x180003076  call    cs:__imp_LocalFree
0x18000307c  mov     rcx, [rbp+40h]; this
0x180003080  test    ebx, ebx
0x180003082  jns     short loc_180003098
0x180003084  mov     r9d, ebx; char *
0x180003087  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18000308e  mov     edx, 457h; void *
0x180003093  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003098  cmp     [rbp+arg_0], 0
0x18000309c  jnz     short loc_180003102
0x18000309e  mov     rcx, [rbp+pvInput]; pvInput
0x1800030a2  mov     [rbp+pvInput], r13
0x1800030a6  test    rcx, rcx
0x1800030a9  jz      short loc_1800030B1
0x1800030ab  call    cs:__imp_NCryptFreeBuffer
0x1800030b1  lea     rax, [rbp+pvInput]
0x1800030b5  mov     [rbp+var_20], rax
0x1800030b9  mov     [rbp+ppKeyName], r13
0x1800030bd  mov     [rbp+var_10], 1
0x1800030c1  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x1800030c6  lea     r9, [r14+8]; ppEnumState
0x1800030ca  lea     r8, [rbp+ppKeyName]; ppKeyName
0x1800030ce  xor     edx, edx; pszScope
0x1800030d0  mov     rcx, [rbp+phProvider]; hProvider
0x1800030d4  call    cs:__imp_NCryptEnumKeys
0x1800030da  mov     ebx, eax
0x1800030dc  cmp     [rbp+var_10], 0
0x1800030e0  jz      loc_180002FF0
0x1800030e6  mov     rdx, [rbp+var_20]
0x1800030ea  mov     rcx, [rdx]
0x1800030ed  mov     rax, [rbp+ppKeyName]
0x1800030f1  mov     [rdx], rax
0x1800030f4  test    rcx, rcx
0x1800030f7  jz      loc_180002FF0
0x1800030fd  jmp     loc_180002FE6
0x180003102  mov     rdx, [rbp+arg_10]
0x180003106  mov     [rbp+arg_10], r13
0x18000310a  mov     rax, [rdi+8]
0x18000310e  mov     rcx, [rax]
0x180003111  mov     [rcx], rdx
0x180003114  mov     rax, [rdi+10h]
0x180003118  mov     rcx, [rax]
0x18000311b  mov     [rcx], r14
0x18000311e  test    r12b, r12b
0x180003121  cmovnz  r15, r13
0x180003125  mov     rcx, [rbp+arg_10]; hMem
0x180003129  mov     [rbp+arg_10], r13
0x18000312d  test    rcx, rcx
0x180003130  jz      short loc_180003139
0x180003132  call    cs:__imp_LocalFree
0x180003138  nop
0x180003139  mov     rcx, [rbp+pvInput]; pvInput
0x18000313d  mov     [rbp+pvInput], r13
0x180003141  test    rcx, rcx
0x180003144  jz      short loc_18000314D
0x180003146  call    cs:__imp_NCryptFreeBuffer
0x18000314c  nop
0x18000314d  mov     rcx, [rbp+phProvider]; hObject
0x180003151  test    rcx, rcx
0x180003154  jz      short loc_18000315D
0x180003156  call    cs:__imp_NCryptFreeObject
0x18000315c  nop
0x18000315d  test    r15, r15
0x180003160  jz      short loc_18000316B
0x180003162  mov     rcx, r15; hMem
0x180003165  call    cs:__imp_LocalFree
0x18000316b  xor     eax, eax
0x18000316d  jmp     loc_180003222
0x180003172  mov     rcx, [rbp+40h]; this
0x180003176  mov     r9d, ebx; char *
0x180003179  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180003180  mov     edx, 44Ch; void *
0x180003185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000318a  nop
0x18000318b  mov     rcx, [rbp+arg_10]; hMem
0x18000318f  mov     [rbp+arg_10], r13
0x180003193  test    rcx, rcx
0x180003196  jz      short loc_18000319F
0x180003198  call    cs:__imp_LocalFree
0x18000319e  nop
0x18000319f  mov     rcx, [rbp+pvInput]; pvInput
0x1800031a3  mov     [rbp+pvInput], r13
0x1800031a7  test    rcx, rcx
0x1800031aa  jz      short loc_1800031B3
0x1800031ac  call    cs:__imp_NCryptFreeBuffer
0x1800031b2  nop
0x1800031b3  mov     rcx, [rbp+phProvider]
0x1800031b7  test    rcx, rcx
0x1800031ba  jz      loc_180002F81
0x1800031c0  jmp     loc_180002F7A
0x1800031c5  mov     rcx, [rbp+40h]; this
0x1800031c9  mov     r9d, ebx; char *
0x1800031cc  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800031d3  mov     edx, 478h; void *
0x1800031d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800031dd  nop
0x1800031de  mov     rcx, [rbp+arg_10]; hMem
0x1800031e2  mov     [rbp+arg_10], r13
0x1800031e6  test    rcx, rcx
0x1800031e9  jz      short loc_1800031F2
0x1800031eb  call    cs:__imp_LocalFree
0x1800031f1  nop
0x1800031f2  mov     rcx, [rbp+pvInput]
0x1800031f6  mov     [rbp+pvInput], r13
0x1800031fa  test    rcx, rcx
0x1800031fd  jnz     short loc_1800031AC
0x1800031ff  jmp     short loc_1800031B3
0x180003201  mov     rcx, [rbp+40h]; this
0x180003205  mov     r9d, 8007000Eh; char *
0x18000320b  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180003212  mov     edx, 429h; void *
0x180003217  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000321c  nop
0x18000321d  mov     eax, 8007000Eh
0x180003222  add     rsp, 68h
0x180003226  pop     r15
0x180003228  pop     r14
0x18000322a  pop     r13
0x18000322c  pop     r12
0x18000322e  pop     rdi
0x18000322f  pop     rsi
0x180003230  pop     rbx
0x180003231  pop     rbp
0x180003232  retn
```
