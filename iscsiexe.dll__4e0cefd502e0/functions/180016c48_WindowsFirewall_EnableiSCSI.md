# WindowsFirewall_EnableiSCSI

- ea: `0x180016c48`
- end: `0x180016d1a`
- name: `WindowsFirewall_EnableiSCSI`
- size: `210`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ccc4`
- `0x180012510`

## callees

- `0x180016c18`
- `0x180016c48`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016cad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016cad`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016cfc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016cfc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016c5d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016c5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180016c7d`
- `OLEAUT32!__imp_SysAllocString` at `0x180016c7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180016ce0`
- `OLEAUT32!__imp_SysFreeString` at `0x180016ce0`

## string_xrefs

- `0x180016c6d`: `@FirewallAPI.dll,-29002`

## pseudocode

```c
__int64 __fastcall WindowsFirewall_EnableiSCSI(int a1)
{
  HRESULT v2; // edi
  int v3; // ecx
  OLECHAR *v4; // rbx
  __int64 v5; // r9
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v2 = CoInitializeEx(0, 0);
  if ( v2 >= 0 )
  {
    ppv = 0;
    v4 = SysAllocString(L"@FirewallAPI.dll,-29002");
    if ( !v4 )
      ATL::AtlThrowImpl(v3);
    v2 = CoCreateInstance(
           &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
           0,
           1u,
           &GUID_98325047_c671_4174_8d81_defcd3f03186,
           &ppv);
    if ( v2 >= 0 )
    {
      LOWORD(v5) = -(a1 != 0);
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, OLECHAR *, __int64))(*(_QWORD *)ppv + 160LL))(
             ppv,
             0x7FFFFFFF,
             v4,
             v5);
    }
    SysFreeString(v4);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    CoUninitialize();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180016c48  mov     [rsp+arg_0], rbx
0x180016c4d  mov     [rsp+arg_10], rsi
0x180016c52  push    rdi
0x180016c53  sub     rsp, 30h
0x180016c57  mov     esi, ecx
0x180016c59  xor     edx, edx; dwCoInit
0x180016c5b  xor     ecx, ecx; pvReserved
0x180016c5d  call    cs:__imp_CoInitializeEx
0x180016c63  mov     edi, eax
0x180016c65  test    eax, eax
0x180016c67  js      loc_180016D02
0x180016c6d  lea     rcx, psz; "@FirewallAPI.dll,-29002"
0x180016c74  mov     [rsp+38h+arg_8], 0
0x180016c7d  call    cs:__imp_SysAllocString
0x180016c83  mov     rbx, rax
0x180016c86  test    rax, rax
0x180016c89  jz      loc_180016D14
0x180016c8f  xor     edx, edx; pUnkOuter
0x180016c91  lea     rax, [rsp+38h+arg_8]
0x180016c96  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180016c9d  mov     [rsp+38h+ppv], rax; ppv
0x180016ca2  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180016ca9  lea     r8d, [rdx+1]; dwClsContext
0x180016cad  call    cs:__imp_CoCreateInstance
0x180016cb3  mov     edi, eax
0x180016cb5  test    eax, eax
0x180016cb7  js      short loc_180016CDD
0x180016cb9  mov     rcx, [rsp+38h+arg_8]
0x180016cbe  neg     esi
0x180016cc0  mov     r8, rbx
0x180016cc3  mov     edx, 7FFFFFFFh
0x180016cc8  sbb     r9w, r9w
0x180016ccc  mov     rax, [rcx]
0x180016ccf  mov     rax, [rax+0A0h]
0x180016cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cdb  mov     edi, eax
0x180016cdd  mov     rcx, rbx; bstrString
0x180016ce0  call    cs:__imp_SysFreeString
0x180016ce6  mov     rcx, [rsp+38h+arg_8]
0x180016ceb  test    rcx, rcx
0x180016cee  jz      short loc_180016CFC
0x180016cf0  mov     rax, [rcx]
0x180016cf3  mov     rax, [rax+10h]
0x180016cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cfc  call    cs:__imp_CoUninitialize
0x180016d02  mov     rbx, [rsp+38h+arg_0]
0x180016d07  mov     eax, edi
0x180016d09  mov     rsi, [rsp+38h+arg_10]
0x180016d0e  add     rsp, 30h
0x180016d12  pop     rdi
0x180016d13  retn
0x180016d14  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
