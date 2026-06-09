# NgcSymmetricPopKey::Encrypt(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001ed50`
- end: `0x18001eed7`
- name: `?Encrypt@NgcSymmetricPopKey@@UEAAJPEAEK0K0K0KPEAPEAEPEAK@Z`
- size: `391`
- prototype: `__int64 __fastcall(NgcSymmetricPopKey *this, unsigned __int8 *, ULONG, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *Src, unsigned int Size, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006415`
- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180013270`
- `0x1800137f4`
- `0x180013b38`
- `0x18001e904`
- `0x18001ed50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eeb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eeb7`

## string_xrefs

- `0x18001edcf`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`
- `0x18001ee54`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcSymmetricPopKey::Encrypt(
        NgcSymmetricPopKey *this,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *Src,
        unsigned int Size,
        unsigned __int8 **a10,
        unsigned int *a11)
{
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rdx
  HLOCAL v17; // rbx
  int v18; // edi
  unsigned __int8 *v19; // rdx
  int v21; // [rsp+20h] [rbp-58h]
  int v22; // [rsp+20h] [rbp-58h]
  unsigned int *v23; // [rsp+38h] [rbp-40h]
  HLOCAL hMem; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int8 *v25; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int8 **v27; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v28[2]; // [rsp+60h] [rbp-18h] BYREF
  char v29; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  hKey = 0;
  v13 = NgcSymmetricPopKey::CreateAesKey(this, (void *)0x1A1, a4, a5, a6, a7, &hKey);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = (unsigned int)v13;
    v16 = 141;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
      (const char *)v15,
      v21);
    goto LABEL_13;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, Size);
  v17 = hMem;
  if ( !hMem )
  {
    v14 = -2147024882;
    v15 = 2147942414LL;
    v16 = 144;
    goto LABEL_5;
  }
  memcpy_0(hMem, Src, Size);
  LODWORD(hMem) = 0;
  v25 = 0;
  v27 = &v25;
  *(_QWORD *)v28 = 0;
  v29 = 1;
  v18 = NgcUtils::EncryptData(hKey, a2, a3, (unsigned int)v17, Size, (unsigned int)v28, (unsigned __int8 **)&hMem, v23);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v27);
  if ( v18 >= 0 )
  {
    v19 = v25;
    v25 = 0;
    *a10 = v19;
    *a11 = (unsigned int)hMem;
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v25, 0);
    if ( v17 )
      LocalFree(v17);
    v14 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
      (const char *)(unsigned int)v18,
      v22);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v25, 0);
    if ( v17 )
      LocalFree(v17);
    v14 = v18;
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
  return v14;
}

