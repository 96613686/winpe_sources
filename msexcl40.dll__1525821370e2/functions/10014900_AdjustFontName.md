# AdjustFontName

- ea: `0x10014900`
- end: `0x10014be1`
- name: `AdjustFontName`
- size: `737`
- prototype: `char *__fastcall(int, signed int, void *Src, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x10014c50`

## callees

- `0x10014900`
- `0x1003298b`
- `0x10035510`
- `0x10035530`
- `0x10035b40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10014a14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10014a14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10014a4f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10014a7c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10014a4f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10014a7c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x100149e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x100149e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10014991`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x10014991`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10014a37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10014a37`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10014adf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10014adf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100149d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100149d5`

## string_xrefs

- `0x1001498c`: `MSJINT40.DLL`
- `0x100149a0`: `MSJINT40.DLL`

## pseudocode

```c
char *__fastcall AdjustFontName(int a1, signed int a2, void *Src, char *a4)
{
  int v5; // ebx
  size_t v6; // ecx
  FARPROC CchLszOfId2; // esi
  HMODULE Library; // esi
  int v10; // kr08_4
  unsigned int v11; // eax
  char *v12; // esi
  char *result; // eax
  int v14; // [esp+Ch] [ebp-524h]
  size_t v15; // [esp+14h] [ebp-51Ch]
  int v16; // [esp+18h] [ebp-518h] BYREF
  LPCSTR lpLibFileName; // [esp+1Ch] [ebp-514h]
  char v18; // [esp+20h] [ebp-510h] BYREF
  int v19; // [esp+228h] [ebp-308h]
  WCHAR WideCharStr[256]; // [esp+22Ch] [ebp-304h] BYREF
  CHAR MultiByteStr[256]; // [esp+42Ch] [ebp-104h] BYREF

  v5 = 0;
  v6 = 0;
  v14 = a1;
  v15 = 0;
  switch ( a1 )
  {
    case 3:
    case 4:
      v5 = 6;
      v6 = 7;
      goto LABEL_6;
    case 5:
      v6 = 15;
      goto LABEL_5;
    case 8:
    case 9:
      v6 = 16;
LABEL_5:
      v5 = 14;
LABEL_6:
      v15 = v6;
      break;
    default:
      break;
  }
  memcpy(a4, Src, v6);
  CchLszOfId2 = (FARPROC)hFile;
  if ( hFile )
  {
LABEL_21:
    ((void (__thiscall *)(FARPROC, int, WCHAR *, int))CchLszOfId2)(CchLszOfId2, 10104, WideCharStr, 256);
    if ( dword_1003AE54 )
    {
      FreeLibrary(dword_1003AE54);
      dword_1003AE54 = 0;
      hFile = 0;
    }
    goto LABEL_23;
  }
  if ( wrap )
  {
    Library = LoadLibraryExW(L"MSJINT40.DLL", hFile, 8u);
  }
  else
  {
    v16 = 0;
    lpLibFileName = 0;
    CStrIn::Init((CStrIn *)&v16, L"MSJINT40.DLL", -1);
    if ( v19 < 260 )
    {
      Library = LoadLibraryExA(lpLibFileName, 0, 8u);
    }
    else
    {
      SetLastError(0xA1u);
      Library = 0;
    }
    if ( lpLibFileName != &v18 && (unsigned int)lpLibFileName >> 16 && v16 != -1 )
      _free((void *)lpLibFileName);
    lpLibFileName = 0;
  }
  dword_1003AE54 = Library;
  if ( Library )
  {
    CchLszOfId2 = GetProcAddress(Library, "CchLszOfId2");
    hFile = CchLszOfId2;
    if ( !CchLszOfId2 )
    {
      FreeLibrary(dword_1003AE54);
      goto LABEL_23;
    }
    goto LABEL_21;
  }
LABEL_23:
  v10 = wcslen(WideCharStr);
  if ( v14 >= 8 )
  {
    a4[v5] = v10;
    v12 = &a4[v5];
    memcpy(&a4[v15], WideCharStr, 2 * v10 + 2);
  }
  else
  {
    if ( a2 == 1200 )
      v11 = WideCharToMultiByte(0, 0, WideCharStr, v10, MultiByteStr, 256, 0, 0);
    else
      v11 = WideCharToMultiByte(a2, 0, WideCharStr, v10, MultiByteStr, 256, 0, 0);
    if ( v11 >= 0x100 )
      __report_rangecheckfailure();
    v12 = &a4[v5];
    MultiByteStr[v11] = 0;
    a4[v5] = v11;
    memcpy(&a4[v15], MultiByteStr, v11 + 1);
  }
  if ( a2 > 1250 )
  {
    switch ( a2 )
    {
      case 1251:
        *(v12 - 2) = -52;
        break;
      case 1253:
        *(v12 - 2) = -95;
        break;
      case 1254:
        *(v12 - 2) = -94;
        break;
      case 1255:
        *(v12 - 2) = -79;
        break;
      case 1256:
        *(v12 - 2) = -78;
        break;
      case 1257:
        *(v12 - 2) = -70;
        break;
      default:
LABEL_45:
        *(v12 - 2) = 0;
        break;
    }
  }
  else if ( a2 == 1250 )
  {
    *(v12 - 2) = -18;
  }
  else
  {
    switch ( a2 )
    {
      case 932:
        *(v12 - 2) = 0x80;
        break;
      case 936:
        *(v12 - 2) = -122;
        break;
      case 949:
        *(v12 - 2) = -127;
        break;
      case 950:
        *(v12 - 2) = -120;
        break;
      default:
        goto LABEL_45;
    }
  }
  result = a4;
  a4[v5 - 3] = 32;
  return result;
}

