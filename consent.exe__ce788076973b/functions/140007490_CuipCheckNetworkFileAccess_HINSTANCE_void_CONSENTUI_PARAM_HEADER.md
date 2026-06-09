# CuipCheckNetworkFileAccess(HINSTANCE__ *,void *,_CONSENTUI_PARAM_HEADER *)

- ea: `0x140007490`
- end: `0x140007aed`
- name: `?CuipCheckNetworkFileAccess@@YAKPEAUHINSTANCE__@@PEAXPEAU_CONSENTUI_PARAM_HEADER@@@Z`
- size: `1629`
- prototype: `__int64 __fastcall(HINSTANCE, void *, struct _CONSENTUI_PARAM_HEADER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x140007490`
- `0x140010ad3`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1400077c1`
- `msvcrt!wcsrchr` at `0x1400077c1`
- `msvcrt!wcschr` at `0x140007589`
- `msvcrt!wcschr` at `0x140007589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000756a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000756a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007646`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007abc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140007abc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000751e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000751e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007adb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007adb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140007539`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400075f6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140007539`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400075f6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140007577`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140007a75`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140007577`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140007a75`
- `SspiCli!GetUserNameExW` at `0x140007560`
- `SspiCli!GetUserNameExW` at `0x140007560`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140007633`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140007633`
- `USERENV!LoadUserProfileW` at `0x1400075bc`
- `USERENV!LoadUserProfileW` at `0x1400075bc`
- `USERENV!UnloadUserProfile` at `0x140007ab3`
- `USERENV!UnloadUserProfile` at `0x140007ab3`
- `MPR!WNetAddConnection3W` at `0x1400077fa`
- `MPR!WNetAddConnection3W` at `0x1400077fa`

## pseudocode

```c
__int64 __fastcall CuipCheckNetworkFileAccess(HINSTANCE a1, void *a2, struct _CONSENTUI_PARAM_HEADER *a3)
{
  __int64 FileW; // rbp
  WCHAR *v6; // r13
  wchar_t *v7; // rsi
  DWORD LastError; // edi
  wchar_t *v9; // rax
  WCHAR *v10; // rax
  DWORD v11; // eax
  unsigned int v12; // eax
  int v13; // ecx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  wchar_t *v17; // rax
  wchar_t *v18; // r12
  HWND v19; // rcx
  __int64 v20; // rcx
  _BYTE *v21; // rax
  _NETRESOURCEW NetResource; // [rsp+40h] [rbp-98h] BYREF
  _PROFILEINFOW ProfileInfo; // [rsp+70h] [rbp-68h] BYREF
  ULONG nSize; // [rsp+E0h] [rbp+8h] BYREF
  int v26; // [rsp+E4h] [rbp+Ch]

  v26 = HIDWORD(a1);
  FileW = -1;
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  nSize = 514;
  memset(&NetResource, 0, sizeof(NetResource));
  if ( *((_DWORD *)a3 + 1) )
  {
    LastError = 0;
    v7 = 0;
  }
  else
  {
    v6 = (WCHAR *)*((_QWORD *)a3 + 27);
    if ( !v6 )
      v6 = (WCHAR *)*((_QWORD *)a3 + 28);
    v7 = (wchar_t *)LocalAlloc(0x40u, 0x606u);
    if ( !v7 )
    {
      LastError = 8;
      goto LABEL_111;
    }
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      LastError = GetLastError();
      goto LABEL_111;
    }
    if ( GetUserNameExW(NameSamCompatible, v7, &nSize) )
    {
      RevertToSelf();
      v9 = wcschr(v7, 0x5Cu);
      if ( v9 )
        v10 = v9 + 1;
      else
        v10 = v7;
      ProfileInfo.dwSize = 56;
      ProfileInfo.lpProfilePath = 0;
      ProfileInfo.lpUserName = v10;
      if ( !LoadUserProfileW(a2, &ProfileInfo)
        || (memset_0(v7, 0, 2LL * nSize), nSize = 514, !ImpersonateLoggedOnUser(a2)) )
      {
        LastError = GetLastError();
        goto LABEL_111;
      }
      while ( 1 )
      {
        FileW = (__int64)CreateFileW(v6, 0x80000000, 5u, 0, 3u, 0x80u, 0);
        if ( FileW != -1 )
          break;
        v11 = GetLastError();
        LastError = v11;
        if ( v11 == -799211514
          || v11 == -799211518
          || v11 == -805305464
          || v11 == -805305820
          || (v12 = v11 + 805306273, v13 = 280609, v12 <= 0x12) && _bittest(&v13, v12)
          || LastError == -805306334
          || LastError == -1067646970
          || LastError + 1067646974 <= 2
          || LastError == -1073740755
          || LastError == -1073740920
          || LastError == -1073741276
          || LastError + 1073741729 <= 0x12 && _bittest(&v13, LastError + 1073741729)
          || LastError == -1073741790
          || LastError == -2146892959
          || LastError == -2146892976
          || LastError == -2146893042
          || LastError == -2146893044
          || LastError == -2147022654
          || LastError == -2147022959
          || LastError == -2147022989
          || LastError == -2147023566
          || (v14 = LastError + 2147023631, v15 = 0x2010800000000081LL, (unsigned int)v14 <= 0x3D)
          && _bittest64(&v15, v14)
          || LastError == -2147024810
          || LastError == -2147024891
          || LastError == 2242
          || LastError == 1937
          || LastError == 1907
          || LastError == 1330
          || (v16 = LastError - 1265, (unsigned int)v16 <= 0x3D) && _bittest64(&v15, v16)
          || LastError == 86
          || LastError == 5 )
        {
          v17 = wcsrchr(v6, 0x5Cu);
          v18 = v17;
          if ( v17 )
            *v17 = 0;
          v19 = (HWND)*((_QWORD *)a3 + 2);
          NetResource.dwType = 1;
          NetResource.lpRemoteName = v6;
          LastError = WNetAddConnection3W(v19, &NetResource, v7 + 514, v7, 0x18u);
          v20 = 514;
          v21 = v7 + 514;
          do
          {
            *v21++ = 0;
            --v20;
          }
          while ( v20 );
          if ( v18 )
            *v18 = 92;
          if ( LastError == -1067646974
            || LastError == -799211518
            || LastError == 1272
            || LastError == -2147023624
            || LastError == -1067646970
            || LastError == -799211514
            || LastError == -1067646973
            || LastError == -1067646972
            || LastError == 1937
            || LastError == -2147022959
            || LastError == 1326
            || LastError == -2147023570
            || LastError == -1073741715
            || LastError == -805306259
            || LastError == 5
            || LastError == -2147024891
            || LastError == -1073741790
            || LastError == -805306334
            || LastError == 86
            || LastError == -2147024810
            || LastError == -1073741718
            || LastError == -805306262
            || LastError == -1073741724
            || LastError == -805306268
            || LastError == 1317
            || LastError == -2147023579
            || LastError == 1312
            || LastError == -2147023584
            || LastError == -1073741729
            || LastError == -805306273
            || LastError == -2146893042
            || LastError == -2146893044
            || LastError == -2146892959
            || LastError == -1073740755
            || LastError == 1265
            || LastError == -2147023631
            || LastError == -1073740920
            || LastError == -805305464
            || LastError == -2146892976
            || LastError == 1330
            || LastError == -2147023566
            || LastError == -1073741711
            || LastError == -805306255
            || LastError == 1907
            || LastError == -2147022989
            || LastError == -1073741276
            || LastError == -805305820
            || LastError == 2242
            || LastError == -2147022654 )
          {
            continue;
          }
        }
        goto LABEL_109;
      }
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
LABEL_109:
    RevertToSelf();
  }
LABEL_111:
  if ( ProfileInfo.hProfile )
    UnloadUserProfile(a2, ProfileInfo.hProfile);
  LocalFree(v7);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return LastError;
}

