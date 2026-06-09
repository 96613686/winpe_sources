# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180011050`
- end: `0x1800110c5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180011050`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011092`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011092`

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
0x180011050  mov     [rsp+arg_0], rbx
0x180011055  mov     [rsp+arg_8], rsi
0x18001105a  push    rdi
0x18001105b  sub     rsp, 30h
0x18001105f  mov     rsi, rdx
0x180011062  test    rdx, rdx
0x180011065  jnz     short loc_18001106E
0x180011067  mov     eax, 80004003h
0x18001106c  jmp     short loc_1800110B5
0x18001106e  xor     edi, edi
0x180011070  lea     rbx, [rcx+40h]
0x180011074  cmp     [rbx], rdi
0x180011077  jnz     short loc_18001109E
0x180011079  mov     [rsp+38h+ppv], rbx; ppv
0x18001107e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180011085  xor     edx, edx; pUnkOuter
0x180011087  lea     r8d, [rdi+1]; dwClsContext
0x18001108b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180011092  call    cs:__imp_CoCreateInstance
0x180011098  mov     edi, eax
0x18001109a  test    eax, eax
0x18001109c  js      short loc_1800110B3
0x18001109e  mov     rcx, [rbx]
0x1800110a1  mov     [rsi], rcx
0x1800110a4  mov     rcx, [rbx]
0x1800110a7  mov     rdx, [rcx]
0x1800110aa  mov     rax, [rdx+8]
0x1800110ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110b3  mov     eax, edi
0x1800110b5  mov     rbx, [rsp+38h+arg_0]
0x1800110ba  mov     rsi, [rsp+38h+arg_8]
0x1800110bf  add     rsp, 30h
0x1800110c3  pop     rdi
0x1800110c4  retn
```
