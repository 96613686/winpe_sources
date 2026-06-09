# PSetupCopyDriverPackageFiles

- ea: `0x1800310a0`
- end: `0x180031359`
- name: `PSetupCopyDriverPackageFiles`
- size: `697`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18002a30c`

## callees

- `0x18000b200`
- `0x18000c368`
- `0x18002ffb4`
- `0x180030918`
- `0x180030958`
- `0x180030c60`
- `0x1800310a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800312e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800312e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031268`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180031299`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180031300`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180031299`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180031300`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1800311cb`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180031209`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180031236`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1800311cb`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180031209`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180031236`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003130e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003130e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800311e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800311e3`
- `SETUPAPI!pSetupSetGlobalFlags` at `0x180031275`
- `SETUPAPI!pSetupSetGlobalFlags` at `0x1800312d4`
- `SETUPAPI!pSetupSetGlobalFlags` at `0x180031275`
- `SETUPAPI!pSetupSetGlobalFlags` at `0x1800312d4`
- `SETUPAPI!pSetupGetGlobalFlags` at `0x180031255`
- `SETUPAPI!pSetupGetGlobalFlags` at `0x180031255`
- `SETUPAPI!SetupSetNonInteractiveMode` at `0x18003112e`
- `SETUPAPI!SetupSetNonInteractiveMode` at `0x18003132b`
- `SETUPAPI!SetupSetNonInteractiveMode` at `0x18003112e`
- `SETUPAPI!SetupSetNonInteractiveMode` at `0x18003132b`

## pseudocode

```c
__int64 __fastcall PSetupCopyDriverPackageFiles(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 a3,
        char a4,
        HWND OwnerWindow)
{
  ULONG v5; // esi
  unsigned int v6; // r14d
  struct _STRING_LIST *v7; // rdi
  BOOL v12; // ecx
  int v13; // edx
  int HaveMultiLanguageBinaries; // ebx
  int SupportedCultureNamesInInf; // eax
  WCHAR *v16; // rsi
  NCoreLibrary *v17; // rcx
  WCHAR *v18; // rax
  NCoreLibrary *v19; // rcx
  struct _STRING_LIST *v20; // r14
  int v21; // r12d
  unsigned int v22; // r13d
  __int64 v23; // rcx
  BOOL NonInteractiveFlag; // [rsp+30h] [rbp-30h]
  ULONG pulNumLanguages; // [rsp+34h] [rbp-2Ch] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+38h] [rbp-28h] BYREF
  ULONG v27; // [rsp+3Ch] [rbp-24h] BYREF
  unsigned int GlobalFlags; // [rsp+40h] [rbp-20h]
  struct _STRING_LIST *v29; // [rsp+48h] [rbp-18h] BYREF
  PCZZWSTR pwszLanguagesBuffer; // [rsp+50h] [rbp-10h]

  v5 = 0;
  v6 = a3;
  v7 = 0;
  pcchLanguagesBuffer = 0;
  v29 = 0;
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
    return 2147943660LL;
  v12 = 0;
  NonInteractiveFlag = 0;
  if ( !a1 || !a2 || v6 > 0xC || (v13 = 4673, !_bittest(&v13, v6)) )
  {
    HaveMultiLanguageBinaries = -2147024809;
    goto LABEL_38;
  }
  if ( OwnerWindow == HWND_MESSAGE|0x2LL )
    NonInteractiveFlag = SetupSetNonInteractiveMode(1);
  HaveMultiLanguageBinaries = CopyDriverPackageFilesHelper(a1, a2, v6, a4, OwnerWindow, 0);
  if ( HaveMultiLanguageBinaries >= 0 )
  {
    if ( (a4 & 1) == 0 )
    {
      HaveMultiLanguageBinaries = DoesInfHaveMultiLanguageBinaries(a1, (int *)&pcchLanguagesBuffer);
      if ( HaveMultiLanguageBinaries < 0 )
        goto LABEL_37;
      v5 = pcchLanguagesBuffer;
    }
    if ( v5 )
    {
      SupportedCultureNamesInInf = GetSupportedCultureNamesInInf(a1, &v29);
      v7 = v29;
      HaveMultiLanguageBinaries = SupportedCultureNamesInInf;
      if ( SupportedCultureNamesInInf < 0 )
        goto LABEL_35;
    }
    if ( v7 )
    {
      v16 = 0;
      pcchLanguagesBuffer = 0;
      pulNumLanguages = 0;
      pwszLanguagesBuffer = 0;
      v27 = 0;
      if ( !GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
      {
LABEL_20:
        HaveMultiLanguageBinaries = NCoreLibrary::GetLastErrorAsFailHR(v17);
LABEL_21:
        if ( HaveMultiLanguageBinaries < 0 )
        {
LABEL_33:
          if ( v16 )
            LocalFree(v16);
          goto LABEL_35;
        }
LABEL_22:
        if ( !pulNumLanguages )
          goto LABEL_26;
        if ( GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, v16, &pcchLanguagesBuffer) )
          HaveMultiLanguageBinaries = NCoreLibrary::GetLastErrorAsFailHR(v19);
        if ( HaveMultiLanguageBinaries >= 0 )
        {
LABEL_26:
          v20 = v7;
          v21 = 0;
          GlobalFlags = pSetupGetGlobalFlags();
          v22 = GlobalFlags;
          EnterCriticalSection(&SetupapiGlobalFlagsCritSect);
          v23 = v22;
          LODWORD(v23) = v22 | 0x400;
          pSetupSetGlobalFlags(v23);
          do
          {
            if ( !v20 )
              break;
            if ( SetThreadPreferredUILanguages(8u, *(PCZZWSTR *)v20, &v27) )
            {
              v21 = 1;
              HaveMultiLanguageBinaries = CopyDriverPackageFilesHelper(a1, a2, a3, a4, OwnerWindow, 1);
            }
            v20 = (struct _STRING_LIST *)*((_QWORD *)v20 + 1);
          }
          while ( HaveMultiLanguageBinaries >= 0 );
          pSetupSetGlobalFlags(GlobalFlags);
          LeaveCriticalSection(&SetupapiGlobalFlagsCritSect);
          v7 = v29;
          v16 = (WCHAR *)pwszLanguagesBuffer;
          if ( v21 )
            SetThreadPreferredUILanguages(8u, pwszLanguagesBuffer, &v27);
        }
        goto LABEL_33;
      }
      if ( !pulNumLanguages )
        goto LABEL_21;
      v18 = (WCHAR *)LocalAlloc(0x40u, 2 * pcchLanguagesBuffer);
      pwszLanguagesBuffer = v18;
      v16 = v18;
      if ( v18 )
      {
        HaveMultiLanguageBinaries = 0;
        if ( GetThreadPreferredUILanguages(0x48u, &pulNumLanguages, v18, &pcchLanguagesBuffer) )
          goto LABEL_22;
        goto LABEL_20;
      }
      HaveMultiLanguageBinaries = -2147024882;
LABEL_35:
      if ( v7 )
        DestroyStringList(v7);
    }
  }
LABEL_37:
  v12 = NonInteractiveFlag;
LABEL_38:
  if ( OwnerWindow == HWND_MESSAGE|0x2LL )
    SetupSetNonInteractiveMode(v12);
  return (unsigned int)HaveMultiLanguageBinaries;
}

```

