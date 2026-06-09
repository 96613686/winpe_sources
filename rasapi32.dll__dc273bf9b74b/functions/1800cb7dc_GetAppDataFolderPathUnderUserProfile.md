# GetAppDataFolderPathUnderUserProfile

- ea: `0x1800cb7dc`
- end: `0x1800cbbfd`
- name: `GetAppDataFolderPathUnderUserProfile`
- size: `1057`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800caa9c`

## callees

- `0x180009cb4`
- `0x18000b0f4`
- `0x18000c980`
- `0x18002c3a4`
- `0x18004e580`
- `0x18004e984`
- `0x1800cb7dc`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cb8c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cb8c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cb8e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cb8e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cb8f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cb8f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cb8a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cb8a5`
- `ntdll!wcschr` at `0x1800cbb70`
- `ntdll!wcschr` at `0x1800cbb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb8ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cba8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb8ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cba8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cbba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cbba9`
- `USERENV!GetProfilesDirectoryW` at `0x1800cba82`
- `USERENV!GetProfilesDirectoryW` at `0x1800cba82`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800cba36`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800cba36`

## pseudocode

```c
__int64 __fastcall GetAppDataFolderPathUnderUserProfile(__int64 *a1)
{
  DWORD v2; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  DWORD v6; // eax
  char *v7; // rcx
  __int64 v8; // rdx
  DWORD SidFromToken; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int16 BasicProfileFolderPath; // ax
  unsigned __int16 v14; // ax
  unsigned __int16 v15; // ax
  wchar_t *v16; // rax
  wchar_t *v17; // rcx
  __int64 v18; // rax
  DWORD cchSize; // [rsp+20h] [rbp-E0h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h]
  size_t pcchLength; // [rsp+38h] [rbp-C8h] BYREF
  size_t v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t psz[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ProfileDir[264]; // [rsp+260h] [rbp+160h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 767, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  memset_0(psz, 0, 0x20Au);
  memset_0(ProfileDir, 0, 0x20Au);
  pcchLength = 0;
  v24[0] = 0;
  cchSize = 0;
  TokenHandle = 0;
  v22 = 0;
  if ( !a1 )
  {
    v2 = 87;
    goto LABEL_64;
  }
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    goto LABEL_30;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError != 1008 )
  {
    if ( LastError )
    {
      v7 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v2;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_26;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 770, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
    }
    v7 = (char *)WPP_GLOBAL_Control;
LABEL_26:
    if ( v7 == (char *)&WPP_GLOBAL_Control || v7[28] >= 0 || (unsigned __int8)v7[25] < 6u )
      return v2;
    v8 = 771;
LABEL_70:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v2);
    return v2;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
  {
    v6 = GetLastError();
    v2 = v6;
    if ( v6 )
    {
      v7 = (char *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v2;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_16;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 768, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v6);
    }
    v7 = (char *)WPP_GLOBAL_Control;
LABEL_16:
    if ( v7 == (char *)&WPP_GLOBAL_Control || v7[28] >= 0 || (unsigned __int8)v7[25] < 6u )
      return v2;
    v8 = 769;
    goto LABEL_70;
  }
LABEL_30:
  SidFromToken = GetSidFromToken(TokenHandle);
  v2 = SidFromToken;
  if ( !SidFromToken )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(7, v22, psz, 261);
    v2 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v11 = 773;
    }
    else
    {
      cchSize = 261;
      if ( !GetProfilesDirectoryW(ProfileDir, &cchSize) )
      {
        v2 = GetLastError();
        goto LABEL_64;
      }
      v14 = StringCchLengthW(ProfileDir, 0x105u, &pcchLength);
      v2 = v14;
      if ( v14 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((char *)WPP_GLOBAL_Control + 28) >= 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_64;
        }
        v11 = 774;
      }
      else
      {
        v15 = StringCchLengthW(psz, 0x105u, v24);
        v2 = v15;
        if ( v15 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || *((char *)WPP_GLOBAL_Control + 28) >= 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_64;
          }
          v11 = 775;
        }
        else
        {
          if ( v24[0] >= pcchLength + 1 )
          {
            if ( pcchLength < 0x104 )
            {
              v16 = wcschr(&psz[pcchLength + 1], 0x5Cu);
              v17 = v16 + 1;
              if ( !v16 )
                v17 = 0;
              v18 = StrDup(v17);
              *a1 = v18;
              if ( !v18 )
                v2 = 8;
            }
            goto LABEL_64;
          }
          v2 = 10;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || *((char *)WPP_GLOBAL_Control + 28) >= 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_64;
          }
          v11 = 776;
        }
      }
    }
    v12 = v2;
    goto LABEL_35;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 772;
    v12 = SidFromToken;
LABEL_35:
    WPP_SF_d(v10[2], v11, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v12);
  }
LABEL_64:
  Free0(v22);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  v7 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v8 = 777;
    goto LABEL_70;
  }
  return v2;
}

```

