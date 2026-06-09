# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800081b0`
- end: `0x180008225`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800081b0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800081f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800081f2`

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
0x1800081b0  mov     [rsp+arg_0], rbx
0x1800081b5  mov     [rsp+arg_8], rsi
0x1800081ba  push    rdi
0x1800081bb  sub     rsp, 30h
0x1800081bf  mov     rsi, rdx
0x1800081c2  test    rdx, rdx
0x1800081c5  jnz     short loc_1800081CE
0x1800081c7  mov     eax, 80004003h
0x1800081cc  jmp     short loc_180008215
0x1800081ce  xor     edi, edi
0x1800081d0  lea     rbx, [rcx+40h]
0x1800081d4  cmp     [rbx], rdi
0x1800081d7  jnz     short loc_1800081FE
0x1800081d9  mov     [rsp+38h+ppv], rbx; ppv
0x1800081de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800081e5  xor     edx, edx; pUnkOuter
0x1800081e7  lea     r8d, [rdi+1]; dwClsContext
0x1800081eb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800081f2  call    cs:__imp_CoCreateInstance
0x1800081f8  mov     edi, eax
0x1800081fa  test    eax, eax
0x1800081fc  js      short loc_180008213
0x1800081fe  mov     rcx, [rbx]
0x180008201  mov     [rsi], rcx
0x180008204  mov     rcx, [rbx]
0x180008207  mov     rdx, [rcx]
0x18000820a  mov     rax, [rdx+8]
0x18000820e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008213  mov     eax, edi
0x180008215  mov     rbx, [rsp+38h+arg_0]
0x18000821a  mov     rsi, [rsp+38h+arg_8]
0x18000821f  add     rsp, 30h
0x180008223  pop     rdi
0x180008224  retn
```
