# Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)

- ea: `0x180005aa0`
- end: `0x180005ac6`
- name: `?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004b00`
- `0x1800078e0`
- `0x180017fe4`
- `0x180018c78`
- `0x1800194d0`

## callees

- `0x180005aa0`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(__int64 *a1)
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
0x180005aa0  sub     rsp, 28h
0x180005aa4  mov     rdx, rcx
0x180005aa7  xor     eax, eax
0x180005aa9  mov     rcx, [rcx]
0x180005aac  test    rcx, rcx
0x180005aaf  jz      short loc_180005AC1
0x180005ab1  mov     [rdx], rax
0x180005ab4  mov     rax, [rcx]
0x180005ab7  mov     rax, [rax+10h]
0x180005abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac0  nop
0x180005ac1  add     rsp, 28h
0x180005ac5  retn
```
