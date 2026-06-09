# CAutomateContent::OnNewWindow3(ATL::CComBSTR,int *)

- ea: `0x18000cf60`
- end: `0x18000cff7`
- name: `?OnNewWindow3@CAutomateContent@@QEAAXVCComBSTR@ATL@@PEAH@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c0c0`

## callees

- `0x18000cf60`
- `0x180078010`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x18000cfe1`
- `ntdll!WinSqmIncrementDWORD` at `0x18000cfe1`
- `ole32!CoCreateInstance` at `0x18000cf9e`
- `ole32!CoCreateInstance` at `0x18000cf9e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cfeb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cfeb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAutomateContent::OnNewWindow3(__int64 a1, BSTR *a2, _DWORD *a3)
{
  __int64 v4; // rdx
  LPVOID v5; // [rsp+40h] [rbp+8h] BYREF
  BSTR *v6; // [rsp+48h] [rbp+10h]

  v6 = a2;
  *a3 = 1;
  v5 = 0;
  if ( CoCreateInstance(&CLSID_HxHelpPane, 0, 3u, &GUID_8cec595b_07a1_11d9_b15e_000d56bfe6ee, &v5) < 0 )
  {
    v4 = 5017;
  }
  else
  {
    (*(void (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v5 + 24LL))(v5, *a2);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    v4 = 5018;
  }
  WinSqmIncrementDWORD(0, v4, 1);
  SysFreeString(*a2);
}

```

## disassembly

```asm
0x18000cf60  mov     r11, rsp
0x18000cf63  mov     [r11+10h], rdx
0x18000cf67  mov     [r11+8], rcx
0x18000cf6b  push    rbx
0x18000cf6c  sub     rsp, 30h
0x18000cf70  mov     rbx, rdx
0x18000cf73  mov     dword ptr [r8], 1
0x18000cf7a  mov     qword ptr [r11+8], 0
0x18000cf82  lea     rax, [r11+8]
0x18000cf86  mov     [r11-18h], rax
0x18000cf8a  lea     r9, _GUID_8cec595b_07a1_11d9_b15e_000d56bfe6ee; riid
0x18000cf91  xor     edx, edx; pUnkOuter
0x18000cf93  lea     r8d, [rdx+3]; dwClsContext
0x18000cf97  lea     rcx, CLSID_HxHelpPane; rclsid
0x18000cf9e  call    cs:__imp_CoCreateInstance
0x18000cfa4  test    eax, eax
0x18000cfa6  js      short loc_18000CFD4
0x18000cfa8  mov     rcx, [rsp+38h+arg_0]
0x18000cfad  mov     rax, [rcx]
0x18000cfb0  mov     rdx, [rbx]
0x18000cfb3  mov     rax, [rax+18h]
0x18000cfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfbc  mov     rcx, [rsp+38h+arg_0]
0x18000cfc1  mov     rax, [rcx]
0x18000cfc4  mov     rax, [rax+10h]
0x18000cfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfcd  mov     edx, 139Ah
0x18000cfd2  jmp     short loc_18000CFD9
0x18000cfd4  mov     edx, 1399h
0x18000cfd9  mov     r8d, 1
0x18000cfdf  xor     ecx, ecx
0x18000cfe1  call    cs:__imp_WinSqmIncrementDWORD
0x18000cfe7  nop
0x18000cfe8  mov     rcx, [rbx]; bstrString
0x18000cfeb  call    cs:__imp_SysFreeString
0x18000cff1  add     rsp, 30h
0x18000cff5  pop     rbx
0x18000cff6  retn
```
