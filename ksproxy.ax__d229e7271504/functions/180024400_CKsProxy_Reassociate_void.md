# CKsProxy::Reassociate(void)

- ea: `0x180024400`
- end: `0x180024494`
- name: `?Reassociate@CKsProxy@@UEAAJXZ`
- size: `148`
- prototype: `__int64 __fastcall(CKsProxy *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180024400`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180024464`
- `KERNEL32!GetLastError` at `0x180024464`
- `KERNEL32!CreateFileW` at `0x180024444`
- `KERNEL32!CreateFileW` at `0x180024444`

## pseudocode

```c
__int64 __fastcall CKsProxy::Reassociate(CKsProxy *this)
{
  const WCHAR *v2; // rcx
  unsigned int v3; // ebx
  ISpecifyPropertyPages_vtbl *FileW; // rax
  signed int LastError; // eax

  v2 = *(const WCHAR **)&this->m_MarshalerList.m_Cache.m_iCacheSize;
  if ( !v2 || this->ISpecifyPropertyPages::IUnknown::__vftable )
  {
    return (unsigned int)-2147024894;
  }
  else
  {
    v3 = 0;
    FileW = (ISpecifyPropertyPages_vtbl *)CreateFileW(v2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
    this->ISpecifyPropertyPages::IUnknown::__vftable = FileW;
    if ( FileW == (ISpecifyPropertyPages_vtbl *)-1LL )
    {
      this->ISpecifyPropertyPages::IUnknown::__vftable = 0;
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180024400  mov     rax, rsp
0x180024403  mov     [rax+8], rbx
0x180024407  push    rdi
0x180024408  sub     rsp, 40h
0x18002440c  mov     rdi, rcx
0x18002440f  mov     rcx, [rcx+160h]; lpFileName
0x180024416  test    rcx, rcx
0x180024419  jz      short loc_180024481
0x18002441b  cmp     qword ptr [rdi+88h], 0
0x180024423  jnz     short loc_180024481
0x180024425  xor     ebx, ebx
0x180024427  xor     r9d, r9d; lpSecurityAttributes
0x18002442a  mov     [rax-18h], rbx
0x18002442e  xor     r8d, r8d; dwShareMode
0x180024431  mov     dword ptr [rax-20h], 40000080h
0x180024438  mov     edx, 0C0000000h; dwDesiredAccess
0x18002443d  mov     dword ptr [rax-28h], 3
0x180024444  call    cs:__imp_CreateFileW
0x18002444b  nop     dword ptr [rax+rax+00h]
0x180024450  mov     [rdi+88h], rax
0x180024457  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002445b  jnz     short loc_180024486
0x18002445d  mov     [rdi+88h], rbx
0x180024464  call    cs:__imp_GetLastError
0x18002446b  nop     dword ptr [rax+rax+00h]
0x180024470  mov     ebx, eax
0x180024472  test    eax, eax
0x180024474  jle     short loc_180024486
0x180024476  movzx   ebx, ax
0x180024479  or      ebx, 80070000h
0x18002447f  jmp     short loc_180024486
0x180024481  mov     ebx, 80070002h
0x180024486  mov     eax, ebx
0x180024488  mov     rbx, [rsp+48h+arg_0]
0x18002448d  add     rsp, 40h
0x180024491  pop     rdi
0x180024492  retn
```
