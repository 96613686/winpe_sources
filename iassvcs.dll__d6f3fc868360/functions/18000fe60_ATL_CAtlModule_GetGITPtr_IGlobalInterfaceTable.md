# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000fe60`
- end: `0x18000fed5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000fe60`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fea2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fea2`

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
0x18000fe60  mov     [rsp+arg_0], rbx
0x18000fe65  mov     [rsp+arg_8], rsi
0x18000fe6a  push    rdi
0x18000fe6b  sub     rsp, 30h
0x18000fe6f  mov     rsi, rdx
0x18000fe72  test    rdx, rdx
0x18000fe75  jnz     short loc_18000FE7E
0x18000fe77  mov     eax, 80004003h
0x18000fe7c  jmp     short loc_18000FEC5
0x18000fe7e  xor     edi, edi
0x18000fe80  lea     rbx, [rcx+40h]
0x18000fe84  cmp     [rbx], rdi
0x18000fe87  jnz     short loc_18000FEAE
0x18000fe89  mov     [rsp+38h+ppv], rbx; ppv
0x18000fe8e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000fe95  xor     edx, edx; pUnkOuter
0x18000fe97  lea     r8d, [rdi+1]; dwClsContext
0x18000fe9b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000fea2  call    cs:__imp_CoCreateInstance
0x18000fea8  mov     edi, eax
0x18000feaa  test    eax, eax
0x18000feac  js      short loc_18000FEC3
0x18000feae  mov     rcx, [rbx]
0x18000feb1  mov     [rsi], rcx
0x18000feb4  mov     rcx, [rbx]
0x18000feb7  mov     rdx, [rcx]
0x18000feba  mov     rax, [rdx+8]
0x18000febe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fec3  mov     eax, edi
0x18000fec5  mov     rbx, [rsp+38h+arg_0]
0x18000feca  mov     rsi, [rsp+38h+arg_8]
0x18000fecf  add     rsp, 30h
0x18000fed3  pop     rdi
0x18000fed4  retn
```
