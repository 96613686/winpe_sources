# ConfigureTrans

- ea: `0x180004e80`
- end: `0x180005101`
- name: `ConfigureTrans`
- size: `641`
- prototype: `__int64 __fastcall(HWND hWnd, STRSAFE_LPCWSTR pszSrc, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180005c00`

## callees

- `0x1800017c0`
- `0x180002940`
- `0x180002e14`
- `0x180002e4c`
- `0x180004e80`
- `0x1800080c4`
- `0x18000a378`
- `0x180015010`

## import_xrefs

- `msvcrt!calloc` at `0x180004eac`
- `msvcrt!calloc` at `0x180004eac`
- `KERNEL32!SetThreadErrorMode` at `0x180004f44`
- `KERNEL32!SetThreadErrorMode` at `0x180004f68`
- `KERNEL32!SetThreadErrorMode` at `0x180004f44`
- `KERNEL32!SetThreadErrorMode` at `0x180004f68`
- `KERNEL32!LoadLibraryExW` at `0x180004f55`
- `KERNEL32!LoadLibraryExW` at `0x180004f55`
- `KERNEL32!FreeLibrary` at `0x1800050e0`
- `KERNEL32!FreeLibrary` at `0x1800050e0`
- `KERNEL32!GetProcAddress` at `0x180004fbd`
- `KERNEL32!GetProcAddress` at `0x180004fbd`

## string_xrefs

- `0x180004fb0`: `ConfigTranslator`

## pseudocode

```c
__int64 __fastcall ConfigureTrans(HWND hWnd, STRSAFE_LPCWSTR pszSrc, __int64 a3)
{
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  wchar_t *v9; // r14
  BOOL v10; // ebx
  HMODULE Library; // r12
  unsigned int v12; // ebx
  FARPROC ProcAddress; // rax
  __int16 v14; // cx
  __int64 v15; // rax
  __int64 v16; // r11
  __int64 v17; // rax
  DWORD OldMode[22]; // [rsp+30h] [rbp-58h] BYREF
  int v19; // [rsp+A8h] [rbp+20h] BYREF

  v19 = 0;
  v6 = (WCHAR *)calloc(0x410u, 1u);
  v7 = v6;
  if ( !v6 )
    return 0;
  v9 = v6 + 260;
  if ( !(unsigned int)SQLGetPrivateProfileStringCover(pszSrc, L"Setup", &SubKey, v6, 260, L"ODBCINST.INI") )
  {
    SetString(v7, 260);
    StringCchPrintfW(v9, 0x104u, v7, pszSrc);
    DoMessage(hWnd, v9, 0x40u);
    OFree(v7);
    return 0;
  }
  OldMode[0] = 0;
  v10 = SetThreadErrorMode(0x8001u, OldMode);
  Library = LoadLibraryExW(v7, 0, 8u);
  if ( v10 )
    SetThreadErrorMode(OldMode[0], 0);
  if ( Library )
  {
    v12 = 0;
    ProcAddress = GetProcAddress(Library, "ConfigTranslator");
    if ( ProcAddress )
    {
      v19 = **(_DWORD **)(a3 + 48);
      if ( !((unsigned int (__fastcall *)(HWND, int *))ProcAddress)(hWnd, &v19) )
      {
LABEL_22:
        FreeLibrary(Library);
        goto LABEL_23;
      }
      if ( (unsigned int)SQLGetPrivateProfileStringCover(pszSrc, L"Translator", &SubKey, v7, 260, L"ODBCINST.INI") )
      {
        StringCchCopyW(*(STRSAFE_LPWSTR *)a3, *(unsigned __int16 *)(a3 + 8), pszSrc);
        if ( *(_QWORD *)a3 )
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)(*(_QWORD *)a3 + 2 * v15) );
          v14 = v15;
        }
        else
        {
          v14 = 0;
        }
        **(_WORD **)(a3 + 16) = v14;
        StringCchCopyW(*(STRSAFE_LPWSTR *)(a3 + 24), *(unsigned __int16 *)(a3 + 32), v7);
        v17 = *(_QWORD *)(a3 + 24);
        if ( v17 )
        {
          do
            ++v16;
          while ( *(_WORD *)(v17 + 2 * v16) );
        }
        else
        {
          LOWORD(v16) = 0;
        }
        v12 = 1;
        **(_WORD **)(a3 + 40) = v16;
        **(_DWORD **)(a3 + 48) = v19;
        goto LABEL_22;
      }
    }
    SetString(v7, 260);
    StringCchPrintfW(v9, 0x104u, v7, pszSrc);
    DoMessage(hWnd, v9, 0x40u);
    goto LABEL_22;
  }
  SetString(v7, 260);
  StringCchPrintfW(v9, 0x104u, v7, pszSrc);
  DoMessage(hWnd, v9, 0x40u);
  v12 = 0;
LABEL_23:
  OFree(v7);
  return v12;
}

```

