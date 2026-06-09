# DoComplexLibraryInit

- ea: `0x18000e418`
- end: `0x18000e4d2`
- name: `DoComplexLibraryInit`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e4d8`

## callees

- `0x18000e418`
- `0x18000f04c`
- `0x180029010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000e445`
- `ole32!CoCreateInstance` at `0x18000e445`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 DoComplexLibraryInit()
{
  HRESULT UniqueWinmsgIds; // ebx
  unsigned int v2; // [rsp+40h] [rbp+8h] BYREF
  UINT v3; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  ppv = 0;
  UniqueWinmsgIds = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 0x17u, &IID_IGlobalInterfaceTable, &ppv);
  if ( UniqueWinmsgIds < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)UniqueWinmsgIds;
  }
  v2 = 0;
  v3 = 0;
  UniqueWinmsgIds = GetUniqueWinmsgIds(&v2, &v3);
  if ( UniqueWinmsgIds < 0 )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)UniqueWinmsgIds;
  }
  g_pGIT = (struct IGlobalInterfaceTable *)ppv;
  g_uiMsgidArrived = v2;
  g_uiMsgidArrivedError = v3;
  return 0;
}

```

## disassembly

```asm
0x18000e418  push    rbx
0x18000e41a  sub     rsp, 30h
0x18000e41e  mov     [rsp+38h+arg_10], 0
0x18000e427  lea     rax, [rsp+38h+arg_10]
0x18000e42c  mov     [rsp+38h+ppv], rax; ppv
0x18000e431  lea     r9, IID_IGlobalInterfaceTable; riid
0x18000e438  xor     edx, edx; pUnkOuter
0x18000e43a  lea     r8d, [rdx+17h]; dwClsContext
0x18000e43e  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000e445  call    cs:__imp_CoCreateInstance
0x18000e44b  mov     ebx, eax
0x18000e44d  test    eax, eax
0x18000e44f  jns     short loc_18000E46C
0x18000e451  mov     rcx, [rsp+38h+arg_10]
0x18000e456  test    rcx, rcx
0x18000e459  jz      short loc_18000E468
0x18000e45b  mov     rdx, [rcx]
0x18000e45e  mov     rax, [rdx+10h]
0x18000e462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e467  nop
0x18000e468  mov     eax, ebx
0x18000e46a  jmp     short loc_18000E4CC
0x18000e46c  mov     [rsp+38h+arg_0], 0
0x18000e474  mov     [rsp+38h+arg_8], 0
0x18000e47c  lea     rdx, [rsp+38h+arg_8]
0x18000e481  lea     rcx, [rsp+38h+arg_0]
0x18000e486  call    GetUniqueWinmsgIds
0x18000e48b  mov     ebx, eax
0x18000e48d  test    eax, eax
0x18000e48f  jns     short loc_18000E4AA
0x18000e491  mov     rcx, [rsp+38h+arg_10]
0x18000e496  test    rcx, rcx
0x18000e499  jz      short loc_18000E4A8
0x18000e49b  mov     rdx, [rcx]
0x18000e49e  mov     rax, [rdx+10h]
0x18000e4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4a7  nop
0x18000e4a8  jmp     short loc_18000E468
0x18000e4aa  mov     rax, [rsp+38h+arg_10]
0x18000e4af  mov     cs:?g_pGIT@@3PEAUIGlobalInterfaceTable@@EA, rax; IGlobalInterfaceTable * g_pGIT
0x18000e4b6  mov     eax, [rsp+38h+arg_0]
0x18000e4ba  mov     cs:?g_uiMsgidArrived@@3IA, eax; uint g_uiMsgidArrived
0x18000e4c0  mov     eax, [rsp+38h+arg_8]
0x18000e4c4  mov     cs:?g_uiMsgidArrivedError@@3IA, eax; uint g_uiMsgidArrivedError
0x18000e4ca  xor     eax, eax
0x18000e4cc  add     rsp, 30h
0x18000e4d0  pop     rbx
0x18000e4d1  retn
```
