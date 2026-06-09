# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800071d0`
- end: `0x180007245`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800071d0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007212`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007212`

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
0x1800071d0  mov     [rsp+arg_0], rbx
0x1800071d5  mov     [rsp+arg_8], rsi
0x1800071da  push    rdi
0x1800071db  sub     rsp, 30h
0x1800071df  mov     rsi, rdx
0x1800071e2  test    rdx, rdx
0x1800071e5  jnz     short loc_1800071EE
0x1800071e7  mov     eax, 80004003h
0x1800071ec  jmp     short loc_180007235
0x1800071ee  xor     edi, edi
0x1800071f0  lea     rbx, [rcx+40h]
0x1800071f4  cmp     [rbx], rdi
0x1800071f7  jnz     short loc_18000721E
0x1800071f9  mov     [rsp+38h+ppv], rbx; ppv
0x1800071fe  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007205  xor     edx, edx; pUnkOuter
0x180007207  lea     r8d, [rdi+1]; dwClsContext
0x18000720b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007212  call    cs:__imp_CoCreateInstance
0x180007218  mov     edi, eax
0x18000721a  test    eax, eax
0x18000721c  js      short loc_180007233
0x18000721e  mov     rcx, [rbx]
0x180007221  mov     [rsi], rcx
0x180007224  mov     rcx, [rbx]
0x180007227  mov     rdx, [rcx]
0x18000722a  mov     rax, [rdx+8]
0x18000722e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007233  mov     eax, edi
0x180007235  mov     rbx, [rsp+38h+arg_0]
0x18000723a  mov     rsi, [rsp+38h+arg_8]
0x18000723f  add     rsp, 30h
0x180007243  pop     rdi
0x180007244  retn
```
