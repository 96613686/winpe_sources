# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180005970`
- end: `0x1800059e5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005970`
- `0x18000b010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800059b2`
- `ole32!CoCreateInstance` at `0x1800059b2`

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
0x180005970  mov     [rsp+arg_0], rbx
0x180005975  mov     [rsp+arg_8], rsi
0x18000597a  push    rdi
0x18000597b  sub     rsp, 30h
0x18000597f  mov     rsi, rdx
0x180005982  test    rdx, rdx
0x180005985  jnz     short loc_18000598E
0x180005987  mov     eax, 80004003h
0x18000598c  jmp     short loc_1800059D5
0x18000598e  xor     edi, edi
0x180005990  lea     rbx, [rcx+40h]
0x180005994  cmp     [rbx], rdi
0x180005997  jnz     short loc_1800059BE
0x180005999  mov     [rsp+38h+ppv], rbx; ppv
0x18000599e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800059a5  xor     edx, edx; pUnkOuter
0x1800059a7  lea     r8d, [rdi+1]; dwClsContext
0x1800059ab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800059b2  call    cs:__imp_CoCreateInstance
0x1800059b8  mov     edi, eax
0x1800059ba  test    eax, eax
0x1800059bc  js      short loc_1800059D3
0x1800059be  mov     rcx, [rbx]
0x1800059c1  mov     [rsi], rcx
0x1800059c4  mov     rcx, [rbx]
0x1800059c7  mov     rdx, [rcx]
0x1800059ca  mov     rax, [rdx+8]
0x1800059ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059d3  mov     eax, edi
0x1800059d5  mov     rbx, [rsp+38h+arg_0]
0x1800059da  mov     rsi, [rsp+38h+arg_8]
0x1800059df  add     rsp, 30h
0x1800059e3  pop     rdi
0x1800059e4  retn
```
