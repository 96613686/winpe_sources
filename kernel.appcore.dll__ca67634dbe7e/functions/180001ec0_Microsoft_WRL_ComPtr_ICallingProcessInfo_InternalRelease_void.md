# Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)

- ea: `0x180001ec0`
- end: `0x180001ee1`
- name: `?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001920`
- `0x180001e20`

## callees

- `0x180001ec0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(__int64 *a1)
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
0x180001ec0  mov     rax, rcx
0x180001ec3  xor     edx, edx
0x180001ec5  mov     rcx, [rcx]
0x180001ec8  test    rcx, rcx
0x180001ecb  jz      short loc_180001EDD
0x180001ecd  mov     [rax], rdx
0x180001ed0  mov     rax, [rcx]
0x180001ed3  mov     rax, [rax+10h]
0x180001ed7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001edc  retn
0x180001edd  mov     eax, edx
0x180001edf  jmp     short locret_180001EDC
```
