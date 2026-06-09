# IASIsNTLMv2CompatibilityEnabled

- ea: `0x180028688`
- end: `0x18002890a`
- name: `IASIsNTLMv2CompatibilityEnabled`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800291bc`

## callees

- `0x18001426c`
- `0x18001daa8`
- `0x1800254a0`
- `0x180028688`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800288f8`
- `ADVAPI32!RegCloseKey` at `0x1800288f8`
- `ADVAPI32!RegOpenKeyExW` at `0x1800286e3`
- `ADVAPI32!RegOpenKeyExW` at `0x1800286e3`
- `ADVAPI32!RegQueryValueExW` at `0x18002877d`
- `ADVAPI32!RegQueryValueExW` at `0x18002877d`

## string_xrefs

- `0x18002871d`: `Cannot open the reg key %S, error %ld`
- `0x180028812`: `The registry value %S does not exist. Using default %ld`
- `0x1800288ad`: `Cannot read value %S.  Wrong type %ld. Size = %ld. Value = %ld`
- `0x1800287b9`: `Cannot read value %S.  error %ld`
- `0x1800286a5`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`
- `0x180028763`: `Enable NTLMv2 Compatibility`

## pseudocode

```c
__int64 __fastcall IASIsNTLMv2CompatibilityEnabled(__int64 a1)
{
  unsigned int v1; // ebx
  int v2; // r9d
  LSTATUS v3; // eax
  int v4; // edi
  int v5; // r9d
  int v6; // eax
  int v7; // r9d
  int v8; // r9d
  int Data; // [rsp+70h] [rbp+28h] BYREF
  int v11; // [rsp+74h] [rbp+2Ch]
  DWORD cbData; // [rsp+78h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+40h] BYREF

  v11 = HIDWORD(a1);
  hKey = 0;
  cbData = 4;
  Type = 0;
  Data = 0;
  isNTLMv2CompatibilityEnabled = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
         0,
         0x20019u,
         &hKey);
  if ( !v1 )
  {
    v3 = RegQueryValueExW(hKey, L"Enable NTLMv2 Compatibility", 0, &Type, (LPBYTE)&Data, &cbData);
    v1 = v3;
    v4 = 1;
    if ( v3 )
    {
      if ( v3 == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("The registry value %S does not exist. Using default %ld");
          WPP_SF_sSl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids,
            v7,
            (__int64)L"Enable NTLMv2 Compatibility",
            0);
        }
        v1 = 0;
        v6 = 0;
        Data = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("Cannot read value %S.  error %ld");
          WPP_SF_sSl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids,
            v5,
            (__int64)L"Enable NTLMv2 Compatibility",
            v1);
        }
        v6 = Data;
      }
      if ( v1 )
        goto LABEL_32;
    }
    else
    {
      v6 = Data;
      if ( Type != 4 || cbData != 4 )
        goto LABEL_29;
      if ( !Data )
        goto LABEL_25;
      if ( Data != 1 )
      {
LABEL_29:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("Cannot read value %S.  Wrong type %ld. Size = %ld. Value = %ld");
          WPP_SF_sSlll(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            (unsigned int)WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids,
            v8,
            (__int64)L"Enable NTLMv2 Compatibility",
            Type,
            cbData,
            Data);
        }
        v1 = -2147024809;
        goto LABEL_32;
      }
    }
    if ( v6 )
    {
LABEL_26:
      isNTLMv2CompatibilityEnabled = v4;
LABEL_32:
      RegCloseKey(hKey);
      return v1;
    }
LABEL_25:
    v4 = 0;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Cannot open the reg key %S, error %ld");
    WPP_SF_sSl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids,
      v2,
      (__int64)L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
      v1);
  }
  return v1;
}

