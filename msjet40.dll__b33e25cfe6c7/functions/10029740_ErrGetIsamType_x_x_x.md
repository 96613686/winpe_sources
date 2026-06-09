# ErrGetIsamType(x,x,x)

- ea: `0x10029740`
- end: `0x10029e7e`
- name: `_ErrGetIsamType@12`
- size: `1854`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10017010`
- `0x100176e0`
- `0x100a8770`

## callees

- `0x100129b0`
- `0x1001ea70`
- `0x10029340`
- `0x10029740`
- `0x10046198`
- `0x10046a9f`
- `0x10050000`
- `0x10122f60`
- `0x101248d8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x100299c2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10029e5f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x100299c2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10029e5f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10029c88`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10029c88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10029b92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x10029b92`

## string_xrefs

- `0x100297b1`: `MS Access`

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
    if ( (unsigned int)dword_1012B470 > 5 )
    {
      cbData[0] = dword_1012B478;
      if ( (dword_1012B47C & 0x4000) != 0 && !dword_1012B480 && (dword_1012B484 & 0x4000) == dword_1012B484 )
      {
        v42[1] = 0;
        v49 = v42;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = (unsigned int)off_1012B474;
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
        UserData.Size = (unsigned __int16)*off_1012B474;
        UserData.Reserved = 2;
        v45 = (__int16 *)&dword_100122A4;
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
        if ( (unsigned int)dword_1012B470 > 5 )
        {
          cbData[0] = dword_1012B478;
          if ( (dword_1012B47C & 0x4000) != 0 && !dword_1012B480 && (dword_1012B484 & 0x4000) == dword_1012B484 )
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
            UserData.Ptr = (unsigned int)off_1012B474;
            v53 = Destination;
            UserData.Size = (unsigned __int16)*off_1012B474;
            UserData.Reserved = 2;
            v45 = &word_100122E2;
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
          v37 = dword_101304D8;
          v12 = 3 * dword_101304D8;
          if ( dword_101304D8 == -1 )
            return -1109;
          dword_101304D8 = dword_101304F4[6 * dword_101304D8];
          v11 = (char *)&xmmword_101304E0 + 8 * v12;
          *(_OWORD *)v11 = 0;
          v40 = (unsigned int *)v11;
          *(_QWORD *)&byte_101304F0[8 * v12] = 0;
          dword_101304F4[2 * v12] = -1;
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
                        v31 = dword_101304D8;
                        dword_101304D8 = v37;
                        dword_101304F4[6 * v37] = v31;
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
        v33 = dword_101304D8;
        dword_101304D8 = v37;
        dword_101304F4[6 * v37] = v33;
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
0x10029740  mov     edi, edi
0x10029742  push    ebp
0x10029743  mov     ebp, esp
0x10029745  and     esp, 0FFFFFFF8h
0x10029748  sub     esp, 554h
0x1002974e  mov     eax, ___security_cookie
0x10029753  xor     eax, esp
0x10029755  mov     [esp+554h+var_4], eax
0x1002975c  push    ebx
0x1002975d  push    esi
0x1002975e  mov     ebx, edx
0x10029760  mov     [esp+55Ch+var_54C], 0FFFFFFFFh
0x10029768  mov     edx, [ebp+arg_0]
0x1002976b  xor     esi, esi
0x1002976d  mov     [esp+55Ch+cbData], ebx
0x10029771  mov     [esp+55Ch+var_530], edx
0x10029775  push    edi; unsigned int
0x10029776  mov     edi, ecx
0x10029778  mov     [esp+560h+var_550], edi
0x1002977c  test    ebx, ebx
0x1002977e  jz      loc_10029D23
0x10029784  movzx   eax, word ptr [ebx]
0x10029787  mov     ecx, ebx
0x10029789  cmp     eax, 3Bh ; ';'
0x1002978c  jz      loc_10029D23
0x10029792  lea     ecx, [ecx+2]
0x10029795  test    ax, ax
0x10029798  jz      short loc_100297A3
0x1002979a  movzx   eax, word ptr [ecx]
0x1002979d  inc     esi
0x1002979e  cmp     eax, 3Bh ; ';'
0x100297a1  jnz     short loc_10029792
0x100297a3  test    esi, esi
0x100297a5  jz      loc_10029D23
0x100297ab  cmp     esi, 9
0x100297ae  jnz     short loc_100297D0
0x100297b0  push    esi
0x100297b1  mov     edx, offset _wszAccess; "MS Access"
0x100297b6  mov     ecx, ebx
0x100297b8  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100297bd  test    eax, eax
0x100297bf  jnz     short loc_100297F5
0x100297c1  mov     ecx, [esp+560h+var_530]
0x100297c5  mov     dword ptr [ecx], 0FFFFh
0x100297cb  jmp     loc_10029E65
0x100297d0  cmp     esi, 4
0x100297d3  jnz     short loc_100297F5
0x100297d5  push    esi
0x100297d6  mov     edx, offset aOdbc_0; "ODBC"
0x100297db  mov     ecx, ebx
0x100297dd  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100297e2  test    eax, eax
0x100297e4  jnz     short loc_100297F5
0x100297e6  mov     ecx, [esp+560h+var_530]
0x100297ea  mov     dword ptr [ecx], 0FFFEh
0x100297f0  jmp     loc_10029E65
0x100297f5  mov     ecx, edi
0x100297f7  call    _ErrIsammgrInit@4; ErrIsammgrInit(x)
0x100297fc  test    eax, eax
0x100297fe  js      loc_10029CD9
0x10029804  mov     eax, _rgtib
0x10029809  xor     ebx, ebx
0x1002980b  imul    ecx, edi, 90Ch
0x10029811  mov     edi, [ecx+eax+418h]
0x10029818  mov     eax, [ecx+eax+414h]
0x1002981f  mov     [esp+560h+var_540], eax
0x10029823  test    eax, eax
0x10029825  jz      short loc_1002984F
0x10029827  mov     ecx, [esp+560h+cbData]
0x1002982b  mov     edx, edi
0x1002982d  push    esi
0x1002982e  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10029833  test    eax, eax
0x10029835  jnz     short loc_1002983D
0x10029837  cmp     [edi+esi*2], ax
0x1002983b  jz      short loc_1002984B
0x1002983d  mov     eax, [esp+560h+var_540]
0x10029841  inc     ebx
0x10029842  add     edi, 3Ch ; '<'
0x10029845  cmp     ebx, eax
0x10029847  jb      short loc_10029827
0x10029849  jmp     short loc_1002984F
0x1002984b  mov     eax, [esp+560h+var_540]
0x1002984f  cmp     ebx, eax
0x10029851  jz      loc_10029CD9
0x10029857  push    0FFh; Count
0x1002985c  lea     eax, [esp+564h+Destination]
0x10029863  push    edi; Source
0x10029864  push    eax; Destination
0x10029865  call    _wcsncpy
0x1002986a  mov     eax, dword_1012B470
0x1002986f  add     esp, 0Ch
0x10029872  cmp     eax, 5
0x10029875  jbe     loc_100299C8
0x1002987b  mov     esi, dword_1012B480
0x10029881  mov     edx, dword_1012B484
0x10029887  mov     eax, dword_1012B478
0x1002988c  mov     ecx, dword_1012B47C
0x10029892  mov     [esp+560h+cbData], eax
0x10029896  and     ecx, 4000h
0x1002989c  xor     eax, eax
0x1002989e  or      eax, ecx
0x100298a0  jz      loc_100299C8
0x100298a6  mov     ecx, edx
0x100298a8  xor     eax, eax
0x100298aa  and     ecx, 4000h
0x100298b0  cmp     eax, esi
0x100298b2  jnz     loc_100299C8
0x100298b8  cmp     ecx, edx
0x100298ba  jnz     loc_100299C8
0x100298c0  mov     [esp+560h+var_534], eax
0x100298c4  lea     ecx, [esp+560h+Destination]
0x100298cb  lea     eax, [esp+560h+var_538]
0x100298cf  mov     [esp+560h+var_538], 2000000h
0x100298d7  mov     [esp+560h+var_4F8], eax
0x100298db  lea     edx, [ecx+2]
0x100298de  mov     [esp+560h+var_4F4], 0
0x100298e6  mov     [esp+560h+var_4F0], 8
0x100298ee  mov     [esp+560h+var_4EC], 0
0x100298f6  mov     ax, [ecx]
0x100298f9  add     ecx, 2
0x100298fc  test    ax, ax
0x100298ff  jnz     short loc_100298F6
0x10029901  sub     ecx, edx
0x10029903  mov     [esp+560h+var_4E4], 0
0x1002990b  sar     ecx, 1
0x1002990d  mov     [esp+560h+var_4DC], 0
0x10029918  mov     dword ptr [esp+560h+EventDescriptor.Id], 0B000000h
0x10029920  mov     dword ptr [esp+560h+EventDescriptor.Keyword], 0
0x10029928  lea     eax, ds:2[ecx*2]
0x1002992f  mov     dword ptr [esp+560h+EventDescriptor.Keyword+4], 4000h
0x10029937  mov     [esp+560h+var_4E0], eax
0x1002993e  lea     ecx, [esp+560h+Destination]
0x10029945  movzx   eax, ds:word_100122D8
0x1002994c  mov     dword ptr [esp+560h+EventDescriptor.Level], eax
0x10029950  mov     eax, off_1012B474
0x10029955  mov     dword ptr [esp+560h+UserData.Ptr], eax
0x10029959  mov     [esp+560h+var_4E8], ecx
0x1002995d  mov     dword ptr [esp+560h+UserData.Ptr+4], 0
0x10029965  movzx   eax, word ptr [eax]
0x10029968  mov     [esp+560h+UserData.Size], eax
0x1002996c  mov     eax, offset __TraceLoggingMetadataEnd
0x10029971  sub     eax, offset __TraceLoggingMetadata
0x10029976  mov     dword ptr [esp+560h+UserData.0Ch], 2
0x1002997e  mov     [esp+560h+var_508], offset word_100122E2
0x10029986  mov     [esp+560h+var_504], 0
0x1002998e  mov     [esp+560h+var_500], 32h ; '2'
0x10029996  mov     [esp+560h+var_4FC], 1
0x1002999e  mov     [esp+560h+cbData], eax
0x100299a2  mov     eax, [esp+560h+cbData]
0x100299a6  lea     eax, [esp+560h+UserData]
0x100299aa  push    eax; UserData
0x100299ab  push    4; UserDataCount
0x100299ad  push    0; RelatedActivityId
0x100299af  push    0; ActivityId
0x100299b1  lea     eax, [esp+570h+EventDescriptor]
0x100299b5  push    eax; EventDescriptor
0x100299b6  push    dword ptr RegHandle+4
0x100299bc  push    dword ptr RegHandle; RegHandle
0x100299c2  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x100299c8  mov     ecx, _rgtib
0x100299ce  test    ecx, ecx
0x100299d0  jz      short loc_100299FA
0x100299d2  cmp     ebx, 27h ; '''
0x100299d5  ja      short loc_100299FA
0x100299d7  mov     eax, [esp+560h+var_550]
0x100299db  cmp     eax, 3Fh ; '?'
0x100299de  ja      short loc_100299FA
0x100299e0  imul    eax, 243h
0x100299e6  lfence
0x100299e9  add     eax, ebx
0x100299eb  mov     eax, [ecx+eax*4+420h]
0x100299f2  mov     [esp+560h+var_53C], eax
0x100299f6  test    eax, eax
0x100299f8  jnz     short loc_10029A45
0x100299fa  mov     eax, dword_101304D8
0x100299ff  mov     [esp+560h+var_54C], eax
0x10029a03  lea     ecx, [eax+eax*2]
0x10029a06  cmp     eax, 0FFFFFFFFh
0x10029a09  jz      loc_10029D07
0x10029a0f  mov     eax, dword_101304F4[ecx*8]
0x10029a16  xorps   xmm0, xmm0
0x10029a19  mov     dword_101304D8, eax
0x10029a1e  lea     eax, xmmword_101304E0[ecx*8]
0x10029a25  movups  xmmword_101304E0[ecx*8], xmm0
0x10029a2d  mov     [esp+560h+var_53C], eax
0x10029a31  movq    qword ptr byte_101304F0[ecx*8], xmm0
0x10029a3a  mov     dword_101304F4[ecx*8], 0FFFFFFFFh
0x10029a45  cmp     dword ptr [eax+4], 0
0x10029a49  jnz     loc_10029CF5
0x10029a4f  cmp     word ptr [edi+1Eh], 0
0x10029a54  lea     ecx, [edi+1Eh]
0x10029a57  mov     eax, 208h
0x10029a5c  mov     [esp+560h+var_538], 0
0x10029a64  mov     [esp+560h+cbData], eax
0x10029a68  mov     [esp+560h+hLibModule], ecx
0x10029a6c  jz      loc_10029CC0
0x10029a72  mov     eax, 7FFFFFFEh
0x10029a77  lea     ecx, [esp+560h+SubKey]
0x10029a7e  mov     edx, offset _wszRegIsamEngines; "SOFTWARE\\Microsoft\\Jet\\4.0\\Engines"...
0x10029a83  mov     esi, 64h ; 'd'
0x10029a88  test    eax, eax
0x10029a8a  jz      short loc_10029AA3
0x10029a8c  movzx   edi, word ptr [edx]
0x10029a8f  test    di, di
0x10029a92  jz      short loc_10029AA3
0x10029a94  mov     [ecx], di
0x10029a97  add     edx, 2
0x10029a9a  add     ecx, 2
0x10029a9d  dec     eax
0x10029a9e  sub     esi, 1
0x10029aa1  jnz     short loc_10029A88
0x10029aa3  mov     edx, [esp+560h+hLibModule]
0x10029aa7  lea     eax, [ecx-2]
0x10029aaa  test    esi, esi
0x10029aac  push    64h ; 'd'
0x10029aae  cmovnz  eax, ecx
0x10029ab1  xor     ecx, ecx
0x10029ab3  mov     [eax], cx
0x10029ab6  lea     ecx, [esp+564h+SubKey]
0x10029abd  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10029ac2  lea     eax, [esp+560h+cbData]
0x10029ac6  mov     ecx, 80000002h; hKey
0x10029acb  push    eax; lpcbData
0x10029acc  lea     eax, [esp+564h+LibFileName]
0x10029ad3  push    eax; lpData
0x10029ad4  push    offset aWin32; "win32"
0x10029ad9  lea     edx, [esp+56Ch+SubKey]; lpSubKey
0x10029ae0  call    _UtilRegQueryValueW@20; UtilRegQueryValueW(x,x,x,x,x)
0x10029ae5  test    eax, eax
0x10029ae7  jnz     loc_10029CC0
0x10029aed  mov     ecx, [esp+560h+hLibModule]
0x10029af1  mov     eax, [esp+560h+cbData]
0x10029af5  cmp     word ptr [ecx], 0
0x10029af9  jz      loc_10029CC0
0x10029aff  shr     eax, 1
0x10029b01  jz      loc_10029CC0
0x10029b07  cmp     eax, 104h
0x10029b0c  jnb     loc_10029CC0
0x10029b12  push    0; int
0x10029b14  push    0; hFile
0x10029b16  lea     eax, [esp+568h+LibFileName]
0x10029b1d  push    eax; lpLibFileName
0x10029b1e  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x10029b23  mov     [esp+560h+hLibModule], eax
0x10029b27  test    eax, eax
0x10029b29  jz      loc_10029CC0
0x10029b2f  mov     edi, [esp+560h+var_540]
0x10029b33  xor     ecx, ecx
0x10029b35  mov     edx, _rgtib
0x10029b3b  test    edi, edi
0x10029b3d  jz      short loc_10029B87
0x10029b3f  nop
0x10029b40  test    edx, edx
0x10029b42  jz      short loc_10029B7E
0x10029b44  cmp     ecx, 27h ; '''
0x10029b47  ja      short loc_10029B7E
0x10029b49  mov     esi, [esp+560h+var_550]
0x10029b4d  cmp     esi, 3Fh ; '?'
0x10029b50  ja      short loc_10029B7E
0x10029b52  imul    eax, esi, 243h
0x10029b58  lfence
0x10029b5b  add     eax, ecx
0x10029b5d  mov     eax, [edx+eax*4+420h]
0x10029b64  test    eax, eax
0x10029b66  jz      short loc_10029B7E
0x10029b68  mov     edi, [esp+560h+hLibModule]
0x10029b6c  cmp     [eax+4], edi
0x10029b6f  mov     edi, [esp+560h+var_540]
0x10029b73  jnz     short loc_10029B7E
0x10029b75  cmp     [eax+10h], ecx
0x10029b78  jz      loc_10029C22
0x10029b7e  inc     ecx
0x10029b7f  cmp     ecx, edi
0x10029b81  jb      short loc_10029B40
0x10029b83  mov     eax, [esp+560h+hLibModule]
0x10029b87  cmp     ecx, edi
0x10029b89  jnz     loc_10029C1E
0x10029b8f  push    1; lpProcName
0x10029b91  push    eax; hModule
0x10029b92  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10029b98  mov     esi, eax
0x10029b9a  test    esi, esi
0x10029b9c  jnz     short loc_10029BA8
0x10029b9e  mov     esi, 0FFFFFC15h
0x10029ba3  jmp     loc_10029C84
0x10029ba8  lea     eax, [esp+560h+var_538]
0x10029bac  mov     ecx, esi
0x10029bae  push    eax; unsigned int
0x10029baf  push    offset _JetInfoBlock; void *
0x10029bb4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10029bba  call    esi
0x10029bbc  mov     esi, eax
0x10029bbe  test    esi, esi
0x10029bc0  js      loc_10029C84
0x10029bc6  mov     esi, [esp+560h+var_538]
0x10029bca  mov     eax, [esi]
0x10029bcc  test    al, 20h
0x10029bce  jz      short loc_10029BF1
0x10029bd0  mov     eax, [esp+560h+var_53C]
  ... truncated ...
```
