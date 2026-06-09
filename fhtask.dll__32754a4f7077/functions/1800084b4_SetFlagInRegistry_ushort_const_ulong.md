# SetFlagInRegistry(ushort const *,ulong)

- ea: `0x1800084b4`
- end: `0x1800085eb`
- name: `?SetFlagInRegistry@@YAXPEBGK@Z`
- size: `311`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ba0`

## callees

- `0x180006728`
- `0x1800084b4`
- `0x180009578`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800085df`
- `ADVAPI32!RegCloseKey` at `0x1800085df`
- `ADVAPI32!RegCreateKeyExW` at `0x18000850c`
- `ADVAPI32!RegCreateKeyExW` at `0x18000850c`
- `ADVAPI32!RegSetValueExW` at `0x18000858a`
- `ADVAPI32!RegSetValueExW` at `0x18000858a`

## pseudocode

```c
void __fastcall SetFlagInRegistry(const unsigned __int16 *a1)
{
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  int v3; // r8d
  BYTE Data[24]; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  *(_DWORD *)Data = 1;
  hKey = 0;
  v1 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &hKey,
         0);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_8158daeccbd13eff1bb477c819869c69_Traceguids,
        (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
        v1);
  }
  else
  {
    v2 = RegSetValueExW(hKey, L"RehydrationPaused", 0, 4u, Data, 4u);
    if ( v2 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        v3,
        (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
        (__int64)L"RehydrationPaused",
        v2);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800084b4  mov     r11, rsp
0x1800084b7  mov     [r11+8], rcx
0x1800084bb  push    rsi
0x1800084bc  sub     rsp, 60h
0x1800084c0  mov     qword ptr [r11-28h], 0
0x1800084c8  lea     rax, [r11+8]
0x1800084cc  mov     [r11-30h], rax
0x1800084d0  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800084d7  mov     qword ptr [r11-38h], 0
0x1800084df  xor     r9d, r9d; lpClass
0x1800084e2  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x1800084ea  xor     r8d, r8d; Reserved
0x1800084ed  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800084f4  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800084fc  mov     dword ptr [rsp+68h+Data], 1
0x180008504  mov     qword ptr [r11+8], 0
0x18000850c  call    cs:__imp_RegCreateKeyExW
0x180008512  test    eax, eax
0x180008514  jz      short loc_180008563
0x180008516  jle     short loc_180008520
0x180008518  movzx   eax, ax
0x18000851b  or      eax, 80070000h
0x180008520  mov     rcx, cs:WPP_GLOBAL_Control
0x180008527  lea     rdx, WPP_GLOBAL_Control
0x18000852e  cmp     rcx, rdx
0x180008531  jz      loc_1800085D5
0x180008537  test    byte ptr [rcx+1Ch], 1
0x18000853b  jz      loc_1800085D5
0x180008541  mov     rcx, [rcx+10h]
0x180008545  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000854c  mov     edx, 17h
0x180008551  mov     [rsp+68h+dwOptions], eax
0x180008555  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x18000855c  call    WPP_SF_Sd
0x180008561  jmp     short loc_1800085D5
0x180008563  mov     rcx, [rsp+68h+hKey]; hKey
0x180008568  lea     rax, [rsp+68h+Data]
0x18000856d  mov     r9d, 4; dwType
0x180008573  lea     rsi, aRehydrationpau; "RehydrationPaused"
0x18000857a  mov     [rsp+68h+samDesired], r9d; cbData
0x18000857f  mov     rdx, rsi; lpValueName
0x180008582  xor     r8d, r8d; Reserved
0x180008585  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18000858a  call    cs:__imp_RegSetValueExW
0x180008590  test    eax, eax
0x180008592  jz      short loc_1800085D5
0x180008594  jle     short loc_18000859E
0x180008596  movzx   eax, ax
0x180008599  or      eax, 80070000h
0x18000859e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085a5  lea     rdx, WPP_GLOBAL_Control
0x1800085ac  cmp     rcx, rdx
0x1800085af  jz      short loc_1800085D5
0x1800085b1  test    byte ptr [rcx+1Ch], 1
0x1800085b5  jz      short loc_1800085D5
0x1800085b7  mov     rcx, [rcx+10h]
0x1800085bb  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800085c2  mov     [rsp+68h+samDesired], eax
0x1800085c6  mov     edx, 18h
0x1800085cb  mov     qword ptr [rsp+68h+dwOptions], rsi
0x1800085d0  call    WPP_SF_SSd
0x1800085d5  mov     rcx, [rsp+68h+hKey]; hKey
0x1800085da  test    rcx, rcx
0x1800085dd  jz      short loc_1800085E5
0x1800085df  call    cs:__imp_RegCloseKey
0x1800085e5  add     rsp, 60h
0x1800085e9  pop     rsi
0x1800085ea  retn
```
