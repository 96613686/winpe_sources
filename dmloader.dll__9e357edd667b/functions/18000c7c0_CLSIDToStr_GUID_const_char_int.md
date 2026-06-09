# CLSIDToStr(_GUID const &,char *,int)

- ea: `0x18000c7c0`
- end: `0x18000c808`
- name: `?CLSIDToStr@@YAJAEBU_GUID@@PEADH@Z`
- size: `72`
- prototype: `__int64 __fastcall(const struct _GUID *, char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000cae4`
- `0x18000cca0`

## callees

- `0x18000c7c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18000c7ef`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18000c7ef`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c7d7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c7d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7fa`

## pseudocode

```c
HRESULT __fastcall CLSIDToStr(const struct _GUID *a1, char *a2)
{
  HRESULT result; // eax
  LPOLESTR lpsz; // [rsp+48h] [rbp+20h] BYREF

  lpsz = 0;
  result = StringFromCLSID(a1, &lpsz);
  if ( result >= 0 )
  {
    _o_wcstombs(a2, lpsz, 39);
    CoTaskMemFree(lpsz);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c7c0  push    rbx
0x18000c7c2  sub     rsp, 20h
0x18000c7c6  mov     rbx, rdx
0x18000c7c9  mov     [rsp+28h+lpsz], 0
0x18000c7d2  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x18000c7d7  call    cs:__imp_StringFromCLSID
0x18000c7dd  test    eax, eax
0x18000c7df  js      short loc_18000C802
0x18000c7e1  mov     rdx, [rsp+28h+lpsz]
0x18000c7e6  mov     r8d, 27h ; '''
0x18000c7ec  mov     rcx, rbx
0x18000c7ef  call    cs:__imp__o_wcstombs
0x18000c7f5  mov     rcx, [rsp+28h+lpsz]; pv
0x18000c7fa  call    cs:__imp_CoTaskMemFree
0x18000c800  xor     eax, eax
0x18000c802  add     rsp, 20h
0x18000c806  pop     rbx
0x18000c807  retn
```
