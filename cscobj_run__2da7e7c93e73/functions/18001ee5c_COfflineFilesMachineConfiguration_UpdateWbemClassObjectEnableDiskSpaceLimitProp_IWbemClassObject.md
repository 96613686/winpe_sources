# COfflineFilesMachineConfiguration::UpdateWbemClassObjectEnableDiskSpaceLimitProp(IWbemClassObject *)

- ea: `0x18001ee5c`
- end: `0x18001ef68`
- name: `?UpdateWbemClassObjectEnableDiskSpaceLimitProp@COfflineFilesMachineConfiguration@@CAJPEAUIWbemClassObject@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x18001957c`
- `0x18001da18`
- `0x18001ee5c`
- `0x18001f1c4`
- `0x180028508`
- `0x1800296a0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001eeb4`
- `OLEAUT32!__imp_VariantInit` at `0x18001eee1`
- `OLEAUT32!__imp_VariantInit` at `0x18001eeb4`
- `OLEAUT32!__imp_VariantInit` at `0x18001eee1`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef12`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef44`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef4e`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef12`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef44`
- `OLEAUT32!__imp_VariantClear` at `0x18001ef4e`

## string_xrefs

- `0x18001eef4`: `AutoCacheSizeInMB`

## pseudocode

```c
__int64 __fastcall COfflineFilesMachineConfiguration::UpdateWbemClassObjectEnableDiskSpaceLimitProp(
        struct IWbemClassObject *a1)
{
  unsigned int v2; // ebx
  VARIANTARG v4; // [rsp+20h] [rbp-50h] BYREF
  VARIANTARG v5; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF

