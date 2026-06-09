# SetTunnelConfigParams

- ea: `0x180028a18`
- end: `0x180028d1f`
- name: `SetTunnelConfigParams`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180027c90`

## callees

- `0x180028a18`
- `0x180030648`
- `0x180031178`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028c88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028ab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028c88`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180028c5a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180028c5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028bdf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028c1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028c79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028bdf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028c1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028c79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028a90`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028b20`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028a90`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028b20`
- `sstpcfg!SetSstpConfiguration` at `0x180028cfa`
- `sstpcfg!SetSstpConfiguration` at `0x180028cfa`

## string_xrefs

- `0x180028b19`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\L2TP`
- `0x180028a89`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\Ikev2`

## pseudocode

```c
__int64 __fastcall SetTunnelConfigParams(__int64 a1, char *a2, char a3)
{
  char v4; // si
  unsigned int v6; // ebx
  HKEY v7; // rcx
  HKEY v8; // rcx
  int v9; // r12d
  HKEY v10; // r14
  unsigned int v11; // esi
  int v12; // eax
  __int64 v13; // r9
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  LPCWSTR lpValueName; // [rsp+58h] [rbp-11h]
  BYTE *lpData[12]; // [rsp+60h] [rbp-9h]
  DWORD dwDisposition; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = a3;
  v6 = 0;
  if ( (a3 & 8) == 0
    || (a2[16] & 1) == 0
    || (v7 = *(HKEY *)(a1 + 16),
        hKey = 0,
        dwDisposition = 0,
        (v6 = RegCreateKeyExW(
                v7,
                L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ikev2",
                0,
                0,
                0,
                0xF003Fu,
                0,
                &hKey,
                &dwDisposition)) == 0)
    && (v6 = SetIkev2ConfigParams(hKey, *a2, (__int64)(a2 + 24)), RegCloseKey(hKey), !v6) )
  {
    if ( (v4 & 2) == 0 || (a2[144] & 1) == 0 || (unsigned __int8)(*a2 - 3) > 2u )
      goto LABEL_29;
    v8 = *(HKEY *)(a1 + 16);
    hKey = 0;
    dwDisposition = 0;
    v6 = RegCreateKeyExW(
           v8,
           L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\L2TP",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKey,
           &dwDisposition);
    if ( !v6 )
    {
      v9 = *a2;
      lpData[0] = (BYTE *)(a2 + 152);
      lpValueName = L"idleTimeout";
      lpData[1] = (BYTE *)L"saLifeTime";
      lpData[2] = (BYTE *)(a2 + 160);
      lpData[3] = (BYTE *)L"saDataSize";
      lpData[4] = (BYTE *)(a2 + 164);
      if ( v9 != 1 && v9 != 2 )
      {
        if ( v9 == 3 || (unsigned int)(v9 - 4) < 2 )
        {
          if ( *((_DWORD *)a2 + 39) <= 3u )
          {
            v10 = hKey;
            v11 = 0;
            while ( 1 )
            {
              v6 = RegSetValueExW(v10, (LPCWSTR)lpData[2 * v11 - 1], 0, 4u, lpData[2 * v11], 4u);
              if ( v6 )
                break;
              if ( ++v11 >= 3 )
              {
                if ( ((char)v9 < 5 || (v6 = RegSetValueExW(v10, L"mmSaLifeTime", 0, 4u, (const BYTE *)a2 + 176, 4u)) == 0)
                  && (char)v9 >= 3 )
                {
                  if ( *((_QWORD *)a2 + 21) )
                  {
                    v6 = SetL2tpCustomPolicy(v10);
                    if ( v6 )
                      break;
                  }
                  else
                  {
                    RegDeleteKeyExW(v10, L"L2TPCustomPolicy", 0, 0);
                  }
                  v6 = RegSetValueExW(v10, L"EncryptionType", 0, 4u, (const BYTE *)a2 + 156, 4u);
                }
                break;
              }
            }
            v4 = a3;
          }
          else
          {
            v6 = 87;
          }
        }
        else
        {
          v6 = 50;
        }
      }
      RegCloseKey(hKey);
      if ( !v6 )
      {
LABEL_29:
        if ( (v4 & 4) != 0 )
        {
          if ( *a2 == 1 || *a2 == 2 || *a2 == 3 || (unsigned int)(*a2 - 4) < 2 )
          {
            if ( *((_DWORD *)a2 + 49) != 32780 )
              return 87;
            v12 = *((_DWORD *)a2 + 52);
            if ( (v12 & 0xFFFFFFDF) != 0 )
            {
              return 87;
            }
            else
            {
              v13 = 0;
              if ( v12 )
                v13 = *((_QWORD *)a2 + 27);
              return (unsigned int)SetSstpConfiguration(
                                     *(_QWORD *)(a1 + 16),
                                     *(_QWORD *)(a1 + 8),
                                     *((unsigned int *)a2 + 48),
                                     v13);
            }
          }
          else
          {
            return 50;
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180028a18  mov     [rsp-8+arg_0], rbx
0x180028a1d  mov     [rsp-8+arg_10], r8d
0x180028a22  push    rbp
0x180028a23  push    rsi
0x180028a24  push    rdi
0x180028a25  push    r12
0x180028a27  push    r13
0x180028a29  push    r14
0x180028a2b  push    r15
0x180028a2d  lea     rbp, [rsp-27h]
0x180028a32  sub     rsp, 90h
0x180028a39  mov     rdi, rdx
0x180028a3c  mov     esi, r8d
0x180028a3f  xor     edx, edx
0x180028a41  mov     r15, rcx
0x180028a44  mov     ebx, edx
0x180028a46  mov     r14d, 0F003Fh
0x180028a4c  test    r8b, 8
0x180028a50  jz      short loc_180028AC5
0x180028a52  test    byte ptr [rdi+10h], 1
0x180028a56  jz      short loc_180028AC5
0x180028a58  mov     rcx, [rcx+10h]; hKey
0x180028a5c  lea     rax, [rbp+57h+dwDisposition]
0x180028a60  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180028a65  xor     r9d, r9d; lpClass
0x180028a68  lea     rax, [rbp+57h+hKey]
0x180028a6c  mov     [rbp+57h+hKey], rdx
0x180028a70  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180028a75  xor     r8d, r8d; Reserved
0x180028a78  mov     [rsp+0C0h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x180028a7d  mov     [rbp+57h+dwDisposition], edx
0x180028a80  mov     [rsp+0C0h+samDesired], r14d; samDesired
0x180028a85  mov     [rsp+0C0h+dwOptions], edx; dwOptions
0x180028a89  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180028a90  call    cs:__imp_RegCreateKeyExW
0x180028a96  mov     ebx, eax
0x180028a98  test    eax, eax
0x180028a9a  jnz     loc_180028D02
0x180028aa0  mov     dl, [rdi]
0x180028aa2  lea     r8, [rdi+18h]
0x180028aa6  mov     rcx, [rbp+57h+hKey]; hKey
0x180028aaa  call    SetIkev2ConfigParams
0x180028aaf  mov     rcx, [rbp+57h+hKey]; hKey
0x180028ab3  mov     ebx, eax
0x180028ab5  call    cs:__imp_RegCloseKey
0x180028abb  xor     edx, edx
0x180028abd  test    ebx, ebx
0x180028abf  jnz     loc_180028D02
0x180028ac5  test    sil, 2
0x180028ac9  jz      loc_180028C94
0x180028acf  test    byte ptr [rdi+90h], 1
0x180028ad6  jz      loc_180028C94
0x180028adc  mov     al, [rdi]
0x180028ade  sub     al, 3
0x180028ae0  cmp     al, 2
0x180028ae2  ja      loc_180028C94
0x180028ae8  mov     rcx, [r15+10h]; hKey
0x180028aec  lea     rax, [rbp+57h+dwDisposition]
0x180028af0  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180028af5  xor     r9d, r9d; lpClass
0x180028af8  lea     rax, [rbp+57h+hKey]
0x180028afc  mov     [rbp+57h+hKey], rdx
0x180028b00  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180028b05  xor     r8d, r8d; Reserved
0x180028b08  mov     [rsp+0C0h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x180028b0d  mov     [rbp+57h+dwDisposition], edx
0x180028b10  mov     [rsp+0C0h+samDesired], r14d; samDesired
0x180028b15  mov     [rsp+0C0h+dwOptions], edx; dwOptions
0x180028b19  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180028b20  call    cs:__imp_RegCreateKeyExW
0x180028b26  mov     ebx, eax
0x180028b28  test    eax, eax
0x180028b2a  jnz     loc_180028D02
0x180028b30  movsx   r12d, byte ptr [rdi]
0x180028b34  lea     rdx, [rdi+98h]
0x180028b3b  lea     rax, aIdletimeout; "idleTimeout"
0x180028b42  mov     [rbp+57h+lpData], rdx
0x180028b46  mov     [rbp+57h+lpValueName], rax
0x180028b4a  mov     ecx, r12d
0x180028b4d  lea     rax, aSalifetime; "saLifeTime"
0x180028b54  mov     [rbp+57h+var_58], rax
0x180028b58  lea     rax, [rdx+8]
0x180028b5c  mov     [rbp+57h+var_50], rax
0x180028b60  lea     rax, aSadatasize; "saDataSize"
0x180028b67  mov     [rbp+57h+var_48], rax
0x180028b6b  lea     rax, [rdx+0Ch]
0x180028b6f  mov     [rbp+57h+var_40], rax
0x180028b73  sub     ecx, 1
0x180028b76  jz      loc_180028C84
0x180028b7c  sub     ecx, 1
0x180028b7f  jz      loc_180028C84
0x180028b85  sub     ecx, 1
0x180028b88  jz      short loc_180028B9E
0x180028b8a  sub     ecx, 1
0x180028b8d  jz      short loc_180028B9E
0x180028b8f  cmp     ecx, 1
0x180028b92  jz      short loc_180028B9E
0x180028b94  mov     ebx, 32h ; '2'
0x180028b99  jmp     loc_180028C84
0x180028b9e  lea     r13, [rdx+4]
0x180028ba2  cmp     dword ptr [r13+0], 3
0x180028ba7  jbe     short loc_180028BB3
0x180028ba9  mov     ebx, 57h ; 'W'
0x180028bae  jmp     loc_180028C84
0x180028bb3  mov     r14, [rbp+57h+hKey]
0x180028bb7  xor     esi, esi
0x180028bb9  mov     ecx, 4
0x180028bbe  mov     edx, esi
0x180028bc0  add     rdx, rdx
0x180028bc3  mov     [rsp+0C0h+samDesired], ecx; cbData
0x180028bc7  mov     r9d, ecx; dwType
0x180028bca  xor     r8d, r8d; Reserved
0x180028bcd  mov     rcx, r14; hKey
0x180028bd0  mov     rax, [rbp+rdx*8+57h+lpData]
0x180028bd5  mov     rdx, [rbp+rdx*8+57h+lpValueName]; lpValueName
0x180028bda  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x180028bdf  call    cs:__imp_RegSetValueExW
0x180028be5  mov     ebx, eax
0x180028be7  test    eax, eax
0x180028be9  jnz     loc_180028C81
0x180028bef  inc     esi
0x180028bf1  cmp     esi, 3
0x180028bf4  jb      short loc_180028BB9
0x180028bf6  lea     esi, [rax+4]
0x180028bf9  cmp     r12b, 5
0x180028bfd  jl      short loc_180028C2B
0x180028bff  lea     rax, [rdi+0B0h]
0x180028c06  mov     [rsp+0C0h+samDesired], esi; cbData
0x180028c0a  mov     r9d, esi; dwType
0x180028c0d  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x180028c12  xor     r8d, r8d; Reserved
0x180028c15  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x180028c1c  mov     rcx, r14; hKey
0x180028c1f  call    cs:__imp_RegSetValueExW
0x180028c25  mov     ebx, eax
0x180028c27  test    eax, eax
0x180028c29  jnz     short loc_180028C81
0x180028c2b  cmp     r12b, 3
0x180028c2f  jl      short loc_180028C81
0x180028c31  mov     rdx, [rdi+0A8h]
0x180028c38  mov     rcx, r14; hKey
0x180028c3b  test    rdx, rdx
0x180028c3e  jz      short loc_180028C4D
0x180028c40  call    SetL2tpCustomPolicy
0x180028c45  mov     ebx, eax
0x180028c47  test    eax, eax
0x180028c49  jnz     short loc_180028C81
0x180028c4b  jmp     short loc_180028C60
0x180028c4d  xor     r9d, r9d; Reserved
0x180028c50  lea     rdx, aL2tpcustompoli; "L2TPCustomPolicy"
0x180028c57  xor     r8d, r8d; samDesired
0x180028c5a  call    cs:__imp_RegDeleteKeyExW
0x180028c60  mov     [rsp+0C0h+samDesired], esi; cbData
0x180028c64  lea     rdx, aEncryptiontype; "EncryptionType"
0x180028c6b  mov     r9d, esi; dwType
0x180028c6e  mov     qword ptr [rsp+0C0h+dwOptions], r13; lpData
0x180028c73  xor     r8d, r8d; Reserved
0x180028c76  mov     rcx, r14; hKey
0x180028c79  call    cs:__imp_RegSetValueExW
0x180028c7f  mov     ebx, eax
0x180028c81  mov     esi, [rbp+57h+arg_10]
0x180028c84  mov     rcx, [rbp+57h+hKey]; hKey
0x180028c88  call    cs:__imp_RegCloseKey
0x180028c8e  xor     edx, edx
0x180028c90  test    ebx, ebx
0x180028c92  jnz     short loc_180028D02
0x180028c94  test    sil, 4
0x180028c98  jz      short loc_180028D02
0x180028c9a  movsx   ecx, byte ptr [rdi]
0x180028c9d  sub     ecx, 1
0x180028ca0  jz      short loc_180028CBD
0x180028ca2  sub     ecx, 1
0x180028ca5  jz      short loc_180028CBD
0x180028ca7  sub     ecx, 1
0x180028caa  jz      short loc_180028CBD
0x180028cac  sub     ecx, 1
0x180028caf  jz      short loc_180028CBD
0x180028cb1  cmp     ecx, 1
0x180028cb4  jz      short loc_180028CBD
0x180028cb6  mov     ebx, 32h ; '2'
0x180028cbb  jmp     short loc_180028D02
0x180028cbd  cmp     dword ptr [rdi+0C4h], 800Ch
0x180028cc7  jz      short loc_180028CD0
0x180028cc9  mov     ebx, 57h ; 'W'
0x180028cce  jmp     short loc_180028D02
0x180028cd0  mov     eax, [rdi+0D0h]
0x180028cd6  test    eax, 0FFFFFFDFh
0x180028cdb  jnz     short loc_180028CC9
0x180028cdd  mov     r9, rdx
0x180028ce0  test    eax, eax
0x180028ce2  jz      short loc_180028CEB
0x180028ce4  mov     r9, [rdi+0D8h]
0x180028ceb  mov     r8d, [rdi+0C0h]
0x180028cf2  mov     rdx, [r15+8]
0x180028cf6  mov     rcx, [r15+10h]
0x180028cfa  call    cs:__imp_SetSstpConfiguration
0x180028d00  mov     ebx, eax
0x180028d02  mov     eax, ebx
0x180028d04  mov     rbx, [rsp+0C0h+arg_0]
0x180028d0c  add     rsp, 90h
0x180028d13  pop     r15
0x180028d15  pop     r14
0x180028d17  pop     r13
0x180028d19  pop     r12
0x180028d1b  pop     rdi
0x180028d1c  pop     rsi
0x180028d1d  pop     rbp
0x180028d1e  retn
```
