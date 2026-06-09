# crt_ptr<_EAP_METHOD_INFO>::Assign(_EAP_METHOD_INFO const *)

- ea: `0x180023f90`
- end: `0x180024009`
- name: `?Assign@?$crt_ptr@U_EAP_METHOD_INFO@@@@QEAAXPEBU_EAP_METHOD_INFO@@@Z`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026850`

## callees

- `0x18001a068`
- `0x180023f90`
- `0x1800244c8`
- `0x18002fe84`
- `0x180030994`

## string_xrefs

- `0x180023fe0`: `com_ptr::Assign`

## pseudocode

```c
__int64 __fastcall crt_ptr<_EAP_METHOD_INFO>::Assign(_QWORD *a1, __int64 a2)
{
  _OWORD *v2; // rbx
  _OWORD *v5; // rax
  __int64 result; // rax

  v2 = 0;
  if ( a2 )
  {
    v5 = Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, 0x30u);
    v2 = v5;
    if ( !v5 || (*v5 = 0, v5[1] = 0, v5[2] = 0, !(unsigned __int8)Copy<HeapAllocator>(v5, a2)) )
      LowMemoryError::Throw(L"com_ptr::Assign");
  }
  result = crt_ptr<_EAP_METHOD_INFO>::Clear(a1);
  *a1 = v2;
  return result;
}

```

## disassembly

```asm
0x180023f90  mov     [rsp+arg_0], rbx
0x180023f95  mov     [rsp+arg_8], rsi
0x180023f9a  push    rdi
0x180023f9b  sub     rsp, 20h
0x180023f9f  xor     ebx, ebx
0x180023fa1  mov     rsi, rdx
0x180023fa4  mov     rdi, rcx
0x180023fa7  test    rdx, rdx
0x180023faa  jz      short loc_180023FED
0x180023fac  lea     edx, [rbx+30h]; unsigned __int64
0x180023faf  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180023fb6  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180023fbb  mov     rbx, rax
0x180023fbe  test    rax, rax
0x180023fc1  jz      short loc_180023FE0
0x180023fc3  xorps   xmm0, xmm0
0x180023fc6  mov     rdx, rsi
0x180023fc9  movups  xmmword ptr [rax], xmm0
0x180023fcc  mov     rcx, rax
0x180023fcf  movups  xmmword ptr [rax+10h], xmm0
0x180023fd3  movups  xmmword ptr [rax+20h], xmm0
0x180023fd7  call    ??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_METHOD_INFO@@AEBU0@@Z; Copy<HeapAllocator>(_EAP_METHOD_INFO &,_EAP_METHOD_INFO const &)
0x180023fdc  test    al, al
0x180023fde  jnz     short loc_180023FED
0x180023fe0  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x180023fe7  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180023fed  mov     rcx, rdi
0x180023ff0  call    ?Clear@?$crt_ptr@U_EAP_METHOD_INFO@@@@QEAAXXZ; crt_ptr<_EAP_METHOD_INFO>::Clear(void)
0x180023ff5  mov     rsi, [rsp+28h+arg_8]
0x180023ffa  mov     [rdi], rbx
0x180023ffd  mov     rbx, [rsp+28h+arg_0]
0x180024002  add     rsp, 20h
0x180024006  pop     rdi
0x180024007  retn
```
