# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000a330`
- end: `0x18000a3a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a330`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a372`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a372`

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
0x18000a330  mov     [rsp+arg_0], rbx
0x18000a335  mov     [rsp+arg_8], rsi
0x18000a33a  push    rdi
0x18000a33b  sub     rsp, 30h
0x18000a33f  mov     rsi, rdx
0x18000a342  test    rdx, rdx
0x18000a345  jnz     short loc_18000A34E
0x18000a347  mov     eax, 80004003h
0x18000a34c  jmp     short loc_18000A395
0x18000a34e  xor     edi, edi
0x18000a350  lea     rbx, [rcx+40h]
0x18000a354  cmp     [rbx], rdi
0x18000a357  jnz     short loc_18000A37E
0x18000a359  mov     [rsp+38h+ppv], rbx; ppv
0x18000a35e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000a365  xor     edx, edx; pUnkOuter
0x18000a367  lea     r8d, [rdi+1]; dwClsContext
0x18000a36b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000a372  call    cs:__imp_CoCreateInstance
0x18000a378  mov     edi, eax
0x18000a37a  test    eax, eax
0x18000a37c  js      short loc_18000A393
0x18000a37e  mov     rcx, [rbx]
0x18000a381  mov     [rsi], rcx
0x18000a384  mov     rcx, [rbx]
0x18000a387  mov     rdx, [rcx]
0x18000a38a  mov     rax, [rdx+8]
0x18000a38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a393  mov     eax, edi
0x18000a395  mov     rbx, [rsp+38h+arg_0]
0x18000a39a  mov     rsi, [rsp+38h+arg_8]
0x18000a39f  add     rsp, 30h
0x18000a3a3  pop     rdi
0x18000a3a4  retn
```