```

## disassembly

```asm
0x140007490  mov     r11, rsp
0x140007493  mov     [r11+8], rcx
0x140007497  push    rbp
0x140007498  push    rdi
0x140007499  sub     rsp, 0C8h
0x1400074a0  mov     [r11+10h], rbx
0x1400074a4  xorps   xmm1, xmm1
0x1400074a7  mov     [r11+18h], rsi
0x1400074ab  xorps   xmm0, xmm0
0x1400074ae  mov     [r11+20h], r12
0x1400074b2  xor     eax, eax
0x1400074b4  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1400074bb  mov     [r11-18h], r13
0x1400074bf  movups  xmmword ptr [rsp+0D8h+ProfileInfo.dwSize], xmm1
0x1400074c4  mov     [r11-20h], r14
0x1400074c8  mov     r14, r8
0x1400074cb  mov     [r11-28h], r15
0x1400074cf  mov     r15, rdx
0x1400074d2  mov     dword ptr [r11+8], 202h
0x1400074da  movups  xmmword ptr [rsp+0D8h+NetResource.dwScope], xmm0
0x1400074df  mov     [r11-38h], rax
0x1400074e3  movups  xmmword ptr [rsp+0D8h+NetResource.lpLocalName], xmm0
0x1400074e8  movups  xmmword ptr [rsp+0D8h+NetResource.lpComment], xmm0
0x1400074ed  movups  xmmword ptr [r11-58h], xmm1
0x1400074f2  movups  xmmword ptr [r11-48h], xmm1
0x1400074f7  cmp     [r8+4], eax
0x1400074fb  jnz     loc_140007A7D
0x140007501  mov     r13, [r8+0D8h]
0x140007508  test    r13, r13
0x14000750b  jnz     short loc_140007514
0x14000750d  mov     r13, [r8+0E0h]
0x140007514  mov     edx, 606h; uBytes
0x140007519  mov     ecx, 40h ; '@'; uFlags
0x14000751e  call    cs:__imp_LocalAlloc
0x140007524  mov     rsi, rax
0x140007527  test    rax, rax
0x14000752a  jnz     short loc_140007536
0x14000752c  mov     edi, 8
0x140007531  jmp     loc_140007A83
0x140007536  mov     rcx, r15; hToken
0x140007539  call    cs:__imp_ImpersonateLoggedOnUser
0x14000753f  test    eax, eax
0x140007541  jnz     short loc_140007550
0x140007543  call    cs:__imp_GetLastError
0x140007549  mov     edi, eax
0x14000754b  jmp     loc_140007A83
0x140007550  lea     r8, [rsp+0D8h+nSize]; nSize
0x140007558  mov     rdx, rsi; lpNameBuffer
0x14000755b  mov     ecx, 2; NameFormat
0x140007560  call    cs:__imp_GetUserNameExW
0x140007566  test    al, al
0x140007568  jnz     short loc_140007577
0x14000756a  call    cs:__imp_GetLastError
0x140007570  mov     edi, eax
0x140007572  jmp     loc_140007A75
0x140007577  call    cs:__imp_RevertToSelf
0x14000757d  mov     r12d, 5Ch ; '\'
0x140007583  mov     rcx, rsi; Str
0x140007586  mov     edx, r12d; Ch
0x140007589  call    cs:__imp_wcschr
0x14000758f  test    rax, rax
0x140007592  jnz     short loc_140007599
0x140007594  mov     rax, rsi
0x140007597  jmp     short loc_14000759D
0x140007599  add     rax, 2
0x14000759d  xor     ebx, ebx
0x14000759f  mov     [rsp+0D8h+ProfileInfo.dwSize], 38h ; '8'
0x1400075a7  lea     rdx, [rsp+0D8h+ProfileInfo]; lpProfileInfo
0x1400075ac  mov     [rsp+0D8h+ProfileInfo.lpProfilePath], rbx
0x1400075b4  mov     rcx, r15; hToken
0x1400075b7  mov     [rsp+0D8h+ProfileInfo.lpUserName], rax
0x1400075bc  call    cs:__imp_LoadUserProfileW
0x1400075c2  test    eax, eax
0x1400075c4  jnz     short loc_1400075D3
0x1400075c6  call    cs:__imp_GetLastError
0x1400075cc  mov     edi, eax
0x1400075ce  jmp     loc_140007A83
0x1400075d3  mov     r8d, [rsp+0D8h+nSize]
0x1400075db  xor     edx, edx; Val
0x1400075dd  add     r8, r8; Size
0x1400075e0  mov     rcx, rsi; void *
0x1400075e3  call    memset_0
0x1400075e8  mov     rcx, r15; hToken
0x1400075eb  mov     [rsp+0D8h+nSize], 202h
0x1400075f6  call    cs:__imp_ImpersonateLoggedOnUser
0x1400075fc  test    eax, eax
0x1400075fe  jnz     short loc_14000760D
0x140007600  call    cs:__imp_GetLastError
0x140007606  mov     edi, eax
0x140007608  jmp     loc_140007A83
0x14000760d  mov     [rsp+0D8h+hTemplateFile], rbx; hTemplateFile
0x140007612  xor     r9d, r9d; lpSecurityAttributes
0x140007615  mov     [rsp+0D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000761d  mov     edx, 80000000h; dwDesiredAccess
0x140007622  mov     r8d, 5; dwShareMode
0x140007628  mov     [rsp+0D8h+dwCreationDisposition], 3; dwCreationDisposition
0x140007630  mov     rcx, r13; lpFileName
0x140007633  call    cs:__imp_CreateFileW
0x140007639  mov     rbp, rax
0x14000763c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140007640  jnz     loc_140007A73
0x140007646  call    cs:__imp_GetLastError
0x14000764c  mov     edi, eax
0x14000764e  cmp     eax, 0D05D0006h
0x140007653  jz      loc_1400077BB
0x140007659  cmp     eax, 0D05D0002h
0x14000765e  jz      loc_1400077BB
0x140007664  cmp     eax, 0D0000388h
0x140007669  jz      loc_1400077BB
0x14000766f  cmp     eax, 0D0000224h
0x140007674  jz      loc_1400077BB
0x14000767a  add     eax, 2FFFFFA1h
0x14000767f  mov     ecx, 44821h
0x140007684  cmp     eax, 12h
0x140007687  ja      short loc_140007692
0x140007689  bt      ecx, eax
0x14000768c  jb      loc_1400077BB
0x140007692  cmp     edi, 0D0000022h
0x140007698  jz      loc_1400077BB
0x14000769e  cmp     edi, 0C05D0006h
0x1400076a4  jz      loc_1400077BB
0x1400076aa  lea     eax, [rdi+3FA2FFFEh]
0x1400076b0  cmp     eax, 2
0x1400076b3  jbe     loc_1400077BB
0x1400076b9  cmp     edi, 0C000042Dh
0x1400076bf  jz      loc_1400077BB
0x1400076c5  cmp     edi, 0C0000388h
0x1400076cb  jz      loc_1400077BB
0x1400076d1  cmp     edi, 0C0000224h
0x1400076d7  jz      loc_1400077BB
0x1400076dd  lea     eax, [rdi+3FFFFFA1h]
0x1400076e3  cmp     eax, 12h
0x1400076e6  ja      short loc_1400076F1
0x1400076e8  bt      ecx, eax
0x1400076eb  jb      loc_1400077BB
0x1400076f1  cmp     edi, 0C0000022h
0x1400076f7  jz      loc_1400077BB
0x1400076fd  cmp     edi, 80090361h
0x140007703  jz      loc_1400077BB
0x140007709  cmp     edi, 80090350h
0x14000770f  jz      loc_1400077BB
0x140007715  cmp     edi, 8009030Eh
0x14000771b  jz      loc_1400077BB
0x140007721  cmp     edi, 8009030Ch
0x140007727  jz      loc_1400077BB
0x14000772d  cmp     edi, 800708C2h
0x140007733  jz      loc_1400077BB
0x140007739  cmp     edi, 80070791h
0x14000773f  jz      short loc_1400077BB
0x140007741  cmp     edi, 80070773h
0x140007747  jz      short loc_1400077BB
0x140007749  cmp     edi, 80070532h
0x14000774f  jz      short loc_1400077BB
0x140007751  lea     eax, [rdi+7FF8FB0Fh]
0x140007757  mov     rcx, 2010800000000081h
0x140007761  cmp     eax, 3Dh ; '='
0x140007764  ja      short loc_14000776C
0x140007766  bt      rcx, rax
0x14000776a  jb      short loc_1400077BB
0x14000776c  cmp     edi, 80070056h
0x140007772  jz      short loc_1400077BB
0x140007774  cmp     edi, 80070005h
0x14000777a  jz      short loc_1400077BB
0x14000777c  cmp     edi, 8C2h
0x140007782  jz      short loc_1400077BB
0x140007784  cmp     edi, 791h
0x14000778a  jz      short loc_1400077BB
0x14000778c  cmp     edi, 773h
0x140007792  jz      short loc_1400077BB
0x140007794  cmp     edi, 532h
0x14000779a  jz      short loc_1400077BB
0x14000779c  lea     eax, [rdi-4F1h]
0x1400077a2  cmp     eax, 3Dh ; '='
0x1400077a5  ja      short loc_1400077AD
0x1400077a7  bt      rcx, rax
0x1400077ab  jb      short loc_1400077BB
0x1400077ad  cmp     edi, 56h ; 'V'
0x1400077b0  jz      short loc_1400077BB
0x1400077b2  cmp     edi, 5
0x1400077b5  jnz     loc_140007A75
0x1400077bb  mov     edx, r12d; Ch
0x1400077be  mov     rcx, r13; Str
0x1400077c1  call    cs:__imp_wcsrchr
0x1400077c7  mov     r12, rax
0x1400077ca  test    rax, rax
0x1400077cd  jz      short loc_1400077D2
0x1400077cf  mov     [rax], bx
0x1400077d2  mov     rcx, [r14+10h]; hwndOwner
0x1400077d6  lea     r8, [rsi+404h]; lpPassword
0x1400077dd  mov     r9, rsi; lpUserName
0x1400077e0  mov     [rsp+0D8h+NetResource.dwType], 1
0x1400077e8  lea     rdx, [rsp+0D8h+NetResource]; lpNetResource
0x1400077ed  mov     [rsp+0D8h+NetResource.lpRemoteName], r13
0x1400077f2  mov     [rsp+0D8h+dwCreationDisposition], 18h; dwFlags
0x1400077fa  call    cs:__imp_WNetAddConnection3W
0x140007800  mov     edi, eax
0x140007802  mov     ecx, 202h
0x140007807  lea     rax, [rsi+404h]
0x14000780e  mov     [rax], bl
0x140007810  lea     rax, [rax+1]
0x140007814  sub     rcx, 1
0x140007818  jnz     short loc_14000780E
0x14000781a  test    r12, r12
0x14000781d  jz      short loc_140007826
0x14000781f  mov     word ptr [r12], 5Ch ; '\'
0x140007826  mov     r12d, 5Ch ; '\'
0x14000782c  cmp     edi, 0C05D0002h
0x140007832  jz      loc_14000760D
0x140007838  cmp     edi, 0D05D0002h
0x14000783e  jz      loc_14000760D
0x140007844  cmp     edi, 4F8h
0x14000784a  jz      loc_14000760D
0x140007850  cmp     edi, 800704F8h
0x140007856  jz      loc_14000760D
0x14000785c  cmp     edi, 0C05D0006h
0x140007862  jz      loc_14000760D
0x140007868  cmp     edi, 0D05D0006h
0x14000786e  jz      loc_14000760D
0x140007874  cmp     edi, 0C05D0003h
0x14000787a  jz      loc_14000760D
0x140007880  cmp     edi, 0C05D0004h
0x140007886  jz      loc_14000760D
0x14000788c  cmp     edi, 791h
0x140007892  jz      loc_14000760D
0x140007898  cmp     edi, 80070791h
0x14000789e  jz      loc_14000760D
0x1400078a4  cmp     edi, 52Eh
0x1400078aa  jz      loc_14000760D
0x1400078b0  cmp     edi, 8007052Eh
0x1400078b6  jz      loc_14000760D
0x1400078bc  cmp     edi, 0C000006Dh
0x1400078c2  jz      loc_14000760D
0x1400078c8  cmp     edi, 0D000006Dh
0x1400078ce  jz      loc_14000760D
0x1400078d4  cmp     edi, 5
0x1400078d7  jz      loc_14000760D
0x1400078dd  cmp     edi, 80070005h
0x1400078e3  jz      loc_14000760D
0x1400078e9  cmp     edi, 0C0000022h
0x1400078ef  jz      loc_14000760D
0x1400078f5  cmp     edi, 0D0000022h
0x1400078fb  jz      loc_14000760D
0x140007901  cmp     edi, 56h ; 'V'
0x140007904  jz      loc_14000760D
0x14000790a  cmp     edi, 80070056h
0x140007910  jz      loc_14000760D
0x140007916  cmp     edi, 0C000006Ah
0x14000791c  jz      loc_14000760D
0x140007922  cmp     edi, 0D000006Ah
0x140007928  jz      loc_14000760D
0x14000792e  cmp     edi, 0C0000064h
0x140007934  jz      loc_14000760D
0x14000793a  cmp     edi, 0D0000064h
0x140007940  jz      loc_14000760D
0x140007946  cmp     edi, 525h
0x14000794c  jz      loc_14000760D
0x140007952  cmp     edi, 80070525h
0x140007958  jz      loc_14000760D
0x14000795e  cmp     edi, 520h
0x140007964  jz      loc_14000760D
0x14000796a  cmp     edi, 80070520h
0x140007970  jz      loc_14000760D
0x140007976  cmp     edi, 0C000005Fh
0x14000797c  jz      loc_14000760D
0x140007982  cmp     edi, 0D000005Fh
0x140007988  jz      loc_14000760D
0x14000798e  cmp     edi, 8009030Eh
0x140007994  jz      loc_14000760D
0x14000799a  cmp     edi, 8009030Ch
0x1400079a0  jz      loc_14000760D
0x1400079a6  cmp     edi, 80090361h
0x1400079ac  jz      loc_14000760D
0x1400079b2  cmp     edi, 0C000042Dh
0x1400079b8  jz      loc_14000760D
0x1400079be  cmp     edi, 4F1h
0x1400079c4  jz      loc_14000760D
0x1400079ca  cmp     edi, 800704F1h
0x1400079d0  jz      loc_14000760D
0x1400079d6  cmp     edi, 0C0000388h
0x1400079dc  jz      loc_14000760D
0x1400079e2  cmp     edi, 0D0000388h
0x1400079e8  jz      loc_14000760D
0x1400079ee  cmp     edi, 80090350h
0x1400079f4  jz      loc_14000760D
0x1400079fa  cmp     edi, 532h
0x140007a00  jz      loc_14000760D
0x140007a06  cmp     edi, 80070532h
0x140007a0c  jz      loc_14000760D
0x140007a12  cmp     edi, 0C0000071h
0x140007a18  jz      loc_14000760D
0x140007a1e  cmp     edi, 0D0000071h
0x140007a24  jz      loc_14000760D
0x140007a2a  cmp     edi, 773h
0x140007a30  jz      loc_14000760D
0x140007a36  cmp     edi, 80070773h
0x140007a3c  jz      loc_14000760D
0x140007a42  cmp     edi, 0C0000224h
0x140007a48  jz      loc_14000760D
0x140007a4e  cmp     edi, 0D0000224h
0x140007a54  jz      loc_14000760D
  ... truncated ...
```
