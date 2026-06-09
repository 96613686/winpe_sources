# StartList::GetSettingConfigurationValue(ushort *,uint,ATL::CRegKey &)

- ea: `0x14001ec2c`
- end: `0x14001ed15`
- name: `?GetSettingConfigurationValue@StartList@@AEAAXPEAGIAEAVCRegKey@ATL@@@Z`
- size: `233`
- prototype: `void(StartList *__hidden this, unsigned __int16 *, unsigned int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f728`

## callees

- `0x140007e90`
- `0x14000df20`
- `0x14001c768`
- `0x14001c8a8`
- `0x14001ec2c`

## string_xrefs

- `0x14001ecc3`: `SettingConfiguration`
- `0x14001ec59`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x14001ec52`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
void __fastcall StartList::GetSettingConfigurationValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct ATL::CRegKey *a4)
{
  int IsInteractiveUser; // eax
  const WCHAR *v7; // r8
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  *a2 = 0;
  IsInteractiveUser = CATUtils::IsInteractiveUser();
  v7 = StartList::_accessibilityKeyString;
  if ( !IsInteractiveUser )
    v7 = StartList::_oobeAccessibilityKeyString;
  v8 = ATL::CRegKey::Open(a4, (HKEY)(-(__int64)(IsInteractiveUser != 0) - 2147483646), v7, 0x2001Fu);
  if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v8);
  v10 = 1024;
  v9 = ATL::CRegKey::QueryStringValue(a4, StartList::_settingConfiguration, a2, &v10);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v9);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x14001ec2c  mov     [rsp+arg_0], rbx
0x14001ec31  mov     [rsp+arg_8], rsi
0x14001ec36  mov     [rsp+arg_10], r8d
0x14001ec3b  push    rdi
0x14001ec3c  sub     rsp, 20h
0x14001ec40  xor     eax, eax
0x14001ec42  mov     rdi, r9
0x14001ec45  mov     [rdx], ax
0x14001ec48  mov     rbx, rdx
0x14001ec4b  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x14001ec50  test    eax, eax
0x14001ec52  lea     rcx, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001ec59  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001ec60  mov     r9d, 2001Fh; unsigned int
0x14001ec66  cmovz   r8, rcx; lpSubKey
0x14001ec6a  neg     eax
0x14001ec6c  mov     rcx, rdi; this
0x14001ec6f  sbb     rdx, rdx
0x14001ec72  add     rdx, 0FFFFFFFF80000002h; hKey
0x14001ec79  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001ec7e  lea     rsi, WPP_GLOBAL_Control
0x14001ec85  test    eax, eax
0x14001ec87  jz      short loc_14001ECB3
0x14001ec89  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ec90  cmp     rcx, rsi
0x14001ec93  jz      short loc_14001ECB3
0x14001ec95  test    byte ptr [rcx+1Ch], 8
0x14001ec99  jz      short loc_14001ECB3
0x14001ec9b  mov     rcx, [rcx+10h]
0x14001ec9f  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001eca6  mov     edx, 22h ; '"'
0x14001ecab  mov     r9d, eax
0x14001ecae  call    WPP_SF_d
0x14001ecb3  lea     r9, [rsp+28h+arg_10]; unsigned int *
0x14001ecb8  mov     [rsp+28h+arg_10], 400h
0x14001ecc0  mov     r8, rbx; unsigned __int16 *
0x14001ecc3  lea     rdx, ?_settingConfiguration@StartList@@0PAGA; "SettingConfiguration"
0x14001ecca  mov     rcx, rdi; this
0x14001eccd  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001ecd2  test    eax, eax
0x14001ecd4  jz      short loc_14001ED05
0x14001ecd6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ecdd  cmp     rcx, rsi
0x14001ece0  jz      short loc_14001ED00
0x14001ece2  test    byte ptr [rcx+1Ch], 8
0x14001ece6  jz      short loc_14001ED00
0x14001ece8  mov     rcx, [rcx+10h]
0x14001ecec  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001ecf3  mov     edx, 23h ; '#'
0x14001ecf8  mov     r9d, eax
0x14001ecfb  call    WPP_SF_d
0x14001ed00  xor     eax, eax
0x14001ed02  mov     [rbx], ax
0x14001ed05  mov     rbx, [rsp+28h+arg_0]
0x14001ed0a  mov     rsi, [rsp+28h+arg_8]
0x14001ed0f  add     rsp, 20h
0x14001ed13  pop     rdi
0x14001ed14  retn
```
