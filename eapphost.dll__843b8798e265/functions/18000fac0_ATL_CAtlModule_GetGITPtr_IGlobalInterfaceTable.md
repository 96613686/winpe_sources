# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000fac0`
- end: `0x18000fb3c`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000fac0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fb02`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fb02`

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
0x18000fac0  mov     [rsp+arg_0], rbx
0x18000fac5  mov     [rsp+arg_8], rsi
0x18000faca  push    rdi
0x18000facb  sub     rsp, 30h
0x18000facf  mov     rsi, rdx
0x18000fad2  test    rdx, rdx
0x18000fad5  jnz     short loc_18000FADE
0x18000fad7  mov     eax, 80004003h
0x18000fadc  jmp     short loc_18000FB2B
0x18000fade  xor     edi, edi
0x18000fae0  lea     rbx, [rcx+40h]
0x18000fae4  cmp     [rbx], rdi
0x18000fae7  jnz     short loc_18000FB14
0x18000fae9  mov     [rsp+38h+ppv], rbx; ppv
0x18000faee  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000faf5  xor     edx, edx; pUnkOuter
0x18000faf7  lea     r8d, [rdi+1]; dwClsContext
0x18000fafb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000fb02  call    cs:__imp_CoCreateInstance
0x18000fb09  nop     dword ptr [rax+rax+00h]
0x18000fb0e  mov     edi, eax
0x18000fb10  test    eax, eax
0x18000fb12  js      short loc_18000FB29
0x18000fb14  mov     rcx, [rbx]
0x18000fb17  mov     [rsi], rcx
0x18000fb1a  mov     rcx, [rbx]
0x18000fb1d  mov     rdx, [rcx]
0x18000fb20  mov     rax, [rdx+8]
0x18000fb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb29  mov     eax, edi
0x18000fb2b  mov     rbx, [rsp+38h+arg_0]
0x18000fb30  mov     rsi, [rsp+38h+arg_8]
0x18000fb35  add     rsp, 30h
0x18000fb39  pop     rdi
0x18000fb3a  retn
```
