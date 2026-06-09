# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180026d90`
- end: `0x180026e05`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180026d90`
- `0x180088010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180026dd2`
- `ole32!CoCreateInstance` at `0x180026dd2`

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
0x180026d90  mov     [rsp+arg_0], rbx
0x180026d95  mov     [rsp+arg_8], rsi
0x180026d9a  push    rdi
0x180026d9b  sub     rsp, 30h
0x180026d9f  mov     rsi, rdx
0x180026da2  test    rdx, rdx
0x180026da5  jnz     short loc_180026DAE
0x180026da7  mov     eax, 80004003h
0x180026dac  jmp     short loc_180026DF5
0x180026dae  xor     edi, edi
0x180026db0  lea     rbx, [rcx+40h]
0x180026db4  cmp     [rbx], rdi
0x180026db7  jnz     short loc_180026DDE
0x180026db9  mov     [rsp+38h+ppv], rbx; ppv
0x180026dbe  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180026dc5  xor     edx, edx; pUnkOuter
0x180026dc7  lea     r8d, [rdi+1]; dwClsContext
0x180026dcb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180026dd2  call    cs:__imp_CoCreateInstance
0x180026dd8  mov     edi, eax
0x180026dda  test    eax, eax
0x180026ddc  js      short loc_180026DF3
0x180026dde  mov     rcx, [rbx]
0x180026de1  mov     [rsi], rcx
0x180026de4  mov     rcx, [rbx]
0x180026de7  mov     rdx, [rcx]
0x180026dea  mov     rax, [rdx+8]
0x180026dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026df3  mov     eax, edi
0x180026df5  mov     rbx, [rsp+38h+arg_0]
0x180026dfa  mov     rsi, [rsp+38h+arg_8]
0x180026dff  add     rsp, 30h
0x180026e03  pop     rdi
0x180026e04  retn
```
