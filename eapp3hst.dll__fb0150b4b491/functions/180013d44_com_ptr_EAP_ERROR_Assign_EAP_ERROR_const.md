# com_ptr<_EAP_ERROR>::Assign(_EAP_ERROR const *)

- ea: `0x180013d44`
- end: `0x180013db6`
- name: `?Assign@?$com_ptr@U_EAP_ERROR@@@@QEAAXPEBU_EAP_ERROR@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180014064`
- `0x1800140f4`

## callees

- `0x18000213c`
- `0x180012a00`
- `0x18001322c`
- `0x180013d44`
- `0x180013dbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013d63`

## string_xrefs

- `0x180013d8e`: `com_ptr::Assign`

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
0x180013d44  mov     [rsp+arg_0], rbx
0x180013d49  mov     [rsp+arg_8], rsi
0x180013d4e  push    rdi
0x180013d4f  sub     rsp, 20h
0x180013d53  xor     ebx, ebx
0x180013d55  mov     rsi, rdx
0x180013d58  mov     rdi, rcx
0x180013d5b  test    rdx, rdx
0x180013d5e  jz      short loc_180013D9B
0x180013d60  lea     ecx, [rbx+58h]; cb
0x180013d63  call    cs:__imp_CoTaskMemAlloc
0x180013d69  mov     rbx, rax
0x180013d6c  test    rax, rax
0x180013d6f  jz      short loc_180013D8E
0x180013d71  xor     edx, edx; Val
0x180013d73  mov     rcx, rax; void *
0x180013d76  lea     r8d, [rdx+58h]; Size
0x180013d7a  call    memset_0
0x180013d7f  mov     rdx, rsi
0x180013d82  mov     rcx, rbx; void *
0x180013d85  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x180013d8a  test    al, al
0x180013d8c  jnz     short loc_180013D9B
0x180013d8e  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x180013d95  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180013d9b  mov     rcx, rdi
0x180013d9e  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x180013da3  mov     rsi, [rsp+28h+arg_8]
0x180013da8  mov     [rdi], rbx
0x180013dab  mov     rbx, [rsp+28h+arg_0]
0x180013db0  add     rsp, 20h
0x180013db4  pop     rdi
0x180013db5  retn
```
