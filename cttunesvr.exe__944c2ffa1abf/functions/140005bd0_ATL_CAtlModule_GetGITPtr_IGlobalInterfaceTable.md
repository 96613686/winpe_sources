# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x140005bd0`
- end: `0x140005c45`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005bd0`
- `0x140007010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140005c12`
- `ole32!CoCreateInstance` at `0x140005c12`

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
0x140005bd0  mov     [rsp+arg_0], rbx
0x140005bd5  mov     [rsp+arg_8], rsi
0x140005bda  push    rdi
0x140005bdb  sub     rsp, 30h
0x140005bdf  mov     rsi, rdx
0x140005be2  test    rdx, rdx
0x140005be5  jnz     short loc_140005BEE
0x140005be7  mov     eax, 80004003h
0x140005bec  jmp     short loc_140005C35
0x140005bee  xor     edi, edi
0x140005bf0  lea     rbx, [rcx+40h]
0x140005bf4  cmp     [rbx], rdi
0x140005bf7  jnz     short loc_140005C1E
0x140005bf9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x140005c00  mov     [rsp+38h+ppv], rbx; ppv
0x140005c05  xor     edx, edx; pUnkOuter
0x140005c07  lea     r8d, [rdi+1]; dwClsContext
0x140005c0b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x140005c12  call    cs:__imp_CoCreateInstance
0x140005c18  mov     edi, eax
0x140005c1a  test    eax, eax
0x140005c1c  js      short loc_140005C33
0x140005c1e  mov     rcx, [rbx]
0x140005c21  mov     [rsi], rcx
0x140005c24  mov     rcx, [rbx]
0x140005c27  mov     rdx, [rcx]
0x140005c2a  mov     rax, [rdx+8]
0x140005c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c33  mov     eax, edi
0x140005c35  mov     rbx, [rsp+38h+arg_0]
0x140005c3a  mov     rsi, [rsp+38h+arg_8]
0x140005c3f  add     rsp, 30h
0x140005c43  pop     rdi
0x140005c44  retn
```
