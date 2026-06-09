# SmartPtr<CConfigDescriptor>::operator=(CConfigDescriptor *)

- ea: `0x18000eefc`
- end: `0x18000ef5e`
- name: `??4?$SmartPtr@VCConfigDescriptor@@@@QEAAAEAV0@PEAVCConfigDescriptor@@@Z`
- size: `98`
- prototype: `_QWORD *__fastcall(_QWORD *, CConfigDescriptor *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003f00`
- `0x18000aa08`

## callees

- `0x180004e50`
- `0x18000cadc`
- `0x18000eefc`

## pseudocode

```c
_QWORD *__fastcall SmartPtr<CConfigDescriptor>::operator=(_QWORD *a1, CConfigDescriptor *a2)
{
  __int64 v4; // rcx
  _DWORD *v5; // rax
  _QWORD *result; // rax
  __int64 v7; // [rsp+0h] [rbp-28h] BYREF

  v4 = *a1;
  if ( v4 )
    SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(v4);
  try
  {
    if ( a2 )
    {
      v5 = operator new(0x10u);
      if ( v5 )
      {
        *(_QWORD *)v5 = a2;
        v5[2] = 0;
      }
      *a1 = v5;
      if ( v5 )
        ++v5[2];
    }
    else
    {
      *a1 = 0;
    }
    result = a1;
  }
  catch ( ... )
  {
    CConfigDescriptor::`scalar deleting destructor'(a2, (unsigned int)&v7);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000eefc  mov     [rsp+arg_10], rbx
0x18000ef01  mov     [rsp+arg_8], rdx
0x18000ef06  push    rdi
0x18000ef07  sub     rsp, 20h
0x18000ef0b  mov     rdi, rdx
0x18000ef0e  mov     rbx, rcx
0x18000ef11  mov     rcx, [rcx]
0x18000ef14  test    rcx, rcx
0x18000ef17  jz      short loc_18000EF1E
0x18000ef19  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x18000ef1e  test    rdi, rdi
0x18000ef21  jz      short loc_18000EF49
0x18000ef23  mov     ecx, 10h; Size
0x18000ef28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ef2d  test    rax, rax
0x18000ef30  jz      short loc_18000EF3C
0x18000ef32  mov     [rax], rdi
0x18000ef35  mov     dword ptr [rax+8], 0
0x18000ef3c  mov     [rbx], rax
0x18000ef3f  test    rax, rax
0x18000ef42  jz      short loc_18000EF50
0x18000ef44  inc     dword ptr [rax+8]
0x18000ef47  jmp     short loc_18000EF50
0x18000ef49  mov     qword ptr [rbx], 0
0x18000ef50  mov     rax, rbx
0x18000ef53  mov     rbx, [rsp+28h+arg_10]
0x18000ef58  add     rsp, 20h
0x18000ef5c  pop     rdi
0x18000ef5d  retn
```
