# IsSpellCheckFacilityPresent(void)

- ea: `0x18027c810`
- end: `0x18027c8c5`
- name: `?IsSpellCheckFacilityPresent@@YA_NXZ`
- size: `181`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180274b8c`

## callees

- `0x18013ce80`
- `0x18013dce6`
- `0x180145168`
- `0x18027c810`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18027c849`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18027c849`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18027c898`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18027c898`

## string_xrefs

- `0x18027c878`: `%s\msspellcheckingfacility.dll`

## pseudocode

```c
bool IsSpellCheckFacilityPresent(void)
{
  char v0; // bl
  WCHAR Buffer[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR pszPath[264]; // [rsp+230h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  v0 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    memset_0(pszPath, 0, 0x208u);
    if ( (int)StringCchPrintfW(pszPath, 0x104u, L"%s\\msspellcheckingfacility.dll", Buffer) >= 0 )
      return PathFileExistsW(pszPath);
  }
  return v0;
}

```

## disassembly

```asm
0x18027c810  push    rbx
0x18027c812  sub     rsp, 450h
0x18027c819  mov     rax, cs:__security_cookie
0x18027c820  xor     rax, rsp
0x18027c823  mov     [rsp+458h+var_18], rax
0x18027c82b  xor     edx, edx; Val
0x18027c82d  lea     rcx, [rsp+458h+Buffer]; void *
0x18027c832  mov     r8d, 208h; Size
0x18027c838  call    memset_0
0x18027c83d  mov     edx, 104h; uSize
0x18027c842  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x18027c847  xor     bl, bl
0x18027c849  call    cs:__imp_GetSystemDirectoryW
0x18027c850  nop     dword ptr [rax+rax+00h]
0x18027c855  test    eax, eax
0x18027c857  jz      short loc_18027C8A9
0x18027c859  xor     edx, edx; Val
0x18027c85b  lea     rcx, [rsp+458h+pszPath]; void *
0x18027c863  mov     r8d, 208h; Size
0x18027c869  call    memset_0
0x18027c86e  lea     r9, [rsp+458h+Buffer]
0x18027c873  mov     edx, 104h; unsigned __int64
0x18027c878  lea     r8, aSMsspellchecki; "%s\\msspellcheckingfacility.dll"
0x18027c87f  lea     rcx, [rsp+458h+pszPath]; unsigned __int16 *
0x18027c887  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18027c88c  test    eax, eax
0x18027c88e  js      short loc_18027C8A9
0x18027c890  lea     rcx, [rsp+458h+pszPath]; pszPath
0x18027c898  call    cs:__imp_PathFileExistsW
0x18027c89f  nop     dword ptr [rax+rax+00h]
0x18027c8a4  test    eax, eax
0x18027c8a6  setnz   bl
0x18027c8a9  mov     al, bl
0x18027c8ab  mov     rcx, [rsp+458h+var_18]
0x18027c8b3  xor     rcx, rsp; StackCookie
0x18027c8b6  call    __security_check_cookie
0x18027c8bb  add     rsp, 450h
0x18027c8c2  pop     rbx
0x18027c8c3  retn
```
