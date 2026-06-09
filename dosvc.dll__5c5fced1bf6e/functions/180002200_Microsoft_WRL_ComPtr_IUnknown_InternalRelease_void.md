# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180002200`
- end: `0x18000222d`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `45`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f60`
- `0x18000a4d0`

## callees

- `0x180002200`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( !v2 )
    return 0;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x180002200  sub     rsp, 28h
0x180002204  mov     rax, rcx
0x180002207  xor     edx, edx
0x180002209  mov     rcx, [rcx]
0x18000220c  test    rcx, rcx
0x18000220f  jz      short loc_180002226
0x180002211  mov     [rax], rdx
0x180002214  mov     rax, [rcx]
0x180002217  mov     rax, [rax+10h]
0x18000221b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002220  nop
0x180002221  add     rsp, 28h
0x180002225  retn
0x180002226  mov     eax, edx
0x180002228  add     rsp, 28h
0x18000222c  retn
```
