# CKsProxy::Reassociate(void)

- ea: `0x1000e860`
- end: `0x1000e8c3`
- name: `?Reassociate@CKsProxy@@UAGJXZ`
- size: `99`
- prototype: `unsigned int __stdcall(CKsProxy *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1000e860`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000e89f`
- `KERNEL32!GetLastError` at `0x1000e89f`
- `KERNEL32!CreateFileW` at `0x1000e88e`
- `KERNEL32!CreateFileW` at `0x1000e88e`

## pseudocode

```c
unsigned int __stdcall CKsProxy::Reassociate(CKsProxy *this)
{
  unsigned int v1; // esi
  CBaseList::CNode *m_pLast; // eax
  CPersistStream_vtbl *FileW; // eax
  signed int LastError; // eax

  v1 = 0;
  m_pLast = this->m_MarshalerList.m_pLast;
  if ( !m_pLast || this->CPersistStream::IPersistStream::IPersist::IUnknown::__vftable )
    return -2147024894;
  FileW = (CPersistStream_vtbl *)CreateFileW((LPCWSTR)m_pLast, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
  this->CPersistStream::IPersistStream::IPersist::IUnknown::__vftable = FileW;
  if ( FileW == (CPersistStream_vtbl *)-1 )
  {
    this->CPersistStream::IPersistStream::IPersist::IUnknown::__vftable = 0;
    LastError = GetLastError();
    v1 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return LastError;
  }
  return v1;
}

```

## disassembly

```asm
0x1000e860  mov     edi, edi
0x1000e862  push    ebp
0x1000e863  mov     ebp, esp
0x1000e865  push    ebx
0x1000e866  push    esi
0x1000e867  push    edi
0x1000e868  mov     edi, [ebp+this]
0x1000e86b  xor     ebx, ebx
0x1000e86d  mov     esi, ebx
0x1000e86f  mov     eax, [edi+0C8h]
0x1000e875  test    eax, eax
0x1000e877  jz      short loc_1000E8B5
0x1000e879  cmp     [edi+50h], ebx
0x1000e87c  jnz     short loc_1000E8B5
0x1000e87e  push    ebx; hTemplateFile
0x1000e87f  push    40000080h; dwFlagsAndAttributes
0x1000e884  push    3; dwCreationDisposition
0x1000e886  push    ebx; lpSecurityAttributes
0x1000e887  push    ebx; dwShareMode
0x1000e888  push    0C0000000h; dwDesiredAccess
0x1000e88d  push    eax; lpFileName
0x1000e88e  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x1000e894  mov     [edi+50h], eax
0x1000e897  cmp     eax, 0FFFFFFFFh
0x1000e89a  jnz     short loc_1000E8BA
0x1000e89c  mov     [edi+50h], ebx
0x1000e89f  call    ds:__imp__GetLastError@0; GetLastError()
0x1000e8a5  movzx   esi, ax
0x1000e8a8  or      esi, 80070000h
0x1000e8ae  test    eax, eax
0x1000e8b0  cmovle  esi, eax
0x1000e8b3  jmp     short loc_1000E8BA
0x1000e8b5  mov     esi, 80070002h
0x1000e8ba  pop     edi
0x1000e8bb  mov     eax, esi
0x1000e8bd  pop     esi
0x1000e8be  pop     ebx
0x1000e8bf  pop     ebp
0x1000e8c0  retn    4
```
