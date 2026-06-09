# CProtocolsTable::GetStartProtocolPosition(CProtocolsTable::PrEnumInfo * *)

- ea: `0x180039920`
- end: `0x180039a6d`
- name: `?GetStartProtocolPosition@CProtocolsTable@@UEAAJPEAPEAUPrEnumInfo@1@@Z`
- size: `333`
- prototype: `__int64 __fastcall(CProtocolsTable *__hidden this, struct CProtocolsTable::PrEnumInfo **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180039920`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800399d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039a1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800399d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039a1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003996a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003996a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800399aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039a04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800399aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039a04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a42`

## string_xrefs

- `0x18003999f`: `DCOM Protocols`
- `0x1800399f9`: `DCOM Protocols`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProtocolsTable::GetStartProtocolPosition(
        CProtocolsTable *this,
        struct CProtocolsTable::PrEnumInfo **a2)
{
  BYTE *v3; // rsi
  struct CProtocolsTable::PrEnumInfo *v4; // rdi
  LSTATUS v5; // eax
  __int64 v6; // rbx
  bool v7; // cc
  struct CProtocolsTable::PrEnumInfo *v8; // rax
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  hKey = 0;
  Type = 0;
  v3 = 0;
  cbData = 0;
  v4 = 0;
  *a2 = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RPC", 0, 0x20019u, &hKey);
  LODWORD(v6) = v5;
  v7 = v5 <= 0;
  if ( v5
    || (v5 = RegQueryValueExW(hKey, L"DCOM Protocols", 0, &Type, 0, &cbData), v6 = (unsigned int)v5, v7 = v5 <= 0, v5) )
  {
    if ( v7 )
      goto LABEL_13;
    goto LABEL_3;
  }
  if ( cbData <= 4 )
    goto LABEL_13;
  v3 = (BYTE *)CoTaskMemAlloc(saturated_mul((unsigned __int64)cbData >> 1, (unsigned int)(v5 + 2)));
  if ( !v3 )
    goto LABEL_12;
  v5 = RegQueryValueExW(hKey, L"DCOM Protocols", 0, &Type, v3, &cbData);
  if ( v5 )
  {
    if ( v5 <= 0 )
    {
      LODWORD(v6) = v5;
      goto LABEL_13;
    }
LABEL_3:
    LODWORD(v6) = (unsigned __int16)v5 | 0x80070000;
    goto LABEL_13;
  }
  v8 = (struct CProtocolsTable::PrEnumInfo *)CoTaskMemAlloc(0x10u);
  v4 = v8;
  if ( v8 )
  {
    *((_QWORD *)v8 + 1) = v6;
    *(_QWORD *)v8 = v3;
  }
  else
  {
LABEL_12:
    LODWORD(v6) = -2147024882;
  }
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  if ( (int)v6 >= 0 )
  {
    *a2 = v4;
  }
  else if ( v3 )
  {
    CoTaskMemFree(v3);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180039920  push    rbp
0x180039922  push    rbx
0x180039923  push    rsi
0x180039924  push    rdi
0x180039925  push    r14
0x180039927  mov     rbp, rsp
0x18003992a  sub     rsp, 30h
0x18003992e  mov     r14, rdx
0x180039931  mov     [rbp+hKey], 0
0x180039939  mov     [rbp+Type], 0
0x180039940  xor     esi, esi
0x180039942  mov     [rbp+cbData], esi
0x180039945  xor     edi, edi
0x180039947  mov     [rdx], rsi
0x18003994a  lea     rax, [rbp+hKey]
0x18003994e  mov     [rsp+30h+phkResult], rax; phkResult
0x180039953  mov     r9d, 20019h; samDesired
0x180039959  xor     r8d, r8d; ulOptions
0x18003995c  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\RPC"
0x180039963  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003996a  call    cs:__imp_RegOpenKeyExW
0x180039970  mov     ebx, eax
0x180039972  test    eax, eax
0x180039974  jz      short loc_18003998A
0x180039976  jle     loc_180039A39
0x18003997c  movzx   ebx, ax
0x18003997f  or      ebx, 80070000h
0x180039985  jmp     loc_180039A39
0x18003998a  lea     rax, [rbp+cbData]
0x18003998e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180039993  mov     [rsp+30h+phkResult], rsi; lpData
0x180039998  lea     r9, [rbp+Type]; lpType
0x18003999c  xor     r8d, r8d; lpReserved
0x18003999f  lea     rdx, aDcomProtocols; "DCOM Protocols"
0x1800399a6  mov     rcx, [rbp+hKey]; hKey
0x1800399aa  call    cs:__imp_RegQueryValueExW
0x1800399b0  mov     ebx, eax
0x1800399b2  test    eax, eax
0x1800399b4  jnz     short loc_180039976
0x1800399b6  cmp     [rbp+cbData], 4
0x1800399ba  jbe     short loc_180039A39
0x1800399bc  mov     ecx, [rbp+cbData]
0x1800399bf  shr     rcx, 1
0x1800399c2  lea     eax, [rbx+2]
0x1800399c5  mul     rcx
0x1800399c8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800399cf  cmovb   rax, rcx
0x1800399d3  mov     rcx, rax; cb
0x1800399d6  call    cs:__imp_CoTaskMemAlloc
0x1800399dc  mov     rsi, rax
0x1800399df  test    rax, rax
0x1800399e2  jz      short loc_180039A34
0x1800399e4  lea     rax, [rbp+cbData]
0x1800399e8  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800399ed  mov     [rsp+30h+phkResult], rsi; lpData
0x1800399f2  lea     r9, [rbp+Type]; lpType
0x1800399f6  xor     r8d, r8d; lpReserved
0x1800399f9  lea     rdx, aDcomProtocols; "DCOM Protocols"
0x180039a00  mov     rcx, [rbp+hKey]; hKey
0x180039a04  call    cs:__imp_RegQueryValueExW
0x180039a0a  test    eax, eax
0x180039a0c  jz      short loc_180039A18
0x180039a0e  jg      loc_18003997C
0x180039a14  mov     ebx, eax
0x180039a16  jmp     short loc_180039A39
0x180039a18  mov     ecx, 10h; cb
0x180039a1d  call    cs:__imp_CoTaskMemAlloc
0x180039a23  mov     rdi, rax
0x180039a26  test    rax, rax
0x180039a29  jz      short loc_180039A34
0x180039a2b  mov     [rax+8], rbx
0x180039a2f  mov     [rax], rsi
0x180039a32  jmp     short loc_180039A39
0x180039a34  mov     ebx, 8007000Eh
0x180039a39  mov     rcx, [rbp+hKey]; hKey
0x180039a3d  test    rcx, rcx
0x180039a40  jz      short loc_180039A48
0x180039a42  call    cs:__imp_RegCloseKey
0x180039a48  test    ebx, ebx
0x180039a4a  jns     short loc_180039A5D
0x180039a4c  test    rsi, rsi
0x180039a4f  jz      short loc_180039A60
0x180039a51  mov     rcx, rsi; pv
0x180039a54  call    cs:__imp_CoTaskMemFree
0x180039a5a  nop
0x180039a5b  jmp     short loc_180039A60
0x180039a5d  mov     [r14], rdi
0x180039a60  mov     eax, ebx
0x180039a62  add     rsp, 30h
0x180039a66  pop     r14
0x180039a68  pop     rdi
0x180039a69  pop     rsi
0x180039a6a  pop     rbx
0x180039a6b  pop     rbp
0x180039a6c  retn
```
