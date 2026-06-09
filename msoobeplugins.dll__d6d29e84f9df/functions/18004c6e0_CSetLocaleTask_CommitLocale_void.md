# CSetLocaleTask::_CommitLocale(void)

- ea: `0x18004c6e0`
- end: `0x18004c918`
- name: `?_CommitLocale@CSetLocaleTask@@AEAAJXZ`
- size: `568`
- prototype: `__int64 __fastcall(CSetLocaleTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004c480`

## callees

- `0x180003470`
- `0x18000ac48`
- `0x18004c6e0`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c74c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c768`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c74c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c768`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c8c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c8c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c7f0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004c7f0`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18004c7c8`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18004c7c8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004c72e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004c72e`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x18004c721`
- `api-ms-win-core-localization-private-l1-1-0!NlsUpdateLocale` at `0x18004c721`

## string_xrefs

- `0x18004c7b0`: `Succeed in copying locale settings for "%s" to default/system/new user account.`
- `0x18004c77d`: `Start copy locale settings for "%s" to default/system/new user account.`
- `0x18004c75e`: `IntlUpdateSystemLocale`
- `0x18004c740`: `IntlCopyDefaultUserLocale`
- `0x18004c8ae`: `Failed to find IntlUpdateSystemLocale`
- `0x18004c89d`: `Failed in user copying locale settings for "%s" to default/system/new user account with hr=0x08%X`
- `0x18004c871`: `System locale is already "%s". There is no need to set the system locale.`
- `0x18004c8b7`: `Failed to find IntlCopyDefaultUserLocale`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSetLocaleTask::_CommitLocale(CSetLocaleTask *this)
{
  char *v1; // rdi
  HMODULE LibraryW; // rax
  HMODULE v4; // rsi
  __int64 Error; // rbx
  FARPROC ProcAddress; // rbp
  FARPROC v7; // r15
  int v8; // eax
  int v9; // eax
  char *v10; // r8
  WCHAR LocaleName[88]; // [rsp+30h] [rbp-E8h] BYREF

  v1 = (char *)this + 552;
  NlsUpdateLocale((char *)this + 552, 1);
  LibraryW = LoadLibraryW(L"intl.cpl");
  v4 = LibraryW;
  if ( LibraryW )
  {
    LODWORD(Error) = 0;
    ProcAddress = GetProcAddress(LibraryW, "IntlCopyDefaultUserLocale");
    if ( ProcAddress )
    {
      v7 = GetProcAddress(v4, "IntlUpdateSystemLocale");
      if ( v7 )
      {
        UnattendLogW(0, L"Start copy locale settings for \"%s\" to default/system/new user account.", v1);
        v8 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
        LODWORD(Error) = v8;
        if ( v8 > 0 )
          LODWORD(Error) = (unsigned __int16)v8 | 0x80070000;
        if ( (int)Error < 0 )
        {
          UnattendLogW(
            1,
            L"Failed in user copying locale settings for \"%s\" to default/system/new user account with hr=0x08%X",
            v1,
            (unsigned int)Error);
        }
        else
        {
          UnattendLogW(0, L"Succeed in copying locale settings for \"%s\" to default/system/new user account.", v1);
          if ( GetSystemDefaultLocaleName(LocaleName, 85) )
          {
            if ( CompareStringOrdinal(LocaleName, -1, (LPCWCH)this + 361, -1, 1) == 2 )
            {
              UnattendLogW(
                0,
                L"System locale is already \"%s\". There is no need to set the system locale.",
                LocaleName);
            }
            else
            {
              UnattendLogW(0, L"Start setting system locale \"%s\" and its related font settings.", (char *)this + 722);
              v9 = ((__int64 (__fastcall *)(char *, __int64))v7)((char *)this + 722, 2);
              LODWORD(Error) = v9;
              if ( v9 > 0 )
                LODWORD(Error) = (unsigned __int16)v9 | 0x80070000;
              v10 = (char *)this + 722;
              if ( (int)Error < 0 )
              {
                UnattendLogW(
                  0,
                  L"Failed to set system locale \"%s\" and its related font settings with hr=0x08%X",
                  v10,
                  (unsigned int)Error);
              }
              else
              {
                UnattendLogW(0, L"Succeed in setting system locale \"%s\" and its related font settings.", v10);
                *((_BYTE *)this + 892) = 1;
                UnattendLogW(
                  0,
                  L"The new system locale \"%s\" is not the same as the current system locale \"%s\". System will be rebooted later.",
                  (char *)this + 722,
                  LocaleName);
              }
            }
          }
          else
          {
            Error = (unsigned int)ResultFromKnownLastError();
            UnattendLogW(1, L"Failed to get current system locale with hr=0x08%X", Error);
          }
        }
      }
      else
      {
        UnattendLogW(1, L"Failed to find IntlUpdateSystemLocale");
      }
    }
    else
    {
      UnattendLogW(1, L"Failed to find IntlCopyDefaultUserLocale");
    }
    FreeLibrary(v4);
  }
  else
  {
    Error = (unsigned int)ResultFromKnownLastError();
    UnattendLogW(1, L"Failed to load intl.cpl with hr=0x%08X", Error);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004c6e0  mov     [rsp+arg_8], rbx
0x18004c6e5  mov     [rsp+arg_10], rbp
0x18004c6ea  push    rsi
0x18004c6eb  push    rdi
0x18004c6ec  push    r12
0x18004c6ee  push    r14
0x18004c6f0  push    r15
0x18004c6f2  sub     rsp, 0F0h
0x18004c6f9  mov     rax, cs:__security_cookie
0x18004c700  xor     rax, rsp
0x18004c703  mov     [rsp+118h+var_38], rax
0x18004c70b  lea     rdi, [rcx+228h]
0x18004c712  mov     r14, rcx
0x18004c715  mov     r12d, 1
0x18004c71b  mov     rcx, rdi
0x18004c71e  mov     edx, r12d
0x18004c721  call    cs:__imp_NlsUpdateLocale
0x18004c727  lea     rcx, aIntlCpl; "intl.cpl"
0x18004c72e  call    cs:__imp_LoadLibraryW
0x18004c734  mov     rsi, rax
0x18004c737  test    rax, rax
0x18004c73a  jz      loc_18004C8D1
0x18004c740  lea     rdx, aIntlcopydefaul; "IntlCopyDefaultUserLocale"
0x18004c747  mov     rcx, rax; hModule
0x18004c74a  xor     ebx, ebx
0x18004c74c  call    cs:__imp_GetProcAddress
0x18004c752  mov     rbp, rax
0x18004c755  test    rax, rax
0x18004c758  jz      loc_18004C8B7
0x18004c75e  lea     rdx, aIntlupdatesyst; "IntlUpdateSystemLocale"
0x18004c765  mov     rcx, rsi; hModule
0x18004c768  call    cs:__imp_GetProcAddress
0x18004c76e  mov     r15, rax
0x18004c771  test    rax, rax
0x18004c774  jz      loc_18004C8AE
0x18004c77a  mov     r8, rdi
0x18004c77d  lea     rdx, aStartCopyLocal; "Start copy locale settings for \"%s\" t"...
0x18004c784  xor     ecx, ecx
0x18004c786  call    UnattendLogW
0x18004c78b  xor     ecx, ecx
0x18004c78d  mov     rax, rbp
0x18004c790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c795  mov     ebx, eax
0x18004c797  mov     ebp, 80070000h
0x18004c79c  test    eax, eax
0x18004c79e  jle     short loc_18004C7A5
0x18004c7a0  movzx   ebx, ax
0x18004c7a3  or      ebx, ebp
0x18004c7a5  mov     r8, rdi
0x18004c7a8  test    ebx, ebx
0x18004c7aa  js      loc_18004C89A
0x18004c7b0  lea     rdx, aSucceedInCopyi; "Succeed in copying locale settings for "...
0x18004c7b7  xor     ecx, ecx
0x18004c7b9  call    UnattendLogW
0x18004c7be  mov     edx, 55h ; 'U'; cchLocaleName
0x18004c7c3  lea     rcx, [rsp+118h+LocaleName]; lpLocaleName
0x18004c7c8  call    cs:__imp_GetSystemDefaultLocaleName
0x18004c7ce  test    eax, eax
0x18004c7d0  jz      loc_18004C87F
0x18004c7d6  or      edx, 0FFFFFFFFh; cchCount1
0x18004c7d9  mov     [rsp+118h+bIgnoreCase], r12d; bIgnoreCase
0x18004c7de  lea     rdi, [r14+2D2h]
0x18004c7e5  mov     r9d, edx; cchCount2
0x18004c7e8  mov     r8, rdi; lpString2
0x18004c7eb  lea     rcx, [rsp+118h+LocaleName]; lpString1
0x18004c7f0  call    cs:__imp_CompareStringOrdinal
0x18004c7f6  xor     ecx, ecx
0x18004c7f8  cmp     eax, 2
0x18004c7fb  jz      short loc_18004C86C
0x18004c7fd  mov     r8, rdi
0x18004c800  lea     rdx, aStartSettingSy; "Start setting system locale \"%s\" and "...
0x18004c807  call    UnattendLogW
0x18004c80c  mov     edx, 2
0x18004c811  mov     rcx, rdi
0x18004c814  mov     rax, r15
0x18004c817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c81c  mov     ebx, eax
0x18004c81e  test    eax, eax
0x18004c820  jle     short loc_18004C827
0x18004c822  movzx   ebx, ax
0x18004c825  or      ebx, ebp
0x18004c827  xor     ecx, ecx
0x18004c829  mov     r8, rdi
0x18004c82c  test    ebx, ebx
0x18004c82e  js      short loc_18004C85B
0x18004c830  lea     rdx, aSucceedInSetti; "Succeed in setting system locale \"%s\""...
0x18004c837  call    UnattendLogW
0x18004c83c  lea     r9, [rsp+118h+LocaleName]
0x18004c841  mov     [r14+37Ch], r12b
0x18004c848  mov     r8, rdi
0x18004c84b  lea     rdx, aTheNewSystemLo; "The new system locale \"%s\" is not the"...
0x18004c852  xor     ecx, ecx
0x18004c854  call    UnattendLogW
0x18004c859  jmp     short loc_18004C8C6
0x18004c85b  mov     r9d, ebx
0x18004c85e  lea     rdx, aFailedToSetSys; "Failed to set system locale \"%s\" and "...
0x18004c865  call    UnattendLogW
0x18004c86a  jmp     short loc_18004C8C6
0x18004c86c  lea     r8, [rsp+118h+LocaleName]
0x18004c871  lea     rdx, aSystemLocaleIs; "System locale is already \"%s\". There "...
0x18004c878  call    UnattendLogW
0x18004c87d  jmp     short loc_18004C8C6
0x18004c87f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004c884  mov     r8d, eax
0x18004c887  lea     rdx, aFailedToGetCur; "Failed to get current system locale wit"...
0x18004c88e  mov     ecx, r12d
0x18004c891  mov     ebx, eax
0x18004c893  call    UnattendLogW
0x18004c898  jmp     short loc_18004C8C6
0x18004c89a  mov     r9d, ebx
0x18004c89d  lea     rdx, aFailedInUserCo; "Failed in user copying locale settings "...
0x18004c8a4  mov     ecx, r12d
0x18004c8a7  call    UnattendLogW
0x18004c8ac  jmp     short loc_18004C8C6
0x18004c8ae  lea     rdx, aFailedToFindIn; "Failed to find IntlUpdateSystemLocale"
0x18004c8b5  jmp     short loc_18004C8BE
0x18004c8b7  lea     rdx, aFailedToFindIn_0; "Failed to find IntlCopyDefaultUserLocal"...
0x18004c8be  mov     ecx, r12d
0x18004c8c1  call    UnattendLogW
0x18004c8c6  mov     rcx, rsi; hLibModule
0x18004c8c9  call    cs:__imp_FreeLibrary
0x18004c8cf  jmp     short loc_18004C8EA
0x18004c8d1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004c8d6  mov     r8d, eax
0x18004c8d9  lea     rdx, aFailedToLoadIn; "Failed to load intl.cpl with hr=0x%08X"
0x18004c8e0  mov     ecx, r12d
0x18004c8e3  mov     ebx, eax
0x18004c8e5  call    UnattendLogW
0x18004c8ea  mov     eax, ebx
0x18004c8ec  mov     rcx, [rsp+118h+var_38]
0x18004c8f4  xor     rcx, rsp; StackCookie
0x18004c8f7  call    __security_check_cookie
0x18004c8fc  lea     r11, [rsp+118h+var_28]
0x18004c904  mov     rbx, [r11+38h]
0x18004c908  mov     rbp, [r11+40h]
0x18004c90c  mov     rsp, r11
0x18004c90f  pop     r15
0x18004c911  pop     r14
0x18004c913  pop     r12
0x18004c915  pop     rdi
0x18004c916  pop     rsi
0x18004c917  retn
```
