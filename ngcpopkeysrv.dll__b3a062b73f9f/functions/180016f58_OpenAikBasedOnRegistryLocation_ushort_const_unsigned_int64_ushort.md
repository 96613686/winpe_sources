# OpenAikBasedOnRegistryLocation(ushort const *,unsigned __int64 *,ushort * *)

- ea: `0x180016f58`
- end: `0x18001706a`
- name: `?OpenAikBasedOnRegistryLocation@@YAJPEBGPEA_KPEAPEAG@Z`
- size: `274`
- prototype: `__int64 __fastcall(HKEY lpSubKey, unsigned __int64 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015bf0`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180011e48`
- `0x180014588`
- `0x180016f58`
- `0x180023124`

## string_xrefs

- `0x180016fca`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`
- `0x180017007`: `onecore\ds\security\ngc\ngcpopkey\common\aik.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OpenAikBasedOnRegistryLocation(const WCHAR *lpSubKey, unsigned __int64 *a2, unsigned __int16 **a3)
{
  int RegistryValue; // ebx
  unsigned __int64 *v6; // r8
  int v7; // eax
  unsigned __int16 *v8; // rax
  unsigned __int64 v9; // rax
  int v11; // [rsp+20h] [rbp-48h]
  unsigned __int16 v12[4]; // [rsp+30h] [rbp-38h] BYREF
  NgcUtils *v13; // [rsp+38h] [rbp-30h] BYREF
  NgcUtils **v14; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v15[2]; // [rsp+48h] [rbp-20h] BYREF
  char v16; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  unsigned __int8 *v18; // [rsp+A8h] [rbp+40h] BYREF

  v13 = 0;
  v14 = &v13;
  *(_QWORD *)v15 = 0;
  v16 = 1;
  RegistryValue = NgcUtils::GetRegistryValue(HKEY_LOCAL_MACHINE, lpSubKey, L"Aik", 2u, v15, &v18);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v14);
  if ( RegistryValue >= 0 )
  {
    *(_QWORD *)v12 = 0;
    v7 = NgcUtils::OpenAikNCryptHandle(v13, v12, v6);
    RegistryValue = v7;
    if ( v7 >= 0 )
    {
      if ( a3 )
      {
        v8 = (unsigned __int16 *)v13;
        v13 = 0;
        *a3 = v8;
      }
      v9 = *(_QWORD *)v12;
      *(_QWORD *)v12 = 0;
      *a2 = v9;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(v12);
      RegistryValue = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
        (const char *)(unsigned int)v7,
        v11);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\common\\aik.cpp",
      (const char *)(unsigned int)RegistryValue,
      v11);
  }
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v13, 0);
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x180016f58  push    rbp
0x180016f5a  push    rbx
0x180016f5b  push    rsi
0x180016f5c  push    rdi
0x180016f5d  mov     rbp, rsp
0x180016f60  sub     rsp, 68h
0x180016f64  mov     rdi, r8
0x180016f67  mov     rsi, rdx
0x180016f6a  mov     [rbp+var_30], 0
0x180016f72  lea     rax, [rbp+var_30]
0x180016f76  mov     [rbp+var_28], rax
0x180016f7a  mov     qword ptr [rbp+var_20], 0
0x180016f82  mov     [rbp+var_18], 1
0x180016f86  lea     rax, [rbp+arg_18]
0x180016f8a  mov     [rsp+68h+var_40], rax; unsigned __int8 **
0x180016f8f  lea     rax, [rbp+var_20]
0x180016f93  mov     qword ptr [rsp+68h+var_48], rax; int
0x180016f98  mov     r9d, 2; dwFlags
0x180016f9e  lea     r8, ValueName; "Aik"
0x180016fa5  mov     rdx, rcx; lpSubKey
0x180016fa8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180016faf  call    ?GetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; NgcUtils::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x180016fb4  mov     ebx, eax
0x180016fb6  lea     rcx, [rbp+var_28]
0x180016fba  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180016fbf  test    ebx, ebx
0x180016fc1  jns     short loc_180016FDD
0x180016fc3  mov     rcx, [rbp+20h]; this
0x180016fc7  mov     r9d, ebx; char *
0x180016fca  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180016fd1  mov     edx, 1Bh; void *
0x180016fd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fdb  jmp     short loc_180017054
0x180016fdd  mov     qword ptr [rbp+var_38], 0
0x180016fe5  mov     qword ptr [rbp+var_38], 0
0x180016fed  lea     rdx, [rbp+var_38]; unsigned __int16 *
0x180016ff1  mov     rcx, [rbp+var_30]; this
0x180016ff5  call    ?OpenAikNCryptHandle@NgcUtils@@YAJPEBGPEA_K@Z; NgcUtils::OpenAikNCryptHandle(ushort const *,unsigned __int64 *)
0x180016ffa  mov     ebx, eax
0x180016ffc  test    eax, eax
0x180016ffe  jns     short loc_180017025
0x180017000  mov     rcx, [rbp+20h]; this
0x180017004  mov     r9d, eax; char *
0x180017007  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001700e  mov     edx, 20h ; ' '; void *
0x180017013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017018  nop
0x180017019  lea     rcx, [rbp+var_38]
0x18001701d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180017022  nop
0x180017023  jmp     short loc_180017054
0x180017025  test    rdi, rdi
0x180017028  jz      short loc_180017039
0x18001702a  mov     rax, [rbp+var_30]
0x18001702e  mov     [rbp+var_30], 0
0x180017036  mov     [rdi], rax
0x180017039  mov     rax, qword ptr [rbp+var_38]
0x18001703d  mov     qword ptr [rbp+var_38], 0
0x180017045  mov     [rsi], rax
0x180017048  lea     rcx, [rbp+var_38]
0x18001704c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180017051  nop
0x180017052  xor     ebx, ebx
0x180017054  xor     edx, edx
0x180017056  lea     rcx, [rbp+var_30]
0x18001705a  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001705f  mov     eax, ebx
0x180017061  add     rsp, 68h
0x180017065  pop     rdi
0x180017066  pop     rsi
0x180017067  pop     rbx
0x180017068  pop     rbp
0x180017069  retn
```
