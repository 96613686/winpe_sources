# SmartPtr<CVolumeTrackingDescriptor>::operator=(CVolumeTrackingDescriptor *)

- ea: `0x18000b1e8`
- end: `0x18000b24a`
- name: `??4?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAAEAV0@PEAVCVolumeTrackingDescriptor@@@Z`
- size: `98`
- prototype: `_QWORD *__fastcall(_QWORD *, CVolumeTrackingDescriptor *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a360`
- `0x18000ac48`

## callees

- `0x180008640`
- `0x18000b1e8`
- `0x18000cadc`

## pseudocode

```c
_QWORD *__fastcall SmartPtr<CVolumeTrackingDescriptor>::operator=(_QWORD *a1, CVolumeTrackingDescriptor *a2)
{
  _DWORD *v4; // rax
  _QWORD *result; // rax
  __int64 v6; // [rsp+0h] [rbp-28h] BYREF

  if ( *a1 )
    SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs();
  try
  {
    if ( a2 )
    {
      v4 = operator new(0x10u);
      if ( v4 )
      {
        *(_QWORD *)v4 = a2;
        v4[2] = 0;
      }
      *a1 = v4;
      if ( v4 )
        ++v4[2];
    }
    else
    {
      *a1 = 0;
    }
    result = a1;
  }
  catch ( ... )
  {
    CVolumeTrackingDescriptor::`scalar deleting destructor'(a2, (unsigned int)&v6);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000b1e8  mov     [rsp+arg_10], rbx
0x18000b1ed  mov     [rsp+arg_8], rdx
0x18000b1f2  push    rdi
0x18000b1f3  sub     rsp, 20h
0x18000b1f7  mov     rdi, rdx
0x18000b1fa  mov     rbx, rcx
0x18000b1fd  mov     rcx, [rcx]
0x18000b200  test    rcx, rcx
0x18000b203  jz      short loc_18000B20A
0x18000b205  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAHXZ; SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs(void)
0x18000b20a  test    rdi, rdi
0x18000b20d  jz      short loc_18000B235
0x18000b20f  mov     ecx, 10h; Size
0x18000b214  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b219  test    rax, rax
0x18000b21c  jz      short loc_18000B228
0x18000b21e  mov     [rax], rdi
0x18000b221  mov     dword ptr [rax+8], 0
0x18000b228  mov     [rbx], rax
0x18000b22b  test    rax, rax
0x18000b22e  jz      short loc_18000B23C
0x18000b230  inc     dword ptr [rax+8]
0x18000b233  jmp     short loc_18000B23C
0x18000b235  mov     qword ptr [rbx], 0
0x18000b23c  mov     rax, rbx
0x18000b23f  mov     rbx, [rsp+28h+arg_10]
0x18000b244  add     rsp, 20h
0x18000b248  pop     rdi
0x18000b249  retn
```
