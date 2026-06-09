# CLSIDToStr(_GUID const &,char *,int)

- ea: `0x180015150`
- end: `0x180015198`
- name: `?CLSIDToStr@@YAJAEBU_GUID@@PEADH@Z`
- size: `72`
- prototype: `__int64 __fastcall(const struct _GUID *, char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015474`
- `0x180015630`

## callees

- `0x180015150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18001517f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18001517f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015167`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015167`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001518a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001518a`

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
0x180015150  push    rbx
0x180015152  sub     rsp, 20h
0x180015156  mov     rbx, rdx
0x180015159  mov     [rsp+28h+lpsz], 0
0x180015162  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x180015167  call    cs:__imp_StringFromCLSID
0x18001516d  test    eax, eax
0x18001516f  js      short loc_180015192
0x180015171  mov     rdx, [rsp+28h+lpsz]
0x180015176  mov     r8d, 27h ; '''
0x18001517c  mov     rcx, rbx
0x18001517f  call    cs:__imp__o_wcstombs
0x180015185  mov     rcx, [rsp+28h+lpsz]; pv
0x18001518a  call    cs:__imp_CoTaskMemFree
0x180015190  xor     eax, eax
0x180015192  add     rsp, 20h
0x180015196  pop     rbx
0x180015197  retn
```
