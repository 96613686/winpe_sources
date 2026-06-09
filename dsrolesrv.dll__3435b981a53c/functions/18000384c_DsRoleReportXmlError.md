# DsRoleReportXmlError

- ea: `0x18000384c`
- end: `0x18000398e`
- name: `DsRoleReportXmlError`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800072ec`

## callees

- `0x18000384c`
- `0x180020dbc`
- `0x18002e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000393a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000393a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000397d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c443`
- `OLEAUT32!__imp_SysFreeString` at `0x18000397d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c443`

## string_xrefs

- `0x180003961`: `XML Parse error: line %lu, line position %lu, errorCode 0x%x, reason %ws\n`

## pseudocode

```c
void __fastcall DsRoleReportXmlError(__int64 a1, int *a2)
{
  unsigned int v4; // [rsp+30h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v6[3]; // [rsp+40h] [rbp-18h] BYREF
  int v7; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v8; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  v8 = 0;
  v7 = -2147467259;
  v6[0] = 0;
  bstrString = 0;
  if ( a1 )
  {
    if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 88LL))(a1, &v4) < 0 )
      v4 = 0;
    if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 96LL))(a1, &v8) < 0 )
      v8 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 56LL))(a1, &v7) < 0 )
      v7 = -2147467259;
    if ( (*(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 64LL))(a1, v6) < 0 )
      v6[0] = 0;
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a1 + 72LL))(a1, &bstrString) < 0 )
      bstrString = 0;
  }
  if ( !bstrString )
    bstrString = SysAllocString(&base);
  DsRolepLogPrintRoutine(
    1,
    "XML Parse error: line %lu, line position %lu, errorCode 0x%x, reason %ws\n",
    v4,
    v8,
    v7,
    bstrString);
  *a2 = v7;
  SysFreeString(bstrString);
}

```

## disassembly

```asm
0x18000384c  mov     rax, rsp
0x18000384f  mov     [rax+8], rbx
0x180003853  push    rdi
0x180003854  sub     rsp, 50h
0x180003858  mov     rdi, rdx
0x18000385b  mov     rbx, rcx
0x18000385e  mov     dword ptr [rax-28h], 0
0x180003865  mov     dword ptr [rax+20h], 0
0x18000386c  mov     dword ptr [rax+18h], 80004005h
0x180003873  mov     qword ptr [rax-18h], 0
0x18000387b  mov     qword ptr [rax-20h], 0
0x180003883  test    rcx, rcx
0x180003886  jz      loc_18000392B
0x18000388c  mov     rax, [rcx]
0x18000388f  lea     rdx, [rsp+58h+var_28]
0x180003894  mov     rax, [rax+58h]
0x180003898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389d  test    eax, eax
0x18000389f  jns     short loc_1800038A9
0x1800038a1  mov     [rsp+58h+var_28], 0
0x1800038a9  mov     rax, [rbx]
0x1800038ac  lea     rdx, [rsp+58h+arg_18]
0x1800038b1  mov     rcx, rbx
0x1800038b4  mov     rax, [rax+60h]
0x1800038b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038bd  test    eax, eax
0x1800038bf  jns     short loc_1800038C9
0x1800038c1  mov     [rsp+58h+arg_18], 0
0x1800038c9  mov     rax, [rbx]
0x1800038cc  lea     rdx, [rsp+58h+arg_10]
0x1800038d1  mov     rcx, rbx
0x1800038d4  mov     rax, [rax+38h]
0x1800038d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038dd  test    eax, eax
0x1800038df  jns     short loc_1800038E9
0x1800038e1  mov     [rsp+58h+arg_10], 80004005h
0x1800038e9  mov     rax, [rbx]
0x1800038ec  lea     rdx, [rsp+58h+var_18]
0x1800038f1  mov     rcx, rbx
0x1800038f4  mov     rax, [rax+40h]
0x1800038f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038fd  test    eax, eax
0x1800038ff  jns     short loc_18000390A
0x180003901  mov     [rsp+58h+var_18], 0
0x18000390a  mov     rax, [rbx]
0x18000390d  lea     rdx, [rsp+58h+bstrString]
0x180003912  mov     rcx, rbx
0x180003915  mov     rax, [rax+48h]
0x180003919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000391e  test    eax, eax
0x180003920  jns     short loc_18000392B
0x180003922  mov     [rsp+58h+bstrString], 0
0x18000392b  cmp     [rsp+58h+bstrString], 0
0x180003931  jnz     short loc_180003945
0x180003933  lea     rcx, base; psz
0x18000393a  call    cs:__imp_SysAllocString
0x180003940  mov     [rsp+58h+bstrString], rax
0x180003945  mov     rax, [rsp+58h+bstrString]
0x18000394a  mov     [rsp+58h+var_30], rax
0x18000394f  mov     eax, [rsp+58h+arg_10]
0x180003953  mov     [rsp+58h+var_38], eax
0x180003957  mov     r9d, [rsp+58h+arg_18]
0x18000395c  mov     r8d, [rsp+58h+var_28]
0x180003961  lea     rdx, aXmlParseErrorL; "XML Parse error: line %lu, line positio"...
0x180003968  mov     ecx, 1
0x18000396d  call    DsRolepLogPrintRoutine
0x180003972  mov     eax, [rsp+58h+arg_10]
0x180003976  mov     [rdi], eax
0x180003978  mov     rcx, [rsp+58h+bstrString]; bstrString
0x18000397d  call    cs:__imp_SysFreeString
0x180003983  mov     rbx, [rsp+58h+arg_0]
0x180003988  add     rsp, 50h
0x18000398c  pop     rdi
0x18000398d  retn
0x18002c436  push    rbp
0x18002c438  sub     rsp, 30h
0x18002c43c  mov     rbp, rdx
0x18002c43f  mov     rcx, [rbp+38h]; bstrString
0x18002c443  call    cs:__imp_SysFreeString
0x18002c449  nop
0x18002c44a  add     rsp, 30h
0x18002c44e  pop     rbp
0x18002c44f  retn
```
