# Windows::AutoComPtr<IClassFactory>::Close(void)

- ea: `0x140024a70`
- end: `0x140024a9a`
- name: `?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140024980`
- `0x1400249e0`
- `0x140024c30`

## callees

- `0x140024a70`
- `0x14002a010`

## pseudocode

```c
__int64 __fastcall Windows::AutoComPtr<IClassFactory>::Close(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140024a70  push    rbx
0x140024a72  sub     rsp, 20h
0x140024a76  mov     rbx, rcx
0x140024a79  mov     rcx, [rcx]
0x140024a7c  test    rcx, rcx
0x140024a7f  jz      short loc_140024A94
0x140024a81  mov     rax, [rcx]
0x140024a84  mov     rax, [rax+10h]
0x140024a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024a8d  mov     qword ptr [rbx], 0
0x140024a94  add     rsp, 20h
0x140024a98  pop     rbx
0x140024a99  retn
```
