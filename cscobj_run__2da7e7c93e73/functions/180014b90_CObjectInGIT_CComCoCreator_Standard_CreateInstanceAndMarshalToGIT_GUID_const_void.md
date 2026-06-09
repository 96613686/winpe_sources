# CObjectInGIT<CComCoCreator_Standard>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)

- ea: `0x180014b90`
- end: `0x180014c03`
- name: `?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_Standard@@@@QEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `115`
- prototype: `__int64 __fastcall(CInterfaceInGITBase *this, struct _GUID *, LPVOID *ppv)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014a60`
- `0x180026338`

## callees

- `0x180006500`
- `0x180014b90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014bbd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014bbd`

## pseudocode

```c
__int64 __fastcall CObjectInGIT<CComCoCreator_Standard>::CreateInstanceAndMarshalToGIT(
        CInterfaceInGITBase *this,
        struct _GUID *a2,
        LPVOID *ppv)
{
  HRESULT Instance; // ebx
  LPVOID v7; // rdi

  *ppv = 0;
  Instance = CoCreateInstance(*((const IID *const *)this + 3), 0, *((_DWORD *)this + 8), a2, ppv);
  if ( Instance >= 0 )
  {
    v7 = *ppv;
    Instance = CInterfaceInGITBase::_Marshal(this, a2, (struct IUnknown *)*ppv);
    if ( Instance < 0 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
      *ppv = 0;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180014b90  push    rbx
0x180014b92  push    rbp
0x180014b93  push    rsi
0x180014b94  push    rdi
0x180014b95  push    r14
0x180014b97  sub     rsp, 30h
0x180014b9b  mov     qword ptr [r8], 0
0x180014ba2  mov     rsi, r8
0x180014ba5  mov     [rsp+58h+ppv], r8; ppv
0x180014baa  mov     r14, rdx
0x180014bad  mov     r8d, [rcx+20h]; dwClsContext
0x180014bb1  mov     rbp, rcx
0x180014bb4  mov     rcx, [rcx+18h]; rclsid
0x180014bb8  mov     r9, rdx; riid
0x180014bbb  xor     edx, edx; pUnkOuter
0x180014bbd  call    cs:__imp_CoCreateInstance
0x180014bc3  mov     ebx, eax
0x180014bc5  test    eax, eax
0x180014bc7  js      short loc_180014BF6
0x180014bc9  mov     rdi, [rsi]
0x180014bcc  mov     rdx, r14; struct _GUID *
0x180014bcf  mov     r8, rdi; struct IUnknown *
0x180014bd2  mov     rcx, rbp; this
0x180014bd5  call    ?_Marshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CInterfaceInGITBase::_Marshal(_GUID const &,IUnknown *)
0x180014bda  mov     ebx, eax
0x180014bdc  test    eax, eax
0x180014bde  jns     short loc_180014BF6
0x180014be0  mov     rax, [rdi]
0x180014be3  mov     rcx, rdi
0x180014be6  mov     rax, [rax+10h]
0x180014bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bef  mov     qword ptr [rsi], 0
0x180014bf6  mov     eax, ebx
0x180014bf8  add     rsp, 30h
0x180014bfc  pop     r14
0x180014bfe  pop     rdi
0x180014bff  pop     rsi
0x180014c00  pop     rbp
0x180014c01  pop     rbx
0x180014c02  retn
```
