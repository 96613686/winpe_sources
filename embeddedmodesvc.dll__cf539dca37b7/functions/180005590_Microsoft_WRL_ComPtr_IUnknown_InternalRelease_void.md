# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180005590`
- end: `0x1800055b6`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a748`
- `0x18000ad2c`
- `0x18000b190`
- `0x180010494`
- `0x1800106fc`
- `0x180010d40`
- `0x18001245c`
- `0x1800151f8`
- `0x180015234`
- `0x180015930`
- `0x180015e98`

## callees

- `0x180005590`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
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
0x180005590  sub     rsp, 28h
0x180005594  mov     rdx, rcx
0x180005597  xor     eax, eax
0x180005599  mov     rcx, [rcx]
0x18000559c  test    rcx, rcx
0x18000559f  jz      short loc_1800055B1
0x1800055a1  mov     [rdx], rax
0x1800055a4  mov     rax, [rcx]
0x1800055a7  mov     rax, [rax+10h]
0x1800055ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b0  nop
0x1800055b1  add     rsp, 28h
0x1800055b5  retn
```
