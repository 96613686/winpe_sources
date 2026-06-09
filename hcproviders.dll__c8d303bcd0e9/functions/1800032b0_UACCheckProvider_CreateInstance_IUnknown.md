# UACCheckProvider_CreateInstance(IUnknown * *)

- ea: `0x1800032b0`
- end: `0x180003312`
- name: `?UACCheckProvider_CreateInstance@@YAJPEAPEAUIUnknown@@@Z`
- size: `98`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800032b0`
- `0x180003320`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall UACCheckProvider_CreateInstance(struct IUnknown **a1)
{
  __int64 result; // rax
  __int64 (__fastcall ***v3)(_QWORD, GUID *, struct IUnknown **); // rdi
  unsigned int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, struct IUnknown **); // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v5 = 0;
  result = CObjectFactory<_GUID const &,CUACCheckProvider>::s_CreateInstance((__int64)a1, &v5);
  if ( (int)result >= 0 )
  {
    v3 = v5;
    v4 = (**v5)(v5, &GUID_00000000_0000_0000_c000_000000000046, a1);
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **)))(*v3)[2])(v3);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800032b0  push    rbx
0x1800032b2  sub     rsp, 20h
0x1800032b6  xor     eax, eax
0x1800032b8  lea     rdx, [rsp+28h+arg_0]
0x1800032bd  mov     [rcx], rax
0x1800032c0  mov     rbx, rcx
0x1800032c3  mov     [rsp+28h+arg_0], rax
0x1800032c8  call    ?s_CreateInstance@?$CObjectFactory@AEBU_GUID@@VCUACCheckProvider@@@@SAJAEBU_GUID@@PEAPEAVCUACCheckProvider@@@Z; CObjectFactory<_GUID const &,CUACCheckProvider>::s_CreateInstance(_GUID const &,CUACCheckProvider * *)
0x1800032cd  test    eax, eax
0x1800032cf  js      short loc_18000330B
0x1800032d1  mov     [rsp+28h+arg_8], rdi
0x1800032d6  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800032dd  mov     rdi, [rsp+28h+arg_0]
0x1800032e2  mov     r8, rbx
0x1800032e5  mov     rcx, rdi
0x1800032e8  mov     rax, [rdi]
0x1800032eb  mov     rax, [rax]
0x1800032ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f3  mov     rdx, [rdi]
0x1800032f6  mov     ebx, eax
0x1800032f8  mov     rcx, rdi
0x1800032fb  mov     rax, [rdx+10h]
0x1800032ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003304  mov     rdi, [rsp+28h+arg_8]
0x180003309  mov     eax, ebx
0x18000330b  add     rsp, 20h
0x18000330f  pop     rbx
0x180003310  retn
```
