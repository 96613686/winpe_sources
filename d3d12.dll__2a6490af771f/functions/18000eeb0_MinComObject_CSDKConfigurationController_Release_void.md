# MinComObject<CSDKConfigurationController>::Release(void)

- ea: `0x18000eeb0`
- end: `0x18000eedf`
- name: `?Release@?$MinComObject@VCSDKConfigurationController@@@@UEAAKXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000eeb0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall MinComObject<CSDKConfigurationController>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 48LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x18000eeb0  push    rbx
0x18000eeb2  sub     rsp, 20h
0x18000eeb6  or      ebx, 0FFFFFFFFh
0x18000eeb9  lock xadd [rcx+8], ebx
0x18000eebe  sub     ebx, 1
0x18000eec1  jnz     short loc_18000EED7
0x18000eec3  test    rcx, rcx
0x18000eec6  jz      short loc_18000EED7
0x18000eec8  mov     rdx, [rcx]
0x18000eecb  mov     rax, [rdx+30h]
0x18000eecf  lea     edx, [rbx+1]
0x18000eed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed7  mov     eax, ebx
0x18000eed9  add     rsp, 20h
0x18000eedd  pop     rbx
0x18000eede  retn
```
