# RestoreEventsSink::RestoreEventsSink(void)

- ea: `0x1800067e0`
- end: `0x180006922`
- name: `??0RestoreEventsSink@@QEAA@XZ`
- size: `322`
- prototype: `RestoreEventsSink *__fastcall(RestoreEventsSink *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ba0`

## callees

- `0x180005ea4`
- `0x1800067e0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18000686d`
- `ADVAPI32!RegGetValueW` at `0x18000686d`
- `SHELL32!SHGetKnownFolderPath` at `0x1800068e0`
- `SHELL32!SHGetKnownFolderPath` at `0x1800068e0`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18000689e`
- `SHELL32!SHGetSpecialFolderPathW` at `0x18000689e`

## pseudocode

```c
RestoreEventsSink *__fastcall RestoreEventsSink::RestoreEventsSink(RestoreEventsSink *this)
{
  int ValueW; // eax
  int v4; // [rsp+60h] [rbp+8h] BYREF
  DWORD v5; // [rsp+68h] [rbp+10h] BYREF

  v5 = 4;
  *(GUID *)((char *)this + 8) = GUID_NULL;
  *((_DWORD *)this + 10) = 0;
  *(_QWORD *)this = &RestoreEventsSink::`vftable';
  *(GUID *)((char *)this + 24) = GUID_NULL;
  *((_WORD *)this + 28) = 0;
  v4 = 0;
  *((_DWORD *)this + 11) = -16843010;
  *((_QWORD *)this + 6) = 0;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\SettingSync\\Groups\\BrowserSettings",
             L"Enabled",
             0x10u,
             0,
             &v4,
             &v5);
  if ( ValueW > 0 )
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  if ( ValueW >= 0
    && v4
    && !SHGetSpecialFolderPathW(0, (LPWSTR)this + 28, 6, 0)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
  }
  if ( SHGetKnownFolderPath(&FOLDERID_SkyDrive, 0x4000u, 0, (PWSTR *)this + 6) < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
  }
  return this;
}

```

## disassembly

```asm
0x1800067e0  mov     r11, rsp
0x1800067e3  mov     [r11+18h], rbx
0x1800067e7  push    rsi
0x1800067e8  push    rdi
0x1800067e9  push    r14
0x1800067eb  sub     rsp, 40h
0x1800067ef  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800067f6  xor     eax, eax
0x1800067f8  mov     [rsp+58h+arg_8], 4
0x180006800  mov     rbx, rcx
0x180006803  lea     r8, Value; "Enabled"
0x18000680a  movdqu  xmmword ptr [rcx+8], xmm0
0x18000680f  mov     r9d, 10h; dwFlags
0x180006815  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000681c  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x180006823  mov     [rcx+28h], eax
0x180006826  lea     rax, ??_7RestoreEventsSink@@6B@; const RestoreEventsSink::`vftable'
0x18000682d  mov     [rcx], rax
0x180006830  xor     eax, eax
0x180006832  movdqu  xmmword ptr [rcx+18h], xmm1
0x180006837  mov     [rcx+38h], ax
0x18000683b  mov     [rsp+58h+arg_0], eax
0x18000683f  lea     rax, [r11+10h]
0x180006843  mov     [r11-28h], rax
0x180006847  lea     rax, [r11+8]
0x18000684b  mov     dword ptr [rcx+2Ch], 0FEFEFEFEh
0x180006852  mov     qword ptr [rcx+30h], 0
0x18000685a  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180006861  mov     [r11-30h], rax
0x180006865  mov     qword ptr [r11-38h], 0
0x18000686d  call    cs:__imp_RegGetValueW
0x180006873  test    eax, eax
0x180006875  jle     short loc_18000687F
0x180006877  movzx   eax, ax
0x18000687a  or      eax, 80070000h
0x18000687f  lea     r14, WPP_GLOBAL_Control
0x180006886  test    eax, eax
0x180006888  js      short loc_1800068CD
0x18000688a  cmp     [rsp+58h+arg_0], 0
0x18000688f  jz      short loc_1800068CD
0x180006891  xor     r9d, r9d; fCreate
0x180006894  lea     rdx, [rbx+38h]; pszPath
0x180006898  xor     ecx, ecx; hwnd
0x18000689a  lea     r8d, [r9+6]; csidl
0x18000689e  call    cs:__imp_SHGetSpecialFolderPathW
0x1800068a4  test    eax, eax
0x1800068a6  jnz     short loc_1800068CD
0x1800068a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068af  cmp     rcx, r14
0x1800068b2  jz      short loc_1800068CD
0x1800068b4  test    byte ptr [rcx+1Ch], 8
0x1800068b8  jz      short loc_1800068CD
0x1800068ba  mov     rcx, [rcx+10h]
0x1800068be  lea     edx, [rax+0Ah]
0x1800068c1  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x1800068c8  call    WPP_SF_
0x1800068cd  lea     r9, [rbx+30h]; ppszPath
0x1800068d1  xor     r8d, r8d; hToken
0x1800068d4  mov     edx, 4000h; dwFlags
0x1800068d9  lea     rcx, FOLDERID_SkyDrive; rfid
0x1800068e0  call    cs:__imp_SHGetKnownFolderPath
0x1800068e6  test    eax, eax
0x1800068e8  jns     short loc_180006911
0x1800068ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068f1  cmp     rcx, r14
0x1800068f4  jz      short loc_180006911
0x1800068f6  test    byte ptr [rcx+1Ch], 8
0x1800068fa  jz      short loc_180006911
0x1800068fc  mov     rcx, [rcx+10h]
0x180006900  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180006907  mov     edx, 0Bh
0x18000690c  call    WPP_SF_
0x180006911  mov     rax, rbx
0x180006914  mov     rbx, [rsp+58h+arg_10]
0x180006919  add     rsp, 40h
0x18000691d  pop     r14
0x18000691f  pop     rdi
0x180006920  pop     rsi
0x180006921  retn
```
