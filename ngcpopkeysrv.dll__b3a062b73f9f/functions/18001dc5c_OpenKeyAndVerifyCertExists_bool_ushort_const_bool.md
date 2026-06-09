# OpenKeyAndVerifyCertExists(bool,ushort const *,bool *)

- ea: `0x18001dc5c`
- end: `0x18001dd0b`
- name: `?OpenKeyAndVerifyCertExists@@YAJ_NPEBGPEA_N@Z`
- size: `175`
- prototype: `int(bool, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aae8`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180011e48`
- `0x1800141e4`
- `0x180014588`
- `0x18001dc5c`

## string_xrefs

- `0x18001dc8c`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\utilities.cpp`

## pseudocode

```c
__int64 __fastcall OpenKeyAndVerifyCertExists(__int64 a1, NgcUtils *a2, bool *a3)
{
  int v4; // eax
  int NCryptBinaryBlob; // ebx
  NCRYPT_HANDLE v6; // rcx
  __int64 *v8; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 v9[4]; // [rsp+28h] [rbp-18h] BYREF
  char v10; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned __int8 *v12; // [rsp+60h] [rbp+20h] BYREF
  __int64 v13; // [rsp+70h] [rbp+30h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+78h] [rbp+38h] BYREF

  *a3 = 0;
  hObject = 0;
  v4 = NgcUtils::OpenAikNCryptHandle(a2, (unsigned __int16 *)&hObject, (unsigned __int64 *)a3);
  NCryptBinaryBlob = v4;
  if ( v4 >= 0 )
  {
    v6 = hObject;
    v8 = &v13;
    *a3 = 1;
    v13 = 0;
    *(_QWORD *)v9 = 0;
    v10 = 1;
    NCryptBinaryBlob = NgcUtils::GetNCryptBinaryBlob(v6, L"SmartCardKeyCertificate", v9, &v12);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v8);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v13, 0);
    if ( NCryptBinaryBlob >= 0 )
    {
      *a3 = 0;
      NCryptBinaryBlob = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\utilities.cpp",
      (const char *)(unsigned int)v4,
      (int)v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  return (unsigned int)NCryptBinaryBlob;
}

```

## disassembly

```asm
0x18001dc5c  push    rbp
0x18001dc5e  push    rbx
0x18001dc5f  push    rdi
0x18001dc60  mov     rbp, rsp
0x18001dc63  sub     rsp, 40h
0x18001dc67  mov     rcx, rdx; this
0x18001dc6a  mov     byte ptr [r8], 0
0x18001dc6e  lea     rdx, [rbp+hObject]; unsigned __int16 *
0x18001dc72  mov     [rbp+hObject], 0
0x18001dc7a  mov     rdi, r8
0x18001dc7d  call    ?OpenAikNCryptHandle@NgcUtils@@YAJPEBGPEA_K@Z; NgcUtils::OpenAikNCryptHandle(ushort const *,unsigned __int64 *)
0x18001dc82  mov     ebx, eax
0x18001dc84  test    eax, eax
0x18001dc86  jns     short loc_18001DCA2
0x18001dc88  mov     rcx, [rbp+18h]; this
0x18001dc8c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001dc93  mov     r9d, eax; char *
0x18001dc96  mov     edx, 3Ch ; '<'; void *
0x18001dc9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dca0  jmp     short loc_18001DCF8
0x18001dca2  mov     rcx, [rbp+hObject]; hObject
0x18001dca6  lea     rax, [rbp+arg_10]
0x18001dcaa  lea     r9, [rbp+arg_0]; unsigned __int8 **
0x18001dcae  mov     [rbp+var_20], rax
0x18001dcb2  lea     r8, [rbp+var_18]; unsigned __int16 *
0x18001dcb6  mov     byte ptr [rdi], 1
0x18001dcb9  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18001dcc0  mov     [rbp+arg_10], 0
0x18001dcc8  mov     qword ptr [rbp+var_18], 0
0x18001dcd0  mov     [rbp+var_10], 1
0x18001dcd4  call    ?GetNCryptBinaryBlob@NgcUtils@@YAJ_KPEBGPEAPEAEPEAK@Z; NgcUtils::GetNCryptBinaryBlob(unsigned __int64,ushort const *,uchar * *,ulong *)
0x18001dcd9  lea     rcx, [rbp+var_20]
0x18001dcdd  mov     ebx, eax
0x18001dcdf  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001dce4  xor     edx, edx
0x18001dce6  lea     rcx, [rbp+arg_10]
0x18001dcea  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001dcef  test    ebx, ebx
0x18001dcf1  js      short loc_18001DCF8
0x18001dcf3  mov     byte ptr [rdi], 0
0x18001dcf6  xor     ebx, ebx
0x18001dcf8  lea     rcx, [rbp+hObject]
0x18001dcfc  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001dd01  mov     eax, ebx
0x18001dd03  add     rsp, 40h
0x18001dd07  pop     rdi
0x18001dd08  pop     rbx
0x18001dd09  pop     rbp
0x18001dd0a  retn
```
