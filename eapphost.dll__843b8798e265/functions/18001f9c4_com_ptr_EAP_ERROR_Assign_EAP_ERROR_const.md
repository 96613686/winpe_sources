# com_ptr<_EAP_ERROR>::Assign(_EAP_ERROR const *)

- ea: `0x18001f9c4`
- end: `0x18001fa3d`
- name: `?Assign@?$com_ptr@U_EAP_ERROR@@@@QEAAXPEBU_EAP_ERROR@@@Z`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001fca4`
- `0x18001fd34`

## callees

- `0x1800034cc`
- `0x180003d0c`
- `0x180018498`
- `0x18001f9c4`
- `0x18002fe84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f9e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f9e3`

## string_xrefs

- `0x18001fa14`: `com_ptr::Assign`

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
0x18001f9c4  mov     [rsp+arg_0], rbx
0x18001f9c9  mov     [rsp+arg_8], rsi
0x18001f9ce  push    rdi
0x18001f9cf  sub     rsp, 20h
0x18001f9d3  xor     ebx, ebx
0x18001f9d5  mov     rsi, rdx
0x18001f9d8  mov     rdi, rcx
0x18001f9db  test    rdx, rdx
0x18001f9de  jz      short loc_18001FA21
0x18001f9e0  lea     ecx, [rbx+58h]; cb
0x18001f9e3  call    cs:__imp_CoTaskMemAlloc
0x18001f9ea  nop     dword ptr [rax+rax+00h]
0x18001f9ef  mov     rbx, rax
0x18001f9f2  test    rax, rax
0x18001f9f5  jz      short loc_18001FA14
0x18001f9f7  xor     edx, edx; Val
0x18001f9f9  mov     rcx, rax; void *
0x18001f9fc  lea     r8d, [rdx+58h]; Size
0x18001fa00  call    memset_0
0x18001fa05  mov     rdx, rsi
0x18001fa08  mov     rcx, rbx; void *
0x18001fa0b  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x18001fa10  test    al, al
0x18001fa12  jnz     short loc_18001FA21
0x18001fa14  lea     rcx, aComPtrAssign; "com_ptr::Assign"
0x18001fa1b  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x18001fa21  mov     rcx, rdi
0x18001fa24  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001fa29  mov     rsi, [rsp+28h+arg_8]
0x18001fa2e  mov     [rdi], rbx
0x18001fa31  mov     rbx, [rsp+28h+arg_0]
0x18001fa36  add     rsp, 20h
0x18001fa3a  pop     rdi
0x18001fa3b  retn
```
