# SettingsCopier::InteractiveDesktopCopy(void)

- ea: `0x140025184`
- end: `0x140025239`
- name: `?InteractiveDesktopCopy@SettingsCopier@@QEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(SettingsCopier *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140020938`

## callees

- `0x140005c90`
- `0x14001c768`
- `0x14002491c`
- `0x140025184`
- `0x1400252a8`
- `0x140025400`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SettingsCopier::InteractiveDesktopCopy(SettingsCopier *this)
{
  SettingsCopier *v3; // rcx
  unsigned int v4; // ebx
  HKEY v5[3]; // [rsp+20h] [rbp-30h] BYREF
  HKEY v6[3]; // [rsp+38h] [rbp-18h] BYREF

  if ( !(unsigned int)CATUtils::IsInteractiveUser() )
    return 2147500037LL;
  memset(v5, 0, sizeof(v5));
  if ( (int)SettingsCopier::OpenUserConfigKey((struct ATL::CRegKey *)v5) < 0 )
  {
    ATL::CRegKey::Close((ATL::CRegKey *)v5);
    return 2147500037LL;
  }
  memset(v6, 0, sizeof(v6));
  if ( (int)SettingsCopier::OpenSessionKey(v3, (struct ATL::CRegKey *)v6) < 0
    || (int)SettingsCopier::CopyATSettings(this, v5, v6) < 0 )
  {
    v4 = -2147467259;
  }
  else
  {
    v4 = 0;
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v6);
  ATL::CRegKey::Close((ATL::CRegKey *)v5);
  return v4;
}

```

## disassembly

```asm
0x140025184  mov     [rsp-8+arg_0], rbx
0x140025189  push    rbp
0x14002518a  mov     rbp, rsp
0x14002518d  sub     rsp, 50h
0x140025191  mov     rbx, rcx
0x140025194  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x140025199  test    eax, eax
0x14002519b  jnz     short loc_1400251A7
0x14002519d  mov     eax, 80004005h
0x1400251a2  jmp     loc_14002522E
0x1400251a7  mov     [rbp+var_30], 0
0x1400251af  mov     [rbp+var_28], 0
0x1400251b7  mov     [rbp+var_20], 0
0x1400251bf  lea     rcx, [rbp+var_30]; this
0x1400251c3  call    ?OpenUserConfigKey@SettingsCopier@@CAJAEAVCRegKey@ATL@@K@Z; SettingsCopier::OpenUserConfigKey(ATL::CRegKey &,ulong)
0x1400251c8  test    eax, eax
0x1400251ca  jns     short loc_1400251D7
0x1400251cc  lea     rcx, [rbp+var_30]; this
0x1400251d0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400251d5  jmp     short loc_14002519D
0x1400251d7  mov     [rbp+var_18], 0
0x1400251df  mov     [rbp+var_10], 0
0x1400251e7  mov     [rbp+var_8], 0
0x1400251ef  lea     rdx, [rbp+var_18]; struct ATL::CRegKey *
0x1400251f3  call    ?OpenSessionKey@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@K@Z; SettingsCopier::OpenSessionKey(ATL::CRegKey &,ulong)
0x1400251f8  test    eax, eax
0x1400251fa  js      short loc_140025214
0x1400251fc  lea     r8, [rbp+var_18]; struct ATL::CRegKey *
0x140025200  lea     rdx, [rbp+var_30]; struct ATL::CRegKey *
0x140025204  mov     rcx, rbx; this
0x140025207  call    ?CopyATSettings@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@0@Z; SettingsCopier::CopyATSettings(ATL::CRegKey &,ATL::CRegKey &)
0x14002520c  test    eax, eax
0x14002520e  js      short loc_140025214
0x140025210  xor     ebx, ebx
0x140025212  jmp     short loc_140025219
0x140025214  mov     ebx, 80004005h
0x140025219  lea     rcx, [rbp+var_18]; this
0x14002521d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140025222  nop
0x140025223  lea     rcx, [rbp+var_30]; this
0x140025227  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14002522c  mov     eax, ebx
0x14002522e  mov     rbx, [rsp+50h+arg_0]
0x140025233  add     rsp, 50h
0x140025237  pop     rbp
0x140025238  retn
```
