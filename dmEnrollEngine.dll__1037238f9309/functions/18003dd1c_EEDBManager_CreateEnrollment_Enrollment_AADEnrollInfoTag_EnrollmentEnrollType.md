# EEDBManager::CreateEnrollment(Enrollment *,AADEnrollInfoTag *,EnrollmentEnrollType)

- ea: `0x18003dd1c`
- end: `0x18003df56`
- name: `?CreateEnrollment@EEDBManager@@QEAAJPEAVEnrollment@@PEAUAADEnrollInfoTag@@W4EnrollmentEnrollType@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800370f0`

## callees

- `0x1800071c0`
- `0x180010950`
- `0x18003dd1c`
- `0x18003e570`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dee4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003df17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dee4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003df17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003df39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003df39`

## string_xrefs

- `0x18003ddec`: `DiscoveryServiceFullURL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EEDBManager::CreateEnrollment(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  signed int v7; // ebx
  __int64 v8; // rcx
  const unsigned __int16 *v9; // r8
  LSTATUS v10; // eax
  bool v11; // cc
  BYTE lpData[8]; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  __int128 v15; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+20h] BYREF
  int v17; // [rsp+74h] [rbp+24h]
  int Data; // [rsp+78h] [rbp+28h] BYREF

  v17 = HIDWORD(a1);
  hKey = 0;
  v16 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v16);
  if ( v7 >= 0 )
  {
    if ( ((a4 - 6) & 0xFFFFFFEF) != 0 || *(_QWORD *)(a3 + 40) && (a4 != 22 || *(_QWORD *)(a3 + 72)) )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v15 = *(_OWORD *)(a2 + 28);
      v7 = EEDBManager::CreateEnrollmentCommon(v8, &v15, v16, a4, &hKey);
      if ( v7 >= 0 )
      {
        v7 = WriteStringToRegistry(hKey, L"UPN", *(const unsigned __int16 **)(a3 + 8));
        if ( v7 >= 0 )
        {
          v7 = WriteStringToRegistry(hKey, L"DiscoveryServiceFullURL", *(const unsigned __int16 **)(a3 + 16));
          if ( v7 >= 0 )
          {
            v7 = WriteStringToRegistry(hKey, L"PartnerOpaqueID", *(const unsigned __int16 **)a3);
            if ( v7 >= 0 )
            {
              v7 = WriteStringToRegistry(hKey, L"AADResourceID", *(const unsigned __int16 **)(a3 + 40));
              if ( v7 >= 0 )
              {
                v7 = WriteStringToRegistry(hKey, L"AADOpaqueID", *(const unsigned __int16 **)(a3 + 64));
                if ( v7 >= 0 )
                {
                  v7 = WriteStringToRegistry(hKey, L"AADTenantID", *(const unsigned __int16 **)(a3 + 72));
                  if ( v7 >= 0 )
                  {
                    v7 = WriteStringToRegistry(hKey, L"CorrelationID", *(const unsigned __int16 **)(a3 + 80));
                    if ( v7 >= 0 )
                    {
                      v9 = *(const unsigned __int16 **)(a3 + 48);
                      if ( !v9 || (v7 = WriteStringToRegistry(hKey, L"SID", v9), v7 >= 0) )
                      {
                        Data = 1;
                        v10 = RegSetValueExW(hKey, L"IsFederated", 0, 4u, (const BYTE *)&Data, 4u);
                        v11 = v10 <= 0;
                        if ( v10
                          || (*(_DWORD *)lpData = *(_DWORD *)(a3 + 56) & 0x100000,
                              v10 = RegSetValueExW(hKey, L"EnrollmentFlags", 0, 4u, lpData, 4u),
                              v11 = v10 <= 0,
                              v10) )
                        {
                          if ( v11 )
                            v7 = v10;
                          else
                            v7 = (unsigned __int16)v10 | 0x80070000;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      v7 = -2147024809;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003dd1c  mov     [rsp-18h+arg_10], rbx
0x18003dd21  mov     [rsp-18h+arg_18], rsi
0x18003dd26  mov     [rsp-18h+arg_0], rcx
0x18003dd2b  push    rbp
0x18003dd2c  push    rdi
0x18003dd2d  push    r14
0x18003dd2f  mov     rbp, rsp
0x18003dd32  sub     rsp, 50h
0x18003dd36  mov     esi, r9d
0x18003dd39  mov     rdi, r8
0x18003dd3c  mov     r14, rdx
0x18003dd3f  mov     [rbp+hKey], 0
0x18003dd47  mov     dword ptr [rbp+arg_0], 0
0x18003dd4e  mov     rax, [rdx]
0x18003dd51  lea     rdx, [rbp+arg_0]
0x18003dd55  mov     rcx, r14
0x18003dd58  mov     rax, [rax+38h]
0x18003dd5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd61  mov     ebx, eax
0x18003dd63  test    eax, eax
0x18003dd65  js      loc_18003DF30
0x18003dd6b  lea     eax, [rsi-6]
0x18003dd6e  test    eax, 0FFFFFFEFh
0x18003dd73  jnz     short loc_18003DD92
0x18003dd75  cmp     qword ptr [rdi+28h], 0
0x18003dd7a  jnz     short loc_18003DD86
0x18003dd7c  mov     ebx, 80070057h
0x18003dd81  jmp     loc_18003DF30
0x18003dd86  cmp     esi, 16h
0x18003dd89  jnz     short loc_18003DD92
0x18003dd8b  cmp     qword ptr [rdi+48h], 0
0x18003dd90  jz      short loc_18003DD7C
0x18003dd92  xor     edx, edx
0x18003dd94  lea     rcx, [rbp+hKey]
0x18003dd98  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003dd9d  movups  xmm0, xmmword ptr [r14+1Ch]
0x18003dda2  movdqu  [rbp+var_10], xmm0
0x18003dda7  lea     rax, [rbp+hKey]
0x18003ddab  mov     [rsp+50h+lpData], rax
0x18003ddb0  mov     r9d, esi
0x18003ddb3  mov     r8d, dword ptr [rbp+arg_0]
0x18003ddb7  lea     rdx, [rbp+var_10]
0x18003ddbb  call    ?CreateEnrollmentCommon@EEDBManager@@AEAAJU_GUID@@W4EnrollmentStateTag@@W4EnrollmentEnrollType@@PEAPEAUHKEY__@@@Z; EEDBManager::CreateEnrollmentCommon(_GUID,EnrollmentStateTag,EnrollmentEnrollType,HKEY__ * *)
0x18003ddc0  mov     ebx, eax
0x18003ddc2  test    eax, eax
0x18003ddc4  js      loc_18003DF30
0x18003ddca  mov     r8, [rdi+8]; unsigned __int16 *
0x18003ddce  lea     rdx, aUpn; "UPN"
0x18003ddd5  mov     rcx, [rbp+hKey]; hKey
0x18003ddd9  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003ddde  mov     ebx, eax
0x18003dde0  test    eax, eax
0x18003dde2  js      loc_18003DF30
0x18003dde8  mov     r8, [rdi+10h]; unsigned __int16 *
0x18003ddec  lea     rdx, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18003ddf3  mov     rcx, [rbp+hKey]; hKey
0x18003ddf7  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003ddfc  mov     ebx, eax
0x18003ddfe  test    eax, eax
0x18003de00  js      loc_18003DF30
0x18003de06  mov     r8, [rdi]; unsigned __int16 *
0x18003de09  lea     rdx, aPartneropaquei; "PartnerOpaqueID"
0x18003de10  mov     rcx, [rbp+hKey]; hKey
0x18003de14  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003de19  mov     ebx, eax
0x18003de1b  test    eax, eax
0x18003de1d  js      loc_18003DF30
0x18003de23  mov     r8, [rdi+28h]; unsigned __int16 *
0x18003de27  lea     rdx, aAadresourceid; "AADResourceID"
0x18003de2e  mov     rcx, [rbp+hKey]; hKey
0x18003de32  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003de37  mov     ebx, eax
0x18003de39  test    eax, eax
0x18003de3b  js      loc_18003DF30
0x18003de41  mov     r8, [rdi+40h]; unsigned __int16 *
0x18003de45  lea     rdx, aAadopaqueid; "AADOpaqueID"
0x18003de4c  mov     rcx, [rbp+hKey]; hKey
0x18003de50  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003de55  mov     ebx, eax
0x18003de57  test    eax, eax
0x18003de59  js      loc_18003DF30
0x18003de5f  mov     r8, [rdi+48h]; unsigned __int16 *
0x18003de63  lea     rdx, aAadtenantid; "AADTenantID"
0x18003de6a  mov     rcx, [rbp+hKey]; hKey
0x18003de6e  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003de73  mov     ebx, eax
0x18003de75  test    eax, eax
0x18003de77  js      loc_18003DF30
0x18003de7d  mov     r8, [rdi+50h]; unsigned __int16 *
0x18003de81  lea     rdx, aCorrelationid; "CorrelationID"
0x18003de88  mov     rcx, [rbp+hKey]; hKey
0x18003de8c  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003de91  mov     ebx, eax
0x18003de93  test    eax, eax
0x18003de95  js      loc_18003DF30
0x18003de9b  mov     r8, [rdi+30h]; unsigned __int16 *
0x18003de9f  test    r8, r8
0x18003dea2  jz      short loc_18003DEBA
0x18003dea4  lea     rdx, aSid; "SID"
0x18003deab  mov     rcx, [rbp+hKey]; hKey
0x18003deaf  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003deb4  mov     ebx, eax
0x18003deb6  test    eax, eax
0x18003deb8  js      short loc_18003DF30
0x18003deba  mov     [rbp+Data], 1
0x18003dec1  mov     esi, 4
0x18003dec6  mov     [rsp+50h+cbData], esi; cbData
0x18003deca  lea     rax, [rbp+Data]
0x18003dece  mov     [rsp+50h+lpData], rax; lpData
0x18003ded3  mov     r9d, esi; dwType
0x18003ded6  xor     r8d, r8d; Reserved
0x18003ded9  lea     rdx, aIsfederated; "IsFederated"
0x18003dee0  mov     rcx, [rbp+hKey]; hKey
0x18003dee4  call    cs:__imp_RegSetValueExW
0x18003deea  test    eax, eax
0x18003deec  jnz     short loc_18003DF21
0x18003deee  mov     eax, [rdi+38h]
0x18003def1  and     eax, 100000h
0x18003def6  mov     dword ptr [rbp+var_20], eax
0x18003def9  mov     [rsp+50h+cbData], esi; cbData
0x18003defd  lea     rax, [rbp+var_20]
0x18003df01  mov     [rsp+50h+lpData], rax; lpData
0x18003df06  mov     r9d, esi; dwType
0x18003df09  xor     r8d, r8d; Reserved
0x18003df0c  lea     rdx, aEnrollmentflag; "EnrollmentFlags"
0x18003df13  mov     rcx, [rbp+hKey]; hKey
0x18003df17  call    cs:__imp_RegSetValueExW
0x18003df1d  test    eax, eax
0x18003df1f  jz      short loc_18003DF30
0x18003df21  jg      short loc_18003DF27
0x18003df23  mov     ebx, eax
0x18003df25  jmp     short loc_18003DF30
0x18003df27  movzx   ebx, ax
0x18003df2a  or      ebx, 80070000h
0x18003df30  mov     rcx, [rbp+hKey]; hKey
0x18003df34  test    rcx, rcx
0x18003df37  jz      short loc_18003DF3F
0x18003df39  call    cs:__imp_RegCloseKey
0x18003df3f  mov     eax, ebx
0x18003df41  lea     r11, [rsp+50h+var_s0]
0x18003df46  mov     rbx, [r11+30h]
0x18003df4a  mov     rsi, [r11+38h]
0x18003df4e  mov     rsp, r11
0x18003df51  pop     r14
0x18003df53  pop     rdi
0x18003df54  pop     rbp
0x18003df55  retn
```
