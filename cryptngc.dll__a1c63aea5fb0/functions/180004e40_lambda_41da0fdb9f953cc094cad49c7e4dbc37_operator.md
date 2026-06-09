# _lambda_41da0fdb9f953cc094cad49c7e4dbc37_::operator()

- ea: `0x180004e40`
- end: `0x18000530f`
- name: `_lambda_41da0fdb9f953cc094cad49c7e4dbc37_::operator()`
- size: `1231`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000323c`

## callees

- `0x180004e40`
- `0x180006538`
- `0x180009570`
- `0x180018430`
- `0x18001b9b4`
- `0x180028380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005190`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005190`
- `bcrypt!BCryptDestroyKey` at `0x180005273`
- `bcrypt!BCryptDestroyKey` at `0x1800052f6`
- `bcrypt!BCryptDestroyKey` at `0x180005304`
- `bcrypt!BCryptDestroyKey` at `0x180005273`
- `bcrypt!BCryptDestroyKey` at `0x1800052f6`
- `bcrypt!BCryptDestroyKey` at `0x180005304`
- `bcrypt!BCryptSetProperty` at `0x180005096`
- `bcrypt!BCryptSetProperty` at `0x180005096`

## string_xrefs

- `0x180004eb8`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180004f09`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180004f3b`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180004f6d`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180004ff3`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180005031`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x1800050ac`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180005108`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180005135`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180005167`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x18000519e`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x1800051d7`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180005200`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180005229`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180005252`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`

## pseudocode

```c
__int64 __fastcall lambda_41da0fdb9f953cc094cad49c7e4dbc37_::operator()(__int64 a1)
{
  const unsigned __int16 *v2; // r10
  __int64 v3; // rdi
  int v4; // r8d
  unsigned int v5; // ecx
  unsigned int v7; // edx
  unsigned int v8; // ecx
  unsigned int v9; // edx
  char v10; // r9
  HWND v11; // r8
  unsigned __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // esi
  BCRYPT_HANDLE v15; // rsi
  __int64 v16; // r14
  UCHAR *v17; // rbp
  ULONG v18; // edi
  NTSTATUS v19; // eax
  unsigned int v20; // r9d
  int v21; // edi
  int v22; // edx
  HLOCAL v23; // r8
  HLOCAL v24; // rcx
  int dwFlags; // [rsp+20h] [rbp-68h]
  int dwFlagsa; // [rsp+20h] [rbp-68h]
  SIZE_T dwFlagsb; // [rsp+20h] [rbp-68h]
  int dwFlagsc; // [rsp+20h] [rbp-68h]
  int dwFlagsd; // [rsp+20h] [rbp-68h]
  unsigned int *v30; // [rsp+38h] [rbp-50h]
  HLOCAL *p_hMem; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v32[2]; // [rsp+48h] [rbp-40h] BYREF
  char v33; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  BCRYPT_HANDLE hObject; // [rsp+90h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+10h] BYREF

  v2 = **(const unsigned __int16 ***)a1;
  if ( !v2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  v3 = **(_QWORD **)(a1 + 8);
  if ( !v3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  v4 = **(_DWORD **)(a1 + 16);
  if ( !v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  if ( !**(_QWORD **)(a1 + 24) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  if ( !**(_QWORD **)(a1 + 32) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  if ( *(_DWORD *)v3 != 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090005LL,
      dwFlags);
    return 2148073477LL;
  }
  v5 = *(_DWORD *)(v3 + 12) + 20;
  if ( *(_DWORD *)(v3 + 12) >= 0xFFFFFFEC )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090005LL,
      dwFlags);
    return 2148073477LL;
  }
  v7 = v5 + *(_DWORD *)(v3 + 4);
  if ( v7 < v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090005LL,
      dwFlags);
    return 2148073477LL;
  }
  v8 = v7 + *(_DWORD *)(v3 + 8);
  if ( v8 < v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090005LL,
      dwFlags);
    return 2148073477LL;
  }
  v9 = v8 + *(_DWORD *)(v3 + 16);
  if ( v9 < v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090005LL,
      dwFlags);
    return 2148073477LL;
  }
  if ( v4 != v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)0x80090005LL,
      dwFlags);
    return 2148073477LL;
  }
  v10 = **(_BYTE **)(a1 + 56);
  v11 = **(HWND **)(a1 + 48);
  v12 = **(_QWORD **)(a1 + 40);
  hObject = 0;
  v13 = UnwrapNgcContentEncryptionKey(
          v2,
          v12,
          v11,
          v10,
          (const struct _NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB *)v3,
          &hObject);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)(unsigned int)v13,
      dwFlagsa);
    if ( hObject )
      BCryptDestroyKey(hObject);
    return v14;
  }
  v15 = hObject;
  v16 = *(unsigned int *)(v3 + 8);
  v17 = (UCHAR *)(v3 + *(unsigned int *)(v3 + 4) + 20LL);
  v18 = *(_DWORD *)(v3 + 12);
  v19 = BCryptSetProperty(hObject, L"IV", v17, v16, 0);
  if ( v19 >= 0 )
  {
    LODWORD(hObject) = 0;
    p_hMem = &hMem;
    hMem = 0;
    *(_QWORD *)v32 = 0;
    v33 = 1;
    v21 = NgcUtils::DecryptData(
            v15,
            &v17[v16],
            v18,
            v20,
            dwFlagsb,
            (unsigned int)v32,
            (unsigned __int8 **)&hObject,
            v30);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( v21 >= 0 )
    {
      v22 = (int)hObject;
      v23 = hMem;
      goto LABEL_24;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)(unsigned int)v21,
      dwFlagsd);
    v24 = hMem;
    hMem = 0;
    if ( v24 )
      LocalFree(v24);
  }
  else
  {
    v21 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x107,
            (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
            (const char *)(unsigned int)v19,
            dwFlagsb);
    if ( v21 >= 0 )
    {
      v22 = 0;
      v23 = 0;
LABEL_24:
      ***(_QWORD ***)(a1 + 24) = v23;
      ***(_DWORD ***)(a1 + 32) = v22;
      if ( v15 )
        BCryptDestroyKey(v15);
      return 0;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D7,
    (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
    (const char *)(unsigned int)v21,
    dwFlagsc);
  if ( v15 )
    BCryptDestroyKey(v15);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180004e40  push    rbx
0x180004e42  sub     rsp, 80h
0x180004e49  mov     rax, [rcx]
0x180004e4c  mov     rbx, rcx
0x180004e4f  mov     r10, [rax]
0x180004e52  test    r10, r10
0x180004e55  jz      loc_180005100
0x180004e5b  mov     rax, [rcx+8]
0x180004e5f  mov     [rsp+88h+var_18], rdi
0x180004e64  mov     rdi, [rax]
0x180004e67  test    rdi, rdi
0x180004e6a  jz      loc_180005029
0x180004e70  mov     rax, [rcx+10h]
0x180004e74  mov     r8d, [rax]
0x180004e77  test    r8d, r8d
0x180004e7a  jz      loc_1800051CF
0x180004e80  mov     rax, [rcx+18h]
0x180004e84  cmp     qword ptr [rax], 0
0x180004e88  jz      loc_18000512D
0x180004e8e  mov     rax, [rcx+20h]
0x180004e92  cmp     qword ptr [rax], 0
0x180004e96  jz      loc_1800051F8
0x180004e9c  cmp     dword ptr [rdi], 1
0x180004e9f  jnz     loc_180005221
0x180004ea5  mov     ecx, [rdi+0Ch]
0x180004ea8  add     ecx, 14h
0x180004eab  cmp     ecx, 14h
0x180004eae  jnb     short loc_180004EE2
0x180004eb0  mov     rcx, [rsp+88h]; this
0x180004eb8  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004ebf  mov     r9d, 80090005h; char *
0x180004ec5  mov     edx, 1BCh; void *
0x180004eca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ecf  mov     eax, 80090005h
0x180004ed4  mov     rdi, [rsp+88h+var_18]
0x180004ed9  add     rsp, 80h
0x180004ee0  pop     rbx
0x180004ee1  retn
0x180004ee2  mov     edx, [rdi+4]
0x180004ee5  add     edx, ecx
0x180004ee7  cmp     edx, ecx
0x180004ee9  jb      short loc_180004F33
0x180004eeb  mov     ecx, [rdi+8]
0x180004eee  add     ecx, edx
0x180004ef0  cmp     ecx, edx
0x180004ef2  jb      short loc_180004F65
0x180004ef4  mov     edx, [rdi+10h]
0x180004ef7  add     edx, ecx
0x180004ef9  cmp     edx, ecx
0x180004efb  jnb     loc_180004F97
0x180004f01  mov     rcx, [rsp+88h]; this
0x180004f09  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004f10  mov     r9d, 80090005h; char *
0x180004f16  mov     edx, 1BFh; void *
0x180004f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f20  mov     rdi, [rsp+88h+var_18]
0x180004f25  mov     eax, 80090005h
0x180004f2a  add     rsp, 80h
0x180004f31  pop     rbx
0x180004f32  retn
0x180004f33  mov     rcx, [rsp+88h]; this
0x180004f3b  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004f42  mov     r9d, 80090005h; char *
0x180004f48  mov     edx, 1BDh; void *
0x180004f4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f52  mov     rdi, [rsp+88h+var_18]
0x180004f57  mov     eax, 80090005h
0x180004f5c  add     rsp, 80h
0x180004f63  pop     rbx
0x180004f64  retn
0x180004f65  mov     rcx, [rsp+88h]; this
0x180004f6d  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004f74  mov     r9d, 80090005h; char *
0x180004f7a  mov     edx, 1BEh; void *
0x180004f7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f84  mov     rdi, [rsp+88h+var_18]
0x180004f89  mov     eax, 80090005h
0x180004f8e  add     rsp, 80h
0x180004f95  pop     rbx
0x180004f96  retn
0x180004f97  cmp     r8d, edx
0x180004f9a  jnz     loc_18000524A
0x180004fa0  mov     r9, [rbx+38h]
0x180004fa4  lea     rax, [rsp+88h+hObject]
0x180004fac  mov     r8, [rbx+30h]
0x180004fb0  mov     rcx, r10; unsigned __int16 *
0x180004fb3  mov     rdx, [rbx+28h]
0x180004fb7  mov     [rsp+88h+var_60], rax; void **
0x180004fbc  movzx   r9d, byte ptr [r9]; bool
0x180004fc0  mov     r8, [r8]; HWND
0x180004fc3  mov     rdx, [rdx]; unsigned __int64
0x180004fc6  mov     [rsp+88h+var_10], rsi
0x180004fcb  mov     [rsp+88h+var_28], r15
0x180004fd0  xor     r15d, r15d
0x180004fd3  mov     [rsp+88h+hObject], r15
0x180004fdb  mov     qword ptr [rsp+88h+dwFlags], rdi; int
0x180004fe0  call    ?UnwrapNgcContentEncryptionKey@@YAJPEBG_KPEAUHWND__@@_NPEBU_NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB@@PEAPEAX@Z; UnwrapNgcContentEncryptionKey(ushort const *,unsigned __int64,HWND__ *,bool,_NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB const *,void * *)
0x180004fe5  mov     esi, eax
0x180004fe7  test    eax, eax
0x180004fe9  jns     short loc_18000505B
0x180004feb  mov     rcx, [rsp+88h]; this
0x180004ff3  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180004ffa  mov     r9d, eax; char *
0x180004ffd  mov     edx, 1C9h; void *
0x180005002  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005007  mov     rcx, [rsp+88h+hObject]; hKey
0x18000500f  test    rcx, rcx
0x180005012  jnz     loc_180005273
0x180005018  mov     eax, esi
0x18000501a  mov     rsi, [rsp+88h+var_10]
0x18000501f  mov     r15, [rsp+88h+var_28]
0x180005024  jmp     loc_180004ED4
0x180005029  mov     rcx, [rsp+88h]; this
0x180005031  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180005038  mov     r9d, 80090027h; char *
0x18000503e  mov     edx, 1B3h; void *
0x180005043  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005048  mov     rdi, [rsp+88h+var_18]
0x18000504d  mov     eax, 80090027h
0x180005052  add     rsp, 80h
0x180005059  pop     rbx
0x18000505a  retn
0x18000505b  mov     rsi, [rsp+88h+hObject]
0x180005063  lea     rdx, aIv; "IV"
0x18000506a  mov     [rsp+88h+arg_10], rbp
0x180005072  mov     rcx, rsi; hObject
0x180005075  mov     ebp, [rdi+4]
0x180005078  add     rbp, 14h
0x18000507c  mov     [rsp+88h+var_20], r14
0x180005081  mov     r14d, [rdi+8]
0x180005085  add     rbp, rdi
0x180005088  mov     edi, [rdi+0Ch]
0x18000508b  mov     r8, rbp; pbInput
0x18000508e  mov     r9d, r14d; cbInput
0x180005091  mov     [rsp+88h+dwFlags], r15d; uBytes
0x180005096  call    cs:__imp_BCryptSetProperty
0x18000509c  test    eax, eax
0x18000509e  jns     loc_18000527E
0x1800050a4  mov     rcx, [rsp+88h]; this
0x1800050ac  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800050b3  mov     r9d, eax; char *
0x1800050b6  mov     edx, 107h; void *
0x1800050bb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800050c0  mov     edi, eax
0x1800050c2  test    eax, eax
0x1800050c4  js      loc_180005196
0x1800050ca  mov     edx, r15d
0x1800050cd  mov     r8, r15
0x1800050d0  mov     rax, [rbx+18h]
0x1800050d4  mov     rcx, [rax]
0x1800050d7  mov     [rcx], r8
0x1800050da  mov     rax, [rbx+20h]
0x1800050de  mov     rcx, [rax]
0x1800050e1  mov     [rcx], edx
0x1800050e3  test    rsi, rsi
0x1800050e6  jnz     loc_180005301
0x1800050ec  mov     r14, [rsp+88h+var_20]
0x1800050f1  xor     eax, eax
0x1800050f3  mov     rbp, [rsp+88h+arg_10]
0x1800050fb  jmp     loc_18000501A
0x180005100  mov     rcx, [rsp+88h]; this
0x180005108  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18000510f  mov     r9d, 80090027h; char *
0x180005115  mov     edx, 1B2h; void *
0x18000511a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000511f  mov     eax, 80090027h
0x180005124  add     rsp, 80h
0x18000512b  pop     rbx
0x18000512c  retn
0x18000512d  mov     rcx, [rsp+88h]; this
0x180005135  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18000513c  mov     r9d, 80090027h; char *
0x180005142  mov     edx, 1B5h; void *
0x180005147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000514c  mov     rdi, [rsp+88h+var_18]
0x180005151  mov     eax, 80090027h
0x180005156  add     rsp, 80h
0x18000515d  pop     rbx
0x18000515e  retn
0x18000515f  mov     rcx, [rsp+88h]; this
0x180005167  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18000516e  mov     r9d, edi; char *
0x180005171  mov     edx, 112h; void *
0x180005176  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000517b  mov     rcx, [rsp+88h+hMem]; hMem
0x180005183  mov     [rsp+88h+hMem], r15
0x18000518b  test    rcx, rcx
0x18000518e  jz      short loc_180005196
0x180005190  call    cs:__imp_LocalFree
0x180005196  mov     rcx, [rsp+88h]; this
0x18000519e  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800051a5  mov     r9d, edi; char *
0x1800051a8  mov     edx, 1D7h; void *
0x1800051ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051b2  test    rsi, rsi
0x1800051b5  jnz     loc_1800052F3
0x1800051bb  mov     r14, [rsp+88h+var_20]
0x1800051c0  mov     eax, edi
0x1800051c2  mov     rbp, [rsp+88h+arg_10]
0x1800051ca  jmp     loc_18000501A
0x1800051cf  mov     rcx, [rsp+88h]; this
0x1800051d7  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800051de  mov     r9d, 80090027h; char *
0x1800051e4  mov     edx, 1B4h; void *
0x1800051e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051ee  mov     eax, 80090027h
0x1800051f3  jmp     loc_180004ED4
0x1800051f8  mov     rcx, [rsp+88h]; this
0x180005200  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180005207  mov     r9d, 80090027h; char *
0x18000520d  mov     edx, 1B6h; void *
0x180005212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005217  mov     eax, 80090027h
0x18000521c  jmp     loc_180004ED4
0x180005221  mov     rcx, [rsp+88h]; this
0x180005229  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180005230  mov     r9d, 80090005h; char *
0x180005236  mov     edx, 1B9h; void *
0x18000523b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005240  mov     eax, 80090005h
0x180005245  jmp     loc_180004ED4
0x18000524a  mov     rcx, [rsp+88h]; this
0x180005252  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180005259  mov     r9d, 80090005h; char *
0x18000525f  mov     edx, 1C0h; void *
0x180005264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005269  mov     eax, 80090005h
0x18000526e  jmp     loc_180004ED4
0x180005273  call    cs:__imp_BCryptDestroyKey
0x180005279  jmp     loc_180005018
0x18000527e  lea     rax, [rsp+88h+hMem]
0x180005286  mov     dword ptr [rsp+88h+hObject], r15d
0x18000528e  mov     [rsp+88h+var_48], rax
0x180005293  lea     rdx, [r14+rbp]; pbInput
0x180005297  lea     rax, [rsp+88h+hObject]
0x18000529f  mov     [rsp+88h+hMem], r15
0x1800052a7  mov     [rsp+88h+var_58], rax; unsigned __int8 **
0x1800052ac  mov     r8d, edi; cbInput
0x1800052af  lea     rax, [rsp+88h+var_40]
0x1800052b4  mov     qword ptr [rsp+88h+var_40], r15
0x1800052b9  mov     rcx, rsi; hKey
0x1800052bc  mov     [rsp+88h+var_60], rax; unsigned int
0x1800052c1  mov     [rsp+88h+var_38], 1
0x1800052c6  call    ?DecryptData@NgcUtils@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z; NgcUtils::DecryptData(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x1800052cb  lea     rcx, [rsp+88h+var_48]
0x1800052d0  mov     edi, eax
0x1800052d2  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800052d7  test    edi, edi
0x1800052d9  js      loc_18000515F
0x1800052df  mov     edx, dword ptr [rsp+88h+hObject]
0x1800052e6  mov     r8, [rsp+88h+hMem]
0x1800052ee  jmp     loc_1800050D0
0x1800052f3  mov     rcx, rsi; hKey
0x1800052f6  call    cs:__imp_BCryptDestroyKey
0x1800052fc  jmp     loc_1800051BB
0x180005301  mov     rcx, rsi; hKey
0x180005304  call    cs:__imp_BCryptDestroyKey
0x18000530a  jmp     loc_1800050EC
```
