# MSXML::IXMLDOMNode::selectNodes(_bstr_t)

- ea: `0x14001c1b8`
- end: `0x14001c23c`
- name: `?selectNodes@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a28c`
- `0x14001b9fc`
- `0x140027534`

## callees

- `0x1400193b4`
- `0x14001c1b8`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall MSXML::IXMLDOMNode::selectNodes(struct IUnknown *a1, _QWORD *a2, _bstr_t *a3)
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
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))a1->lpVtbl[12].QueryInterface)(a1, v6, &v9);
  if ( v7 < 0 )
    _com_issue_errorex(v7, a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
  *a2 = v9;
  _bstr_t::~_bstr_t(a3);
  return a2;
}

```

## disassembly

```asm
0x14001c1b8  mov     rax, rsp
0x14001c1bb  mov     [rax+10h], rbx
0x14001c1bf  mov     [rax+20h], rsi
0x14001c1c3  mov     [rax+18h], r8
0x14001c1c7  push    rdi
0x14001c1c8  sub     rsp, 30h
0x14001c1cc  mov     rdi, r8
0x14001c1cf  mov     rbx, rdx
0x14001c1d2  mov     rsi, rcx
0x14001c1d5  mov     qword ptr [rax+8], 0
0x14001c1dd  mov     rax, [rcx]
0x14001c1e0  mov     r9, [rax+120h]
0x14001c1e7  mov     rax, [r8]
0x14001c1ea  test    rax, rax
0x14001c1ed  jz      short loc_14001C1F4
0x14001c1ef  mov     rdx, [rax]
0x14001c1f2  jmp     short loc_14001C1F6
0x14001c1f4  xor     edx, edx
0x14001c1f6  lea     r8, [rsp+38h+arg_0]
0x14001c1fb  mov     rax, r9
0x14001c1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c203  test    eax, eax
0x14001c205  js      short loc_14001C22A
0x14001c207  mov     rax, [rsp+38h+arg_0]
0x14001c20c  mov     [rbx], rax
0x14001c20f  mov     rcx, rdi; this
0x14001c212  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001c217  mov     rax, rbx
0x14001c21a  mov     rbx, [rsp+38h+arg_8]
0x14001c21f  mov     rsi, [rsp+38h+arg_18]
0x14001c224  add     rsp, 30h
0x14001c228  pop     rdi
0x14001c229  retn
0x14001c22a  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001c231  mov     rdx, rsi; struct IUnknown *
0x14001c234  mov     ecx, eax; int
0x14001c236  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
