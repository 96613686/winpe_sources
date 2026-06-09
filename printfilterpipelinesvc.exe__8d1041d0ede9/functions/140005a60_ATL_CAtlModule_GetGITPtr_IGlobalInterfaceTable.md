# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x140005a60`
- end: `0x140005ad5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005a60`
- `0x140063010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140005aa2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140005aa2`

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
0x140005a60  mov     [rsp+arg_0], rbx
0x140005a65  mov     [rsp+arg_8], rsi
0x140005a6a  push    rdi
0x140005a6b  sub     rsp, 30h
0x140005a6f  mov     rsi, rdx
0x140005a72  test    rdx, rdx
0x140005a75  jnz     short loc_140005A7E
0x140005a77  mov     eax, 80004003h
0x140005a7c  jmp     short loc_140005AC5
0x140005a7e  xor     edi, edi
0x140005a80  lea     rbx, [rcx+40h]
0x140005a84  cmp     [rbx], rdi
0x140005a87  jnz     short loc_140005AAE
0x140005a89  mov     [rsp+38h+ppv], rbx; ppv
0x140005a8e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x140005a95  xor     edx, edx; pUnkOuter
0x140005a97  lea     r8d, [rdi+1]; dwClsContext
0x140005a9b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x140005aa2  call    cs:__imp_CoCreateInstance
0x140005aa8  mov     edi, eax
0x140005aaa  test    eax, eax
0x140005aac  js      short loc_140005AC3
0x140005aae  mov     rcx, [rbx]
0x140005ab1  mov     [rsi], rcx
0x140005ab4  mov     rcx, [rbx]
0x140005ab7  mov     rdx, [rcx]
0x140005aba  mov     rax, [rdx+8]
0x140005abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ac3  mov     eax, edi
0x140005ac5  mov     rbx, [rsp+38h+arg_0]
0x140005aca  mov     rsi, [rsp+38h+arg_8]
0x140005acf  add     rsp, 30h
0x140005ad3  pop     rdi
0x140005ad4  retn
```
