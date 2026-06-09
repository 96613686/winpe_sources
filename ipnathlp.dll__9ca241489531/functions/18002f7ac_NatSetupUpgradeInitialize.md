# NatSetupUpgradeInitialize

- ea: `0x18002f7ac`
- end: `0x18002fa88`
- name: `NatSetupUpgradeInitialize`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002f0f8`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18002f7ac`
- `0x180036db0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f8d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f8d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f9d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f9d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa46`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f856`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f856`

## string_xrefs

- `0x18002f80c`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Setup`
- `0x18002f8cf`: `ServiceUpgrade`
- `0x18002f9be`: `ServiceUpgrade`

## pseudocode

```c
__int64 NatSetupUpgradeInitialize()
{
  unsigned int v0; // eax
  signed int v1; // ebx
  PVOID *v2; // rcx
  unsigned int v3; // eax
  unsigned int v4; // edi
  __int64 v5; // rdx
  LSTATUS v6; // eax
  DWORD cbData; // [rsp+90h] [rbp+38h] BYREF
  int Data; // [rsp+98h] [rbp+40h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9005bb16e893322af2e15a9898236f66_Traceguids);
  }
  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Setup",
         0,
         0,
         0,
         3u,
         0,
         &hKey,
         0);
  v1 = v0;
  if ( !v0 )
  {
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"ServiceUpgrade", 0, &Type, (LPBYTE)&Data, &cbData);
    v4 = v3;
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9005bb16e893322af2e15a9898236f66_Traceguids, v3);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 == 2 )
    {
      if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x200) != 0 && *((_BYTE *)v2 + 25) >= 5u )
        WPP_SF_(v2[2], 13, WPP_9005bb16e893322af2e15a9898236f66_Traceguids);
      v1 = FwSetupICSPortsUpgrade(1);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9005bb16e893322af2e15a9898236f66_Traceguids);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v1 >= 0 )
      {
        v6 = RegSetValueExW(hKey, L"ServiceUpgrade", 0, 4u, (const BYTE *)&Data, 4u);
        if ( !v6 )
          goto LABEL_44;
        if ( v6 > 0 )
          v1 = (unsigned __int16)v6 | 0x80070000;
        else
          v1 = v6;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_45;
        }
        v5 = 16;
      }
      else
      {
        if ( v2 == &WPP_GLOBAL_Control || (*((_DWORD *)v2 + 7) & 0x200) == 0 || *((_BYTE *)v2 + 25) < 2u )
          goto LABEL_45;
        v5 = 15;
      }
      WPP_SF_d(v2[2], v5, WPP_9005bb16e893322af2e15a9898236f66_Traceguids, (unsigned int)v1);
    }
    else
    {
      v1 = 0;
      if ( !v4 || v2 == &WPP_GLOBAL_Control || (*((_DWORD *)v2 + 7) & 0x200) == 0 || *((_BYTE *)v2 + 25) < 3u )
        goto LABEL_45;
      WPP_SF_d(v2[2], 17, WPP_9005bb16e893322af2e15a9898236f66_Traceguids, v4);
    }
LABEL_44:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9005bb16e893322af2e15a9898236f66_Traceguids, v0);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 > 0 )
    v1 = (unsigned __int16)v1 | 0x80070000;
