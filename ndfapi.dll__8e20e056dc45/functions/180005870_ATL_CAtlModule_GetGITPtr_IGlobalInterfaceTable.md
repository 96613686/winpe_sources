# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180005870`
- end: `0x1800058e5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005870`
- `0x180021010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800058b2`
- `ole32!CoCreateInstance` at `0x1800058b2`

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
0x180005870  mov     [rsp+arg_0], rbx
0x180005875  mov     [rsp+arg_8], rsi
0x18000587a  push    rdi
0x18000587b  sub     rsp, 30h
0x18000587f  mov     rsi, rdx
0x180005882  test    rdx, rdx
0x180005885  jnz     short loc_18000588E
0x180005887  mov     eax, 80004003h
0x18000588c  jmp     short loc_1800058D5
0x18000588e  xor     edi, edi
0x180005890  lea     rbx, [rcx+40h]
0x180005894  cmp     [rbx], rdi
0x180005897  jnz     short loc_1800058BE
0x180005899  mov     [rsp+38h+ppv], rbx; ppv
0x18000589e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800058a5  xor     edx, edx; pUnkOuter
0x1800058a7  lea     r8d, [rdi+1]; dwClsContext
0x1800058ab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800058b2  call    cs:__imp_CoCreateInstance
0x1800058b8  mov     edi, eax
0x1800058ba  test    eax, eax
0x1800058bc  js      short loc_1800058D3
0x1800058be  mov     rcx, [rbx]
0x1800058c1  mov     [rsi], rcx
0x1800058c4  mov     rcx, [rbx]
0x1800058c7  mov     rdx, [rcx]
0x1800058ca  mov     rax, [rdx+8]
0x1800058ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d3  mov     eax, edi
0x1800058d5  mov     rbx, [rsp+38h+arg_0]
0x1800058da  mov     rsi, [rsp+38h+arg_8]
0x1800058df  add     rsp, 30h
0x1800058e3  pop     rdi
0x1800058e4  retn
```
