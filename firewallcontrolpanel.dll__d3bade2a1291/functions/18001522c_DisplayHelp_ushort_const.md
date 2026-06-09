# DisplayHelp(ushort const *)

- ea: `0x18001522c`
- end: `0x1800152b8`
- name: `?DisplayHelp@@YAJPEBG@Z`
- size: `140`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011e94`

## callees

- `0x180013e00`
- `0x18001522c`
- `0x180032010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800152aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800152aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001526f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001526f`

## pseudocode

```c
__int64 __fastcall DisplayHelp(const unsigned __int16 *a1)
{
  HRESULT v1; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"mshelp://windows/?id=f12788e4-8405-4cc2-b363-b76b71b01a20");
  v1 = CoCreateInstance(
         &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
         0,
         1u,
         &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
         &ppv);
  if ( v1 >= 0 )
  {
    v1 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 24LL))(ppv, bstrString);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  SysFreeString(bstrString);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001522c  mov     [rsp+arg_0], rcx
0x180015231  push    rbx
0x180015232  sub     rsp, 30h
0x180015236  mov     [rsp+38h+arg_0], 0
0x18001523f  lea     rdx, aMshelpWindowsI; "mshelp://windows/?id=f12788e4-8405-4cc2"...
0x180015246  lea     rcx, [rsp+38h+bstrString]; this
0x18001524b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180015250  nop
0x180015251  lea     rax, [rsp+38h+arg_0]
0x180015256  mov     [rsp+38h+ppv], rax; ppv
0x18001525b  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180015262  xor     edx, edx; pUnkOuter
0x180015264  lea     r8d, [rdx+1]; dwClsContext
0x180015268  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x18001526f  call    cs:__imp_CoCreateInstance
0x180015275  mov     ebx, eax
0x180015277  test    eax, eax
0x180015279  js      short loc_1800152A5
0x18001527b  mov     rcx, [rsp+38h+arg_0]
0x180015280  mov     rax, [rcx]
0x180015283  mov     rdx, [rsp+38h+bstrString]
0x180015288  mov     rax, [rax+18h]
0x18001528c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015291  mov     ebx, eax
0x180015293  mov     rcx, [rsp+38h+arg_0]
0x180015298  mov     rax, [rcx]
0x18001529b  mov     rax, [rax+10h]
0x18001529f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152a4  nop
0x1800152a5  mov     rcx, [rsp+38h+bstrString]; bstrString
0x1800152aa  call    cs:__imp_SysFreeString
0x1800152b0  mov     eax, ebx
0x1800152b2  add     rsp, 30h
0x1800152b6  pop     rbx
0x1800152b7  retn
```
