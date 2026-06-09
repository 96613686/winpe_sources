# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180005904`
- end: `0x180005929`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006c5c`
- `0x1800070cc`
- `0x1800072cc`
- `0x18000888c`
- `0x180009de8`
- `0x18000a640`
- `0x1800130dc`

## callees

- `0x180005904`
- `0x18001a010`

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
0x180005904  sub     rsp, 28h
0x180005908  mov     rdx, rcx
0x18000590b  xor     eax, eax
0x18000590d  mov     rcx, [rcx]
0x180005910  test    rcx, rcx
0x180005913  jz      short loc_180005924
0x180005915  mov     [rdx], rax
0x180005918  mov     rax, [rcx]
0x18000591b  mov     rax, [rax+10h]
0x18000591f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005924  add     rsp, 28h
0x180005928  retn
```
