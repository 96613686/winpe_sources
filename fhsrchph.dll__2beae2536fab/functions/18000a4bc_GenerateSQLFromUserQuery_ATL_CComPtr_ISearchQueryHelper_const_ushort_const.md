# _GenerateSQLFromUserQuery(ATL::CComPtr<ISearchQueryHelper> const &,ushort const *)

- ea: `0x18000a4bc`
- end: `0x18000a50d`
- name: `?_GenerateSQLFromUserQuery@@YA?AV?$unique_ptr@GUCoTaskMemDeleter@@@std@@AEBV?$CComPtr@UISearchQueryHelper@@@ATL@@PEBG@Z`
- size: `81`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800099e4`

## callees

- `0x18000278c`
- `0x18000a4bc`
- `0x18000c010`

## pseudocode

```c
_QWORD *__fastcall _GenerateSQLFromUserQuery(_QWORD *a1, _QWORD *a2)
{
  int v3; // eax
  __int64 v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(*(_QWORD *)*a2 + 160LL))(*a2, L"*", &v5);
  if ( v3 < 0 )
    ATL::AtlThrowImpl(v3);
  *a1 = v5;
  return a1;
}

```

## disassembly

```asm
0x18000a4bc  mov     [rsp+arg_10], r8
0x18000a4c1  push    rbx
0x18000a4c2  sub     rsp, 30h
0x18000a4c6  mov     rbx, rcx
0x18000a4c9  mov     [rsp+38h+arg_10], 0
0x18000a4d2  mov     rcx, [rdx]
0x18000a4d5  lea     r8, [rsp+38h+arg_10]
0x18000a4da  lea     rdx, asc_18000E448; "*"
0x18000a4e1  mov     rax, [rcx]
0x18000a4e4  mov     rax, [rax+0A0h]
0x18000a4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f0  test    eax, eax
0x18000a4f2  js      short loc_18000A505
0x18000a4f4  mov     rax, [rsp+38h+arg_10]
0x18000a4f9  mov     [rbx], rax
0x18000a4fc  mov     rax, rbx
0x18000a4ff  add     rsp, 30h
0x18000a503  pop     rbx
0x18000a504  retn
0x18000a505  mov     ecx, eax; int
0x18000a507  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
