# NgcSymmetricPopKey::DecryptGcm(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001ebe0`
- end: `0x18001ed3e`
- name: `?DecryptGcm@NgcSymmetricPopKey@@QEAAJPEAEK0K0K0K0K0KPEAPEAEPEAK@Z`
- size: `350`
- prototype: `__int64 __fastcall(NgcSymmetricPopKey *this, unsigned __int8 *, ULONG, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, ULONG, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012a08`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x1800137f4`
- `0x180013994`
- `0x18001e904`
- `0x18001ebe0`

## string_xrefs

- `0x18001ec39`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`
- `0x18001ecda`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcSymmetricPopKey::DecryptGcm(
        NgcSymmetricPopKey *this,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        ULONG a9,
        unsigned __int8 *a10,
        unsigned int a11,
        unsigned __int8 *a12,
        unsigned int a13,
        unsigned __int8 **a14,
        unsigned int *a15)
{
  int v17; // eax
  int v18; // ebx
  unsigned __int8 *v19; // rcx
  int v21; // [rsp+20h] [rbp-71h]
  int v22; // [rsp+20h] [rbp-71h]
  unsigned __int8 *v23; // [rsp+30h] [rbp-61h]
  unsigned __int8 *v24; // [rsp+40h] [rbp-51h]
  unsigned int *v25; // [rsp+58h] [rbp-39h]
  unsigned __int8 *v26; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int8 *v27; // [rsp+68h] [rbp-29h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+70h] [rbp-21h] BYREF
  unsigned __int8 **v29; // [rsp+78h] [rbp-19h] BYREF
  unsigned int v30[2]; // [rsp+80h] [rbp-11h] BYREF
  char v31; // [rsp+88h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+27h]

  hKey = 0;
  v17 = NgcSymmetricPopKey::CreateAesKey(this, (void *)0x1E1, a4, a5, a6, a7, &hKey);
  v18 = v17;
  if ( v17 >= 0 )
  {
    LODWORD(v26) = 0;
    v27 = 0;
    v29 = &v27;
    *(_QWORD *)v30 = 0;
    v31 = 1;
    LODWORD(v24) = a13;
    LODWORD(v23) = a11;
    v18 = NgcUtils::DecryptDataAuthenticated(
            hKey,
            a2,
            a3,
            (unsigned int)a8,
            a9,
            a10,
            v23,
            (unsigned int)a12,
            v24,
            (unsigned int)v30,
            &v26,
            v25);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v29);
    if ( v18 >= 0 )
    {
      v19 = v27;
      v27 = 0;
      *a14 = v19;
      *a15 = (unsigned int)v26;
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v27,
        0);
      v18 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12F,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
        (const char *)(unsigned int)v18,
        v22);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v27,
        0);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x120,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
      (const char *)(unsigned int)v17,
      v21);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18001ebe0  push    rbp
