# NfsXmlLoadXmlFromString(ushort const *,IXMLDOMDocument * *,uchar)

- ea: `0x180027b7c`
- end: `0x180027c56`
- name: `?NfsXmlLoadXmlFromString@@YAJPEBGPEAPEAUIXMLDOMDocument@@E@Z`
- size: `218`
- prototype: `__int64 __fastcall(OLECHAR *psz, LPVOID *ppv, unsigned __int8)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027c5c`
- `0x18002889c`
- `0x180028ac4`

## callees

- `0x180027b7c`
- `0x180028fa8`
- `0x180037010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180027bb1`
- `ole32!CoCreateInstance` at `0x180027bb1`
- `OLEAUT32!__imp_SysAllocString` at `0x180027bc2`
- `OLEAUT32!__imp_SysAllocString` at `0x180027bc2`

## pseudocode

```c
HRESULT __fastcall NfsXmlLoadXmlFromString(OLECHAR *psz, LPVOID *ppv, char a3)
{
  HRESULT result; // eax
  BSTR v6; // rdi
  __int64 v7; // rcx
  __int16 v8; // [rsp+50h] [rbp+18h] BYREF
  struct IXMLDOMParseError *v9; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  if ( !a3 || (result = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, ppv), result >= 0) )
  {
    v6 = SysAllocString(psz);
    if ( v6 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 504LL))(*ppv, 0);
      result = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int16 *))(*(_QWORD *)*ppv + 520LL))(*ppv, v6, &v8);
      if ( result >= 0 && (result || v8 != -1) )
      {
        v7 = (__int64)*ppv;
        v9 = 0;
        if ( (*(int (__fastcall **)(__int64, struct IXMLDOMParseError **))(*(_QWORD *)v7 + 480LL))(v7, &v9) >= 0 )
        {
          if ( v9 )
            WriteLoadFailureInformation(v9);
        }
        return -1072897499;
      }
    }
    else
    {
      return -2147024888;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027b7c  mov     [rsp+arg_0], rbx
0x180027b81  push    rdi
0x180027b82  sub     rsp, 30h
0x180027b86  xor     eax, eax
0x180027b88  mov     rbx, rdx
0x180027b8b  mov     [rsp+38h+arg_10], ax
0x180027b90  mov     rdi, rcx
0x180027b93  test    r8b, r8b
0x180027b96  jz      short loc_180027BBF
0x180027b98  mov     [rsp+38h+ppv], rdx; ppv
0x180027b9d  lea     r9, IID_IXMLDOMDocument; riid
0x180027ba4  xor     edx, edx; pUnkOuter
0x180027ba6  lea     r8d, [rax+1]; dwClsContext
0x180027baa  lea     rcx, CLSID_DOMDocument60; rclsid
0x180027bb1  call    cs:__imp_CoCreateInstance
0x180027bb7  test    eax, eax
0x180027bb9  js      loc_180027C4B
0x180027bbf  mov     rcx, rdi; psz
0x180027bc2  call    cs:__imp_SysAllocString
0x180027bc8  mov     rdi, rax
0x180027bcb  test    rax, rax
0x180027bce  jnz     short loc_180027BD7
0x180027bd0  mov     eax, 80070008h
0x180027bd5  jmp     short loc_180027C4B
0x180027bd7  mov     rcx, [rbx]
0x180027bda  xor     edx, edx
0x180027bdc  mov     rax, [rcx]
0x180027bdf  mov     rax, [rax+1F8h]
0x180027be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027beb  mov     rcx, [rbx]
0x180027bee  lea     r8, [rsp+38h+arg_10]
0x180027bf3  mov     rdx, rdi
0x180027bf6  mov     rax, [rcx]
0x180027bf9  mov     rax, [rax+208h]
0x180027c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c05  test    eax, eax
0x180027c07  js      short loc_180027C4B
0x180027c09  jnz     short loc_180027C13
0x180027c0b  cmp     [rsp+38h+arg_10], 0FFFFh
0x180027c11  jz      short loc_180027C4B
0x180027c13  mov     rcx, [rbx]
0x180027c16  lea     rdx, [rsp+38h+arg_18]
0x180027c1b  mov     [rsp+38h+arg_18], 0
0x180027c24  mov     rax, [rcx]
0x180027c27  mov     rax, [rax+1E0h]
0x180027c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c33  test    eax, eax
0x180027c35  js      short loc_180027C46
0x180027c37  mov     rcx, [rsp+38h+arg_18]; struct IXMLDOMParseError *
0x180027c3c  test    rcx, rcx
0x180027c3f  jz      short loc_180027C46
0x180027c41  call    ?WriteLoadFailureInformation@@YAXPEAUIXMLDOMParseError@@@Z; WriteLoadFailureInformation(IXMLDOMParseError *)
0x180027c46  mov     eax, 0C00CE225h
0x180027c4b  mov     rbx, [rsp+38h+arg_0]
0x180027c50  add     rsp, 30h
0x180027c54  pop     rdi
0x180027c55  retn
```
