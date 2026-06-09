# CAutoVerifierPlugin::GetOriginalBucket(HINSTANCE__ *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18002bf54`
- end: `0x18002c05a`
- name: `?GetOriginalBucket@CAutoVerifierPlugin@@AEAAJPEAUHINSTANCE__@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002c6f0`

## callees

- `0x180002890`
- `0x180009e04`
- `0x18002bf54`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bfd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bfd5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c034`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c034`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002bf97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002bf97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfaa`

## string_xrefs

- `0x18002bf90`: `werdiagcontroller.dll`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::GetOriginalBucket(__int64 a1, __int64 a2, _QWORD *a3)
{
  _WORD *v6; // rcx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  signed int LastError; // eax
  signed int v10; // ebx
  FARPROC ProcAddress; // rax
  unsigned __int64 v12; // r8
  _WORD v14[256]; // [rsp+40h] [rbp-238h] BYREF

  v6 = (_WORD *)*a3;
  a3[1] = *a3;
  *v6 = 0;
  Library = LoadLibraryExW(L"werdiagcontroller.dll", 0, 0);
  v8 = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "QueryOriginalBucket")) != 0 )
  {
    v10 = ((__int64 (__fastcall *)(_QWORD, __int64, _WORD *, __int64))ProcAddress)(*(_QWORD *)(a1 + 784), a2, v14, 256);
    if ( v10 >= 0 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v14[v12] );
      v10 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((__int64)a3, v14, v12) == 0
          ? 0x8007000E
          : 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147467259;
  }
  if ( v8 )
    FreeLibrary(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002bf54  push    rbx
0x18002bf56  push    rbp
0x18002bf57  push    rsi
0x18002bf58  push    rdi
0x18002bf59  push    r14
0x18002bf5b  sub     rsp, 250h
0x18002bf62  mov     rax, cs:__security_cookie
0x18002bf69  xor     rax, rsp
0x18002bf6c  mov     [rsp+278h+var_38], rax
0x18002bf74  mov     rsi, r8
0x18002bf77  mov     rbp, rdx
0x18002bf7a  mov     rbx, rcx
0x18002bf7d  mov     rcx, [r8]
0x18002bf80  mov     [r8+8], rcx
0x18002bf84  xor     r14d, r14d
0x18002bf87  mov     [rcx], r14w
0x18002bf8b  xor     r8d, r8d; dwFlags
0x18002bf8e  xor     edx, edx; hFile
0x18002bf90  lea     rcx, aWerdiagcontrol; "werdiagcontroller.dll"
0x18002bf97  call    cs:__imp_LoadLibraryExW
0x18002bf9d  mov     rdi, rax
0x18002bfa0  mov     [rsp+278h+var_248], rax
0x18002bfa5  test    rax, rax
0x18002bfa8  jnz     short loc_18002BFCB
0x18002bfaa  call    cs:__imp_GetLastError
0x18002bfb0  mov     ebx, eax
0x18002bfb2  test    eax, eax
0x18002bfb4  jle     short loc_18002BFBF
0x18002bfb6  movzx   ebx, ax
0x18002bfb9  or      ebx, 80070000h
0x18002bfbf  mov     eax, 80004005h
0x18002bfc4  test    ebx, ebx
0x18002bfc6  cmovns  ebx, eax
0x18002bfc9  jmp     short loc_18002C02C
0x18002bfcb  lea     rdx, aQueryoriginalb; "QueryOriginalBucket"
0x18002bfd2  mov     rcx, rdi; hModule
0x18002bfd5  call    cs:__imp_GetProcAddress
0x18002bfdb  test    rax, rax
0x18002bfde  jz      short loc_18002BFAA
0x18002bfe0  mov     r9d, 100h
0x18002bfe6  lea     r8, [rsp+278h+var_238]
0x18002bfeb  mov     rdx, rbp
0x18002bfee  mov     rcx, [rbx+310h]
0x18002bff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bffa  mov     ebx, eax
0x18002bffc  test    eax, eax
0x18002bffe  js      short loc_18002C02C
0x18002c000  lea     rax, [rsp+278h+var_238]
0x18002c005  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c009  inc     r8
0x18002c00c  cmp     [rax+r8*2], r14w
0x18002c011  jnz     short loc_18002C009
0x18002c013  lea     rdx, [rsp+278h+var_238]
0x18002c018  mov     rcx, rsi
0x18002c01b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002c020  neg     al
0x18002c022  sbb     ebx, ebx
0x18002c024  not     ebx
0x18002c026  and     ebx, 8007000Eh
0x18002c02c  test    rdi, rdi
0x18002c02f  jz      short loc_18002C03A
0x18002c031  mov     rcx, rdi; hLibModule
0x18002c034  call    cs:__imp_FreeLibrary
0x18002c03a  mov     eax, ebx
0x18002c03c  mov     rcx, [rsp+278h+var_38]
0x18002c044  xor     rcx, rsp; StackCookie
0x18002c047  call    __security_check_cookie
0x18002c04c  add     rsp, 250h
0x18002c053  pop     r14
0x18002c055  pop     rdi
0x18002c056  pop     rsi
0x18002c057  pop     rbp
0x18002c058  pop     rbx
0x18002c059  retn
```