## disassembly

```asm
0x180004e80  mov     rax, rsp
0x180004e83  push    rbx
0x180004e84  push    rbp
0x180004e85  push    rsi
0x180004e86  push    rdi
0x180004e87  push    r12
0x180004e89  push    r13
0x180004e8b  push    r14
0x180004e8d  push    r15
0x180004e8f  sub     rsp, 48h
0x180004e93  xor     r13d, r13d
0x180004e96  mov     rbp, rdx
0x180004e99  mov     r15, rcx
0x180004e9c  mov     [rax+20h], r13d
0x180004ea0  mov     ecx, 410h; Count
0x180004ea5  mov     rsi, r8
0x180004ea8  lea     edx, [r13+1]; Size
0x180004eac  call    cs:__imp_calloc
0x180004eb2  mov     rdi, rax
0x180004eb5  test    rax, rax
0x180004eb8  jnz     short loc_180004EC1
0x180004eba  xor     eax, eax
0x180004ebc  jmp     loc_1800050F0
0x180004ec1  lea     r14, [rax+208h]
0x180004ec8  mov     ebx, 104h
0x180004ecd  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180004ed4  mov     r9, rdi
0x180004ed7  mov     [rsp+88h+var_60], rax
0x180004edc  lea     r8, SubKey
0x180004ee3  lea     rdx, aSetup; "Setup"
0x180004eea  mov     [rsp+88h+var_68], ebx
0x180004eee  mov     rcx, rbp
0x180004ef1  call    SQLGetPrivateProfileStringCover
0x180004ef6  test    eax, eax
0x180004ef8  jnz     short loc_180004F35
0x180004efa  mov     r8d, 551h
0x180004f00  mov     edx, ebx; cchBufferMax
0x180004f02  mov     rcx, rdi; lpBuffer
0x180004f05  call    SetString
0x180004f0a  mov     r9, rbp
0x180004f0d  mov     r8, rdi; pszFormat
0x180004f10  mov     edx, ebx; cchDest
0x180004f12  mov     rcx, r14; pszDest
0x180004f15  call    StringCchPrintfW
0x180004f1a  mov     r8d, 40h ; '@'; uType
0x180004f20  mov     rdx, r14; lpText
0x180004f23  mov     rcx, r15; hWnd
0x180004f26  call    DoMessage
0x180004f2b  mov     rcx, rdi
0x180004f2e  call    OFree
0x180004f33  jmp     short loc_180004EBA
0x180004f35  lea     rdx, [rsp+88h+OldMode]; lpOldMode
0x180004f3a  mov     [rsp+88h+OldMode], r13d
0x180004f3f  mov     ecx, 8001h; dwNewMode
0x180004f44  call    cs:__imp_SetThreadErrorMode
0x180004f4a  xor     edx, edx; hFile
0x180004f4c  mov     rcx, rdi; lpLibFileName
0x180004f4f  mov     ebx, eax
0x180004f51  lea     r8d, [rdx+8]; dwFlags
0x180004f55  call    cs:__imp_LoadLibraryExW
0x180004f5b  mov     r12, rax
0x180004f5e  test    ebx, ebx
0x180004f60  jz      short loc_180004F6E
0x180004f62  mov     ecx, [rsp+88h+OldMode]; dwNewMode
0x180004f66  xor     edx, edx; lpOldMode
0x180004f68  call    cs:__imp_SetThreadErrorMode
0x180004f6e  test    r12, r12
0x180004f71  jnz     short loc_180004FB0
0x180004f73  mov     ebx, 104h
0x180004f78  mov     r8d, 552h
0x180004f7e  mov     edx, ebx; cchBufferMax
0x180004f80  mov     rcx, rdi; lpBuffer
0x180004f83  call    SetString
0x180004f88  mov     r9, rbp
0x180004f8b  mov     r8, rdi; pszFormat
0x180004f8e  mov     edx, ebx; cchDest
0x180004f90  mov     rcx, r14; pszDest
0x180004f93  call    StringCchPrintfW
0x180004f98  lea     r8d, [r12+40h]; uType
0x180004f9d  mov     rdx, r14; lpText
0x180004fa0  mov     rcx, r15; hWnd
0x180004fa3  call    DoMessage
0x180004fa8  mov     ebx, r13d
0x180004fab  jmp     loc_1800050E6
0x180004fb0  lea     rdx, aConfigtranslat; "ConfigTranslator"
0x180004fb7  mov     rcx, r12; hModule
0x180004fba  mov     ebx, r13d
0x180004fbd  call    cs:__imp_GetProcAddress
0x180004fc3  mov     r8, rax
0x180004fc6  test    rax, rax
0x180004fc9  jnz     short loc_180004FD3
0x180004fcb  mov     r8d, 553h
0x180004fd1  jmp     short loc_180005032
0x180004fd3  mov     rax, [rsi+30h]
0x180004fd7  lea     rdx, [rsp+88h+arg_18]
0x180004fdf  mov     ecx, [rax]
0x180004fe1  mov     rax, r8
0x180004fe4  mov     [rsp+88h+arg_18], ecx
0x180004feb  mov     rcx, r15
0x180004fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff3  test    eax, eax
0x180004ff5  jz      loc_1800050DD
0x180004ffb  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180005002  mov     r9, rdi
0x180005005  mov     [rsp+88h+var_60], rax
0x18000500a  lea     r8, SubKey
0x180005011  lea     rdx, aTranslator; "Translator"
0x180005018  mov     [rsp+88h+var_68], 104h
0x180005020  mov     rcx, rbp
0x180005023  call    SQLGetPrivateProfileStringCover
0x180005028  test    eax, eax
0x18000502a  jnz     short loc_180005064
0x18000502c  mov     r8d, 554h
0x180005032  mov     esi, 104h
0x180005037  mov     rcx, rdi; lpBuffer
0x18000503a  mov     edx, esi; cchBufferMax
0x18000503c  call    SetString
0x180005041  mov     r9, rbp
0x180005044  mov     r8, rdi; pszFormat
0x180005047  mov     edx, esi; cchDest
0x180005049  mov     rcx, r14; pszDest
0x18000504c  call    StringCchPrintfW
0x180005051  mov     r8d, 40h ; '@'; uType
0x180005057  mov     rdx, r14; lpText
0x18000505a  mov     rcx, r15; hWnd
0x18000505d  call    DoMessage
0x180005062  jmp     short loc_1800050DD
0x180005064  movzx   edx, word ptr [rsi+8]; cchDest
0x180005068  mov     r8, rbp; pszSrc
0x18000506b  mov     rcx, [rsi]; pszDest
0x18000506e  call    StringCchCopyW
0x180005073  mov     rcx, [rsi]
0x180005076  or      r11, 0FFFFFFFFFFFFFFFFh
0x18000507a  test    rcx, rcx
0x18000507d  jnz     short loc_180005084
0x18000507f  mov     ecx, r13d
0x180005082  jmp     short loc_180005094
0x180005084  mov     rax, r11
0x180005087  inc     rax
0x18000508a  cmp     [rcx+rax*2], r13w
0x18000508f  jnz     short loc_180005087
0x180005091  movzx   ecx, ax
0x180005094  mov     rax, [rsi+10h]
0x180005098  mov     r8, rdi; pszSrc
0x18000509b  mov     [rax], cx
0x18000509e  movzx   edx, word ptr [rsi+20h]; cchDest
0x1800050a2  mov     rcx, [rsi+18h]; pszDest
0x1800050a6  call    StringCchCopyW
0x1800050ab  mov     rax, [rsi+18h]
0x1800050af  test    rax, rax
0x1800050b2  jnz     short loc_1800050B9
0x1800050b4  mov     r11d, r13d
0x1800050b7  jmp     short loc_1800050C3
0x1800050b9  inc     r11
0x1800050bc  cmp     [rax+r11*2], r13w
0x1800050c1  jnz     short loc_1800050B9
0x1800050c3  mov     rax, [rsi+28h]
0x1800050c7  mov     ebx, 1
0x1800050cc  mov     [rax], r11w
0x1800050d0  mov     rcx, [rsi+30h]
0x1800050d4  mov     eax, [rsp+88h+arg_18]
0x1800050db  mov     [rcx], eax
0x1800050dd  mov     rcx, r12; hLibModule
0x1800050e0  call    cs:__imp_FreeLibrary
0x1800050e6  mov     rcx, rdi
0x1800050e9  call    OFree
0x1800050ee  mov     eax, ebx
0x1800050f0  add     rsp, 48h
0x1800050f4  pop     r15
0x1800050f6  pop     r14
0x1800050f8  pop     r13
0x1800050fa  pop     r12
0x1800050fc  pop     rdi
0x1800050fd  pop     rsi
0x1800050fe  pop     rbp
0x1800050ff  pop     rbx
0x180005100  retn
```
