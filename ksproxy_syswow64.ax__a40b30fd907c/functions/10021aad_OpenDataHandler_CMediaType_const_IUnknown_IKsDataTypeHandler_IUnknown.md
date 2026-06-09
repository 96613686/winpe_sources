# OpenDataHandler(CMediaType const *,IUnknown *,IKsDataTypeHandler * *,IUnknown * *)

- ea: `0x10021aad`
- end: `0x10021b82`
- name: `?OpenDataHandler@@YGXPBVCMediaType@@PAUIUnknown@@PAPAUIKsDataTypeHandler@@PAPAU2@@Z`
- size: `213`
- prototype: `void __userpurge(IUnknown *@<edx>, int@<ecx>, const struct CMediaType *, LPVOID *ppv, struct IKsDataTypeHandler **, struct IUnknown **)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1000af81`
- `0x100122c3`
- `0x100163d0`
- `0x10016a04`
- `0x1001b660`

## callees

- `0x10021aad`
- `0x1002d510`

## import_xrefs

- `ole32!CoCreateInstance` at `0x10021adb`
- `ole32!CoCreateInstance` at `0x10021af6`
- `ole32!CoCreateInstance` at `0x10021b0e`
- `ole32!CoCreateInstance` at `0x10021adb`
- `ole32!CoCreateInstance` at `0x10021af6`
- `ole32!CoCreateInstance` at `0x10021b0e`

## pseudocode

```c
void __userpurge OpenDataHandler(
        IUnknown *a1@<edx>,
        int a2@<ecx>,
        const struct CMediaType *a3,
        LPVOID *ppv,
        struct IKsDataTypeHandler **a5,
        struct IUnknown **a6)
{
  a3->majortype.Data1 = 0;
  *ppv = 0;
  CoCreateInstance((const IID *const)(a2 + 44), a1, 0x401u, &_GUID_00000000_0000_0000_c000_000000000046, ppv);
  if ( !*ppv )
  {
    CoCreateInstance((const IID *const)(a2 + 16), a1, 0x401u, &_GUID_00000000_0000_0000_c000_000000000046, ppv);
    if ( !*ppv )
      CoCreateInstance((const IID *const)a2, a1, 0x401u, &_GUID_00000000_0000_0000_c000_000000000046, ppv);
  }
  if ( *ppv )
  {
    (**(void (__thiscall ***)(_DWORD, _DWORD, GUID *, const struct CMediaType *))*ppv)(
      **(_DWORD **)*ppv,
      *ppv,
      &_GUID_5ffbaa02_49a3_11d0_9f36_00aa00a216a1,
      a3);
    if ( a3->majortype.Data1 )
    {
      (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)a3->majortype.Data1 + 8))(
        *(_DWORD *)(*(_DWORD *)a3->majortype.Data1 + 8),
        a3->majortype.Data1);
      (*(void (__thiscall **)(_DWORD, unsigned int, int))(*(_DWORD *)a3->majortype.Data1 + 28))(
        *(_DWORD *)(*(_DWORD *)a3->majortype.Data1 + 28),
        a3->majortype.Data1,
        a2);
    }
    else
    {
      (*(void (__thiscall **)(_DWORD, _DWORD))(*(_DWORD *)*ppv + 8))(*(_DWORD *)(*(_DWORD *)*ppv + 8), *ppv);
      *ppv = 0;
    }
  }
}

```

## disassembly

```asm
0x10021aad  mov     edi, edi
0x10021aaf  push    ebp
0x10021ab0  mov     ebp, esp
0x10021ab2  mov     eax, [ebp+arg_0]
0x10021ab5  push    ebx
0x10021ab6  push    esi
0x10021ab7  push    edi
0x10021ab8  mov     edi, [ebp+ppv]
0x10021abb  mov     ebx, ecx
0x10021abd  push    edi; ppv
0x10021abe  push    offset __GUID_00000000_0000_0000_c000_000000000046; riid
0x10021ac3  push    401h; dwClsContext
0x10021ac8  mov     esi, edx
0x10021aca  mov     dword ptr [eax], 0
0x10021ad0  push    esi; pUnkOuter
0x10021ad1  lea     eax, [ebx+2Ch]
0x10021ad4  mov     dword ptr [edi], 0
0x10021ada  push    eax; rclsid
0x10021adb  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10021ae1  cmp     dword ptr [edi], 0
0x10021ae4  jnz     short loc_10021B14
0x10021ae6  push    edi; ppv
0x10021ae7  push    offset __GUID_00000000_0000_0000_c000_000000000046; riid
0x10021aec  push    401h; dwClsContext
0x10021af1  push    esi; pUnkOuter
0x10021af2  lea     eax, [ebx+10h]
0x10021af5  push    eax; rclsid
0x10021af6  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10021afc  cmp     dword ptr [edi], 0
0x10021aff  jnz     short loc_10021B14
0x10021b01  push    edi; ppv
0x10021b02  push    offset __GUID_00000000_0000_0000_c000_000000000046; riid
0x10021b07  push    401h; dwClsContext
0x10021b0c  push    esi; pUnkOuter
0x10021b0d  push    ebx; rclsid
0x10021b0e  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10021b14  mov     ecx, [edi]
0x10021b16  test    ecx, ecx
0x10021b18  jz      short loc_10021B7B
0x10021b1a  mov     eax, [ecx]
0x10021b1c  mov     edx, [ebp+arg_0]
0x10021b1f  push    edx
0x10021b20  push    offset __GUID_5ffbaa02_49a3_11d0_9f36_00aa00a216a1
0x10021b25  mov     esi, [eax]
0x10021b27  push    ecx
0x10021b28  mov     ecx, esi; this
0x10021b2a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10021b30  call    esi
0x10021b32  mov     eax, [ebp+arg_0]
0x10021b35  mov     ecx, [eax]
0x10021b37  test    ecx, ecx
0x10021b39  jz      short loc_10021B63
0x10021b3b  mov     eax, [ecx]
0x10021b3d  push    ecx
0x10021b3e  mov     esi, [eax+8]
0x10021b41  mov     ecx, esi; this
0x10021b43  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10021b49  call    esi
0x10021b4b  mov     edx, [ebp+arg_0]
0x10021b4e  push    ebx
0x10021b4f  mov     eax, [edx]
0x10021b51  push    eax
0x10021b52  mov     ecx, [eax]
0x10021b54  mov     esi, [ecx+1Ch]
0x10021b57  mov     ecx, esi; this
0x10021b59  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10021b5f  call    esi
0x10021b61  jmp     short loc_10021B7B
0x10021b63  mov     eax, [edi]
0x10021b65  push    eax
0x10021b66  mov     ecx, [eax]
0x10021b68  mov     esi, [ecx+8]
0x10021b6b  mov     ecx, esi; this
0x10021b6d  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10021b73  call    esi
0x10021b75  mov     dword ptr [edi], 0
0x10021b7b  pop     edi
0x10021b7c  pop     esi
0x10021b7d  pop     ebx
0x10021b7e  pop     ebp
0x10021b7f  retn    8
```
