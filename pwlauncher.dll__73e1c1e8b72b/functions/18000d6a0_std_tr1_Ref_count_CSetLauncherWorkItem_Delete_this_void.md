# std::tr1::_Ref_count<CSetLauncherWorkItem>::_Delete_this(void)

- ea: `0x18000d6a0`
- end: `0x18000d6bf`
- name: `?_Delete_this@?$_Ref_count@VCSetLauncherWorkItem@@@tr1@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d6a0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall std::tr1::_Ref_count<CSetLauncherWorkItem>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000d6a0  sub     rsp, 28h
0x18000d6a4  test    rcx, rcx
0x18000d6a7  jz      short loc_18000D6BA
0x18000d6a9  mov     rax, [rcx]
0x18000d6ac  mov     edx, 1
0x18000d6b1  mov     rax, [rax+10h]
0x18000d6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ba  add     rsp, 28h
0x18000d6be  retn
```
