# SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs(void)

- ea: `0x180008640`
- end: `0x180008674`
- name: `?Dec_nRefs@RefCounter@?$SmartPtr@VCVolumeTrackingDescriptor@@@@QEAAHXZ`
- size: `52`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a360`
- `0x18000ac48`
- `0x18000b1e8`
- `0x18000b5b4`
- `0x18000be90`

## callees

- `0x180008640`
- `0x180008680`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008663`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008663`

## pseudocode

```c
__int64 __fastcall SmartPtr<CVolumeTrackingDescriptor>::RefCounter::Dec_nRefs(_DWORD *a1)
{
  bool v1; // zf
  __int64 result; // rax
  CVolumeTrackingDescriptor *v4; // rcx

  v1 = a1[2]-- == 1;
  result = (unsigned int)a1[2];
  if ( v1 )
  {
    v4 = *(CVolumeTrackingDescriptor **)a1;
    if ( v4 )
      CVolumeTrackingDescriptor::`scalar deleting destructor'(v4);
    operator delete(a1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008640  push    rbx
0x180008642  sub     rsp, 20h
0x180008646  sub     dword ptr [rcx+8], 1
0x18000864a  mov     rbx, rcx
0x18000864d  mov     eax, [rcx+8]
0x180008650  jz      short loc_180008658
0x180008652  add     rsp, 20h
0x180008656  pop     rbx
0x180008657  retn
0x180008658  mov     rcx, [rcx]; this
0x18000865b  test    rcx, rcx
0x18000865e  jnz     short loc_18000866D
0x180008660  mov     rcx, rbx
0x180008663  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008669  xor     eax, eax
0x18000866b  jmp     short loc_180008652
0x18000866d  call    ??_GCVolumeTrackingDescriptor@@QEAAPEAXI@Z; CVolumeTrackingDescriptor::`scalar deleting destructor'(uint)
0x180008672  jmp     short loc_180008660
```
