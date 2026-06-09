# CSimpStorage::SetElementTimes(ushort const *,_FILETIME const *,_FILETIME const *,_FILETIME const *)

- ea: `0x18004ea20`
- end: `0x18004ea76`
- name: `?SetElementTimes@CSimpStorage@@UEAAJPEBGPEBU_FILETIME@@11@Z`
- size: `86`
- prototype: `int(CSimpStorage *__hidden this, const unsigned __int16 *, const struct _FILETIME *, const struct _FILETIME *, const struct _FILETIME *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180016910`
- `0x180026bc4`
- `0x18004ea20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea5e`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18004ea54`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18004ea54`

## pseudocode

```c
__int64 __fastcall CSimpStorage::SetElementTimes(
        HANDLE *this,
        const unsigned __int16 *a2,
        const struct _FILETIME *a3,
        const struct _FILETIME *a4,
        const struct _FILETIME *lpLastWriteTime)
{
  int v5; // eax
  unsigned int v6; // ecx
  DWORD LastError; // eax

  if ( a2 )
  {
    v5 = CheckName(a2);
    v6 = -2147287039;
    if ( v5 < 0 )
      return (unsigned int)v5;
    return v6;
  }
  else if ( SetFileTime(this[8], a3, a4, lpLastWriteTime) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    return Win32ErrorToScode(LastError);
  }
}

```

## disassembly

```asm
0x18004ea20  sub     rsp, 28h
0x18004ea24  mov     rax, r9
0x18004ea27  mov     r10, r8
0x18004ea2a  test    rdx, rdx
0x18004ea2d  jz      short loc_18004EA45
0x18004ea2f  mov     rcx, rdx; unsigned __int16 *
0x18004ea32  call    ?CheckName@@YAJPEBG@Z; CheckName(ushort const *)
0x18004ea37  test    eax, eax
0x18004ea39  mov     ecx, 80030001h
0x18004ea3e  cmovs   ecx, eax
0x18004ea41  mov     eax, ecx
0x18004ea43  jmp     short loc_18004EA71
0x18004ea45  mov     r9, [rsp+28h+lpLastWriteTime]; lpLastWriteTime
0x18004ea4a  mov     r8, rax; lpLastAccessTime
0x18004ea4d  mov     rcx, [rcx+40h]; hFile
0x18004ea51  mov     rdx, r10; lpCreationTime
0x18004ea54  call    cs:__imp_SetFileTime
0x18004ea5a  test    eax, eax
0x18004ea5c  jnz     short loc_18004EA6F
0x18004ea5e  call    cs:__imp_GetLastError
0x18004ea64  mov     ecx, eax; unsigned int
0x18004ea66  add     rsp, 28h
0x18004ea6a  jmp     ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004ea6f  xor     eax, eax
0x18004ea71  add     rsp, 28h
0x18004ea75  retn
```
