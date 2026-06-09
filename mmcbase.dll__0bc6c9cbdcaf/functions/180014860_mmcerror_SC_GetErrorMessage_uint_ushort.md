# mmcerror::SC::GetErrorMessage(uint,ushort *)

- ea: `0x180014860`
- end: `0x18001499d`
- name: `?GetErrorMessage@SC@mmcerror@@QEBAXIPEAG@Z`
- size: `317`
- prototype: `void(mmcerror::SC *__hidden this, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800147e0`

## callees

- `0x1800064b4`
- `0x180014860`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800148bc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800148d7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800148f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014977`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800148bc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800148d7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800148f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014977`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001490b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001490b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001495b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001495b`

## string_xrefs

- `0x180014902`: `msxml6.dll`

## pseudocode

```c
void __fastcall mmcerror::SC::GetErrorMessage(mmcerror::SC *this, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int64 nSize; // rsi
  DWORD StringW; // eax
  HMODULE v7; // rbx
  HMODULE ModuleHandleW; // rax
  DWORD v9; // r8d

  if ( !a3 )
    return;
  nSize = a2;
  if ( !a2 )
    return;
  *a3 = 0;
  if ( *(_DWORD *)this == 1 )
    goto LABEL_6;
  if ( *(_DWORD *)this != 2 )
  {
    if ( *(_DWORD *)this != 3 )
      return;
LABEL_6:
    if ( *((_DWORD *)this + 1) == -2147418113 )
    {
      StringW = LoadStringW(mmcerror::SC::s_hInst, 0x2EF0u, a3, a2);
    }
    else
    {
      v7 = 0;
      ModuleHandleW = GetModuleHandleW(L"msxml6.dll");
      v9 = *((unsigned __int16 *)this + 2);
      if ( ModuleHandleW )
        v7 = ModuleHandleW;
      if ( (*((_DWORD *)this + 1) & 0xFFFF0000) != 0x80070000 )
        v9 = *((_DWORD *)this + 1);
      StringW = FormatMessageW(ModuleHandleW != 0 ? 6656 : 4608, v7, v9, 0, a3, nSize, 0);
    }
    if ( !StringW && !LoadStringW(mmcerror::SC::s_hInst, 0x2EEEu, a3, nSize) )
      StringCchCopyW(a3, nSize, L"Unknown error");
    return;
  }
  if ( !LoadStringW(mmcerror::SC::s_hInst, *((_DWORD *)this + 1), a3, a2) )
    LoadStringW(mmcerror::SC::s_hInst, 0x2EEEu, a3, nSize);
}

```

## disassembly

```asm
0x180014860  test    r8, r8
0x180014863  jz      locret_18001499C
0x180014869  push    rbx
0x18001486a  push    rsi
0x18001486b  push    rdi
0x18001486c  push    r14
0x18001486e  sub     rsp, 48h
0x180014872  mov     esi, edx
0x180014874  mov     rdi, r8
0x180014877  mov     r14, rcx
0x18001487a  test    edx, edx
0x18001487c  jz      loc_180014993
0x180014882  xor     eax, eax
0x180014884  mov     [r8], ax
0x180014888  mov     r8d, [rcx]
0x18001488b  sub     r8d, 1
0x18001488f  jz      short loc_1800148A1
0x180014891  sub     r8d, 1
0x180014895  jz      short loc_1800148C7
0x180014897  cmp     r8d, 1
0x18001489b  jnz     loc_180014993
0x1800148a1  cmp     dword ptr [rcx+4], 8000FFFFh
0x1800148a8  jnz     short loc_180014902
0x1800148aa  mov     rcx, cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA; hInstance
0x1800148b1  mov     r9d, esi; cchBufferMax
0x1800148b4  mov     r8, rdi; lpBuffer
0x1800148b7  mov     edx, 2EF0h; uID
0x1800148bc  call    cs:__imp_LoadStringW
0x1800148c2  jmp     loc_180014961
0x1800148c7  mov     edx, [rcx+4]; uID
0x1800148ca  mov     r9d, esi; cchBufferMax
0x1800148cd  mov     rcx, cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA; hInstance
0x1800148d4  mov     r8, rdi; lpBuffer
0x1800148d7  call    cs:__imp_LoadStringW
0x1800148dd  test    eax, eax
0x1800148df  jnz     loc_180014993
0x1800148e5  mov     rcx, cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA; hInstance
0x1800148ec  mov     r9d, esi; cchBufferMax
0x1800148ef  mov     r8, rdi; lpBuffer
0x1800148f2  mov     edx, 2EEEh; uID
0x1800148f7  call    cs:__imp_LoadStringW
0x1800148fd  jmp     loc_180014993
0x180014902  lea     rcx, ModuleName; "msxml6.dll"
0x180014909  xor     ebx, ebx
0x18001490b  call    cs:__imp_GetModuleHandleW
0x180014911  mov     ecx, [r14+4]
0x180014915  test    rax, rax
0x180014918  movzx   r8d, word ptr [r14+4]
0x18001491d  cmovnz  rbx, rax
0x180014921  mov     [rsp+68h+Arguments], 0; Arguments
0x18001492a  and     ecx, 0FFFF0000h
0x180014930  mov     [rsp+68h+nSize], esi; nSize
0x180014934  cmp     ecx, 80070000h
0x18001493a  mov     [rsp+68h+lpBuffer], rdi; lpBuffer
0x18001493f  mov     rdx, rbx; lpSource
0x180014942  cmovnz  r8d, [r14+4]; dwMessageId
0x180014947  neg     rax
0x18001494a  sbb     ecx, ecx
0x18001494c  xor     r9d, r9d; dwLanguageId
0x18001494f  and     ecx, 800h
0x180014955  add     ecx, 1200h; dwFlags
0x18001495b  call    cs:__imp_FormatMessageW
0x180014961  test    eax, eax
0x180014963  jnz     short loc_180014993
0x180014965  mov     rcx, cs:?s_hInst@SC@mmcerror@@0PEAUHINSTANCE__@@EA; hInstance
0x18001496c  mov     r9d, esi; cchBufferMax
0x18001496f  mov     r8, rdi; lpBuffer
0x180014972  mov     edx, 2EEEh; uID
0x180014977  call    cs:__imp_LoadStringW
0x18001497d  test    eax, eax
0x18001497f  jnz     short loc_180014993
0x180014981  mov     rdx, rsi; unsigned __int64
0x180014984  lea     r8, aUnknownError; "Unknown error"
0x18001498b  mov     rcx, rdi; unsigned __int16 *
0x18001498e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014993  add     rsp, 48h
0x180014997  pop     r14
0x180014999  pop     rdi
0x18001499a  pop     rsi
0x18001499b  pop     rbx
0x18001499c  retn
```
