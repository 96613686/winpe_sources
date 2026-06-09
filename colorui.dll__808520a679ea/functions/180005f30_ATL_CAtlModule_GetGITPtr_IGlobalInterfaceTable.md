# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180005f30`
- end: `0x180005fa5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005f30`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180005f72`
- `ole32!CoCreateInstance` at `0x180005f72`

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
0x180005f30  mov     [rsp+arg_0], rbx
0x180005f35  mov     [rsp+arg_8], rsi
0x180005f3a  push    rdi
0x180005f3b  sub     rsp, 30h
0x180005f3f  mov     rsi, rdx
0x180005f42  test    rdx, rdx
0x180005f45  jnz     short loc_180005F4E
0x180005f47  mov     eax, 80004003h
0x180005f4c  jmp     short loc_180005F95
0x180005f4e  xor     edi, edi
0x180005f50  lea     rbx, [rcx+40h]
0x180005f54  cmp     [rbx], rdi
0x180005f57  jnz     short loc_180005F7E
0x180005f59  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180005f60  mov     [rsp+38h+ppv], rbx; ppv
0x180005f65  xor     edx, edx; pUnkOuter
0x180005f67  lea     r8d, [rdi+1]; dwClsContext
0x180005f6b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180005f72  call    cs:__imp_CoCreateInstance
0x180005f78  mov     edi, eax
0x180005f7a  test    eax, eax
0x180005f7c  js      short loc_180005F93
0x180005f7e  mov     rcx, [rbx]
0x180005f81  mov     [rsi], rcx
0x180005f84  mov     rcx, [rbx]
0x180005f87  mov     rdx, [rcx]
0x180005f8a  mov     rax, [rdx+8]
0x180005f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f93  mov     eax, edi
0x180005f95  mov     rbx, [rsp+38h+arg_0]
0x180005f9a  mov     rsi, [rsp+38h+arg_8]
0x180005f9f  add     rsp, 30h
0x180005fa3  pop     rdi
0x180005fa4  retn
```
