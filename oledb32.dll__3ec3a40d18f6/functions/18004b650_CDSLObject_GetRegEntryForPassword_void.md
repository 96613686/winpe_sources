# CDSLObject::GetRegEntryForPassword(void)

- ea: `0x18004b650`
- end: `0x18004b729`
- name: `?GetRegEntryForPassword@CDSLObject@@QEAAKXZ`
- size: `217`
- prototype: `unsigned int __fastcall(CDSLObject *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004be30`
- `0x180056e50`

## callees

- `0x180013870`
- `0x18002b42c`
- `0x18002bccc`
- `0x18004b650`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18004b6e2`
- `ADVAPI32!RegQueryValueExW` at `0x18004b6e2`
- `ole32!CoTaskMemFree` at `0x18004b70e`
- `ole32!CoTaskMemFree` at `0x18004b70e`
- `ole32!StringFromCLSID` at `0x18004b67e`
- `ole32!StringFromCLSID` at `0x18004b67e`

## string_xrefs

- `0x18004b688`: `CLSID`

## pseudocode

```c
__int64 __fastcall CDSLObject::GetRegEntryForPassword(CDSLObject *this)
{
  unsigned int v1; // r9d
  unsigned int v2; // r9d
  unsigned int v3; // ebx
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int Data; // [rsp+70h] [rbp+18h] BYREF
  int v7; // [rsp+74h] [rbp+1Ch]
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF
  DWORD Type; // [rsp+80h] [rbp+28h] BYREF
  LPOLESTR lpsz; // [rsp+88h] [rbp+30h] BYREF

  v7 = HIDWORD(this);
  lpsz = 0;
  Data = 0;
  memset(hKey, 0, 24);
  if ( StringFromCLSID(&CLSID_DataLinks, &lpsz) < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147467259, L"<CDSLObject::GetRegEntryForPassword|OLEDB|ERR> ", 0x6A4u);
  }
  else
  {
    ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, L"CLSID", v1);
    if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, hKey[0], lpsz, v2) )
    {
      Type = 0;
      cbData = 4;
      RegQueryValueExW(hKey[0], L"fDPS", 0, &Type, (LPBYTE)&Data, &cbData);
    }
  }
  CoTaskMemFree(lpsz);
  v3 = Data;
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v3;
}

```

## disassembly

```asm
0x18004b650  mov     qword ptr [rsp-10h+Data], rcx
0x18004b655  push    rbp
0x18004b656  push    rbx
0x18004b657  mov     rbp, rsp
0x18004b65a  sub     rsp, 58h
0x18004b65e  xor     ebx, ebx
0x18004b660  lea     rdx, [rbp+lpsz]; lplpsz
0x18004b664  lea     rcx, CLSID_DataLinks; rclsid
0x18004b66b  mov     [rbp+lpsz], rbx
0x18004b66f  mov     [rbp+Data], ebx
0x18004b672  mov     [rbp+hKey], rbx
0x18004b676  mov     [rbp+var_20], rbx
0x18004b67a  mov     [rbp+var_18], rbx
0x18004b67e  call    cs:__imp_StringFromCLSID
0x18004b684  test    eax, eax
0x18004b686  js      short loc_18004B6EA
0x18004b688  lea     r8, aClsid_0; "CLSID"
0x18004b68f  mov     rdx, 0FFFFFFFF80000000h; hKey
0x18004b696  lea     rcx, [rbp+hKey]; this
0x18004b69a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004b69f  mov     r8, [rbp+lpsz]; lpSubKey
0x18004b6a3  lea     rcx, [rbp+hKey]; this
0x18004b6a7  mov     rdx, [rbp+hKey]; hKey
0x18004b6ab  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004b6b0  test    eax, eax
0x18004b6b2  jnz     short loc_18004B70A
0x18004b6b4  mov     rcx, [rbp+hKey]; hKey
0x18004b6b8  lea     rax, [rbp+cbData]
0x18004b6bc  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18004b6c1  lea     r9, [rbp+Type]; lpType
0x18004b6c5  lea     rax, [rbp+Data]
0x18004b6c9  mov     [rbp+Type], ebx
0x18004b6cc  xor     r8d, r8d; lpReserved
0x18004b6cf  mov     [rsp+58h+lpData], rax; lpData
0x18004b6d4  lea     rdx, aFdps; "fDPS"
0x18004b6db  mov     [rbp+cbData], 4
0x18004b6e2  call    cs:__imp_RegQueryValueExW
0x18004b6e8  jmp     short loc_18004B70A
0x18004b6ea  test    byte ptr cs:_bidGblFlags, 2
0x18004b6f1  jz      short loc_18004B70A
0x18004b6f3  mov     r8d, 6A4h; unsigned int
0x18004b6f9  lea     rdx, aCdslobjectGetr; "<CDSLObject::GetRegEntryForPassword|OLE"...
0x18004b700  mov     ecx, 80004005h; int
0x18004b705  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004b70a  mov     rcx, [rbp+lpsz]; pv
0x18004b70e  call    cs:__imp_CoTaskMemFree
0x18004b714  mov     ebx, [rbp+Data]
0x18004b717  lea     rcx, [rbp+hKey]; this
0x18004b71b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004b720  mov     eax, ebx
0x18004b722  add     rsp, 58h
0x18004b726  pop     rbx
0x18004b727  pop     rbp
0x18004b728  retn
```
