# MSXML::IXMLDOMParseError::Getreason(void)

- ea: `0x14002ad94`
- end: `0x14002ae20`
- name: `?Getreason@IXMLDOMParseError@MSXML@@QEAA?AV_bstr_t@@XZ`
- size: `140`
- prototype: `_QWORD *__fastcall(struct IUnknown *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002aebc`

## callees

- `0x1400017d4`
- `0x14002ad94`
- `0x14002c070`
- `0x14002c084`
- `0x140030010`

## pseudocode

```c
_QWORD *__fastcall MSXML::IXMLDOMParseError::Getreason(struct IUnknown *a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  _QWORD *v6; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  _QWORD *v9; // [rsp+50h] [rbp+18h]

  v8 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))a1->lpVtbl[3].QueryInterface)(a1, &v8);
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
0x14002ad94  mov     [rsp+arg_8], rbx
0x14002ad99  push    rdi
0x14002ad9a  sub     rsp, 30h
0x14002ad9e  mov     rbx, rdx
0x14002ada1  mov     rdi, rcx
0x14002ada4  mov     [rsp+38h+arg_0], 0
0x14002adad  mov     rax, [rcx]
0x14002adb0  lea     rdx, [rsp+38h+arg_0]
0x14002adb5  mov     rax, [rax+48h]
0x14002adb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002adbe  test    eax, eax
0x14002adc0  js      short loc_14002AE0E
0x14002adc2  mov     rdi, [rsp+38h+arg_0]
0x14002adc7  mov     ecx, 18h; Size
0x14002adcc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002add1  mov     [rsp+38h+arg_10], rax
0x14002add6  test    rax, rax
0x14002add9  jz      short loc_14002ADED
0x14002addb  mov     qword ptr [rax+8], 0
0x14002ade3  mov     dword ptr [rax+10h], 1
0x14002adea  mov     [rax], rdi
0x14002aded  mov     [rbx], rax
0x14002adf0  test    rax, rax
0x14002adf3  jz      short loc_14002AE03
0x14002adf5  mov     rax, rbx
0x14002adf8  mov     rbx, [rsp+38h+arg_8]
0x14002adfd  add     rsp, 30h
0x14002ae01  pop     rdi
0x14002ae02  retn
0x14002ae03  mov     ecx, 8007000Eh; int
0x14002ae08  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14002ae0e  lea     r8, _GUID_3efaa426_272f_11d2_836f_0000f87a7782; struct _GUID *
0x14002ae15  mov     rdx, rdi; struct IUnknown *
0x14002ae18  mov     ecx, eax; int
0x14002ae1a  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
