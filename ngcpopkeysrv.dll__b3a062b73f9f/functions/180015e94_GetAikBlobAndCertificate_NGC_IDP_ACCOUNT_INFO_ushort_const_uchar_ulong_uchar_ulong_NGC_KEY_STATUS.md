# GetAikBlobAndCertificate(_NGC_IDP_ACCOUNT_INFO *,ushort const *,uchar * *,ulong *,uchar * *,ulong *,_NGC_KEY_STATUS *)

- ea: `0x180015e94`
- end: `0x180016084`
- name: `?GetAikBlobAndCertificate@@YAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBGPEAPEAEPEAK23PEAW4_NGC_KEY_STATUS@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, enum _NGC_KEY_STATUS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e03c`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180011e48`
- `0x180013e3c`
- `0x1800141e4`
- `0x180015608`
- `0x180015bf0`
- `0x180015e94`

## string_xrefs

- `0x180015f08`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180015f79`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180015fe9`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
__int64 __fastcall GetAikBlobAndCertificate(
        struct _NGC_IDP_ACCOUNT_INFO *a1,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        enum _NGC_KEY_STATUS *a7)
{
  enum _NGC_KEY_STATUS *v9; // rdi
  int Aik; // ebx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rcx
  unsigned int *v14; // [rsp+20h] [rbp-51h]
  int v15; // [rsp+20h] [rbp-51h]
  unsigned __int8 *v16; // [rsp+40h] [rbp-31h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int8 *v18; // [rsp+50h] [rbp-21h] BYREF
  unsigned __int8 *v19; // [rsp+58h] [rbp-19h] BYREF
  unsigned __int8 **v20; // [rsp+60h] [rbp-11h] BYREF
  unsigned int v21[2]; // [rsp+68h] [rbp-9h] BYREF
  char v22; // [rsp+70h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+47h]

  v9 = a7;
  *(_DWORD *)a7 = 3;
  LODWORD(a7) = 0;
  hKey = 0;
  Aik = GetAik(1, a1, a2, 0);
  if ( Aik < 0 )
  {
    *(_DWORD *)v9 = ConvertRetryTypeToKeyStatus((unsigned int)a7);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)Aik,
      (int)&hKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    return (unsigned int)Aik;
  }
  LODWORD(a7) = 0;
  v18 = 0;
  v20 = &v18;
  *(_QWORD *)v21 = 0;
  v22 = 1;
  Aik = NgcUtils::ExportNCryptKey(
          hKey,
          L"OpaqueKeyBlob",
          0,
          (unsigned int)v21,
          (unsigned __int8 **)&a7,
          (unsigned int *)&a7);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v20);
  if ( Aik < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)Aik,
      (int)v14);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v18, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    return (unsigned int)Aik;
  }
  LODWORD(v16) = 0;
  v19 = 0;
  v20 = &v19;
  *(_QWORD *)v21 = 0;
  v22 = 1;
  Aik = NgcUtils::GetNCryptBinaryBlob(hKey, L"SmartCardKeyCertificate", (const unsigned __int16 *)v21, &v16, v14);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v20);
  if ( Aik < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)Aik,
      v15);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v19, 0);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v18, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    return (unsigned int)Aik;
  }
  v12 = v18;
  v18 = 0;
  *a3 = v12;
  *a4 = (unsigned int)a7;
  v13 = v19;
  v19 = 0;
  *a5 = v13;
  *a6 = (unsigned int)v16;
  *(_DWORD *)v9 = 7;
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v19, 0);
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v18, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180015e94  push    rbp
0x180015e96  push    rbx
0x180015e97  push    rsi
0x180015e98  push    rdi
0x180015e99  push    r14
0x180015e9b  push    r15
0x180015e9d  lea     rbp, [rsp-17h]
0x180015ea2  sub     rsp, 88h
0x180015ea9  mov     rsi, r9
0x180015eac  mov     r14, r8
0x180015eaf  mov     rdi, [rbp+3Fh+arg_30]
0x180015eb3  mov     dword ptr [rdi], 3
0x180015eb9  xor     r15d, r15d
0x180015ebc  mov     [rbp+3Fh+hKey], r15
0x180015ec0  mov     dword ptr [rbp+3Fh+arg_30], r15d
0x180015ec4  mov     [rbp+3Fh+hKey], r15
0x180015ec8  mov     [rsp+0B0h+var_80], r15
0x180015ecd  lea     rax, [rbp+3Fh+arg_30]
0x180015ed1  mov     [rsp+0B0h+var_88], rax; unsigned int *
0x180015ed6  lea     rax, [rbp+3Fh+hKey]
0x180015eda  mov     [rsp+0B0h+var_90], rax; int
0x180015edf  xor     r9d, r9d
0x180015ee2  mov     r8, rdx
0x180015ee5  mov     rdx, rcx
0x180015ee8  lea     ecx, [r15+1]
0x180015eec  call    ?GetAik@@YAJW4PregenKeyType@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBG_NPEA_KPEAW4DelayRetryAction@@PEAPEAG@Z; GetAik(PregenKeyType,_NGC_IDP_ACCOUNT_INFO *,ushort const *,bool,unsigned __int64 *,DelayRetryAction *,ushort * *)
0x180015ef1  mov     ebx, eax
0x180015ef3  test    eax, eax
0x180015ef5  jns     short loc_180015F2B
0x180015ef7  mov     ecx, dword ptr [rbp+3Fh+arg_30]
0x180015efa  call    ?ConvertRetryTypeToKeyStatus@@YA?AW4_NGC_KEY_STATUS@@W4DelayRetryAction@@@Z; ConvertRetryTypeToKeyStatus(DelayRetryAction)
0x180015eff  mov     [rdi], eax
0x180015f01  mov     rcx, [rbp+47h]; this
0x180015f05  mov     r9d, ebx; char *
0x180015f08  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180015f0f  mov     edx, 152h; void *
0x180015f14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f19  nop
0x180015f1a  lea     rcx, [rbp+3Fh+hKey]
0x180015f1e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180015f23  nop
0x180015f24  mov     eax, ebx
0x180015f26  jmp     loc_180016074
0x180015f2b  mov     dword ptr [rbp+3Fh+arg_30], r15d
0x180015f2f  mov     [rbp+3Fh+var_60], r15
0x180015f33  lea     rax, [rbp+3Fh+var_60]
0x180015f37  mov     [rbp+3Fh+var_50], rax
0x180015f3b  mov     qword ptr [rbp+3Fh+var_48], r15
0x180015f3f  mov     [rbp+3Fh+var_40], 1
0x180015f43  lea     rax, [rbp+3Fh+arg_30]
0x180015f47  mov     [rsp+0B0h+var_90], rax; int
0x180015f4c  lea     r9, [rbp+3Fh+var_48]; unsigned int
0x180015f50  xor     r8d, r8d; dwFlags
0x180015f53  lea     rdx, aOpaquekeyblob; "OpaqueKeyBlob"
0x180015f5a  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180015f5e  call    ?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z; NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)
0x180015f63  mov     ebx, eax
0x180015f65  lea     rcx, [rbp+3Fh+var_50]
0x180015f69  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180015f6e  test    ebx, ebx
0x180015f70  jns     short loc_180015FA3
0x180015f72  mov     rcx, [rbp+47h]; this
0x180015f76  mov     r9d, ebx; char *
0x180015f79  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180015f80  mov     edx, 15Ch; void *
0x180015f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f8a  nop
0x180015f8b  xor     edx, edx
0x180015f8d  lea     rcx, [rbp+3Fh+var_60]
0x180015f91  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180015f96  nop
0x180015f97  lea     rcx, [rbp+3Fh+hKey]
0x180015f9b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180015fa0  nop
0x180015fa1  jmp     short loc_180015F24
0x180015fa3  mov     dword ptr [rbp+3Fh+var_70], r15d
0x180015fa7  mov     [rbp+3Fh+var_58], r15
0x180015fab  lea     rax, [rbp+3Fh+var_58]
0x180015faf  mov     [rbp+3Fh+var_50], rax
0x180015fb3  mov     qword ptr [rbp+3Fh+var_48], r15
0x180015fb7  mov     [rbp+3Fh+var_40], 1
0x180015fbb  lea     r9, [rbp+3Fh+var_70]; unsigned __int8 **
0x180015fbf  lea     r8, [rbp+3Fh+var_48]; unsigned __int16 *
0x180015fc3  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180015fca  mov     rcx, [rbp+3Fh+hKey]; hObject
0x180015fce  call    ?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z; NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)
0x180015fd3  mov     ebx, eax
0x180015fd5  lea     rcx, [rbp+3Fh+var_50]
0x180015fd9  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180015fde  test    ebx, ebx
0x180015fe0  jns     short loc_180016022
0x180015fe2  mov     rcx, [rbp+47h]; this
0x180015fe6  mov     r9d, ebx; char *
0x180015fe9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180015ff0  mov     edx, 164h; void *
0x180015ff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ffa  nop
0x180015ffb  xor     edx, edx
0x180015ffd  lea     rcx, [rbp+3Fh+var_58]
0x180016001  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180016006  nop
0x180016007  xor     edx, edx
0x180016009  lea     rcx, [rbp+3Fh+var_60]
0x18001600d  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180016012  nop
0x180016013  lea     rcx, [rbp+3Fh+hKey]
0x180016017  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001601c  nop
0x18001601d  jmp     loc_180015F24
0x180016022  mov     rax, [rbp+3Fh+var_60]
0x180016026  mov     [rbp+3Fh+var_60], r15
0x18001602a  mov     [r14], rax
0x18001602d  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x180016030  mov     [rsi], eax
0x180016032  mov     rcx, [rbp+3Fh+var_58]
0x180016036  mov     [rbp+3Fh+var_58], r15
0x18001603a  mov     rax, [rbp+3Fh+arg_20]
0x18001603e  mov     [rax], rcx
0x180016041  mov     rcx, [rbp+3Fh+arg_28]
0x180016045  mov     eax, dword ptr [rbp+3Fh+var_70]
0x180016048  mov     [rcx], eax
0x18001604a  mov     dword ptr [rdi], 7
0x180016050  xor     edx, edx
0x180016052  lea     rcx, [rbp+3Fh+var_58]
0x180016056  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001605b  nop
0x18001605c  xor     edx, edx
0x18001605e  lea     rcx, [rbp+3Fh+var_60]
0x180016062  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180016067  nop
0x180016068  lea     rcx, [rbp+3Fh+hKey]
0x18001606c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180016071  nop
0x180016072  xor     eax, eax
0x180016074  add     rsp, 88h
0x18001607b  pop     r15
0x18001607d  pop     r14
0x18001607f  pop     rdi
0x180016080  pop     rsi
0x180016081  pop     rbx
0x180016082  pop     rbp
0x180016083  retn
```
