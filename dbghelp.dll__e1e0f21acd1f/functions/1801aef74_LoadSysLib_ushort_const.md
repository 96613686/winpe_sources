# LoadSysLib(ushort const *)

- ea: `0x1801aef74`
- end: `0x1801af02a`
- name: `?LoadSysLib@@YAPEAUHINSTANCE__@@PEBG@Z`
- size: `182`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1801a2834`
- `0x1801aa1c4`

## callees

- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x1801aef74`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801aefee`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801af003`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801aefee`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801af003`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801aefa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801aefa5`

## pseudocode

```c
HINSTANCE __fastcall LoadSysLib(const unsigned __int16 *a1)
{
  unsigned __int64 v2; // rdx
  HINSTANCE result; // rax
  WCHAR LibFileName[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR Buffer[264]; // [rsp+230h] [rbp-228h] BYREF

  if ( !GetSystemDirectoryW(Buffer, 0x105u) )
    return LoadLibraryExW(LibFileName, 0, 0);
  wcscpy_s_ex(LibFileName, 0x105u, Buffer);
  if ( !(unsigned int)BackslashCat(LibFileName, 261) )
    return 0;
  wcscat_s_ex(LibFileName, v2, a1);
  result = LoadLibraryExW(LibFileName, 0, 0);
  if ( !result )
    return LoadLibraryExW(LibFileName, 0, 0);
  return result;
}

```

## disassembly

```asm
0x1801aef74  mov     [rsp+arg_8], rbx
0x1801aef79  push    rdi
0x1801aef7a  sub     rsp, 450h
0x1801aef81  mov     rax, cs:__security_cookie
0x1801aef88  xor     rax, rsp
0x1801aef8b  mov     [rsp+458h+var_18], rax
0x1801aef93  mov     rbx, rcx
0x1801aef96  mov     edi, 105h
0x1801aef9b  mov     edx, edi; uSize
0x1801aef9d  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x1801aefa5  call    cs:__imp_GetSystemDirectoryW
0x1801aefab  test    eax, eax
0x1801aefad  jz      short loc_1801AEFF9
0x1801aefaf  lea     r8, [rsp+458h+Buffer]; unsigned __int16 *
0x1801aefb7  mov     edx, edi; unsigned __int64
0x1801aefb9  lea     rcx, [rsp+458h+LibFileName]; unsigned __int16 *
0x1801aefbe  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801aefc3  mov     edx, edi
0x1801aefc5  lea     rcx, [rsp+458h+LibFileName]
0x1801aefca  call    BackslashCat
0x1801aefcf  test    eax, eax
0x1801aefd1  jnz     short loc_1801AEFD7
0x1801aefd3  xor     eax, eax
0x1801aefd5  jmp     short loc_1801AF009
0x1801aefd7  mov     r8, rbx; unsigned __int16 *
0x1801aefda  lea     rcx, [rsp+458h+LibFileName]; unsigned __int16 *
0x1801aefdf  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801aefe4  xor     r8d, r8d; dwFlags
0x1801aefe7  lea     rcx, [rsp+458h+LibFileName]; lpLibFileName
0x1801aefec  xor     edx, edx; hFile
0x1801aefee  call    cs:__imp_LoadLibraryExW
0x1801aeff4  test    rax, rax
0x1801aeff7  jnz     short loc_1801AF009
0x1801aeff9  xor     r8d, r8d; dwFlags
0x1801aeffc  lea     rcx, [rsp+458h+LibFileName]; lpLibFileName
0x1801af001  xor     edx, edx; hFile
0x1801af003  call    cs:__imp_LoadLibraryExW
0x1801af009  mov     rcx, [rsp+458h+var_18]
0x1801af011  xor     rcx, rsp; StackCookie
0x1801af014  call    __security_check_cookie
0x1801af019  mov     rbx, [rsp+458h+arg_8]
0x1801af021  add     rsp, 450h
0x1801af028  pop     rdi
0x1801af029  retn
```
