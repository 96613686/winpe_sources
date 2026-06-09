# CMapiPreviewer::AllowBrowsingToUrl(wchar_t const *,int *)

- ea: `0x1800224a4`
- end: `0x180022546`
- name: `?AllowBrowsingToUrl@CMapiPreviewer@@CAJPEB_WPEAH@Z`
- size: `162`
- prototype: `__int64 __fastcall(const wchar_t *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025fd0`
- `0x1800261c0`

## callees

- `0x180005210`
- `0x1800224a4`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800224e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800224e4`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::AllowBrowsingToUrl(const wchar_t *a1, int *a2)
{
  HRESULT v4; // ebx
  int v6; // [rsp+48h] [rbp+10h] BYREF
  LPVOID v7; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v7 = 0;
  v4 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 0x17u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &v7);
  v6 = -1;
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, int *, _QWORD))(*(_QWORD *)v7 + 40LL))(v7, a1, &v6, 0);
    if ( v4 >= 0 )
      *a2 = (unsigned int)(v6 - 1) <= 2;
  }
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800224a4  mov     r11, rsp
0x1800224a7  mov     [r11+8], rbx
0x1800224ab  mov     [r11+20h], rsi
0x1800224af  push    rdi
0x1800224b0  sub     rsp, 30h
0x1800224b4  mov     rdi, rdx
0x1800224b7  mov     rsi, rcx
0x1800224ba  mov     dword ptr [rdx], 0
0x1800224c0  mov     qword ptr [r11+18h], 0
0x1800224c8  lea     rax, [r11+18h]
0x1800224cc  mov     [r11-18h], rax
0x1800224d0  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x1800224d7  xor     edx, edx; pUnkOuter
0x1800224d9  lea     r8d, [rdx+17h]; dwClsContext
0x1800224dd  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x1800224e4  call    cs:__imp_CoCreateInstance
0x1800224ea  mov     ebx, eax
0x1800224ec  mov     [rsp+38h+arg_8], 0FFFFFFFFh
0x1800224f4  test    eax, eax
0x1800224f6  js      short loc_18002252A
0x1800224f8  mov     rcx, [rsp+38h+arg_10]
0x1800224fd  mov     rax, [rcx]
0x180022500  xor     r9d, r9d
0x180022503  lea     r8, [rsp+38h+arg_8]
0x180022508  mov     rdx, rsi
0x18002250b  mov     rax, [rax+28h]
0x18002250f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022514  mov     ebx, eax
0x180022516  test    eax, eax
0x180022518  js      short loc_18002252A
0x18002251a  mov     eax, [rsp+38h+arg_8]
0x18002251e  dec     eax
0x180022520  xor     ecx, ecx
0x180022522  cmp     eax, 2
0x180022525  setbe   cl
0x180022528  mov     [rdi], ecx
0x18002252a  lea     rcx, [rsp+38h+arg_10]
0x18002252f  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180022534  mov     eax, ebx
0x180022536  mov     rbx, [rsp+38h+arg_0]
0x18002253b  mov     rsi, [rsp+38h+arg_18]
0x180022540  add     rsp, 30h
0x180022544  pop     rdi
0x180022545  retn
```
