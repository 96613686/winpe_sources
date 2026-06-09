# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800198a0`
- end: `0x180019915`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800198a0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800198e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800198e2`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // edi
  _QWORD *v5; // rbx

  if ( !a2 )
    return 2147500035LL;
  Instance = 0;
  v5 = (_QWORD *)((char *)this + 64);
  if ( *((_QWORD *)this + 8)
    || (Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)this + 8),
        Instance >= 0) )
  {
    *a2 = (struct IGlobalInterfaceTable *)*v5;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800198a0  mov     [rsp+arg_0], rbx
0x1800198a5  mov     [rsp+arg_8], rsi
0x1800198aa  push    rdi
0x1800198ab  sub     rsp, 30h
0x1800198af  mov     rsi, rdx
0x1800198b2  test    rdx, rdx
0x1800198b5  jnz     short loc_1800198BE
0x1800198b7  mov     eax, 80004003h
0x1800198bc  jmp     short loc_180019905
0x1800198be  xor     edi, edi
0x1800198c0  lea     rbx, [rcx+40h]
0x1800198c4  cmp     [rbx], rdi
0x1800198c7  jnz     short loc_1800198EE
0x1800198c9  mov     [rsp+38h+ppv], rbx; ppv
0x1800198ce  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800198d5  xor     edx, edx; pUnkOuter
0x1800198d7  lea     r8d, [rdi+1]; dwClsContext
0x1800198db  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800198e2  call    cs:__imp_CoCreateInstance
0x1800198e8  mov     edi, eax
0x1800198ea  test    eax, eax
0x1800198ec  js      short loc_180019903
0x1800198ee  mov     rcx, [rbx]
0x1800198f1  mov     [rsi], rcx
0x1800198f4  mov     rcx, [rbx]
0x1800198f7  mov     rdx, [rcx]
0x1800198fa  mov     rax, [rdx+8]
0x1800198fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019903  mov     eax, edi
0x180019905  mov     rbx, [rsp+38h+arg_0]
0x18001990a  mov     rsi, [rsp+38h+arg_8]
0x18001990f  add     rsp, 30h
0x180019913  pop     rdi
0x180019914  retn
```
