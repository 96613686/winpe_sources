# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18005c4f0`
- end: `0x18005c565`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18005c4f0`
- `0x1800d6010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18005c532`
- `ole32!CoCreateInstance` at `0x18005c532`

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
0x18005c4f0  mov     [rsp+arg_0], rbx
0x18005c4f5  mov     [rsp+arg_8], rsi
0x18005c4fa  push    rdi
0x18005c4fb  sub     rsp, 30h
0x18005c4ff  mov     rsi, rdx
0x18005c502  test    rdx, rdx
0x18005c505  jnz     short loc_18005C50E
0x18005c507  mov     eax, 80004003h
0x18005c50c  jmp     short loc_18005C555
0x18005c50e  xor     edi, edi
0x18005c510  lea     rbx, [rcx+40h]
0x18005c514  cmp     [rbx], rdi
0x18005c517  jnz     short loc_18005C53E
0x18005c519  mov     [rsp+38h+ppv], rbx; ppv
0x18005c51e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18005c525  xor     edx, edx; pUnkOuter
0x18005c527  lea     r8d, [rdi+1]; dwClsContext
0x18005c52b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18005c532  call    cs:__imp_CoCreateInstance
0x18005c538  mov     edi, eax
0x18005c53a  test    eax, eax
0x18005c53c  js      short loc_18005C553
0x18005c53e  mov     rcx, [rbx]
0x18005c541  mov     [rsi], rcx
0x18005c544  mov     rcx, [rbx]
0x18005c547  mov     rdx, [rcx]
0x18005c54a  mov     rax, [rdx+8]
0x18005c54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c553  mov     eax, edi
0x18005c555  mov     rbx, [rsp+38h+arg_0]
0x18005c55a  mov     rsi, [rsp+38h+arg_8]
0x18005c55f  add     rsp, 30h
0x18005c563  pop     rdi
0x18005c564  retn
```
