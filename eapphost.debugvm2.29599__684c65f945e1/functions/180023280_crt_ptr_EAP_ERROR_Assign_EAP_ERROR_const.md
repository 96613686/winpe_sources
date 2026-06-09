# crt_ptr<_EAP_ERROR>::Assign(_EAP_ERROR const *)

- ea: `0x180023280`
- end: `0x1800232f8`
- name: `?Assign@?$crt_ptr@U_EAP_ERROR@@@@QEAAXPEBU_EAP_ERROR@@@Z`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025b18`
- `0x18002aad4`

## callees

- `0x18000343c`
- `0x180011cf4`
- `0x180012f8c`
- `0x180023280`
- `0x18002ed84`
- `0x18002f7ec`

## string_xrefs

- `0x1800232d0`: `com_ptr::Assign`

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
0x180023280  mov     [rsp+arg_0], rbx
0x180023285  mov     [rsp+arg_8], rsi
0x18002328a  push    rdi
0x18002328b  sub     rsp, 20h
0x18002328f  xor     ebx, ebx
0x180023291  mov     rsi, rdx
0x180023294  mov     rdi, rcx
0x180023297  test    rdx, rdx
0x18002329a  jz      short loc_1800232DD
0x18002329c  lea     edx, [rbx+58h]; unsigned __int64
0x18002329f  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x1800232a6  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x1800232ab  mov     rbx, rax
0x1800232ae  test    rax, rax
0x1800232b1  jz      short loc_1800232D0
0x1800232b3  xor     edx, edx; Val
0x1800232b5  mov     rcx, rax; void *
0x1800232b8  lea     r8d, [rdx+58h]; Size
0x1800232bc  call    memset_0
0x1800232c1  mov     rdx, rsi
0x1800232c4  mov     rcx, rbx; void *
0x1800232c7  call    ??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<HeapAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x1800232cc  test    al, al
0x1800232ce  jnz     short loc_1800232DD
0x1800232d0  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x1800232d7  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x1800232dd  mov     rcx, rdi
0x1800232e0  call    ?Clear@?$crt_ptr@U_EAP_ERROR@@@@QEAAXXZ; crt_ptr<_EAP_ERROR>::Clear(void)
0x1800232e5  mov     rsi, [rsp+28h+arg_8]
0x1800232ea  mov     [rdi], rbx
0x1800232ed  mov     rbx, [rsp+28h+arg_0]
0x1800232f2  add     rsp, 20h
0x1800232f6  pop     rdi
0x1800232f7  retn
```
