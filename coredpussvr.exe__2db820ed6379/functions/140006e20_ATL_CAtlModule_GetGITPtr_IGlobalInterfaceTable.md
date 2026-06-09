# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x140006e20`
- end: `0x140006e9c`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140006e20`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006e62`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006e62`

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
0x140006e20  mov     [rsp+arg_0], rbx
0x140006e25  mov     [rsp+arg_8], rsi
0x140006e2a  push    rdi
0x140006e2b  sub     rsp, 30h
0x140006e2f  mov     rsi, rdx
0x140006e32  test    rdx, rdx
0x140006e35  jnz     short loc_140006E3E
0x140006e37  mov     eax, 80004003h
0x140006e3c  jmp     short loc_140006E8B
0x140006e3e  xor     edi, edi
0x140006e40  lea     rbx, [rcx+40h]
0x140006e44  cmp     [rbx], rdi
0x140006e47  jnz     short loc_140006E74
0x140006e49  mov     [rsp+38h+ppv], rbx; ppv
0x140006e4e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x140006e55  xor     edx, edx; pUnkOuter
0x140006e57  lea     r8d, [rdi+1]; dwClsContext
0x140006e5b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x140006e62  call    cs:__imp_CoCreateInstance
0x140006e69  nop     dword ptr [rax+rax+00h]
0x140006e6e  mov     edi, eax
0x140006e70  test    eax, eax
0x140006e72  js      short loc_140006E89
0x140006e74  mov     rcx, [rbx]
0x140006e77  mov     [rsi], rcx
0x140006e7a  mov     rcx, [rbx]
0x140006e7d  mov     rdx, [rcx]
0x140006e80  mov     rax, [rdx+8]
0x140006e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e89  mov     eax, edi
0x140006e8b  mov     rbx, [rsp+38h+arg_0]
0x140006e90  mov     rsi, [rsp+38h+arg_8]
0x140006e95  add     rsp, 30h
0x140006e99  pop     rdi
0x140006e9a  retn
```
