# Microsoft::WRL::ComPtr<IWpnAppEndpoint>::InternalRelease(void)

- ea: `0x18000a9d4`
- end: `0x18000a9fa`
- name: `?InternalRelease@?$ComPtr@UIWpnAppEndpoint@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac1c`

## callees

- `0x18000a9d4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IWpnAppEndpoint>::InternalRelease(__int64 *a1)
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
0x18000a9d4  sub     rsp, 28h
0x18000a9d8  mov     rdx, rcx
0x18000a9db  xor     eax, eax
0x18000a9dd  mov     rcx, [rcx]
0x18000a9e0  test    rcx, rcx
0x18000a9e3  jz      short loc_18000A9F5
0x18000a9e5  mov     [rdx], rax
0x18000a9e8  mov     rax, [rcx]
0x18000a9eb  mov     rax, [rax+10h]
0x18000a9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9f4  nop
0x18000a9f5  add     rsp, 28h
0x18000a9f9  retn
```
