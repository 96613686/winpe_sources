# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180002fb0`
- end: `0x180003025`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fb0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002ff2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002ff2`

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
0x180002fb0  mov     [rsp+arg_0], rbx
0x180002fb5  mov     [rsp+arg_8], rsi
0x180002fba  push    rdi
0x180002fbb  sub     rsp, 30h
0x180002fbf  mov     rsi, rdx
0x180002fc2  test    rdx, rdx
0x180002fc5  jnz     short loc_180002FCE
0x180002fc7  mov     eax, 80004003h
0x180002fcc  jmp     short loc_180003015
0x180002fce  xor     edi, edi
0x180002fd0  lea     rbx, [rcx+40h]
0x180002fd4  cmp     [rbx], rdi
0x180002fd7  jnz     short loc_180002FFE
0x180002fd9  mov     [rsp+38h+ppv], rbx; ppv
0x180002fde  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180002fe5  xor     edx, edx; pUnkOuter
0x180002fe7  lea     r8d, [rdi+1]; dwClsContext
0x180002feb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180002ff2  call    cs:__imp_CoCreateInstance
0x180002ff8  mov     edi, eax
0x180002ffa  test    eax, eax
0x180002ffc  js      short loc_180003013
0x180002ffe  mov     rcx, [rbx]
0x180003001  mov     [rsi], rcx
0x180003004  mov     rcx, [rbx]
0x180003007  mov     rdx, [rcx]
0x18000300a  mov     rax, [rdx+8]
0x18000300e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003013  mov     eax, edi
0x180003015  mov     rbx, [rsp+38h+arg_0]
0x18000301a  mov     rsi, [rsp+38h+arg_8]
0x18000301f  add     rsp, 30h
0x180003023  pop     rdi
0x180003024  retn
```
