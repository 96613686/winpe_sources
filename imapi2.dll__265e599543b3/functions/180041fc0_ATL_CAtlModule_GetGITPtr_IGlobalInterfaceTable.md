# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180041fc0`
- end: `0x180042035`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180041fc0`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180042002`
- `ole32!CoCreateInstance` at `0x180042002`

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
0x180041fc0  mov     [rsp+arg_0], rbx
0x180041fc5  mov     [rsp+arg_8], rsi
0x180041fca  push    rdi
0x180041fcb  sub     rsp, 30h
0x180041fcf  mov     rsi, rdx
0x180041fd2  test    rdx, rdx
0x180041fd5  jnz     short loc_180041FDE
0x180041fd7  mov     eax, 80004003h
0x180041fdc  jmp     short loc_180042025
0x180041fde  xor     edi, edi
0x180041fe0  lea     rbx, [rcx+40h]
0x180041fe4  cmp     [rbx], rdi
0x180041fe7  jnz     short loc_18004200E
0x180041fe9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180041ff0  mov     [rsp+38h+ppv], rbx; ppv
0x180041ff5  xor     edx, edx; pUnkOuter
0x180041ff7  lea     r8d, [rdi+1]; dwClsContext
0x180041ffb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180042002  call    cs:__imp_CoCreateInstance
0x180042008  mov     edi, eax
0x18004200a  test    eax, eax
0x18004200c  js      short loc_180042023
0x18004200e  mov     rcx, [rbx]
0x180042011  mov     [rsi], rcx
0x180042014  mov     rcx, [rbx]
0x180042017  mov     rdx, [rcx]
0x18004201a  mov     rax, [rdx+8]
0x18004201e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042023  mov     eax, edi
0x180042025  mov     rbx, [rsp+38h+arg_0]
0x18004202a  mov     rsi, [rsp+38h+arg_8]
0x18004202f  add     rsp, 30h
0x180042033  pop     rdi
0x180042034  retn
```
