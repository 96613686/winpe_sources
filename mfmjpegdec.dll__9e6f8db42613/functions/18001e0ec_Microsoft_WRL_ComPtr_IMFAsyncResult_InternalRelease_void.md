# Microsoft::WRL::ComPtr<IMFAsyncResult>::InternalRelease(void)

- ea: `0x18001e0ec`
- end: `0x18001e109`
- name: `?InternalRelease@?$ComPtr@UIMFAsyncResult@@@WRL@Microsoft@@IEAAKXZ`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021080`
- `0x180021ca0`
- `0x180069b14`

## callees

- `0x18001e0ec`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IMFAsyncResult>::InternalRelease(__int64 *a1)
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
0x18001e0ec  mov     rdx, rcx
0x18001e0ef  xor     eax, eax
0x18001e0f1  mov     rcx, [rcx]
0x18001e0f4  test    rcx, rcx
0x18001e0f7  jnz     short loc_18001E0FA
0x18001e0f9  retn
0x18001e0fa  mov     [rdx], rax
0x18001e0fd  mov     rax, [rcx]
0x18001e100  mov     rax, [rax+10h]
0x18001e104  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
