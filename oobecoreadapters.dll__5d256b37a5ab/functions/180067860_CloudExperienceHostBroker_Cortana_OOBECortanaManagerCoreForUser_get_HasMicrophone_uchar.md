# CloudExperienceHostBroker::Cortana::OOBECortanaManagerCoreForUser::get_HasMicrophone(uchar *)

- ea: `0x180067860`
- end: `0x180067955`
- name: `?get_HasMicrophone@OOBECortanaManagerCoreForUser@Cortana@CloudExperienceHostBroker@@UEAAJPEAE@Z`
- size: `245`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::Cortana::OOBECortanaManagerCoreForUser *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000683c`
- `0x1800076d4`
- `0x18000b098`
- `0x180067860`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800678a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800678a5`

## string_xrefs

- `0x1800678b9`: `shellcommon\shell\oobe\core\components\winrt\oobecortanamanagercore.cpp`
- `0x180067917`: `shellcommon\shell\oobe\core\components\winrt\oobecortanamanagercore.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::Cortana::OOBECortanaManagerCoreForUser::get_HasMicrophone(
        CloudExperienceHostBroker::Cortana::OOBECortanaManagerCoreForUser *this,
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
          (void *)0x68,
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
      (void *)0x63,
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
0x180067860  mov     rax, rsp
0x180067863  mov     [rax+8], rbx
0x180067867  mov     [rax+20h], rsi
0x18006786b  push    rdi
0x18006786c  sub     rsp, 30h
0x180067870  mov     rsi, rdx
0x180067873  mov     byte ptr [rdx], 0
0x180067876  mov     qword ptr [rax+18h], 0
0x18006787e  lea     rcx, [rax+18h]
0x180067882  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067887  lea     rax, [rsp+38h+arg_10]
0x18006788c  mov     qword ptr [rsp+38h+ppv], rax; int
0x180067891  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x180067898  xor     edx, edx; pUnkOuter
0x18006789a  lea     r8d, [rdx+1]; dwClsContext
0x18006789e  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800678a5  call    cs:__imp_CoCreateInstance
0x1800678ab  mov     ebx, eax
0x1800678ad  test    eax, eax
0x1800678af  jns     short loc_1800678CC
0x1800678b1  mov     rcx, [rsp+38h]; this
0x1800678b6  mov     r9d, eax; char *
0x1800678b9  lea     r8, aShellcommonShe_25; "shellcommon\\shell\\oobe\\core\\compone"...
0x1800678c0  mov     edx, 63h ; 'c'; void *
0x1800678c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800678ca  jmp     short loc_180067939
0x1800678cc  mov     [rsp+38h+arg_8], 0
0x1800678d5  mov     rdi, [rsp+38h+arg_10]
0x1800678da  mov     rax, [rdi]
0x1800678dd  mov     rbx, [rax+20h]
0x1800678e1  lea     rcx, [rsp+38h+arg_8]
0x1800678e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800678eb  lea     r9, [rsp+38h+arg_8]
0x1800678f0  mov     edx, 1
0x1800678f5  mov     r8d, edx
0x1800678f8  mov     rcx, rdi
0x1800678fb  mov     rax, rbx
0x1800678fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067903  cmp     [rsp+38h+arg_8], 0
0x180067909  jz      short loc_18006792D
0x18006790b  mov     rcx, [rsp+38h]; this
0x180067910  test    eax, eax
0x180067912  jns     short loc_18006792A
0x180067914  mov     r9d, eax; char *
0x180067917  lea     r8, aShellcommonShe_25; "shellcommon\\shell\\oobe\\core\\compone"...
0x18006791e  mov     edx, 68h ; 'h'; void *
0x180067923  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180067928  jmp     short loc_18006792D
0x18006792a  mov     byte ptr [rsi], 1
0x18006792d  lea     rcx, [rsp+38h+arg_8]
0x180067932  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067937  xor     ebx, ebx
0x180067939  lea     rcx, [rsp+38h+arg_10]
0x18006793e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067943  mov     eax, ebx
0x180067945  mov     rbx, [rsp+38h+arg_0]
0x18006794a  mov     rsi, [rsp+38h+arg_18]
0x18006794f  add     rsp, 30h
0x180067953  pop     rdi
0x180067954  retn
```
