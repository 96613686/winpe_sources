# ErrGetIsamType(x,x,x)

- ea: `0x10029910`
- end: `0x1002a04e`
- name: `_ErrGetIsamType@12`
- size: `1854`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10017150`
- `0x10017820`
- `0x100a8900`

## callees

- `0x10012af0`
- `0x1001ebc0`
- `0x10029510`
- `0x10029910`
- `0x10046318`
- `0x10046c1f`
- `0x10050190`
- `0x10123110`
- `0x10124a88`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10029b92`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1002a02f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10029b92`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1002a02f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10029e58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10029e58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10029d62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10029d62`

## string_xrefs

- `0x10029981`: `MS Access`

## pseudocode

```c
int __fastcall ErrGetIsamType(unsigned int a1, unsigned __int16 *a2, _DWORD *a3)
{
  int v3; // esi
  int v5; // eax
  unsigned __int16 *v6; // ecx
  unsigned int v7; // ebx
  int v8; // ecx
  int v9; // edi
  unsigned int v10; // eax
  char *v11; // eax
  int v12; // ecx
  bool v13; // zf
  int v14; // eax
  WCHAR *v15; // ecx
  const wchar_t *v16; // edx
  int v17; // esi
  WCHAR *v18; // eax
  HMODULE Library; // eax
  unsigned int v20; // edi
  unsigned int v21; // ecx
  _DWORD *v22; // edx
  unsigned int v23; // esi
  int v24; // eax
  FARPROC ProcAddress; // esi
  int v26; // esi
  int v27; // eax
  unsigned int *v28; // edi
  unsigned int v29; // eax
  _DWORD *v30; // ecx
  int v31; // eax
  int v33; // eax
  HMODULE hLibModule; // [esp+Ch] [ebp-554h]
  HMODULE hLibModulea; // [esp+Ch] [ebp-554h]
  int v37; // [esp+14h] [ebp-54Ch]
  DWORD cbData[2]; // [esp+18h] [ebp-548h] BYREF
  unsigned int v39; // [esp+20h] [ebp-540h]
  unsigned int *v40; // [esp+24h] [ebp-53Ch]
  unsigned int v41[2]; // [esp+28h] [ebp-538h] BYREF
  _DWORD v42[2]; // [esp+30h] [ebp-530h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [esp+38h] [ebp-528h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [esp+48h] [ebp-518h] BYREF
  __int16 *v45; // [esp+58h] [ebp-508h]
  int v46; // [esp+5Ch] [ebp-504h]
  int v47; // [esp+60h] [ebp-500h]
  int v48; // [esp+64h] [ebp-4FCh]
  unsigned int *v49; // [esp+68h] [ebp-4F8h]
  int v50; // [esp+6Ch] [ebp-4F4h]
  int v51; // [esp+70h] [ebp-4F0h]
  int v52; // [esp+74h] [ebp-4ECh]
  wchar_t *v53; // [esp+78h] [ebp-4E8h]
  int v54; // [esp+7Ch] [ebp-4E4h]
  unsigned int v55; // [esp+80h] [ebp-4E0h]
  int v56; // [esp+84h] [ebp-4DCh]
  WCHAR SubKey[100]; // [esp+88h] [ebp-4D8h] BYREF
  wchar_t Destination[256]; // [esp+150h] [ebp-410h] BYREF
  WCHAR LibFileName[262]; // [esp+350h] [ebp-210h] BYREF

  v37 = -1;
  v3 = 0;
  cbData[0] = (DWORD)a2;
  v42[0] = a3;
  if ( !a2 )
    goto LABEL_76;
  v5 = *a2;
  v6 = a2;
  if ( v5 == 59 )
    goto LABEL_76;
  do
  {
    ++v6;
    if ( !(_WORD)v5 )
      break;
    v5 = *v6;
    ++v3;
  }
  while ( v5 != 59 );
  if ( !v3 )
  {
LABEL_76:
    *a3 = 0xFFFF;
    if ( (unsigned int)dword_1012B480 > 5 )
    {
      cbData[0] = dword_1012B488;
      if ( (dword_1012B48C & 0x4000) != 0 && !dword_1012B490 && (dword_1012B494 & 0x4000) == dword_1012B494 )
      {
        v42[1] = 0;
        v49 = v42;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (unsigned int)off_1012B484;
        v42[0] = 0x2000000;
        v50 = 0;
        v51 = 8;
        v52 = 0;
        v53 = L"Jet 4.0";
        v54 = 0;
        v55 = 16;
        v56 = 0;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x400000000000LL;
        UserData.Size = (unsigned __int16)*off_1012B484;
        UserData.Reserved = 2;
        v45 = (__int16 *)&dword_100123E4;
        v46 = 0;
        v47 = 50;
        v48 = 1;
        cbData[0] = &_TraceLoggingMetadataEnd - (const UINT8 *)&_TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
    }
    return 0;
  }
  if ( v3 != 9 )
  {
    if ( v3 == 4 && !WCSNICMP(4) )
    {
      *(_DWORD *)v42[0] = 65534;
      return 0;
    }
LABEL_12:
    if ( (int)ErrIsammgrInit() >= 0 )
    {
      v7 = 0;
      v8 = 2316 * a1;
      v9 = *((_DWORD *)rgtib + 579 * a1 + 262);
      v10 = *(_DWORD *)((char *)rgtib + v8 + 1044);
      v39 = v10;
      if ( v10 )
      {
        while ( WCSNICMP(v3) || *(_WORD *)(v9 + 2 * v3) )
        {
          v10 = v39;
          ++v7;
          v9 += 60;
          if ( v7 >= v39 )
            goto LABEL_19;
        }
        v10 = v39;
      }
LABEL_19:
      if ( v7 != v10 )
      {
        wcsncpy(Destination, (const wchar_t *)v9, 0xFFu);
        if ( (unsigned int)dword_1012B480 > 5 )
        {
          cbData[0] = dword_1012B488;
          if ( (dword_1012B48C & 0x4000) != 0 && !dword_1012B490 && (dword_1012B494 & 0x4000) == dword_1012B494 )
          {
            v41[1] = 0;
            v41[0] = 0x2000000;
            v49 = v41;
            v50 = 0;
            v51 = 8;
            v52 = 0;
            v54 = 0;
            v56 = 0;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            EventDescriptor.Keyword = 0x400000000000LL;
            v55 = 2 * wcslen(Destination) + 2;
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (unsigned int)off_1012B484;
            v53 = Destination;
            UserData.Size = (unsigned __int16)*off_1012B484;
            UserData.Reserved = 2;
            v45 = &word_10012422;
            v46 = 0;
            v47 = 50;
            v48 = 1;
            cbData[0] = &_TraceLoggingMetadataEnd - (const UINT8 *)&_TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
          }
        }
        if ( !rgtib
          || v7 > 0x27
          || a1 > 0x3F
          || (_mm_lfence(), v11 = (char *)*((_DWORD *)rgtib + 579 * a1 + v7 + 264), (v40 = (unsigned int *)v11) == 0) )
        {
          v37 = dword_10130570;
          v12 = 3 * dword_10130570;
          if ( dword_10130570 == -1 )
            return -1109;
          dword_10130570 = dword_10130594[6 * dword_10130570];
          v11 = (char *)&xmmword_10130580 + 8 * v12;
          *(_OWORD *)v11 = 0;
          v40 = (unsigned int *)v11;
          *(_QWORD *)&byte_10130590[8 * v12] = 0;
          dword_10130594[2 * v12] = -1;
        }
        if ( *((_DWORD *)v11 + 1) )
        {
          v28 = v40;
          goto LABEL_74;
        }
        v13 = *(_WORD *)(v9 + 30) == 0;
        v41[0] = 0;
        cbData[0] = 520;
        hLibModule = (HMODULE)(v9 + 30);
        if ( !v13 )
        {
          v14 = 2147483646;
          v15 = SubKey;
          v16 = L"SOFTWARE\\Microsoft\\Jet\\4.0\\Engines\\";
          v17 = 100;
          do
          {
            if ( !v14 )
              break;
            if ( !*v16 )
              break;
            *v15++ = *v16++;
            --v14;
            --v17;
          }
          while ( v17 );
          v18 = v15 - 1;
          if ( v17 )
            v18 = v15;
          *v18 = 0;
          WCSCAT2(SubKey, hLibModule, 0x64u);
          if ( !UtilRegQueryValueW(HKEY_LOCAL_MACHINE, SubKey, L"win32", (LPBYTE)LibFileName, cbData) )
          {
            if ( *(_WORD *)hLibModule )
            {
              if ( cbData[0] >> 1 )
              {
                if ( cbData[0] >> 1 < 0x104 )
                {
                  Library = (HMODULE)JetLoadLibraryExW(LibFileName, 0, 0);
                  hLibModulea = Library;
                  if ( Library )
                  {
                    v20 = v39;
                    v21 = 0;
                    v22 = rgtib;
                    if ( v39 )
                    {
                      while ( 1 )
                      {
                        if ( rgtib )
                        {
                          if ( v21 <= 0x27 )
                          {
                            v23 = a1;
                            if ( a1 <= 0x3F )
                            {
                              _mm_lfence();
                              v24 = *((_DWORD *)rgtib + 579 * a1 + v21 + 264);
                              if ( v24 )
                              {
                                v20 = v39;
                                if ( *(HMODULE *)(v24 + 4) == hLibModulea && *(_DWORD *)(v24 + 16) == v21 )
                                  break;
                              }
                            }
                          }
                        }
                        if ( ++v21 >= v20 )
                        {
                          Library = hLibModulea;
                          goto LABEL_53;
                        }
                      }
LABEL_64:
                      v28 = v40;
                      v40[1] = (unsigned int)hLibModulea;
                      v29 = v41[0];
                      v28[3] = 0;
                      v28[4] = v21;
                      *v28 = v29;
                      if ( v37 != -1 && v22 && v7 <= 0x27 && v23 <= 0x3F )
                      {
                        v30 = (_DWORD *)v42[0];
                        v22[579 * v23 + 264 + v7] = v28;
                        *v30 = v28[4];
                        return 0;
                      }
LABEL_74:
                      *(_DWORD *)v42[0] = v28[4];
                      return 0;
                    }
LABEL_53:
                    if ( v21 == v20 )
                    {
                      ProcAddress = GetProcAddress(Library, (LPCSTR)1);
                      if ( !ProcAddress )
                      {
                        v26 = -1003;
                        goto LABEL_70;
                      }
                      v26 = ((int (__thiscall *)(FARPROC, int (__stdcall **)(int, int), unsigned int *))ProcAddress)(
                              ProcAddress,
                              &JetInfoBlock,
                              v41);
                      if ( v26 < 0 )
                        goto LABEL_70;
                      if ( (*(_DWORD *)v41[0] & 0x20) != 0 )
                      {
                        v27 = (*(int (__thiscall **)(_DWORD, unsigned int, unsigned int *))(v41[0] + 40))(
                                *(_DWORD *)(v41[0] + 40),
                                a1 + 144,
                                v40 + 2);
                      }
                      else
                      {
                        if ( (*(_DWORD *)v41[0] & 8) == 0 )
                        {
                          v26 = -1070;
                          goto LABEL_70;
                        }
                        v27 = (*(int (__thiscall **)(_DWORD, unsigned int))(v41[0] + 40))(
                                *(_DWORD *)(v41[0] + 40),
                                a1 + 144);
                      }
                      v26 = v27;
                      if ( v27 < 0 )
                      {
LABEL_70:
                        FreeLibrary(hLibModulea);
                        v31 = dword_10130570;
                        dword_10130570 = v37;
                        dword_10130594[6 * v37] = v31;
                        return v26;
                      }
                      v22 = rgtib;
                      v21 = v7;
                    }
                    v23 = a1;
                    goto LABEL_64;
                  }
                }
              }
            }
          }
        }
        v33 = dword_10130570;
        dword_10130570 = v37;
        dword_10130594[6 * v37] = v33;
      }
    }
    return -1056;
  }
  if ( WCSNICMP(9) )
    goto LABEL_12;
  *(_DWORD *)v42[0] = 0xFFFF;
  return 0;
}

```

