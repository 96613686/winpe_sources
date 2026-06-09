# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180004e70`
- end: `0x180004ee5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004e70`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004eb2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004eb2`

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
0x180004e70  mov     [rsp+arg_0], rbx
0x180004e75  mov     [rsp+arg_8], rsi
0x180004e7a  push    rdi
0x180004e7b  sub     rsp, 30h
0x180004e7f  mov     rsi, rdx
0x180004e82  test    rdx, rdx
0x180004e85  jnz     short loc_180004E8E
0x180004e87  mov     eax, 80004003h
0x180004e8c  jmp     short loc_180004ED5
0x180004e8e  xor     edi, edi
0x180004e90  lea     rbx, [rcx+40h]
0x180004e94  cmp     [rbx], rdi
0x180004e97  jnz     short loc_180004EBE
0x180004e99  mov     [rsp+38h+ppv], rbx; ppv
0x180004e9e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180004ea5  xor     edx, edx; pUnkOuter
0x180004ea7  lea     r8d, [rdi+1]; dwClsContext
0x180004eab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004eb2  call    cs:__imp_CoCreateInstance
0x180004eb8  mov     edi, eax
0x180004eba  test    eax, eax
0x180004ebc  js      short loc_180004ED3
0x180004ebe  mov     rcx, [rbx]
0x180004ec1  mov     [rsi], rcx
0x180004ec4  mov     rcx, [rbx]
0x180004ec7  mov     rdx, [rcx]
0x180004eca  mov     rax, [rdx+8]
0x180004ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed3  mov     eax, edi
0x180004ed5  mov     rbx, [rsp+38h+arg_0]
0x180004eda  mov     rsi, [rsp+38h+arg_8]
0x180004edf  add     rsp, 30h
0x180004ee3  pop     rdi
0x180004ee4  retn
```
