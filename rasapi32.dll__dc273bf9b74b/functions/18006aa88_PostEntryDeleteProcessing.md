# PostEntryDeleteProcessing

- ea: `0x18006aa88`
- end: `0x18006ae5b`
- name: `PostEntryDeleteProcessing`
- size: `979`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a7f48`

## callees

- `0x18000efe4`
- `0x180036250`
- `0x18004e580`
- `0x18004e984`
- `0x18006aa88`
- `0x18007e5f0`
- `0x1800c7c64`
- `0x1800d023c`
- `0x1800ded06`
- `0x1800ded2a`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006ab85`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006abde`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006ab85`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006abde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ab93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006abec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ab93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006abec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ac33`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006ac33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ac19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ac19`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006ac01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006ac01`
- `rasman!RasSetKey` at `0x18006acb2`
- `rasman!RasSetKey` at `0x18006acb2`

## string_xrefs

- `0x18006ac0f`: `HNetDeleteRasConnection`

## pseudocode

```c
__int64 __fastcall PostEntryDeleteProcessing(wchar_t *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  HKEY v8; // rsi
  int v9; // eax
  HKEY v10; // rsi
  HMODULE Library; // rax
  HMODULE v12; // rsi
  FARPROC ProcAddress; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  _QWORD *v16; // rcx
  _WORD *v17; // r8
  unsigned int v18; // eax
  wchar_t *v19; // rcx
  unsigned int active; // eax
  unsigned int TriggerProfile; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String1[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 1112, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, a1);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1113, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids);
  }
  v6 = 0;
  memset_0(String1, 0, 0x202u);
  hKey[0] = 0;
  if ( !(unsigned int)RasGetDefIntConnName(0, String1, hKey) )
  {
    v7 = wcsncmp_0(String1, a1, 0x101u);
    v8 = hKey[0];
    if ( !v7 )
      RegDeleteValueW(hKey[0], L"DefaultInternet");
    if ( v8 )
      RegCloseKey(v8);
  }
  if ( !*(_DWORD *)(a2 + 8) && !(unsigned int)RasGetDefIntConnName(1, String1, hKey) )
  {
    v9 = wcsncmp_0(String1, a1, 0x101u);
    v10 = hKey[0];
    if ( !v9 )
      RegDeleteValueW(hKey[0], L"DefaultInternet");
    if ( v10 )
      RegCloseKey(v10);
  }
  Library = LoadLibraryExW(L"hnetcfg", 0, 0x800u);
  v12 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "HNetDeleteRasConnection");
    if ( ProcAddress )
      ((void (__fastcall *)(_QWORD))ProcAddress)(*(_QWORD *)(a3 + 464));
    FreeLibrary(v12);
  }
  if ( (*(_DWORD *)(a2 + 32) & 0x400) != 0 )
    goto LABEL_36;
  v14 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_pRasSetDialParams)(
          *(unsigned int *)(a3 + 456),
          3221225472LL,
          0,
          0);
  if ( v14
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1114, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v14);
  }
  v15 = RasSetKey(*(_QWORD *)(a3 + 464), 128, 0, 0);
  v6 = v15;
  if ( !v15 )
    goto LABEL_36;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1115, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v15);
LABEL_36:
    v16 = WPP_GLOBAL_Control;
  }
  v17 = *(_WORD **)(a3 + 448);
  if ( v17 && *v17 )
  {
    v18 = DwCustomDeleteEntryNotify(*(PCNZWCH *)a2);
    if ( v18 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_45;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1116, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v18);
    }
    v16 = WPP_GLOBAL_Control;
LABEL_45:
    v6 = 0;
  }
  if ( *(_DWORD *)(a3 + 704) )
  {
    v19 = *(wchar_t **)a2;
    LODWORD(hKey[0]) = 0;
    active = IsActiveAutoTriggerConnection(v19, a1);
    if ( active )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_53:
        if ( LODWORD(hKey[0]) )
        {
          TriggerProfile = RasSelectNextTriggerProfile();
          if ( TriggerProfile )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_60;
            }
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              1118,
              WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids,
              TriggerProfile);
          }
          v16 = WPP_GLOBAL_Control;
        }
LABEL_60:
        v6 = 0;
        goto LABEL_61;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1117, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, active);
    }
    v16 = WPP_GLOBAL_Control;
    goto LABEL_53;
  }
