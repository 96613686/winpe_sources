# CloudExperienceHostBroker::Cortana::OOBECortanaManagerCore::get_HasMicrophone(uchar *)

- ea: `0x180067760`
- end: `0x180067855`
- name: `?get_HasMicrophone@OOBECortanaManagerCore@Cortana@CloudExperienceHostBroker@@UEAAJPEAE@Z`
- size: `245`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::Cortana::OOBECortanaManagerCore *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000683c`
- `0x1800076d4`
- `0x18000b098`
- `0x180067760`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800677a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800677a5`

## string_xrefs

- `0x1800677b9`: `shellcommon\shell\oobe\core\components\winrt\oobecortanamanagercore.cpp`
- `0x180067817`: `shellcommon\shell\oobe\core\components\winrt\oobecortanamanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::Cortana::OOBECortanaManagerCore::get_HasMicrophone(
        CloudExperienceHostBroker::Cortana::OOBECortanaManagerCore *this,
        unsigned __int8 *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, __int64, __int64, __int64 *); // rbx
  int v7; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v12; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v3 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         1u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &v12);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v11 = 0;
    v5 = v12;
    v6 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64 *))(*(_QWORD *)v12 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    v7 = v6(v5, 1, 1, &v11);
    if ( v11 )
    {
      if ( v7 >= 0 )
        *a2 = 1;
      else
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x10A,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobecortanamanagercore.cpp",
          (const char *)(unsigned int)v7,
          ppv);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobecortanamanagercore.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return v4;
}

```

## disassembly

```asm
0x180067760  mov     rax, rsp
0x180067763  mov     [rax+8], rbx
0x180067767  mov     [rax+20h], rsi
0x18006776b  push    rdi
0x18006776c  sub     rsp, 30h
0x180067770  mov     rsi, rdx
0x180067773  mov     byte ptr [rdx], 0
0x180067776  mov     qword ptr [rax+18h], 0
0x18006777e  lea     rcx, [rax+18h]
0x180067782  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067787  lea     rax, [rsp+38h+arg_10]
0x18006778c  mov     qword ptr [rsp+38h+ppv], rax; int
0x180067791  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180067798  xor     edx, edx; pUnkOuter
0x18006779a  lea     r8d, [rdx+1]; dwClsContext
0x18006779e  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800677a5  call    cs:__imp_CoCreateInstance
0x1800677ab  mov     ebx, eax
0x1800677ad  test    eax, eax
0x1800677af  jns     short loc_1800677CC
0x1800677b1  mov     rcx, [rsp+38h]; this
0x1800677b6  mov     r9d, eax; char *
0x1800677b9  lea     r8, aShellcommonShe_25; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800677c0  mov     edx, 105h; void *
0x1800677c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800677ca  jmp     short loc_180067839
0x1800677cc  mov     [rsp+38h+arg_8], 0
0x1800677d5  mov     rdi, [rsp+38h+arg_10]
0x1800677da  mov     rax, [rdi]
0x1800677dd  mov     rbx, [rax+20h]
0x1800677e1  lea     rcx, [rsp+38h+arg_8]
0x1800677e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800677eb  lea     r9, [rsp+38h+arg_8]
0x1800677f0  mov     edx, 1
0x1800677f5  mov     r8d, edx
0x1800677f8  mov     rcx, rdi
0x1800677fb  mov     rax, rbx
0x1800677fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067803  cmp     [rsp+38h+arg_8], 0
0x180067809  jz      short loc_18006782D
0x18006780b  mov     rcx, [rsp+38h]; this
0x180067810  test    eax, eax
0x180067812  jns     short loc_18006782A
0x180067814  mov     r9d, eax; char *
0x180067817  lea     r8, aShellcommonShe_25; "shellcommon\\shell\\oobe\\core\\compone"...
0x18006781e  mov     edx, 10Ah; void *
0x180067823  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180067828  jmp     short loc_18006782D
0x18006782a  mov     byte ptr [rsi], 1
0x18006782d  lea     rcx, [rsp+38h+arg_8]
0x180067832  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067837  xor     ebx, ebx
0x180067839  lea     rcx, [rsp+38h+arg_10]
0x18006783e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067843  mov     eax, ebx
0x180067845  mov     rbx, [rsp+38h+arg_0]
0x18006784a  mov     rsi, [rsp+38h+arg_18]
0x18006784f  add     rsp, 30h
0x180067853  pop     rdi
0x180067854  retn
```
