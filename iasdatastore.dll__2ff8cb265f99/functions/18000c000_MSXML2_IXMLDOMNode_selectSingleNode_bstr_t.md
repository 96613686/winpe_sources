# MSXML2::IXMLDOMNode::selectSingleNode(_bstr_t)

- ea: `0x18000c000`
- end: `0x18000c084`
- name: `?selectSingleNode@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800079fc`
- `0x18000a4a0`
- `0x18000b210`

## callees

- `0x1800076dc`
- `0x18000c000`
- `0x18000db7c`
- `0x180010010`

## pseudocode

```c
_QWORD *__fastcall MSXML2::IXMLDOMNode::selectSingleNode(struct IUnknown *a1, _QWORD *a2, _bstr_t *a3)
{
  __int64 v6; // rdx
  int v7; // eax
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  _bstr_t *v10; // [rsp+50h] [rbp+18h]

  v10 = a3;
  v9 = 0;
  if ( *(_QWORD *)a3 )
    v6 = **(_QWORD **)a3;
  else
    v6 = 0;
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))a1->lpVtbl[12].AddRef)(a1, v6, &v9);
  if ( v7 < 0 )
    _com_issue_errorex(v7, a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
  *a2 = v9;
  _bstr_t::~_bstr_t(a3);
  return a2;
}

```

## disassembly

```asm
0x18000c000  mov     rax, rsp
0x18000c003  mov     [rax+10h], rbx
0x18000c007  mov     [rax+20h], rsi
0x18000c00b  mov     [rax+18h], r8
0x18000c00f  push    rdi
0x18000c010  sub     rsp, 30h
0x18000c014  mov     rdi, r8
0x18000c017  mov     rbx, rdx
0x18000c01a  mov     rsi, rcx
0x18000c01d  mov     qword ptr [rax+8], 0
0x18000c025  mov     rax, [rcx]
0x18000c028  mov     r9, [rax+128h]
0x18000c02f  mov     rax, [r8]
0x18000c032  test    rax, rax
0x18000c035  jz      short loc_18000C03C
0x18000c037  mov     rdx, [rax]
0x18000c03a  jmp     short loc_18000C03E
0x18000c03c  xor     edx, edx
0x18000c03e  lea     r8, [rsp+38h+arg_0]
0x18000c043  mov     rax, r9
0x18000c046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c04b  test    eax, eax
0x18000c04d  js      short loc_18000C072
0x18000c04f  mov     rax, [rsp+38h+arg_0]
0x18000c054  mov     [rbx], rax
0x18000c057  mov     rcx, rdi; this
0x18000c05a  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000c05f  mov     rax, rbx
0x18000c062  mov     rbx, [rsp+38h+arg_8]
0x18000c067  mov     rsi, [rsp+38h+arg_18]
0x18000c06c  add     rsp, 30h
0x18000c070  pop     rdi
0x18000c071  retn
0x18000c072  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x18000c079  mov     rdx, rsi; struct IUnknown *
0x18000c07c  mov     ecx, eax; int
0x18000c07e  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
