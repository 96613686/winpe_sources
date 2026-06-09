# MSXML::IXMLDOMNode::selectSingleNode(_bstr_t)

- ea: `0x14001c244`
- end: `0x14001c2c8`
- name: `?selectSingleNode@IXMLDOMNode@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400196f4`
- `0x14001a28c`
- `0x140027410`
- `0x14002774c`
- `0x140027d80`

## callees

- `0x1400193b4`
- `0x14001c244`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
_QWORD *__fastcall MSXML::IXMLDOMNode::selectSingleNode(struct IUnknown *a1, _QWORD *a2, _bstr_t *a3)
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
0x14001c244  mov     rax, rsp
0x14001c247  mov     [rax+10h], rbx
0x14001c24b  mov     [rax+20h], rsi
0x14001c24f  mov     [rax+18h], r8
0x14001c253  push    rdi
0x14001c254  sub     rsp, 30h
0x14001c258  mov     rdi, r8
0x14001c25b  mov     rbx, rdx
0x14001c25e  mov     rsi, rcx
0x14001c261  mov     qword ptr [rax+8], 0
0x14001c269  mov     rax, [rcx]
0x14001c26c  mov     r9, [rax+128h]
0x14001c273  mov     rax, [r8]
0x14001c276  test    rax, rax
0x14001c279  jz      short loc_14001C280
0x14001c27b  mov     rdx, [rax]
0x14001c27e  jmp     short loc_14001C282
0x14001c280  xor     edx, edx
0x14001c282  lea     r8, [rsp+38h+arg_0]
0x14001c287  mov     rax, r9
0x14001c28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c28f  test    eax, eax
0x14001c291  js      short loc_14001C2B6
0x14001c293  mov     rax, [rsp+38h+arg_0]
0x14001c298  mov     [rbx], rax
0x14001c29b  mov     rcx, rdi; this
0x14001c29e  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001c2a3  mov     rax, rbx
0x14001c2a6  mov     rbx, [rsp+38h+arg_8]
0x14001c2ab  mov     rsi, [rsp+38h+arg_18]
0x14001c2b0  add     rsp, 30h
0x14001c2b4  pop     rdi
0x14001c2b5  retn
0x14001c2b6  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001c2bd  mov     rdx, rsi; struct IUnknown *
0x14001c2c0  mov     ecx, eax; int
0x14001c2c2  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
