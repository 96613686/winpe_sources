# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)

- ea: `0x14000e884`
- end: `0x14000e8aa`
- name: `?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a7b0`
- `0x14000e5e4`
- `0x14000e878`

## callees

- `0x14000e884`
- `0x14001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(
        __int64 *a1)
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
0x14000e884  sub     rsp, 28h
0x14000e888  mov     rdx, rcx
0x14000e88b  xor     eax, eax
0x14000e88d  mov     rcx, [rcx]
0x14000e890  test    rcx, rcx
0x14000e893  jz      short loc_14000E8A5
0x14000e895  mov     [rdx], rax
0x14000e898  mov     rax, [rcx]
0x14000e89b  mov     rax, [rax+10h]
0x14000e89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e8a4  nop
0x14000e8a5  add     rsp, 28h
0x14000e8a9  retn
```
