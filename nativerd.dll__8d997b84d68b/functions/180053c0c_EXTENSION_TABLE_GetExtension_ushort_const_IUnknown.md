# EXTENSION_TABLE::GetExtension(ushort const *,IUnknown * *)

- ea: `0x180053c0c`
- end: `0x180053ccd`
- name: `?GetExtension@EXTENSION_TABLE@@AEAAJPEBGPEAPEAUIUnknown@@@Z`
- size: `193`
- prototype: `int(EXTENSION_TABLE *__hidden this, const unsigned __int16 *, struct IUnknown **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031df8`
- `0x1800576f8`
- `0x1800584f0`

## callees

- `0x180053c0c`
- `0x180053cd4`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053c7f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053c7f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180053c5c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180053c5c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180053c4a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180053c4a`

## pseudocode

```c
__int64 __fastcall EXTENSION_TABLE::GetExtension(EXTENSION_TABLE *this, const unsigned __int16 *a2, LPVOID *a3)
{
  HRESULT v5; // ebx
  HRESULT v7; // [rsp+28h] [rbp-30h]
  GUID pclsid; // [rsp+30h] [rbp-28h] BYREF

  pclsid = 0;
  if ( !a2 || !a3 )
  {
    v5 = -2147024809;
LABEL_8:
    if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 4) != 0 )
    {
      v7 = v5;
      McTemplateU0zjzd_EtwEventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)&pclsid,
        (__int64)a2,
        v7,
        *(_QWORD *)&pclsid.Data1,
        *(_QWORD *)pclsid.Data4);
    }
    return (unsigned int)v5;
  }
  if ( CLSIDFromString(a2, &pclsid) < 0 )
  {
    v5 = CLSIDFromProgID(a2, &pclsid);
    if ( v5 < 0 )
      goto LABEL_8;
  }
  v5 = CoCreateInstance(&pclsid, 0, 1u, &IID_IUnknown, a3);
  if ( v5 < 0 )
    goto LABEL_8;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180053c0c  mov     [rsp+arg_0], rbx
0x180053c11  mov     [rsp+arg_18], rsi
0x180053c16  push    rdi
0x180053c17  sub     rsp, 50h
0x180053c1b  mov     rax, cs:__security_cookie
0x180053c22  xor     rax, rsp
0x180053c25  mov     [rsp+58h+var_18], rax
0x180053c2a  xorps   xmm0, xmm0
0x180053c2d  mov     rsi, r8
0x180053c30  mov     rdi, rdx
0x180053c33  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x180053c38  test    rdx, rdx
0x180053c3b  jz      short loc_180053C8D
0x180053c3d  test    r8, r8
0x180053c40  jz      short loc_180053C8D
0x180053c42  lea     rdx, [rsp+58h+pclsid]; pclsid
0x180053c47  mov     rcx, rdi; lpsz
0x180053c4a  call    cs:__imp_CLSIDFromString
0x180053c50  test    eax, eax
0x180053c52  jns     short loc_180053C68
0x180053c54  lea     rdx, [rsp+58h+pclsid]; lpclsid
0x180053c59  mov     rcx, rdi; lpszProgID
0x180053c5c  call    cs:__imp_CLSIDFromProgID
0x180053c62  mov     ebx, eax
0x180053c64  test    eax, eax
0x180053c66  js      short loc_180053C92
0x180053c68  xor     edx, edx; pUnkOuter
0x180053c6a  mov     [rsp+58h+ppv], rsi; ppv
0x180053c6f  lea     r9, IID_IUnknown; riid
0x180053c76  lea     rcx, [rsp+58h+pclsid]; rclsid
0x180053c7b  lea     r8d, [rdx+1]; dwClsContext
0x180053c7f  call    cs:__imp_CoCreateInstance
0x180053c85  mov     ebx, eax
0x180053c87  test    eax, eax
0x180053c89  js      short loc_180053C92
0x180053c8b  jmp     short loc_180053CAE
0x180053c8d  mov     ebx, 80070057h
0x180053c92  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 4
0x180053c99  jz      short loc_180053CAE
0x180053c9b  mov     [rsp+58h+var_30], ebx
0x180053c9f  lea     r9, [rsp+58h+pclsid]
0x180053ca4  mov     [rsp+58h+ppv], rdi
0x180053ca9  call    McTemplateU0zjzd_EtwEventWriteTransfer
0x180053cae  mov     eax, ebx
0x180053cb0  mov     rcx, [rsp+58h+var_18]
0x180053cb5  xor     rcx, rsp; StackCookie
0x180053cb8  call    __security_check_cookie
0x180053cbd  mov     rbx, [rsp+58h+arg_0]
0x180053cc2  mov     rsi, [rsp+58h+arg_18]
0x180053cc7  add     rsp, 50h
0x180053ccb  pop     rdi
0x180053ccc  retn
```
