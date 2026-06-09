# std::_Destroy_range<std::allocator<ATL::CComPtr<IDomNode>>>(ATL::CComPtr<IDomNode> *,ATL::CComPtr<IDomNode> * const,std::allocator<ATL::CComPtr<IDomNode>> &)

- ea: `0x180023be8`
- end: `0x180023c1a`
- name: `??$_Destroy_range@V?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@std@@@std@@YAXPEAV?$CComPtr@UIDomNode@@@ATL@@QEAV12@AEAV?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@0@@Z`
- size: `50`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023c20`
- `0x180023fcc`
- `0x1800240d8`
- `0x18002412c`
- `0x1800241e0`
- `0x180024370`
- `0x1800257ec`

## callees

- `0x1800110bc`
- `0x180023be8`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<ATL::CComPtr<IDomNode>>>(__int64 *a1, __int64 *a2)
{
  __int64 *v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
      result = wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(v3++);
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180023be8  cmp     rcx, rdx
0x180023beb  jz      short locret_180023C18
0x180023bed  mov     [rsp+arg_0], rbx
0x180023bf2  push    rdi
0x180023bf3  sub     rsp, 20h
0x180023bf7  mov     rdi, rdx
0x180023bfa  mov     rbx, rcx
0x180023bfd  mov     rcx, rbx
0x180023c00  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180023c05  add     rbx, 8
0x180023c09  cmp     rbx, rdi
0x180023c0c  jnz     short loc_180023BFD
0x180023c0e  mov     rbx, [rsp+28h+arg_0]
0x180023c13  add     rsp, 20h
0x180023c17  pop     rdi
0x180023c18  retn
```
