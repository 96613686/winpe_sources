# CMemoryMappedCache::_InitROCacheObject(void)

- ea: `0x1800248e4`
- end: `0x180024a12`
- name: `?_InitROCacheObject@CMemoryMappedCache@@AEAAXXZ`
- size: `302`
- prototype: `void __fastcall(CMemoryMappedCache *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x180024340`
- `0x1800248a0`

## callees

- `0x180024594`
- `0x1800248e4`
- `0x180024a18`
- `0x18002513c`
- `0x18002568c`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a07`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800249bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800249bd`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800249d5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800249d5`

## pseudocode

```c
void __fastcall CMemoryMappedCache::_InitROCacheObject(CMemoryMappedCache *this, __int64 a2, unsigned int a3)
{
  HANDLE v4; // rax
  HANDLE FileW; // rax
  void *v6; // rdi
  DWORD FileSize; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-458h]
  unsigned __int16 v9[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR FileName[264]; // [rsp+250h] [rbp-228h] BYREF

  if ( !*((_QWORD *)this + 7) && CMemoryMappedCache::_GetObjectName(this, v9, a3) >= 0 )
  {
    v4 = OpenMapping((__int16 *)this + 44, (__int64)v9, *((_DWORD *)this + 5), 4u);
    *((_QWORD *)this + 7) = v4;
    if ( !v4 && (int)StringCchPrintfW(FileName, 0x104u, L"%s\\%s", (char *)this + 88, v9) >= 0 )
    {
      FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0, 0);
      v6 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        FileSize = GetFileSize(FileW, 0);
        dwCreationDisposition = *((_DWORD *)this + 5);
        *((_DWORD *)this + 16) = FileSize;
        *((_QWORD *)this + 7) = CreateMapping(v6, (__int16 *)this + 44, (__int64)v9, 0, dwCreationDisposition, 2u);
        CloseHandle(v6);
      }
    }
  }
}

```

## disassembly

```asm
0x1800248e4  mov     [rsp+arg_8], rbx
0x1800248e9  mov     [rsp+arg_10], rsi
0x1800248ee  push    rdi
0x1800248ef  sub     rsp, 470h
0x1800248f6  mov     rax, cs:__security_cookie
0x1800248fd  xor     rax, rsp
0x180024900  mov     [rsp+478h+var_18], rax
0x180024908  xor     edi, edi
0x18002490a  mov     rbx, rcx
0x18002490d  cmp     [rcx+38h], rdi
0x180024911  jz      short loc_180024938
0x180024913  mov     rcx, [rsp+478h+var_18]
0x18002491b  xor     rcx, rsp; StackCookie
0x18002491e  call    __security_check_cookie
0x180024923  lea     r11, [rsp+478h+var_8]
0x18002492b  mov     rbx, [r11+18h]
0x18002492f  mov     rsi, [r11+20h]
0x180024933  mov     rsp, r11
0x180024936  pop     rdi
0x180024937  retn
0x180024938  lea     rdx, [rsp+478h+var_438]; unsigned __int16 *
0x18002493d  call    ?_GetObjectName@CMemoryMappedCache@@AEAAJPEAGK@Z; CMemoryMappedCache::_GetObjectName(ushort *,ulong)
0x180024942  test    eax, eax
0x180024944  js      short loc_180024913
0x180024946  mov     r8d, [rbx+14h]
0x18002494a  lea     rsi, [rbx+58h]
0x18002494e  mov     rcx, rsi
0x180024951  lea     rdx, [rsp+478h+var_438]
0x180024956  mov     r9d, 4
0x18002495c  call    ?OpenMapping@@YAPEAXPEBG0W4CM_SCOPEFLAGS@@K@Z; OpenMapping(ushort const *,ushort const *,CM_SCOPEFLAGS,ulong)
0x180024961  mov     [rbx+38h], rax
0x180024965  test    rax, rax
0x180024968  jnz     short loc_180024913
0x18002496a  lea     rax, [rsp+478h+var_438]
0x18002496f  mov     r9, rsi
0x180024972  lea     r8, aSS; "%s\\%s"
0x180024979  mov     qword ptr [rsp+478h+dwCreationDisposition], rax
0x18002497e  mov     edx, 104h; unsigned __int64
0x180024983  lea     rcx, [rsp+478h+FileName]; unsigned __int16 *
0x18002498b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024990  test    eax, eax
0x180024992  js      loc_180024913
0x180024998  xor     r9d, r9d; lpSecurityAttributes
0x18002499b  mov     [rsp+478h+hTemplateFile], rdi; hTemplateFile
0x1800249a0  mov     [rsp+478h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800249a4  lea     rcx, [rsp+478h+FileName]; lpFileName
0x1800249ac  mov     edx, 80000000h; dwDesiredAccess
0x1800249b1  mov     [rsp+478h+dwCreationDisposition], 3; dwCreationDisposition
0x1800249b9  lea     r8d, [r9+1]; dwShareMode
0x1800249bd  call    cs:__imp_CreateFileW
0x1800249c3  mov     rdi, rax
0x1800249c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800249ca  jz      loc_180024913
0x1800249d0  xor     edx, edx; lpFileSizeHigh
0x1800249d2  mov     rcx, rax; hFile
0x1800249d5  call    cs:__imp_GetFileSize
0x1800249db  mov     ecx, [rbx+14h]
0x1800249de  lea     r8, [rsp+478h+var_438]
0x1800249e3  mov     [rsp+478h+dwFlagsAndAttributes], 2
0x1800249eb  xor     r9d, r9d
0x1800249ee  mov     [rsp+478h+dwCreationDisposition], ecx
0x1800249f2  mov     rdx, rsi
0x1800249f5  mov     rcx, rdi
0x1800249f8  mov     [rbx+40h], eax
0x1800249fb  call    ?CreateMapping@@YAPEAXPEAXPEBG1KW4CM_SCOPEFLAGS@@K@Z; CreateMapping(void *,ushort const *,ushort const *,ulong,CM_SCOPEFLAGS,ulong)
0x180024a00  mov     rcx, rdi; hObject
0x180024a03  mov     [rbx+38h], rax
0x180024a07  call    cs:__imp_CloseHandle
0x180024a0d  jmp     loc_180024913
```
