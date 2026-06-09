# IsDeviceInstallAllowed

- ea: `0x180008d80`
- end: `0x180009409`
- name: `IsDeviceInstallAllowed`
- size: `1673`
- prototype: `_BOOL8 __fastcall(__int64, void *, struct _SP_DEVINFO_DATA *, __int64, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180001da8`

## callees

- `0x1800040d8`
- `0x1800086bc`
- `0x1800087c4`
- `0x18000892c`
- `0x180008bc0`
- `0x180008d80`
- `0x180009410`
- `0x18000a16e`
- `0x18000a1a0`
- `0x18000a230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009091`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e35`
- `SETUPAPI!pSetupStringFromGuid` at `0x180008e67`
- `SETUPAPI!pSetupStringFromGuid` at `0x180008e67`
- `SETUPAPI!SetupGetThreadLogToken` at `0x180008e06`
- `SETUPAPI!SetupGetThreadLogToken` at `0x180008e06`
- `SETUPAPI!SetupWriteTextLog` at `0x180009171`
- `SETUPAPI!SetupWriteTextLog` at `0x180009196`
- `SETUPAPI!SetupWriteTextLog` at `0x1800091b5`
- `SETUPAPI!SetupWriteTextLog` at `0x1800091e0`
- `SETUPAPI!SetupWriteTextLog` at `0x18000920b`
- `SETUPAPI!SetupWriteTextLog` at `0x180009234`
- `SETUPAPI!SetupWriteTextLog` at `0x18000925a`
- `SETUPAPI!SetupWriteTextLog` at `0x18000926c`
- `SETUPAPI!SetupWriteTextLog` at `0x18000929d`
- `SETUPAPI!SetupWriteTextLog` at `0x1800092cb`
- `SETUPAPI!SetupWriteTextLog` at `0x180009317`
- `SETUPAPI!SetupWriteTextLog` at `0x180009332`
- `SETUPAPI!SetupWriteTextLog` at `0x18000935d`
- `SETUPAPI!SetupWriteTextLog` at `0x180009385`
- `SETUPAPI!SetupWriteTextLog` at `0x1800093ad`
- `SETUPAPI!SetupWriteTextLog` at `0x1800093c2`
- `SETUPAPI!SetupWriteTextLog` at `0x1800093f1`
- `SETUPAPI!SetupWriteTextLog` at `0x180009171`
- `SETUPAPI!SetupWriteTextLog` at `0x180009196`
- `SETUPAPI!SetupWriteTextLog` at `0x1800091b5`
- `SETUPAPI!SetupWriteTextLog` at `0x1800091e0`
- `SETUPAPI!SetupWriteTextLog` at `0x18000920b`
- `SETUPAPI!SetupWriteTextLog` at `0x180009234`
- `SETUPAPI!SetupWriteTextLog` at `0x18000925a`
- `SETUPAPI!SetupWriteTextLog` at `0x18000926c`
- `SETUPAPI!SetupWriteTextLog` at `0x18000929d`
- `SETUPAPI!SetupWriteTextLog` at `0x1800092cb`
- `SETUPAPI!SetupWriteTextLog` at `0x180009317`
- `SETUPAPI!SetupWriteTextLog` at `0x180009332`
- `SETUPAPI!SetupWriteTextLog` at `0x18000935d`
- `SETUPAPI!SetupWriteTextLog` at `0x180009385`
- `SETUPAPI!SetupWriteTextLog` at `0x1800093ad`
- `SETUPAPI!SetupWriteTextLog` at `0x1800093c2`
- `SETUPAPI!SetupWriteTextLog` at `0x1800093f1`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180008e2b`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180008e2b`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180008f09`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180008f09`

## string_xrefs

- `0x180008e9c`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x180008f39`: `Software\Policies\Microsoft\Windows\DeviceInstall`
- `0x18000915c`: `{Device installation policy check [%ws]}`
- `0x1800091cf`: `[-] Restricted Hardware or Compatible ID: %ws`
- `0x180009265`: `[*] One or more matching policy restrictions that allow installation overrides the device restrictions:`
- `0x1800092ba`: `[+] Hardware or Compatible ID: %ws`
- `0x18000934c`: `[+] Hardware or Compatible ID: %ws`
- `0x18000930a`: `Device installation policy allows installation of %ws`
- `0x1800093b5`: `Device installation policy will be deferred until a driver is selected for %ws`
- `0x1800093d4`: `{Device installation policy check [%ws] exit(0x%08x)}`

