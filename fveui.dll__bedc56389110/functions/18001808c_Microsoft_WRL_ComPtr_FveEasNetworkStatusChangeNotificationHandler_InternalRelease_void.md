# Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(void)

- ea: `0x18001808c`
- end: `0x1800180b2`
- name: `?InternalRelease@?$ComPtr@VFveEasNetworkStatusChangeNotificationHandler@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001535c`
- `0x1800153f4`
- `0x1800154b0`
- `0x1800154f0`
- `0x180016628`
- `0x180017dec`
- `0x180018620`

## callees

- `0x18001808c`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<FveEasNetworkStatusChangeNotificationHandler>::InternalRelease(__int64 *a1)
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
0x18001808c  sub     rsp, 28h
0x180018090  mov     rdx, rcx
0x180018093  xor     eax, eax
0x180018095  mov     rcx, [rcx]
0x180018098  test    rcx, rcx
0x18001809b  jz      short loc_1800180AD
0x18001809d  mov     [rdx], rax
0x1800180a0  mov     rax, [rcx]
0x1800180a3  mov     rax, [rax+10h]
0x1800180a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180ac  nop
0x1800180ad  add     rsp, 28h
0x1800180b1  retn
```
