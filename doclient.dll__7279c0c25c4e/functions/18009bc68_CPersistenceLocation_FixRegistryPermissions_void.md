# CPersistenceLocation::FixRegistryPermissions(void)

- ea: `0x18009bc68`
- end: `0x18009bf2f`
- name: `?FixRegistryPermissions@CPersistenceLocation@@SAJXZ`
- size: `711`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006530`

## callees

- `0x1800089f8`
- `0x180008fb8`
- `0x18000933c`
- `0x18009bc68`
- `0x18009c368`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009bcaa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009bcaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009bd3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009bd3b`
- `OLEAUT32!__imp_SysAllocString` at `0x18009bd66`
- `OLEAUT32!__imp_SysAllocString` at `0x18009bd66`
- `OLEAUT32!__imp_VariantInit` at `0x18009bd4e`
- `OLEAUT32!__imp_VariantInit` at `0x18009bd4e`
- `OLEAUT32!__imp_VariantClear` at `0x18009bd9b`
- `OLEAUT32!__imp_VariantClear` at `0x18009be45`
- `OLEAUT32!__imp_VariantClear` at `0x18009becb`
- `OLEAUT32!__imp_VariantClear` at `0x18009bd9b`
- `OLEAUT32!__imp_VariantClear` at `0x18009be45`
- `OLEAUT32!__imp_VariantClear` at `0x18009becb`

## string_xrefs

- `0x18009bcbe`: `Failed to CoCreate WaaSProtectedSettingsProvider`
- `0x18009bea5`: `UnprotectRegistryKey failed`
- `0x18009be1f`: `ProtectRegistryKey failed`

## pseudocode

```c
__int64 CPersistenceLocation::FixRegistryPermissions(void)
{
  HRESULT v0; // ebx
  LPVOID v1; // rcx
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  LPVOID v6; // rcx
  int v7; // ebx
  LPVOID v8; // rcx
  unsigned int v9; // eax
  LPVOID v10; // rcx
  int ppv; // [rsp+20h] [rbp-88h]
  const char *v12; // [rsp+28h] [rbp-80h]
  VARIANTARG v13; // [rsp+30h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-58h] BYREF
  LPVOID v15; // [rsp+68h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-38h] BYREF
  HSTRING string; // [rsp+88h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v15 = 0;
  v0 = CoCreateInstance(
         &GUID_9ea82395_e31b_41ca_8df7_ec1cee7194df,
         0,
         4u,
         &GUID_e4dc719b_fe77_414f_9dbe_3e4ffea7a7a5,
         &v15);
  if ( v0 >= 0 )
  {
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    string = 0;
    v3 = WindowsCreateStringReference(
           L"S-1-5-20\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeliveryOptimization",
           0x47u,
           &hstringHeader,
           &string);
    if ( v3 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
      JUMPOUT(0x18009BF2DLL);
    }
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(
                              L"D:(A;CI;GA;;;SY)(A;CI;GRGWSD;;;BA)(A;CI;GRGWSD;;;NS)(A;CI;GR;;;AU)(A;CI;GA;;;S-1-5-80-3055"
                               "155277-3816794035-3994065555-2874236192-2193176987)");
    if ( pvarg.llVal )
    {
      v13 = pvarg;
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, HSTRING, VARIANTARG *))(*(_QWORD *)v15 + 40LL))(
             v15,
             3,
             string,
             &v13);
      if ( v7 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, HSTRING))(*(_QWORD *)v15 + 48LL))(v15, 3, string);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0x123,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
          (const char *)v9,
          (int)"UnprotectRegistryKey failed",
          v12);
        VariantClear(&pvarg);
        string = 0;
        v10 = v15;
        if ( v15 )
        {
          v15 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
        }
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x11B,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
          (const char *)(unsigned int)v7,
          (int)"ProtectRegistryKey failed",
          v12);
        VariantClear(&pvarg);
        string = 0;
        v8 = v15;
        if ( v15 )
        {
          v15 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
        }
        return (unsigned int)v7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x117,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
        (const char *)0x8007000ELL,
        ppv);
      VariantClear(&pvarg);
      string = 0;
      v6 = v15;
      if ( v15 )
      {
        v15 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
      }
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x111,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\StatePersistence\\win10\\PersistenceLocation.cpp",
      (const char *)(unsigned int)v0,
      (int)"Failed to CoCreate WaaSProtectedSettingsProvider",
      v12);
    v1 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v1 + 16LL))(v1);
    }
    return (unsigned int)v0;
  }
}

```