LABEL_45:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x200) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    WPP_SF_d(v2[2], 18, WPP_9005bb16e893322af2e15a9898236f66_Traceguids, (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18002f7ac  push    rbp
0x18002f7ae  push    rbx
0x18002f7af  push    rdi
0x18002f7b0  push    r12
0x18002f7b2  push    r14
0x18002f7b4  push    r15
0x18002f7b6  mov     rbp, rsp
0x18002f7b9  sub     rsp, 58h
0x18002f7bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7c4  lea     r15, WPP_GLOBAL_Control
0x18002f7cb  lea     r12, WPP_9005bb16e893322af2e15a9898236f66_Traceguids
0x18002f7d2  mov     r14d, 200h
0x18002f7d8  cmp     rcx, r15
0x18002f7db  jz      short loc_18002F7FA
0x18002f7dd  test    [rcx+1Ch], r14d
0x18002f7e1  jz      short loc_18002F7FA
0x18002f7e3  cmp     byte ptr [rcx+19h], 6
0x18002f7e7  jb      short loc_18002F7FA
0x18002f7e9  mov     rcx, [rcx+10h]
0x18002f7ed  mov     edx, 0Ah
0x18002f7f2  mov     r8, r12
0x18002f7f5  call    WPP_SF_
0x18002f7fa  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18002f803  lea     rax, [rbp+hKey]
0x18002f807  mov     [rsp+58h+phkResult], rax; phkResult
0x18002f80c  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18002f813  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002f81c  xor     r9d, r9d; lpClass
0x18002f81f  mov     [rsp+58h+samDesired], 3; samDesired
0x18002f827  xor     r8d, r8d; Reserved
0x18002f82a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f831  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002f839  mov     [rbp+hKey], 0
0x18002f841  mov     [rbp+Type], 0
0x18002f848  mov     [rbp+cbData], 0
0x18002f84f  mov     [rbp+Data], 0
0x18002f856  call    cs:__imp_RegCreateKeyExW
0x18002f85c  mov     ebx, eax
0x18002f85e  test    eax, eax
0x18002f860  jz      short loc_18002F8AB
0x18002f862  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f869  cmp     rcx, r15
0x18002f86c  jz      short loc_18002F895
0x18002f86e  test    [rcx+1Ch], r14d
0x18002f872  jz      short loc_18002F895
0x18002f874  cmp     byte ptr [rcx+19h], 2
0x18002f878  jb      short loc_18002F895
0x18002f87a  mov     rcx, [rcx+10h]
0x18002f87e  mov     edx, 0Bh
0x18002f883  mov     r9d, eax
0x18002f886  mov     r8, r12
0x18002f889  call    WPP_SF_d
0x18002f88e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f895  test    ebx, ebx
0x18002f897  jle     loc_18002FA3A
0x18002f89d  movzx   ebx, bx
0x18002f8a0  or      ebx, 80070000h
0x18002f8a6  jmp     loc_18002FA3A
0x18002f8ab  mov     rcx, [rbp+hKey]; hKey
0x18002f8af  lea     rax, [rbp+cbData]
0x18002f8b3  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x18002f8b8  lea     r9, [rbp+Type]; lpType
0x18002f8bc  lea     rax, [rbp+Data]
0x18002f8c0  mov     [rbp+cbData], 4
0x18002f8c7  xor     r8d, r8d; lpReserved
0x18002f8ca  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18002f8cf  lea     rdx, aServiceupgrade; "ServiceUpgrade"
0x18002f8d6  call    cs:__imp_RegQueryValueExW
0x18002f8dc  mov     edi, eax
0x18002f8de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8e5  cmp     rcx, r15
0x18002f8e8  jz      short loc_18002F911
0x18002f8ea  test    [rcx+1Ch], r14d
0x18002f8ee  jz      short loc_18002F911
0x18002f8f0  cmp     byte ptr [rcx+19h], 5
0x18002f8f4  jb      short loc_18002F911
0x18002f8f6  mov     rcx, [rcx+10h]
0x18002f8fa  mov     edx, 0Ch
0x18002f8ff  mov     r9d, eax
0x18002f902  mov     r8, r12
0x18002f905  call    WPP_SF_d
0x18002f90a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f911  cmp     edi, 2
0x18002f914  jnz     loc_18002FA0A
0x18002f91a  cmp     rcx, r15
0x18002f91d  jz      short loc_18002F93A
0x18002f91f  test    [rcx+1Ch], r14d
0x18002f923  jz      short loc_18002F93A
0x18002f925  cmp     byte ptr [rcx+19h], 5
0x18002f929  jb      short loc_18002F93A
0x18002f92b  mov     rcx, [rcx+10h]
0x18002f92f  lea     edx, [rdi+0Bh]
0x18002f932  mov     r8, r12
0x18002f935  call    WPP_SF_
0x18002f93a  mov     ecx, 1
0x18002f93f  call    FwSetupICSPortsUpgrade
0x18002f944  mov     ebx, eax
0x18002f946  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f94d  cmp     rcx, r15
0x18002f950  jz      short loc_18002F976
0x18002f952  test    [rcx+1Ch], r14d
0x18002f956  jz      short loc_18002F976
0x18002f958  cmp     byte ptr [rcx+19h], 5
0x18002f95c  jb      short loc_18002F976
0x18002f95e  mov     rcx, [rcx+10h]
0x18002f962  mov     edx, 0Eh
0x18002f967  mov     r8, r12
0x18002f96a  call    WPP_SF_
0x18002f96f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f976  test    ebx, ebx
0x18002f978  jns     short loc_18002F9B0
0x18002f97a  cmp     rcx, r15
0x18002f97d  jz      loc_18002FA3A
0x18002f983  test    [rcx+1Ch], r14d
0x18002f987  jz      loc_18002FA3A
0x18002f98d  cmp     byte ptr [rcx+19h], 2
0x18002f991  jb      loc_18002FA3A
0x18002f997  mov     edx, 0Fh
0x18002f99c  mov     rcx, [rcx+10h]
0x18002f9a0  mov     r9d, ebx
0x18002f9a3  mov     r8, r12
0x18002f9a6  call    WPP_SF_d
0x18002f9ab  jmp     loc_18002FA33
0x18002f9b0  mov     rcx, [rbp+hKey]; hKey
0x18002f9b4  lea     rax, [rbp+Data]
0x18002f9b8  mov     r9d, 4; dwType
0x18002f9be  lea     rdx, aServiceupgrade; "ServiceUpgrade"
0x18002f9c5  mov     [rsp+58h+samDesired], r9d; cbData
0x18002f9ca  xor     r8d, r8d; Reserved
0x18002f9cd  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18002f9d2  call    cs:__imp_RegSetValueExW
0x18002f9d8  test    eax, eax
0x18002f9da  jz      short loc_18002FA33
0x18002f9dc  jg      short loc_18002F9E2
0x18002f9de  mov     ebx, eax
0x18002f9e0  jmp     short loc_18002F9EB
0x18002f9e2  movzx   ebx, ax
0x18002f9e5  or      ebx, 80070000h
0x18002f9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9f2  cmp     rcx, r15
0x18002f9f5  jz      short loc_18002FA3A
0x18002f9f7  test    [rcx+1Ch], r14d
0x18002f9fb  jz      short loc_18002FA3A
0x18002f9fd  cmp     byte ptr [rcx+19h], 2
0x18002fa01  jb      short loc_18002FA3A
0x18002fa03  mov     edx, 10h
0x18002fa08  jmp     short loc_18002F99C
0x18002fa0a  xor     ebx, ebx
0x18002fa0c  test    edi, edi
0x18002fa0e  jz      short loc_18002FA3A
0x18002fa10  cmp     rcx, r15
0x18002fa13  jz      short loc_18002FA3A
0x18002fa15  test    [rcx+1Ch], r14d
0x18002fa19  jz      short loc_18002FA3A
0x18002fa1b  cmp     byte ptr [rcx+19h], 3
0x18002fa1f  jb      short loc_18002FA3A
0x18002fa21  mov     rcx, [rcx+10h]
0x18002fa25  lea     edx, [rbx+11h]
0x18002fa28  mov     r9d, edi
0x18002fa2b  mov     r8, r12
0x18002fa2e  call    WPP_SF_d
0x18002fa33  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa3a  mov     rax, [rbp+hKey]
0x18002fa3e  test    rax, rax
0x18002fa41  jz      short loc_18002FA53
0x18002fa43  mov     rcx, rax; hKey
0x18002fa46  call    cs:__imp_RegCloseKey
0x18002fa4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa53  cmp     rcx, r15
0x18002fa56  jz      short loc_18002FA78
0x18002fa58  test    [rcx+1Ch], r14d
0x18002fa5c  jz      short loc_18002FA78
0x18002fa5e  cmp     byte ptr [rcx+19h], 6
0x18002fa62  jb      short loc_18002FA78
0x18002fa64  mov     rcx, [rcx+10h]
0x18002fa68  mov     edx, 12h
0x18002fa6d  mov     r9d, ebx
0x18002fa70  mov     r8, r12
0x18002fa73  call    WPP_SF_d
0x18002fa78  mov     eax, ebx
0x18002fa7a  add     rsp, 58h
0x18002fa7e  pop     r15
0x18002fa80  pop     r14
0x18002fa82  pop     r12
0x18002fa84  pop     rdi
0x18002fa85  pop     rbx
0x18002fa86  pop     rbp
0x18002fa87  retn
```
