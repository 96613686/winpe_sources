# CStartupAppCheck::_UpdateState(bool)

- ea: `0x1800085b0`
- end: `0x180008638`
- name: `?_UpdateState@CStartupAppCheck@@AEAAJ_N@Z`
- size: `136`
- prototype: `__int64 __fastcall(CStartupAppCheck *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004b10`
- `0x180008820`

## callees

- `0x1800019f0`
- `0x180004618`
- `0x1800085b0`

## pseudocode

```c
__int64 __fastcall CStartupAppCheck::_UpdateState(RTL_SRWLOCK *this, char a2)
{
  unsigned int v4; // eax
  unsigned int v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\StartupNotify",
              L"EnableStartupAppNotification",
              &v6) < 0 )
  {
    v4 = 0;
  }
  else
  {
    v4 = 2;
    if ( v6 <= 2 && (v6 != 1 || !g_BatteryPresent) )
      v4 = v6;
  }
  return CCheckBase::_SetState(this, (const struct HCSTATE *)(&CStartupAppCheck::c_rgStates + 10 * (int)v4), a2);
}

```

## disassembly

```asm
0x1800085b0  mov     [rsp+arg_0], rbx
0x1800085b5  push    rdi
0x1800085b6  sub     rsp, 20h
0x1800085ba  mov     bl, dl
0x1800085bc  mov     [rsp+28h+arg_10], 0
0x1800085c4  mov     rdi, rcx
0x1800085c7  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800085ce  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800085d5  lea     r9, [rsp+28h+arg_10]; unsigned int *
0x1800085da  lea     r8, aEnablestartupa; "EnableStartupAppNotification"
0x1800085e1  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800085e6  test    eax, eax
0x1800085e8  js      short loc_18000860D
0x1800085ea  mov     r8d, [rsp+28h+arg_10]
0x1800085ef  mov     eax, 2
0x1800085f4  cmp     r8d, eax
0x1800085f7  ja      short loc_18000860F
0x1800085f9  cmp     r8d, 1
0x1800085fd  jnz     short loc_180008608
0x1800085ff  cmp     cs:?g_BatteryPresent@@3HA, 0; int g_BatteryPresent
0x180008606  jnz     short loc_18000860F
0x180008608  mov     eax, r8d
0x18000860b  jmp     short loc_18000860F
0x18000860d  xor     eax, eax
0x18000860f  cdqe
0x180008611  mov     r8b, bl; bool
0x180008614  mov     rcx, rdi; this
0x180008617  lea     rdx, [rax+rax*4]
0x18000861b  shl     rdx, 4
0x18000861f  lea     rax, ?c_rgStates@CStartupAppCheck@@0QBUHCSTATE@@B; HCSTATE const near * const CStartupAppCheck::c_rgStates
0x180008626  add     rdx, rax; struct HCSTATE *
0x180008629  mov     rbx, [rsp+28h+arg_0]
0x18000862e  add     rsp, 20h
0x180008632  pop     rdi
0x180008633  jmp     ?_SetState@CCheckBase@@IEAAJPEBUHCSTATE@@_N@Z; CCheckBase::_SetState(HCSTATE const *,bool)
```
