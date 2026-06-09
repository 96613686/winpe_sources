# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180018400`
- end: `0x180018475`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180018400`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018442`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018442`

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
0x180018400  mov     [rsp+arg_0], rbx
0x180018405  mov     [rsp+arg_8], rsi
0x18001840a  push    rdi
0x18001840b  sub     rsp, 30h
0x18001840f  mov     rsi, rdx
0x180018412  test    rdx, rdx
0x180018415  jnz     short loc_18001841E
0x180018417  mov     eax, 80004003h
0x18001841c  jmp     short loc_180018465
0x18001841e  xor     edi, edi
0x180018420  lea     rbx, [rcx+40h]
0x180018424  cmp     [rbx], rdi
0x180018427  jnz     short loc_18001844E
0x180018429  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180018430  mov     [rsp+38h+ppv], rbx; ppv
0x180018435  xor     edx, edx; pUnkOuter
0x180018437  lea     r8d, [rdi+1]; dwClsContext
0x18001843b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180018442  call    cs:__imp_CoCreateInstance
0x180018448  mov     edi, eax
0x18001844a  test    eax, eax
0x18001844c  js      short loc_180018463
0x18001844e  mov     rcx, [rbx]
0x180018451  mov     [rsi], rcx
0x180018454  mov     rcx, [rbx]
0x180018457  mov     rdx, [rcx]
0x18001845a  mov     rax, [rdx+8]
0x18001845e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018463  mov     eax, edi
0x180018465  mov     rbx, [rsp+38h+arg_0]
0x18001846a  mov     rsi, [rsp+38h+arg_8]
0x18001846f  add     rsp, 30h
0x180018473  pop     rdi
0x180018474  retn
```
