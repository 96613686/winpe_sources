# HvSysConfigTimer::LogSysConfig(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180008700`
- end: `0x180008738`
- name: `?LogSysConfig@HvSysConfigTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `56`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, HANDLE **Context, PTP_TIMER Timer)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800084f4`

## callees

- `0x180007594`
- `0x180008700`

## pseudocode

```c
void __fastcall HvSysConfigTimer::LogSysConfig(PTP_CALLBACK_INSTANCE Instance, HANDLE **Context, PTP_TIMER Timer)
{
  if ( Context && *Context )
  {
    try
    {
      HvServiceUtil::Ioctl(*Context, 0x228050u, 0, 0, 0, 0);
    }
    catch ( ... )
    {
    }
  }
}

```

## disassembly

```asm
0x180008700  sub     rsp, 38h
0x180008704  test    rdx, rdx
0x180008707  jz      short loc_180008733
0x180008709  mov     rcx, [rdx]; this
0x18000870c  test    rcx, rcx
0x18000870f  jz      short loc_180008733
0x180008711  mov     [rsp+38h+var_10], 0; DWORD
0x180008719  mov     [rsp+38h+var_18], 0; void *
0x180008722  xor     r9d, r9d; unsigned int
0x180008725  xor     r8d, r8d; void *
0x180008728  mov     edx, 228050h; unsigned int
0x18000872d  call    ?Ioctl@HvServiceUtil@@AEBAXKPEBXKPEAXK@Z; HvServiceUtil::Ioctl(ulong,void const *,ulong,void *,ulong)
0x180008732  nop
0x180008733  add     rsp, 38h
0x180008737  retn
```
