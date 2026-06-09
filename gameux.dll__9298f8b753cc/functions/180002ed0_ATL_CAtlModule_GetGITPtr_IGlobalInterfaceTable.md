# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180002ed0`
- end: `0x180002f45`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ed0`
- `0x180004010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180002f12`
- `ole32!CoCreateInstance` at `0x180002f12`

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
0x180002ed0  mov     [rsp+arg_0], rbx
0x180002ed5  mov     [rsp+arg_8], rsi
0x180002eda  push    rdi
0x180002edb  sub     rsp, 30h
0x180002edf  mov     rsi, rdx
0x180002ee2  test    rdx, rdx
0x180002ee5  jnz     short loc_180002EEE
0x180002ee7  mov     eax, 80004003h
0x180002eec  jmp     short loc_180002F35
0x180002eee  xor     edi, edi
0x180002ef0  lea     rbx, [rcx+40h]
0x180002ef4  cmp     [rbx], rdi
0x180002ef7  jnz     short loc_180002F1E
0x180002ef9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180002f00  mov     [rsp+38h+ppv], rbx; ppv
0x180002f05  xor     edx, edx; pUnkOuter
0x180002f07  lea     r8d, [rdi+1]; dwClsContext
0x180002f0b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180002f12  call    cs:__imp_CoCreateInstance
0x180002f18  mov     edi, eax
0x180002f1a  test    eax, eax
0x180002f1c  js      short loc_180002F33
0x180002f1e  mov     rcx, [rbx]
0x180002f21  mov     [rsi], rcx
0x180002f24  mov     rcx, [rbx]
0x180002f27  mov     rdx, [rcx]
0x180002f2a  mov     rax, [rdx+8]
0x180002f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f33  mov     eax, edi
0x180002f35  mov     rbx, [rsp+38h+arg_0]
0x180002f3a  mov     rsi, [rsp+38h+arg_8]
0x180002f3f  add     rsp, 30h
0x180002f43  pop     rdi
0x180002f44  retn
```