0x18001ebe2  push    rbx
0x18001ebe3  push    rsi
0x18001ebe4  push    rdi
0x18001ebe5  lea     rbp, [rsp-7]
0x18001ebea  sub     rsp, 98h
0x18001ebf1  mov     r10, r9
0x18001ebf4  mov     edi, r8d
0x18001ebf7  mov     rsi, rdx
0x18001ebfa  mov     [rbp+1Fh+hKey], 0
0x18001ec02  lea     rax, [rbp+1Fh+hKey]
0x18001ec06  mov     [rsp+0B0h+var_80], rax; void **
0x18001ec0b  mov     eax, [rbp+1Fh+arg_30]
0x18001ec0e  mov     dword ptr [rsp+0B0h+var_88], eax; unsigned int
0x18001ec12  mov     rax, [rbp+1Fh+arg_28]
0x18001ec16  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18001ec1b  mov     r9d, [rbp+1Fh+arg_20]; unsigned int
0x18001ec1f  mov     r8, r10; unsigned __int8 *
0x18001ec22  mov     edx, 1E1h; void *
0x18001ec27  call    ?CreateAesKey@NgcSymmetricPopKey@@IEAAJPEAXPEAEK1KPEAPEAX@Z; NgcSymmetricPopKey::CreateAesKey(void *,uchar *,ulong,uchar *,ulong,void * *)
0x18001ec2c  mov     ebx, eax
0x18001ec2e  test    eax, eax
0x18001ec30  jns     short loc_18001EC4F
0x18001ec32  mov     rcx, [rbp+27h]; this
0x18001ec36  mov     r9d, eax; char *
0x18001ec39  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ec40  mov     edx, 120h; void *
0x18001ec45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec4a  jmp     loc_18001ED27
0x18001ec4f  mov     dword ptr [rbp+1Fh+var_50], 0
0x18001ec56  mov     [rbp+1Fh+var_48], 0
0x18001ec5e  lea     rax, [rbp+1Fh+var_48]
0x18001ec62  mov     [rbp+1Fh+var_38], rax
0x18001ec66  mov     qword ptr [rbp+1Fh+var_30], 0
0x18001ec6e  mov     [rbp+1Fh+var_28], 1
0x18001ec72  lea     rax, [rbp+1Fh+var_50]
0x18001ec76  mov     [rsp+0B0h+var_60], rax; unsigned __int8 **
0x18001ec7b  lea     rax, [rbp+1Fh+var_30]
0x18001ec7f  mov     qword ptr [rsp+0B0h+var_68], rax; unsigned int
0x18001ec84  mov     eax, dword ptr [rbp+1Fh+arg_60]
0x18001ec8a  mov     dword ptr [rsp+0B0h+var_70], eax; unsigned __int8 *
0x18001ec8e  mov     rax, [rbp+1Fh+arg_58]
0x18001ec95  mov     qword ptr [rsp+0B0h+var_78], rax; unsigned int
0x18001ec9a  mov     eax, dword ptr [rbp+1Fh+arg_50]
0x18001ec9d  mov     dword ptr [rsp+0B0h+var_80], eax; unsigned __int8 *
0x18001eca1  mov     rax, [rbp+1Fh+arg_48]
0x18001eca5  mov     [rsp+0B0h+var_88], rax; PUCHAR
0x18001ecaa  mov     eax, [rbp+1Fh+arg_40]
0x18001ecad  mov     [rsp+0B0h+var_90], eax; int
0x18001ecb1  mov     r9, [rbp+1Fh+arg_38]; unsigned int
0x18001ecb5  mov     r8d, edi; cbInput
0x18001ecb8  mov     rdx, rsi; pbInput
0x18001ecbb  mov     rcx, [rbp+1Fh+hKey]; hKey
0x18001ecbf  call    ?DecryptDataAuthenticated@NgcUtils@@YAJPEAXPEAEK1K1K1KPEAPEAEPEAK@Z; NgcUtils::DecryptDataAuthenticated(void *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18001ecc4  mov     ebx, eax
0x18001ecc6  lea     rcx, [rbp+1Fh+var_38]
0x18001ecca  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001eccf  test    ebx, ebx
0x18001ecd1  jns     short loc_18001ECF8
0x18001ecd3  mov     rcx, [rbp+27h]; this
0x18001ecd7  mov     r9d, ebx; char *
0x18001ecda  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ece1  mov     edx, 12Fh; void *
0x18001ece6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eceb  xor     edx, edx
0x18001eced  lea     rcx, [rbp+1Fh+var_48]
0x18001ecf1  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001ecf6  jmp     short loc_18001ED27
0x18001ecf8  mov     rcx, [rbp+1Fh+var_48]
0x18001ecfc  mov     [rbp+1Fh+var_48], 0
0x18001ed04  mov     rax, [rbp+1Fh+arg_68]
0x18001ed0b  mov     [rax], rcx
0x18001ed0e  mov     rcx, [rbp+1Fh+arg_70]
0x18001ed15  mov     eax, dword ptr [rbp+1Fh+var_50]
0x18001ed18  mov     [rcx], eax
0x18001ed1a  xor     edx, edx
0x18001ed1c  lea     rcx, [rbp+1Fh+var_48]
0x18001ed20  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001ed25  xor     ebx, ebx
0x18001ed27  lea     rcx, [rbp+1Fh+hKey]
0x18001ed2b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ed30  mov     eax, ebx
0x18001ed32  add     rsp, 98h
0x18001ed39  pop     rdi
0x18001ed3a  pop     rsi
0x18001ed3b  pop     rbx
0x18001ed3c  pop     rbp
0x18001ed3d  retn
```
