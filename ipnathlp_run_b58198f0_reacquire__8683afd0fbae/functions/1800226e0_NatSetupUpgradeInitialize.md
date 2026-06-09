# NatSetupUpgradeInitialize

- ea: `0x1800226e0`
- end: `0x1800229d5`
- name: `NatSetupUpgradeInitialize`
- size: `757`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180021fb8`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800226e0`
- `0x180039a80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022810`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022810`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180022912`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180022912`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002298c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002298c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002278a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002278a`

## string_xrefs

- `0x180022740`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Setup`
- `0x180022809`: `ServiceUpgrade`
- `0x1800228fe`: `ServiceUpgrade`

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
0x1800226e0  push    rbp
0x1800226e2  push    rbx
0x1800226e3  push    rdi
0x1800226e4  push    r12
0x1800226e6  push    r14
0x1800226e8  push    r15
0x1800226ea  mov     rbp, rsp
0x1800226ed  sub     rsp, 58h
0x1800226f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226f8  lea     r15, WPP_GLOBAL_Control
0x1800226ff  lea     r12, WPP_9005bb16e893322af2e15a9898236f66_Traceguids
0x180022706  mov     r14d, 200h
0x18002270c  cmp     rcx, r15
0x18002270f  jz      short loc_18002272E
0x180022711  test    [rcx+1Ch], r14d
0x180022715  jz      short loc_18002272E
0x180022717  cmp     byte ptr [rcx+19h], 6
0x18002271b  jb      short loc_18002272E
0x18002271d  mov     rcx, [rcx+10h]
0x180022721  mov     edx, 0Ah
0x180022726  mov     r8, r12
0x180022729  call    WPP_SF_
0x18002272e  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180022737  lea     rax, [rbp+hKey]
0x18002273b  mov     [rsp+58h+phkResult], rax; phkResult
0x180022740  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x180022747  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180022750  xor     r9d, r9d; lpClass
0x180022753  mov     [rsp+58h+samDesired], 3; samDesired
0x18002275b  xor     r8d, r8d; Reserved
0x18002275e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022765  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002276d  mov     [rbp+hKey], 0
0x180022775  mov     [rbp+Type], 0
0x18002277c  mov     [rbp+cbData], 0
0x180022783  mov     [rbp+Data], 0
0x18002278a  call    cs:__imp_RegCreateKeyExW
0x180022791  nop     dword ptr [rax+rax+00h]
0x180022796  mov     ebx, eax
0x180022798  test    eax, eax
0x18002279a  jz      short loc_1800227E5
0x18002279c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227a3  cmp     rcx, r15
0x1800227a6  jz      short loc_1800227CF
0x1800227a8  test    [rcx+1Ch], r14d
0x1800227ac  jz      short loc_1800227CF
0x1800227ae  cmp     byte ptr [rcx+19h], 2
0x1800227b2  jb      short loc_1800227CF
0x1800227b4  mov     rcx, [rcx+10h]
0x1800227b8  mov     edx, 0Bh
0x1800227bd  mov     r9d, eax
0x1800227c0  mov     r8, r12
0x1800227c3  call    WPP_SF_d
0x1800227c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227cf  test    ebx, ebx
0x1800227d1  jle     loc_180022980
0x1800227d7  movzx   ebx, bx
0x1800227da  or      ebx, 80070000h
0x1800227e0  jmp     loc_180022980
0x1800227e5  mov     rcx, [rbp+hKey]; hKey
0x1800227e9  lea     rax, [rbp+cbData]
0x1800227ed  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x1800227f2  lea     r9, [rbp+Type]; lpType
0x1800227f6  lea     rax, [rbp+Data]
0x1800227fa  mov     [rbp+cbData], 4
0x180022801  xor     r8d, r8d; lpReserved
0x180022804  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180022809  lea     rdx, aServiceupgrade; "ServiceUpgrade"
0x180022810  call    cs:__imp_RegQueryValueExW
0x180022817  nop     dword ptr [rax+rax+00h]
0x18002281c  mov     edi, eax
0x18002281e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022825  cmp     rcx, r15
0x180022828  jz      short loc_180022851
0x18002282a  test    [rcx+1Ch], r14d
0x18002282e  jz      short loc_180022851
0x180022830  cmp     byte ptr [rcx+19h], 5
0x180022834  jb      short loc_180022851
0x180022836  mov     rcx, [rcx+10h]
0x18002283a  mov     edx, 0Ch
0x18002283f  mov     r9d, eax
0x180022842  mov     r8, r12
0x180022845  call    WPP_SF_d
0x18002284a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022851  cmp     edi, 2
0x180022854  jnz     loc_180022950
0x18002285a  cmp     rcx, r15
0x18002285d  jz      short loc_18002287A
0x18002285f  test    [rcx+1Ch], r14d
0x180022863  jz      short loc_18002287A
0x180022865  cmp     byte ptr [rcx+19h], 5
0x180022869  jb      short loc_18002287A
0x18002286b  mov     rcx, [rcx+10h]
0x18002286f  lea     edx, [rdi+0Bh]
0x180022872  mov     r8, r12
0x180022875  call    WPP_SF_
0x18002287a  mov     ecx, 1
0x18002287f  call    FwSetupICSPortsUpgrade
0x180022884  mov     ebx, eax
0x180022886  mov     rcx, cs:WPP_GLOBAL_Control
0x18002288d  cmp     rcx, r15
0x180022890  jz      short loc_1800228B6
0x180022892  test    [rcx+1Ch], r14d
0x180022896  jz      short loc_1800228B6
0x180022898  cmp     byte ptr [rcx+19h], 5
0x18002289c  jb      short loc_1800228B6
0x18002289e  mov     rcx, [rcx+10h]
0x1800228a2  mov     edx, 0Eh
0x1800228a7  mov     r8, r12
0x1800228aa  call    WPP_SF_
0x1800228af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228b6  test    ebx, ebx
0x1800228b8  jns     short loc_1800228F0
0x1800228ba  cmp     rcx, r15
0x1800228bd  jz      loc_180022980
0x1800228c3  test    [rcx+1Ch], r14d
0x1800228c7  jz      loc_180022980
0x1800228cd  cmp     byte ptr [rcx+19h], 2
0x1800228d1  jb      loc_180022980
0x1800228d7  mov     edx, 0Fh
0x1800228dc  mov     rcx, [rcx+10h]
0x1800228e0  mov     r9d, ebx
0x1800228e3  mov     r8, r12
0x1800228e6  call    WPP_SF_d
0x1800228eb  jmp     loc_180022979
0x1800228f0  mov     rcx, [rbp+hKey]; hKey
0x1800228f4  lea     rax, [rbp+Data]
0x1800228f8  mov     r9d, 4; dwType
0x1800228fe  lea     rdx, aServiceupgrade; "ServiceUpgrade"
0x180022905  mov     [rsp+58h+samDesired], r9d; cbData
0x18002290a  xor     r8d, r8d; Reserved
0x18002290d  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180022912  call    cs:__imp_RegSetValueExW
0x180022919  nop     dword ptr [rax+rax+00h]
0x18002291e  test    eax, eax
0x180022920  jz      short loc_180022979
0x180022922  jg      short loc_180022928
0x180022924  mov     ebx, eax
0x180022926  jmp     short loc_180022931
0x180022928  movzx   ebx, ax
0x18002292b  or      ebx, 80070000h
0x180022931  mov     rcx, cs:WPP_GLOBAL_Control
0x180022938  cmp     rcx, r15
0x18002293b  jz      short loc_180022980
0x18002293d  test    [rcx+1Ch], r14d
0x180022941  jz      short loc_180022980
0x180022943  cmp     byte ptr [rcx+19h], 2
0x180022947  jb      short loc_180022980
0x180022949  mov     edx, 10h
0x18002294e  jmp     short loc_1800228DC
0x180022950  xor     ebx, ebx
0x180022952  test    edi, edi
0x180022954  jz      short loc_180022980
0x180022956  cmp     rcx, r15
0x180022959  jz      short loc_180022980
0x18002295b  test    [rcx+1Ch], r14d
0x18002295f  jz      short loc_180022980
0x180022961  cmp     byte ptr [rcx+19h], 3
0x180022965  jb      short loc_180022980
0x180022967  mov     rcx, [rcx+10h]
0x18002296b  lea     edx, [rbx+11h]
0x18002296e  mov     r9d, edi
0x180022971  mov     r8, r12
0x180022974  call    WPP_SF_d
0x180022979  mov     rcx, cs:WPP_GLOBAL_Control
0x180022980  mov     rax, [rbp+hKey]
0x180022984  test    rax, rax
0x180022987  jz      short loc_18002299F
0x180022989  mov     rcx, rax; hKey
0x18002298c  call    cs:__imp_RegCloseKey
0x180022993  nop     dword ptr [rax+rax+00h]
0x180022998  mov     rcx, cs:WPP_GLOBAL_Control
0x18002299f  cmp     rcx, r15
0x1800229a2  jz      short loc_1800229C4
0x1800229a4  test    [rcx+1Ch], r14d
0x1800229a8  jz      short loc_1800229C4
0x1800229aa  cmp     byte ptr [rcx+19h], 6
0x1800229ae  jb      short loc_1800229C4
0x1800229b0  mov     rcx, [rcx+10h]
0x1800229b4  mov     edx, 12h
0x1800229b9  mov     r9d, ebx
0x1800229bc  mov     r8, r12
0x1800229bf  call    WPP_SF_d
0x1800229c4  mov     eax, ebx
0x1800229c6  add     rsp, 58h
0x1800229ca  pop     r15
0x1800229cc  pop     r14
0x1800229ce  pop     r12
0x1800229d0  pop     rdi
0x1800229d1  pop     rbx
0x1800229d2  pop     rbp
0x1800229d3  retn
```
