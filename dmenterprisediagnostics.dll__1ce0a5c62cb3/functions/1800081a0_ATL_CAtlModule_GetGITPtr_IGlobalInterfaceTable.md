# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800081a0`
- end: `0x180008215`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800081a0`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800081e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800081e2`

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
0x1800081a0  mov     [rsp+arg_0], rbx
0x1800081a5  mov     [rsp+arg_8], rsi
0x1800081aa  push    rdi
0x1800081ab  sub     rsp, 30h
0x1800081af  mov     rsi, rdx
0x1800081b2  test    rdx, rdx
0x1800081b5  jnz     short loc_1800081BE
0x1800081b7  mov     eax, 80004003h
0x1800081bc  jmp     short loc_180008205
0x1800081be  xor     edi, edi
0x1800081c0  lea     rbx, [rcx+40h]
0x1800081c4  cmp     [rbx], rdi
0x1800081c7  jnz     short loc_1800081EE
0x1800081c9  mov     [rsp+38h+ppv], rbx; ppv
0x1800081ce  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800081d5  xor     edx, edx; pUnkOuter
0x1800081d7  lea     r8d, [rdi+1]; dwClsContext
0x1800081db  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800081e2  call    cs:__imp_CoCreateInstance
0x1800081e8  mov     edi, eax
0x1800081ea  test    eax, eax
0x1800081ec  js      short loc_180008203
0x1800081ee  mov     rcx, [rbx]
0x1800081f1  mov     [rsi], rcx
0x1800081f4  mov     rcx, [rbx]
0x1800081f7  mov     rdx, [rcx]
0x1800081fa  mov     rax, [rdx+8]
0x1800081fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008203  mov     eax, edi
0x180008205  mov     rbx, [rsp+38h+arg_0]
0x18000820a  mov     rsi, [rsp+38h+arg_8]
0x18000820f  add     rsp, 30h
0x180008213  pop     rdi
0x180008214  retn
```