```

## disassembly

```asm
0x18001ed50  push    rbp
0x18001ed52  push    rbx
0x18001ed53  push    rsi
0x18001ed54  push    rdi
0x18001ed55  push    r14
0x18001ed57  push    r15
0x18001ed59  mov     rbp, rsp
0x18001ed5c  sub     rsp, 78h
0x18001ed60  mov     r10, r9
0x18001ed63  mov     r14d, r8d
0x18001ed66  mov     r15, rdx
0x18001ed69  mov     [rbp+hKey], 0
0x18001ed71  lea     rax, [rbp+hKey]
0x18001ed75  mov     [rsp+78h+var_48], rax; void **
0x18001ed7a  mov     eax, [rbp+arg_30]
0x18001ed7d  mov     [rsp+78h+var_50], eax; unsigned int
0x18001ed81  mov     rax, [rbp+arg_28]
0x18001ed85  mov     qword ptr [rsp+78h+var_58], rax; int
0x18001ed8a  mov     r9d, [rbp+arg_20]; unsigned int
0x18001ed8e  mov     r8, r10; unsigned __int8 *
0x18001ed91  mov     edx, 1A1h; void *
0x18001ed96  call    ?CreateAesKey@NgcSymmetricPopKey@@IEAAJPEAXPEAEK1KPEAPEAX@Z; NgcSymmetricPopKey::CreateAesKey(void *,uchar *,ulong,uchar *,ulong,void * *)
0x18001ed9b  mov     ebx, eax
0x18001ed9d  test    eax, eax
0x18001ed9f  jns     short loc_18001EDAB
0x18001eda1  mov     r9d, eax
0x18001eda4  mov     edx, 8Dh
0x18001eda9  jmp     short loc_18001EDCF
0x18001edab  mov     edi, dword ptr [rbp+Size]
0x18001edae  mov     edx, edi
0x18001edb0  lea     rcx, [rbp+hMem]
0x18001edb4  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001edb9  mov     rbx, [rbp+hMem]
0x18001edbd  test    rbx, rbx
0x18001edc0  jnz     short loc_18001EDE4
0x18001edc2  mov     ebx, 8007000Eh
0x18001edc7  mov     r9d, ebx; char *
0x18001edca  mov     edx, 90h; void *
0x18001edcf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001edd6  mov     rcx, [rbp+30h]; this
0x18001edda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eddf  jmp     loc_18001EEBF
0x18001ede4  mov     r8, rdi; Size
0x18001ede7  mov     rdx, [rbp+Src]; Src
0x18001edeb  mov     rcx, rbx; void *
0x18001edee  call    memcpy_0
0x18001edf3  mov     dword ptr [rbp+hMem], 0
0x18001edfa  mov     [rbp+var_30], 0
0x18001ee02  lea     rax, [rbp+var_30]
0x18001ee06  mov     [rbp+var_20], rax
0x18001ee0a  mov     qword ptr [rbp+var_18], 0
0x18001ee12  mov     [rbp+var_10], 1
0x18001ee16  lea     rax, [rbp+hMem]
0x18001ee1a  mov     [rsp+78h+var_48], rax; unsigned __int8 **
0x18001ee1f  lea     rax, [rbp+var_18]
0x18001ee23  mov     qword ptr [rsp+78h+var_50], rax; unsigned int
0x18001ee28  mov     [rsp+78h+var_58], edi; int
0x18001ee2c  mov     r9, rbx; unsigned int
0x18001ee2f  mov     r8d, r14d; cbInput
0x18001ee32  mov     rdx, r15; pbInput
0x18001ee35  mov     rcx, [rbp+hKey]; hKey
0x18001ee39  call    ?EncryptData@NgcUtils@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z; NgcUtils::EncryptData(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18001ee3e  mov     edi, eax
0x18001ee40  lea     rcx, [rbp+var_20]
0x18001ee44  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001ee49  test    edi, edi
0x18001ee4b  jns     short loc_18001EE82
0x18001ee4d  mov     rcx, [rbp+30h]; this
0x18001ee51  mov     r9d, edi; char *
0x18001ee54  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ee5b  mov     edx, 9Fh; void *
0x18001ee60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee65  xor     edx, edx
0x18001ee67  lea     rcx, [rbp+var_30]
0x18001ee6b  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001ee70  test    rbx, rbx
0x18001ee73  jz      short loc_18001EE7E
0x18001ee75  mov     rcx, rbx; hMem
0x18001ee78  call    cs:__imp_LocalFree
0x18001ee7e  mov     ebx, edi
0x18001ee80  jmp     short loc_18001EEBF
0x18001ee82  mov     rdx, [rbp+var_30]
0x18001ee86  mov     [rbp+var_30], 0
0x18001ee8e  mov     rax, [rbp+arg_48]
0x18001ee95  mov     [rax], rdx
0x18001ee98  mov     rdx, [rbp+arg_50]
0x18001ee9f  mov     eax, dword ptr [rbp+hMem]
0x18001eea2  mov     [rdx], eax
0x18001eea4  xor     edx, edx
0x18001eea6  lea     rcx, [rbp+var_30]
0x18001eeaa  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001eeaf  test    rbx, rbx
0x18001eeb2  jz      short loc_18001EEBD
0x18001eeb4  mov     rcx, rbx; hMem
0x18001eeb7  call    cs:__imp_LocalFree
0x18001eebd  xor     ebx, ebx
0x18001eebf  lea     rcx, [rbp+hKey]
0x18001eec3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001eec8  mov     eax, ebx
0x18001eeca  add     rsp, 78h
0x18001eece  pop     r15
0x18001eed0  pop     r14
0x18001eed2  pop     rdi
0x18001eed3  pop     rsi
0x18001eed4  pop     rbx
0x18001eed5  pop     rbp
0x18001eed6  retn
```
