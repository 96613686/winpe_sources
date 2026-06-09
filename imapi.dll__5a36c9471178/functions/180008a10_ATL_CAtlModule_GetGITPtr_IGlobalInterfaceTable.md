# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180008a10`
- end: `0x180008a85`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008a10`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180008a52`
- `ole32!CoCreateInstance` at `0x180008a52`

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
0x180008a10  mov     [rsp+arg_0], rbx
0x180008a15  mov     [rsp+arg_8], rsi
0x180008a1a  push    rdi
0x180008a1b  sub     rsp, 30h
0x180008a1f  mov     rsi, rdx
0x180008a22  test    rdx, rdx
0x180008a25  jnz     short loc_180008A2E
0x180008a27  mov     eax, 80004003h
0x180008a2c  jmp     short loc_180008A75
0x180008a2e  xor     edi, edi
0x180008a30  lea     rbx, [rcx+40h]
0x180008a34  cmp     [rbx], rdi
0x180008a37  jnz     short loc_180008A5E
0x180008a39  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180008a40  mov     [rsp+38h+ppv], rbx; ppv
0x180008a45  xor     edx, edx; pUnkOuter
0x180008a47  lea     r8d, [rdi+1]; dwClsContext
0x180008a4b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180008a52  call    cs:__imp_CoCreateInstance
0x180008a58  mov     edi, eax
0x180008a5a  test    eax, eax
0x180008a5c  js      short loc_180008A73
0x180008a5e  mov     rcx, [rbx]
0x180008a61  mov     [rsi], rcx
0x180008a64  mov     rcx, [rbx]
0x180008a67  mov     rdx, [rcx]
0x180008a6a  mov     rax, [rdx+8]
0x180008a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a73  mov     eax, edi
0x180008a75  mov     rbx, [rsp+38h+arg_0]
0x180008a7a  mov     rsi, [rsp+38h+arg_8]
0x180008a7f  add     rsp, 30h
0x180008a83  pop     rdi
0x180008a84  retn
```
