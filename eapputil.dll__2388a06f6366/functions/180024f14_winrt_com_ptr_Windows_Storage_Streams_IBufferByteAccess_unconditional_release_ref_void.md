# winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(void)

- ea: `0x180024f14`
- end: `0x180024f37`
- name: `?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@Streams@Storage@Windows@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800174a0`
- `0x180018e1c`
- `0x180019dc4`
- `0x18001a704`
- `0x18001c220`
- `0x18001d6d0`
- `0x18002dd5c`
- `0x18002de70`
- `0x18002e2c8`

## callees

- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<Windows::Storage::Streams::IBufferByteAccess>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180024f14  sub     rsp, 28h
0x180024f18  mov     rdx, [rcx]
0x180024f1b  mov     qword ptr [rcx], 0
0x180024f22  mov     rax, [rdx]
0x180024f25  mov     rcx, rdx
0x180024f28  mov     rax, [rax+10h]
0x180024f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f31  nop
0x180024f32  add     rsp, 28h
0x180024f36  retn
```
