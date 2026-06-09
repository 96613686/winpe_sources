# MSXML2::IXMLDOMNode::selectNodes(_bstr_t)

- ea: `0x18000bf74`
- end: `0x18000bff8`
- name: `?selectNodes@IXMLDOMNode@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNodeList@MSXML2@@$1?_GUID_2933bf82_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800081b8`
- `0x1800086c8`
- `0x18000a4a0`
- `0x18000b210`

## callees

- `0x1800076dc`
- `0x18000bf74`
- `0x18000db7c`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall MSXML2::IXMLDOMNode::selectNodes(struct IUnknown *a1, _QWORD *a2, _bstr_t *a3)
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
0x18000bf74  mov     rax, rsp
0x18000bf77  mov     [rax+10h], rbx
0x18000bf7b  mov     [rax+20h], rsi
0x18000bf7f  mov     [rax+18h], r8
0x18000bf83  push    rdi
0x18000bf84  sub     rsp, 30h
0x18000bf88  mov     rdi, r8
0x18000bf8b  mov     rbx, rdx
0x18000bf8e  mov     rsi, rcx
0x18000bf91  mov     qword ptr [rax+8], 0
0x18000bf99  mov     rax, [rcx]
0x18000bf9c  mov     r9, [rax+120h]
0x18000bfa3  mov     rax, [r8]
0x18000bfa6  test    rax, rax
0x18000bfa9  jz      short loc_18000BFB0
0x18000bfab  mov     rdx, [rax]
0x18000bfae  jmp     short loc_18000BFB2
0x18000bfb0  xor     edx, edx
0x18000bfb2  lea     r8, [rsp+38h+arg_0]
0x18000bfb7  mov     rax, r9
0x18000bfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfbf  test    eax, eax
0x18000bfc1  js      short loc_18000BFE6
0x18000bfc3  mov     rax, [rsp+38h+arg_0]
0x18000bfc8  mov     [rbx], rax
0x18000bfcb  mov     rcx, rdi; this
0x18000bfce  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000bfd3  mov     rax, rbx
0x18000bfd6  mov     rbx, [rsp+38h+arg_8]
0x18000bfdb  mov     rsi, [rsp+38h+arg_18]
0x18000bfe0  add     rsp, 30h
0x18000bfe4  pop     rdi
0x18000bfe5  retn
0x18000bfe6  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x18000bfed  mov     rdx, rsi; struct IUnknown *
0x18000bff0  mov     ecx, eax; int
0x18000bff2  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
