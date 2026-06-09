# DhcpCopyToCurrentContext

- ea: `0x180013398`
- end: `0x1800134ba`
- name: `DhcpCopyToCurrentContext`
- size: `290`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180024488`

## callees

- `0x180013398`
- `0x1800139e4`
- `0x180013b60`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001345d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001345d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800133e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800133e0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001347c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001347c`

## pseudocode

```c
__int64 __fastcall DhcpCopyToCurrentContext(__int64 a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  HKEY v6; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( a1 && a2 )
  {
    v4 = RegOpenKeyExW(*(HKEY *)(a1 + 728), a2, 0, 0xFu, &hKey);
    if ( v4 )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_(1028, 100, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
    }
    else if ( hKey )
    {
      DhcpRegCopyInterfaceSettings(hKey, *(HKEY *)(a1 + 728));
      if ( (unsigned int)UpdateWINSServerList(a1, hKey) && (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_(1028, 101, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
      RegCloseKey(hKey);
      v6 = *(HKEY *)(a1 + 728);
      hKey = 0;
      return (unsigned int)RegDeleteKeyExW(v6, a2, 0, 0);
    }
    return v4;
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 99, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x180013398  mov     r11, rsp
0x18001339b  mov     [r11+10h], rbx
0x18001339f  mov     [r11+18h], rsi
0x1800133a3  push    rdi
0x1800133a4  sub     rsp, 30h
0x1800133a8  mov     qword ptr [r11+8], 0
0x1800133b0  mov     rsi, rdx
0x1800133b3  mov     rdi, rcx
0x1800133b6  test    rcx, rcx
0x1800133b9  jz      loc_180013486
0x1800133bf  test    rdx, rdx
0x1800133c2  jz      loc_180013486
0x1800133c8  mov     rcx, [rcx+2D8h]; hKey
0x1800133cf  lea     rax, [r11+8]
0x1800133d3  mov     r9d, 0Fh; samDesired
0x1800133d9  mov     [r11-18h], rax
0x1800133dd  xor     r8d, r8d; ulOptions
0x1800133e0  call    cs:__imp_RegOpenKeyExW
0x1800133e6  mov     ebx, eax
0x1800133e8  test    eax, eax
0x1800133ea  jz      short loc_180013412
0x1800133ec  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800133f3  jz      short loc_18001340B
0x1800133f5  mov     edx, 64h ; 'd'
0x1800133fa  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180013401  mov     ecx, 404h
0x180013406  call    WPP_SF_
0x18001340b  mov     eax, ebx
0x18001340d  jmp     loc_1800134AA
0x180013412  mov     rcx, [rsp+38h+hKey]; hKey
0x180013417  test    rcx, rcx
0x18001341a  jz      short loc_18001340B
0x18001341c  mov     rdx, [rdi+2D8h]; HKEY
0x180013423  call    DhcpRegCopyInterfaceSettings
0x180013428  mov     rdx, [rsp+38h+hKey]
0x18001342d  mov     rcx, rdi
0x180013430  call    UpdateWINSServerList
0x180013435  test    eax, eax
0x180013437  jz      short loc_180013458
0x180013439  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013440  jz      short loc_180013458
0x180013442  mov     edx, 65h ; 'e'
0x180013447  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18001344e  mov     ecx, 404h
0x180013453  call    WPP_SF_
0x180013458  mov     rcx, [rsp+38h+hKey]; hKey
0x18001345d  call    cs:__imp_RegCloseKey
0x180013463  mov     rcx, [rdi+2D8h]; hKey
0x18001346a  xor     r9d, r9d; Reserved
0x18001346d  xor     r8d, r8d; samDesired
0x180013470  mov     [rsp+38h+hKey], 0
0x180013479  mov     rdx, rsi; lpSubKey
0x18001347c  call    cs:__imp_RegDeleteKeyExW
0x180013482  mov     ebx, eax
0x180013484  jmp     short loc_18001340B
0x180013486  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001348d  jz      short loc_1800134A5
0x18001348f  mov     edx, 63h ; 'c'
0x180013494  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18001349b  mov     ecx, 404h
0x1800134a0  call    WPP_SF_
0x1800134a5  mov     eax, 57h ; 'W'
0x1800134aa  mov     rbx, [rsp+38h+arg_8]
0x1800134af  mov     rsi, [rsp+38h+arg_10]
0x1800134b4  add     rsp, 30h
0x1800134b8  pop     rdi
0x1800134b9  retn
```
