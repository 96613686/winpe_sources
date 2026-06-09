# OSKSettingsManager::GetOskSetting(ulong,ulong *,int)

- ea: `0x140017378`
- end: `0x140017422`
- name: `?GetOskSetting@OSKSettingsManager@@QEAAJKPEAKH@Z`
- size: `170`
- prototype: `__int64 __fastcall(OSKSettingsManager *__hidden this, unsigned int, unsigned int *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001732c`
- `0x1400174f8`

## callees

- `0x140005c90`
- `0x140007e90`
- `0x140017378`
- `0x140017644`
- `0x140017a6c`

## string_xrefs

- `0x1400173a2`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig\osk`

## pseudocode

```c
__int64 __fastcall OSKSettingsManager::GetOskSetting(
        OSKSettingsManager *this,
        unsigned int a2,
        unsigned int *a3,
        int a4)
{
  __int64 v4; // rbx
  const WCHAR *v8; // r8
  unsigned int v9; // ebx
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF

  v4 = a2;
  *a3 = 0;
  if ( a2 >= 0x14 )
    return (unsigned int)-2147467259;
  v8 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig\\osk";
  if ( !a4 )
    v8 = L"Software\\Microsoft\\Osk";
  if ( (unsigned int)ATL::CRegKey::Open(this, HKEY_CURRENT_USER, v8, 0x20019u) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v11 = 0;
    if ( (unsigned int)ATL::CRegKey::QueryDWORDValue(this, (const unsigned __int16 *)*(&g_rgOskSettings + 3 * v4), &v11) )
    {
      v9 = -2147467259;
    }
    else
    {
      OSKSettingsManager::_KeepSettingValueInBounds(this, v4, &v11, a4);
      v9 = 0;
      *a3 = v11;
    }
    ATL::CRegKey::Close(this);
  }
  return v9;
}

```

## disassembly

```asm
0x140017378  push    rbx
0x14001737a  push    rbp
0x14001737b  push    rsi
0x14001737c  push    rdi
0x14001737d  sub     rsp, 28h
0x140017381  mov     ebx, edx
0x140017383  mov     ebp, r9d
0x140017386  mov     dword ptr [r8], 0
0x14001738d  mov     rsi, r8
0x140017390  mov     rdi, rcx
0x140017393  cmp     edx, 14h
0x140017396  jnb     short loc_140017412
0x140017398  test    r9d, r9d
0x14001739b  lea     rax, aSoftwareMicros_9; "Software\\Microsoft\\Osk"
0x1400173a2  lea     r8, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400173a9  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1400173b0  cmovz   r8, rax; lpSubKey
0x1400173b4  mov     r9d, 20019h; unsigned int
0x1400173ba  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400173bf  test    eax, eax
0x1400173c1  jnz     short loc_140017412
0x1400173c3  mov     [rsp+48h+arg_8], eax
0x1400173c7  lea     rdx, [rbx+rbx*2]
0x1400173cb  lea     rax, ?g_rgOskSettings@@3PAU_OSKSETTINGSINFO@@A; _OSKSETTINGSINFO near * g_rgOskSettings
0x1400173d2  mov     rcx, rdi; this
0x1400173d5  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x1400173d9  lea     r8, [rsp+48h+arg_8]; unsigned int *
0x1400173de  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1400173e3  test    eax, eax
0x1400173e5  jnz     short loc_140017403
0x1400173e7  mov     r9d, ebp; int
0x1400173ea  lea     r8, [rsp+48h+arg_8]; unsigned int *
0x1400173ef  mov     edx, ebx; unsigned int
0x1400173f1  mov     rcx, rdi; this
0x1400173f4  call    ?_KeepSettingValueInBounds@OSKSettingsManager@@AEAAXKPEAKH@Z; OSKSettingsManager::_KeepSettingValueInBounds(ulong,ulong *,int)
0x1400173f9  mov     eax, [rsp+48h+arg_8]
0x1400173fd  xor     ebx, ebx
0x1400173ff  mov     [rsi], eax
0x140017401  jmp     short loc_140017408
0x140017403  mov     ebx, 80004005h
0x140017408  mov     rcx, rdi; this
0x14001740b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017410  jmp     short loc_140017417
0x140017412  mov     ebx, 80004005h
0x140017417  mov     eax, ebx
0x140017419  add     rsp, 28h
0x14001741d  pop     rdi
0x14001741e  pop     rsi
0x14001741f  pop     rbp
0x140017420  pop     rbx
0x140017421  retn
```