## disassembly

```asm
0x18009bc68  push    rbx
0x18009bc6a  sub     rsp, 0A0h
0x18009bc71  mov     rax, cs:__security_cookie
0x18009bc78  xor     rax, rsp
0x18009bc7b  mov     [rsp+0A8h+var_18], rax
0x18009bc83  mov     [rsp+0A8h+var_40], 0
0x18009bc8c  lea     rax, [rsp+0A8h+var_40]
0x18009bc91  mov     [rsp+0A8h+ppv], rax; int
0x18009bc96  lea     r9, _GUID_e4dc719b_fe77_414f_9dbe_3e4ffea7a7a5; riid
0x18009bc9d  xor     edx, edx; pUnkOuter
0x18009bc9f  lea     r8d, [rdx+4]; dwClsContext
0x18009bca3  lea     rcx, _GUID_9ea82395_e31b_41ca_8df7_ec1cee7194df; rclsid
0x18009bcaa  call    cs:__imp_CoCreateInstance
0x18009bcb0  mov     ebx, eax
0x18009bcb2  test    eax, eax
0x18009bcb4  jns     short loc_18009BD06
0x18009bcb6  mov     rcx, [rsp+0A8h]; this
0x18009bcbe  lea     rax, aFailedToCocrea_1; "Failed to CoCreate WaaSProtectedSetting"...
0x18009bcc5  mov     [rsp+0A8h+ppv], rax; int
0x18009bcca  mov     r9d, ebx; char *
0x18009bccd  lea     r8, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009bcd4  mov     edx, 111h; void *
0x18009bcd9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009bcde  nop
0x18009bcdf  mov     rcx, [rsp+0A8h+var_40]
0x18009bce4  test    rcx, rcx
0x18009bce7  jz      short loc_18009BCFF
0x18009bce9  mov     [rsp+0A8h+var_40], 0
0x18009bcf2  mov     rax, [rcx]
0x18009bcf5  mov     rax, [rax+10h]
0x18009bcf9  call    _guard_dispatch_icall
0x18009bcfe  nop
0x18009bcff  mov     eax, ebx
0x18009bd01  jmp     loc_18009BF0D
0x18009bd06  xorps   xmm0, xmm0
0x18009bd09  movups  xmmword ptr [rsp+0A8h+hstringHeader.Reserved], xmm0
0x18009bd0e  movups  xmmword ptr [rsp+0A8h+hstringHeader.Reserved+10h], xmm0
0x18009bd16  mov     [rsp+0A8h+string], 0
0x18009bd22  lea     r9, [rsp+0A8h+string]; string
0x18009bd2a  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x18009bd2f  mov     edx, 47h ; 'G'; length
0x18009bd34  lea     rcx, sourceString; "S-1-5-20\\SOFTWARE\\Microsoft\\Windows"...
0x18009bd3b  call    cs:__imp_WindowsCreateStringReference
0x18009bd41  test    eax, eax
0x18009bd43  js      loc_18009BF26
0x18009bd49  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18009bd4e  call    cs:__imp_VariantInit
0x18009bd54  nop
0x18009bd55  mov     eax, 8
0x18009bd5a  mov     word ptr [rsp+0A8h+pvarg], ax
0x18009bd5f  lea     rcx, aDACiGaSyACiGrg; "D:(A;CI;GA;;;SY)(A;CI;GRGWSD;;;BA)(A;CI"...
0x18009bd66  call    cs:__imp_SysAllocString
0x18009bd6c  mov     qword ptr [rsp+0A8h+pvarg+8], rax
0x18009bd71  test    rax, rax
0x18009bd74  jnz     short loc_18009BDD8
0x18009bd76  mov     rcx, [rsp+0A8h]; this
0x18009bd7e  mov     r9d, 8007000Eh; char *
0x18009bd84  lea     r8, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009bd8b  mov     edx, 117h; void *
0x18009bd90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009bd95  nop
0x18009bd96  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18009bd9b  call    cs:__imp_VariantClear
0x18009bda1  nop
0x18009bda2  mov     [rsp+0A8h+string], 0
0x18009bdae  mov     rcx, [rsp+0A8h+var_40]
0x18009bdb3  test    rcx, rcx
0x18009bdb6  jz      short loc_18009BDCE
0x18009bdb8  mov     [rsp+0A8h+var_40], 0
0x18009bdc1  mov     rdx, [rcx]
0x18009bdc4  mov     rax, [rdx+10h]
0x18009bdc8  call    _guard_dispatch_icall
0x18009bdcd  nop
0x18009bdce  mov     eax, 8007000Eh
0x18009bdd3  jmp     loc_18009BF0D
0x18009bdd8  movups  xmm0, xmmword ptr [rsp+0A8h+pvarg]
0x18009bddd  movaps  [rsp+0A8h+var_78], xmm0
0x18009bde2  movsd   xmm1, qword ptr [rsp+0A8h+pvarg+10h]
0x18009bde8  movsd   [rsp+0A8h+var_68], xmm1
0x18009bdee  mov     rcx, [rsp+0A8h+var_40]
0x18009bdf3  mov     rax, [rcx]
0x18009bdf6  lea     r9, [rsp+0A8h+var_78]
0x18009bdfb  mov     r8, [rsp+0A8h+string]
0x18009be03  mov     edx, 3
0x18009be08  mov     rax, [rax+28h]
0x18009be0c  call    _guard_dispatch_icall
0x18009be11  mov     ebx, eax
0x18009be13  test    eax, eax
0x18009be15  jns     short loc_18009BE7F
0x18009be17  mov     rcx, [rsp+0A8h]; this
0x18009be1f  lea     rax, aProtectregistr; "ProtectRegistryKey failed"
0x18009be26  mov     [rsp+0A8h+ppv], rax; int
0x18009be2b  mov     r9d, ebx; char *
0x18009be2e  lea     r8, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009be35  mov     edx, 11Bh; void *
0x18009be3a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009be3f  nop
0x18009be40  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18009be45  call    cs:__imp_VariantClear
0x18009be4b  nop
0x18009be4c  mov     [rsp+0A8h+string], 0
0x18009be58  mov     rcx, [rsp+0A8h+var_40]
0x18009be5d  test    rcx, rcx
0x18009be60  jz      short loc_18009BE78
0x18009be62  mov     [rsp+0A8h+var_40], 0
0x18009be6b  mov     rax, [rcx]
0x18009be6e  mov     rax, [rax+10h]
0x18009be72  call    _guard_dispatch_icall
0x18009be77  nop
0x18009be78  mov     eax, ebx
0x18009be7a  jmp     loc_18009BF0D
0x18009be7f  mov     rcx, [rsp+0A8h+var_40]
0x18009be84  mov     rax, [rcx]
0x18009be87  mov     r8, [rsp+0A8h+string]
0x18009be8f  mov     edx, 3
0x18009be94  mov     rax, [rax+30h]
0x18009be98  call    _guard_dispatch_icall
0x18009be9d  mov     rcx, [rsp+0A8h]; this
0x18009bea5  lea     rdx, aUnprotectregis; "UnprotectRegistryKey failed"
0x18009beac  mov     [rsp+0A8h+ppv], rdx; int
0x18009beb1  mov     r9d, eax; char *
0x18009beb4  lea     r8, aCW1SSrcDeliver_110; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18009bebb  mov     edx, 123h; void *
0x18009bec0  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18009bec5  nop
0x18009bec6  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18009becb  call    cs:__imp_VariantClear
0x18009bed1  nop
0x18009bed2  mov     [rsp+0A8h+string], 0
0x18009bede  mov     rcx, [rsp+0A8h+var_40]
0x18009bee3  test    rcx, rcx
0x18009bee6  jz      short loc_18009BEFE
0x18009bee8  mov     [rsp+0A8h+var_40], 0
0x18009bef1  mov     rax, [rcx]
0x18009bef4  mov     rax, [rax+10h]
0x18009bef8  call    _guard_dispatch_icall
0x18009befd  nop
0x18009befe  xor     eax, eax
0x18009bf00  jmp     short loc_18009BF0D
0x18009bf02  mov     eax, 8007000Eh
0x18009bf07  jmp     short loc_18009BF0D
0x18009bf09  mov     eax, dword ptr [rsp+0A8h+var_40]
0x18009bf0d  mov     rcx, [rsp+0A8h+var_18]
0x18009bf15  xor     rcx, rsp; StackCookie
0x18009bf18  call    __security_check_cookie
0x18009bf1d  add     rsp, 0A0h
0x18009bf24  pop     rbx
0x18009bf25  retn
0x18009bf26  mov     ecx, eax; this
0x18009bf28  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
