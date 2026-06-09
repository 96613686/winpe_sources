# SmartPtr<CVolumeTrackingDescriptor>::operator=(SmartPtr<CVolumeTrackingDescriptor> const &)

- ea: `0x18000b5b4`
- end: `0x18000b5f2`
- name: `??4?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAAEAV0@AEBV0@@Z`
- size: `62`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a360`
- `0x18000ac48`
- `0x18000b4ac`
- `0x18000fe58`

## callees

- `0x180008640`
- `0x18000b5b4`

## pseudocode

```c
__int64 *__fastcall SmartPtr<CVolumeTrackingDescriptor>::operator=(__int64 *a1, __int64 *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rax

  v4 = *a1;
  if ( v4 != *a2 )
  {
    if ( v4 )
      SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs();
    v5 = *a2;
    *a1 = *a2;
    if ( v5 )
      ++*(_DWORD *)(v5 + 8);
  }
  return a1;
}

```

## disassembly

```asm
0x18000b5b4  mov     [rsp+arg_0], rbx
0x18000b5b9  push    rdi
0x18000b5ba  sub     rsp, 20h
0x18000b5be  mov     rbx, rcx
0x18000b5c1  mov     rdi, rdx
0x18000b5c4  mov     rcx, [rcx]
0x18000b5c7  cmp     rcx, [rdx]
0x18000b5ca  jz      short loc_18000B5E4
0x18000b5cc  test    rcx, rcx
0x18000b5cf  jz      short loc_18000B5D6
0x18000b5d1  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAHXZ; SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs(void)
0x18000b5d6  mov     rax, [rdi]
0x18000b5d9  mov     [rbx], rax
0x18000b5dc  test    rax, rax
0x18000b5df  jz      short loc_18000B5E4
0x18000b5e1  inc     dword ptr [rax+8]
0x18000b5e4  mov     rax, rbx
0x18000b5e7  mov     rbx, [rsp+28h+arg_0]
0x18000b5ec  add     rsp, 20h
0x18000b5f0  pop     rdi
0x18000b5f1  retn
```
