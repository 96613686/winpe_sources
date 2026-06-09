# Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)

- ea: `0x1800050e0`
- end: `0x180005107`
- name: `?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003994`
- `0x180003eec`
- `0x180006138`
- `0x1800064a0`
- `0x180006730`
- `0x180006dc0`

## callees

- `0x1800050e0`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(__int64 *a1)
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
0x1800050e0  sub     rsp, 28h
0x1800050e4  mov     rdx, rcx
0x1800050e7  xor     eax, eax
0x1800050e9  mov     rcx, [rcx]
0x1800050ec  test    rcx, rcx
0x1800050ef  jz      short loc_180005101
0x1800050f1  mov     [rdx], rax
0x1800050f4  mov     rax, [rcx]
0x1800050f7  mov     rax, [rax+10h]
0x1800050fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005100  nop
0x180005101  add     rsp, 28h
0x180005105  retn
```
