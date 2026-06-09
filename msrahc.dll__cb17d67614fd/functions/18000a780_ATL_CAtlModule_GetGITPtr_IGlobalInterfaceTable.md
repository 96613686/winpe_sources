# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000a780`
- end: `0x18000a7f5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a780`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a7c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a7c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000a780  mov     [rsp+arg_0], rbx
0x18000a785  mov     [rsp+arg_8], rsi
0x18000a78a  push    rdi
0x18000a78b  sub     rsp, 30h
0x18000a78f  mov     rsi, rdx
0x18000a792  test    rdx, rdx
0x18000a795  jnz     short loc_18000A79E
0x18000a797  mov     eax, 80004003h
0x18000a79c  jmp     short loc_18000A7E5
0x18000a79e  xor     edi, edi
0x18000a7a0  lea     rbx, [rcx+40h]
0x18000a7a4  cmp     [rbx], rdi
0x18000a7a7  jnz     short loc_18000A7CE
0x18000a7a9  mov     [rsp+38h+ppv], rbx; ppv
0x18000a7ae  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000a7b5  xor     edx, edx; pUnkOuter
0x18000a7b7  lea     r8d, [rdi+1]; dwClsContext
0x18000a7bb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000a7c2  call    cs:__imp_CoCreateInstance
0x18000a7c8  mov     edi, eax
0x18000a7ca  test    eax, eax
0x18000a7cc  js      short loc_18000A7E3
0x18000a7ce  mov     rcx, [rbx]
0x18000a7d1  mov     [rsi], rcx
0x18000a7d4  mov     rcx, [rbx]
0x18000a7d7  mov     rdx, [rcx]
0x18000a7da  mov     rax, [rdx+8]
0x18000a7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e3  mov     eax, edi
0x18000a7e5  mov     rbx, [rsp+38h+arg_0]
0x18000a7ea  mov     rsi, [rsp+38h+arg_8]
0x18000a7ef  add     rsp, 30h
0x18000a7f3  pop     rdi
0x18000a7f4  retn
```
