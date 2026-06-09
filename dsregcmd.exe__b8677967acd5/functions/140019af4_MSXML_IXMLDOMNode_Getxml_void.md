# MSXML::IXMLDOMNode::Getxml(void)

- ea: `0x140019af4`
- end: `0x140019b83`
- name: `?Getxml@IXMLDOMNode@MSXML@@QEAA?AV_bstr_t@@XZ`
- size: `143`
- prototype: `_QWORD *__fastcall(struct IUnknown *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001a28c`
- `0x14002774c`

## callees

- `0x1400017d4`
- `0x140019af4`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall MSXML::IXMLDOMNode::Getxml(struct IUnknown *a1, _QWORD *a2)
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
0x140019af4  mov     [rsp+arg_8], rbx
0x140019af9  push    rdi
0x140019afa  sub     rsp, 30h
0x140019afe  mov     rbx, rdx
0x140019b01  mov     rdi, rcx
0x140019b04  mov     [rsp+38h+arg_0], 0
0x140019b0d  mov     rax, [rcx]
0x140019b10  lea     rdx, [rsp+38h+arg_0]
0x140019b15  mov     rax, [rax+110h]
0x140019b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019b21  test    eax, eax
0x140019b23  js      short loc_140019B71
0x140019b25  mov     rdi, [rsp+38h+arg_0]
0x140019b2a  mov     ecx, 18h; Size
0x140019b2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140019b34  mov     [rsp+38h+arg_10], rax
0x140019b39  test    rax, rax
0x140019b3c  jz      short loc_140019B50
0x140019b3e  mov     qword ptr [rax+8], 0
0x140019b46  mov     dword ptr [rax+10h], 1
0x140019b4d  mov     [rax], rdi
0x140019b50  mov     [rbx], rax
0x140019b53  test    rax, rax
0x140019b56  jz      short loc_140019B66
0x140019b58  mov     rax, rbx
0x140019b5b  mov     rbx, [rsp+38h+arg_8]
0x140019b60  add     rsp, 30h
0x140019b64  pop     rdi
0x140019b65  retn
0x140019b66  mov     ecx, 8007000Eh; int
0x140019b6b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140019b71  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x140019b78  mov     rdx, rdi; struct IUnknown *
0x140019b7b  mov     ecx, eax; int
0x140019b7d  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
