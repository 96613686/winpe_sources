# crt_ptr<_EAP_ERROR>::Assign(_EAP_ERROR const *)

- ea: `0x180023f10`
- end: `0x180023f89`
- name: `?Assign@?$crt_ptr@U_EAP_ERROR@@@@QEAAXPEBU_EAP_ERROR@@@Z`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026850`
- `0x18002b900`

## callees

- `0x1800034cc`
- `0x18001246c`
- `0x180013734`
- `0x180023f10`
- `0x18002fe84`
- `0x180030994`

## string_xrefs

- `0x180023f60`: `com_ptr::Assign`

## pseudocode

```c
__int64 __fastcall crt_ptr<_EAP_ERROR>::Assign(_QWORD *a1, __int64 a2)
{
  void *v2; // rbx
  void *v4; // rax
  __int64 result; // rax

  v2 = 0;
  if ( a2 )
  {
    v4 = Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, 0x58u);
    v2 = v4;
    if ( !v4 || (memset_0(v4, 0, 0x58u), !(unsigned __int8)Copy<HeapAllocator>(v2)) )
      LowMemoryError::Throw(L"com_ptr::Assign");
  }
  result = crt_ptr<_EAP_ERROR>::Clear(a1);
  *a1 = v2;
  return result;
}

```

## disassembly

```asm
0x180023f10  mov     [rsp+arg_0], rbx
0x180023f15  mov     [rsp+arg_8], rsi
0x180023f1a  push    rdi
0x180023f1b  sub     rsp, 20h
0x180023f1f  xor     ebx, ebx
0x180023f21  mov     rsi, rdx
0x180023f24  mov     rdi, rcx
0x180023f27  test    rdx, rdx
0x180023f2a  jz      short loc_180023F6D
0x180023f2c  lea     edx, [rbx+58h]; unsigned __int64
0x180023f2f  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180023f36  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180023f3b  mov     rbx, rax
0x180023f3e  test    rax, rax
0x180023f41  jz      short loc_180023F60
0x180023f43  xor     edx, edx; Val
0x180023f45  mov     rcx, rax; void *
0x180023f48  lea     r8d, [rdx+58h]; Size
0x180023f4c  call    memset_0
0x180023f51  mov     rdx, rsi
0x180023f54  mov     rcx, rbx; void *
0x180023f57  call    ??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<HeapAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x180023f5c  test    al, al
0x180023f5e  jnz     short loc_180023F6D
0x180023f60  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x180023f67  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180023f6d  mov     rcx, rdi
0x180023f70  call    ?Clear@?$crt_ptr@U_EAP_ERROR@@@@QEAAXXZ; crt_ptr<_EAP_ERROR>::Clear(void)
0x180023f75  mov     rsi, [rsp+28h+arg_8]
0x180023f7a  mov     [rdi], rbx
0x180023f7d  mov     rbx, [rsp+28h+arg_0]
0x180023f82  add     rsp, 20h
0x180023f86  pop     rdi
0x180023f87  retn
```
