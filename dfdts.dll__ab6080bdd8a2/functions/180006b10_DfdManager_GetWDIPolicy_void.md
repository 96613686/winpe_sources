# DfdManager::GetWDIPolicy(void)

- ea: `0x180006b10`
- end: `0x180006c6e`
- name: `?GetWDIPolicy@DfdManager@@AEAAKXZ`
- size: `350`
- prototype: `__int64 __fastcall(DfdManager *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002450`
- `0x180002790`

## callees

- `0x180002c90`
- `0x180006744`
- `0x180006b10`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180006b5b`
- `ADVAPI32!RegOpenKeyExW` at `0x180006b5b`
- `ADVAPI32!RegCloseKey` at `0x180006c52`
- `ADVAPI32!RegCloseKey` at `0x180006c52`
- `ADVAPI32!RegQueryValueExW` at `0x180006bc9`
- `ADVAPI32!RegQueryValueExW` at `0x180006c39`
- `ADVAPI32!RegQueryValueExW` at `0x180006bc9`
- `ADVAPI32!RegQueryValueExW` at `0x180006c39`

## pseudocode

```c
__int64 __fastcall DfdManager::GetWDIPolicy(DfdManager *this)
{
  unsigned int v1; // eax
  _QWORD *v2; // rcx
  bool v3; // bl
  __int64 v4; // rdx
  DfdManager *v5; // rcx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  int v8; // [rsp+54h] [rbp+1Ch]
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v8 = HIDWORD(this);
  Data = 10;
  cbData = 4;
  Type = 4;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows\\WDI", 0, 0x20019u, &hKey);
  if ( v1 )
  {
    v2 = WPP_GLOBAL_Control;
    v3 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 34;
LABEL_5:
      WPP_SF_d(v2[2], v4, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, v1);
    }
  }
  else
  {
    v1 = RegQueryValueExW(hKey, L"ScenarioExecutionEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v1 )
    {
      v2 = WPP_GLOBAL_Control;
      v3 = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 35;
        goto LABEL_5;
      }
    }
    else
    {
      v3 = 0;
      if ( Data )
      {
        v3 = 1;
        if ( Data == 1 )
        {
          Data = 10;
          cbData = 4;
          if ( !RegQueryValueExW(hKey, L"EnabledScenarioExecutionLevel", 0, &Type, (LPBYTE)&Data, &cbData) )
            v3 = Data != 1;
        }
      }
    }
  }
  v5 = (DfdManager *)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    return DfdManager::GetDFDPolicy(v5);
  return Data;
}

```

## disassembly

```asm
0x180006b10  mov     qword ptr [rsp-10h+Data], rcx
0x180006b15  push    rbp
0x180006b16  push    rbx
0x180006b17  mov     rbp, rsp
0x180006b1a  sub     rsp, 38h
0x180006b1e  lea     rax, [rbp+hKey]
0x180006b22  mov     [rbp+Data], 0Ah
0x180006b29  mov     r9d, 20019h; samDesired
0x180006b2f  mov     [rsp+38h+phkResult], rax; phkResult
0x180006b34  xor     r8d, r8d; ulOptions
0x180006b37  mov     [rbp+cbData], 4
0x180006b3e  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180006b45  mov     [rbp+Type], 4
0x180006b4c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006b53  mov     [rbp+hKey], 0
0x180006b5b  call    cs:__imp_RegOpenKeyExW
0x180006b61  test    eax, eax
0x180006b63  jz      short loc_180006BA5
0x180006b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b6c  lea     rdx, WPP_GLOBAL_Control
0x180006b73  mov     ebx, 1
0x180006b78  cmp     rcx, rdx
0x180006b7b  jz      loc_180006C49
0x180006b81  test    [rcx+1Ch], bl
0x180006b84  jz      loc_180006C49
0x180006b8a  lea     edx, [rbx+21h]
0x180006b8d  mov     rcx, [rcx+10h]
0x180006b91  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006b98  mov     r9d, eax
0x180006b9b  call    WPP_SF_d
0x180006ba0  jmp     loc_180006C49
0x180006ba5  mov     rcx, [rbp+hKey]; hKey
0x180006ba9  lea     rax, [rbp+cbData]
0x180006bad  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180006bb2  lea     r9, [rbp+Type]; lpType
0x180006bb6  lea     rax, [rbp+Data]
0x180006bba  xor     r8d, r8d; lpReserved
0x180006bbd  lea     rdx, aScenarioexecut; "ScenarioExecutionEnabled"
0x180006bc4  mov     [rsp+38h+phkResult], rax; lpData
0x180006bc9  call    cs:__imp_RegQueryValueExW
0x180006bcf  test    eax, eax
0x180006bd1  jz      short loc_180006BF5
0x180006bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bda  lea     rdx, WPP_GLOBAL_Control
0x180006be1  mov     ebx, 1
0x180006be6  cmp     rcx, rdx
0x180006be9  jz      short loc_180006C49
0x180006beb  test    [rcx+1Ch], bl
0x180006bee  jz      short loc_180006C49
0x180006bf0  lea     edx, [rbx+22h]
0x180006bf3  jmp     short loc_180006B8D
0x180006bf5  mov     eax, [rbp+Data]
0x180006bf8  xor     bl, bl
0x180006bfa  test    eax, eax
0x180006bfc  jz      short loc_180006C49
0x180006bfe  mov     ebx, 1
0x180006c03  cmp     eax, ebx
0x180006c05  jnz     short loc_180006C49
0x180006c07  mov     rcx, [rbp+hKey]; hKey
0x180006c0b  lea     rax, [rbp+cbData]
0x180006c0f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180006c14  lea     r9, [rbp+Type]; lpType
0x180006c18  lea     rax, [rbp+Data]
0x180006c1c  mov     [rbp+Data], 0Ah
0x180006c23  xor     r8d, r8d; lpReserved
0x180006c26  mov     [rsp+38h+phkResult], rax; lpData
0x180006c2b  lea     rdx, aEnabledscenari; "EnabledScenarioExecutionLevel"
0x180006c32  mov     [rbp+cbData], 4
0x180006c39  call    cs:__imp_RegQueryValueExW
0x180006c3f  test    eax, eax
0x180006c41  jnz     short loc_180006C49
0x180006c43  cmp     [rbp+Data], ebx
0x180006c46  setnz   bl
0x180006c49  mov     rcx, [rbp+hKey]; hKey
0x180006c4d  test    rcx, rcx
0x180006c50  jz      short loc_180006C58
0x180006c52  call    cs:__imp_RegCloseKey
0x180006c58  test    bl, bl
0x180006c5a  jz      short loc_180006C64
0x180006c5c  call    ?GetDFDPolicy@DfdManager@@AEAAKXZ; DfdManager::GetDFDPolicy(void)
0x180006c61  mov     [rbp+Data], eax
0x180006c64  mov     eax, [rbp+Data]
0x180006c67  add     rsp, 38h
0x180006c6b  pop     rbx
0x180006c6c  pop     rbp
0x180006c6d  retn
```
