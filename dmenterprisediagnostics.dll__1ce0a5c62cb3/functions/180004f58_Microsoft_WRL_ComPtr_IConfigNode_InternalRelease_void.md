# Microsoft::WRL::ComPtr<IConfigNode>::InternalRelease(void)

- ea: `0x180004f58`
- end: `0x180004f7e`
- name: `?InternalRelease@?$ComPtr@UIConfigNode@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003934`
- `0x180003ec8`
- `0x180005f0c`
- `0x180006250`
- `0x1800064dc`
- `0x180006b40`

## callees

- `0x180004f58`
- `0x180026010`

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
0x180004f58  sub     rsp, 28h
0x180004f5c  mov     rdx, rcx
0x180004f5f  xor     eax, eax
0x180004f61  mov     rcx, [rcx]
0x180004f64  test    rcx, rcx
0x180004f67  jz      short loc_180004F79
0x180004f69  mov     [rdx], rax
0x180004f6c  mov     rax, [rcx]
0x180004f6f  mov     rax, [rax+10h]
0x180004f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f78  nop
0x180004f79  add     rsp, 28h
0x180004f7d  retn
```
