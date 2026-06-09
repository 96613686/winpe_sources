# SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(void)

- ea: `0x18000be90`
- end: `0x18000bea6`
- name: `??1?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a360`
- `0x18000b65c`
- `0x18000ee9c`
- `0x180011da6`

## callees

- `0x180008640`
- `0x18000be90`

## pseudocode

```c
__int64 __fastcall SmartPtr<CVolumeTrackingDescriptor>::~SmartPtr<CVolumeTrackingDescriptor>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs();
  return result;
}

```

## disassembly

```asm
0x18000be90  sub     rsp, 28h
0x18000be94  mov     rcx, [rcx]
0x18000be97  test    rcx, rcx
0x18000be9a  jz      short loc_18000BEA1
0x18000be9c  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAHXZ; SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs(void)
0x18000bea1  add     rsp, 28h
0x18000bea5  retn
```
