# Microsoft::Windows::MDM::OmadmClient::PowerStateManager::UpdateSkippedSessionsCount(ulong,ushort const *)

- ea: `0x14004e2a4`
- end: `0x14004e37f`
- name: `?UpdateSkippedSessionsCount@PowerStateManager@OmadmClient@MDM@Windows@Microsoft@@AEAAJKPEBG@Z`
- size: `219`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::PowerStateManager *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14004db50`

## callees

- `0x14000b0f4`
- `0x14004e030`
- `0x14004e2a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004e328`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004e328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e2f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e34d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e365`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e2f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e34d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e365`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::PowerStateManager::UpdateSkippedSessionsCount(
        Microsoft::Windows::MDM::OmadmClient::PowerStateManager *this,
        int a2,
        const unsigned __int16 *a3)
{
  int PowerSettingsKey; // eax
  unsigned int v4; // ebx
  HKEY v6; // rbx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  hKey = 0;
  PowerSettingsKey = Microsoft::Windows::MDM::OmadmClient::PowerStateManager::GetPowerSettingsKey(this, &hKey, a3);
  v4 = PowerSettingsKey;
  if ( PowerSettingsKey >= 0 )
  {
    v6 = hKey;
    v7 = RegSetValueExW(hKey, L"SessionsSkippedCountInLowPowerState", 0, 4u, (const BYTE *)&Data, 4u);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      if ( v6 )
        RegCloseKey(v6);
      return v8;
    }
    else
    {
      if ( v6 )
        RegCloseKey(v6);
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\powerstatemanager.cpp",
      (const char *)(unsigned int)PowerSettingsKey,
      lpData);
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
}

```

## disassembly

```asm
0x14004e2a4  mov     rax, rsp
0x14004e2a7  mov     [rax+18h], rbx
0x14004e2ab  mov     [rax+10h], edx
0x14004e2ae  mov     [rax+8], rcx
0x14004e2b2  push    rdi
0x14004e2b3  sub     rsp, 30h
0x14004e2b7  lea     rdx, [rax+8]; HKEY *
0x14004e2bb  mov     qword ptr [rax+8], 0
0x14004e2c3  call    ?GetPowerSettingsKey@PowerStateManager@OmadmClient@MDM@Windows@Microsoft@@AEAAJPEAPEAUHKEY__@@PEBG@Z; Microsoft::Windows::MDM::OmadmClient::PowerStateManager::GetPowerSettingsKey(HKEY__ * *,ushort const *)
0x14004e2c8  mov     ebx, eax
0x14004e2ca  test    eax, eax
0x14004e2cc  jns     short loc_14004E301
0x14004e2ce  mov     rcx, [rsp+38h]; this
0x14004e2d3  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004e2da  mov     r9d, eax; char *
0x14004e2dd  mov     edx, 148h; void *
0x14004e2e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004e2e7  mov     rcx, [rsp+38h+hKey]; hKey
0x14004e2ec  test    rcx, rcx
0x14004e2ef  jz      short loc_14004E2FD
0x14004e2f1  call    cs:__imp_RegCloseKey
0x14004e2f8  nop     dword ptr [rax+rax+00h]
0x14004e2fd  mov     eax, ebx
0x14004e2ff  jmp     short loc_14004E373
0x14004e301  mov     rbx, [rsp+38h+hKey]
0x14004e306  lea     rax, [rsp+38h+Data]
0x14004e30b  mov     r9d, 4; dwType
0x14004e311  lea     rdx, aSessionsskippe; "SessionsSkippedCountInLowPowerState"
0x14004e318  mov     [rsp+38h+cbData], r9d; cbData
0x14004e31d  mov     rcx, rbx; hKey
0x14004e320  xor     r8d, r8d; Reserved
0x14004e323  mov     [rsp+38h+lpData], rax; lpData
0x14004e328  call    cs:__imp_RegSetValueExW
0x14004e32f  nop     dword ptr [rax+rax+00h]
0x14004e334  mov     edi, eax
0x14004e336  test    eax, eax
0x14004e338  jz      short loc_14004E35D
0x14004e33a  jle     short loc_14004E345
0x14004e33c  movzx   edi, ax
0x14004e33f  or      edi, 80070000h
0x14004e345  test    rbx, rbx
0x14004e348  jz      short loc_14004E359
0x14004e34a  mov     rcx, rbx; hKey
0x14004e34d  call    cs:__imp_RegCloseKey
0x14004e354  nop     dword ptr [rax+rax+00h]
0x14004e359  mov     eax, edi
0x14004e35b  jmp     short loc_14004E373
0x14004e35d  test    rbx, rbx
0x14004e360  jz      short loc_14004E371
0x14004e362  mov     rcx, rbx; hKey
0x14004e365  call    cs:__imp_RegCloseKey
0x14004e36c  nop     dword ptr [rax+rax+00h]
0x14004e371  xor     eax, eax
0x14004e373  mov     rbx, [rsp+38h+arg_10]
0x14004e378  add     rsp, 30h
0x14004e37c  pop     rdi
0x14004e37d  retn
```
