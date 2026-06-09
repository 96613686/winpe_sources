# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18004bf90`
- end: `0x18004c005`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18004bf90`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004bfd2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004bfd2`

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
0x18004bf90  mov     [rsp+arg_0], rbx
0x18004bf95  mov     [rsp+arg_8], rsi
0x18004bf9a  push    rdi
0x18004bf9b  sub     rsp, 30h
0x18004bf9f  mov     rsi, rdx
0x18004bfa2  test    rdx, rdx
0x18004bfa5  jnz     short loc_18004BFAE
0x18004bfa7  mov     eax, 80004003h
0x18004bfac  jmp     short loc_18004BFF5
0x18004bfae  xor     edi, edi
0x18004bfb0  lea     rbx, [rcx+40h]
0x18004bfb4  cmp     [rbx], rdi
0x18004bfb7  jnz     short loc_18004BFDE
0x18004bfb9  mov     [rsp+38h+ppv], rbx; ppv
0x18004bfbe  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18004bfc5  xor     edx, edx; pUnkOuter
0x18004bfc7  lea     r8d, [rdi+1]; dwClsContext
0x18004bfcb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18004bfd2  call    cs:__imp_CoCreateInstance
0x18004bfd8  mov     edi, eax
0x18004bfda  test    eax, eax
0x18004bfdc  js      short loc_18004BFF3
0x18004bfde  mov     rcx, [rbx]
0x18004bfe1  mov     [rsi], rcx
0x18004bfe4  mov     rcx, [rbx]
0x18004bfe7  mov     rdx, [rcx]
0x18004bfea  mov     rax, [rdx+8]
0x18004bfee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bff3  mov     eax, edi
0x18004bff5  mov     rbx, [rsp+38h+arg_0]
0x18004bffa  mov     rsi, [rsp+38h+arg_8]
0x18004bfff  add     rsp, 30h
0x18004c003  pop     rdi
0x18004c004  retn
```
