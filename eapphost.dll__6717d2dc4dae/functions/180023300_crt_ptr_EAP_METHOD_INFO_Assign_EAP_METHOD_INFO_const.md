# crt_ptr<_EAP_METHOD_INFO>::Assign(_EAP_METHOD_INFO const *)

- ea: `0x180023300`
- end: `0x180023378`
- name: `?Assign@?$crt_ptr@U_EAP_METHOD_INFO@@@@QEAAXPEBU_EAP_METHOD_INFO@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025b18`

## callees

- `0x180019680`
- `0x180023300`
- `0x180023800`
- `0x18002ed84`
- `0x18002f7ec`

## string_xrefs

- `0x180023350`: `com_ptr::Assign`

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
    if ( !v5 || (*v5 = 0, v5[1] = 0, v5[2] = 0, !Copy<HeapAllocator>((__int64)v5, a2)) )
      LowMemoryError::Throw(L"com_ptr::Assign");
  }
  result = crt_ptr<_EAP_METHOD_INFO>::Clear(a1);
  *a1 = v2;
  return result;
}

```

## disassembly

```asm
0x180023300  mov     [rsp+arg_0], rbx
0x180023305  mov     [rsp+arg_8], rsi
0x18002330a  push    rdi
0x18002330b  sub     rsp, 20h
0x18002330f  xor     ebx, ebx
0x180023311  mov     rsi, rdx
0x180023314  mov     rdi, rcx
0x180023317  test    rdx, rdx
0x18002331a  jz      short loc_18002335D
0x18002331c  lea     edx, [rbx+30h]; unsigned __int64
0x18002331f  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180023326  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x18002332b  mov     rbx, rax
0x18002332e  test    rax, rax
0x180023331  jz      short loc_180023350
0x180023333  xorps   xmm0, xmm0
0x180023336  mov     rdx, rsi
0x180023339  movups  xmmword ptr [rax], xmm0
0x18002333c  mov     rcx, rax
0x18002333f  movups  xmmword ptr [rax+10h], xmm0
0x180023343  movups  xmmword ptr [rax+20h], xmm0
0x180023347  call    ??$Copy@VHeapAllocator@@@@YA_NAEAU_EAP_METHOD_INFO@@AEBU0@@Z; Copy<HeapAllocator>(_EAP_METHOD_INFO &,_EAP_METHOD_INFO const &)
0x18002334c  test    al, al
0x18002334e  jnz     short loc_18002335D
0x180023350  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x180023357  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x18002335d  mov     rcx, rdi
0x180023360  call    ?Clear@?$crt_ptr@U_EAP_METHOD_INFO@@@@QEAAXXZ; crt_ptr<_EAP_METHOD_INFO>::Clear(void)
0x180023365  mov     rsi, [rsp+28h+arg_8]
0x18002336a  mov     [rdi], rbx
0x18002336d  mov     rbx, [rsp+28h+arg_0]
0x180023372  add     rsp, 20h
0x180023376  pop     rdi
0x180023377  retn
```
