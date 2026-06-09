# Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)

- ea: `0x180006160`
- end: `0x180006186`
- name: `?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000289c`
- `0x180004118`
- `0x1800046a0`
- `0x180007a88`

## callees

- `0x180006160`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(__int64 *a1)
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
0x180006160  sub     rsp, 28h
0x180006164  mov     rdx, rcx
0x180006167  xor     eax, eax
0x180006169  mov     rcx, [rcx]
0x18000616c  test    rcx, rcx
0x18000616f  jz      short loc_180006181
0x180006171  mov     [rdx], rax
0x180006174  mov     rax, [rcx]
0x180006177  mov     rax, [rax+10h]
0x18000617b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006180  nop
0x180006181  add     rsp, 28h
0x180006185  retn
```
