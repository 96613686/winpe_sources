# _lambda_e82d19b8eb780fd1bda3c5533e431fc2_::operator()

- ea: `0x18002aa3c`
- end: `0x18002ab90`
- name: `_lambda_e82d19b8eb780fd1bda3c5533e431fc2_::operator()`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002aa14`

## callees

- `0x180006538`
- `0x180009510`
- `0x1800167f8`
- `0x180018430`
- `0x180018460`
- `0x18002aa3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab75`

## string_xrefs

- `0x18002aa5c`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18002aab5`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x18002ab15`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall lambda_e82d19b8eb780fd1bda3c5533e431fc2_::operator()(_QWORD **a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  unsigned int UserIdKeyPublicKey; // ebx
  int v5; // eax
  const unsigned __int16 *v6; // rdx
  HLOCAL v7; // rcx
  _QWORD **v8; // rax
  HLOCAL v9; // rdx
  HLOCAL v10; // rcx
  HLOCAL *p_hMem; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int8 *v13; // [rsp+28h] [rbp-18h] BYREF
  char v14; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int v16; // [rsp+60h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int64 v18; // [rsp+70h] [rbp+30h] BYREF

  v2 = *a1;
  if ( !*v2 )
  {
    v3 = 1271;
LABEL_3:
    UserIdKeyPublicKey = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)0x80090027LL,
      (int)p_hMem);
    return UserIdKeyPublicKey;
  }
  if ( !*a1[1] )
  {
    v3 = 1272;
    goto LABEL_3;
  }
  if ( !*a1[2] )
  {
    v3 = 1273;
    goto LABEL_3;
  }
  v18 = 0;
  v5 = NgcOpenUserIdKey(*v2, &v18);
  UserIdKeyPublicKey = v5;
  if ( v5 >= 0 )
  {
    p_hMem = &hMem;
    v16 = 0;
    hMem = 0;
    v13 = 0;
    v14 = 1;
    UserIdKeyPublicKey = GetUserIdKeyPublicKey(v18, v6, &v13, &v16);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( (UserIdKeyPublicKey & 0x80000000) == 0 )
    {
      v8 = (_QWORD **)a1[1];
      v9 = hMem;
      hMem = 0;
      **v8 = v9;
      *(_DWORD *)*a1[2] = v16;
      v10 = hMem;
      hMem = 0;
      if ( v10 )
        LocalFree(v10);
      UserIdKeyPublicKey = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x506,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
        (const char *)UserIdKeyPublicKey,
        (int)p_hMem);
      v7 = hMem;
      hMem = 0;
      if ( v7 )
        LocalFree(v7);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4FE,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v5,
      (int)p_hMem);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v18);
  return UserIdKeyPublicKey;
}

```

## disassembly

```asm
0x18002aa3c  push    rbp
0x18002aa3e  push    rbx
0x18002aa3f  push    rdi
0x18002aa40  mov     rbp, rsp
0x18002aa43  sub     rsp, 40h
0x18002aa47  mov     rdi, rcx
0x18002aa4a  mov     rcx, [rcx]
0x18002aa4d  cmp     qword ptr [rcx], 0
0x18002aa51  jnz     short loc_18002AA75
0x18002aa53  mov     edx, 4F7h; void *
0x18002aa58  mov     rcx, [rbp+18h]; this
0x18002aa5c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002aa63  mov     ebx, 80090027h
0x18002aa68  mov     r9d, ebx; char *
0x18002aa6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aa70  jmp     loc_18002AB86
0x18002aa75  mov     rax, [rdi+8]
0x18002aa79  cmp     qword ptr [rax], 0
0x18002aa7d  jnz     short loc_18002AA86
0x18002aa7f  mov     edx, 4F8h
0x18002aa84  jmp     short loc_18002AA58
0x18002aa86  mov     rax, [rdi+10h]
0x18002aa8a  cmp     qword ptr [rax], 0
0x18002aa8e  jnz     short loc_18002AA97
0x18002aa90  mov     edx, 4F9h
0x18002aa95  jmp     short loc_18002AA58
0x18002aa97  mov     [rbp+arg_10], 0
0x18002aa9f  lea     rdx, [rbp+arg_10]
0x18002aaa3  mov     rcx, [rcx]
0x18002aaa6  call    NgcOpenUserIdKey
0x18002aaab  mov     ebx, eax
0x18002aaad  test    eax, eax
0x18002aaaf  jns     short loc_18002AACE
0x18002aab1  mov     rcx, [rbp+18h]; this
0x18002aab5  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002aabc  mov     r9d, eax; char *
0x18002aabf  mov     edx, 4FEh; void *
0x18002aac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aac9  jmp     loc_18002AB7D
0x18002aace  mov     rcx, [rbp+arg_10]; unsigned __int64
0x18002aad2  lea     rax, [rbp+hMem]
0x18002aad6  lea     r9, [rbp+arg_0]; unsigned int *
0x18002aada  mov     [rbp+var_20], rax
0x18002aade  lea     r8, [rbp+var_18]; unsigned __int8 **
0x18002aae2  mov     [rbp+arg_0], 0
0x18002aae9  mov     [rbp+hMem], 0
0x18002aaf1  mov     [rbp+var_18], 0
0x18002aaf9  mov     [rbp+var_10], 1
0x18002aafd  call    ?GetUserIdKeyPublicKey@@YAJ_KPEBGPEAPEAEPEAK@Z; GetUserIdKeyPublicKey(unsigned __int64,ushort const *,uchar * *,ulong *)
0x18002ab02  lea     rcx, [rbp+var_20]
0x18002ab06  mov     ebx, eax
0x18002ab08  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18002ab0d  test    ebx, ebx
0x18002ab0f  jns     short loc_18002AB42
0x18002ab11  mov     rcx, [rbp+18h]; this
0x18002ab15  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002ab1c  mov     r9d, ebx; char *
0x18002ab1f  mov     edx, 506h; void *
0x18002ab24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ab29  mov     rcx, [rbp+hMem]; hMem
0x18002ab2d  mov     [rbp+hMem], 0
0x18002ab35  test    rcx, rcx
0x18002ab38  jz      short loc_18002AB7D
0x18002ab3a  call    cs:__imp_LocalFree
0x18002ab40  jmp     short loc_18002AB7D
0x18002ab42  mov     rax, [rdi+8]
0x18002ab46  mov     rdx, [rbp+hMem]
0x18002ab4a  mov     [rbp+hMem], 0
0x18002ab52  mov     rcx, [rax]
0x18002ab55  mov     [rcx], rdx
0x18002ab58  mov     rax, [rdi+10h]
0x18002ab5c  mov     rcx, [rax]
0x18002ab5f  mov     eax, [rbp+arg_0]
0x18002ab62  mov     [rcx], eax
0x18002ab64  mov     rcx, [rbp+hMem]; hMem
0x18002ab68  mov     [rbp+hMem], 0
0x18002ab70  test    rcx, rcx
0x18002ab73  jz      short loc_18002AB7B
0x18002ab75  call    cs:__imp_LocalFree
0x18002ab7b  xor     ebx, ebx
0x18002ab7d  lea     rcx, [rbp+arg_10]
0x18002ab81  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18002ab86  mov     eax, ebx
0x18002ab88  add     rsp, 40h
0x18002ab8c  pop     rdi
0x18002ab8d  pop     rbx
0x18002ab8e  pop     rbp
0x18002ab8f  retn
```