## disassembly

```asm
0x1800cb7dc  push    rbp
0x1800cb7de  push    rbx
0x1800cb7df  push    rdi
0x1800cb7e0  push    r12
0x1800cb7e2  push    r13
0x1800cb7e4  push    r15
0x1800cb7e6  lea     rbp, [rsp-388h]
0x1800cb7ee  sub     rsp, 488h
0x1800cb7f5  mov     rax, cs:__security_cookie
0x1800cb7fc  xor     rax, rsp
0x1800cb7ff  mov     [rbp+3B0h+var_40], rax
0x1800cb806  mov     rdi, rcx
0x1800cb809  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb810  lea     r15, WPP_GLOBAL_Control
0x1800cb817  lea     r12, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cb81e  cmp     rcx, r15
0x1800cb821  jz      short loc_1800CB840
0x1800cb823  test    byte ptr [rcx+1Ch], 80h
0x1800cb827  jz      short loc_1800CB840
0x1800cb829  cmp     byte ptr [rcx+19h], 6
0x1800cb82d  jb      short loc_1800CB840
0x1800cb82f  mov     rcx, [rcx+10h]
0x1800cb833  mov     edx, 2FFh
0x1800cb838  mov     r8, r12
0x1800cb83b  call    WPP_SF_
0x1800cb840  mov     ebx, 20Ah
0x1800cb845  lea     rcx, [rsp+4B0h+psz]; void *
0x1800cb84a  mov     r8d, ebx; Size
0x1800cb84d  xor     edx, edx; Val
0x1800cb84f  call    memset_0
0x1800cb854  mov     r8d, ebx; Size
0x1800cb857  lea     rcx, [rbp+3B0h+ProfileDir]; void *
0x1800cb85e  xor     edx, edx; Val
0x1800cb860  call    memset_0
0x1800cb865  mov     [rsp+4B0h+pcchLength], 0
0x1800cb86e  mov     [rsp+4B0h+var_470], 0
0x1800cb877  mov     [rsp+4B0h+cchSize], 0
0x1800cb87f  mov     [rsp+4B0h+TokenHandle], 0
0x1800cb888  mov     [rsp+4B0h+var_480], 0
0x1800cb891  test    rdi, rdi
0x1800cb894  jnz     short loc_1800CB89E
0x1800cb896  lea     ebx, [rdi+57h]
0x1800cb899  jmp     loc_1800CBB94
0x1800cb89e  mov     qword ptr [rdi], 0
0x1800cb8a5  call    cs:__imp_GetCurrentThread
0x1800cb8ab  mov     r8d, 1; OpenAsSelf
0x1800cb8b1  lea     r9, [rsp+4B0h+TokenHandle]; TokenHandle
0x1800cb8b6  mov     rcx, rax; ThreadHandle
0x1800cb8b9  lea     r13d, [r8+0Bh]
0x1800cb8bd  mov     edx, r13d; DesiredAccess
0x1800cb8c0  call    cs:__imp_OpenThreadToken
0x1800cb8c6  test    eax, eax
0x1800cb8c8  jnz     loc_1800CB9CC
0x1800cb8ce  call    cs:__imp_GetLastError
0x1800cb8d4  mov     ebx, eax
0x1800cb8d6  cmp     eax, 3F0h
0x1800cb8db  jnz     loc_1800CB96A
0x1800cb8e1  call    cs:__imp_GetCurrentProcess
0x1800cb8e7  lea     r8, [rsp+4B0h+TokenHandle]; TokenHandle
0x1800cb8ec  mov     edx, r13d; DesiredAccess
0x1800cb8ef  mov     rcx, rax; ProcessHandle
0x1800cb8f2  call    cs:__imp_OpenProcessToken
0x1800cb8f8  test    eax, eax
0x1800cb8fa  jnz     loc_1800CB9CC
0x1800cb900  call    cs:__imp_GetLastError
0x1800cb906  mov     ebx, eax
0x1800cb908  test    eax, eax
0x1800cb90a  jz      short loc_1800CB93C
0x1800cb90c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb913  cmp     rcx, r15
0x1800cb916  jz      loc_1800CBBDB
0x1800cb91c  test    byte ptr [rcx+1Ch], 80h
0x1800cb920  jz      short loc_1800CB943
0x1800cb922  cmp     byte ptr [rcx+19h], 2
0x1800cb926  jb      short loc_1800CB943
0x1800cb928  mov     rcx, [rcx+10h]
0x1800cb92c  mov     edx, 300h
0x1800cb931  mov     r9d, eax
0x1800cb934  mov     r8, r12
0x1800cb937  call    WPP_SF_d
0x1800cb93c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb943  cmp     rcx, r15
0x1800cb946  jz      loc_1800CBBDB
0x1800cb94c  test    byte ptr [rcx+1Ch], 80h
0x1800cb950  jz      loc_1800CBBDB
0x1800cb956  cmp     byte ptr [rcx+19h], 6
0x1800cb95a  jb      loc_1800CBBDB
0x1800cb960  mov     edx, 301h
0x1800cb965  jmp     loc_1800CBBCC
0x1800cb96a  test    ebx, ebx
0x1800cb96c  jz      short loc_1800CB99E
0x1800cb96e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb975  cmp     rcx, r15
0x1800cb978  jz      loc_1800CBBDB
0x1800cb97e  test    byte ptr [rcx+1Ch], 80h
0x1800cb982  jz      short loc_1800CB9A5
0x1800cb984  cmp     byte ptr [rcx+19h], 2
0x1800cb988  jb      short loc_1800CB9A5
0x1800cb98a  mov     rcx, [rcx+10h]
0x1800cb98e  mov     edx, 302h
0x1800cb993  mov     r9d, ebx
0x1800cb996  mov     r8, r12
0x1800cb999  call    WPP_SF_d
0x1800cb99e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb9a5  cmp     rcx, r15
0x1800cb9a8  jz      loc_1800CBBDB
0x1800cb9ae  test    byte ptr [rcx+1Ch], 80h
0x1800cb9b2  jz      loc_1800CBBDB
0x1800cb9b8  cmp     byte ptr [rcx+19h], 6
0x1800cb9bc  jb      loc_1800CBBDB
0x1800cb9c2  mov     edx, 303h
0x1800cb9c7  jmp     loc_1800CBBCC
0x1800cb9cc  mov     rcx, [rsp+4B0h+TokenHandle]; TokenHandle
0x1800cb9d1  lea     rdx, [rsp+4B0h+var_480]
0x1800cb9d6  call    GetSidFromToken
0x1800cb9db  mov     ebx, eax
0x1800cb9dd  test    eax, eax
0x1800cb9df  jz      short loc_1800CBA1E
0x1800cb9e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb9e8  cmp     rcx, r15
0x1800cb9eb  jz      loc_1800CBB94
0x1800cb9f1  test    byte ptr [rcx+1Ch], 80h
0x1800cb9f5  jz      loc_1800CBB94
0x1800cb9fb  cmp     byte ptr [rcx+19h], 2
0x1800cb9ff  jb      loc_1800CBB94
0x1800cba05  mov     edx, 304h
0x1800cba0a  mov     r9d, eax
0x1800cba0d  mov     rcx, [rcx+10h]
0x1800cba11  mov     r8, r12
0x1800cba14  call    WPP_SF_d
0x1800cba19  jmp     loc_1800CBB94
0x1800cba1e  mov     rdx, [rsp+4B0h+var_480]
0x1800cba23  lea     r8, [rsp+4B0h+psz]
0x1800cba28  mov     r13d, 105h
0x1800cba2e  mov     ecx, 7
0x1800cba33  mov     r9d, r13d
0x1800cba36  call    cs:__imp_GetBasicProfileFolderPath
0x1800cba3c  movzx   ebx, ax
0x1800cba3f  test    ebx, ebx
0x1800cba41  jz      short loc_1800CBA71
0x1800cba43  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cba4a  cmp     rcx, r15
0x1800cba4d  jz      loc_1800CBB94
0x1800cba53  test    byte ptr [rcx+1Ch], 80h
0x1800cba57  jz      loc_1800CBB94
0x1800cba5d  cmp     byte ptr [rcx+19h], 2
0x1800cba61  jb      loc_1800CBB94
0x1800cba67  mov     edx, 305h
0x1800cba6c  mov     r9d, ebx
0x1800cba6f  jmp     short loc_1800CBA0D
0x1800cba71  lea     rdx, [rsp+4B0h+cchSize]; lpcchSize
0x1800cba76  mov     [rsp+4B0h+cchSize], r13d
0x1800cba7b  lea     rcx, [rbp+3B0h+ProfileDir]; lpProfileDir
0x1800cba82  call    cs:__imp_GetProfilesDirectoryW
0x1800cba88  test    eax, eax
0x1800cba8a  jnz     short loc_1800CBA99
0x1800cba8c  call    cs:__imp_GetLastError
0x1800cba92  mov     ebx, eax
0x1800cba94  jmp     loc_1800CBB94
0x1800cba99  lea     r8, [rsp+4B0h+pcchLength]; pcchLength
0x1800cba9e  mov     rdx, r13; cchMax
0x1800cbaa1  lea     rcx, [rbp+3B0h+ProfileDir]; psz
0x1800cbaa8  call    StringCchLengthW
0x1800cbaad  movzx   ebx, ax
0x1800cbab0  test    ebx, ebx
0x1800cbab2  jz      short loc_1800CBADF
0x1800cbab4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbabb  cmp     rcx, r15
0x1800cbabe  jz      loc_1800CBB94
0x1800cbac4  test    byte ptr [rcx+1Ch], 80h
0x1800cbac8  jz      loc_1800CBB94
0x1800cbace  cmp     byte ptr [rcx+19h], 2
0x1800cbad2  jb      loc_1800CBB94
0x1800cbad8  mov     edx, 306h
0x1800cbadd  jmp     short loc_1800CBA6C
0x1800cbadf  lea     r8, [rsp+4B0h+var_470]; pcchLength
0x1800cbae4  mov     rdx, r13; cchMax
0x1800cbae7  lea     rcx, [rsp+4B0h+psz]; psz
0x1800cbaec  call    StringCchLengthW
0x1800cbaf1  movzx   ebx, ax
0x1800cbaf4  test    ebx, ebx
0x1800cbaf6  jz      short loc_1800CBB22
0x1800cbaf8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbaff  cmp     rcx, r15
0x1800cbb02  jz      loc_1800CBB94
0x1800cbb08  test    byte ptr [rcx+1Ch], 80h
0x1800cbb0c  jz      loc_1800CBB94
0x1800cbb12  cmp     byte ptr [rcx+19h], 2
0x1800cbb16  jb      short loc_1800CBB94
0x1800cbb18  mov     edx, 307h
0x1800cbb1d  jmp     loc_1800CBA6C
0x1800cbb22  mov     rcx, [rsp+4B0h+pcchLength]
0x1800cbb27  lea     rax, [rcx+1]
0x1800cbb2b  cmp     [rsp+4B0h+var_470], rax
0x1800cbb30  jnb     short loc_1800CBB59
0x1800cbb32  mov     ebx, 0Ah
0x1800cbb37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbb3e  cmp     rcx, r15
0x1800cbb41  jz      short loc_1800CBB94
0x1800cbb43  test    byte ptr [rcx+1Ch], 80h
0x1800cbb47  jz      short loc_1800CBB94
0x1800cbb49  cmp     byte ptr [rcx+19h], 2
0x1800cbb4d  jb      short loc_1800CBB94
0x1800cbb4f  mov     edx, 308h
0x1800cbb54  jmp     loc_1800CBA6C
0x1800cbb59  cmp     rcx, 104h
0x1800cbb60  jnb     short loc_1800CBB94
0x1800cbb62  lea     rax, [rsp+4B0h+var_45E]
0x1800cbb67  mov     edx, 5Ch ; '\'; Ch
0x1800cbb6c  lea     rcx, [rax+rcx*2]; Str
0x1800cbb70  call    cs:__imp_wcschr
0x1800cbb76  test    rax, rax
0x1800cbb79  lea     rcx, [rax+2]
0x1800cbb7d  cmovz   rcx, rax
0x1800cbb81  call    StrDup
0x1800cbb86  test    rax, rax
0x1800cbb89  mov     [rdi], rax
0x1800cbb8c  mov     ecx, 8
0x1800cbb91  cmovz   ebx, ecx
0x1800cbb94  mov     rcx, [rsp+4B0h+var_480]
0x1800cbb99  call    Free0
0x1800cbb9e  mov     rcx, [rsp+4B0h+TokenHandle]; hObject
0x1800cbba3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800cbba7  jz      short loc_1800CBBAF
0x1800cbba9  call    cs:__imp_CloseHandle
0x1800cbbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cbbb6  cmp     rcx, r15
0x1800cbbb9  jz      short loc_1800CBBDB
0x1800cbbbb  test    byte ptr [rcx+1Ch], 80h
0x1800cbbbf  jz      short loc_1800CBBDB
0x1800cbbc1  cmp     byte ptr [rcx+19h], 6
0x1800cbbc5  jb      short loc_1800CBBDB
0x1800cbbc7  mov     edx, 309h
0x1800cbbcc  mov     rcx, [rcx+10h]
0x1800cbbd0  mov     r9d, ebx
0x1800cbbd3  mov     r8, r12
0x1800cbbd6  call    WPP_SF_d
0x1800cbbdb  mov     eax, ebx
0x1800cbbdd  mov     rcx, [rbp+3B0h+var_40]
0x1800cbbe4  xor     rcx, rsp; StackCookie
0x1800cbbe7  call    __security_check_cookie
0x1800cbbec  add     rsp, 488h
0x1800cbbf3  pop     r15
0x1800cbbf5  pop     r13
0x1800cbbf7  pop     r12
0x1800cbbf9  pop     rdi
0x1800cbbfa  pop     rbx
0x1800cbbfb  pop     rbp
0x1800cbbfc  retn
```
