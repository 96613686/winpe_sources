# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180010800`
- end: `0x180010875`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180010800`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010842`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010842`

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
0x180010800  mov     [rsp+arg_0], rbx
0x180010805  mov     [rsp+arg_8], rsi
0x18001080a  push    rdi
0x18001080b  sub     rsp, 30h
0x18001080f  mov     rsi, rdx
0x180010812  test    rdx, rdx
0x180010815  jnz     short loc_18001081E
0x180010817  mov     eax, 80004003h
0x18001081c  jmp     short loc_180010865
0x18001081e  xor     edi, edi
0x180010820  lea     rbx, [rcx+40h]
0x180010824  cmp     [rbx], rdi
0x180010827  jnz     short loc_18001084E
0x180010829  mov     [rsp+38h+ppv], rbx; ppv
0x18001082e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180010835  xor     edx, edx; pUnkOuter
0x180010837  lea     r8d, [rdi+1]; dwClsContext
0x18001083b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180010842  call    cs:__imp_CoCreateInstance
0x180010848  mov     edi, eax
0x18001084a  test    eax, eax
0x18001084c  js      short loc_180010863
0x18001084e  mov     rcx, [rbx]
0x180010851  mov     [rsi], rcx
0x180010854  mov     rcx, [rbx]
0x180010857  mov     rdx, [rcx]
0x18001085a  mov     rax, [rdx+8]
0x18001085e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010863  mov     eax, edi
0x180010865  mov     rbx, [rsp+38h+arg_0]
0x18001086a  mov     rsi, [rsp+38h+arg_8]
0x18001086f  add     rsp, 30h
0x180010873  pop     rdi
0x180010874  retn
```