## pseudocode

```c
_BOOL8 __fastcall IsDeviceInstallAllowed(__int64 a1, void *a2, struct _SP_DEVINFO_DATA *a3, __int64 a4, int *a5)
{
  int v7; // r13d
  SP_LOG_TOKEN ThreadLogToken; // rax
  SP_LOG_TOKEN v9; // rbx
  DWORD LastError; // edi
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // esi
  int PolicyValue; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // eax
  int v18; // r14d
  int v19; // r15d
  int *v20; // rax
  int v21; // r12d
  unsigned int v23; // r14d
  unsigned int v24; // r15d
  DWORD PropertyBufferSize[2]; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+44h] [rbp-BCh] BYREF
  BYTE PropertyBuffer[4]; // [rsp+48h] [rbp-B8h] BYREF
  int v29; // [rsp+4Ch] [rbp-B4h]
  int v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+54h] [rbp-ACh]
  BOOL v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+5Ch] [rbp-A4h]
  int *v34; // [rsp+60h] [rbp-A0h]
  __int128 v35; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+78h] [rbp-88h]
  __int128 v37; // [rsp+88h] [rbp-78h]
  char v38[1568]; // [rsp+A0h] [rbp-60h] BYREF
  char v39[1584]; // [rsp+6C0h] [rbp+5C0h] BYREF
  wchar_t pszSrc[40]; // [rsp+CF0h] [rbp+BF0h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+D40h] [rbp+C40h] BYREF
  wchar_t pszDest[200]; // [rsp+ED0h] [rbp+DD0h] BYREF
  wchar_t v43[200]; // [rsp+1060h] [rbp+F60h] BYREF

  v34 = a5;
  memset_0(v38, 0, sizeof(v38));
  memset_0(v39, 0, sizeof(v39));
  v7 = 0;
  v35 = 0;
  v26 = 0;
  v36 = 0;
  v37 = 0;
  ThreadLogToken = SetupGetThreadLogToken();
  *a5 = 0;
  v9 = ThreadLogToken;
  if ( !SetupDiGetDeviceInstanceIdW(a2, a3, DeviceInstanceId, 0xC8u, 0) )
  {
    LastError = GetLastError();
    goto LABEL_32;
  }
  LastError = 0;
  if ( !(unsigned int)IsDevicePolicyExempt(a2, a3) )
  {
    LastError = pSetupStringFromGuid(&a3->ClassGuid, pszSrc, 39);
    if ( !LastError )
    {
      v13 = 0;
      v29 = 0;
      v30 = 0;
      if ( dword_1800117DC )
      {
        PolicyValue = dword_1800117D8;
      }
      else
      {
        PolicyValue = pSetupGetPolicyValue(
                        v11,
                        L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                        v12,
                        L"AllowDenyLayered",
                        0,
                        1);
        dword_1800117D8 = PolicyValue;
        dword_1800117DC = 1;
      }
      v32 = PolicyValue != 0;
      PropertyType = 0;
      *(_DWORD *)PropertyBuffer = 0;
      if ( SetupDiGetDevicePropertyW(a2, a3, &DEVPKEY_Device_Capabilities, &PropertyType, PropertyBuffer, 4u, 0, 0)
        && PropertyType == 7
        && (PropertyBuffer[0] & 4) != 0 )
      {
        if ( dword_1800117E4 )
        {
          v17 = dword_1800117E0;
        }
        else
        {
          v17 = pSetupGetPolicyValue(
                  v15,
                  L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall",
                  v16,
                  L"DenyRemovableDevices",
                  0,
                  1);
          dword_1800117E0 = v17;
          dword_1800117E4 = 1;
        }
        if ( v17 )
          v13 = 1;
      }
      v33 = v13;
      PropertyType = IsDeviceInDeviceIDsList((int)a2, (int)a3, 0, 0, pszDest);
      LOBYTE(v7) = PropertyType != 0;
      if ( (unsigned int)IsDeviceInDeviceIDsList((int)a2, (int)a3, 1, (int)&v26, v43) && v26 )
      {
        *a5 = v26;
        v18 = 1;
        v29 = 1;
        v13 = 1;
      }
      else
      {
        v18 = v29;
      }
      *(_DWORD *)PropertyBuffer = IsDeviceInInstanceIDsList(DeviceInstanceId);
      v19 = *(_DWORD *)PropertyBuffer;
      if ( *(_DWORD *)PropertyBuffer )
        v7 = 1;
      if ( (unsigned int)IsDeviceInInstanceIDsList(DeviceInstanceId) && v26 )
      {
        *a5 = v26;
        v30 = 1;
        v13 = 1;
      }
      v31 = IsClassInDeviceAllowList(pszSrc);
      if ( v31 )
        v7 = 1;
      if ( (unsigned int)IsClassInDeviceDenyList(pszSrc) && v26 )
      {
        v20 = v34;
        v21 = 1;
        v13 = 1;
        *v34 = v26;
      }
      else
      {
        v21 = 0;
        if ( !v13 )
        {
          if ( !v7 )
            goto LABEL_32;
          goto LABEL_50;
        }
        v20 = v34;
      }
      if ( v32 )
      {
        if ( v7 )
        {
          if ( v30 )
          {
            v23 = 0;
          }
          else if ( v18 )
          {
            v23 = 1;
          }
          else
          {
            v23 = 3 - (v21 != 0);
          }
          if ( v19 )
            v24 = 0;
          else
            v24 = 2 - (PropertyType != 0);
          if ( v24 >= v23 )
            LastError = -536870328;
          goto LABEL_51;
        }
LABEL_47:
        LastError = -536870328;
        v23 = 0;
        v24 = 0;
        if ( !*v20 )
          goto LABEL_32;
        goto LABEL_51;
      }
      if ( !v7 )
        goto LABEL_47;
      LastError = -536870328;
LABEL_50:
      v23 = 0;
      v24 = 0;
LABEL_51:
      SetupWriteTextLog(v9, 0x800000u, 0x20005u, "{Device installation policy check [%ws]}", DeviceInstanceId);
      if ( v13 )
      {
        SetupWriteTextLog(v9, 0x800000u, 1u, "The device is explicitly restricted by the following policy settings:");
        if ( v33 )
          SetupWriteTextLog(v9, 0x800000u, 1u, "[-] Removable devices are restricted");
        if ( v29 )
          SetupWriteTextLog(v9, 0x800000u, 1u, "[-] Restricted Hardware or Compatible ID: %ws", v43);
        if ( v30 )
          SetupWriteTextLog(v9, 0x800000u, 1u, "[-] Restricted Instance ID: %ws", DeviceInstanceId);
        if ( v21 )
          SetupWriteTextLog(v9, 0x800000u, 1u, "[-] Restricted setup class of selected driver: %ws", pszSrc);
        if ( v7 )
        {
          if ( v23 > v24 )
          {
            SetupWriteTextLog(
              v9,
              0x800000u,
              2u,
              "[*] One or more matching policy restrictions that allow installation overrides the device restrictions:");
            if ( *(_DWORD *)PropertyBuffer )
              SetupWriteTextLog(v9, 0x800000u, 0x80002u, "[+] Instance ID: %ws", DeviceInstanceId);
            if ( PropertyType && v23 > 1 )
              SetupWriteTextLog(v9, 0x800000u, 0x80002u, "[+] Hardware or Compatible ID: %ws", pszDest);
            if ( v31 && v23 > 2 )
              SetupWriteTextLog(v9, 0x800000u, 0x80002u, "[+] Setup class of selected driver: %ws", pszSrc);
          }
          else
          {
            SetupWriteTextLog(
              v9,
              0x800000u,
              2u,
              "[*] One or more matching policy restrictions that would allow the device have been ignored.");
          }
        }
      }
      else if ( v7 )
      {
        SetupWriteTextLog(v9, 0x800000u, 5u, "Device installation policy allows installation of %ws", DeviceInstanceId);
        SetupWriteTextLog(v9, 0x800000u, 0x80005u, "The device is explicitly allowed by the following policy settings:");
        if ( PropertyType )
          SetupWriteTextLog(v9, 0x800000u, 0x80005u, "[+] Hardware or Compatible ID: %ws", pszDest);
        if ( *(_DWORD *)PropertyBuffer )
          SetupWriteTextLog(v9, 0x800000u, 0x80005u, "[+] Instance ID: %ws", DeviceInstanceId);
        if ( v31 )
          SetupWriteTextLog(v9, 0x800000u, 0x80005u, "[+] Setup class of the selected driver: %ws", pszSrc);
      }
      else
      {
        SetupWriteTextLog(
          v9,
          0x800000u,
          2u,
          "Device installation policy will be deferred until a driver is selected for %ws",
          DeviceInstanceId);
      }
      if ( LastError )
      {
        PropertyBufferSize[0] = LastError;
        SetupWriteTextLog(
          v9,
          0x800000u,
          0x40001u,
          "{Device installation policy check [%ws] exit(0x%08x)}",
          DeviceInstanceId,
          *(_QWORD *)PropertyBufferSize);
      }
      else
      {
        SetupWriteTextLog(
          v9,
          0x800000u,
          0x40005u,
          "{Device installation policy check [%ws] exit(0x%08x)}",
          DeviceInstanceId,
          0);
      }
    }
  }
LABEL_32:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180008d80  mov     [rsp-8+arg_0], rbx
0x180008d85  push    rbp
0x180008d86  push    rsi
0x180008d87  push    rdi
0x180008d88  push    r12
0x180008d8a  push    r13
0x180008d8c  push    r14
0x180008d8e  push    r15
0x180008d90  lea     rbp, [rsp-1100h]
0x180008d98  mov     eax, 1200h
0x180008d9d  call    _alloca_probe
0x180008da2  sub     rsp, rax
0x180008da5  mov     rax, cs:__security_cookie
0x180008dac  xor     rax, rsp
0x180008daf  mov     [rbp+1130h+var_40], rax
0x180008db6  mov     r12, [rbp+1130h+arg_20]
0x180008dbd  lea     rcx, [rbp+1130h+var_1190]; void *
0x180008dc1  mov     r14, r8
0x180008dc4  mov     [rsp+1230h+var_11D0], r12
0x180008dc9  mov     r15, rdx
0x180008dcc  mov     r8d, 620h; Size
0x180008dd2  xor     edx, edx; Val
0x180008dd4  call    memset_0
0x180008dd9  xor     edx, edx; Val
0x180008ddb  lea     rcx, [rbp+1130h+var_B70]; void *
0x180008de2  mov     r8d, 630h; Size
0x180008de8  call    memset_0
0x180008ded  xorps   xmm0, xmm0
0x180008df0  xor     r13d, r13d
0x180008df3  movups  [rsp+1230h+var_11C8], xmm0
0x180008df8  mov     [rsp+1230h+var_11F0], r13d
0x180008dfd  movups  [rsp+1230h+var_11B8], xmm0
0x180008e02  movups  [rbp+1130h+var_11A8], xmm0
0x180008e06  call    cs:__imp_SetupGetThreadLogToken
0x180008e0c  mov     r9d, 0C8h; DeviceInstanceIdSize
0x180008e12  mov     [r12], r13d
0x180008e16  lea     r8, [rbp+1130h+DeviceInstanceId]; DeviceInstanceId
0x180008e1d  mov     [rsp+1230h+RequiredSize], r13; RequiredSize
0x180008e22  mov     rdx, r14; DeviceInfoData
0x180008e25  mov     rcx, r15; DeviceInfoSet
0x180008e28  mov     rbx, rax
0x180008e2b  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x180008e31  test    eax, eax
0x180008e33  jnz     short loc_180008E42
0x180008e35  call    cs:__imp_GetLastError
0x180008e3b  mov     edi, eax
0x180008e3d  jmp     loc_18000908F
0x180008e42  mov     rdx, r14; DeviceInfoData
0x180008e45  mov     rcx, r15; DeviceInfoSet
0x180008e48  mov     edi, r13d
0x180008e4b  call    IsDevicePolicyExempt
0x180008e50  test    eax, eax
0x180008e52  jnz     loc_18000908F
0x180008e58  lea     rcx, [r14+4]
0x180008e5c  lea     r8d, [rax+27h]
0x180008e60  lea     rdx, [rbp+1130h+pszSrc]
0x180008e67  call    cs:__imp_pSetupStringFromGuid
0x180008e6d  mov     edi, eax
0x180008e6f  test    eax, eax
0x180008e71  jnz     loc_18000908F
0x180008e77  cmp     cs:dword_1800117DC, r13d
0x180008e7e  mov     esi, r13d
0x180008e81  mov     [rsp+1230h+var_11E4], r13d
0x180008e86  mov     [rsp+1230h+var_11E0], r13d
0x180008e8b  jnz     short loc_180008EBF
0x180008e8d  mov     [rsp+1230h+PropertyBufferSize], 1
0x180008e95  lea     r9, aAllowdenylayer; "AllowDenyLayered"
0x180008e9c  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008ea3  mov     dword ptr [rsp+1230h+RequiredSize], r13d
0x180008ea8  call    pSetupGetPolicyValue
0x180008ead  mov     cs:dword_1800117D8, eax
0x180008eb3  mov     cs:dword_1800117DC, 1
0x180008ebd  jmp     short loc_180008EC5
0x180008ebf  mov     eax, cs:dword_1800117D8
0x180008ec5  test    eax, eax
0x180008ec7  mov     [rsp+1230h+Flags], r13d; Flags
0x180008ecc  mov     ecx, r13d
0x180008ecf  mov     [rsp+1230h+var_1200], r13; RequiredSize
0x180008ed4  setnz   cl
0x180008ed7  mov     [rsp+1230h+PropertyBufferSize], 4; PropertyBufferSize
0x180008edf  mov     [rsp+1230h+var_11D8], ecx
0x180008ee3  lea     rax, [rsp+1230h+PropertyBuffer]
0x180008ee8  mov     rcx, r15; DeviceInfoSet
0x180008eeb  mov     [rsp+1230h+PropertyType], r13d
0x180008ef0  lea     r9, [rsp+1230h+PropertyType]; PropertyType
0x180008ef5  mov     dword ptr [rsp+1230h+PropertyBuffer], r13d
0x180008efa  lea     r8, DEVPKEY_Device_Capabilities; PropertyKey
0x180008f01  mov     [rsp+1230h+RequiredSize], rax; PropertyBuffer
0x180008f06  mov     rdx, r14; DeviceInfoData
0x180008f09  call    cs:__imp_SetupDiGetDevicePropertyW
0x180008f0f  test    eax, eax
0x180008f11  jz      short loc_180008F6C
0x180008f13  cmp     [rsp+1230h+PropertyType], 7
0x180008f18  jnz     short loc_180008F6C
0x180008f1a  test    [rsp+1230h+PropertyBuffer], 4
0x180008f1f  jz      short loc_180008F6C
0x180008f21  cmp     cs:dword_1800117E4, r13d
0x180008f28  jnz     short loc_180008F5C
0x180008f2a  mov     [rsp+1230h+PropertyBufferSize], 1
0x180008f32  lea     r9, aDenyremovabled; "DenyRemovableDevices"
0x180008f39  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008f40  mov     dword ptr [rsp+1230h+RequiredSize], r13d
0x180008f45  call    pSetupGetPolicyValue
0x180008f4a  mov     cs:dword_1800117E0, eax
0x180008f50  mov     cs:dword_1800117E4, 1
0x180008f5a  jmp     short loc_180008F62
0x180008f5c  mov     eax, cs:dword_1800117E0
0x180008f62  test    eax, eax
0x180008f64  mov     eax, 1
0x180008f69  cmovnz  esi, eax
0x180008f6c  lea     rax, [rbp+1130h+pszDest]
0x180008f73  mov     [rsp+1230h+var_11D4], esi
0x180008f77  xor     r9d, r9d; int
0x180008f7a  mov     [rsp+1230h+RequiredSize], rax; pszDest
0x180008f7f  xor     r8d, r8d; int
0x180008f82  mov     rdx, r14; int
0x180008f85  mov     rcx, r15; int
0x180008f88  call    IsDeviceInDeviceIDsList
0x180008f8d  test    eax, eax
0x180008f8f  mov     [rsp+1230h+PropertyType], eax
0x180008f93  lea     rax, [rbp+1130h+var_1D0]
0x180008f9a  mov     r8d, 1; int
0x180008fa0  lea     r9, [rsp+1230h+var_11F0]; int
0x180008fa5  mov     [rsp+1230h+RequiredSize], rax; pszDest
0x180008faa  mov     rdx, r14; int
0x180008fad  mov     rcx, r15; int
0x180008fb0  setnz   r13b
0x180008fb4  call    IsDeviceInDeviceIDsList
0x180008fb9  test    eax, eax
0x180008fbb  jz      short loc_180008FD9
0x180008fbd  mov     eax, [rsp+1230h+var_11F0]
0x180008fc1  test    eax, eax
0x180008fc3  jz      short loc_180008FD9
0x180008fc5  mov     ecx, 1
0x180008fca  mov     [r12], eax
0x180008fce  mov     r14d, ecx
0x180008fd1  mov     [rsp+1230h+var_11E4], ecx
0x180008fd5  mov     esi, ecx
0x180008fd7  jmp     short loc_180008FDE
0x180008fd9  mov     r14d, [rsp+1230h+var_11E4]
0x180008fde  xor     r8d, r8d
0x180008fe1  lea     rcx, [rbp+1130h+DeviceInstanceId]; pszSrc
0x180008fe8  xor     edx, edx
0x180008fea  call    IsDeviceInInstanceIDsList
0x180008fef  test    eax, eax
0x180008ff1  mov     dword ptr [rsp+1230h+PropertyBuffer], eax
0x180008ff5  mov     r15d, eax
0x180008ff8  lea     r8, [rsp+1230h+var_11F0]
0x180008ffd  mov     eax, 1
0x180009002  lea     rcx, [rbp+1130h+DeviceInstanceId]; pszSrc
0x180009009  mov     edx, eax
0x18000900b  cmovnz  r13d, eax
0x18000900f  call    IsDeviceInInstanceIDsList
0x180009014  test    eax, eax
0x180009016  jz      short loc_18000902F
0x180009018  mov     ecx, [rsp+1230h+var_11F0]
0x18000901c  test    ecx, ecx
0x18000901e  jz      short loc_18000902F
0x180009020  mov     eax, 1
0x180009025  mov     [r12], ecx
0x180009029  mov     [rsp+1230h+var_11E0], eax
0x18000902d  mov     esi, eax
0x18000902f  lea     rcx, [rbp+1130h+pszSrc]; pszSrc
0x180009036  call    IsClassInDeviceAllowList
0x18000903b  test    eax, eax
0x18000903d  mov     [rsp+1230h+var_11DC], eax
0x180009041  mov     eax, 1
0x180009046  lea     rdx, [rsp+1230h+var_11F0]
0x18000904b  lea     rcx, [rbp+1130h+pszSrc]; pszSrc
0x180009052  cmovnz  r13d, eax
0x180009056  call    IsClassInDeviceDenyList
0x18000905b  xor     edx, edx
0x18000905d  test    eax, eax
0x18000905f  jz      short loc_18000907C
0x180009061  mov     ecx, [rsp+1230h+var_11F0]
0x180009065  test    ecx, ecx
0x180009067  jz      short loc_18000907C
0x180009069  mov     rax, [rsp+1230h+var_11D0]
0x18000906e  lea     r8d, [rdx+1]
0x180009072  mov     r12d, r8d
0x180009075  mov     esi, r8d
0x180009078  mov     [rax], ecx
0x18000907a  jmp     short loc_1800090D4
0x18000907c  mov     r12d, edx
0x18000907f  test    esi, esi
0x180009081  jnz     short loc_1800090C9
0x180009083  test    r13d, r13d
0x180009086  jnz     loc_18000914A
0x18000908c  xor     r13d, r13d
0x18000908f  mov     ecx, edi; dwErrCode
0x180009091  call    cs:__imp_SetLastError
0x180009097  test    edi, edi
0x180009099  mov     eax, r13d
0x18000909c  setz    al
0x18000909f  mov     rcx, [rbp+1130h+var_40]
0x1800090a6  xor     rcx, rsp; StackCookie
0x1800090a9  call    __security_check_cookie
0x1800090ae  mov     rbx, [rsp+1230h+arg_0]
0x1800090b6  add     rsp, 1200h
0x1800090bd  pop     r15
0x1800090bf  pop     r14
0x1800090c1  pop     r13
0x1800090c3  pop     r12
0x1800090c5  pop     rdi
0x1800090c6  pop     rsi
0x1800090c7  pop     rbp
0x1800090c8  retn
0x1800090c9  mov     rax, [rsp+1230h+var_11D0]
0x1800090ce  mov     r8d, 1
0x1800090d4  cmp     [rsp+1230h+var_11D8], edx
0x1800090d8  jz      short loc_180009123
0x1800090da  test    r13d, r13d
0x1800090dd  jz      short loc_180009128
0x1800090df  cmp     [rsp+1230h+var_11E0], edx
0x1800090e3  jz      short loc_1800090EA
0x1800090e5  mov     r14d, edx
0x1800090e8  jmp     short loc_180009100
0x1800090ea  test    r14d, r14d
0x1800090ed  jz      short loc_1800090F4
0x1800090ef  mov     r14d, r8d
0x1800090f2  jmp     short loc_180009100
0x1800090f4  mov     eax, r12d
0x1800090f7  neg     eax
0x1800090f9  sbb     r14d, r14d
0x1800090fc  add     r14d, 3
0x180009100  test    r15d, r15d
0x180009103  jz      short loc_18000910A
0x180009105  mov     r15d, edx
0x180009108  jmp     short loc_180009117
0x18000910a  mov     eax, [rsp+1230h+PropertyType]
0x18000910e  neg     eax
0x180009110  sbb     r15d, r15d
0x180009113  add     r15d, 2
0x180009117  cmp     r15d, r14d
0x18000911a  jb      short loc_180009150
0x18000911c  mov     edi, 0E0000248h
0x180009121  jmp     short loc_180009150
0x180009123  test    r13d, r13d
0x180009126  jnz     short loc_180009145
0x180009128  mov     edi, 0E0000248h
0x18000912d  test    esi, esi
0x18000912f  jz      loc_18000908C
0x180009135  mov     r14d, edx
0x180009138  mov     r15d, edx
0x18000913b  cmp     [rax], edx
0x18000913d  jz      loc_18000908C
0x180009143  jmp     short loc_180009150
0x180009145  mov     edi, 0E0000248h
0x18000914a  mov     r14d, edx
0x18000914d  mov     r15d, edx
0x180009150  lea     rax, [rbp+1130h+DeviceInstanceId]
0x180009157  mov     edx, 800000h; Category
0x18000915c  lea     r9, aDeviceInstalla_5; "{Device installation policy check [%ws]"...
0x180009163  mov     [rsp+1230h+RequiredSize], rax
0x180009168  mov     r8d, 20005h; Flags
0x18000916e  mov     rcx, rbx; LogToken
0x180009171  call    cs:__imp_SetupWriteTextLog
0x180009177  test    esi, esi
0x180009179  mov     rcx, rbx; LogToken
0x18000917c  mov     esi, 800000h
0x180009181  mov     edx, esi; Category
0x180009183  jz      loc_1800092F5
0x180009189  lea     r9, aTheDeviceIsExp; "The device is explicitly restricted by "...
0x180009190  mov     r8d, 1; Flags
0x180009196  call    cs:__imp_SetupWriteTextLog
0x18000919c  cmp     [rsp+1230h+var_11D4], 0
0x1800091a1  jz      short loc_1800091BB
0x1800091a3  lea     r9, aRemovableDevic; "[-] Removable devices are restricted"
0x1800091aa  mov     r8d, 1; Flags
0x1800091b0  mov     edx, esi; Category
0x1800091b2  mov     rcx, rbx; LogToken
0x1800091b5  call    cs:__imp_SetupWriteTextLog
0x1800091bb  cmp     [rsp+1230h+var_11E4], 0
0x1800091c0  jz      short loc_1800091E6
0x1800091c2  lea     rax, [rbp+1130h+var_1D0]
0x1800091c9  mov     r8d, 1; Flags
0x1800091cf  lea     r9, aRestrictedHard; "[-] Restricted Hardware or Compatible I"...
0x1800091d6  mov     [rsp+1230h+RequiredSize], rax
0x1800091db  mov     edx, esi; Category
0x1800091dd  mov     rcx, rbx; LogToken
0x1800091e0  call    cs:__imp_SetupWriteTextLog
0x1800091e6  cmp     [rsp+1230h+var_11E0], 0
0x1800091eb  jz      short loc_180009211
0x1800091ed  lea     rax, [rbp+1130h+DeviceInstanceId]
0x1800091f4  mov     r8d, 1; Flags
0x1800091fa  lea     r9, aRestrictedInst; "[-] Restricted Instance ID: %ws"
0x180009201  mov     [rsp+1230h+RequiredSize], rax
0x180009206  mov     edx, esi; Category
0x180009208  mov     rcx, rbx; LogToken
0x18000920b  call    cs:__imp_SetupWriteTextLog
0x180009211  test    r12d, r12d
0x180009214  jz      short loc_18000923A
0x180009216  lea     rax, [rbp+1130h+pszSrc]
0x18000921d  mov     r8d, 1; Flags
0x180009223  lea     r9, aRestrictedSetu; "[-] Restricted setup class of selected "...
0x18000922a  mov     [rsp+1230h+RequiredSize], rax
0x18000922f  mov     edx, esi; Category
0x180009231  mov     rcx, rbx; LogToken
0x180009234  call    cs:__imp_SetupWriteTextLog
0x18000923a  test    r13d, r13d
  ... truncated ...
```
