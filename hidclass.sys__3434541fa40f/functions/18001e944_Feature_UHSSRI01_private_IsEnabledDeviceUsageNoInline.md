# Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline

- ea: `0x18001e944`
- end: `0x18001e979`
- name: `Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline`
- size: `53`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b70`
- `0x180003f40`
- `0x180011738`
- `0x18001a0b8`
- `0x18003b748`
- `0x18003f2b4`

## callees

- `0x18001e944`
- `0x18001e980`

## pseudocode

```c
__int64 Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline()
{
  if ( ((__int64)WPP_MAIN_CB.Reserved & 0x10) != 0 )
    return (__int64)WPP_MAIN_CB.Reserved & 1;
  else
    return Feature_UHSSRI01__private_IsEnabledFallback(LODWORD(WPP_MAIN_CB.Reserved), 3);
}

```

## disassembly

```asm
0x18001e944  sub     rsp, 28h
0x18001e948  mov     eax, dword ptr cs:WPP_MAIN_CB.Reserved
0x18001e94e  mov     [rsp+28h+arg_0], 0
0x18001e957  mov     dword ptr [rsp+28h+arg_0], eax
0x18001e95b  test    al, 10h
0x18001e95d  jz      short loc_18001E964
0x18001e95f  and     eax, 1
0x18001e962  jmp     short loc_18001E973
0x18001e964  mov     rcx, [rsp+28h+arg_0]
0x18001e969  mov     edx, 3
0x18001e96e  call    Feature_UHSSRI01__private_IsEnabledFallback
0x18001e973  add     rsp, 28h
0x18001e977  retn
```
