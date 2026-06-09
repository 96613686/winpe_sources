# sub_1800ED3EC

- ea: `0x1800ed3ec`
- end: `0x1800ed446`
- name: `sub_1800ED3EC`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800ed3c0`

## callees

- `0x1800ed3ec`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1800ed3fc`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1800ed3fc`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1800ed41f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1800ed41f`

## pseudocode

```c
__int64 sub_1800ED3EC()
{
  __int64 result; // rax

  if ( qword_1800DBCC0 )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    qword_1800DBCC0 = 0;
  }
  if ( qword_1800DAE80 )
  {
    result = RtlUnregisterFeatureUsageProvider();
    qword_1800DAE80 = 0;
  }
  dword_1800DBCC8 = 0;
  return result;
}

```

## disassembly

```asm
0x1800ed3ec  sub     rsp, 28h
0x1800ed3f0  mov     rcx, cs:qword_1800DBCC0
0x1800ed3f7  test    rcx, rcx
0x1800ed3fa  jz      short loc_1800ED413
0x1800ed3fc  call    cs:RtlUnregisterFeatureConfigurationChangeNotification
0x1800ed403  nop     dword ptr [rax+rax+00h]
0x1800ed408  mov     cs:qword_1800DBCC0, 0
0x1800ed413  mov     rcx, cs:qword_1800DAE80
0x1800ed41a  test    rcx, rcx
0x1800ed41d  jz      short loc_1800ED436
0x1800ed41f  call    cs:RtlUnregisterFeatureUsageProvider
0x1800ed426  nop     dword ptr [rax+rax+00h]
0x1800ed42b  mov     cs:qword_1800DAE80, 0
0x1800ed436  mov     cs:dword_1800DBCC8, 0
0x1800ed440  add     rsp, 28h
0x1800ed444  retn
```
