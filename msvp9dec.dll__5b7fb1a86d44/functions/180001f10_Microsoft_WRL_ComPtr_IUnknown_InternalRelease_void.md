# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180001f10`
- end: `0x180001f31`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ad0`

## callees

- `0x180001f10`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( !v2 )
    return 0;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x180001f10  mov     rax, rcx
0x180001f13  xor     edx, edx
0x180001f15  mov     rcx, [rcx]
0x180001f18  test    rcx, rcx
0x180001f1b  jz      short loc_180001F2D
0x180001f1d  mov     [rax], rdx
0x180001f20  mov     rax, [rcx]
0x180001f23  mov     rax, [rax+10h]
0x180001f27  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001f2c  retn
0x180001f2d  mov     eax, edx
0x180001f2f  jmp     short locret_180001F2C
```
