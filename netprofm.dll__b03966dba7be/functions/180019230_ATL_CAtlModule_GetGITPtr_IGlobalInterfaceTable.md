# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180019230`
- end: `0x1800192a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180019230`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019272`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019272`

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
0x180019230  mov     [rsp+arg_0], rbx
0x180019235  mov     [rsp+arg_8], rsi
0x18001923a  push    rdi
0x18001923b  sub     rsp, 30h
0x18001923f  mov     rsi, rdx
0x180019242  test    rdx, rdx
0x180019245  jnz     short loc_18001924E
0x180019247  mov     eax, 80004003h
0x18001924c  jmp     short loc_180019295
0x18001924e  xor     edi, edi
0x180019250  lea     rbx, [rcx+40h]
0x180019254  cmp     [rbx], rdi
0x180019257  jnz     short loc_18001927E
0x180019259  mov     [rsp+38h+ppv], rbx; ppv
0x18001925e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180019265  xor     edx, edx; pUnkOuter
0x180019267  lea     r8d, [rdi+1]; dwClsContext
0x18001926b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180019272  call    cs:__imp_CoCreateInstance
0x180019278  mov     edi, eax
0x18001927a  test    eax, eax
0x18001927c  js      short loc_180019293
0x18001927e  mov     rcx, [rbx]
0x180019281  mov     [rsi], rcx
0x180019284  mov     rcx, [rbx]
0x180019287  mov     rdx, [rcx]
0x18001928a  mov     rax, [rdx+8]
0x18001928e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019293  mov     eax, edi
0x180019295  mov     rbx, [rsp+38h+arg_0]
0x18001929a  mov     rsi, [rsp+38h+arg_8]
0x18001929f  add     rsp, 30h
0x1800192a3  pop     rdi
0x1800192a4  retn
```
