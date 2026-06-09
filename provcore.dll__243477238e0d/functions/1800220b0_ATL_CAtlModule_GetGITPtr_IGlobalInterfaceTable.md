# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800220b0`
- end: `0x180022125`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `HRESULT __fastcall(ATL::CAtlModule *this, IGlobalInterfaceTable **ppGIT)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800220b0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800220f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800220f2`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, IGlobalInterfaceTable **ppGIT)
{
  HRESULT Instance; // edi
  IGlobalInterfaceTable **p_m_pGIT; // rbx

  if ( !ppGIT )
    return 2147500035LL;
  Instance = 0;
  p_m_pGIT = &this->m_pGIT;
  if ( this->m_pGIT
    || (Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)&this->m_pGIT),
        Instance >= 0) )
  {
    *ppGIT = *p_m_pGIT;
    (*p_m_pGIT)->AddRef(*p_m_pGIT);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800220b0  mov     [rsp+arg_0], rbx
0x1800220b5  mov     [rsp+arg_8], rsi
0x1800220ba  push    rdi
0x1800220bb  sub     rsp, 30h
0x1800220bf  mov     rsi, ppGIT
0x1800220c2  test    ppGIT, ppGIT
0x1800220c5  jnz     short loc_1800220CE
0x1800220c7  mov     eax, 80004003h
0x1800220cc  jmp     short loc_180022115
0x1800220ce  xor     edi, edi
0x1800220d0  lea     rbx, [this+40h]
0x1800220d4  cmp     [rbx], rdi
0x1800220d7  jnz     short loc_1800220FE
0x1800220d9  mov     [rsp+38h+ppv], rbx; ppv
0x1800220de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800220e5  xor     edx, edx; pUnkOuter
0x1800220e7  lea     r8d, [rdi+1]; dwClsContext
0x1800220eb  lea     this, CLSID_StdGlobalInterfaceTable; rclsid
0x1800220f2  call    cs:__imp_CoCreateInstance
0x1800220f8  mov     edi, eax
0x1800220fa  test    eax, eax
0x1800220fc  js      short loc_180022113
0x1800220fe  mov     this, [rbx]
0x180022101  mov     [rsi], this
0x180022104  mov     this, [rbx]
0x180022107  mov     ppGIT, [this]
0x18002210a  mov     rax, [ppGIT+8]
0x18002210e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022113  mov     eax, edi
0x180022115  mov     rbx, [rsp+38h+arg_0]
0x18002211a  mov     rsi, [rsp+38h+arg_8]
0x18002211f  add     rsp, 30h
0x180022123  pop     rdi
0x180022124  retn
```
