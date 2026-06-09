# SmartPtr<CConfigDescriptor>::operator=(SmartPtr<CConfigDescriptor> const &)

- ea: `0x1800011b0`
- end: `0x1800011f2`
- name: `??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@AEBV0@@Z`
- size: `66`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800020c0`
- `0x180003f00`
- `0x18000aa08`
- `0x18000ac48`
- `0x18000f14c`
- `0x18000f2c0`

## callees

- `0x1800011b0`
- `0x180004e50`

## pseudocode

```c
__int64 *__fastcall SmartPtr<CConfigDescriptor>::operator=(__int64 *a1, __int64 *a2)
{
  __int64 v4; // rcx
  __int64 v6; // rax

  v4 = *a1;
  if ( v4 != *a2 )
  {
    if ( v4 )
      SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(v4);
    v6 = *a2;
    *a1 = *a2;
    if ( v6 )
      ++*(_DWORD *)(v6 + 8);
  }
  return a1;
}

```

## disassembly

```asm
0x1800011b0  mov     [rsp+arg_0], rbx
0x1800011b5  push    rdi
0x1800011b6  sub     rsp, 20h
0x1800011ba  mov     rbx, rcx
0x1800011bd  mov     rdi, rdx
0x1800011c0  mov     rcx, [rcx]
0x1800011c3  cmp     rcx, [rdx]
0x1800011c6  jnz     short loc_1800011D6
0x1800011c8  mov     rax, rbx
0x1800011cb  mov     rbx, [rsp+28h+arg_0]
0x1800011d0  add     rsp, 20h
0x1800011d4  pop     rdi
0x1800011d5  retn
0x1800011d6  test    rcx, rcx
0x1800011d9  jnz     short loc_1800011EB
0x1800011db  mov     rax, [rdi]
0x1800011de  mov     [rbx], rax
0x1800011e1  test    rax, rax
0x1800011e4  jz      short loc_1800011C8
0x1800011e6  inc     dword ptr [rax+8]
0x1800011e9  jmp     short loc_1800011C8
0x1800011eb  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x1800011f0  jmp     short loc_1800011DB
```
