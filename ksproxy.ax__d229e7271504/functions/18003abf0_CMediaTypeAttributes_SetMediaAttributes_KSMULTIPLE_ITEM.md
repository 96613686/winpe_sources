# CMediaTypeAttributes::SetMediaAttributes(KSMULTIPLE_ITEM *)

- ea: `0x18003abf0`
- end: `0x18003ac5c`
- name: `?SetMediaAttributes@CMediaTypeAttributes@@UEAAJPEAUKSMULTIPLE_ITEM@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(CMediaTypeAttributes *this, struct KSMULTIPLE_ITEM *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18003abf0`
- `0x180044850`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18003ac24`
- `ole32!CoTaskMemAlloc` at `0x18003ac24`
- `ole32!CoTaskMemFree` at `0x18003ac09`
- `ole32!CoTaskMemFree` at `0x18003ac09`

## pseudocode

```c
__int64 __fastcall CMediaTypeAttributes::SetMediaAttributes(CMediaTypeAttributes *this, struct KSMULTIPLE_ITEM *a2)
{
  void *v4; // rcx
  void *v5; // rax

  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 1) = 0;
  }
  if ( !a2 )
    return 0;
  v5 = CoTaskMemAlloc(a2->Size);
  *((_QWORD *)this + 1) = v5;
  if ( v5 )
  {
    memcpy_0(v5, a2, a2->Size);
    return 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18003abf0  mov     [rsp+arg_0], rbx
0x18003abf5  push    rdi
0x18003abf6  sub     rsp, 20h
0x18003abfa  mov     rdi, rcx
0x18003abfd  mov     rbx, rdx
0x18003ac00  mov     rcx, [rcx+8]; pv
0x18003ac04  test    rcx, rcx
0x18003ac07  jz      short loc_18003AC1D
0x18003ac09  call    cs:__imp_CoTaskMemFree
0x18003ac10  nop     dword ptr [rax+rax+00h]
0x18003ac15  mov     qword ptr [rdi+8], 0
0x18003ac1d  test    rbx, rbx
0x18003ac20  jz      short loc_18003AC47
0x18003ac22  mov     ecx, [rbx]; cb
0x18003ac24  call    cs:__imp_CoTaskMemAlloc
0x18003ac2b  nop     dword ptr [rax+rax+00h]
0x18003ac30  mov     [rdi+8], rax
0x18003ac34  test    rax, rax
0x18003ac37  jz      short loc_18003AC55
0x18003ac39  mov     r8d, [rbx]; Size
0x18003ac3c  mov     rdx, rbx; Src
0x18003ac3f  mov     rcx, rax; void *
0x18003ac42  call    memcpy_0
0x18003ac47  xor     eax, eax
0x18003ac49  mov     rbx, [rsp+28h+arg_0]
0x18003ac4e  add     rsp, 20h
0x18003ac52  pop     rdi
0x18003ac53  retn
0x18003ac55  mov     eax, 8007000Eh
0x18003ac5a  jmp     short loc_18003AC49
```
