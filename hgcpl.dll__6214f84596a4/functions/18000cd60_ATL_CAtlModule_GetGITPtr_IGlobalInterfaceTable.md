# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000cd60`
- end: `0x18000cdd5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000cd60`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cda2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cda2`

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
0x18000cd60  mov     [rsp+arg_0], rbx
0x18000cd65  mov     [rsp+arg_8], rsi
0x18000cd6a  push    rdi
0x18000cd6b  sub     rsp, 30h
0x18000cd6f  mov     rsi, rdx
0x18000cd72  test    rdx, rdx
0x18000cd75  jnz     short loc_18000CD7E
0x18000cd77  mov     eax, 80004003h
0x18000cd7c  jmp     short loc_18000CDC5
0x18000cd7e  xor     edi, edi
0x18000cd80  lea     rbx, [rcx+40h]
0x18000cd84  cmp     [rbx], rdi
0x18000cd87  jnz     short loc_18000CDAE
0x18000cd89  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000cd90  mov     [rsp+38h+ppv], rbx; ppv
0x18000cd95  xor     edx, edx; pUnkOuter
0x18000cd97  lea     r8d, [rdi+1]; dwClsContext
0x18000cd9b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000cda2  call    cs:__imp_CoCreateInstance
0x18000cda8  mov     edi, eax
0x18000cdaa  test    eax, eax
0x18000cdac  js      short loc_18000CDC3
0x18000cdae  mov     rcx, [rbx]
0x18000cdb1  mov     [rsi], rcx
0x18000cdb4  mov     rcx, [rbx]
0x18000cdb7  mov     rdx, [rcx]
0x18000cdba  mov     rax, [rdx+8]
0x18000cdbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc3  mov     eax, edi
0x18000cdc5  mov     rbx, [rsp+38h+arg_0]
0x18000cdca  mov     rsi, [rsp+38h+arg_8]
0x18000cdcf  add     rsp, 30h
0x18000cdd3  pop     rdi
0x18000cdd4  retn
```