## disassembly

```asm
0x10029910  mov     edi, edi
0x10029912  push    ebp
0x10029913  mov     ebp, esp
0x10029915  and     esp, 0FFFFFFF8h
0x10029918  sub     esp, 554h
0x1002991e  mov     eax, ___security_cookie
0x10029923  xor     eax, esp
0x10029925  mov     [esp+554h+var_4], eax
0x1002992c  push    ebx
0x1002992d  push    esi
0x1002992e  mov     ebx, edx
0x10029930  mov     [esp+55Ch+var_54C], 0FFFFFFFFh
0x10029938  mov     edx, [ebp+arg_0]
0x1002993b  xor     esi, esi
0x1002993d  mov     [esp+55Ch+cbData], ebx
0x10029941  mov     [esp+55Ch+var_530], edx
0x10029945  push    edi; unsigned int
0x10029946  mov     edi, ecx
0x10029948  mov     [esp+560h+var_550], edi
0x1002994c  test    ebx, ebx
0x1002994e  jz      loc_10029EF3
0x10029954  movzx   eax, word ptr [ebx]
0x10029957  mov     ecx, ebx
0x10029959  cmp     eax, 3Bh ; ';'
0x1002995c  jz      loc_10029EF3
0x10029962  lea     ecx, [ecx+2]
0x10029965  test    ax, ax
0x10029968  jz      short loc_10029973
0x1002996a  movzx   eax, word ptr [ecx]
0x1002996d  inc     esi
0x1002996e  cmp     eax, 3Bh ; ';'
0x10029971  jnz     short loc_10029962
0x10029973  test    esi, esi
0x10029975  jz      loc_10029EF3
0x1002997b  cmp     esi, 9
0x1002997e  jnz     short loc_100299A0
0x10029980  push    esi
0x10029981  mov     edx, offset _wszAccess; "MS Access"
0x10029986  mov     ecx, ebx
0x10029988  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x1002998d  test    eax, eax
0x1002998f  jnz     short loc_100299C5
0x10029991  mov     ecx, [esp+560h+var_530]
0x10029995  mov     dword ptr [ecx], 0FFFFh
0x1002999b  jmp     loc_1002A035
0x100299a0  cmp     esi, 4
0x100299a3  jnz     short loc_100299C5
0x100299a5  push    esi
0x100299a6  mov     edx, offset aOdbc_0; "ODBC"
0x100299ab  mov     ecx, ebx
0x100299ad  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100299b2  test    eax, eax
0x100299b4  jnz     short loc_100299C5
0x100299b6  mov     ecx, [esp+560h+var_530]
0x100299ba  mov     dword ptr [ecx], 0FFFEh
0x100299c0  jmp     loc_1002A035
0x100299c5  mov     ecx, edi
0x100299c7  call    _ErrIsammgrInit@4; ErrIsammgrInit(x)
0x100299cc  test    eax, eax
0x100299ce  js      loc_10029EA9
0x100299d4  mov     eax, _rgtib
0x100299d9  xor     ebx, ebx
0x100299db  imul    ecx, edi, 90Ch
0x100299e1  mov     edi, [ecx+eax+418h]
0x100299e8  mov     eax, [ecx+eax+414h]
0x100299ef  mov     [esp+560h+var_540], eax
0x100299f3  test    eax, eax
0x100299f5  jz      short loc_10029A1F
0x100299f7  mov     ecx, [esp+560h+cbData]
0x100299fb  mov     edx, edi
0x100299fd  push    esi
0x100299fe  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10029a03  test    eax, eax
0x10029a05  jnz     short loc_10029A0D
0x10029a07  cmp     [edi+esi*2], ax
0x10029a0b  jz      short loc_10029A1B
0x10029a0d  mov     eax, [esp+560h+var_540]
0x10029a11  inc     ebx
0x10029a12  add     edi, 3Ch ; '<'
0x10029a15  cmp     ebx, eax
0x10029a17  jb      short loc_100299F7
0x10029a19  jmp     short loc_10029A1F
0x10029a1b  mov     eax, [esp+560h+var_540]
0x10029a1f  cmp     ebx, eax
0x10029a21  jz      loc_10029EA9
0x10029a27  push    0FFh; Count
0x10029a2c  lea     eax, [esp+564h+Destination]
0x10029a33  push    edi; Source
0x10029a34  push    eax; Destination
0x10029a35  call    _wcsncpy
0x10029a3a  mov     eax, dword_1012B480
0x10029a3f  add     esp, 0Ch
0x10029a42  cmp     eax, 5
0x10029a45  jbe     loc_10029B98
0x10029a4b  mov     esi, dword_1012B490
0x10029a51  mov     edx, dword_1012B494
0x10029a57  mov     eax, dword_1012B488
0x10029a5c  mov     ecx, dword_1012B48C
0x10029a62  mov     [esp+560h+cbData], eax
0x10029a66  and     ecx, 4000h
0x10029a6c  xor     eax, eax
0x10029a6e  or      eax, ecx
0x10029a70  jz      loc_10029B98
0x10029a76  mov     ecx, edx
0x10029a78  xor     eax, eax
0x10029a7a  and     ecx, 4000h
0x10029a80  cmp     eax, esi
0x10029a82  jnz     loc_10029B98
0x10029a88  cmp     ecx, edx
0x10029a8a  jnz     loc_10029B98
0x10029a90  mov     [esp+560h+var_534], eax
0x10029a94  lea     ecx, [esp+560h+Destination]
0x10029a9b  lea     eax, [esp+560h+var_538]
0x10029a9f  mov     [esp+560h+var_538], 2000000h
0x10029aa7  mov     [esp+560h+var_4F8], eax
0x10029aab  lea     edx, [ecx+2]
0x10029aae  mov     [esp+560h+var_4F4], 0
0x10029ab6  mov     [esp+560h+var_4F0], 8
0x10029abe  mov     [esp+560h+var_4EC], 0
0x10029ac6  mov     ax, [ecx]
0x10029ac9  add     ecx, 2
0x10029acc  test    ax, ax
0x10029acf  jnz     short loc_10029AC6
0x10029ad1  sub     ecx, edx
0x10029ad3  mov     [esp+560h+var_4E4], 0
0x10029adb  sar     ecx, 1
0x10029add  mov     [esp+560h+var_4DC], 0
0x10029ae8  mov     dword ptr [esp+560h+EventDescriptor.Id], 0B000000h
0x10029af0  mov     dword ptr [esp+560h+EventDescriptor.Keyword], 0
0x10029af8  lea     eax, ds:2[ecx*2]
0x10029aff  mov     dword ptr [esp+560h+EventDescriptor.Keyword+4], 4000h
0x10029b07  mov     [esp+560h+var_4E0], eax
0x10029b0e  lea     ecx, [esp+560h+Destination]
0x10029b15  movzx   eax, ds:word_10012418
0x10029b1c  mov     dword ptr [esp+560h+EventDescriptor.Level], eax
0x10029b20  mov     eax, off_1012B484
0x10029b25  mov     dword ptr [esp+560h+UserData.Ptr], eax
0x10029b29  mov     [esp+560h+var_4E8], ecx
0x10029b2d  mov     dword ptr [esp+560h+UserData.Ptr+4], 0
0x10029b35  movzx   eax, word ptr [eax]
0x10029b38  mov     [esp+560h+UserData.Size], eax
0x10029b3c  mov     eax, offset __TraceLoggingMetadataEnd
0x10029b41  sub     eax, offset __TraceLoggingMetadata
0x10029b46  mov     dword ptr [esp+560h+UserData.0Ch], 2
0x10029b4e  mov     [esp+560h+var_508], offset word_10012422
0x10029b56  mov     [esp+560h+var_504], 0
0x10029b5e  mov     [esp+560h+var_500], 32h ; '2'
0x10029b66  mov     [esp+560h+var_4FC], 1
0x10029b6e  mov     [esp+560h+cbData], eax
0x10029b72  mov     eax, [esp+560h+cbData]
0x10029b76  lea     eax, [esp+560h+UserData]
0x10029b7a  push    eax; UserData
0x10029b7b  push    4; UserDataCount
0x10029b7d  push    0; RelatedActivityId
0x10029b7f  push    0; ActivityId
0x10029b81  lea     eax, [esp+570h+EventDescriptor]
0x10029b85  push    eax; EventDescriptor
0x10029b86  push    dword ptr RegHandle+4
0x10029b8c  push    dword ptr RegHandle; RegHandle
0x10029b92  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x10029b98  mov     ecx, _rgtib
0x10029b9e  test    ecx, ecx
0x10029ba0  jz      short loc_10029BCA
0x10029ba2  cmp     ebx, 27h ; '''
0x10029ba5  ja      short loc_10029BCA
0x10029ba7  mov     eax, [esp+560h+var_550]
0x10029bab  cmp     eax, 3Fh ; '?'
0x10029bae  ja      short loc_10029BCA
0x10029bb0  imul    eax, 243h
0x10029bb6  lfence
0x10029bb9  add     eax, ebx
0x10029bbb  mov     eax, [ecx+eax*4+420h]
0x10029bc2  mov     [esp+560h+var_53C], eax
0x10029bc6  test    eax, eax
0x10029bc8  jnz     short loc_10029C15
0x10029bca  mov     eax, dword_10130570
0x10029bcf  mov     [esp+560h+var_54C], eax
0x10029bd3  lea     ecx, [eax+eax*2]
0x10029bd6  cmp     eax, 0FFFFFFFFh
0x10029bd9  jz      loc_10029ED7
0x10029bdf  mov     eax, dword_10130594[ecx*8]
0x10029be6  xorps   xmm0, xmm0
0x10029be9  mov     dword_10130570, eax
0x10029bee  lea     eax, xmmword_10130580[ecx*8]
0x10029bf5  movups  xmmword_10130580[ecx*8], xmm0
0x10029bfd  mov     [esp+560h+var_53C], eax
0x10029c01  movq    qword ptr byte_10130590[ecx*8], xmm0
0x10029c0a  mov     dword_10130594[ecx*8], 0FFFFFFFFh
0x10029c15  cmp     dword ptr [eax+4], 0
0x10029c19  jnz     loc_10029EC5
0x10029c1f  cmp     word ptr [edi+1Eh], 0
0x10029c24  lea     ecx, [edi+1Eh]
0x10029c27  mov     eax, 208h
0x10029c2c  mov     [esp+560h+var_538], 0
0x10029c34  mov     [esp+560h+cbData], eax
0x10029c38  mov     [esp+560h+hLibModule], ecx
0x10029c3c  jz      loc_10029E90
0x10029c42  mov     eax, 7FFFFFFEh
0x10029c47  lea     ecx, [esp+560h+SubKey]
0x10029c4e  mov     edx, offset _wszRegIsamEngines; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"...
0x10029c53  mov     esi, 64h ; 'd'
0x10029c58  test    eax, eax
0x10029c5a  jz      short loc_10029C73
0x10029c5c  movzx   edi, word ptr [edx]
0x10029c5f  test    di, di
0x10029c62  jz      short loc_10029C73
0x10029c64  mov     [ecx], di
0x10029c67  add     edx, 2
0x10029c6a  add     ecx, 2
0x10029c6d  dec     eax
0x10029c6e  sub     esi, 1
0x10029c71  jnz     short loc_10029C58
0x10029c73  mov     edx, [esp+560h+hLibModule]
0x10029c77  lea     eax, [ecx-2]
0x10029c7a  test    esi, esi
0x10029c7c  push    64h ; 'd'
0x10029c7e  cmovnz  eax, ecx
0x10029c81  xor     ecx, ecx
0x10029c83  mov     [eax], cx
0x10029c86  lea     ecx, [esp+564h+SubKey]
0x10029c8d  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10029c92  lea     eax, [esp+560h+cbData]
0x10029c96  mov     ecx, 80000002h; hKey
0x10029c9b  push    eax; lpcbData
0x10029c9c  lea     eax, [esp+564h+LibFileName]
0x10029ca3  push    eax; lpData
0x10029ca4  push    offset aWin32; "win32"
0x10029ca9  lea     edx, [esp+56Ch+SubKey]; lpSubKey
0x10029cb0  call    _UtilRegQueryValueW@20; UtilRegQueryValueW(x,x,x,x,x)
0x10029cb5  test    eax, eax
0x10029cb7  jnz     loc_10029E90
0x10029cbd  mov     ecx, [esp+560h+hLibModule]
0x10029cc1  mov     eax, [esp+560h+cbData]
0x10029cc5  cmp     word ptr [ecx], 0
0x10029cc9  jz      loc_10029E90
0x10029ccf  shr     eax, 1
0x10029cd1  jz      loc_10029E90
0x10029cd7  cmp     eax, 104h
0x10029cdc  jnb     loc_10029E90
0x10029ce2  push    0; int
0x10029ce4  push    0; hFile
0x10029ce6  lea     eax, [esp+568h+LibFileName]
0x10029ced  push    eax; lpLibFileName
0x10029cee  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x10029cf3  mov     [esp+560h+hLibModule], eax
0x10029cf7  test    eax, eax
0x10029cf9  jz      loc_10029E90
0x10029cff  mov     edi, [esp+560h+var_540]
0x10029d03  xor     ecx, ecx
0x10029d05  mov     edx, _rgtib
0x10029d0b  test    edi, edi
0x10029d0d  jz      short loc_10029D57
0x10029d0f  nop
0x10029d10  test    edx, edx
0x10029d12  jz      short loc_10029D4E
0x10029d14  cmp     ecx, 27h ; '''
0x10029d17  ja      short loc_10029D4E
0x10029d19  mov     esi, [esp+560h+var_550]
0x10029d1d  cmp     esi, 3Fh ; '?'
0x10029d20  ja      short loc_10029D4E
0x10029d22  imul    eax, esi, 243h
0x10029d28  lfence
0x10029d2b  add     eax, ecx
0x10029d2d  mov     eax, [edx+eax*4+420h]
0x10029d34  test    eax, eax
0x10029d36  jz      short loc_10029D4E
0x10029d38  mov     edi, [esp+560h+hLibModule]
0x10029d3c  cmp     [eax+4], edi
0x10029d3f  mov     edi, [esp+560h+var_540]
0x10029d43  jnz     short loc_10029D4E
0x10029d45  cmp     [eax+10h], ecx
0x10029d48  jz      loc_10029DF2
0x10029d4e  inc     ecx
0x10029d4f  cmp     ecx, edi
0x10029d51  jb      short loc_10029D10
0x10029d53  mov     eax, [esp+560h+hLibModule]
0x10029d57  cmp     ecx, edi
0x10029d59  jnz     loc_10029DEE
0x10029d5f  push    1; lpProcName
0x10029d61  push    eax; hModule
0x10029d62  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10029d68  mov     esi, eax
0x10029d6a  test    esi, esi
0x10029d6c  jnz     short loc_10029D78
0x10029d6e  mov     esi, 0FFFFFC15h
0x10029d73  jmp     loc_10029E54
0x10029d78  lea     eax, [esp+560h+var_538]
0x10029d7c  mov     ecx, esi
0x10029d7e  push    eax; unsigned int
0x10029d7f  push    offset _JetInfoBlock; void *
0x10029d84  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029d8a  call    esi
0x10029d8c  mov     esi, eax
0x10029d8e  test    esi, esi
0x10029d90  js      loc_10029E54
0x10029d96  mov     esi, [esp+560h+var_538]
0x10029d9a  mov     eax, [esi]
0x10029d9c  test    al, 20h
0x10029d9e  jz      short loc_10029DC1
0x10029da0  mov     eax, [esp+560h+var_53C]
  ... truncated ...
```
