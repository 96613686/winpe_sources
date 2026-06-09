# Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(void)

- ea: `0x180006794`
- end: `0x1800067b9`
- name: `?InternalRelease@?$ComPtr@UIFileDialog@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800046d0`
- `0x18000c714`

## callees

- `0x180006794`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IFileDialog>::InternalRelease(__int64 *a1)
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
0x180006794  sub     rsp, 28h
0x180006798  mov     rdx, rcx
0x18000679b  xor     eax, eax
0x18000679d  mov     rcx, [rcx]
0x1800067a0  test    rcx, rcx
0x1800067a3  jz      short loc_1800067B4
0x1800067a5  mov     [rdx], rax
0x1800067a8  mov     rax, [rcx]
0x1800067ab  mov     rax, [rax+10h]
0x1800067af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067b4  add     rsp, 28h
0x1800067b8  retn
```
