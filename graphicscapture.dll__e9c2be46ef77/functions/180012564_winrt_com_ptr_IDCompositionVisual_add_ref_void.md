# winrt::com_ptr<IDCompositionVisual>::add_ref(void)

- ea: `0x180012564`
- end: `0x180012582`
- name: `?add_ref@?$com_ptr@UIDCompositionVisual@@@winrt@@AEBAXXZ`
- size: `30`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d974`
- `0x180011128`
- `0x1800175a8`
- `0x180019190`
- `0x180019540`
- `0x18001e8ec`
- `0x18001efbc`

## callees

- `0x180012564`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IDCompositionVisual>::add_ref(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180012564  sub     rsp, 28h
0x180012568  mov     rcx, [rcx]
0x18001256b  test    rcx, rcx
0x18001256e  jz      short loc_18001257D
0x180012570  mov     rax, [rcx]
0x180012573  mov     rax, [rax+8]
0x180012577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001257c  nop
0x18001257d  add     rsp, 28h
0x180012581  retn
```
