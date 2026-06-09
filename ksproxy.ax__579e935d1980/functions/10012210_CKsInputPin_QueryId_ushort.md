# CKsInputPin::QueryId(ushort * *)

- ea: `0x10012210`
- end: `0x1001224c`
- name: `?QueryId@CKsInputPin@@UAGJPAPAG@Z`
- size: `60`
- prototype: `int __stdcall(CKsInputPin *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x10010ddb`
- `0x10012210`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x10012217`
- `ole32!CoTaskMemAlloc` at `0x10012217`

## pseudocode

```c
int __stdcall CKsInputPin::QueryId(CKsInputPin *this, unsigned __int16 **a2)
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
0x10012210  mov     edi, edi
0x10012212  push    ebp
0x10012213  mov     ebp, esp
0x10012215  push    16h; cb
0x10012217  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001221d  mov     ecx, [ebp+arg_4]
0x10012220  mov     [ecx], eax
0x10012222  test    eax, eax
0x10012224  jz      short loc_10012243
0x10012226  mov     ecx, [ebp+this]
0x10012229  push    dword ptr [ecx+100h]
0x1001222f  push    offset aU; "%u"
0x10012234  push    16h; unsigned int
0x10012236  push    eax; Buffer
0x10012237  call    ?StringCbPrintfW@@YAJPAGIPBGZZ; StringCbPrintfW(ushort *,uint,ushort const *,...)
0x1001223c  add     esp, 10h
0x1001223f  xor     eax, eax
0x10012241  jmp     short loc_10012248
0x10012243  mov     eax, 8007000Eh
0x10012248  pop     ebp
0x10012249  retn    8
```
