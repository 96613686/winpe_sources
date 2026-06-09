# CKsOutputPin::QueryId(ushort * *)

- ea: `0x10016200`
- end: `0x1001623c`
- name: `?QueryId@CKsOutputPin@@UAGJPAPAG@Z`
- size: `60`
- prototype: `int __stdcall(CKsOutputPin *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x10010ddb`
- `0x10016200`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10016207`
- `ole32!CoTaskMemAlloc` at `0x10016207`

## pseudocode

```c
int __stdcall CKsOutputPin::QueryId(CKsOutputPin *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // eax

  v2 = (unsigned __int16 *)CoTaskMemAlloc(0x16u);
  *a2 = v2;
  if ( !v2 )
    return -2147024882;
  StringCbPrintfW(v2, 0x16u, (wchar_t *)L"%u", this->m_DataTypeHandler);
  return 0;
}

```

## disassembly

```asm
0x10016200  mov     edi, edi
0x10016202  push    ebp
0x10016203  mov     ebp, esp
0x10016205  push    16h; cb
0x10016207  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001620d  mov     ecx, [ebp+arg_4]
0x10016210  mov     [ecx], eax
0x10016212  test    eax, eax
0x10016214  jz      short loc_10016233
0x10016216  mov     ecx, [ebp+this]
0x10016219  push    dword ptr [ecx+178h]
0x1001621f  push    offset aU; "%u"
0x10016224  push    16h; unsigned int
0x10016226  push    eax; Buffer
0x10016227  call    ?StringCbPrintfW@@YAJPAGIPBGZZ; StringCbPrintfW(ushort *,uint,ushort const *,...)
0x1001622c  add     esp, 10h
0x1001622f  xor     eax, eax
0x10016231  jmp     short loc_10016238
0x10016233  mov     eax, 8007000Eh
0x10016238  pop     ebp
0x10016239  retn    8
```
