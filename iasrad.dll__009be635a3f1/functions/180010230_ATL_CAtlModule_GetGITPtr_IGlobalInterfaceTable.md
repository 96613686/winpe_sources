# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180010230`
- end: `0x1800102a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180010230`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010272`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010272`

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
0x180010230  mov     [rsp+arg_0], rbx
0x180010235  mov     [rsp+arg_8], rsi
0x18001023a  push    rdi
0x18001023b  sub     rsp, 30h
0x18001023f  mov     rsi, rdx
0x180010242  test    rdx, rdx
0x180010245  jnz     short loc_18001024E
0x180010247  mov     eax, 80004003h
0x18001024c  jmp     short loc_180010295
0x18001024e  xor     edi, edi
0x180010250  lea     rbx, [rcx+40h]
0x180010254  cmp     [rbx], rdi
0x180010257  jnz     short loc_18001027E
0x180010259  mov     [rsp+38h+ppv], rbx; ppv
0x18001025e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180010265  xor     edx, edx; pUnkOuter
0x180010267  lea     r8d, [rdi+1]; dwClsContext
0x18001026b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180010272  call    cs:__imp_CoCreateInstance
0x180010278  mov     edi, eax
0x18001027a  test    eax, eax
0x18001027c  js      short loc_180010293
0x18001027e  mov     rcx, [rbx]
0x180010281  mov     [rsi], rcx
0x180010284  mov     rcx, [rbx]
0x180010287  mov     rdx, [rcx]
0x18001028a  mov     rax, [rdx+8]
0x18001028e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010293  mov     eax, edi
0x180010295  mov     rbx, [rsp+38h+arg_0]
0x18001029a  mov     rsi, [rsp+38h+arg_8]
0x18001029f  add     rsp, 30h
0x1800102a3  pop     rdi
0x1800102a4  retn
```
