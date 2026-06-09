# MSXML::IXMLDOMNamedNodeMap::getNamedItem(_bstr_t)

- ea: `0x14001c130`
- end: `0x14001c1b1`
- name: `?getNamedItem@IXMLDOMNamedNodeMap@MSXML@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@V_bstr_t@@@Z`
- size: `129`
- prototype: `_QWORD *__fastcall(struct IUnknown *, _QWORD *, _bstr_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400196f4`
- `0x14001a28c`

## callees

- `0x1400193b4`
- `0x14001c130`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
_QWORD *__fastcall MSXML::IXMLDOMNamedNodeMap::getNamedItem(struct IUnknown *a1, _QWORD *a2, _bstr_t *a3)
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
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64 *))a1->lpVtbl[2].AddRef)(a1, v6, &v9);
  if ( v7 < 0 )
    _com_issue_errorex(v7, a1, &GUID_2933bf83_7b36_11d2_b20e_00c04f983e60);
  *a2 = v9;
  _bstr_t::~_bstr_t(a3);
  return a2;
}

```

## disassembly

```asm
0x14001c130  mov     rax, rsp
0x14001c133  mov     [rax+10h], rbx
0x14001c137  mov     [rax+20h], rsi
0x14001c13b  mov     [rax+18h], r8
0x14001c13f  push    rdi
0x14001c140  sub     rsp, 30h
0x14001c144  mov     rdi, r8
0x14001c147  mov     rbx, rdx
0x14001c14a  mov     rsi, rcx
0x14001c14d  mov     qword ptr [rax+8], 0
0x14001c155  mov     rax, [rcx]
0x14001c158  mov     r9, [rax+38h]
0x14001c15c  mov     rax, [r8]
0x14001c15f  test    rax, rax
0x14001c162  jz      short loc_14001C169
0x14001c164  mov     rdx, [rax]
0x14001c167  jmp     short loc_14001C16B
0x14001c169  xor     edx, edx
0x14001c16b  lea     r8, [rsp+38h+arg_0]
0x14001c170  mov     rax, r9
0x14001c173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c178  test    eax, eax
0x14001c17a  js      short loc_14001C19F
0x14001c17c  mov     rax, [rsp+38h+arg_0]
0x14001c181  mov     [rbx], rax
0x14001c184  mov     rcx, rdi; this
0x14001c187  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x14001c18c  mov     rax, rbx
0x14001c18f  mov     rbx, [rsp+38h+arg_8]
0x14001c194  mov     rsi, [rsp+38h+arg_18]
0x14001c199  add     rsp, 30h
0x14001c19d  pop     rdi
0x14001c19e  retn
0x14001c19f  lea     r8, _GUID_2933bf83_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x14001c1a6  mov     rdx, rsi; struct IUnknown *
0x14001c1a9  mov     ecx, eax; int
0x14001c1ab  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