  if ( (unsigned int)GetSettingAuthority(3) == 1 )
  {
    return (unsigned int)CSCWmiConfig::UpdateWbemClassObjectProp(L"DiskSpaceLimitEnabled", 0, a1, 2);
  }
  else
  {
    v4.vt = 11;
    v4.iVal = -1;
    VariantInit(&pvarg);
    if ( (int)CSCWmiConfig::GetUserStateSettingForWbemClassObject(L"TotalSizeInMB", &pvarg, 0, 18) < 0 || pvarg.vt == 1 )
    {
      VariantInit(&v5);
      if ( (int)CSCWmiConfig::GetUserStateSettingForWbemClassObject(L"AutoCacheSizeInMB", &v5, 0, 18) < 0 || v5.vt == 1 )
        v4.vt = 1;
      VariantClear(&v5);
    }
    v5.vt = 0;
    ATL::CComVariant::InternalCopy(&v5, &v4);
    v2 = WmiProp_SetProperty(a1, L"DiskSpaceLimitEnabled", &v5);
    VariantClear(&pvarg);
    VariantClear(&v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18001ee5c  mov     [rsp-8+arg_0], rbx
0x18001ee61  mov     [rsp-8+arg_8], rdi
0x18001ee66  push    rbp
0x18001ee67  mov     rbp, rsp
0x18001ee6a  sub     rsp, 70h
0x18001ee6e  mov     rbx, rcx
0x18001ee71  mov     ecx, 3
0x18001ee76  call    ?GetSettingAuthority@@YA?AW4SETTING_AUTH@@W4UST_COMPONENT_ID@@@Z; GetSettingAuthority(UST_COMPONENT_ID)
0x18001ee7b  mov     edi, 1
0x18001ee80  cmp     eax, edi
0x18001ee82  jnz     short loc_18001EEA0
0x18001ee84  lea     r9d, [rdi+1]
0x18001ee88  mov     r8, rbx
0x18001ee8b  xor     edx, edx
0x18001ee8d  lea     rcx, CSCWMI_STR_PROP_DISKSPACELIMITENABLED; "DiskSpaceLimitEnabled"
0x18001ee94  call    ?UpdateWbemClassObjectProp@CSCWmiConfig@@YAJPEBGPEAXPEAUIWbemClassObject@@W4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::UpdateWbemClassObjectProp(ushort const *,void *,IWbemClassObject *,USERSTATE_SETTING_SOURCES)
0x18001ee99  mov     ebx, eax
0x18001ee9b  jmp     loc_18001EF54
0x18001eea0  mov     eax, 0Bh
0x18001eea5  lea     rcx, [rbp+pvarg]; pvarg
0x18001eea9  mov     word ptr [rbp+var_50], ax
0x18001eead  or      eax, 0FFFFFFFFh
0x18001eeb0  mov     word ptr [rbp+var_50+8], ax
0x18001eeb4  call    cs:__imp_VariantInit
0x18001eeba  mov     r9d, 12h
0x18001eec0  lea     rdx, [rbp+pvarg]
0x18001eec4  xor     r8d, r8d
0x18001eec7  lea     rcx, CSCWMI_STR_PROP_TOTALSIZE; "TotalSizeInMB"
0x18001eece  call    ?GetUserStateSettingForWbemClassObject@CSCWmiConfig@@YAJPEBGAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::GetUserStateSettingForWbemClassObject(ushort const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES)
0x18001eed3  test    eax, eax
0x18001eed5  js      short loc_18001EEDD
0x18001eed7  cmp     word ptr [rbp+pvarg], di
0x18001eedb  jnz     short loc_18001EF18
0x18001eedd  lea     rcx, [rbp+var_38]; pvarg
0x18001eee1  call    cs:__imp_VariantInit
0x18001eee7  mov     r9d, 12h
0x18001eeed  lea     rdx, [rbp+var_38]
0x18001eef1  xor     r8d, r8d
0x18001eef4  lea     rcx, CSCWMI_STR_PROP_AUTOCACHESIZE; "AutoCacheSizeInMB"
0x18001eefb  call    ?GetUserStateSettingForWbemClassObject@CSCWmiConfig@@YAJPEBGAEAVCComVariant@ATL@@PEAXW4USERSTATE_SETTING_SOURCES@@@Z; CSCWmiConfig::GetUserStateSettingForWbemClassObject(ushort const *,ATL::CComVariant &,void *,USERSTATE_SETTING_SOURCES)
0x18001ef00  test    eax, eax
0x18001ef02  js      short loc_18001EF0A
0x18001ef04  cmp     word ptr [rbp+var_38], di
0x18001ef08  jnz     short loc_18001EF0E
0x18001ef0a  mov     word ptr [rbp+var_50], di
0x18001ef0e  lea     rcx, [rbp+var_38]; pvarg
0x18001ef12  call    cs:__imp_VariantClear
0x18001ef18  xor     eax, eax
0x18001ef1a  lea     rdx, [rbp+var_50]; struct tagVARIANT *
0x18001ef1e  lea     rcx, [rbp+var_38]; this
0x18001ef22  mov     word ptr [rbp+var_38], ax
0x18001ef26  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18001ef2b  lea     r8, [rbp+var_38]
0x18001ef2f  mov     rcx, rbx
0x18001ef32  lea     rdx, CSCWMI_STR_PROP_DISKSPACELIMITENABLED; "DiskSpaceLimitEnabled"
0x18001ef39  call    ?WmiProp_SetProperty@@YAJPEAUIWbemClassObject@@PEBGVCComVariant@ATL@@@Z; WmiProp_SetProperty(IWbemClassObject *,ushort const *,ATL::CComVariant)
0x18001ef3e  lea     rcx, [rbp+pvarg]; pvarg
0x18001ef42  mov     ebx, eax
0x18001ef44  call    cs:__imp_VariantClear
0x18001ef4a  lea     rcx, [rbp+var_50]; pvarg
0x18001ef4e  call    cs:__imp_VariantClear
0x18001ef54  lea     r11, [rsp+70h+var_s0]
0x18001ef59  mov     eax, ebx
0x18001ef5b  mov     rbx, [r11+10h]
0x18001ef5f  mov     rdi, [r11+18h]
0x18001ef63  mov     rsp, r11
0x18001ef66  pop     rbp
0x18001ef67  retn
```
