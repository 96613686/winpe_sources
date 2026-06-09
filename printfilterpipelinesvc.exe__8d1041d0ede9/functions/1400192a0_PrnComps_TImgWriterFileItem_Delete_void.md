# PrnComps::TImgWriterFileItem::Delete(void)

- ea: `0x1400192a0`
- end: `0x1400192cf`
- name: `?Delete@TImgWriterFileItem@PrnComps@@UEAAXXZ`
- size: `47`
- prototype: `void __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400190b0`

## callees

- `0x1400071e8`
- `0x1400192a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400192c3`
- `KERNEL32!GetLastError` at `0x1400192c3`
- `KERNEL32!DeleteFileW` at `0x1400192b9`
- `KERNEL32!DeleteFileW` at `0x1400192b9`

## pseudocode

```c
void __fastcall PrnComps::TImgWriterFileItem::Delete(LPCWSTR *this)
{
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(this + 4);
  if ( !DeleteFileW(this[19]) )
    GetLastError();
}

```

## disassembly

```asm
0x1400192a0  push    rbx
0x1400192a2  sub     rsp, 20h
0x1400192a6  mov     rbx, rcx
0x1400192a9  add     rcx, 20h ; ' '
0x1400192ad  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x1400192b2  mov     rcx, [rbx+98h]; lpFileName
0x1400192b9  call    cs:__imp_DeleteFileW
0x1400192bf  test    eax, eax
0x1400192c1  jnz     short loc_1400192C9
0x1400192c3  call    cs:__imp_GetLastError
0x1400192c9  add     rsp, 20h
0x1400192cd  pop     rbx
0x1400192ce  retn
```