```

## disassembly

```asm
0x10014900  mov     edi, edi
0x10014902  push    ebp
0x10014903  mov     ebp, esp
0x10014905  sub     esp, 524h
0x1001490b  mov     eax, ___security_cookie
0x10014910  xor     eax, ebp
0x10014912  mov     [ebp+var_4], eax
0x10014915  push    ebx
0x10014916  mov     eax, ecx
0x10014918  xor     ebx, ebx
0x1001491a  push    esi
0x1001491b  mov     esi, [ebp+arg_4]
0x1001491e  xor     ecx, ecx
0x10014920  mov     [ebp+var_524], eax
0x10014926  add     eax, 0FFFFFFFDh; switch 7 cases
0x10014929  mov     [ebp+var_520], esi
0x1001492f  mov     [ebp+var_51C], ecx
0x10014935  push    edi
0x10014936  mov     edi, edx
0x10014938  mov     edx, [ebp+Src]
0x1001493b  cmp     eax, 6
0x1001493e  ja      short def_10014940; jumptable 10014940 default case, cases 6,7
0x10014940  jmp     ds:jpt_10014940[eax*4]; switch jump
0x10014947  mov     ebx, 6; jumptable 10014940 cases 3,4
0x1001494c  lea     ecx, [ebx+1]
0x1001494f  jmp     short loc_10014962
0x10014951  mov     ecx, 0Fh; jumptable 10014940 case 5
0x10014956  jmp     short loc_1001495D
0x10014958  mov     ecx, 10h; jumptable 10014940 cases 8,9
0x1001495d  mov     ebx, 0Eh
0x10014962  mov     [ebp+var_51C], ecx
0x10014968  push    ecx; jumptable 10014940 default case, cases 6,7
0x10014969  push    edx; Src
0x1001496a  push    esi; void *
0x1001496b  call    _memcpy
0x10014970  mov     esi, CchLszOfId2
0x10014976  add     esp, 0Ch
0x10014979  test    esi, esi
0x1001497b  jnz     loc_10014A57
0x10014981  cmp     ?wrap@@3VWrapper@@A, esi; Wrapper wrap
0x10014987  jz      short loc_1001499E
0x10014989  push    8; dwFlags
0x1001498b  push    esi; hFile
0x1001498c  push    offset LibFileName; "MSJINT40.DLL"
0x10014991  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x10014997  mov     esi, eax
0x10014999  jmp     loc_10014A27
0x1001499e  push    0FFFFFFFFh; int
0x100149a0  push    offset LibFileName; "MSJINT40.DLL"
0x100149a5  lea     ecx, [ebp+var_518]; this
0x100149ab  mov     [ebp+var_518], 0
0x100149b5  mov     [ebp+lpLibFileName], 0
0x100149bf  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x100149c4  cmp     [ebp+var_308], 104h
0x100149ce  jl      short loc_100149DF
0x100149d0  push    0A1h; dwErrCode
0x100149d5  call    ds:__imp__SetLastError@4; SetLastError(x)
0x100149db  xor     esi, esi
0x100149dd  jmp     short loc_100149F1
0x100149df  push    8; dwFlags
0x100149e1  push    0; hFile
0x100149e3  push    [ebp+lpLibFileName]; lpLibFileName
0x100149e9  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x100149ef  mov     esi, eax
0x100149f1  mov     ecx, [ebp+lpLibFileName]
0x100149f7  lea     eax, [ebp+var_510]
0x100149fd  cmp     ecx, eax
0x100149ff  jz      short loc_10014A1D
0x10014a01  mov     eax, ecx
0x10014a03  shr     eax, 10h
0x10014a06  test    eax, eax
0x10014a08  jz      short loc_10014A1D
0x10014a0a  cmp     [ebp+var_518], 0FFFFFFFFh
0x10014a11  jz      short loc_10014A1D
0x10014a13  push    ecx; Block
0x10014a14  call    ds:__imp__free
0x10014a1a  add     esp, 4
0x10014a1d  mov     [ebp+lpLibFileName], 0
0x10014a27  mov     dword_1003AE54, esi
0x10014a2d  test    esi, esi
0x10014a2f  jz      short loc_10014A96
0x10014a31  push    offset ProcName; "CchLszOfId2"
0x10014a36  push    esi; hModule
0x10014a37  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10014a3d  mov     esi, eax
0x10014a3f  mov     CchLszOfId2, esi
0x10014a45  test    esi, esi
0x10014a47  jnz     short loc_10014A57
0x10014a49  push    dword_1003AE54; hLibModule
0x10014a4f  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10014a55  jmp     short loc_10014A96
0x10014a57  push    100h
0x10014a5c  lea     eax, [ebp+WideCharStr]
0x10014a62  mov     ecx, esi
0x10014a64  push    eax
0x10014a65  push    2778h
0x10014a6a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10014a70  call    esi ; CchLszOfId2
0x10014a72  mov     eax, dword_1003AE54
0x10014a77  test    eax, eax
0x10014a79  jz      short loc_10014A96
0x10014a7b  push    eax; hLibModule
0x10014a7c  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10014a82  mov     dword_1003AE54, 0
0x10014a8c  mov     CchLszOfId2, 0
0x10014a96  lea     ecx, [ebp+WideCharStr]
0x10014a9c  lea     edx, [ecx+2]
0x10014a9f  nop
0x10014aa0  mov     ax, [ecx]
0x10014aa3  add     ecx, 2
0x10014aa6  test    ax, ax
0x10014aa9  jnz     short loc_10014AA0
0x10014aab  sub     ecx, edx
0x10014aad  sar     ecx, 1
0x10014aaf  cmp     [ebp+var_524], 8
0x10014ab6  jge     short loc_10014B17
0x10014ab8  lea     eax, [ebp+MultiByteStr]
0x10014abe  push    0; lpUsedDefaultChar
0x10014ac0  push    0; lpDefaultChar
0x10014ac2  push    100h; cbMultiByte
0x10014ac7  push    eax; lpMultiByteStr
0x10014ac8  lea     eax, [ebp+WideCharStr]
0x10014ace  push    ecx; cchWideChar
0x10014acf  push    eax; lpWideCharStr
0x10014ad0  push    0; dwFlags
0x10014ad2  cmp     edi, 4B0h
0x10014ad8  jz      short loc_10014ADD
0x10014ada  push    edi
0x10014adb  jmp     short loc_10014ADF
0x10014add  push    0; CodePage
0x10014adf  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10014ae5  cmp     eax, 100h
0x10014aea  jnb     loc_10014BDC
0x10014af0  mov     edx, [ebp+var_520]
0x10014af6  mov     ecx, [ebp+var_51C]
0x10014afc  lea     esi, [edx+ebx]
0x10014aff  mov     [ebp+eax+MultiByteStr], 0
0x10014b07  add     ecx, edx
0x10014b09  mov     [esi], al
0x10014b0b  inc     eax
0x10014b0c  push    eax
0x10014b0d  lea     eax, [ebp+MultiByteStr]
0x10014b13  push    eax
0x10014b14  push    ecx
0x10014b15  jmp     short loc_10014B3B
0x10014b17  mov     edx, [ebp+var_520]
0x10014b1d  lea     eax, ds:2[ecx*2]
0x10014b24  push    eax; Size
0x10014b25  lea     eax, [ebp+WideCharStr]
0x10014b2b  mov     [edx+ebx], cl
0x10014b2e  push    eax; Src
0x10014b2f  mov     eax, [ebp+var_51C]
0x10014b35  lea     esi, [edx+ebx]
0x10014b38  add     eax, edx
0x10014b3a  push    eax; void *
0x10014b3b  call    _memcpy
0x10014b40  add     esp, 0Ch
0x10014b43  cmp     edi, 4E2h
0x10014b49  jg      short loc_10014B84
0x10014b4b  jz      short loc_10014B7E
0x10014b4d  lea     eax, [edi-3A4h]; switch 19 cases
0x10014b53  cmp     eax, 12h
0x10014b56  ja      short def_10014B5F; jumptable 10014B5F default case, cases 933-935,937-948
0x10014b58  movzx   eax, ds:byte_10014C14[eax]
0x10014b5f  jmp     ds:jpt_10014B5F[eax*4]; switch jump
0x10014b66  mov     byte ptr [esi-2], 80h; jumptable 10014B5F case 932
0x10014b6a  jmp     short loc_10014BBE
0x10014b6c  mov     byte ptr [esi-2], 86h; jumptable 10014B5F case 936
0x10014b70  jmp     short loc_10014BBE
0x10014b72  mov     byte ptr [esi-2], 81h; jumptable 10014B5F case 949
0x10014b76  jmp     short loc_10014BBE
0x10014b78  mov     byte ptr [esi-2], 88h; jumptable 10014B5F case 950
0x10014b7c  jmp     short loc_10014BBE
0x10014b7e  mov     byte ptr [esi-2], 0EEh
0x10014b82  jmp     short loc_10014BBE
0x10014b84  lea     eax, [edi-4E3h]; switch 7 cases
0x10014b8a  cmp     eax, 6
0x10014b8d  ja      short def_10014B5F; jumptable 10014B5F default case, cases 933-935,937-948
0x10014b8f  jmp     ds:jpt_10014B8F[eax*4]; switch jump
0x10014b96  mov     byte ptr [esi-2], 0CCh; jumptable 10014B8F case 1251
0x10014b9a  jmp     short loc_10014BBE
0x10014b9c  mov     byte ptr [esi-2], 0A1h; jumptable 10014B8F case 1253
0x10014ba0  jmp     short loc_10014BBE
0x10014ba2  mov     byte ptr [esi-2], 0A2h; jumptable 10014B8F case 1254
0x10014ba6  jmp     short loc_10014BBE
0x10014ba8  mov     byte ptr [esi-2], 0B1h; jumptable 10014B8F case 1255
0x10014bac  jmp     short loc_10014BBE
0x10014bae  mov     byte ptr [esi-2], 0B2h; jumptable 10014B8F case 1256
0x10014bb2  jmp     short loc_10014BBE
0x10014bb4  mov     byte ptr [esi-2], 0BAh; jumptable 10014B8F case 1257
0x10014bb8  jmp     short loc_10014BBE
0x10014bba  mov     byte ptr [esi-2], 0; jumptable 10014B5F default case, cases 933-935,937-948
0x10014bbe  mov     eax, [ebp+var_520]
0x10014bc4  mov     ecx, [ebp+var_4]
0x10014bc7  pop     edi
0x10014bc8  pop     esi
0x10014bc9  mov     byte ptr [ebx+eax-3], 20h ; ' '
0x10014bce  xor     ecx, ebp; StackCookie
0x10014bd0  pop     ebx
0x10014bd1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10014bd6  mov     esp, ebp
0x10014bd8  pop     ebp
0x10014bd9  retn    8
0x10014bdc  call    ___report_rangecheckfailure
```
