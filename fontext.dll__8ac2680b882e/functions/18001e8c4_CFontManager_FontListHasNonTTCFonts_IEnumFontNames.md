# CFontManager::_FontListHasNonTTCFonts(IEnumFontNames *)

- ea: `0x18001e8c4`
- end: `0x18001e95d`
- name: `?_FontListHasNonTTCFonts@CFontManager@@AEAAHPEAUIEnumFontNames@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(CFontManager *__hidden this, struct IEnumFontNames *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001dcc8`

## callees

- `0x18001e8c4`
- `0x180032010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001e922`
- `msvcrt!_wcsicmp` at `0x18001e922`
- `SHLWAPI!PathFindExtensionW` at `0x18001e912`
- `SHLWAPI!PathFindExtensionW` at `0x18001e912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e937`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e937`

## pseudocode

```c
__int64 __fastcall CFontManager::_FontListHasNonTTCFonts(const WCHAR *this, struct IEnumFontNames *a2)
{
  __int64 v2; // rax
  unsigned int v3; // edi
  const wchar_t *ExtensionW; // rax
  LPCWSTR pszPath; // [rsp+30h] [rbp+8h] BYREF

  pszPath = this;
  v2 = *(_QWORD *)a2;
  v3 = 0;
  pszPath = 0;
  (*(void (__fastcall **)(struct IEnumFontNames *))(v2 + 32))(a2);
  do
  {
    if ( (*(int (__fastcall **)(struct IEnumFontNames *, LPCWSTR *))(*(_QWORD *)a2 + 24LL))(a2, &pszPath) < 0
      || !pszPath )
    {
      break;
    }
    ExtensionW = PathFindExtensionW(pszPath);
    if ( _wcsicmp(ExtensionW, L".ttc") )
      v3 = 1;
    CoTaskMemFree((LPVOID)pszPath);
  }
  while ( !v3 );
  (*(void (__fastcall **)(struct IEnumFontNames *))(*(_QWORD *)a2 + 32LL))(a2);
  return v3;
}

```

## disassembly

```asm
0x18001e8c4  mov     [rsp+arg_8], rbx
0x18001e8c9  mov     [rsp+pszPath], rcx
0x18001e8ce  push    rdi
0x18001e8cf  sub     rsp, 20h
0x18001e8d3  mov     rax, [rdx]
0x18001e8d6  xor     edi, edi
0x18001e8d8  mov     rcx, rdx
0x18001e8db  mov     [rsp+28h+pszPath], 0
0x18001e8e4  mov     rbx, rdx
0x18001e8e7  mov     rax, [rax+20h]
0x18001e8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8f0  mov     rax, [rbx]
0x18001e8f3  lea     rdx, [rsp+28h+pszPath]
0x18001e8f8  mov     rcx, rbx
0x18001e8fb  mov     rax, [rax+18h]
0x18001e8ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e904  test    eax, eax
0x18001e906  js      short loc_18001E941
0x18001e908  mov     rcx, [rsp+28h+pszPath]; pszPath
0x18001e90d  test    rcx, rcx
0x18001e910  jz      short loc_18001E941
0x18001e912  call    cs:__imp_PathFindExtensionW
0x18001e918  mov     rcx, rax; String1
0x18001e91b  lea     rdx, aTtc; ".ttc"
0x18001e922  call    cs:__imp__wcsicmp
0x18001e928  test    eax, eax
0x18001e92a  mov     ecx, 1
0x18001e92f  cmovnz  edi, ecx
0x18001e932  mov     rcx, [rsp+28h+pszPath]; pv
0x18001e937  call    cs:__imp_CoTaskMemFree
0x18001e93d  test    edi, edi
0x18001e93f  jz      short loc_18001E8F0
0x18001e941  mov     rcx, [rbx]
0x18001e944  mov     rax, [rcx+20h]
0x18001e948  mov     rcx, rbx
0x18001e94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e950  mov     rbx, [rsp+28h+arg_8]
0x18001e955  mov     eax, edi
0x18001e957  add     rsp, 20h
0x18001e95b  pop     rdi
0x18001e95c  retn
```
