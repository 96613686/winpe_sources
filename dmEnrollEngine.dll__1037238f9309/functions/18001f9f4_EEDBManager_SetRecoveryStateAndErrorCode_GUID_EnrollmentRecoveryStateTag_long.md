# EEDBManager::SetRecoveryStateAndErrorCode(_GUID,EnrollmentRecoveryStateTag,long)

- ea: `0x18001f9f4`
- end: `0x18001fad7`
- name: `?SetRecoveryStateAndErrorCode@EEDBManager@@SAJU_GUID@@W4EnrollmentRecoveryStateTag@@J@Z`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000e5dc`
- `0x180040da0`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x18001f9f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fa68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001faa6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fa68`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001faa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fac4`

## pseudocode

```c
__int64 __fastcall EEDBManager::SetRecoveryStateAndErrorCode(struct _GUID *a1, int a2, int a3)
{
  LSTATUS v4; // eax
  HKEY v5; // rcx
  signed int v6; // ebx
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  struct _GUID v10; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+10h] BYREF
  int Data; // [rsp+58h] [rbp+18h] BYREF
  int lpData; // [rsp+60h] [rbp+20h] BYREF

  lpData = a3;
  Data = a2;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v10 = *a1;
  v4 = EEDBManager::OpenEnrollmentKey(&v10, 131103, 0, &hKey);
  v5 = hKey;
  v6 = v4;
  if ( v4 >= 0 )
  {
    v7 = RegSetValueExW(hKey, L"RecoveryStatus", 0, 4u, (const BYTE *)&Data, 4u);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    v5 = hKey;
    if ( v6 >= 0 )
    {
      v8 = RegSetValueExW(hKey, L"RecoveryErrorCode", 0, 4u, (const BYTE *)&lpData, 4u);
      v6 = v8;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      v5 = hKey;
    }
  }
  if ( v5 )
    RegCloseKey(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f9f4  mov     [rsp-8+arg_18], rbx
0x18001f9f9  mov     [rsp-8+arg_10], r8d
0x18001f9fe  mov     [rsp-8+Data], edx
0x18001fa02  push    rbp
0x18001fa03  mov     rbp, rsp
0x18001fa06  sub     rsp, 40h
0x18001fa0a  mov     rbx, rcx
0x18001fa0d  mov     [rbp+hKey], 0
0x18001fa15  lea     rcx, [rbp+hKey]
0x18001fa19  xor     edx, edx
0x18001fa1b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001fa20  movaps  xmm0, xmmword ptr [rbx]
0x18001fa23  lea     r9, [rbp+hKey]; HKEY *
0x18001fa27  xor     r8d, r8d; unsigned __int16 *
0x18001fa2a  movdqa  xmmword ptr [rbp+var_10.Data1], xmm0
0x18001fa2f  mov     edx, 2001Fh; unsigned int
0x18001fa34  lea     rcx, [rbp+var_10]; struct _GUID
0x18001fa38  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x18001fa3d  mov     rcx, [rbp+hKey]; hKey
0x18001fa41  mov     ebx, eax
0x18001fa43  test    eax, eax
0x18001fa45  js      short loc_18001FABF
0x18001fa47  lea     rax, [rbp+Data]
0x18001fa4b  mov     [rsp+40h+cbData], 4; cbData
0x18001fa53  mov     r9d, 4; dwType
0x18001fa59  mov     [rsp+40h+lpData], rax; lpData
0x18001fa5e  xor     r8d, r8d; Reserved
0x18001fa61  lea     rdx, aRecoverystatus; "RecoveryStatus"
0x18001fa68  call    cs:__imp_RegSetValueExW
0x18001fa6e  mov     ebx, eax
0x18001fa70  test    eax, eax
0x18001fa72  jle     short loc_18001FA7D
0x18001fa74  movzx   ebx, ax
0x18001fa77  or      ebx, 80070000h
0x18001fa7d  mov     rcx, [rbp+hKey]; hKey
0x18001fa81  test    ebx, ebx
0x18001fa83  js      short loc_18001FABF
0x18001fa85  lea     rax, [rbp+arg_10]
0x18001fa89  mov     [rsp+40h+cbData], 4; cbData
0x18001fa91  mov     r9d, 4; dwType
0x18001fa97  mov     [rsp+40h+lpData], rax; lpData
0x18001fa9c  xor     r8d, r8d; Reserved
0x18001fa9f  lea     rdx, aRecoveryerrorc; "RecoveryErrorCode"
0x18001faa6  call    cs:__imp_RegSetValueExW
0x18001faac  mov     ebx, eax
0x18001faae  test    eax, eax
0x18001fab0  jle     short loc_18001FABB
0x18001fab2  movzx   ebx, ax
0x18001fab5  or      ebx, 80070000h
0x18001fabb  mov     rcx, [rbp+hKey]; hKey
0x18001fabf  test    rcx, rcx
0x18001fac2  jz      short loc_18001FACA
0x18001fac4  call    cs:__imp_RegCloseKey
0x18001faca  mov     eax, ebx
0x18001facc  mov     rbx, [rsp+40h+arg_18]
0x18001fad1  add     rsp, 40h
0x18001fad5  pop     rbp
0x18001fad6  retn
```
