# WSTLocatePackageByAuthScheme(_GUID *)

- ea: `0x180008544`
- end: `0x1800085b9`
- name: `?WSTLocatePackageByAuthScheme@@YAPEAU_WST_SSP_PACKAGE@@PEAU_GUID@@@Z`
- size: `117`
- prototype: `struct _WST_SSP_PACKAGE *__fastcall(struct _GUID *)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800070d0`
- `0x18000c7d0`
- `0x18000ea54`
- `0x180014150`
- `0x180016824`
- `0x180016f70`
- `0x180017f00`
- `0x18001a3b4`
- `0x18001b9b0`
- `0x18001bba4`

## callees

- `0x180008544`
- `0x180008e2c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800085a0`
- `ntdll!RtlReleaseResource` at `0x1800085a0`
- `ntdll!RtlAcquireResourceShared` at `0x18000855c`
- `ntdll!RtlAcquireResourceShared` at `0x18000855c`

## pseudocode

```c
struct _WST_SSP_PACKAGE *__fastcall WSTLocatePackageByAuthScheme(struct _GUID *a1)
{
  struct _WST_SSP_PACKAGE *v2; // rbx
  struct _WST_SSP_PACKAGE *i; // rcx
  __int64 v4; // rax

  v2 = 0;
  RtlAcquireResourceShared(&WSTGlobalLoaderLock, 1u);
  for ( i = WSTGlobalPkgList; i != (struct _WST_SSP_PACKAGE *)&WSTGlobalPkgList; i = *(struct _WST_SSP_PACKAGE **)i )
  {
    v4 = *((_QWORD *)i + 49) - *(_QWORD *)&a1->Data1;
    if ( !v4 )
      v4 = *((_QWORD *)i + 50) - *(_QWORD *)a1->Data4;
    if ( !v4 )
    {
      v2 = i;
      WSTReferencePackage(i);
      break;
    }
  }
  RtlReleaseResource(&WSTGlobalLoaderLock);
  return v2;
}

```

## disassembly

```asm
0x180008544  mov     [rsp+arg_0], rbx
0x180008549  push    rdi
0x18000854a  sub     rsp, 20h
0x18000854e  mov     rdi, rcx
0x180008551  xor     ebx, ebx
0x180008553  lea     rcx, ?WSTGlobalLoaderLock@@3U_RTL_RESOURCE@@A; Resource
0x18000855a  mov     dl, 1; Wait
0x18000855c  call    cs:__imp_RtlAcquireResourceShared
0x180008562  mov     rcx, cs:?WSTGlobalPkgList@@3U_LIST_ENTRY@@A; struct _WST_SSP_PACKAGE *
0x180008569  lea     rax, ?WSTGlobalPkgList@@3U_LIST_ENTRY@@A; _LIST_ENTRY WSTGlobalPkgList
0x180008570  cmp     rcx, rax
0x180008573  jz      short loc_180008599
0x180008575  mov     rax, [rcx+188h]
0x18000857c  sub     rax, [rdi]
0x18000857f  jnz     short loc_18000858C
0x180008581  mov     rax, [rcx+190h]
0x180008588  sub     rax, [rdi+8]
0x18000858c  test    rax, rax
0x18000858f  jnz     short loc_1800085B4
0x180008591  mov     rbx, rcx
0x180008594  call    ?WSTReferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTReferencePackage(_WST_SSP_PACKAGE *)
0x180008599  lea     rcx, ?WSTGlobalLoaderLock@@3U_RTL_RESOURCE@@A; Resource
0x1800085a0  call    cs:__imp_RtlReleaseResource
0x1800085a6  mov     rax, rbx
0x1800085a9  mov     rbx, [rsp+28h+arg_0]
0x1800085ae  add     rsp, 20h
0x1800085b2  pop     rdi
0x1800085b3  retn
0x1800085b4  mov     rcx, [rcx]
0x1800085b7  jmp     short loc_180008569
```
