# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800042e0`
- end: `0x180004355`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800042e0`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004322`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004322`

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
0x1800042e0  mov     [rsp+arg_0], rbx
0x1800042e5  mov     [rsp+arg_8], rsi
0x1800042ea  push    rdi
0x1800042eb  sub     rsp, 30h
0x1800042ef  mov     rsi, rdx
0x1800042f2  test    rdx, rdx
0x1800042f5  jnz     short loc_1800042FE
0x1800042f7  mov     eax, 80004003h
0x1800042fc  jmp     short loc_180004345
0x1800042fe  xor     edi, edi
0x180004300  lea     rbx, [rcx+40h]
0x180004304  cmp     [rbx], rdi
0x180004307  jnz     short loc_18000432E
0x180004309  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180004310  mov     [rsp+38h+ppv], rbx; ppv
0x180004315  xor     edx, edx; pUnkOuter
0x180004317  lea     r8d, [rdi+1]; dwClsContext
0x18000431b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004322  call    cs:__imp_CoCreateInstance
0x180004328  mov     edi, eax
0x18000432a  test    eax, eax
0x18000432c  js      short loc_180004343
0x18000432e  mov     rcx, [rbx]
0x180004331  mov     [rsi], rcx
0x180004334  mov     rcx, [rbx]
0x180004337  mov     rdx, [rcx]
0x18000433a  mov     rax, [rdx+8]
0x18000433e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004343  mov     eax, edi
0x180004345  mov     rbx, [rsp+38h+arg_0]
0x18000434a  mov     rsi, [rsp+38h+arg_8]
0x18000434f  add     rsp, 30h
0x180004353  pop     rdi
0x180004354  retn
```
