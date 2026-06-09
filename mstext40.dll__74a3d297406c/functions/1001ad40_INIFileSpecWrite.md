# INIFileSpecWrite

- ea: `0x1001ad40`
- end: `0x1001b460`
- name: `INIFileSpecWrite`
- size: `1824`
- prototype: `int __stdcall(LPCWSTR lpFileName, LPCWCH lpWideCharStr, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x1001c380`

## callees

- `0x10008f90`
- `0x1000b3f0`
- `0x1000b410`
- `0x1000b600`
- `0x1000b9b0`
- `0x1000ba90`
- `0x1000bd80`
- `0x10019d20`
- `0x1001ad40`
- `0x1001b9c0`
- `0x1001bea0`
- `0x1001bf40`
- `0x1001c3a0`
- `0x1001c3d0`
- `0x1001c420`
- `0x1002b81a`
- `0x1002c32f`
- `0x1002c490`

## pseudocode

```c
int __stdcall INIFileSpecWrite(LPCWSTR lpFileName, WCHAR *lpWideCharStr, int a3)
{
  int v3; // esi
  void *v4; // ecx
  void *v5; // kr00_4
  void *v6; // ecx
  void *v7; // ecx
  int v8; // eax
  HANDLE v9; // esi
  HANDLE v10; // esi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int *v15; // esi
  int v16; // ebx
  WCHAR *v17; // ecx
  int v18; // edx
  WCHAR v19; // ax
  int v20; // edi
  int v21; // eax
  const WCHAR *v23; // [esp-4h] [ebp-434h]
  HANDLE hObject; // [esp+Ch] [ebp-424h] BYREF
  wchar_t pszDest[8]; // [esp+10h] [ebp-420h] BYREF
  wchar_t v26[80]; // [esp+20h] [ebp-410h] BYREF
  wchar_t v27[16]; // [esp+C0h] [ebp-370h] BYREF
  WCHAR WideCharStr[130]; // [esp+E0h] [ebp-350h] BYREF
  CHAR MultiByteStr[68]; // [esp+1E4h] [ebp-24Ch] BYREF
  _BYTE v30[516]; // [esp+228h] [ebp-208h] BYREF

  ErrWideNToMultiByteCb(lpWideCharStr, 65, MultiByteStr, 65);
  if ( DOSFileExists(lpFileName) )
  {
    v3 = DOSCreateFile(lpFileName, (int)&hObject);
  }
  else
  {
    v3 = DOSOpenFile(lpFileName, 2, (int)&hObject);
    DOSSetFilePosition(hObject, 2u, 0);
  }
  if ( v3 )
    return 0;
  DOSWriteFile(v4, hObject, "[", 1u);
  v5 = (void *)strlen(MultiByteStr);
  DOSWriteFile(v5, hObject, MultiByteStr, (DWORD)v5);
  DOSWriteFile(v6, hObject, "]", 1u);
  DOSWriteFile(v7, hObject, &dword_1003E67C, 2u);
  if ( *(_DWORD *)(a3 + 40) == 1 )
    v8 = WriteStringKey(hObject, L"ColNameHeader", L"True");
  else
    v8 = WriteStringKey(hObject, L"ColNameHeader", L"False");
  if ( !v8 )
  {
    v9 = hObject;
    StringCchPrintfW(pszDest, 8u, L"%d", *(_DWORD *)(a3 + 48));
    if ( !WriteStringKey(v9, L"CharacterSet", pszDest) )
    {
      if ( (*(_BYTE *)(a3 + 28) & 4) == 0
        || (v10 = hObject,
            StringCchPrintfW(pszDest, 8u, L"%d", *(_DWORD *)(a3 + 60)),
            !WriteStringKey(v10, L"MaxScanRows", pszDest)) )
      {
        if ( ((*(_BYTE *)(a3 + 28) & 8) == 0 || !WriteIntKey(hObject, L"StartRow", *(_DWORD *)(a3 + 44)))
          && ((*(_BYTE *)(a3 + 28) & 0x20) == 0
           || !WriteIntKey(lpWideCharStr, L"TextDelimiter", *(unsigned __int16 *)(a3 + 84)))
          && ((*(_BYTE *)(a3 + 28) & 0x40) == 0 || !WriteStringKey(hObject, L"DateTimeFormat", (LPCWCH)(a3 + 92)))
          && (*(char *)(a3 + 28) >= 0 || !WriteStringKey(hObject, L"CurrencySymbol", (LPCWCH)(a3 + 700)))
          && ((*(_WORD *)(a3 + 28) & 0x100) == 0 || !WriteIntKey(hObject, L"CurrencyPosFormat", *(_DWORD *)(a3 + 724)))
          && ((*(_WORD *)(a3 + 28) & 0x200) == 0 || !WriteIntKey(hObject, L"CurrencyNegFormat", *(_DWORD *)(a3 + 728)))
          && ((*(_WORD *)(a3 + 28) & 0x400) == 0 || !WriteIntKey(hObject, L"CurrencyDigits", *(_DWORD *)(a3 + 732)))
          && ((*(_WORD *)(a3 + 28) & 0x800) == 0 || !WriteCharKey(hObject, L"DecimalSymbol", *(_WORD *)(a3 + 742)))
          && ((*(_WORD *)(a3 + 28) & 0x1000) == 0 || !WriteIntKey(hObject, L"NumberDigits", *(_DWORD *)(a3 + 748)))
          && ((*(_WORD *)(a3 + 28) & 0x2000) == 0
           || !WriteIntKey(lpWideCharStr, L"CurrencyDecimalSymbol", *(unsigned __int16 *)(a3 + 736)))
          && ((*(_WORD *)(a3 + 28) & 0x4000) == 0
           || !WriteCharKey(lpWideCharStr, L"CurrencyThousandsSymbol", *(_WORD *)(a3 + 738))) )
        {
          if ( *(__int16 *)(a3 + 28) >= 0
            || (*(_DWORD *)(a3 + 752) != 1
              ? (v11 = WriteStringKey(hObject, L"NumbersHaveLeadingZeros", L"False"))
              : (v11 = WriteStringKey(hObject, L"NumbersHaveLeadingZeros", L"True")),
                !v11) )
          {
            v12 = *(_DWORD *)(a3 + 64);
            if ( v12 == 3 )
            {
              v13 = WriteStringKey(hObject, L"Format", L"HTML");
            }
            else if ( v12 == 1 )
            {
              if ( WriteStringKey(hObject, L"Format", L"FixedLength") )
                return -5016;
              if ( *(_DWORD *)(a3 + 32) )
                v23 = L"RaggedEdge";
              else
                v23 = L"TrueFixedLength";
              v13 = WriteStringKey(hObject, L"FixedFormat", v23);
            }
            else
            {
              v14 = *(unsigned __int16 *)(a3 + 68);
              if ( v14 == 44 )
              {
                v13 = WriteStringKey(hObject, L"Format", L"CSVDelimited");
              }
              else if ( v14 == 9 )
              {
                v13 = WriteStringKey(hObject, L"Format", L"TabDelimited");
              }
              else
              {
                StringCchPrintfW(v26, 0x50u, L"%s(%c)", L"Delimited", *(unsigned __int16 *)(a3 + 68));
                v13 = WriteStringKey(hObject, L"Format", v26);
              }
            }
            if ( !v13 )
            {
              v15 = *(int **)(a3 + 916);
              v16 = 1;
              while ( v15 )
              {
                if ( wcschr((const wchar_t *)v15 + 18, 0x22u) || wcschr((const wchar_t *)v15 + 18, 0x20u) )
                {
                  QuoteString(v15 + 9, WideCharStr, 129);
                }
                else
                {
                  v17 = WideCharStr;
                  v18 = 129;
                  while ( v18 != -2147483517 )
                  {
                    v19 = *(WCHAR *)((char *)v17 + (char *)(v15 + 9) - (char *)WideCharStr);
                    if ( !v19 )
                      break;
                    *v17++ = v19;
                    if ( !--v18 )
                    {
                      *(v17 - 1) = 0;
                      goto LABEL_64;
                    }
                  }
                  *v17 = 0;
                }
LABEL_64:
                if ( IsNotAnsiName(WideCharStr) )
                {
                  v20 = 1;
                  memset(v30, 0, 0x202u);
                  INIBytesToHexString(v30, 257, WideCharStr, 2 * wcslen(WideCharStr));
                }
                else
                {
                  v20 = 0;
                }
                v21 = v15[4];
                switch ( v21 )
                {
                  case 10:
                    if ( v20 )
                      StringCchPrintfW(
                        v26,
                        0x50u,
                        L"%s %s Width %d Unicode %s",
                        WideCharStr,
                        off_1003E660[0],
                        (unsigned int)v15[5] >> 1,
                        v30);
                    else
                      StringCchPrintfW(
                        v26,
                        0x50u,
                        L"%s %s Width %d",
                        WideCharStr,
                        off_1003E660[0],
                        (unsigned int)v15[5] >> 1);
                    break;
                  case 16:
                    if ( v20 )
                      StringCchPrintfW(
                        v26,
                        0x50u,
                        L"%s %s Precision %d Scale %d Unicode %s",
                        WideCharStr,
                        off_1003E678,
                        v15[8],
                        v15[7],
                        v30);
                    else
                      StringCchPrintfW(
                        v26,
                        0x50u,
                        L"%s %s Precision %d Scale %d",
                        WideCharStr,
                        off_1003E678,
                        v15[8],
                        v15[7]);
                    break;
                  case 9:
                    if ( v20 )
                      StringCchPrintfW(
                        v26,
                        0x50u,
                        L"%s %s Width %d Unicode %s",
                        WideCharStr,
                        off_1003E65C[0],
                        v15[5],
                        v30);
                    else
                      StringCchPrintfW(v26, 0x50u, L"%s %s Width %d", WideCharStr, off_1003E65C[0], v15[5]);
                    break;
                  case 12:
                    if ( v20 )
                      StringCchPrintfW(
                        v26,
                        0x50u,
                        L"%s %s %s %d Unicode %s",
                        WideCharStr,
                        off_1003E668[0],
                        L"Attribute",
                        v15[2],
                        v30);
                    else
                      StringCchPrintfW(v26, 0x50u, L"%s %s %s %d", WideCharStr, off_1003E668[0], L"Attribute", v15[2]);
                    break;
                  default:
                    if ( v20 )
                      StringCchPrintfW(v26, 0x50u, L"%s %s Unicode %s", WideCharStr, off_1003E638[v21], v30);
                    else
                      StringCchPrintfW(v26, 0x50u, L"%s %s", WideCharStr, off_1003E638[v21]);
                    break;
                }
                StringCchPrintfW(v27, 0x10u, L"%s%d", L"Col", v16);
                if ( WriteStringKey(hObject, v27, v26) )
                  return -5016;
                v15 = (int *)*v15;
                ++v16;
              }
              DOSCloseFile(hObject);
              return 0;
            }
          }
        }
      }
    }
  }
  return -5016;
}

```

