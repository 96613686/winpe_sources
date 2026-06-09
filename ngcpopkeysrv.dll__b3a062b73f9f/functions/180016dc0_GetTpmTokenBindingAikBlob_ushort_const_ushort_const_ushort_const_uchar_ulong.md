# GetTpmTokenBindingAikBlob(ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x180016dc0`
- end: `0x180016f4f`
- name: `?GetTpmTokenBindingAikBlob@@YAJPEBG00PEAPEAEPEAK@Z`
- size: `399`
- prototype: `__int64 __fastcall(NgcUtils *, const unsigned __int16 *, NgcUtils *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f464`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18000db5c`
- `0x18001070c`
- `0x180010730`
- `0x180011e48`
- `0x180013e3c`
- `0x180015bf0`
- `0x180016dc0`

## string_xrefs

- `0x180016e46`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180016ecc`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
__int64 __fastcall GetTpmTokenBindingAikBlob(
        NgcUtils *a1,
        const unsigned __int16 *a2,
        NgcUtils *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  int Aik; // eax
  unsigned int v8; // ebx
  unsigned __int8 *v10; // rax
  int v11; // [rsp+20h] [rbp-50h]
  int v12; // [rsp+20h] [rbp-50h]
  unsigned int *v13; // [rsp+28h] [rbp-48h]
  NCRYPT_KEY_HANDLE hKey; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 *v15; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v16; // [rsp+50h] [rbp-20h] BYREF
  NgcUtils *v17; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v18[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v19; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  unsigned __int8 *v21; // [rsp+80h] [rbp+10h] BYREF

  v19 = 0;
  v17 = a1;
  *(_QWORD *)v18 = a2;
  v16 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v16,
    0);
  hKey = 0;
  Aik = GetAik(5u, &v17, a3, 0, &hKey, (__int64)&v21, &v16);
  v8 = Aik;
  if ( Aik < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)Aik,
      v11);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    return v8;
  }
  LODWORD(v21) = 0;
  v15 = 0;
  v17 = (NgcUtils *)&v15;
  *(_QWORD *)v18 = 0;
  LOBYTE(v19) = 1;
  v8 = NgcUtils::ExportNCryptKey(hKey, L"PUBLICBLOB", 0, (unsigned int)v18, &v21, v13);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v17);
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x293,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)v8,
      v12);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v15, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    return v8;
  }
  v10 = v15;
  v15 = 0;
  *a4 = v10;
  *a5 = (unsigned int)v21;
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v15, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180016dc0  mov     [rsp-8+arg_8], rbx
0x180016dc5  mov     [rsp-8+arg_10], rdi
0x180016dca  push    rbp
0x180016dcb  mov     rbp, rsp
0x180016dce  sub     rsp, 70h
0x180016dd2  mov     rdi, r9
0x180016dd5  mov     rbx, r8
0x180016dd8  mov     [rbp+var_8], 0
0x180016de0  mov     [rbp+var_18], rcx
0x180016de4  mov     qword ptr [rbp+var_10], rdx
0x180016de8  mov     [rbp+hKey], 0
0x180016df0  mov     [rbp+var_20], 0
0x180016df8  xor     edx, edx
0x180016dfa  lea     rcx, [rbp+var_20]
0x180016dfe  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180016e03  mov     [rbp+hKey], 0
0x180016e0b  lea     rax, [rbp+var_20]
0x180016e0f  mov     [rsp+70h+var_40], rax
0x180016e14  lea     rax, [rbp+arg_0]
0x180016e18  mov     [rsp+70h+var_48], rax; unsigned int *
0x180016e1d  lea     rax, [rbp+hKey]
0x180016e21  mov     [rsp+70h+var_50], rax; int
0x180016e26  xor     r9d, r9d
0x180016e29  mov     r8, rbx
0x180016e2c  lea     rdx, [rbp+var_18]
0x180016e30  lea     ecx, [r9+5]
0x180016e34  call    ?GetAik@@YAJW4PregenKeyType@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBG_NPEA_KPEAW4DelayRetryAction@@PEAPEAG@Z; GetAik(PregenKeyType,_NGC_IDP_ACCOUNT_INFO *,ushort const *,bool,unsigned __int64 *,DelayRetryAction *,ushort * *)
0x180016e39  mov     ebx, eax
0x180016e3b  test    eax, eax
0x180016e3d  jns     short loc_180016E73
0x180016e3f  mov     rcx, [rbp+8]; this
0x180016e43  mov     r9d, eax; char *
0x180016e46  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016e4d  mov     edx, 289h; void *
0x180016e52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e57  nop
0x180016e58  lea     rcx, [rbp+var_20]
0x180016e5c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016e61  nop
0x180016e62  lea     rcx, [rbp+hKey]
0x180016e66  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016e6b  nop
0x180016e6c  mov     eax, ebx
0x180016e6e  jmp     loc_180016F3D
0x180016e73  mov     dword ptr [rbp+arg_0], 0
0x180016e7a  mov     [rbp+var_28], 0
0x180016e82  lea     rax, [rbp+var_28]
0x180016e86  mov     [rbp+var_18], rax
0x180016e8a  mov     qword ptr [rbp+var_10], 0
0x180016e92  mov     byte ptr [rbp+var_8], 1
0x180016e96  lea     rax, [rbp+arg_0]
0x180016e9a  mov     [rsp+70h+var_50], rax; int
0x180016e9f  lea     r9, [rbp+var_10]; unsigned int
0x180016ea3  xor     r8d, r8d; dwFlags
0x180016ea6  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180016ead  mov     rcx, [rbp+hKey]; hKey
0x180016eb1  call    ?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z; NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)
0x180016eb6  mov     ebx, eax
0x180016eb8  lea     rcx, [rbp+var_18]
0x180016ebc  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180016ec1  test    ebx, ebx
0x180016ec3  jns     short loc_180016F03
0x180016ec5  mov     rcx, [rbp+8]; this
0x180016ec9  mov     r9d, ebx; char *
0x180016ecc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016ed3  mov     edx, 293h; void *
0x180016ed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016edd  nop
0x180016ede  xor     edx, edx
0x180016ee0  lea     rcx, [rbp+var_28]
0x180016ee4  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180016ee9  nop
0x180016eea  lea     rcx, [rbp+var_20]
0x180016eee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016ef3  nop
0x180016ef4  lea     rcx, [rbp+hKey]
0x180016ef8  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016efd  nop
0x180016efe  jmp     loc_180016E6C
0x180016f03  mov     rax, [rbp+var_28]
0x180016f07  mov     [rbp+var_28], 0
0x180016f0f  mov     [rdi], rax
0x180016f12  mov     rcx, [rbp+arg_20]
0x180016f16  mov     eax, dword ptr [rbp+arg_0]
0x180016f19  mov     [rcx], eax
0x180016f1b  xor     edx, edx
0x180016f1d  lea     rcx, [rbp+var_28]
0x180016f21  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180016f26  nop
0x180016f27  lea     rcx, [rbp+var_20]
0x180016f2b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016f30  nop
0x180016f31  lea     rcx, [rbp+hKey]
0x180016f35  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016f3a  nop
0x180016f3b  xor     eax, eax
0x180016f3d  lea     r11, [rsp+70h+var_s0]
0x180016f42  mov     rbx, [r11+18h]
0x180016f46  mov     rdi, [r11+20h]
0x180016f4a  mov     rsp, r11
0x180016f4d  pop     rbp
0x180016f4e  retn
```
