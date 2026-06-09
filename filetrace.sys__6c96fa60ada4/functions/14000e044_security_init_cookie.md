# __security_init_cookie

- ea: `0x14000e044`
- end: `0x14000e072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e010`

## callees

- `0x14000e044`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  if ( !WmiRegistrationContext.DeviceExtension || WmiRegistrationContext.DeviceExtension == (PVOID)0x2B992DDFA232LL )
    __fastfail(6u);
  *(_QWORD *)&WmiRegistrationContext.DeviceType = ~(__int64)WmiRegistrationContext.DeviceExtension;
}

```

## disassembly

```asm
0x14000e044  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000e04b  test    rax, rax
0x14000e04e  jz      short loc_14000E06B
0x14000e050  mov     rcx, 2B992DDFA232h
0x14000e05a  cmp     rax, rcx
0x14000e05d  jz      short loc_14000E06B
0x14000e05f  not     rax
0x14000e062  mov     qword ptr cs:WmiRegistrationContext.DeviceType, rax
0x14000e069  retn
0x14000e06b  mov     ecx, 6
0x14000e070  int     29h; Win8: RtlFailFast(ecx)
```
