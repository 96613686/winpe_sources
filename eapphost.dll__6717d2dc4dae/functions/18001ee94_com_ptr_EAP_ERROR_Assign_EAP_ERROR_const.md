# com_ptr<_EAP_ERROR>::Assign(_EAP_ERROR const *)

- ea: `0x18001ee94`
- end: `0x18001ef06`
- name: `?Assign@?$com_ptr@U_EAP_ERROR@@@@QEAAXPEBU_EAP_ERROR@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001f168`
- `0x18001f1f8`

## callees

- `0x18000343c`
- `0x180003c40`
- `0x180017b78`
- `0x18001ee94`
- `0x18002ed84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eeb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001eeb3`

## string_xrefs

- `0x18001eede`: `com_ptr::Assign`

## pseudocode

```c
__int64 __fastcall com_ptr<_EAP_ERROR>::Assign(_QWORD *a1, __int64 a2)
{
  _OWORD *v2; // rbx
  _OWORD *v5; // rax
  __int64 result; // rax

  v2 = 0;
  if ( a2 )
  {
    v5 = CoTaskMemAlloc(0x58u);
    v2 = v5;
    if ( !v5 || (memset_0(v5, 0, 0x58u), !Copy<TaskAllocator>(v2, a2)) )
      LowMemoryError::Throw(L"com_ptr::Assign");
  }
  result = com_ptr<_EAP_ERROR>::Clear(a1);
  *a1 = v2;
  return result;
}

```

## disassembly

```asm
0x18001ee94  mov     [rsp+arg_0], rbx
0x18001ee99  mov     [rsp+arg_8], rsi
0x18001ee9e  push    rdi
0x18001ee9f  sub     rsp, 20h
0x18001eea3  xor     ebx, ebx
0x18001eea5  mov     rsi, rdx
0x18001eea8  mov     rdi, rcx
0x18001eeab  test    rdx, rdx
0x18001eeae  jz      short loc_18001EEEB
0x18001eeb0  lea     ecx, [rbx+58h]; cb
0x18001eeb3  call    cs:__imp_CoTaskMemAlloc
0x18001eeb9  mov     rbx, rax
0x18001eebc  test    rax, rax
0x18001eebf  jz      short loc_18001EEDE
0x18001eec1  xor     edx, edx; Val
0x18001eec3  mov     rcx, rax; void *
0x18001eec6  lea     r8d, [rdx+58h]; Size
0x18001eeca  call    memset_0
0x18001eecf  mov     rdx, rsi
0x18001eed2  mov     rcx, rbx; void *
0x18001eed5  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x18001eeda  test    al, al
0x18001eedc  jnz     short loc_18001EEEB
0x18001eede  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x18001eee5  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x18001eeeb  mov     rcx, rdi
0x18001eeee  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001eef3  mov     rsi, [rsp+28h+arg_8]
0x18001eef8  mov     [rdi], rbx
0x18001eefb  mov     rbx, [rsp+28h+arg_0]
0x18001ef00  add     rsp, 20h
0x18001ef04  pop     rdi
0x18001ef05  retn
```
