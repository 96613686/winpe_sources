# MSXML2::IXMLDOMNode::Getxml(void)

- ea: `0x180008ce4`
- end: `0x180008d73`
- name: `?Getxml@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ`
- size: `143`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800079fc`
- `0x180007fb4`
- `0x1800081b8`
- `0x1800086c8`

## callees

- `0x180002310`
- `0x180008ce4`
- `0x18000db68`
- `0x18000db7c`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall MSXML2::IXMLDOMNode::Getxml(struct IUnknown *a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  _QWORD *v6; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v9; // [rsp+50h] [rbp+18h]

  v8 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))a1->lpVtbl[11].AddRef)(a1, &v8);
  if ( v4 < 0 )
    _com_issue_errorex(v4, a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
  v5 = v8;
  v6 = operator new(0x18u);
  v9 = v6;
  if ( v6 )
  {
    v6[1] = 0;
    *((_DWORD *)v6 + 4) = 1;
    *v6 = v5;
  }
  *a2 = v6;
  if ( !v6 )
    _com_issue_error(-2147024882);
  return a2;
}

```

## disassembly

```asm
0x180008ce4  mov     [rsp+arg_8], rbx
0x180008ce9  push    rdi
0x180008cea  sub     rsp, 30h
0x180008cee  mov     rbx, rdx
0x180008cf1  mov     rdi, rcx
0x180008cf4  mov     [rsp+38h+arg_0], 0
0x180008cfd  mov     rax, [rcx]
0x180008d00  lea     rdx, [rsp+38h+arg_0]
0x180008d05  mov     rax, [rax+110h]
0x180008d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d11  test    eax, eax
0x180008d13  js      short loc_180008D61
0x180008d15  mov     rdi, [rsp+38h+arg_0]
0x180008d1a  mov     ecx, 18h; Size
0x180008d1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008d24  mov     [rsp+38h+arg_10], rax
0x180008d29  test    rax, rax
0x180008d2c  jz      short loc_180008D40
0x180008d2e  mov     qword ptr [rax+8], 0
0x180008d36  mov     dword ptr [rax+10h], 1
0x180008d3d  mov     [rax], rdi
0x180008d40  mov     [rbx], rax
0x180008d43  test    rax, rax
0x180008d46  jz      short loc_180008D56
0x180008d48  mov     rax, rbx
0x180008d4b  mov     rbx, [rsp+38h+arg_8]
0x180008d50  add     rsp, 30h
0x180008d54  pop     rdi
0x180008d55  retn
0x180008d56  mov     ecx, 8007000Eh; int
0x180008d5b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180008d61  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x180008d68  mov     rdx, rdi; struct IUnknown *
0x180008d6b  mov     ecx, eax; int
0x180008d6d  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
