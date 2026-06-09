# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmpty(void)

- ea: `0x18000ab18`
- end: `0x18000ab2c`
- name: `?IsEmpty@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ`
- size: `20`
- prototype: `char __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000ac1c`

## callees

- `0x18000ab18`

## pseudocode

```c
char __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmpty(
        _QWORD *a1)
{
  char result; // al

  if ( !*a1 )
    return 1;
  result = 0;
  if ( !*(_WORD *)*a1 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18000ab18  mov     rax, [rcx]
0x18000ab1b  xor     ecx, ecx
0x18000ab1d  test    rax, rax
0x18000ab20  jz      short loc_18000AB29
0x18000ab22  cmp     [rax], cx
0x18000ab25  mov     al, cl
0x18000ab27  jnz     short locret_18000AB2B
0x18000ab29  mov     al, 1
0x18000ab2b  retn
```
