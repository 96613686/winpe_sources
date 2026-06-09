# RxPowerPolicyCallback

- ea: `0x14001d2a0`
- end: `0x14001d327`
- name: `RxPowerPolicyCallback`
- size: `135`
- prototype: `POWER_SETTING_CALLBACK`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14001d2a0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001d2bd`
- `ntoskrnl!RtlCompareMemory` at `0x14001d2bd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001d2e4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001d2e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001d306`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001d306`

## pseudocode

```c
__int64 __fastcall RxPowerPolicyCallback(LPCGUID SettingGuid, _DWORD *Value, ULONG ValueLength, PVOID Context)
{
  unsigned int v6; // ebx

  if ( RtlCompareMemory(SettingGuid, &GUID_RX_POWER_POLICY, 0x10u) == 16 && ValueLength == 4 && Value )
  {
    v6 = 0;
    ExAcquirePushLockExclusiveEx(&RxPowerContext, 0);
    byte_140038BD8 = (*Value != 0) + 1;
    ExReleasePushLockExclusiveEx(&RxPowerContext, 0);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v6;
}

```

## disassembly

```asm
0x14001d2a0  mov     [rsp+arg_0], rbx
0x14001d2a5  push    rdi
0x14001d2a6  sub     rsp, 20h
0x14001d2aa  mov     ebx, r8d
0x14001d2ad  mov     rdi, rdx
0x14001d2b0  mov     r8d, 10h; Length
0x14001d2b6  lea     rdx, GUID_RX_POWER_POLICY; Source2
0x14001d2bd  call    cs:__imp_RtlCompareMemory
0x14001d2c4  nop     dword ptr [rax+rax+00h]
0x14001d2c9  cmp     rax, 10h
0x14001d2cd  jnz     short loc_14001D314
0x14001d2cf  cmp     ebx, 4
0x14001d2d2  jnz     short loc_14001D314
0x14001d2d4  test    rdi, rdi
0x14001d2d7  jz      short loc_14001D314
0x14001d2d9  xor     edx, edx
0x14001d2db  lea     rcx, RxPowerContext
0x14001d2e2  xor     ebx, ebx
0x14001d2e4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001d2eb  nop     dword ptr [rax+rax+00h]
0x14001d2f0  cmp     [rdi], ebx
0x14001d2f2  lea     rcx, RxPowerContext
0x14001d2f9  setnz   al
0x14001d2fc  xor     edx, edx
0x14001d2fe  inc     al
0x14001d300  mov     cs:byte_140038BD8, al
0x14001d306  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001d30d  nop     dword ptr [rax+rax+00h]
0x14001d312  jmp     short loc_14001D319
0x14001d314  mov     ebx, 0C000000Dh
0x14001d319  mov     eax, ebx
0x14001d31b  mov     rbx, [rsp+28h+arg_0]
0x14001d320  add     rsp, 20h
0x14001d324  pop     rdi
0x14001d325  retn
```
