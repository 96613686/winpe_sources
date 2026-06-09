# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800045d0`
- end: `0x180004645`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800045d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004612`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004612`

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
0x1800045d0  mov     [rsp+arg_0], rbx
0x1800045d5  mov     [rsp+arg_8], rsi
0x1800045da  push    rdi
0x1800045db  sub     rsp, 30h
0x1800045df  mov     rsi, rdx
0x1800045e2  test    rdx, rdx
0x1800045e5  jnz     short loc_1800045EE
0x1800045e7  mov     eax, 80004003h
0x1800045ec  jmp     short loc_180004635
0x1800045ee  xor     edi, edi
0x1800045f0  lea     rbx, [rcx+40h]
0x1800045f4  cmp     [rbx], rdi
0x1800045f7  jnz     short loc_18000461E
0x1800045f9  mov     [rsp+38h+ppv], rbx; ppv
0x1800045fe  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180004605  xor     edx, edx; pUnkOuter
0x180004607  lea     r8d, [rdi+1]; dwClsContext
0x18000460b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004612  call    cs:__imp_CoCreateInstance
0x180004618  mov     edi, eax
0x18000461a  test    eax, eax
0x18000461c  js      short loc_180004633
0x18000461e  mov     rcx, [rbx]
0x180004621  mov     [rsi], rcx
0x180004624  mov     rcx, [rbx]
0x180004627  mov     rdx, [rcx]
0x18000462a  mov     rax, [rdx+8]
0x18000462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004633  mov     eax, edi
0x180004635  mov     rbx, [rsp+38h+arg_0]
0x18000463a  mov     rsi, [rsp+38h+arg_8]
0x18000463f  add     rsp, 30h
0x180004643  pop     rdi
0x180004644  retn
```
