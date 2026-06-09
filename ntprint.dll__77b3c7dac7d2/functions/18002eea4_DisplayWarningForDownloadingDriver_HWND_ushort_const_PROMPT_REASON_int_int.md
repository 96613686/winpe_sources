# DisplayWarningForDownloadingDriver(HWND__ *,ushort const *,PROMPT_REASON,int,int *)

- ea: `0x18002eea4`
- end: `0x18002f35d`
- name: `?DisplayWarningForDownloadingDriver@@YAJPEAUHWND__@@PEBGW4PROMPT_REASON@@HPEAH@Z`
- size: `1209`
- prototype: `int __high(HWND, const unsigned __int16 *, enum PROMPT_REASON, int, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f9e0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x18000d7f0`
- `0x18001bc44`
- `0x18001e470`
- `0x180020418`
- `0x1800206ec`
- `0x18002e54c`
- `0x18002eea4`
- `0x18002f364`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f1b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f1b8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f30e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f30e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f11f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f11f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002f111`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002f111`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f015`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f031`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f03f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f04f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f06a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f13c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f152`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f015`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f031`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f03f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f04f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f06a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f13c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f152`

## string_xrefs

- `0x18002f1ae`: `TaskDialogIndirect`
- `0x18002f188`: `comctl32.dll`

## pseudocode

