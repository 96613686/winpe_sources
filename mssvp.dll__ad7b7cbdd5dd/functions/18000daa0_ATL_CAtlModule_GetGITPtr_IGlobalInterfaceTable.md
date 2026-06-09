# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000daa0`
- end: `0x18000db15`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000daa0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000dae2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000dae2`

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
0x18000daa0  mov     [rsp+arg_0], rbx
0x18000daa5  mov     [rsp+arg_8], rsi
0x18000daaa  push    rdi
0x18000daab  sub     rsp, 30h
0x18000daaf  mov     rsi, rdx
0x18000dab2  test    rdx, rdx
0x18000dab5  jnz     short loc_18000DABE
0x18000dab7  mov     eax, 80004003h
0x18000dabc  jmp     short loc_18000DB05
0x18000dabe  xor     edi, edi
0x18000dac0  lea     rbx, [rcx+40h]
0x18000dac4  cmp     [rbx], rdi
0x18000dac7  jnz     short loc_18000DAEE
0x18000dac9  mov     [rsp+38h+ppv], rbx; ppv
0x18000dace  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000dad5  xor     edx, edx; pUnkOuter
0x18000dad7  lea     r8d, [rdi+1]; dwClsContext
0x18000dadb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000dae2  call    cs:__imp_CoCreateInstance
0x18000dae8  mov     edi, eax
0x18000daea  test    eax, eax
0x18000daec  js      short loc_18000DB03
0x18000daee  mov     rcx, [rbx]
0x18000daf1  mov     [rsi], rcx
0x18000daf4  mov     rcx, [rbx]
0x18000daf7  mov     rdx, [rcx]
0x18000dafa  mov     rax, [rdx+8]
0x18000dafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db03  mov     eax, edi
0x18000db05  mov     rbx, [rsp+38h+arg_0]
0x18000db0a  mov     rsi, [rsp+38h+arg_8]
0x18000db0f  add     rsp, 30h
0x18000db13  pop     rdi
0x18000db14  retn
```
