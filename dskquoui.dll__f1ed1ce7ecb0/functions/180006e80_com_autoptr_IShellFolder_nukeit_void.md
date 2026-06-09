# com_autoptr<IShellFolder>::nukeit(void)

- ea: `0x180006e80`
- end: `0x180006e9e`
- name: `?nukeit@?$com_autoptr@UIShellFolder@@@@EEAAXXZ`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006e80`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall com_autoptr<IShellFolder>::nukeit(__int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 16);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180006e80  sub     rsp, 28h
0x180006e84  mov     rcx, [rcx+10h]
0x180006e88  test    rcx, rcx
0x180006e8b  jz      short loc_180006E99
0x180006e8d  mov     rax, [rcx]
0x180006e90  mov     rax, [rax+10h]
0x180006e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e99  add     rsp, 28h
0x180006e9d  retn
```
