# RepairRASystemSetting(void)

- ea: `0x180011af8`
- end: `0x180011b85`
- name: `?RepairRASystemSetting@@YAJXZ`
- size: `141`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18000ebe0`

## callees

- `0x18000f52c`
- `0x180010d70`
- `0x180011af8`
- `0x180014660`
- `0x180015bb0`
- `0x180015c28`

## string_xrefs

- `0x180011b5a`: `RepairRASystemSetting`

## pseudocode

```c
__int64 RepairRASystemSetting(void)
{
  signed int v0; // eax
  const struct _EVENT_DESCRIPTOR *v1; // rdx
  CEventLogger *v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // r9d
  HANDLE v6; // [rsp+30h] [rbp-28h] BYREF
  __int128 v7; // [rsp+38h] [rbp-20h]
  int v8; // [rsp+48h] [rbp-10h]

  v6 = 0;
  v7 = 0;
  v8 = 0;
  v0 = CSettingsManager::Initialize((CSettingsManager *)&v6);
  v3 = v0;
  if ( v0 < 0 )
  {
    v4 = 498;
LABEL_7:
    CEventLogger::LogError(
      v2,
      v1,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      v4,
      L"RepairRASystemSetting",
      v0);
    goto LABEL_8;
  }
  v0 = CSettingsManager::SetSystemSetting(&v6);
  v3 = v0;
  if ( v0 < 0 )
  {
    v4 = 500;
    goto LABEL_7;
  }
  v0 = EnableRAFirewallGroup();
  v3 = v0;
  if ( v0 < 0 )
  {
    v4 = 511;
    goto LABEL_7;
  }
LABEL_8:
  CSettingsManager::~CSettingsManager((CSettingsManager *)&v6);
  return v3;
}

```

## disassembly

```asm
0x180011af8  push    rbx
0x180011afa  sub     rsp, 50h
0x180011afe  mov     [rsp+58h+var_28], 0
0x180011b07  xorps   xmm0, xmm0
0x180011b0a  xor     eax, eax
0x180011b0c  movups  [rsp+58h+var_20], xmm0
0x180011b11  mov     [rsp+58h+var_10], eax
0x180011b15  lea     rcx, [rsp+58h+var_28]; this
0x180011b1a  call    ?Initialize@CSettingsManager@@QEAAJXZ; CSettingsManager::Initialize(void)
0x180011b1f  mov     ebx, eax
0x180011b21  test    eax, eax
0x180011b23  jns     short loc_180011B2D
0x180011b25  mov     r9d, 1F2h
0x180011b2b  jmp     short loc_180011B56
0x180011b2d  lea     rcx, [rsp+58h+var_28]
0x180011b32  call    ?SetSystemSetting@CSettingsManager@@QEAAJW4_RASystemSetting@@K@Z; CSettingsManager::SetSystemSetting(_RASystemSetting,ulong)
0x180011b37  mov     ebx, eax
0x180011b39  test    eax, eax
0x180011b3b  jns     short loc_180011B45
0x180011b3d  mov     r9d, 1F4h
0x180011b43  jmp     short loc_180011B56
0x180011b45  call    ?EnableRAFirewallGroup@@YAJXZ; EnableRAFirewallGroup(void)
0x180011b4a  mov     ebx, eax
0x180011b4c  test    eax, eax
0x180011b4e  jns     short loc_180011B73
0x180011b50  mov     r9d, 1FFh; unsigned int
0x180011b56  mov     [rsp+58h+var_30], eax; unsigned int
0x180011b5a  lea     rax, aRepairrasystem; "RepairRASystemSetting"
0x180011b61  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180011b66  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x180011b6d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180011b72  nop
0x180011b73  lea     rcx, [rsp+58h+var_28]; this
0x180011b78  call    ??1CSettingsManager@@QEAA@XZ; CSettingsManager::~CSettingsManager(void)
0x180011b7d  mov     eax, ebx
0x180011b7f  add     rsp, 50h
0x180011b83  pop     rbx
0x180011b84  retn
```
