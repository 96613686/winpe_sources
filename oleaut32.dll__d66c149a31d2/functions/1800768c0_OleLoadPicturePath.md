# OleLoadPicturePath

- ea: `0x1800768c0`
- end: `0x18007691a`
- name: `OleLoadPicturePath`
- size: `90`
- prototype: `HRESULT __stdcall(LPOLESTR szURLorPath, LPUNKNOWN punkCaller, DWORD dwReserved, OLE_COLOR clrReserved, const IID *const riid, LPVOID *ppvRet)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18004e87c`
- `0x1800768c0`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!OleLoadPicturePathExt` at `0x18007690b`
- `ext-ms-win-ole32-oleautomation-l1-1-0!OleLoadPicturePathExt` at `0x18007690b`

## pseudocode

```c
HRESULT __stdcall OleLoadPicturePath(
        LPOLESTR szURLorPath,
        LPUNKNOWN punkCaller,
        DWORD dwReserved,
        OLE_COLOR clrReserved,
        const IID *const riid,
        LPVOID *ppvRet)
{
  if ( (unsigned __int8)IsMonikerLoadTypeLibPresent() )
    return OleLoadPicturePathExt(szURLorPath, punkCaller, dwReserved, clrReserved, riid, ppvRet);
  else
    return -2147467263;
}

```

## disassembly

```asm
0x1800768c0  push    rbx
0x1800768c2  push    rbp
0x1800768c3  push    rsi
0x1800768c4  push    rdi
0x1800768c5  sub     rsp, 38h
0x1800768c9  mov     ebx, r9d
0x1800768cc  mov     edi, r8d
0x1800768cf  mov     rsi, rdx
0x1800768d2  mov     rbp, rcx
0x1800768d5  call    IsMonikerLoadTypeLibPresent
0x1800768da  test    al, al
0x1800768dc  jnz     short loc_1800768E5
0x1800768de  mov     eax, 80004001h
0x1800768e3  jmp     short loc_180076911
0x1800768e5  mov     rax, [rsp+58h+ppvRet]
0x1800768ed  mov     r9d, ebx
0x1800768f0  mov     [rsp+58h+var_30], rax
0x1800768f5  mov     r8d, edi
0x1800768f8  mov     rax, [rsp+58h+riid]
0x180076900  mov     rdx, rsi
0x180076903  mov     rcx, rbp
0x180076906  mov     [rsp+58h+var_38], rax
0x18007690b  call    cs:__imp_OleLoadPicturePathExt
0x180076911  add     rsp, 38h
0x180076915  pop     rdi
0x180076916  pop     rsi
0x180076917  pop     rbp
0x180076918  pop     rbx
0x180076919  retn
```
