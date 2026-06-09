# CFtpView::_OnGetHelpText(__int64,unsigned __int64)

- ea: `0x180026000`
- end: `0x1800260d1`
- name: `?_OnGetHelpText@CFtpView@@MEAAJ_J_K@Z`
- size: `209`
- prototype: `int(CFtpView *__hidden this, __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002240`
- `0x180009650`
- `0x180026000`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800260a2`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800260a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026060`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026079`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026079`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002604f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002604f`

## string_xrefs

- `0x180026059`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall CFtpView::_OnGetHelpText(CFtpView *this, unsigned __int16 *a2, unsigned __int64 a3)
{
  HINSTANCE v3; // rcx
  unsigned int v6; // edi
  HMODULE ModuleHandleW; // rax
  unsigned __int64 v8; // rbx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  v3 = g_hinst;
  *a2 = 0;
  Buffer[0] = 0;
  v6 = -2147467259;
  if ( LoadStringW(v3, (unsigned __int16)a3, Buffer, 260) )
  {
    ModuleHandleW = GetModuleHandleW(L"shell32.dll");
    if ( ModuleHandleW )
    {
      v8 = a3 >> 16;
      if ( GetProcAddress(ModuleHandleW, "WOWShellExecute") )
        StringCchCopyW(a2, (unsigned __int16)v8, Buffer);
      else
        SHUnicodeToAnsi(Buffer, (PSTR)a2, (unsigned __int16)v8);
      return 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180026000  mov     [rsp+arg_0], rbx
0x180026005  mov     [rsp+arg_18], rsi
0x18002600a  push    rdi
0x18002600b  sub     rsp, 240h
0x180026012  mov     rax, cs:__security_cookie
0x180026019  xor     rax, rsp
0x18002601c  mov     [rsp+248h+var_18], rax
0x180026024  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18002602b  xor     eax, eax
0x18002602d  mov     [rdx], ax
0x180026030  mov     rsi, rdx
0x180026033  movzx   edx, r8w; uID
0x180026037  mov     rbx, r8
0x18002603a  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x18002603f  mov     [rsp+248h+Buffer], ax
0x180026044  mov     r9d, 104h; cchBufferMax
0x18002604a  mov     edi, 80004005h
0x18002604f  call    cs:__imp_LoadStringW
0x180026055  test    eax, eax
0x180026057  jz      short loc_1800260AA
0x180026059  lea     rcx, pszExeFileName; "shell32.dll"
0x180026060  call    cs:__imp_GetModuleHandleW
0x180026066  test    rax, rax
0x180026069  jz      short loc_1800260AA
0x18002606b  lea     rdx, aWowshellexecut; "WOWShellExecute"
0x180026072  shr     rbx, 10h
0x180026076  mov     rcx, rax; hModule
0x180026079  call    cs:__imp_GetProcAddress
0x18002607f  test    rax, rax
0x180026082  jz      short loc_180026096
0x180026084  movzx   edx, bx; unsigned __int64
0x180026087  lea     r8, [rsp+248h+Buffer]; unsigned __int16 *
0x18002608c  mov     rcx, rsi; unsigned __int16 *
0x18002608f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026094  jmp     short loc_1800260A8
0x180026096  movzx   r8d, bx; cchBuf
0x18002609a  lea     rcx, [rsp+248h+Buffer]; pwszSrc
0x18002609f  mov     rdx, rsi; pszDst
0x1800260a2  call    cs:__imp_SHUnicodeToAnsi
0x1800260a8  xor     edi, edi
0x1800260aa  mov     eax, edi
0x1800260ac  mov     rcx, [rsp+248h+var_18]
0x1800260b4  xor     rcx, rsp; StackCookie
0x1800260b7  call    __security_check_cookie
0x1800260bc  lea     r11, [rsp+248h+var_8]
0x1800260c4  mov     rbx, [r11+10h]
0x1800260c8  mov     rsi, [r11+28h]
0x1800260cc  mov     rsp, r11
0x1800260cf  pop     rdi
0x1800260d0  retn
```
