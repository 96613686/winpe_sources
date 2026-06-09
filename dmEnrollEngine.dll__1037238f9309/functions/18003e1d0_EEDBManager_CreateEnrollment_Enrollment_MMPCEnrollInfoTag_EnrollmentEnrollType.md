# EEDBManager::CreateEnrollment(Enrollment *,MMPCEnrollInfoTag *,EnrollmentEnrollType)

- ea: `0x18003e1d0`
- end: `0x18003e403`
- name: `?CreateEnrollment@EEDBManager@@QEAAJPEAVEnrollment@@PEAUMMPCEnrollInfoTag@@W4EnrollmentEnrollType@@@Z`
- size: `563`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800371d0`

## callees

- `0x1800071c0`
- `0x180010950`
- `0x18003e1d0`
- `0x18003e570`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e391`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e3c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e391`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e3c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e3e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e3e6`

## string_xrefs

- `0x18003e2a0`: `DiscoveryServiceFullURL`

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
  HKEY hKey[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v14; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+20h] BYREF
  int v16; // [rsp+74h] [rbp+24h]
  int Data; // [rsp+78h] [rbp+28h] BYREF

  v16 = HIDWORD(a1);
  hKey[0] = 0;
  v15 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v15);
  if ( v7 >= 0 )
  {
    if ( ((a4 - 6) & 0xFFFFFFEF) != 0 || *(_QWORD *)(a3 + 40) && (a4 != 22 || *(_QWORD *)(a3 + 72)) )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        hKey,
        0);
      v14 = *(_OWORD *)(a2 + 28);
      v7 = EEDBManager::CreateEnrollmentCommon(v8, &v14, v15, a4, hKey);
      if ( v7 >= 0 )
      {
        v7 = WriteStringToRegistry(hKey[0], L"UPN", *(const unsigned __int16 **)(a3 + 8));
        if ( v7 >= 0 )
        {
          v7 = WriteStringToRegistry(hKey[0], L"DiscoveryServiceFullURL", *(const unsigned __int16 **)(a3 + 16));
          if ( v7 >= 0 )
          {
            v7 = WriteStringToRegistry(hKey[0], L"PartnerOpaqueID", *(const unsigned __int16 **)a3);
            if ( v7 >= 0 )
            {
              v7 = WriteStringToRegistry(hKey[0], L"AADResourceID", *(const unsigned __int16 **)(a3 + 40));
              if ( v7 >= 0 )
              {
                v7 = WriteStringToRegistry(hKey[0], L"AADOpaqueID", *(const unsigned __int16 **)(a3 + 64));
                if ( v7 >= 0 )
                {
                  v7 = WriteStringToRegistry(hKey[0], L"AADTenantID", *(const unsigned __int16 **)(a3 + 72));
                  if ( v7 >= 0 )
                  {
                    v7 = WriteStringToRegistry(hKey[0], L"CorrelationID", *(const unsigned __int16 **)(a3 + 80));
                    if ( v7 >= 0 )
                    {
                      v9 = *(const unsigned __int16 **)(a3 + 48);
                      if ( !v9 || (v7 = WriteStringToRegistry(hKey[0], L"SID", v9), v7 >= 0) )
                      {
                        v10 = RegSetValueExW(hKey[0], L"IsFederated", 0, 4u, (const BYTE *)(a3 + 88), 4u);
                        v11 = v10 <= 0;
                        if ( v10
                          || (Data = *(_DWORD *)(a3 + 56) & 0x100000,
                              v10 = RegSetValueExW(hKey[0], L"EnrollmentFlags", 0, 4u, (const BYTE *)&Data, 4u),
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
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e1d0  mov     [rsp-18h+arg_10], rbx
0x18003e1d5  mov     [rsp-18h+arg_18], rsi
0x18003e1da  mov     [rsp-18h+arg_0], rcx
0x18003e1df  push    rbp
0x18003e1e0  push    rdi
0x18003e1e1  push    r14
0x18003e1e3  mov     rbp, rsp
0x18003e1e6  sub     rsp, 50h
0x18003e1ea  mov     esi, r9d
0x18003e1ed  mov     rdi, r8
0x18003e1f0  mov     r14, rdx
0x18003e1f3  mov     [rbp+hKey], 0
0x18003e1fb  mov     dword ptr [rbp+arg_0], 0
0x18003e202  mov     rax, [rdx]
0x18003e205  lea     rdx, [rbp+arg_0]
0x18003e209  mov     rcx, r14
0x18003e20c  mov     rax, [rax+38h]
0x18003e210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e215  mov     ebx, eax
0x18003e217  test    eax, eax
0x18003e219  js      loc_18003E3DD
0x18003e21f  lea     eax, [rsi-6]
0x18003e222  test    eax, 0FFFFFFEFh
0x18003e227  jnz     short loc_18003E246
0x18003e229  cmp     qword ptr [rdi+28h], 0
0x18003e22e  jnz     short loc_18003E23A
0x18003e230  mov     ebx, 80070057h
0x18003e235  jmp     loc_18003E3DD
0x18003e23a  cmp     esi, 16h
0x18003e23d  jnz     short loc_18003E246
0x18003e23f  cmp     qword ptr [rdi+48h], 0
0x18003e244  jz      short loc_18003E230
0x18003e246  xor     edx, edx
0x18003e248  lea     rcx, [rbp+hKey]
0x18003e24c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e251  movups  xmm0, xmmword ptr [r14+1Ch]
0x18003e256  movdqu  [rbp+var_10], xmm0
0x18003e25b  lea     rax, [rbp+hKey]
0x18003e25f  mov     [rsp+50h+lpData], rax
0x18003e264  mov     r9d, esi
0x18003e267  mov     r8d, dword ptr [rbp+arg_0]
0x18003e26b  lea     rdx, [rbp+var_10]
0x18003e26f  call    ?CreateEnrollmentCommon@EEDBManager@@AEAAJU_GUID@@W4EnrollmentStateTag@@W4EnrollmentEnrollType@@PEAPEAUHKEY__@@@Z; EEDBManager::CreateEnrollmentCommon(_GUID,EnrollmentStateTag,EnrollmentEnrollType,HKEY__ * *)
0x18003e274  mov     ebx, eax
0x18003e276  test    eax, eax
0x18003e278  js      loc_18003E3DD
0x18003e27e  mov     r8, [rdi+8]; unsigned __int16 *
0x18003e282  lea     rdx, aUpn; "UPN"
0x18003e289  mov     rcx, [rbp+hKey]; hKey
0x18003e28d  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e292  mov     ebx, eax
0x18003e294  test    eax, eax
0x18003e296  js      loc_18003E3DD
0x18003e29c  mov     r8, [rdi+10h]; unsigned __int16 *
0x18003e2a0  lea     rdx, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18003e2a7  mov     rcx, [rbp+hKey]; hKey
0x18003e2ab  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e2b0  mov     ebx, eax
0x18003e2b2  test    eax, eax
0x18003e2b4  js      loc_18003E3DD
0x18003e2ba  mov     r8, [rdi]; unsigned __int16 *
0x18003e2bd  lea     rdx, aPartneropaquei; "PartnerOpaqueID"
0x18003e2c4  mov     rcx, [rbp+hKey]; hKey
0x18003e2c8  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e2cd  mov     ebx, eax
0x18003e2cf  test    eax, eax
0x18003e2d1  js      loc_18003E3DD
0x18003e2d7  mov     r8, [rdi+28h]; unsigned __int16 *
0x18003e2db  lea     rdx, aAadresourceid; "AADResourceID"
0x18003e2e2  mov     rcx, [rbp+hKey]; hKey
0x18003e2e6  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e2eb  mov     ebx, eax
0x18003e2ed  test    eax, eax
0x18003e2ef  js      loc_18003E3DD
0x18003e2f5  mov     r8, [rdi+40h]; unsigned __int16 *
0x18003e2f9  lea     rdx, aAadopaqueid; "AADOpaqueID"
0x18003e300  mov     rcx, [rbp+hKey]; hKey
0x18003e304  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e309  mov     ebx, eax
0x18003e30b  test    eax, eax
0x18003e30d  js      loc_18003E3DD
0x18003e313  mov     r8, [rdi+48h]; unsigned __int16 *
0x18003e317  lea     rdx, aAadtenantid; "AADTenantID"
0x18003e31e  mov     rcx, [rbp+hKey]; hKey
0x18003e322  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e327  mov     ebx, eax
0x18003e329  test    eax, eax
0x18003e32b  js      loc_18003E3DD
0x18003e331  mov     r8, [rdi+50h]; unsigned __int16 *
0x18003e335  lea     rdx, aCorrelationid; "CorrelationID"
0x18003e33c  mov     rcx, [rbp+hKey]; hKey
0x18003e340  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e345  mov     ebx, eax
0x18003e347  test    eax, eax
0x18003e349  js      loc_18003E3DD
0x18003e34f  mov     r8, [rdi+30h]; unsigned __int16 *
0x18003e353  test    r8, r8
0x18003e356  jz      short loc_18003E36E
0x18003e358  lea     rdx, aSid; "SID"
0x18003e35f  mov     rcx, [rbp+hKey]; hKey
0x18003e363  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e368  mov     ebx, eax
0x18003e36a  test    eax, eax
0x18003e36c  js      short loc_18003E3DD
0x18003e36e  lea     rax, [rdi+58h]
0x18003e372  mov     esi, 4
0x18003e377  mov     [rsp+50h+cbData], esi; cbData
0x18003e37b  mov     [rsp+50h+lpData], rax; lpData
0x18003e380  mov     r9d, esi; dwType
0x18003e383  xor     r8d, r8d; Reserved
0x18003e386  lea     rdx, aIsfederated; "IsFederated"
0x18003e38d  mov     rcx, [rbp+hKey]; hKey
0x18003e391  call    cs:__imp_RegSetValueExW
0x18003e397  test    eax, eax
0x18003e399  jnz     short loc_18003E3CE
0x18003e39b  mov     eax, [rdi+38h]
0x18003e39e  and     eax, 100000h
0x18003e3a3  mov     [rbp+Data], eax
0x18003e3a6  mov     [rsp+50h+cbData], esi; cbData
0x18003e3aa  lea     rax, [rbp+Data]
0x18003e3ae  mov     [rsp+50h+lpData], rax; lpData
0x18003e3b3  mov     r9d, esi; dwType
0x18003e3b6  xor     r8d, r8d; Reserved
0x18003e3b9  lea     rdx, aEnrollmentflag; "EnrollmentFlags"
0x18003e3c0  mov     rcx, [rbp+hKey]; hKey
0x18003e3c4  call    cs:__imp_RegSetValueExW
0x18003e3ca  test    eax, eax
0x18003e3cc  jz      short loc_18003E3DD
0x18003e3ce  jg      short loc_18003E3D4
0x18003e3d0  mov     ebx, eax
0x18003e3d2  jmp     short loc_18003E3DD
0x18003e3d4  movzx   ebx, ax
0x18003e3d7  or      ebx, 80070000h
0x18003e3dd  mov     rcx, [rbp+hKey]; hKey
0x18003e3e1  test    rcx, rcx
0x18003e3e4  jz      short loc_18003E3EC
0x18003e3e6  call    cs:__imp_RegCloseKey
0x18003e3ec  mov     eax, ebx
0x18003e3ee  lea     r11, [rsp+50h+var_s0]
0x18003e3f3  mov     rbx, [r11+30h]
0x18003e3f7  mov     rsi, [r11+38h]
0x18003e3fb  mov     rsp, r11
0x18003e3fe  pop     r14
0x18003e400  pop     rdi
0x18003e401  pop     rbp
0x18003e402  retn
```
