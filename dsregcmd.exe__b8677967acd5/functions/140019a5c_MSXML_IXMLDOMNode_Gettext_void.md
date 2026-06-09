# MSXML::IXMLDOMNode::Gettext(void)

- ea: `0x140019a5c`
- end: `0x140019aeb`
- name: `?Gettext@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ`
- size: `143`
- prototype: `_QWORD *__fastcall(struct IUnknown *, _QWORD *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400196f4`
- `0x14001a28c`
- `0x140027410`
- `0x14002774c`
- `0x140027d80`

## callees

- `0x1400017d4`
- `0x140019a5c`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall MSXML::IXMLDOMNode::Gettext(struct IUnknown *a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  _QWORD *v6; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v9; // [rsp+50h] [rbp+18h]

  v8 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))a1->lpVtbl[8].Release)(a1, &v8);
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
0x140019a5c  mov     [rsp+arg_8], rbx
0x140019a61  push    rdi
0x140019a62  sub     rsp, 30h
0x140019a66  mov     rbx, rdx
0x140019a69  mov     rdi, rcx
0x140019a6c  mov     [rsp+38h+arg_0], 0
0x140019a75  mov     rax, [rcx]
0x140019a78  lea     rdx, [rsp+38h+arg_0]
0x140019a7d  mov     rax, [rax+0D0h]
0x140019a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019a89  test    eax, eax
0x140019a8b  js      short loc_140019AD9
0x140019a8d  mov     rdi, [rsp+38h+arg_0]
0x140019a92  mov     ecx, 18h; Size
0x140019a97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140019a9c  mov     [rsp+38h+arg_10], rax
0x140019aa1  test    rax, rax
0x140019aa4  jz      short loc_140019AB8
0x140019aa6  mov     qword ptr [rax+8], 0
0x140019aae  mov     dword ptr [rax+10h], 1
0x140019ab5  mov     [rax], rdi
0x140019ab8  mov     [rbx], rax
0x140019abb  test    rax, rax
0x140019abe  jz      short loc_140019ACE
0x140019ac0  mov     rax, rbx
0x140019ac3  mov     rbx, [rsp+38h+arg_8]
0x140019ac8  add     rsp, 30h
0x140019acc  pop     rdi
0x140019acd  retn
0x140019ace  mov     ecx, 8007000Eh; int
0x140019ad3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140019ad9  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x140019ae0  mov     rdx, rdi; struct IUnknown *
0x140019ae3  mov     ecx, eax; int
0x140019ae5  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
