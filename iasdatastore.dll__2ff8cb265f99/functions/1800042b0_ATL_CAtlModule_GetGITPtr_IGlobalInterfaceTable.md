# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800042b0`
- end: `0x180004325`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800042b0`
- `0x180010010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800042f2`
- `ole32!CoCreateInstance` at `0x1800042f2`

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
0x1800042b0  mov     [rsp+arg_0], rbx
0x1800042b5  mov     [rsp+arg_8], rsi
0x1800042ba  push    rdi
0x1800042bb  sub     rsp, 30h
0x1800042bf  mov     rsi, rdx
0x1800042c2  test    rdx, rdx
0x1800042c5  jnz     short loc_1800042CE
0x1800042c7  mov     eax, 80004003h
0x1800042cc  jmp     short loc_180004315
0x1800042ce  xor     edi, edi
0x1800042d0  lea     rbx, [rcx+40h]
0x1800042d4  cmp     [rbx], rdi
0x1800042d7  jnz     short loc_1800042FE
0x1800042d9  mov     [rsp+38h+ppv], rbx; ppv
0x1800042de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800042e5  xor     edx, edx; pUnkOuter
0x1800042e7  lea     r8d, [rdi+1]; dwClsContext
0x1800042eb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800042f2  call    cs:__imp_CoCreateInstance
0x1800042f8  mov     edi, eax
0x1800042fa  test    eax, eax
0x1800042fc  js      short loc_180004313
0x1800042fe  mov     rcx, [rbx]
0x180004301  mov     [rsi], rcx
0x180004304  mov     rcx, [rbx]
0x180004307  mov     rdx, [rcx]
0x18000430a  mov     rax, [rdx+8]
0x18000430e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004313  mov     eax, edi
0x180004315  mov     rbx, [rsp+38h+arg_0]
0x18000431a  mov     rsi, [rsp+38h+arg_8]
0x18000431f  add     rsp, 30h
0x180004323  pop     rdi
0x180004324  retn
```