```

## disassembly

```asm
0x180028688  mov     qword ptr [rsp-20h+Data], rcx
0x18002868d  push    rbp
0x18002868e  push    rbx
0x18002868f  push    rdi
0x180028690  push    r15
0x180028692  mov     rbp, rsp
0x180028695  sub     rsp, 48h
0x180028699  lea     rax, [rbp+hKey]
0x18002869d  mov     [rbp+hKey], 0
0x1800286a5  lea     rdi, NTLMv2_Compatibility_Key; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x1800286ac  mov     [rbp+cbData], 4
0x1800286b3  mov     rdx, rdi; lpSubKey
0x1800286b6  mov     [rbp+Type], 0
0x1800286bd  mov     r9d, 20019h; samDesired
0x1800286c3  mov     [rbp+Data], 0
0x1800286ca  xor     r8d, r8d; ulOptions
0x1800286cd  mov     cs:isNTLMv2CompatibilityEnabled, 0
0x1800286d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800286de  mov     [rsp+48h+phkResult], rax; phkResult
0x1800286e3  call    cs:__imp_RegOpenKeyExW
0x1800286e9  mov     ebx, eax
0x1800286eb  test    eax, eax
0x1800286ed  jz      short loc_180028756
0x1800286ef  mov     rdx, cs:WPP_GLOBAL_Control
0x1800286f6  lea     rcx, WPP_GLOBAL_Control
0x1800286fd  cmp     rdx, rcx
0x180028700  jz      loc_1800288FE
0x180028706  cmp     byte ptr [rdx+19h], 2
0x18002870a  jb      loc_1800288FE
0x180028710  test    byte ptr [rdx+1Ch], 4
0x180028714  jz      loc_1800288FE
0x18002871a  mov     r8d, eax
0x18002871d  lea     rcx, aCannotOpenTheR; "Cannot open the reg key %S, error %ld"
0x180028724  mov     rdx, rdi
0x180028727  call    WppDbgPrint
0x18002872c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028733  lea     r8, WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids
0x18002873a  mov     edx, 0Dh
0x18002873f  mov     dword ptr [rsp+48h+lpcbData], ebx
0x180028743  mov     [rsp+48h+phkResult], rdi
0x180028748  mov     rcx, [rcx+10h]
0x18002874c  call    WPP_SF_sSl
0x180028751  jmp     loc_1800288FE
0x180028756  mov     rcx, [rbp+hKey]; hKey
0x18002875a  lea     rax, [rbp+cbData]
0x18002875e  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180028763  lea     r15, NTLMv2_Compatibility_Value; "Enable NTLMv2 Compatibility"
0x18002876a  lea     rax, [rbp+Data]
0x18002876e  xor     r8d, r8d; lpReserved
0x180028771  lea     r9, [rbp+Type]; lpType
0x180028775  mov     [rsp+48h+phkResult], rax; lpData
0x18002877a  mov     rdx, r15; lpValueName
0x18002877d  call    cs:__imp_RegQueryValueExW
0x180028783  mov     ebx, eax
0x180028785  mov     edi, 1
0x18002878a  test    eax, eax
0x18002878c  jz      loc_18002885B
0x180028792  cmp     eax, 2
0x180028795  jz      short loc_1800287F0
0x180028797  mov     rax, cs:WPP_GLOBAL_Control
0x18002879e  lea     rcx, WPP_GLOBAL_Control
0x1800287a5  cmp     rax, rcx
0x1800287a8  jz      short loc_1800287EB
0x1800287aa  cmp     byte ptr [rax+19h], 2
0x1800287ae  jb      short loc_1800287EB
0x1800287b0  test    byte ptr [rax+1Ch], 4
0x1800287b4  jz      short loc_1800287EB
0x1800287b6  mov     r8d, ebx
0x1800287b9  lea     rcx, aCannotReadValu_1; "Cannot read value %S.  error %ld"
0x1800287c0  mov     rdx, r15
0x1800287c3  call    WppDbgPrint
0x1800287c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287cf  lea     edx, [rdi+0Dh]
0x1800287d2  mov     dword ptr [rsp+48h+lpcbData], ebx
0x1800287d6  lea     r8, WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids
0x1800287dd  mov     [rsp+48h+phkResult], r15
0x1800287e2  mov     rcx, [rcx+10h]
0x1800287e6  call    WPP_SF_sSl
0x1800287eb  mov     eax, [rbp+Data]
0x1800287ee  jmp     short loc_180028851
0x1800287f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800287f7  lea     rcx, WPP_GLOBAL_Control
0x1800287fe  cmp     rax, rcx
0x180028801  jz      short loc_18002884A
0x180028803  cmp     byte ptr [rax+19h], 4
0x180028807  jb      short loc_18002884A
0x180028809  test    byte ptr [rax+1Ch], 4
0x18002880d  jz      short loc_18002884A
0x18002880f  xor     r8d, r8d
0x180028812  lea     rcx, aTheRegistryVal; "The registry value %S does not exist. U"...
0x180028819  mov     rdx, r15
0x18002881c  call    WppDbgPrint
0x180028821  mov     rcx, cs:WPP_GLOBAL_Control
0x180028828  lea     r8, WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids
0x18002882f  mov     edx, 0Fh
0x180028834  mov     dword ptr [rsp+48h+lpcbData], 0
0x18002883c  mov     [rsp+48h+phkResult], r15
0x180028841  mov     rcx, [rcx+10h]
0x180028845  call    WPP_SF_sSl
0x18002884a  xor     ebx, ebx
0x18002884c  xor     eax, eax
0x18002884e  mov     [rbp+Data], eax
0x180028851  test    ebx, ebx
0x180028853  jnz     loc_1800288F4
0x180028859  jmp     short loc_180028879
0x18002885b  mov     r8d, [rbp+Type]
0x18002885f  mov     r9d, [rbp+cbData]
0x180028863  mov     eax, [rbp+Data]
0x180028866  cmp     r8d, 4
0x18002886a  jnz     short loc_180028887
0x18002886c  cmp     r9d, r8d
0x18002886f  jnz     short loc_180028887
0x180028871  test    eax, eax
0x180028873  jz      short loc_18002887D
0x180028875  cmp     eax, edi
0x180028877  jnz     short loc_180028887
0x180028879  test    eax, eax
0x18002887b  jnz     short loc_18002887F
0x18002887d  xor     edi, edi
0x18002887f  mov     cs:isNTLMv2CompatibilityEnabled, edi
0x180028885  jmp     short loc_1800288F4
0x180028887  mov     rdx, cs:WPP_GLOBAL_Control
0x18002888e  lea     rcx, WPP_GLOBAL_Control
0x180028895  cmp     rdx, rcx
0x180028898  jz      short loc_1800288EF
0x18002889a  cmp     byte ptr [rdx+19h], 2
0x18002889e  jb      short loc_1800288EF
0x1800288a0  test    byte ptr [rdx+1Ch], 4
0x1800288a4  jz      short loc_1800288EF
0x1800288a6  mov     rdx, r15
0x1800288a9  mov     dword ptr [rsp+48h+phkResult], eax
0x1800288ad  lea     rcx, aCannotReadValu; "Cannot read value %S.  Wrong type %ld. "...
0x1800288b4  call    WppDbgPrint
0x1800288b9  mov     eax, [rbp+Data]
0x1800288bc  lea     r8, WPP_e688a2920ba8345c26eb5ab1043ac606_Traceguids
0x1800288c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288ca  mov     edx, 10h
0x1800288cf  mov     [rsp+48h+var_10], eax
0x1800288d3  mov     eax, [rbp+cbData]
0x1800288d6  mov     [rsp+48h+var_18], eax
0x1800288da  mov     eax, [rbp+Type]
0x1800288dd  mov     rcx, [rcx+10h]
0x1800288e1  mov     dword ptr [rsp+48h+lpcbData], eax
0x1800288e5  mov     [rsp+48h+phkResult], r15
0x1800288ea  call    WPP_SF_sSlll
0x1800288ef  mov     ebx, 80070057h
0x1800288f4  mov     rcx, [rbp+hKey]; hKey
0x1800288f8  call    cs:__imp_RegCloseKey
0x1800288fe  mov     eax, ebx
0x180028900  add     rsp, 48h
0x180028904  pop     r15
0x180028906  pop     rdi
0x180028907  pop     rbx
0x180028908  pop     rbp
0x180028909  retn
```
