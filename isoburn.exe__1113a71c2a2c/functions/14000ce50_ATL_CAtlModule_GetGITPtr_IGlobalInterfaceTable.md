# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x14000ce50`
- end: `0x14000cec5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000ce50`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ce92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000ce92`

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
0x14000ce50  mov     [rsp+arg_0], rbx
0x14000ce55  mov     [rsp+arg_8], rsi
0x14000ce5a  push    rdi
0x14000ce5b  sub     rsp, 30h
0x14000ce5f  mov     rsi, rdx
0x14000ce62  test    rdx, rdx
0x14000ce65  jnz     short loc_14000CE6E
0x14000ce67  mov     eax, 80004003h
0x14000ce6c  jmp     short loc_14000CEB5
0x14000ce6e  xor     edi, edi
0x14000ce70  lea     rbx, [rcx+40h]
0x14000ce74  cmp     [rbx], rdi
0x14000ce77  jnz     short loc_14000CE9E
0x14000ce79  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x14000ce80  mov     [rsp+38h+ppv], rbx; ppv
0x14000ce85  xor     edx, edx; pUnkOuter
0x14000ce87  lea     r8d, [rdi+1]; dwClsContext
0x14000ce8b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x14000ce92  call    cs:__imp_CoCreateInstance
0x14000ce98  mov     edi, eax
0x14000ce9a  test    eax, eax
0x14000ce9c  js      short loc_14000CEB3
0x14000ce9e  mov     rcx, [rbx]
0x14000cea1  mov     [rsi], rcx
0x14000cea4  mov     rcx, [rbx]
0x14000cea7  mov     rdx, [rcx]
0x14000ceaa  mov     rax, [rdx+8]
0x14000ceae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ceb3  mov     eax, edi
0x14000ceb5  mov     rbx, [rsp+38h+arg_0]
0x14000ceba  mov     rsi, [rsp+38h+arg_8]
0x14000cebf  add     rsp, 30h
0x14000cec3  pop     rdi
0x14000cec4  retn
```
