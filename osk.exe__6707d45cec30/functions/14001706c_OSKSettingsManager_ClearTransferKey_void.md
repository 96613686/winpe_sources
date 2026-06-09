# OSKSettingsManager::ClearTransferKey(void)

- ea: `0x14001706c`
- end: `0x1400170cf`
- name: `?ClearTransferKey@OSKSettingsManager@@SAXXZ`
- size: `99`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e16c`

## callees

- `0x140005c90`
- `0x140007e90`
- `0x14001706c`
- `0x140017180`

## string_xrefs

- `0x140017081`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
void OSKSettingsManager::ClearTransferKey(void)
{
  const unsigned __int16 *v0; // rdx
  _BYTE v1[40]; // [rsp+20h] [rbp-28h] BYREF

  memset(v1, 0, 24);
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v1,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATConfig",
                        0x20006u) )
  {
    ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v1, v0);
    ATL::CRegKey::Close((ATL::CRegKey *)v1);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v1);
}

```

## disassembly

```asm
0x14001706c  mov     rax, rsp
0x14001706f  sub     rsp, 48h
0x140017073  mov     r9d, 20006h; unsigned int
0x140017079  mov     qword ptr [rax-28h], 0
0x140017081  lea     r8, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x140017088  mov     qword ptr [rax-20h], 0
0x140017090  mov     rdx, 0FFFFFFFF80000001h; hKey
0x140017097  mov     qword ptr [rax-18h], 0
0x14001709f  lea     rcx, [rax-28h]; this
0x1400170a3  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400170a8  test    eax, eax
0x1400170aa  jnz     short loc_1400170C0
0x1400170ac  lea     rcx, [rsp+48h+var_28]; this
0x1400170b1  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1400170b6  lea     rcx, [rsp+48h+var_28]; this
0x1400170bb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400170c0  lea     rcx, [rsp+48h+var_28]; this
0x1400170c5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400170ca  add     rsp, 48h
0x1400170ce  retn
```
