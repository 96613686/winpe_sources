# EEDBManager::CreateEnrollment(Enrollment *,MDMEnrollInfoTag *,EnrollmentEnrollType)

- ea: `0x18003e03c`
- end: `0x18003e1ca`
- name: `?CreateEnrollment@EEDBManager@@QEAAJPEAVEnrollment@@PEAUMDMEnrollInfoTag@@W4EnrollmentEnrollType@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003717c`

## callees

- `0x1800071c0`
- `0x180010950`
- `0x18003e03c`
- `0x18003e570`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e158`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e18b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e158`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e18b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e1ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e1ad`

## string_xrefs

- `0x18003e0e3`: `DiscoveryServiceFullURL`

## pseudocode

```c
__int64 __fastcall EEDBManager::CreateEnrollment(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  signed int v7; // ebx
  __int64 v8; // rcx
  LSTATUS v9; // eax
  bool v10; // cc
  HKEY hKey[2]; // [rsp+30h] [rbp-20h] BYREF
  __int128 v13; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+70h] [rbp+20h] BYREF
  int v15; // [rsp+74h] [rbp+24h]
  int Data; // [rsp+78h] [rbp+28h] BYREF

  v15 = HIDWORD(a1);
  hKey[0] = 0;
  v14 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v14);
  if ( v7 >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hKey,
      0);
    v13 = *(_OWORD *)(a2 + 28);
    v7 = EEDBManager::CreateEnrollmentCommon(v8, &v13, v14, a4, hKey);
    if ( v7 >= 0 )
    {
      v7 = WriteStringToRegistry(hKey[0], L"UPN", *(const unsigned __int16 **)a3);
      if ( v7 >= 0 )
      {
        v7 = WriteStringToRegistry(hKey[0], L"DiscoveryServiceFullURL", *(const unsigned __int16 **)(a3 + 8));
        if ( v7 >= 0 )
        {
          v7 = WriteStringToRegistry(hKey[0], L"DomainUsername", *(const unsigned __int16 **)(a3 + 32));
          if ( v7 >= 0 )
          {
            v7 = WriteStringToRegistry(hKey[0], L"SID", *(const unsigned __int16 **)(a3 + 56));
            if ( v7 >= 0 )
            {
              v9 = RegSetValueExW(hKey[0], L"IsFederated", 0, 4u, (const BYTE *)(a3 + 24), 4u);
              v10 = v9 <= 0;
              if ( v9
                || (Data = *(_DWORD *)(a3 + 28) & 0x100000,
                    v9 = RegSetValueExW(hKey[0], L"EnrollmentFlags", 0, 4u, (const BYTE *)&Data, 4u),
                    v10 = v9 <= 0,
                    v9) )
              {
                if ( v10 )
                  v7 = v9;
                else
                  v7 = (unsigned __int16)v9 | 0x80070000;
              }
            }
          }
        }
      }
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e03c  mov     [rsp-18h+arg_10], rbx
0x18003e041  mov     [rsp-18h+arg_18], rsi
0x18003e046  mov     [rsp-18h+arg_0], rcx
0x18003e04b  push    rbp
0x18003e04c  push    rdi
0x18003e04d  push    r14
0x18003e04f  mov     rbp, rsp
0x18003e052  sub     rsp, 50h
0x18003e056  mov     r14d, r9d
0x18003e059  mov     rdi, r8
0x18003e05c  mov     rsi, rdx
0x18003e05f  mov     [rbp+hKey], 0
0x18003e067  mov     dword ptr [rbp+arg_0], 0
0x18003e06e  mov     rax, [rdx]
0x18003e071  lea     rdx, [rbp+arg_0]
0x18003e075  mov     rcx, rsi
0x18003e078  mov     rax, [rax+38h]
0x18003e07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e081  mov     ebx, eax
0x18003e083  test    eax, eax
0x18003e085  js      loc_18003E1A4
0x18003e08b  xor     edx, edx
0x18003e08d  lea     rcx, [rbp+hKey]
0x18003e091  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e096  movups  xmm0, xmmword ptr [rsi+1Ch]
0x18003e09a  movdqu  [rbp+var_10], xmm0
0x18003e09f  lea     rax, [rbp+hKey]
0x18003e0a3  mov     [rsp+50h+lpData], rax
0x18003e0a8  mov     r9d, r14d
0x18003e0ab  mov     r8d, dword ptr [rbp+arg_0]
0x18003e0af  lea     rdx, [rbp+var_10]
0x18003e0b3  call    ?CreateEnrollmentCommon@EEDBManager@@AEAAJU_GUID@@W4EnrollmentStateTag@@W4EnrollmentEnrollType@@PEAPEAUHKEY__@@@Z; EEDBManager::CreateEnrollmentCommon(_GUID,EnrollmentStateTag,EnrollmentEnrollType,HKEY__ * *)
0x18003e0b8  mov     ebx, eax
0x18003e0ba  test    eax, eax
0x18003e0bc  js      loc_18003E1A4
0x18003e0c2  mov     r8, [rdi]; unsigned __int16 *
0x18003e0c5  lea     rdx, aUpn; "UPN"
0x18003e0cc  mov     rcx, [rbp+hKey]; hKey
0x18003e0d0  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e0d5  mov     ebx, eax
0x18003e0d7  test    eax, eax
0x18003e0d9  js      loc_18003E1A4
0x18003e0df  mov     r8, [rdi+8]; unsigned __int16 *
0x18003e0e3  lea     rdx, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18003e0ea  mov     rcx, [rbp+hKey]; hKey
0x18003e0ee  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e0f3  mov     ebx, eax
0x18003e0f5  test    eax, eax
0x18003e0f7  js      loc_18003E1A4
0x18003e0fd  mov     r8, [rdi+20h]; unsigned __int16 *
0x18003e101  lea     rdx, aDomainusername; "DomainUsername"
0x18003e108  mov     rcx, [rbp+hKey]; hKey
0x18003e10c  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e111  mov     ebx, eax
0x18003e113  test    eax, eax
0x18003e115  js      loc_18003E1A4
0x18003e11b  mov     r8, [rdi+38h]; unsigned __int16 *
0x18003e11f  lea     rdx, aSid; "SID"
0x18003e126  mov     rcx, [rbp+hKey]; hKey
0x18003e12a  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003e12f  mov     ebx, eax
0x18003e131  test    eax, eax
0x18003e133  js      short loc_18003E1A4
0x18003e135  lea     rax, [rdi+18h]
0x18003e139  mov     esi, 4
0x18003e13e  mov     [rsp+50h+cbData], esi; cbData
0x18003e142  mov     [rsp+50h+lpData], rax; lpData
0x18003e147  mov     r9d, esi; dwType
0x18003e14a  xor     r8d, r8d; Reserved
0x18003e14d  lea     rdx, aIsfederated; "IsFederated"
0x18003e154  mov     rcx, [rbp+hKey]; hKey
0x18003e158  call    cs:__imp_RegSetValueExW
0x18003e15e  test    eax, eax
0x18003e160  jnz     short loc_18003E195
0x18003e162  mov     eax, [rdi+1Ch]
0x18003e165  and     eax, 100000h
0x18003e16a  mov     [rbp+Data], eax
0x18003e16d  mov     [rsp+50h+cbData], esi; cbData
0x18003e171  lea     rax, [rbp+Data]
0x18003e175  mov     [rsp+50h+lpData], rax; lpData
0x18003e17a  mov     r9d, esi; dwType
0x18003e17d  xor     r8d, r8d; Reserved
0x18003e180  lea     rdx, aEnrollmentflag; "EnrollmentFlags"
0x18003e187  mov     rcx, [rbp+hKey]; hKey
0x18003e18b  call    cs:__imp_RegSetValueExW
0x18003e191  test    eax, eax
0x18003e193  jz      short loc_18003E1A4
0x18003e195  jg      short loc_18003E19B
0x18003e197  mov     ebx, eax
0x18003e199  jmp     short loc_18003E1A4
0x18003e19b  movzx   ebx, ax
0x18003e19e  or      ebx, 80070000h
0x18003e1a4  mov     rcx, [rbp+hKey]; hKey
0x18003e1a8  test    rcx, rcx
0x18003e1ab  jz      short loc_18003E1B3
0x18003e1ad  call    cs:__imp_RegCloseKey
0x18003e1b3  mov     eax, ebx
0x18003e1b5  lea     r11, [rsp+50h+var_s0]
0x18003e1ba  mov     rbx, [r11+30h]
0x18003e1be  mov     rsi, [r11+38h]
0x18003e1c2  mov     rsp, r11
0x18003e1c5  pop     r14
0x18003e1c7  pop     rdi
0x18003e1c8  pop     rbp
0x18003e1c9  retn
```
