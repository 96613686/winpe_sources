# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000a790`
- end: `0x18000a805`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a790`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a7d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a7d2`

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
0x18000a790  mov     [rsp+arg_0], rbx
0x18000a795  mov     [rsp+arg_8], rsi
0x18000a79a  push    rdi
0x18000a79b  sub     rsp, 30h
0x18000a79f  mov     rsi, rdx
0x18000a7a2  test    rdx, rdx
0x18000a7a5  jnz     short loc_18000A7AE
0x18000a7a7  mov     eax, 80004003h
0x18000a7ac  jmp     short loc_18000A7F5
0x18000a7ae  xor     edi, edi
0x18000a7b0  lea     rbx, [rcx+40h]
0x18000a7b4  cmp     [rbx], rdi
0x18000a7b7  jnz     short loc_18000A7DE
0x18000a7b9  mov     [rsp+38h+ppv], rbx; ppv
0x18000a7be  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000a7c5  xor     edx, edx; pUnkOuter
0x18000a7c7  lea     r8d, [rdi+1]; dwClsContext
0x18000a7cb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000a7d2  call    cs:__imp_CoCreateInstance
0x18000a7d8  mov     edi, eax
0x18000a7da  test    eax, eax
0x18000a7dc  js      short loc_18000A7F3
0x18000a7de  mov     rcx, [rbx]
0x18000a7e1  mov     [rsi], rcx
0x18000a7e4  mov     rcx, [rbx]
0x18000a7e7  mov     rdx, [rcx]
0x18000a7ea  mov     rax, [rdx+8]
0x18000a7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7f3  mov     eax, edi
0x18000a7f5  mov     rbx, [rsp+38h+arg_0]
0x18000a7fa  mov     rsi, [rsp+38h+arg_8]
0x18000a7ff  add     rsp, 30h
0x18000a803  pop     rdi
0x18000a804  retn
```
