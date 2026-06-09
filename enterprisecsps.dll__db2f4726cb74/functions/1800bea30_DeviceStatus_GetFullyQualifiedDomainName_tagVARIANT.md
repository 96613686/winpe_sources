# DeviceStatus::GetFullyQualifiedDomainName(tagVARIANT *)

- ea: `0x1800bea30`
- end: `0x1800beb3c`
- name: `?GetFullyQualifiedDomainName@DeviceStatus@@SAJPEAUtagVARIANT@@@Z`
- size: `268`
- prototype: `static int(struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180092bb0`

## callees

- `0x18000d4b4`
- `0x18000d4d4`
- `0x180025a9c`
- `0x1800bea30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bea5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bea5b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800bea82`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800bea82`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800bea4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800beac6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800bea4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800beac6`

## pseudocode

```c
__int64 __fastcall DeviceStatus::GetFullyQualifiedDomainName(struct tagVARIANT *a1)
{
  const char *v2; // r9
  WCHAR *v3; // rax
  LONGLONG v4; // rbx
  unsigned int LastError; // ebx
  const char *v6; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD nSize; // [rsp+38h] [rbp+10h] BYREF
  WCHAR *v11; // [rsp+40h] [rbp+18h] BYREF

  nSize = 0;
  GetComputerNameExW(ComputerNamePhysicalDnsDomain, 0, &nSize);
  if ( GetLastError() != 234 || !nSize )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5B,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\devicestatus.cpp",
             v2);
  v3 = SysAllocStringLen(0, nSize - 1);
  v11 = v3;
  v4 = (LONGLONG)v3;
  if ( !v3 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\devicestatus.cpp",
      (const char *)0x8007000ELL,
      v8);
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
    return LastError;
  }
  if ( !GetComputerNameExW(ComputerNamePhysicalDnsDomain, v3, &nSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x54,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\devicestatus\\devicestatus.cpp",
                  v6);
    goto LABEL_7;
  }
  a1->vt = 8;
  v11 = 0;
  a1->llVal = v4;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  return 0;
}

```

## disassembly

```asm
0x1800bea30  mov     [rsp+arg_0], rbx
0x1800bea35  push    rdi; int
0x1800bea36  sub     rsp, 20h
0x1800bea3a  xor     edx, edx; lpBuffer
0x1800bea3c  mov     [rsp+28h+nSize], 0
0x1800bea44  mov     rdi, rcx
0x1800bea47  lea     r8, [rsp+28h+nSize]; nSize
0x1800bea4c  lea     ecx, [rdx+6]; NameType
0x1800bea4f  call    cs:__imp_GetComputerNameExW
0x1800bea56  nop     dword ptr [rax+rax+00h]
0x1800bea5b  call    cs:__imp_GetLastError
0x1800bea62  nop     dword ptr [rax+rax+00h]
0x1800bea67  cmp     eax, 0EAh
0x1800bea6c  jnz     loc_1800BEB1A
0x1800bea72  mov     edx, [rsp+28h+nSize]
0x1800bea76  test    edx, edx
0x1800bea78  jz      loc_1800BEB1A
0x1800bea7e  dec     edx; ui
0x1800bea80  xor     ecx, ecx; strIn
0x1800bea82  call    cs:__imp_SysAllocStringLen
0x1800bea89  nop     dword ptr [rax+rax+00h]
0x1800bea8e  mov     [rsp+28h+arg_10], rax
0x1800bea93  mov     rbx, rax
0x1800bea96  test    rax, rax
0x1800bea99  jnz     short loc_1800BEAB9
0x1800bea9b  mov     rcx, [rsp+28h]; this
0x1800beaa0  lea     r8, aOnecoreuapAdmi_54; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800beaa7  mov     ebx, 8007000Eh
0x1800beaac  lea     edx, [rax+50h]; void *
0x1800beaaf  mov     r9d, ebx; char *
0x1800beab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800beab7  jmp     short loc_1800BEAEC
0x1800beab9  lea     r8, [rsp+28h+nSize]; nSize
0x1800beabe  mov     rdx, rbx; lpBuffer
0x1800beac1  mov     ecx, 6; NameType
0x1800beac6  call    cs:__imp_GetComputerNameExW
0x1800beacd  nop     dword ptr [rax+rax+00h]
0x1800bead2  test    eax, eax
0x1800bead4  jnz     short loc_1800BEAFA
0x1800bead6  mov     rcx, [rsp+28h]; this
0x1800beadb  lea     r8, aOnecoreuapAdmi_54; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800beae2  lea     edx, [rax+54h]; void *
0x1800beae5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800beaea  mov     ebx, eax
0x1800beaec  lea     rcx, [rsp+28h+arg_10]
0x1800beaf1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800beaf6  mov     eax, ebx
0x1800beaf8  jmp     short loc_1800BEB30
0x1800beafa  lea     rcx, [rsp+28h+arg_10]
0x1800beaff  mov     word ptr [rdi], 8
0x1800beb04  mov     [rsp+28h+arg_10], 0
0x1800beb0d  mov     [rdi+8], rbx
0x1800beb11  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800beb16  xor     eax, eax
0x1800beb18  jmp     short loc_1800BEB30
0x1800beb1a  mov     rcx, [rsp+28h]; this
0x1800beb1f  lea     r8, aOnecoreuapAdmi_54; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800beb26  mov     edx, 5Bh ; '['; void *
0x1800beb2b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800beb30  mov     rbx, [rsp+28h+arg_0]
0x1800beb35  add     rsp, 20h
0x1800beb39  pop     rdi
0x1800beb3a  retn
```