```c
__int64 __fastcall DisplayWarningForDownloadingDriver(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        _DWORD *a5)
{
  int v5; // edi
  NCoreLibrary *v7; // rcx
  signed int LastErrorAsFailHR; // ebx
  void *v9; // r13
  NCoreLibrary *v10; // rcx
  void *v11; // r12
  NCoreLibrary *v12; // rcx
  void *v13; // rsi
  void *v14; // r15
  NCoreLibrary *v15; // rcx
  NCoreLibrary *v16; // rcx
  const wchar_t *v17; // rax
  wchar_t *v18; // rsi
  HLOCAL v19; // r14
  wchar_t *v20; // rax
  wchar_t *v21; // r14
  UINT v22; // r8d
  NCoreLibrary *v23; // rcx
  void *v24; // rdi
  signed int LastError; // eax
  NCoreLibrary *v26; // rcx
  NCoreLibrary *v27; // rcx
  HMODULE LibraryW; // rdi
  NCoreLibrary *v29; // rcx
  FARPROC ProcAddress; // rsi
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL IsMember; // [rsp+44h] [rbp-BCh] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h]
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v36; // [rsp+54h] [rbp-ACh]
  __int64 StringFromRcFile; // [rsp+58h] [rbp-A8h]
  HLOCAL lpBuffer; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v39; // [rsp+68h] [rbp-98h]
  __int64 v40; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v41; // [rsp+78h] [rbp-88h]
  _DWORD *v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+94h] [rbp-6Ch]
  int v45; // [rsp+A4h] [rbp-5Ch]
  void *v46; // [rsp+ACh] [rbp-54h]
  __int64 v47; // [rsp+B4h] [rbp-4Ch]
  void *v48; // [rsp+BCh] [rbp-44h]
  HLOCAL v49; // [rsp+C4h] [rbp-3Ch]
  int v50; // [rsp+CCh] [rbp-34h]
  __int128 *p_Arguments; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+D8h] [rbp-28h]
  void *v53; // [rsp+ECh] [rbp-14h]
  __int64 (__fastcall *v54)(HWND, int, __int64, __int64, _DWORD *); // [rsp+11Ch] [rbp+1Ch]
  _DWORD *v55; // [rsp+124h] [rbp+24h]
  _DWORD v56[4]; // [rsp+130h] [rbp+30h] BYREF
  __int128 Arguments; // [rsp+140h] [rbp+40h] BYREF
  wchar_t *v58; // [rsp+150h] [rbp+50h]

  v5 = 0;
  v39 = a4;
  v36 = a3;
  v41 = a2;
  v40 = a1;
  v42 = a5;
  IsMember = 0;
  v32 = 0;
  if ( !a2 || !a5 )
    return (unsigned int)-2147024809;
  *a5 = 1;
  if ( (unsigned int)IsLocalAdmin(&IsMember) )
  {
    LastErrorAsFailHR = 0;
  }
  else
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v7);
    if ( LastErrorAsFailHR < 0 )
      return (unsigned int)LastErrorAsFailHR;
  }
  if ( IsMember )
  {
    LastErrorAsFailHR = CheckRegistryKeyForWarningCheckBox(&v32);
    if ( LastErrorAsFailHR < 0 )
      return (unsigned int)LastErrorAsFailHR;
    v5 = v32;
  }
  if ( v5 )
    return (unsigned int)LastErrorAsFailHR;
  lpBuffer = 0;
  v9 = 0;
  hMem = (HLOCAL)GetStringFromRcFile(0x57Fu);
  if ( hMem || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v10), LastErrorAsFailHR >= 0) )
  {
    v11 = 0;
    StringFromRcFile = GetStringFromRcFile(0x57Eu);
    v13 = (void *)StringFromRcFile;
    if ( StringFromRcFile
      || (v14 = 0, LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v12), LastErrorAsFailHR >= 0) )
    {
      v14 = (void *)GetStringFromRcFile(0x57Du);
      if ( v14 || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v15), LastErrorAsFailHR >= 0) )
      {
        v11 = (void *)GetStringFromRcFile(0x581u);
        if ( v11 || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v16), LastErrorAsFailHR >= 0) )
        {
          v17 = (const wchar_t *)AllocStr(a2);
          v18 = (wchar_t *)v17;
          if ( v17 )
          {
            v20 = wcsrchr(v17, 0x5Cu);
            v21 = v20;
            if ( v20 )
            {
              v22 = 1400;
              *v20 = 0;
              if ( v36 )
              {
                if ( v36 == 1 )
                {
                  v22 = 1403;
                }
                else if ( v36 == 3 )
                {
                  v22 = 1404;
                }
              }
              v24 = (void *)GetStringFromRcFile(v22);
              if ( v24 || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v23), LastErrorAsFailHR >= 0) )
              {
                *(_QWORD *)&Arguments = v18;
                *((_QWORD *)&Arguments + 1) = v21 + 1;
                v58 = v18;
                if ( FormatMessageW(0x2500u, v24, 0, 0, (LPWSTR)&lpBuffer, 0, (va_list *)&Arguments) )
                {
                  LastErrorAsFailHR = 0;
                }
                else
                {
                  LastError = GetLastError();
                  LastErrorAsFailHR = LastError;
                  if ( LastError > 0 )
                    LastErrorAsFailHR = (unsigned __int16)LastError | 0x80070000;
                }
                if ( v24 )
                  LocalFree(v24);
              }
              *v21 = 92;
            }
            else
            {
              LastErrorAsFailHR = -2147024809;
            }
            LocalFree(v18);
            if ( LastErrorAsFailHR >= 0 )
            {
              if ( !IsMember
                || (v9 = (void *)GetStringFromRcFile(0x580u)) != 0
                || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v26), LastErrorAsFailHR >= 0) )
              {
                LibraryW = IsolationAwareLoadLibraryW(L"comctl32.dll");
                if ( LibraryW || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v27), LastErrorAsFailHR >= 0) )
                {
                  ProcAddress = GetProcAddress(LibraryW, "TaskDialogIndirect");
                  if ( ProcAddress
                    || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v29), LastErrorAsFailHR >= 0) )
                  {
                    v32 = 0;
                    v35 = 0;
                    memset_0(&v43, 0, 0xA0u);
                    v58 = (wchar_t *)StringFromRcFile;
                    v44 = v40;
                    p_Arguments = &Arguments;
                    v54 = TaskDialogSecurityWarningDlgProc;
                    v49 = lpBuffer;
                    v56[1] = IsMember;
                    v55 = v56;
                    v56[2] = 0;
                    v56[0] = 0;
                    v19 = hMem;
                    HIDWORD(Arguments) = 2;
                    v50 = 2;
                    v52 = 2;
                    LODWORD(Arguments) = 1;
                    *(_QWORD *)((char *)&Arguments + 4) = hMem;
                    v43 = 160;
                    v45 = 8;
                    v47 = 65530;
                    v46 = v14;
                    v48 = v11;
                    v53 = v9;
                    LastErrorAsFailHR = ((__int64 (__fastcall *)(int *, int *, _QWORD, unsigned __int64))ProcAddress)(
                                          &v43,
                                          &v32,
                                          0,
                                          (unsigned __int64)&v35 & -(__int64)(IsMember != 0));
                    if ( LastErrorAsFailHR == -2147024891 )
                    {
                      v44 = 0;
                      LastErrorAsFailHR = ((__int64 (__fastcall *)(int *, int *, _QWORD, unsigned __int64))ProcAddress)(
                                            &v43,
                                            &v32,
                                            0,
                                            (unsigned __int64)&v35 & -(__int64)(IsMember != 0));
                    }
                    if ( LastErrorAsFailHR >= 0 )
                    {
                      if ( v32 == 1 )
                      {
                        LastErrorAsFailHR = v56[0];
                        if ( v56[0] >= 0 )
                          LastErrorAsFailHR = DownloadAndInstallLegacyDriver(v44, v41, v36, v39);
                      }
                      else
                      {
                        LastErrorAsFailHR = -2147023673;
                      }
                    }
                  }
                  else
                  {
                    v19 = hMem;
                  }
                  if ( LibraryW )
                    FreeLibrary(LibraryW);
                }
                else
                {
                  v19 = hMem;
                }
                v13 = (void *)StringFromRcFile;
                *v42 = 0;
                goto LABEL_22;
              }
            }
          }
          else
          {
            LastErrorAsFailHR = -2147024882;
          }
          v13 = (void *)StringFromRcFile;
        }
      }
    }
    v19 = hMem;
LABEL_22:
    if ( v19 )
      LocalFree(v19);
    if ( v13 )
      LocalFree(v13);
    if ( v14 )
      LocalFree(v14);
    if ( v11 )
      LocalFree(v11);
  }
  if ( lpBuffer )
  {
    LocalFree(lpBuffer);
    lpBuffer = 0;
  }
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18002eea4  mov     [rsp-8+arg_18], rbx
0x18002eea9  push    rbp
0x18002eeaa  push    rsi
0x18002eeab  push    rdi
0x18002eeac  push    r12
0x18002eeae  push    r13
0x18002eeb0  push    r14
0x18002eeb2  push    r15
0x18002eeb4  lea     rbp, [rsp-60h]
0x18002eeb9  sub     rsp, 160h
0x18002eec0  mov     rax, cs:__security_cookie
0x18002eec7  xor     rax, rsp
0x18002eeca  mov     [rbp+90h+var_38], rax
0x18002eece  mov     rax, [rbp+90h+arg_20]
0x18002eed5  xor     edi, edi
0x18002eed7  mov     [rsp+190h+var_128], r9d
0x18002eedc  mov     r14, rdx
0x18002eedf  mov     [rsp+190h+var_13C], r8d
0x18002eee4  mov     [rsp+190h+var_118], rdx
0x18002eee9  mov     [rsp+190h+var_120], rcx
0x18002eeee  mov     [rbp+90h+var_110], rax
0x18002eef2  mov     [rsp+190h+IsMember], 0
0x18002eefa  mov     [rsp+190h+var_150], edi
0x18002eefe  test    rdx, rdx
0x18002ef01  jz      loc_18002F32F
0x18002ef07  test    rax, rax
0x18002ef0a  jz      loc_18002F32F
0x18002ef10  lea     rcx, [rsp+190h+IsMember]; IsMember
0x18002ef15  mov     dword ptr [rax], 1
0x18002ef1b  call    IsLocalAdmin
0x18002ef20  test    eax, eax
0x18002ef22  jz      short loc_18002EF28
0x18002ef24  xor     ebx, ebx
0x18002ef26  jmp     short loc_18002EF37
0x18002ef28  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002ef2d  mov     ebx, eax
0x18002ef2f  test    eax, eax
0x18002ef31  js      loc_18002F334
0x18002ef37  cmp     [rsp+190h+IsMember], edi
0x18002ef3b  jz      short loc_18002EF55
0x18002ef3d  lea     rcx, [rsp+190h+var_150]; int *
0x18002ef42  call    ?CheckRegistryKeyForWarningCheckBox@@YAJPEAH@Z; CheckRegistryKeyForWarningCheckBox(int *)
0x18002ef47  mov     ebx, eax
0x18002ef49  test    eax, eax
0x18002ef4b  js      loc_18002F334
0x18002ef51  mov     edi, [rsp+190h+var_150]
0x18002ef55  test    edi, edi
0x18002ef57  jnz     loc_18002F334
0x18002ef5d  mov     ecx, 57Fh; uID
0x18002ef62  mov     [rsp+190h+var_130], 0
0x18002ef6b  xor     r13d, r13d
0x18002ef6e  call    GetStringFromRcFile
0x18002ef73  mov     [rsp+190h+hMem], rax
0x18002ef78  test    rax, rax
0x18002ef7b  jnz     short loc_18002EF8C
0x18002ef7d  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002ef82  mov     ebx, eax
0x18002ef84  test    eax, eax
0x18002ef86  js      loc_18002F045
0x18002ef8c  mov     ecx, 57Eh; uID
0x18002ef91  xor     r12d, r12d
0x18002ef94  call    GetStringFromRcFile
0x18002ef99  mov     [rsp+190h+var_138], rax
0x18002ef9e  mov     rsi, rax
0x18002efa1  test    rax, rax
0x18002efa4  jnz     short loc_18002EFB4
0x18002efa6  xor     r15d, r15d
0x18002efa9  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002efae  mov     ebx, eax
0x18002efb0  test    eax, eax
0x18002efb2  js      short loc_18002F008
0x18002efb4  mov     ecx, 57Dh; uID
0x18002efb9  call    GetStringFromRcFile
0x18002efbe  mov     r15, rax
0x18002efc1  test    rax, rax
0x18002efc4  jnz     short loc_18002EFD1
0x18002efc6  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002efcb  mov     ebx, eax
0x18002efcd  test    eax, eax
0x18002efcf  js      short loc_18002F008
0x18002efd1  mov     ecx, 581h; uID
0x18002efd6  call    GetStringFromRcFile
0x18002efdb  mov     r12, rax
0x18002efde  test    rax, rax
0x18002efe1  jnz     short loc_18002EFEE
0x18002efe3  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002efe8  mov     ebx, eax
0x18002efea  test    eax, eax
0x18002efec  js      short loc_18002F008
0x18002efee  mov     rcx, r14; unsigned __int16 *
0x18002eff1  call    AllocStr
0x18002eff6  mov     rsi, rax
0x18002eff9  test    rax, rax
0x18002effc  jnz     short loc_18002F075
0x18002effe  mov     ebx, 8007000Eh
0x18002f003  mov     rsi, [rsp+190h+var_138]
0x18002f008  mov     r14, [rsp+190h+hMem]
0x18002f00d  test    r14, r14
0x18002f010  jz      short loc_18002F01B
0x18002f012  mov     rcx, r14; hMem
0x18002f015  call    cs:__imp_LocalFree
0x18002f01b  test    rsi, rsi
0x18002f01e  jz      short loc_18002F029
0x18002f020  mov     rcx, rsi; hMem
0x18002f023  call    cs:__imp_LocalFree
0x18002f029  test    r15, r15
0x18002f02c  jz      short loc_18002F037
0x18002f02e  mov     rcx, r15; hMem
0x18002f031  call    cs:__imp_LocalFree
0x18002f037  test    r12, r12
0x18002f03a  jz      short loc_18002F045
0x18002f03c  mov     rcx, r12; hMem
0x18002f03f  call    cs:__imp_LocalFree
0x18002f045  mov     rcx, [rsp+190h+var_130]; hMem
0x18002f04a  test    rcx, rcx
0x18002f04d  jz      short loc_18002F05E
0x18002f04f  call    cs:__imp_LocalFree
0x18002f055  mov     [rsp+190h+var_130], 0
0x18002f05e  test    r13, r13
0x18002f061  jz      loc_18002F334
0x18002f067  mov     rcx, r13; hMem
0x18002f06a  call    cs:__imp_LocalFree
0x18002f070  jmp     loc_18002F334
0x18002f075  mov     edx, 5Ch ; '\'; Ch
0x18002f07a  mov     rcx, rsi; Str
0x18002f07d  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x18002f082  mov     r14, rax
0x18002f085  test    rax, rax
0x18002f088  jz      loc_18002F14A
0x18002f08e  xor     ecx, ecx
0x18002f090  mov     r8d, 578h
0x18002f096  mov     [rax], cx
0x18002f099  mov     eax, [rsp+190h+var_13C]
0x18002f09d  mov     edx, eax
0x18002f09f  test    eax, eax
0x18002f0a1  jz      short loc_18002F0C0
0x18002f0a3  sub     edx, 1
0x18002f0a6  jz      short loc_18002F0BA
0x18002f0a8  sub     edx, 1
0x18002f0ab  jz      short loc_18002F0C0
0x18002f0ad  cmp     edx, 1
0x18002f0b0  jnz     short loc_18002F0C0
0x18002f0b2  mov     r8d, 57Ch
0x18002f0b8  jmp     short loc_18002F0C0
0x18002f0ba  mov     r8d, 57Bh
0x18002f0c0  mov     ecx, r8d; uID
0x18002f0c3  call    GetStringFromRcFile
0x18002f0c8  mov     rdi, rax
0x18002f0cb  test    rax, rax
0x18002f0ce  jnz     short loc_18002F0DB
0x18002f0d0  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f0d5  mov     ebx, eax
0x18002f0d7  test    eax, eax
0x18002f0d9  js      short loc_18002F142
0x18002f0db  lea     rcx, [r14+2]
0x18002f0df  mov     [rbp+90h+var_50], rsi
0x18002f0e3  lea     rax, [rbp+90h+var_50]
0x18002f0e7  mov     [rbp+90h+var_48], rcx
0x18002f0eb  mov     [rsp+190h+Arguments], rax; Arguments
0x18002f0f0  xor     r9d, r9d; dwLanguageId
0x18002f0f3  lea     rax, [rsp+190h+var_130]
0x18002f0f8  mov     [rsp+190h+nSize], r13d; nSize
0x18002f0fd  xor     r8d, r8d; dwMessageId
0x18002f100  mov     [rsp+190h+lpBuffer], rax; lpBuffer
0x18002f105  mov     rdx, rdi; lpSource
0x18002f108  mov     [rbp+90h+var_40], rsi
0x18002f10c  mov     ecx, 2500h; dwFlags
0x18002f111  call    cs:__imp_FormatMessageW
0x18002f117  test    eax, eax
0x18002f119  jz      short loc_18002F11F
0x18002f11b  xor     ebx, ebx
0x18002f11d  jmp     short loc_18002F134
0x18002f11f  call    cs:__imp_GetLastError
0x18002f125  mov     ebx, eax
0x18002f127  test    eax, eax
0x18002f129  jle     short loc_18002F134
0x18002f12b  movzx   ebx, ax
0x18002f12e  or      ebx, 80070000h
0x18002f134  test    rdi, rdi
0x18002f137  jz      short loc_18002F142
0x18002f139  mov     rcx, rdi; hMem
0x18002f13c  call    cs:__imp_LocalFree
0x18002f142  mov     word ptr [r14], 5Ch ; '\'
0x18002f148  jmp     short loc_18002F14F
0x18002f14a  mov     ebx, 80070057h
0x18002f14f  mov     rcx, rsi; hMem
0x18002f152  call    cs:__imp_LocalFree
0x18002f158  test    ebx, ebx
0x18002f15a  js      loc_18002F003
0x18002f160  cmp     [rsp+190h+IsMember], r13d
0x18002f165  jz      short loc_18002F188
0x18002f167  mov     ecx, 580h; uID
0x18002f16c  call    GetStringFromRcFile
0x18002f171  mov     r13, rax
0x18002f174  test    rax, rax
0x18002f177  jnz     short loc_18002F188
0x18002f179  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f17e  mov     ebx, eax
0x18002f180  test    eax, eax
0x18002f182  js      loc_18002F003
0x18002f188  lea     rcx, aComctl32Dll_0; "comctl32.dll"
0x18002f18f  call    IsolationAwareLoadLibraryW
0x18002f194  xor     r14d, r14d
0x18002f197  mov     rdi, rax
0x18002f19a  test    rax, rax
0x18002f19d  jnz     short loc_18002F1AE
0x18002f19f  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f1a4  mov     ebx, eax
0x18002f1a6  test    eax, eax
0x18002f1a8  js      loc_18002F316
0x18002f1ae  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x18002f1b5  mov     rcx, rdi; hModule
0x18002f1b8  call    cs:__imp_GetProcAddress
0x18002f1be  mov     rsi, rax
0x18002f1c1  test    rax, rax
0x18002f1c4  jnz     short loc_18002F1D5
0x18002f1c6  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f1cb  mov     ebx, eax
0x18002f1cd  test    eax, eax
0x18002f1cf  js      loc_18002F301
0x18002f1d5  mov     ebx, 0A0h
0x18002f1da  mov     [rsp+190h+var_150], r14d
0x18002f1df  mov     r8d, ebx; Size
0x18002f1e2  mov     [rsp+190h+var_140], r14d
0x18002f1e7  xor     edx, edx; Val
0x18002f1e9  lea     rcx, [rbp+90h+var_100]; void *
0x18002f1ed  call    memset_0
0x18002f1f2  mov     ecx, [rsp+190h+IsMember]
0x18002f1f6  mov     edx, 2
0x18002f1fb  mov     rax, [rsp+190h+var_138]
0x18002f200  mov     [rbp+90h+var_40], rax
0x18002f204  mov     rax, [rsp+190h+var_120]
0x18002f209  mov     [rbp+90h+var_FC], rax
0x18002f20d  lea     rax, [rbp+90h+var_50]
0x18002f211  mov     [rbp+90h+var_C0], rax
0x18002f215  lea     rax, ?TaskDialogSecurityWarningDlgProc@@YAJPEAUHWND__@@I_K_J2@Z; TaskDialogSecurityWarningDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18002f21c  mov     [rbp+90h+var_74], rax
0x18002f220  mov     rax, [rsp+190h+var_130]
0x18002f225  mov     [rbp+90h+var_CC], rax
0x18002f229  lea     rax, [rbp+90h+var_60]
0x18002f22d  mov     [rbp+90h+var_5C], ecx
0x18002f230  neg     ecx
0x18002f232  mov     [rbp+90h+var_6C], rax
0x18002f236  lea     rcx, [rbp+90h+var_100]
0x18002f23a  sbb     r9, r9
0x18002f23d  mov     [rbp+90h+var_58], r14d
0x18002f241  lea     rax, [rsp+190h+var_140]
0x18002f246  mov     [rbp+90h+var_60], r14d
0x18002f24a  mov     r14, [rsp+190h+hMem]
0x18002f24f  and     r9, rax
0x18002f252  mov     dword ptr [rbp+90h+var_48+4], edx
0x18002f255  mov     rax, rsi
0x18002f258  mov     [rbp+90h+var_C4], edx
0x18002f25b  xor     r8d, r8d
0x18002f25e  mov     [rbp+90h+var_B8], edx
0x18002f261  lea     rdx, [rsp+190h+var_150]
0x18002f266  mov     dword ptr [rbp+90h+var_50], 1
0x18002f26d  mov     [rbp+90h+var_50+4], r14
0x18002f271  mov     [rbp+90h+var_100], ebx
0x18002f274  mov     [rbp+90h+var_EC], 8
0x18002f27b  mov     [rbp+90h+var_DC], 0FFFAh
0x18002f283  mov     [rbp+90h+var_E4], r15
0x18002f287  mov     [rbp+90h+var_D4], r12
0x18002f28b  mov     [rbp+90h+var_A4], r13
0x18002f28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f294  mov     ebx, eax
0x18002f296  cmp     eax, 80070005h
0x18002f29b  jnz     short loc_18002F2CC
0x18002f29d  mov     eax, [rsp+190h+IsMember]
0x18002f2a1  lea     rdx, [rsp+190h+var_150]
0x18002f2a6  neg     eax
0x18002f2a8  mov     [rbp+90h+var_FC], 0
0x18002f2b0  lea     rax, [rsp+190h+var_140]
0x18002f2b5  sbb     r9, r9
0x18002f2b8  lea     rcx, [rbp+90h+var_100]
0x18002f2bc  and     r9, rax
0x18002f2bf  xor     r8d, r8d
0x18002f2c2  mov     rax, rsi
0x18002f2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2ca  mov     ebx, eax
0x18002f2cc  test    ebx, ebx
0x18002f2ce  js      short loc_18002F306
0x18002f2d0  cmp     [rsp+190h+var_150], 1
0x18002f2d5  jz      short loc_18002F2DE
0x18002f2d7  mov     ebx, 800704C7h
0x18002f2dc  jmp     short loc_18002F306
0x18002f2de  mov     ebx, [rbp+90h+var_60]
0x18002f2e1  test    ebx, ebx
0x18002f2e3  js      short loc_18002F306
0x18002f2e5  mov     r9d, [rsp+190h+var_128]
0x18002f2ea  mov     r8d, [rsp+190h+var_13C]
0x18002f2ef  mov     rdx, [rsp+190h+var_118]
0x18002f2f4  mov     rcx, [rbp+90h+var_FC]
0x18002f2f8  call    ?DownloadAndInstallLegacyDriver@@YAJPEAUHWND__@@PEBGW4PROMPT_REASON@@H@Z; DownloadAndInstallLegacyDriver(HWND__ *,ushort const *,PROMPT_REASON,int)
0x18002f2fd  mov     ebx, eax
0x18002f2ff  jmp     short loc_18002F306
0x18002f301  mov     r14, [rsp+190h+hMem]
0x18002f306  test    rdi, rdi
0x18002f309  jz      short loc_18002F31B
0x18002f30b  mov     rcx, rdi; hLibModule
  ... truncated ...
```