## disassembly

```asm
0x1001ad40  sub     esp, 424h
0x1001ad46  mov     eax, ___security_cookie
0x1001ad4b  xor     eax, esp
0x1001ad4d  mov     [esp+424h+var_4], eax
0x1001ad54  push    ebx
0x1001ad55  mov     ebx, [esp+428h+lpWideCharStr]
0x1001ad5c  lea     eax, [esp+428h+MultiByteStr]
0x1001ad63  push    esi
0x1001ad64  mov     esi, [esp+42Ch+lpFileName]
0x1001ad6b  push    edi
0x1001ad6c  mov     edi, [esp+430h+arg_8]
0x1001ad73  push    41h ; 'A'; int
0x1001ad75  push    eax; lpMultiByteStr
0x1001ad76  push    41h ; 'A'; cchWideChar
0x1001ad78  push    ebx; lpWideCharStr
0x1001ad79  call    _ErrWideNToMultiByteCb@16; ErrWideNToMultiByteCb(x,x,x,x)
0x1001ad7e  push    esi; lpFileName
0x1001ad7f  call    _DOSFileExists@4; DOSFileExists(x)
0x1001ad84  test    eax, eax
0x1001ad86  lea     eax, [esp+430h+hObject]
0x1001ad8a  push    eax; int
0x1001ad8b  jnz     short loc_1001ADA6
0x1001ad8d  push    2; int
0x1001ad8f  push    esi; lpFileName
0x1001ad90  call    _DOSOpenFile@12; DOSOpenFile(x,x,x)
0x1001ad95  push    0; lDistanceToMove
0x1001ad97  push    2; dwMoveMethod
0x1001ad99  push    [esp+438h+hObject]; hFile
0x1001ad9d  mov     esi, eax
0x1001ad9f  call    _DOSSetFilePosition@12; DOSSetFilePosition(x,x,x)
0x1001ada4  jmp     short loc_1001ADAE
0x1001ada6  push    esi; lpFileName
0x1001ada7  call    _DOSCreateFile@8; DOSCreateFile(x,x)
0x1001adac  mov     esi, eax
0x1001adae  test    esi, esi
0x1001adb0  jnz     loc_1001B43D
0x1001adb6  push    1; nNumberOfBytesToWrite
0x1001adb8  push    offset asc_1000207C; "["
0x1001adbd  push    [esp+438h+hObject]; hFile
0x1001adc1  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001adc6  lea     ecx, [esp+430h+MultiByteStr]
0x1001adcd  lea     edx, [ecx+1]
0x1001add0  mov     al, [ecx]
0x1001add2  inc     ecx
0x1001add3  test    al, al
0x1001add5  jnz     short loc_1001ADD0
0x1001add7  sub     ecx, edx
0x1001add9  lea     eax, [esp+430h+MultiByteStr]
0x1001ade0  push    ecx; nNumberOfBytesToWrite
0x1001ade1  push    eax; lpBuffer
0x1001ade2  push    [esp+438h+hObject]; hFile
0x1001ade6  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001adeb  push    1; nNumberOfBytesToWrite
0x1001aded  push    offset asc_10002080; "]"
0x1001adf2  push    [esp+438h+hObject]; hFile
0x1001adf6  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001adfb  push    2; nNumberOfBytesToWrite
0x1001adfd  push    offset dword_1003E67C; lpBuffer
0x1001ae02  push    [esp+438h+hObject]; hFile
0x1001ae06  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001ae0b  cmp     dword ptr [edi+28h], 1
0x1001ae0f  jnz     short loc_1001AE18
0x1001ae11  push    offset aTrue; "True"
0x1001ae16  jmp     short loc_1001AE1D
0x1001ae18  push    offset aFalse; "False"
0x1001ae1d  push    offset aColnameheader; "ColNameHeader"
0x1001ae22  push    [esp+438h+hObject]; hFile
0x1001ae26  call    WriteStringKey
0x1001ae2b  test    eax, eax
0x1001ae2d  jnz     loc_1001B441
0x1001ae33  push    dword ptr [edi+30h]
0x1001ae36  mov     esi, [esp+434h+hObject]
0x1001ae3a  lea     eax, [esp+434h+pszDest]
0x1001ae3e  push    offset aD; "%d"
0x1001ae43  push    8; cchDest
0x1001ae45  push    eax; pszDest
0x1001ae46  call    _StringCchPrintfW
0x1001ae4b  add     esp, 10h
0x1001ae4e  lea     eax, [esp+430h+pszDest]
0x1001ae52  push    eax; LPCWCH
0x1001ae53  push    offset aCharacterset; "CharacterSet"
0x1001ae58  push    esi; hFile
0x1001ae59  call    WriteStringKey
0x1001ae5e  test    eax, eax
0x1001ae60  jnz     loc_1001B441
0x1001ae66  test    byte ptr [edi+1Ch], 4
0x1001ae6a  jz      short loc_1001AE9F
0x1001ae6c  push    dword ptr [edi+3Ch]
0x1001ae6f  mov     esi, [esp+434h+hObject]
0x1001ae73  lea     eax, [esp+434h+pszDest]
0x1001ae77  push    offset aD; "%d"
0x1001ae7c  push    8; cchDest
0x1001ae7e  push    eax; pszDest
0x1001ae7f  call    _StringCchPrintfW
0x1001ae84  add     esp, 10h
0x1001ae87  lea     eax, [esp+430h+pszDest]
0x1001ae8b  push    eax; LPCWCH
0x1001ae8c  push    offset aMaxscanrows; "MaxScanRows"
0x1001ae91  push    esi; hFile
0x1001ae92  call    WriteStringKey
0x1001ae97  test    eax, eax
0x1001ae99  jnz     loc_1001B441
0x1001ae9f  test    byte ptr [edi+1Ch], 8
0x1001aea3  jz      short loc_1001AEBE
0x1001aea5  push    dword ptr [edi+2Ch]; int
0x1001aea8  push    offset aStartrow; "StartRow"
0x1001aead  push    [esp+438h+hObject]; hFile
0x1001aeb1  call    WriteIntKey
0x1001aeb6  test    eax, eax
0x1001aeb8  jnz     loc_1001B441
0x1001aebe  test    byte ptr [edi+1Ch], 20h
0x1001aec2  jz      short loc_1001AEDC
0x1001aec4  movzx   eax, word ptr [edi+54h]
0x1001aec8  push    eax; int
0x1001aec9  push    offset aTextdelimiter; "TextDelimiter"
0x1001aece  push    ebx; hFile
0x1001aecf  call    WriteIntKey
0x1001aed4  test    eax, eax
0x1001aed6  jnz     loc_1001B441
0x1001aedc  test    byte ptr [edi+1Ch], 40h
0x1001aee0  jz      short loc_1001AEFC
0x1001aee2  lea     eax, [edi+5Ch]
0x1001aee5  push    eax; LPCWCH
0x1001aee6  push    offset aDatetimeformat; "DateTimeFormat"
0x1001aeeb  push    [esp+438h+hObject]; hFile
0x1001aeef  call    WriteStringKey
0x1001aef4  test    eax, eax
0x1001aef6  jnz     loc_1001B441
0x1001aefc  test    byte ptr [edi+1Ch], 80h
0x1001af00  jz      short loc_1001AF1F
0x1001af02  lea     eax, [edi+2BCh]
0x1001af08  push    eax; LPCWCH
0x1001af09  push    offset aCurrencysymbol; "CurrencySymbol"
0x1001af0e  push    [esp+438h+hObject]; hFile
0x1001af12  call    WriteStringKey
0x1001af17  test    eax, eax
0x1001af19  jnz     loc_1001B441
0x1001af1f  mov     eax, 100h
0x1001af24  test    [edi+1Ch], ax
0x1001af28  jz      short loc_1001AF46
0x1001af2a  push    dword ptr [edi+2D4h]; int
0x1001af30  push    offset aCurrencyposfor; "CurrencyPosFormat"
0x1001af35  push    [esp+438h+hObject]; hFile
0x1001af39  call    WriteIntKey
0x1001af3e  test    eax, eax
0x1001af40  jnz     loc_1001B441
0x1001af46  mov     eax, 200h
0x1001af4b  test    [edi+1Ch], ax
0x1001af4f  jz      short loc_1001AF6D
0x1001af51  push    dword ptr [edi+2D8h]; int
0x1001af57  push    offset aCurrencynegfor; "CurrencyNegFormat"
0x1001af5c  push    [esp+438h+hObject]; hFile
0x1001af60  call    WriteIntKey
0x1001af65  test    eax, eax
0x1001af67  jnz     loc_1001B441
0x1001af6d  mov     eax, 400h
0x1001af72  test    [edi+1Ch], ax
0x1001af76  jz      short loc_1001AF94
0x1001af78  push    dword ptr [edi+2DCh]; int
0x1001af7e  push    offset aCurrencydigits; "CurrencyDigits"
0x1001af83  push    [esp+438h+hObject]; hFile
0x1001af87  call    WriteIntKey
0x1001af8c  test    eax, eax
0x1001af8e  jnz     loc_1001B441
0x1001af94  mov     eax, 800h
0x1001af99  test    [edi+1Ch], ax
0x1001af9d  jz      short loc_1001AFBD
0x1001af9f  movzx   eax, word ptr [edi+2E6h]
0x1001afa6  push    eax; WCHAR
0x1001afa7  push    offset aDecimalsymbol; "DecimalSymbol"
0x1001afac  push    [esp+438h+hObject]; hFile
0x1001afb0  call    WriteCharKey
0x1001afb5  test    eax, eax
0x1001afb7  jnz     loc_1001B441
0x1001afbd  mov     eax, 1000h
0x1001afc2  test    [edi+1Ch], ax
0x1001afc6  jz      short loc_1001AFE4
0x1001afc8  push    dword ptr [edi+2ECh]; int
0x1001afce  push    offset aNumberdigits; "NumberDigits"
0x1001afd3  push    [esp+438h+hObject]; hFile
0x1001afd7  call    WriteIntKey
0x1001afdc  test    eax, eax
0x1001afde  jnz     loc_1001B441
0x1001afe4  mov     eax, 2000h
0x1001afe9  test    [edi+1Ch], ax
0x1001afed  jz      short loc_1001B00A
0x1001afef  movzx   eax, word ptr [edi+2E0h]
0x1001aff6  push    eax; int
0x1001aff7  push    offset aCurrencydecima; "CurrencyDecimalSymbol"
0x1001affc  push    ebx; hFile
0x1001affd  call    WriteIntKey
0x1001b002  test    eax, eax
0x1001b004  jnz     loc_1001B441
0x1001b00a  mov     eax, 4000h
0x1001b00f  test    [edi+1Ch], ax
0x1001b013  jz      short loc_1001B030
0x1001b015  movzx   eax, word ptr [edi+2E2h]
0x1001b01c  push    eax; WCHAR
0x1001b01d  push    offset aCurrencythousa; "CurrencyThousandsSymbol"
0x1001b022  push    ebx; hFile
0x1001b023  call    WriteCharKey
0x1001b028  test    eax, eax
0x1001b02a  jnz     loc_1001B441
0x1001b030  mov     eax, 8000h
0x1001b035  test    [edi+1Ch], ax
0x1001b039  jz      short loc_1001B066
0x1001b03b  cmp     dword ptr [edi+2F0h], 1
0x1001b042  jnz     short loc_1001B04B
0x1001b044  push    offset aTrue; "True"
0x1001b049  jmp     short loc_1001B050
0x1001b04b  push    offset aFalse; "False"
0x1001b050  push    offset aNumbershavelea; "NumbersHaveLeadingZeros"
0x1001b055  push    [esp+438h+hObject]; hFile
0x1001b059  call    WriteStringKey
0x1001b05e  test    eax, eax
0x1001b060  jnz     loc_1001B441
0x1001b066  mov     eax, [edi+40h]
0x1001b069  cmp     eax, 3
0x1001b06c  jnz     short loc_1001B075
0x1001b06e  push    offset aHtml_0; "HTML"
0x1001b073  jmp     short loc_1001B0ED
0x1001b075  cmp     eax, 1
0x1001b078  jnz     short loc_1001B0B2
0x1001b07a  push    offset aFixedlength; "FixedLength"
0x1001b07f  push    offset aFormat; "Format"
0x1001b084  push    [esp+438h+hObject]; hFile
0x1001b088  call    WriteStringKey
0x1001b08d  test    eax, eax
0x1001b08f  jnz     loc_1001B441
0x1001b095  cmp     [edi+20h], eax
0x1001b098  jz      short loc_1001B0A6
0x1001b09a  push    offset aRaggededge; "RaggedEdge"
0x1001b09f  push    offset aFixedformat; "FixedFormat"
0x1001b0a4  jmp     short loc_1001B0F2
0x1001b0a6  push    offset aTruefixedlengt; "TrueFixedLength"
0x1001b0ab  push    offset aFixedformat; "FixedFormat"
0x1001b0b0  jmp     short loc_1001B0F2
0x1001b0b2  movzx   eax, word ptr [edi+44h]
0x1001b0b6  cmp     eax, 2Ch ; ','
0x1001b0b9  jnz     short loc_1001B0C2
0x1001b0bb  push    offset aCsvdelimited; "CSVDelimited"
0x1001b0c0  jmp     short loc_1001B0ED
0x1001b0c2  cmp     eax, 9
0x1001b0c5  jnz     short loc_1001B0CE
0x1001b0c7  push    offset aTabdelimited; "TabDelimited"
0x1001b0cc  jmp     short loc_1001B0ED
0x1001b0ce  push    eax
0x1001b0cf  push    offset aDelimited; "Delimited"
0x1001b0d4  push    offset aSC; "%s(%c)"
0x1001b0d9  lea     eax, [esp+43Ch+var_410]
0x1001b0dd  push    50h ; 'P'; cchDest
0x1001b0df  push    eax; pszDest
0x1001b0e0  call    _StringCchPrintfW
0x1001b0e5  add     esp, 14h
0x1001b0e8  lea     eax, [esp+430h+var_410]
0x1001b0ec  push    eax; LPCWCH
0x1001b0ed  push    offset aFormat; "Format"
0x1001b0f2  push    [esp+438h+hObject]; hFile
0x1001b0f6  call    WriteStringKey
0x1001b0fb  test    eax, eax
0x1001b0fd  jnz     loc_1001B441
0x1001b103  mov     esi, [edi+394h]
0x1001b109  lea     ebx, [eax+1]
0x1001b10c  test    esi, esi
0x1001b10e  jz      loc_1001B434
0x1001b114  lea     edi, [esi+24h]
0x1001b117  push    22h ; '"'; Ch
0x1001b119  push    edi; Str
0x1001b11a  call    _wcschr
0x1001b11f  add     esp, 8
0x1001b122  test    eax, eax
0x1001b124  jnz     short loc_1001B179
0x1001b126  push    20h ; ' '; Ch
0x1001b128  push    edi; Str
0x1001b129  call    _wcschr
0x1001b12e  add     esp, 8
0x1001b131  test    eax, eax
0x1001b133  jnz     short loc_1001B179
0x1001b135  lea     ecx, [esp+430h+WideCharStr]
0x1001b13c  mov     edx, 81h
0x1001b141  mov     eax, ecx
0x1001b143  sub     edi, eax
0x1001b145  lea     eax, [edx+7FFFFF7Dh]
0x1001b14b  test    eax, eax
0x1001b14d  jz      short loc_1001B16B
0x1001b14f  movzx   eax, word ptr [edi+ecx]
0x1001b153  test    ax, ax
0x1001b156  jz      short loc_1001B16B
0x1001b158  mov     [ecx], ax
0x1001b15b  add     ecx, 2
0x1001b15e  dec     edx
0x1001b15f  jnz     short loc_1001B145
0x1001b161  sub     ecx, 2
0x1001b164  xor     eax, eax
0x1001b166  mov     [ecx], ax
0x1001b169  jmp     short loc_1001B18C
0x1001b16b  test    edx, edx
0x1001b16d  jnz     short loc_1001B172
0x1001b16f  sub     ecx, 2
0x1001b172  xor     eax, eax
  ... truncated ...
```
