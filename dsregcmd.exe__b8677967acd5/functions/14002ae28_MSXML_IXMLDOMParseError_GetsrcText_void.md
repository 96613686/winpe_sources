# MSXML::IXMLDOMParseError::GetsrcText(void)

- ea: `0x14002ae28`
- end: `0x14002aeb4`
- name: `?GetsrcText@IXMLDOMParseError@MSXML@@QEAA?AV_bstr_t@@XZ`
- size: `140`
- prototype: `_QWORD *__fastcall(struct IUnknown *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002aebc`

## callees

- `0x1400017d4`
- `0x14002ae28`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
_QWORD *__fastcall MSXML::IXMLDOMParseError::GetsrcText(struct IUnknown *a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  _QWORD *v6; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v9; // [rsp+50h] [rbp+18h]

  v8 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))a1->lpVtbl[3].AddRef)(a1, &v8);
  if ( v4 < 0 )
    _com_issue_errorex(v4, a1, &GUID_3efaa426_272f_11d2_836f_0000f87a7782);
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
0x14002ae28  mov     [rsp+arg_8], rbx
0x14002ae2d  push    rdi
0x14002ae2e  sub     rsp, 30h
0x14002ae32  mov     rbx, rdx
0x14002ae35  mov     rdi, rcx
0x14002ae38  mov     [rsp+38h+arg_0], 0
0x14002ae41  mov     rax, [rcx]
0x14002ae44  lea     rdx, [rsp+38h+arg_0]
0x14002ae49  mov     rax, [rax+50h]
0x14002ae4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ae52  test    eax, eax
0x14002ae54  js      short loc_14002AEA2
0x14002ae56  mov     rdi, [rsp+38h+arg_0]
0x14002ae5b  mov     ecx, 18h; Size
0x14002ae60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002ae65  mov     [rsp+38h+arg_10], rax
0x14002ae6a  test    rax, rax
0x14002ae6d  jz      short loc_14002AE81
0x14002ae6f  mov     qword ptr [rax+8], 0
0x14002ae77  mov     dword ptr [rax+10h], 1
0x14002ae7e  mov     [rax], rdi
0x14002ae81  mov     [rbx], rax
0x14002ae84  test    rax, rax
0x14002ae87  jz      short loc_14002AE97
0x14002ae89  mov     rax, rbx
0x14002ae8c  mov     rbx, [rsp+38h+arg_8]
0x14002ae91  add     rsp, 30h
0x14002ae95  pop     rdi
0x14002ae96  retn
0x14002ae97  mov     ecx, 8007000Eh; int
0x14002ae9c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14002aea2  lea     r8, _GUID_3efaa426_272f_11d2_836f_0000f87a7782; struct _GUID *
0x14002aea9  mov     rdx, rdi; struct IUnknown *
0x14002aeac  mov     ecx, eax; int
0x14002aeae  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
