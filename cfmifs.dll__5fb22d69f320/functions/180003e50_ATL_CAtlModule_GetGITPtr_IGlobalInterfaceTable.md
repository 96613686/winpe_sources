# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180003e50`
- end: `0x180003ec5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003e50`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003e92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003e92`

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
0x180003e50  mov     [rsp+arg_0], rbx
0x180003e55  mov     [rsp+arg_8], rsi
0x180003e5a  push    rdi
0x180003e5b  sub     rsp, 30h
0x180003e5f  mov     rsi, rdx
0x180003e62  test    rdx, rdx
0x180003e65  jnz     short loc_180003E6E
0x180003e67  mov     eax, 80004003h
0x180003e6c  jmp     short loc_180003EB5
0x180003e6e  xor     edi, edi
0x180003e70  lea     rbx, [rcx+40h]
0x180003e74  cmp     [rbx], rdi
0x180003e77  jnz     short loc_180003E9E
0x180003e79  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003e80  mov     [rsp+38h+ppv], rbx; ppv
0x180003e85  xor     edx, edx; pUnkOuter
0x180003e87  lea     r8d, [rdi+1]; dwClsContext
0x180003e8b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003e92  call    cs:__imp_CoCreateInstance
0x180003e98  mov     edi, eax
0x180003e9a  test    eax, eax
0x180003e9c  js      short loc_180003EB3
0x180003e9e  mov     rcx, [rbx]
0x180003ea1  mov     [rsi], rcx
0x180003ea4  mov     rcx, [rbx]
0x180003ea7  mov     rdx, [rcx]
0x180003eaa  mov     rax, [rdx+8]
0x180003eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb3  mov     eax, edi
0x180003eb5  mov     rbx, [rsp+38h+arg_0]
0x180003eba  mov     rsi, [rsp+38h+arg_8]
0x180003ebf  add     rsp, 30h
0x180003ec3  pop     rdi
0x180003ec4  retn
```
