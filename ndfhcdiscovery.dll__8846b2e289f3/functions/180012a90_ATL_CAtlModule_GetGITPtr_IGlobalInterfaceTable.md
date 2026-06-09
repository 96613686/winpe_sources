# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180012a90`
- end: `0x180012b0c`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012a90`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012ad2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012ad2`

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
0x180012a90  mov     [rsp+arg_0], rbx
0x180012a95  mov     [rsp+arg_8], rsi
0x180012a9a  push    rdi
0x180012a9b  sub     rsp, 30h
0x180012a9f  mov     rsi, rdx
0x180012aa2  test    rdx, rdx
0x180012aa5  jnz     short loc_180012AAE
0x180012aa7  mov     eax, 80004003h
0x180012aac  jmp     short loc_180012AFB
0x180012aae  xor     edi, edi
0x180012ab0  lea     rbx, [rcx+40h]
0x180012ab4  cmp     [rbx], rdi
0x180012ab7  jnz     short loc_180012AE4
0x180012ab9  mov     [rsp+38h+ppv], rbx; ppv
0x180012abe  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180012ac5  xor     edx, edx; pUnkOuter
0x180012ac7  lea     r8d, [rdi+1]; dwClsContext
0x180012acb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180012ad2  call    cs:__imp_CoCreateInstance
0x180012ad9  nop     dword ptr [rax+rax+00h]
0x180012ade  mov     edi, eax
0x180012ae0  test    eax, eax
0x180012ae2  js      short loc_180012AF9
0x180012ae4  mov     rcx, [rbx]
0x180012ae7  mov     [rsi], rcx
0x180012aea  mov     rcx, [rbx]
0x180012aed  mov     rdx, [rcx]
0x180012af0  mov     rax, [rdx+8]
0x180012af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012af9  mov     eax, edi
0x180012afb  mov     rbx, [rsp+38h+arg_0]
0x180012b00  mov     rsi, [rsp+38h+arg_8]
0x180012b05  add     rsp, 30h
0x180012b09  pop     rdi
0x180012b0a  retn
```
