# winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)

- ea: `0x1800083ec`
- end: `0x180008405`
- name: `?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `103`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800080ec`
- `0x180008194`
- `0x18000831c`
- `0x180008760`
- `0x18000cf00`
- `0x18000d0c0`
- `0x18000d120`
- `0x18000db40`
- `0x18000e4c0`
- `0x18000e740`
- `0x18000eaf0`
- `0x18000ebb8`
- `0x18000ec20`
- `0x18000ed30`
- `0x18000ed80`
- `0x18000f5c0`
- `0x18000f900`
- `0x180010210`
- `0x1800103b0`
- `0x180010550`
- `0x180010910`
- `0x180010ab0`
- `0x180010c50`
- `0x180011030`
- `0x18001109c`
- `0x1800112ec`
- `0x18001156c`
- `0x180011618`
- `0x1800116ac`
- `0x1800117d0`
- `0x180011b70`
- `0x180011be0`
- `0x180011e80`
- `0x180011fa0`
- `0x180012580`
- `0x1800126d0`
- `0x1800127e0`
- `0x1800129e0`
- `0x180012b00`
- `0x180012f40`
- `0x18001336c`
- `0x1800134b0`
- `0x180013520`
- `0x180013650`
- `0x180015bec`
- `0x180015de0`
- `0x1800178dc`
- `0x180017a28`
- `0x180017aa8`
- `0x180018580`

## callees

- `0x180033010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1800083ec  mov     rdx, [rcx]
0x1800083ef  mov     qword ptr [rcx], 0
0x1800083f6  mov     rcx, rdx
0x1800083f9  mov     rax, [rdx]
0x1800083fc  mov     rax, [rax+10h]
0x180008400  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
