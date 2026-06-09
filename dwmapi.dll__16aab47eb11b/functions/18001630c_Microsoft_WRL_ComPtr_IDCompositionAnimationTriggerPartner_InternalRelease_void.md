# Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(void)

- ea: `0x18001630c`
- end: `0x180016331`
- name: `?InternalRelease@?$ComPtr@UIDCompositionAnimationTriggerPartner@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015a98`
- `0x180015f90`

## callees

- `0x18001630c`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(__int64 *a1)
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
0x18001630c  sub     rsp, 28h
0x180016310  mov     rdx, rcx
0x180016313  xor     eax, eax
0x180016315  mov     rcx, [rcx]
0x180016318  test    rcx, rcx
0x18001631b  jz      short loc_18001632C
0x18001631d  mov     [rdx], rax
0x180016320  mov     rax, [rcx]
0x180016323  mov     rax, [rax+10h]
0x180016327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001632c  add     rsp, 28h
0x180016330  retn
```
