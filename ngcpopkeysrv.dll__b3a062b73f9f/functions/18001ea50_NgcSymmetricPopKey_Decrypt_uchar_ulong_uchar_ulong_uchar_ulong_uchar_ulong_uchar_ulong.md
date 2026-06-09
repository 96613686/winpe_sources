# NgcSymmetricPopKey::Decrypt(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001ea50`
- end: `0x18001ebd7`
- name: `?Decrypt@NgcSymmetricPopKey@@UEAAJPEAEK0K0K0KPEAPEAEPEAK@Z`
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
- `0x180013834`
- `0x18001e904`
- `0x18001ea50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ebb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eb78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ebb7`

## string_xrefs

- `0x18001eacf`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`
- `0x18001eb54`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcSymmetricPopKey::Decrypt(
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
    v16 = 188;
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
    v16 = 191;
    goto LABEL_5;
  }
  memcpy_0(hMem, Src, Size);
  LODWORD(hMem) = 0;
  v25 = 0;
  v27 = &v25;
  *(_QWORD *)v28 = 0;
  v29 = 1;
  v18 = NgcUtils::DecryptData(hKey, a2, a3, (unsigned int)v17, Size, (unsigned int)v28, (unsigned __int8 **)&hMem, v23);
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
      (void *)0xCE,
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
0x18001ea50  push    rbp
0x18001ea52  push    rbx
0x18001ea53  push    rsi
0x18001ea54  push    rdi
0x18001ea55  push    r14
0x18001ea57  push    r15
0x18001ea59  mov     rbp, rsp
0x18001ea5c  sub     rsp, 78h
0x18001ea60  mov     r10, r9
0x18001ea63  mov     r14d, r8d
0x18001ea66  mov     r15, rdx
0x18001ea69  mov     [rbp+hKey], 0
0x18001ea71  lea     rax, [rbp+hKey]
0x18001ea75  mov     [rsp+78h+var_48], rax; void **
0x18001ea7a  mov     eax, [rbp+arg_30]
0x18001ea7d  mov     [rsp+78h+var_50], eax; unsigned int
0x18001ea81  mov     rax, [rbp+arg_28]
0x18001ea85  mov     qword ptr [rsp+78h+var_58], rax; int
0x18001ea8a  mov     r9d, [rbp+arg_20]; unsigned int
0x18001ea8e  mov     r8, r10; unsigned __int8 *
0x18001ea91  mov     edx, 1A1h; void *
0x18001ea96  call    ?CreateAesKey@NgcSymmetricPopKey@@IEAAJPEAXPEAEK1KPEAPEAX@Z; NgcSymmetricPopKey::CreateAesKey(void *,uchar *,ulong,uchar *,ulong,void * *)
0x18001ea9b  mov     ebx, eax
0x18001ea9d  test    eax, eax
0x18001ea9f  jns     short loc_18001EAAB
0x18001eaa1  mov     r9d, eax
0x18001eaa4  mov     edx, 0BCh
0x18001eaa9  jmp     short loc_18001EACF
0x18001eaab  mov     edi, dword ptr [rbp+Size]
0x18001eaae  mov     edx, edi
0x18001eab0  lea     rcx, [rbp+hMem]
0x18001eab4  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001eab9  mov     rbx, [rbp+hMem]
0x18001eabd  test    rbx, rbx
0x18001eac0  jnz     short loc_18001EAE4
0x18001eac2  mov     ebx, 8007000Eh
0x18001eac7  mov     r9d, ebx; char *
0x18001eaca  mov     edx, 0BFh; void *
0x18001eacf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ead6  mov     rcx, [rbp+30h]; this
0x18001eada  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eadf  jmp     loc_18001EBBF
0x18001eae4  mov     r8, rdi; Size
0x18001eae7  mov     rdx, [rbp+Src]; Src
0x18001eaeb  mov     rcx, rbx; void *
0x18001eaee  call    memcpy_0
0x18001eaf3  mov     dword ptr [rbp+hMem], 0
0x18001eafa  mov     [rbp+var_30], 0
0x18001eb02  lea     rax, [rbp+var_30]
0x18001eb06  mov     [rbp+var_20], rax
0x18001eb0a  mov     qword ptr [rbp+var_18], 0
0x18001eb12  mov     [rbp+var_10], 1
0x18001eb16  lea     rax, [rbp+hMem]
0x18001eb1a  mov     [rsp+78h+var_48], rax; unsigned __int8 **
0x18001eb1f  lea     rax, [rbp+var_18]
0x18001eb23  mov     qword ptr [rsp+78h+var_50], rax; unsigned int
0x18001eb28  mov     [rsp+78h+var_58], edi; int
0x18001eb2c  mov     r9, rbx; unsigned int
0x18001eb2f  mov     r8d, r14d; cbInput
0x18001eb32  mov     rdx, r15; pbInput
0x18001eb35  mov     rcx, [rbp+hKey]; hKey
0x18001eb39  call    ?DecryptData@NgcUtils@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z; NgcUtils::DecryptData(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18001eb3e  mov     edi, eax
0x18001eb40  lea     rcx, [rbp+var_20]
0x18001eb44  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001eb49  test    edi, edi
0x18001eb4b  jns     short loc_18001EB82
0x18001eb4d  mov     rcx, [rbp+30h]; this
0x18001eb51  mov     r9d, edi; char *
0x18001eb54  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001eb5b  mov     edx, 0CEh; void *
0x18001eb60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb65  xor     edx, edx
0x18001eb67  lea     rcx, [rbp+var_30]
0x18001eb6b  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001eb70  test    rbx, rbx
0x18001eb73  jz      short loc_18001EB7E
0x18001eb75  mov     rcx, rbx; hMem
0x18001eb78  call    cs:__imp_LocalFree
0x18001eb7e  mov     ebx, edi
0x18001eb80  jmp     short loc_18001EBBF
0x18001eb82  mov     rdx, [rbp+var_30]
0x18001eb86  mov     [rbp+var_30], 0
0x18001eb8e  mov     rax, [rbp+arg_48]
0x18001eb95  mov     [rax], rdx
0x18001eb98  mov     rdx, [rbp+arg_50]
0x18001eb9f  mov     eax, dword ptr [rbp+hMem]
0x18001eba2  mov     [rdx], eax
0x18001eba4  xor     edx, edx
0x18001eba6  lea     rcx, [rbp+var_30]
0x18001ebaa  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001ebaf  test    rbx, rbx
0x18001ebb2  jz      short loc_18001EBBD
0x18001ebb4  mov     rcx, rbx; hMem
0x18001ebb7  call    cs:__imp_LocalFree
0x18001ebbd  xor     ebx, ebx
0x18001ebbf  lea     rcx, [rbp+hKey]
0x18001ebc3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ebc8  mov     eax, ebx
0x18001ebca  add     rsp, 78h
0x18001ebce  pop     r15
0x18001ebd0  pop     r14
0x18001ebd2  pop     rdi
0x18001ebd3  pop     rsi
0x18001ebd4  pop     rbx
0x18001ebd5  pop     rbp
0x18001ebd6  retn
```
