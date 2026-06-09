# OSKSettingsManager::_HandleUpdateAllListeners(void)

- ea: `0x1400179b0`
- end: `0x140017a63`
- name: `?_HandleUpdateAllListeners@OSKSettingsManager@@AEAAXXZ`
- size: `179`
- prototype: `void __fastcall(OSKSettingsManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140017990`

## callees

- `0x140005c90`
- `0x140007e90`
- `0x1400175e8`
- `0x140017644`
- `0x140017888`
- `0x1400179b0`
- `0x140017a6c`

## pseudocode

```c
void __fastcall OSKSettingsManager::_HandleUpdateAllListeners(OSKSettingsManager *this)
{
  OSKSettingsManager *v1; // rdi
  unsigned int i; // ebx
  OSKSettingsManager *v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = this;
  v1 = OSKSettingsManager::s_pThis;
  if ( !(unsigned int)ATL::CRegKey::Open(
                        OSKSettingsManager::s_pThis,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Osk",
                        0x20019u) )
  {
    for ( i = 0; i < 0x14; ++i )
    {
      LODWORD(v3) = 0;
      if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue(
                            v1,
                            (const unsigned __int16 *)*(&g_rgOskSettings + 3 * (int)i),
                            (unsigned int *)&v3) )
      {
        OSKSettingsManager::_KeepSettingValueInBounds(v1, i, (unsigned int *)&v3, 0);
        OSKSettingsManager::SetOskSetting(v1, i, (unsigned int)v3, (unsigned __int16 *)1);
        OSKSettingsManager::NotifyListeners(v1, i, (unsigned int)v3);
      }
    }
    ATL::CRegKey::Close(v1);
  }
}

```

## disassembly

```asm
0x1400179b0  mov     [rsp+arg_8], rbx
0x1400179b5  mov     [rsp+arg_0], rcx
0x1400179ba  push    rdi
0x1400179bb  sub     rsp, 20h
0x1400179bf  mov     rdi, cs:?s_pThis@OSKSettingsManager@@1PEAV1@EA; OSKSettingsManager * OSKSettingsManager::s_pThis
0x1400179c6  lea     r8, aSoftwareMicros_9; "Software\\Microsoft\\Osk"
0x1400179cd  mov     rcx, rdi; this
0x1400179d0  mov     r9d, 20019h; unsigned int
0x1400179d6  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1400179dd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400179e2  test    eax, eax
0x1400179e4  jnz     short loc_140017A58
0x1400179e6  xor     ebx, ebx
0x1400179e8  movsxd  rax, ebx
0x1400179eb  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x1400179f0  mov     rcx, rdi; this
0x1400179f3  mov     dword ptr [rsp+28h+arg_0], 0
0x1400179fb  lea     rdx, [rax+rax*2]
0x1400179ff  lea     rax, ?g_rgOskSettings@@3PAU_OSKSETTINGSINFO@@A; _OSKSETTINGSINFO near * g_rgOskSettings
0x140017a06  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x140017a0a  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x140017a0f  test    eax, eax
0x140017a11  jnz     short loc_140017A49
0x140017a13  xor     r9d, r9d; int
0x140017a16  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x140017a1b  mov     edx, ebx; unsigned int
0x140017a1d  mov     rcx, rdi; this
0x140017a20  call    ?_KeepSettingValueInBounds@OSKSettingsManager@@AEAAXKPEAKH@Z; OSKSettingsManager::_KeepSettingValueInBounds(ulong,ulong *,int)
0x140017a25  mov     r8d, dword ptr [rsp+28h+arg_0]; unsigned int
0x140017a2a  mov     r9d, 1; int
0x140017a30  mov     edx, ebx; unsigned int
0x140017a32  mov     rcx, rdi; this
0x140017a35  call    ?SetOskSetting@OSKSettingsManager@@QEAAJKKH@Z; OSKSettingsManager::SetOskSetting(ulong,ulong,int)
0x140017a3a  mov     r8d, dword ptr [rsp+28h+arg_0]; unsigned int
0x140017a3f  mov     edx, ebx; unsigned int
0x140017a41  mov     rcx, rdi; this
0x140017a44  call    ?NotifyListeners@OSKSettingsManager@@QEAAXKK@Z; OSKSettingsManager::NotifyListeners(ulong,ulong)
0x140017a49  inc     ebx
0x140017a4b  cmp     ebx, 14h
0x140017a4e  jb      short loc_1400179E8
0x140017a50  mov     rcx, rdi; this
0x140017a53  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140017a58  mov     rbx, [rsp+28h+arg_8]
0x140017a5d  add     rsp, 20h
0x140017a61  pop     rdi
0x140017a62  retn
```
