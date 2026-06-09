# Microsoft::WRL::ComPtr<IDOService>::InternalRelease(void)

- ea: `0x1800021d0`
- end: `0x1800021f6`
- name: `?InternalRelease@?$ComPtr@UIDOService@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001f60`

## callees

- `0x1800021d0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IDOService>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x1800021d0  sub     rsp, 28h
0x1800021d4  mov     rdx, rcx
0x1800021d7  xor     eax, eax
0x1800021d9  mov     rcx, [rcx]
0x1800021dc  test    rcx, rcx
0x1800021df  jz      short loc_1800021F1
0x1800021e1  mov     [rdx], rax
0x1800021e4  mov     rax, [rcx]
0x1800021e7  mov     rax, [rax+10h]
0x1800021eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021f0  nop
0x1800021f1  add     rsp, 28h
0x1800021f5  retn
```