LABEL_61:
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x800) != 0 && *((_BYTE *)v16 + 25) >= 6u )
    WPP_SF_d(v16[2], 1119, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18006aa88  push    rbp
0x18006aa8a  push    rbx
0x18006aa8b  push    rsi
0x18006aa8c  push    rdi
0x18006aa8d  push    r12
0x18006aa8f  push    r14
0x18006aa91  push    r15
0x18006aa93  lea     rbp, [rsp-160h]
0x18006aa9b  sub     rsp, 260h
0x18006aaa2  mov     rax, cs:__security_cookie
0x18006aaa9  xor     rax, rsp
0x18006aaac  mov     [rbp+190h+var_40], rax
0x18006aab3  mov     r15, r8
0x18006aab6  mov     r12, rdx
0x18006aab9  mov     r14, rcx
0x18006aabc  mov     eax, 800h
0x18006aac1  test    rcx, rcx
0x18006aac4  jz      short loc_18006AAFE
0x18006aac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aacd  lea     rdi, WPP_GLOBAL_Control
0x18006aad4  cmp     rcx, rdi
0x18006aad7  jz      short loc_18006AB31
0x18006aad9  test    [rcx+1Ch], eax
0x18006aadc  jz      short loc_18006AB31
0x18006aade  cmp     byte ptr [rcx+19h], 6
0x18006aae2  jb      short loc_18006AB31
0x18006aae4  mov     rcx, [rcx+10h]
0x18006aae8  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006aaef  mov     edx, 458h
0x18006aaf4  mov     r9, r14
0x18006aaf7  call    WPP_SF_S
0x18006aafc  jmp     short loc_18006AB31
0x18006aafe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ab05  lea     rdi, WPP_GLOBAL_Control
0x18006ab0c  cmp     rcx, rdi
0x18006ab0f  jz      short loc_18006AB31
0x18006ab11  test    [rcx+1Ch], eax
0x18006ab14  jz      short loc_18006AB31
0x18006ab16  cmp     byte ptr [rcx+19h], 6
0x18006ab1a  jb      short loc_18006AB31
0x18006ab1c  mov     rcx, [rcx+10h]
0x18006ab20  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006ab27  mov     edx, 459h
0x18006ab2c  call    WPP_SF_
0x18006ab31  xor     edx, edx; Val
0x18006ab33  lea     rcx, [rsp+290h+String1]; void *
0x18006ab38  mov     r8d, 202h; Size
0x18006ab3e  xor     ebx, ebx
0x18006ab40  call    memset_0
0x18006ab45  lea     r8, [rsp+290h+hKey]
0x18006ab4a  mov     [rsp+290h+hKey], rbx
0x18006ab4f  lea     rdx, [rsp+290h+String1]
0x18006ab54  xor     ecx, ecx
0x18006ab56  call    RasGetDefIntConnName
0x18006ab5b  test    eax, eax
0x18006ab5d  jnz     short loc_18006AB99
0x18006ab5f  mov     r8d, 101h; MaxCount
0x18006ab65  lea     rcx, [rsp+290h+String1]; String1
0x18006ab6a  mov     rdx, r14; String2
0x18006ab6d  call    wcsncmp_0
0x18006ab72  mov     rsi, [rsp+290h+hKey]
0x18006ab77  test    eax, eax
0x18006ab79  jnz     short loc_18006AB8B
0x18006ab7b  lea     rdx, aDefaultinterne; "DefaultInternet"
0x18006ab82  mov     rcx, rsi; hKey
0x18006ab85  call    cs:__imp_RegDeleteValueW
0x18006ab8b  test    rsi, rsi
0x18006ab8e  jz      short loc_18006AB99
0x18006ab90  mov     rcx, rsi; hKey
0x18006ab93  call    cs:__imp_RegCloseKey
0x18006ab99  cmp     [r12+8], ebx
0x18006ab9e  jnz     short loc_18006ABF2
0x18006aba0  lea     r8, [rsp+290h+hKey]
0x18006aba5  mov     ecx, 1
0x18006abaa  lea     rdx, [rsp+290h+String1]
0x18006abaf  call    RasGetDefIntConnName
0x18006abb4  test    eax, eax
0x18006abb6  jnz     short loc_18006ABF2
0x18006abb8  mov     r8d, 101h; MaxCount
0x18006abbe  lea     rcx, [rsp+290h+String1]; String1
0x18006abc3  mov     rdx, r14; String2
0x18006abc6  call    wcsncmp_0
0x18006abcb  mov     rsi, [rsp+290h+hKey]
0x18006abd0  test    eax, eax
0x18006abd2  jnz     short loc_18006ABE4
0x18006abd4  lea     rdx, aDefaultinterne; "DefaultInternet"
0x18006abdb  mov     rcx, rsi; hKey
0x18006abde  call    cs:__imp_RegDeleteValueW
0x18006abe4  test    rsi, rsi
0x18006abe7  jz      short loc_18006ABF2
0x18006abe9  mov     rcx, rsi; hKey
0x18006abec  call    cs:__imp_RegCloseKey
0x18006abf2  xor     edx, edx; hFile
0x18006abf4  lea     rcx, aHnetcfg; "hnetcfg"
0x18006abfb  mov     r8d, 800h; dwFlags
0x18006ac01  call    cs:__imp_LoadLibraryExW
0x18006ac07  mov     rsi, rax
0x18006ac0a  test    rax, rax
0x18006ac0d  jz      short loc_18006AC39
0x18006ac0f  lea     rdx, aHnetdeleterasc; "HNetDeleteRasConnection"
0x18006ac16  mov     rcx, rax; hModule
0x18006ac19  call    cs:__imp_GetProcAddress
0x18006ac1f  test    rax, rax
0x18006ac22  jz      short loc_18006AC30
0x18006ac24  mov     rcx, [r15+1D0h]
0x18006ac2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac30  mov     rcx, rsi; hLibModule
0x18006ac33  call    cs:__imp_FreeLibrary
0x18006ac39  test    dword ptr [r12+20h], 400h
0x18006ac42  mov     sil, 2
0x18006ac45  jnz     loc_18006ACF1
0x18006ac4b  mov     ecx, [r15+1C8h]
0x18006ac52  xor     r9d, r9d
0x18006ac55  mov     rax, cs:g_pRasSetDialParams
0x18006ac5c  xor     r8d, r8d
0x18006ac5f  mov     edx, 0C0000000h
0x18006ac64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac69  test    eax, eax
0x18006ac6b  jz      short loc_18006ACA0
0x18006ac6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ac74  cmp     rcx, rdi
0x18006ac77  jz      short loc_18006ACA0
0x18006ac79  test    dword ptr [rcx+1Ch], 800h
0x18006ac80  jz      short loc_18006ACA0
0x18006ac82  cmp     [rcx+19h], sil
0x18006ac86  jb      short loc_18006ACA0
0x18006ac88  mov     rcx, [rcx+10h]
0x18006ac8c  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006ac93  mov     edx, 45Ah
0x18006ac98  mov     r9d, eax
0x18006ac9b  call    WPP_SF_d
0x18006aca0  mov     rcx, [r15+1D0h]
0x18006aca7  xor     r9d, r9d
0x18006acaa  xor     r8d, r8d
0x18006acad  mov     edx, 80h
0x18006acb2  call    cs:__imp_RasSetKey
0x18006acb8  mov     ebx, eax
0x18006acba  test    eax, eax
0x18006acbc  jz      short loc_18006ACF1
0x18006acbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006acc5  cmp     rcx, rdi
0x18006acc8  jz      short loc_18006ACF8
0x18006acca  test    dword ptr [rcx+1Ch], 800h
0x18006acd1  jz      short loc_18006ACF8
0x18006acd3  cmp     [rcx+19h], sil
0x18006acd7  jb      short loc_18006ACF8
0x18006acd9  mov     rcx, [rcx+10h]
0x18006acdd  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006ace4  mov     edx, 45Bh
0x18006ace9  mov     r9d, eax
0x18006acec  call    WPP_SF_d
0x18006acf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006acf8  mov     r8, [r15+1C0h]
0x18006acff  test    r8, r8
0x18006ad02  jz      short loc_18006AD58
0x18006ad04  xor     eax, eax
0x18006ad06  cmp     ax, [r8]
0x18006ad0a  jz      short loc_18006AD58
0x18006ad0c  mov     rcx, [r12]
0x18006ad10  mov     rdx, r14
0x18006ad13  call    DwCustomDeleteEntryNotify
0x18006ad18  test    eax, eax
0x18006ad1a  jz      short loc_18006AD4F
0x18006ad1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad23  cmp     rcx, rdi
0x18006ad26  jz      short loc_18006AD56
0x18006ad28  test    dword ptr [rcx+1Ch], 800h
0x18006ad2f  jz      short loc_18006AD56
0x18006ad31  cmp     [rcx+19h], sil
0x18006ad35  jb      short loc_18006AD56
0x18006ad37  mov     rcx, [rcx+10h]
0x18006ad3b  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006ad42  mov     edx, 45Ch
0x18006ad47  mov     r9d, eax
0x18006ad4a  call    WPP_SF_d
0x18006ad4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad56  xor     ebx, ebx
0x18006ad58  cmp     dword ptr [r15+2C0h], 0
0x18006ad60  jz      loc_18006AE0C
0x18006ad66  mov     rcx, [r12]; String1
0x18006ad6a  lea     r9, [rsp+290h+hKey]
0x18006ad6f  xor     r8d, r8d
0x18006ad72  mov     dword ptr [rsp+290h+hKey], 0
0x18006ad7a  mov     rdx, r14; wchar_t *
0x18006ad7d  call    IsActiveAutoTriggerConnection
0x18006ad82  test    eax, eax
0x18006ad84  jz      short loc_18006ADB9
0x18006ad86  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ad8d  cmp     rcx, rdi
0x18006ad90  jz      short loc_18006ADC0
0x18006ad92  test    dword ptr [rcx+1Ch], 800h
0x18006ad99  jz      short loc_18006ADC0
0x18006ad9b  cmp     [rcx+19h], sil
0x18006ad9f  jb      short loc_18006ADC0
0x18006ada1  mov     rcx, [rcx+10h]
0x18006ada5  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006adac  mov     edx, 45Dh
0x18006adb1  mov     r9d, eax
0x18006adb4  call    WPP_SF_d
0x18006adb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006adc0  cmp     dword ptr [rsp+290h+hKey], 0
0x18006adc5  jz      short loc_18006AE0A
0x18006adc7  call    RasSelectNextTriggerProfile
0x18006adcc  test    eax, eax
0x18006adce  jz      short loc_18006AE03
0x18006add0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006add7  cmp     rcx, rdi
0x18006adda  jz      short loc_18006AE0A
0x18006addc  test    dword ptr [rcx+1Ch], 800h
0x18006ade3  jz      short loc_18006AE0A
0x18006ade5  cmp     [rcx+19h], sil
0x18006ade9  jb      short loc_18006AE0A
0x18006adeb  mov     rcx, [rcx+10h]
0x18006adef  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006adf6  mov     edx, 45Eh
0x18006adfb  mov     r9d, eax
0x18006adfe  call    WPP_SF_d
0x18006ae03  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ae0a  xor     ebx, ebx
0x18006ae0c  cmp     rcx, rdi
0x18006ae0f  jz      short loc_18006AE38
0x18006ae11  test    dword ptr [rcx+1Ch], 800h
0x18006ae18  jz      short loc_18006AE38
0x18006ae1a  cmp     byte ptr [rcx+19h], 6
0x18006ae1e  jb      short loc_18006AE38
0x18006ae20  mov     rcx, [rcx+10h]
0x18006ae24  lea     r8, WPP_74ed4adbfb8e37cfed34d82a2c9e1e80_Traceguids
0x18006ae2b  mov     edx, 45Fh
0x18006ae30  mov     r9d, ebx
0x18006ae33  call    WPP_SF_d
0x18006ae38  mov     eax, ebx
0x18006ae3a  mov     rcx, [rbp+190h+var_40]
0x18006ae41  xor     rcx, rsp; StackCookie
0x18006ae44  call    __security_check_cookie
0x18006ae49  add     rsp, 260h
0x18006ae50  pop     r15
0x18006ae52  pop     r14
0x18006ae54  pop     r12
0x18006ae56  pop     rdi
0x18006ae57  pop     rsi
0x18006ae58  pop     rbx
0x18006ae59  pop     rbp
0x18006ae5a  retn
```
