# SslCopyTlsExtensions

- ea: `0x18000e820`
- end: `0x18000e892`
- name: `SslCopyTlsExtensions`
- size: `114`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, char, __int64, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000e7c4`
- `0x18000e820`
- `0x180010920`

## pseudocode

```c
__int64 __fastcall SslCopyTlsExtensions(__int64 a1, unsigned int a2, __int64 a3, char a4, __int64 a5, int a6)
{
  __int64 v10; // r9
  struct _LIST_ENTRY *Blink; // rax

  if ( !(unsigned int)Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledDeviceUsageNoInline() )
    return 2148074242LL;
  if ( !WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink )
    return 3221225474LL;
  Blink = WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink[4].Blink;
  if ( !Blink )
    return 3221225474LL;
  LOBYTE(v10) = a4;
  return ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, __int64, int))Blink)(a1, a2, a3, v10, a5, a6);
}

```

## disassembly

```asm
0x18000e820  push    rbx
0x18000e822  push    rbp
0x18000e823  push    rsi
0x18000e824  push    rdi
0x18000e825  sub     rsp, 48h
0x18000e829  mov     bl, r9b
0x18000e82c  mov     rdi, r8
0x18000e82f  mov     esi, edx
0x18000e831  mov     rbp, rcx
0x18000e834  call    Feature_Schannel_SslCopyTlsExtensions__private_IsEnabledDeviceUsageNoInline
0x18000e839  test    eax, eax
0x18000e83b  jnz     short loc_18000E844
0x18000e83d  mov     eax, 80090302h
0x18000e842  jmp     short loc_18000E888
0x18000e844  mov     rax, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink
0x18000e84b  test    rax, rax
0x18000e84e  jz      short loc_18000E883
0x18000e850  mov     rax, [rax+48h]
0x18000e854  test    rax, rax
0x18000e857  jz      short loc_18000E883
0x18000e859  mov     ecx, [rsp+68h+arg_28]
0x18000e860  mov     r9b, bl
0x18000e863  mov     [rsp+68h+var_40], ecx
0x18000e867  mov     r8, rdi
0x18000e86a  mov     rcx, [rsp+68h+arg_20]
0x18000e872  mov     edx, esi
0x18000e874  mov     [rsp+68h+var_48], rcx
0x18000e879  mov     rcx, rbp
0x18000e87c  call    _guard_dispatch_icall
0x18000e881  jmp     short loc_18000E888
0x18000e883  mov     eax, 0C0000002h
0x18000e888  add     rsp, 48h
0x18000e88c  pop     rdi
0x18000e88d  pop     rsi
0x18000e88e  pop     rbp
0x18000e88f  pop     rbx
0x18000e890  retn
```
