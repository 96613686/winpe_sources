# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180008550`
- end: `0x1800085cc`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008550`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008592`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008592`

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
0x180008550  mov     [rsp+arg_0], rbx
0x180008555  mov     [rsp+arg_8], rsi
0x18000855a  push    rdi
0x18000855b  sub     rsp, 30h
0x18000855f  mov     rsi, rdx
0x180008562  test    rdx, rdx
0x180008565  jnz     short loc_18000856E
0x180008567  mov     eax, 80004003h
0x18000856c  jmp     short loc_1800085BB
0x18000856e  xor     edi, edi
0x180008570  lea     rbx, [rcx+40h]
0x180008574  cmp     [rbx], rdi
0x180008577  jnz     short loc_1800085A4
0x180008579  mov     [rsp+38h+ppv], rbx; ppv
0x18000857e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180008585  xor     edx, edx; pUnkOuter
0x180008587  lea     r8d, [rdi+1]; dwClsContext
0x18000858b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180008592  call    cs:__imp_CoCreateInstance
0x180008599  nop     dword ptr [rax+rax+00h]
0x18000859e  mov     edi, eax
0x1800085a0  test    eax, eax
0x1800085a2  js      short loc_1800085B9
0x1800085a4  mov     rcx, [rbx]
0x1800085a7  mov     [rsi], rcx
0x1800085aa  mov     rcx, [rbx]
0x1800085ad  mov     rdx, [rcx]
0x1800085b0  mov     rax, [rdx+8]
0x1800085b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085b9  mov     eax, edi
0x1800085bb  mov     rbx, [rsp+38h+arg_0]
0x1800085c0  mov     rsi, [rsp+38h+arg_8]
0x1800085c5  add     rsp, 30h
0x1800085c9  pop     rdi
0x1800085ca  retn
```
