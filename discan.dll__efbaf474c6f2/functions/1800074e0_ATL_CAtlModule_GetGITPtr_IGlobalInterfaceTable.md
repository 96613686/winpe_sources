# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800074e0`
- end: `0x180007555`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800074e0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007522`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007522`

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
0x1800074e0  mov     [rsp+arg_0], rbx
0x1800074e5  mov     [rsp+arg_8], rsi
0x1800074ea  push    rdi
0x1800074eb  sub     rsp, 30h
0x1800074ef  mov     rsi, rdx
0x1800074f2  test    rdx, rdx
0x1800074f5  jnz     short loc_1800074FE
0x1800074f7  mov     eax, 80004003h
0x1800074fc  jmp     short loc_180007545
0x1800074fe  xor     edi, edi
0x180007500  lea     rbx, [rcx+40h]
0x180007504  cmp     [rbx], rdi
0x180007507  jnz     short loc_18000752E
0x180007509  mov     [rsp+38h+ppv], rbx; ppv
0x18000750e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007515  xor     edx, edx; pUnkOuter
0x180007517  lea     r8d, [rdi+1]; dwClsContext
0x18000751b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007522  call    cs:__imp_CoCreateInstance
0x180007528  mov     edi, eax
0x18000752a  test    eax, eax
0x18000752c  js      short loc_180007543
0x18000752e  mov     rcx, [rbx]
0x180007531  mov     [rsi], rcx
0x180007534  mov     rcx, [rbx]
0x180007537  mov     rdx, [rcx]
0x18000753a  mov     rax, [rdx+8]
0x18000753e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007543  mov     eax, edi
0x180007545  mov     rbx, [rsp+38h+arg_0]
0x18000754a  mov     rsi, [rsp+38h+arg_8]
0x18000754f  add     rsp, 30h
0x180007553  pop     rdi
0x180007554  retn
```
