# _lambda_91965be931cb0cafdf04baf499281b5e_::operator()

- ea: `0x180010de8`
- end: `0x180010e9e`
- name: `_lambda_91965be931cb0cafdf04baf499281b5e_::operator()`
- size: `182`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014148`

## callees

- `0x18000cc34`
- `0x180010310`
- `0x180010de8`
- `0x180014bcc`
- `0x18001c9ac`
- `0x18001ce64`

## string_xrefs

- `0x180010e28`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180010e71`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
__int64 __fastcall lambda_91965be931cb0cafdf04baf499281b5e_::operator()(__int64 a1)
{
  const unsigned __int16 *v2; // rdx
  NgcUtils *v3; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  const unsigned __int16 *v5; // r8
  unsigned int v6; // ebx
  int v7; // eax
  unsigned __int16 *v9; // [rsp+20h] [rbp-38h]
  int v10; // [rsp+20h] [rbp-38h]
  unsigned __int8 *v11; // [rsp+30h] [rbp-28h]
  unsigned int v12; // [rsp+38h] [rbp-20h]
  HKEY v13[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v13[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    v13,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v3,
                                        v2,
                                        **(const unsigned __int16 ***)a1,
                                        (unsigned __int16 *)v13);
  v6 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    LODWORD(v11) = 4;
    LODWORD(v9) = 4;
    v7 = NgcUtils::SetRegistryValue(
           (NgcUtils *)4,
           v13[0],
           v5,
           (struct _SECURITY_ATTRIBUTES *)L"ErrorCode",
           v9,
           *(_QWORD *)(a1 + 8),
           v11,
           v12);
    v6 = v7;
    if ( v7 >= 0 )
      v6 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x279,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v7,
        v10);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      (int)v9);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v13);
  return v6;
}

```

## disassembly

```asm
0x180010de8  mov     [rsp+arg_0], rbx
0x180010ded  push    rdi
0x180010dee  sub     rsp, 50h
0x180010df2  mov     rdi, rcx
0x180010df5  mov     [rsp+58h+var_18], 0
0x180010dfe  xor     edx, edx
0x180010e00  lea     rcx, [rsp+58h+var_18]
0x180010e05  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180010e0a  mov     r8, [rdi]
0x180010e0d  lea     r9, [rsp+58h+var_18]; unsigned __int16 *
0x180010e12  mov     r8, [r8]; unsigned __int16 *
0x180010e15  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180010e1a  mov     ebx, eax
0x180010e1c  test    eax, eax
0x180010e1e  jns     short loc_180010E3C
0x180010e20  mov     rcx, [rsp+58h]; this
0x180010e25  mov     r9d, eax; char *
0x180010e28  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180010e2f  mov     edx, 270h; void *
0x180010e34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e39  nop
0x180010e3a  jmp     short loc_180010E87
0x180010e3c  mov     ecx, 4; this
0x180010e41  mov     dword ptr [rsp+58h+var_28], ecx; unsigned __int8 *
0x180010e45  mov     rax, [rdi+8]
0x180010e49  mov     qword ptr [rsp+58h+var_30], rax; unsigned int
0x180010e4e  mov     dword ptr [rsp+58h+var_38], ecx; int
0x180010e52  lea     r9, aErrorcode; "ErrorCode"
0x180010e59  mov     rdx, [rsp+58h+var_18]; HKEY
0x180010e5e  call    ?SetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBGPEAU_SECURITY_ATTRIBUTES@@1KPEAEK@Z; NgcUtils::SetRegistryValue(HKEY__ *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong,uchar *,ulong)
0x180010e63  mov     ebx, eax
0x180010e65  test    eax, eax
0x180010e67  jns     short loc_180010E85
0x180010e69  mov     rcx, [rsp+58h]; this
0x180010e6e  mov     r9d, eax; char *
0x180010e71  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180010e78  mov     edx, 279h; void *
0x180010e7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010e82  nop
0x180010e83  jmp     short loc_180010E87
0x180010e85  xor     ebx, ebx
0x180010e87  lea     rcx, [rsp+58h+var_18]
0x180010e8c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010e91  mov     eax, ebx
0x180010e93  mov     rbx, [rsp+58h+arg_0]
0x180010e98  add     rsp, 50h
0x180010e9c  pop     rdi
0x180010e9d  retn
```