## disassembly

```asm
0x1800310a0  mov     rax, rsp
0x1800310a3  mov     [rax+8], rbx
0x1800310a7  mov     [rax+20h], r9d
0x1800310ab  mov     [rax+18h], r8w
0x1800310b0  mov     [rax+10h], rdx
0x1800310b4  push    rbp
0x1800310b5  push    rsi
0x1800310b6  push    rdi
0x1800310b7  push    r12
0x1800310b9  push    r13
0x1800310bb  push    r14
0x1800310bd  push    r15
0x1800310bf  mov     rbp, rsp
0x1800310c2  sub     rsp, 60h
0x1800310c6  xor     esi, esi
0x1800310c8  movzx   r14d, r8w
0x1800310cc  xor     edi, edi
0x1800310ce  mov     [rbp+pcchLanguagesBuffer], esi
0x1800310d1  mov     [rbp+var_18], rdi
0x1800310d5  mov     r13d, r9d
0x1800310d8  mov     r12, rdx
0x1800310db  mov     r15, rcx
0x1800310de  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x1800310e3  test    al, al
0x1800310e5  jz      short loc_1800310F1
0x1800310e7  mov     eax, 800704ECh
0x1800310ec  jmp     loc_180031333
0x1800310f1  xor     ecx, ecx
0x1800310f3  mov     [rbp+NonInteractiveFlag], ecx
0x1800310f6  test    r15, r15
0x1800310f9  jz      loc_180031352
0x1800310ff  test    r12, r12
0x180031102  jz      loc_180031352
0x180031108  cmp     r14d, 0Ch
0x18003110c  ja      loc_180031352
0x180031112  mov     edx, 1241h
0x180031117  bt      edx, r14d
0x18003111b  jnb     loc_180031352
0x180031121  mov     rbx, [rbp+arg_20]
0x180031125  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180031129  jnz     short loc_180031137
0x18003112b  lea     ecx, [rbx+2]; NonInteractiveFlag
0x18003112e  call    cs:__imp_SetupSetNonInteractiveMode
0x180031134  mov     [rbp+NonInteractiveFlag], eax
0x180031137  mov     [rsp+60h+var_38], esi; int
0x18003113b  mov     r9d, r13d; unsigned int
0x18003113e  movzx   r8d, r14w; unsigned __int16
0x180031142  mov     [rsp+60h+OwnerWindow], rbx; OwnerWindow
0x180031147  mov     rdx, r12; unsigned __int16 *
0x18003114a  mov     rcx, r15; unsigned __int16 *
0x18003114d  call    ?CopyDriverPackageFilesHelper@@YAJPEBG0GKPEAUHWND__@@H@Z; CopyDriverPackageFilesHelper(ushort const *,ushort const *,ushort,ulong,HWND__ *,int)
0x180031152  mov     ebx, eax
0x180031154  test    eax, eax
0x180031156  js      loc_180031321
0x18003115c  test    r13b, 1
0x180031160  jnz     short loc_18003117B
0x180031162  lea     rdx, [rbp+pcchLanguagesBuffer]; int *
0x180031166  mov     rcx, r15; unsigned __int16 *
0x180031169  call    ?DoesInfHaveMultiLanguageBinaries@@YAJPEBGPEAH@Z; DoesInfHaveMultiLanguageBinaries(ushort const *,int *)
0x18003116e  mov     ebx, eax
0x180031170  test    eax, eax
0x180031172  js      loc_180031321
0x180031178  mov     esi, [rbp+pcchLanguagesBuffer]
0x18003117b  test    esi, esi
0x18003117d  jz      short loc_180031199
0x18003117f  lea     rdx, [rbp+var_18]; struct _STRING_LIST **
0x180031183  mov     rcx, r15; unsigned __int16 *
0x180031186  call    ?GetSupportedCultureNamesInInf@@YAJPEBGPEAPEAU_STRING_LIST@@@Z; GetSupportedCultureNamesInInf(ushort const *,_STRING_LIST * *)
0x18003118b  mov     rdi, [rbp+var_18]
0x18003118f  mov     ebx, eax
0x180031191  test    eax, eax
0x180031193  js      loc_180031314
0x180031199  test    rdi, rdi
0x18003119c  jz      loc_180031321
0x1800311a2  xor     esi, esi
0x1800311a4  mov     [rbp+pcchLanguagesBuffer], 0
0x1800311ab  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800311af  mov     [rbp+pulNumLanguages], 0
0x1800311b6  xor     r8d, r8d; pwszLanguagesBuffer
0x1800311b9  mov     [rbp+pwszLanguagesBuffer], rsi
0x1800311bd  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x1800311c1  mov     [rbp+var_24], esi
0x1800311c4  lea     r14d, [rsi+48h]
0x1800311c8  mov     ecx, r14d; dwFlags
0x1800311cb  call    cs:__imp_GetThreadPreferredUILanguages
0x1800311d1  test    eax, eax
0x1800311d3  jz      short loc_180031213
0x1800311d5  cmp     [rbp+pulNumLanguages], esi
0x1800311d8  jbe     short loc_18003121A
0x1800311da  mov     eax, [rbp+pcchLanguagesBuffer]
0x1800311dd  lea     ecx, [rsi+40h]; uFlags
0x1800311e0  lea     edx, [rax+rax]; uBytes
0x1800311e3  call    cs:__imp_LocalAlloc
0x1800311e9  mov     [rbp+pwszLanguagesBuffer], rax
0x1800311ed  mov     rsi, rax
0x1800311f0  test    rax, rax
0x1800311f3  jz      loc_18003134B
0x1800311f9  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800311fd  mov     r8, rax; pwszLanguagesBuffer
0x180031200  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x180031204  mov     ecx, r14d; dwFlags
0x180031207  xor     ebx, ebx
0x180031209  call    cs:__imp_GetThreadPreferredUILanguages
0x18003120f  test    eax, eax
0x180031211  jnz     short loc_180031222
0x180031213  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180031218  mov     ebx, eax
0x18003121a  test    ebx, ebx
0x18003121c  js      loc_180031306
0x180031222  cmp     [rbp+pulNumLanguages], 0
0x180031226  jbe     short loc_18003124F
0x180031228  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18003122c  mov     r8, rsi; pwszLanguagesBuffer
0x18003122f  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x180031233  mov     ecx, r14d; dwFlags
0x180031236  call    cs:__imp_GetThreadPreferredUILanguages
0x18003123c  test    eax, eax
0x18003123e  jz      short loc_180031247
0x180031240  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180031245  mov     ebx, eax
0x180031247  test    ebx, ebx
0x180031249  js      loc_180031306
0x18003124f  mov     r14, rdi
0x180031252  xor     r12d, r12d
0x180031255  call    cs:__imp_pSetupGetGlobalFlags
0x18003125b  lea     rcx, SetupapiGlobalFlagsCritSect; lpCriticalSection
0x180031262  mov     [rbp+var_20], eax
0x180031265  mov     r13d, eax
0x180031268  call    cs:__imp_EnterCriticalSection
0x18003126e  mov     ecx, r13d
0x180031271  bts     ecx, 0Ah
0x180031275  call    cs:__imp_pSetupSetGlobalFlags
0x18003127b  mov     rdi, [rbp+arg_20]
0x18003127f  movzx   r13d, [rbp+arg_10]
0x180031284  mov     rsi, [rbp+arg_8]
0x180031288  test    r14, r14
0x18003128b  jz      short loc_1800312D1
0x18003128d  mov     rdx, [r14]; pwszLanguagesBuffer
0x180031290  lea     r8, [rbp+var_24]; pulNumLanguages
0x180031294  mov     ecx, 8; dwFlags
0x180031299  call    cs:__imp_SetThreadPreferredUILanguages
0x18003129f  test    eax, eax
0x1800312a1  jz      short loc_1800312C9
0x1800312a3  mov     r9d, [rbp+arg_18]; unsigned int
0x1800312a7  mov     eax, 1
0x1800312ac  mov     [rsp+60h+var_38], eax; int
0x1800312b0  movzx   r8d, r13w; unsigned __int16
0x1800312b4  mov     rdx, rsi; unsigned __int16 *
0x1800312b7  mov     [rsp+60h+OwnerWindow], rdi; OwnerWindow
0x1800312bc  mov     rcx, r15; unsigned __int16 *
0x1800312bf  mov     r12d, eax
0x1800312c2  call    ?CopyDriverPackageFilesHelper@@YAJPEBG0GKPEAUHWND__@@H@Z; CopyDriverPackageFilesHelper(ushort const *,ushort const *,ushort,ulong,HWND__ *,int)
0x1800312c7  mov     ebx, eax
0x1800312c9  mov     r14, [r14+8]
0x1800312cd  test    ebx, ebx
0x1800312cf  jns     short loc_180031288
0x1800312d1  mov     ecx, [rbp+var_20]
0x1800312d4  call    cs:__imp_pSetupSetGlobalFlags
0x1800312da  lea     rcx, SetupapiGlobalFlagsCritSect; lpCriticalSection
0x1800312e1  call    cs:__imp_LeaveCriticalSection
0x1800312e7  mov     rdi, [rbp+var_18]
0x1800312eb  mov     rsi, [rbp+pwszLanguagesBuffer]
0x1800312ef  test    r12d, r12d
0x1800312f2  jz      short loc_180031306
0x1800312f4  lea     r8, [rbp+var_24]; pulNumLanguages
0x1800312f8  mov     rdx, rsi; pwszLanguagesBuffer
0x1800312fb  mov     ecx, 8; dwFlags
0x180031300  call    cs:__imp_SetThreadPreferredUILanguages
0x180031306  test    rsi, rsi
0x180031309  jz      short loc_180031314
0x18003130b  mov     rcx, rsi; hMem
0x18003130e  call    cs:__imp_LocalFree
0x180031314  test    rdi, rdi
0x180031317  jz      short loc_180031321
0x180031319  mov     rcx, rdi; struct _STRING_LIST *
0x18003131c  call    ?DestroyStringList@@YAXPEAU_STRING_LIST@@@Z; DestroyStringList(_STRING_LIST *)
0x180031321  mov     ecx, [rbp+NonInteractiveFlag]; NonInteractiveFlag
0x180031324  cmp     [rbp+arg_20], 0FFFFFFFFFFFFFFFFh
0x180031329  jnz     short loc_180031331
0x18003132b  call    cs:__imp_SetupSetNonInteractiveMode
0x180031331  mov     eax, ebx
0x180031333  mov     rbx, [rsp+60h+arg_0]
0x18003133b  add     rsp, 60h
0x18003133f  pop     r15
0x180031341  pop     r14
0x180031343  pop     r13
0x180031345  pop     r12
0x180031347  pop     rdi
0x180031348  pop     rsi
0x180031349  pop     rbp
0x18003134a  retn
0x18003134b  mov     ebx, 8007000Eh
0x180031350  jmp     short loc_180031314
0x180031352  mov     ebx, 80070057h
0x180031357  jmp     short loc_180031324
```
