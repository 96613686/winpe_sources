# PlayUACSoundProc(void *)

- ea: `0x1400061a0`
- end: `0x1400068ee`
- name: `?PlayUACSoundProc@@YAKPEAX@Z`
- size: `1870`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400061a0`
- `0x14000eca4`
- `0x14000fbec`
- `0x140010798`
- `0x140010ad3`
- `0x140013928`
- `0x14001e050`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006220`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006292`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006292`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000685b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000685b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400067e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400067e1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006468`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140006468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000622e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000622e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006698`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400067ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400067f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400067ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400067f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006610`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006610`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400065c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400065c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x14000656d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x14000656d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140006689`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140006689`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1400066e7`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1400066e7`

## string_xrefs

- `0x140006219`: `audioses.dll`
- `0x140006288`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall PlayUACSoundProc(PVOID Parameter)
{
  _QWORD *v1; // rbx
  HMODULE Library; // rax
  HMODULE v3; // rdi
  signed int LastError; // eax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  FARPROC ProcAddress; // rax
  int v9; // esi
  _OWORD *v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rdx
  HANDLE EventW; // r14
  _QWORD *v14; // rax
  _QWORD *v15; // rsi
  void *v16; // rcx
  int ValueW; // esi
  __int64 v18; // rax
  __int64 v19; // rdx
  HANDLE FileW; // rax
  HANDLE v21; // rsi
  signed int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v33; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v38; // [rsp+68h] [rbp-98h]
  __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h]
  int v41; // [rsp+7Ch] [rbp-84h]
  int v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+84h] [rbp-7Ch]
  int v44; // [rsp+88h] [rbp-78h]
  int v45; // [rsp+8Ch] [rbp-74h]
  int v46; // [rsp+90h] [rbp-70h]
  int v47; // [rsp+94h] [rbp-6Ch]
  int v48; // [rsp+98h] [rbp-68h]
  int v49; // [rsp+9Ch] [rbp-64h]
  char v50[256]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v51; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v52; // [rsp+1B0h] [rbp+B0h]
  _BYTE v53[36]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v54; // [rsp+1E4h] [rbp+E4h]
  WCHAR FileName[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v33 = 0;
  v36 = 0;
  v35 = 0;
  memset_0(v53, 0, 0x130u);
  v51 = 0;
  v52 = 0;
  v1 = 0;
  v38 = 0;
  pcbData = 0;
  Library = LoadLibraryExW(L"audioses.dll", 0, 0x800u);
  v3 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      v6 = 12;
LABEL_7:
      v7 = (unsigned int)LastError;
LABEL_8:
      WPP_SF_D(*(_QWORD *)(v5 + 16), v6, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids, v7);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  v33 = 0;
  phkResult = 0;
  ProcAddress = GetProcAddress(Library, "DllGetClassObject");
  if ( !ProcAddress )
  {
    v9 = -2147418113;
    goto LABEL_14;
  }
  v9 = ((__int64 (__fastcall *)(GUID *, GUID *, HKEY *))ProcAddress)(
         &CLSID_AudioPlayerFacade,
         &IID_IClassFactory,
         &phkResult);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(HKEY, _QWORD, GUID *, __int64 *))(*(_QWORD *)phkResult + 24LL))(
           phkResult,
           0,
           &GUID_4d19ad40_4049_4c52_aa2a_84e4e52e9ec2,
           &v33);
    (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult + 16LL))(phkResult);
  }
  if ( v9 < 0 )
  {
LABEL_14:
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      v6 = 13;
      v7 = (unsigned int)v9;
      goto LABEL_8;
    }
    goto LABEL_79;
  }
  v39 = 304;
  v40 = -1443938343;
  v41 = 1163805248;
  v42 = -1275931228;
  v43 = -1299769296;
  v44 = 0x10000;
  v45 = 40;
  v46 = 500;
  v47 = 10000;
  v48 = 250;
  v49 = 5;
  memset_0(v50, 0, sizeof(v50));
  v10 = v53;
  v11 = &v39;
  v12 = 2;
  do
  {
    *v10 = *(_OWORD *)v11;
    v10[1] = *((_OWORD *)v11 + 1);
    v10[2] = *((_OWORD *)v11 + 2);
    v10[3] = *((_OWORD *)v11 + 3);
    v10[4] = *((_OWORD *)v11 + 4);
    v10[5] = *((_OWORD *)v11 + 5);
    v10[6] = *((_OWORD *)v11 + 6);
    v10[7] = *((_OWORD *)v11 + 7);
    v10 += 8;
    v11 += 16;
    --v12;
  }
  while ( v12 );
  *v10 = *(_OWORD *)v11;
  v10[1] = *((_OWORD *)v11 + 1);
  v10[2] = *((_OWORD *)v11 + 2);
  v54 = 0;
  LastError = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *, _BYTE *))(*(_QWORD *)v33 + 24LL))(
                v33,
                &GUID_81ef556b_a13d_4f0c_b88e_5eded83750f7,
                &v36,
                v53);
  if ( LastError >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v6 = 15;
        goto LABEL_7;
      }
      goto LABEL_79;
    }
    v1 = 0;
    v14 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v15 = v14;
    if ( v14 )
    {
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioPlaybackEvents>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioPlaybackEvents>(v14);
      *v15 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAudioPlaybackEvents>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *v15 = &CAudioPlaybackEventCallback::`vftable';
      v15[2] = EventW;
      v1 = v15;
    }
    v38 = v1;
    if ( !v1 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids);
      goto LABEL_37;
    }
    pcbData = 1040;
    FileName[0] = 0;
    phkResult = 0;
    ValueW = RegOpenCurrentUser(1u, &phkResult);
    if ( ValueW )
    {
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v19 = 10;
LABEL_46:
        WPP_SF_D(*(_QWORD *)(v18 + 16), v19, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids, (unsigned int)ValueW);
        goto LABEL_47;
      }
    }
    else
    {
      ValueW = RegGetValueW(
                 phkResult,
                 L"AppEvents\\Schemes\\Apps\\.Default\\WindowsUAC\\.Current",
                 0,
                 2u,
                 0,
                 FileName,
                 &pcbData);
      if ( !ValueW )
      {
LABEL_47:
        v18 = WPP_GLOBAL_Control;
        goto LABEL_48;
      }
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v19 = 11;
        goto LABEL_46;
      }
    }
LABEL_48:
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      v18 = WPP_GLOBAL_Control;
    }
    if ( ValueW )
    {
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 2) != 0 )
      {
        WPP_SF_D(*(_QWORD *)(v18 + 16), 17, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids, (unsigned int)ValueW);
        v16 = EventW;
        goto LABEL_78;
      }
LABEL_37:
      v16 = EventW;
LABEL_78:
      CloseHandle(v16);
      goto LABEL_79;
    }
    FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x60000080u, 0);
    v21 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_D(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          18,
          WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids,
          (unsigned int)v22);
        v16 = EventW;
        goto LABEL_78;
      }
      goto LABEL_37;
    }
    if ( GetFileType(FileW) == 3 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids);
      goto LABEL_76;
    }
    v23 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *, HANDLE))(*(_QWORD *)v33 + 32LL))(
            v33,
            &GUID_aa66e9d1_a5a6_435d_8677_155e8a01ee9f,
            &v35,
            v21);
    if ( v23 >= 0 )
    {
      v51 = 0x18u;
      v52 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, _QWORD *, _QWORD))(*(_QWORD *)v36 + 40LL))(
              v36,
              v35,
              &v51,
              v1,
              0);
      if ( v23 >= 0 )
      {
        WaitForSingleObject(EventW, 0x1388u);
        goto LABEL_76;
      }
      v24 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_76;
      v25 = 21;
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_76;
      v25 = 20;
    }
    WPP_SF_D(*(_QWORD *)(v24 + 16), v25, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids, (unsigned int)v23);
LABEL_76:
    CloseHandle(EventW);
    if ( !v21 )
      goto LABEL_79;
    v16 = v21;
    goto LABEL_78;
  }
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    v6 = 14;
    goto LABEL_7;
  }
LABEL_79:
  v26 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  if ( v3 )
    FreeLibrary(v3);
  if ( v1 )
    (*(void (__fastcall **)(_QWORD *))(*v1 + 16LL))(v1);
  v29 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return 0;
}

```

## disassembly

```asm
0x1400061a0  push    rbp
0x1400061a2  push    rbx
0x1400061a3  push    rsi
0x1400061a4  push    rdi
0x1400061a5  push    r12
0x1400061a7  push    r14
0x1400061a9  push    r15
0x1400061ab  lea     rbp, [rsp-610h]
0x1400061b3  sub     rsp, 710h
0x1400061ba  mov     rax, cs:__security_cookie
0x1400061c1  xor     rax, rsp
0x1400061c4  mov     [rbp+640h+var_40], rax
0x1400061cb  xor     r12d, r12d
0x1400061ce  mov     [rsp+740h+var_700], r12
0x1400061d3  mov     [rsp+740h+var_6E8], r12
0x1400061d8  mov     [rsp+740h+var_6F0], r12
0x1400061dd  xor     edx, edx; Val
0x1400061df  mov     r8d, 130h; Size
0x1400061e5  lea     rcx, [rbp+640h+var_580]; void *
0x1400061ec  call    memset_0
0x1400061f1  xorps   xmm0, xmm0
0x1400061f4  xor     eax, eax
0x1400061f6  movups  [rbp+640h+var_5A0], xmm0
0x1400061fd  mov     [rbp+640h+var_590], rax
0x140006204  mov     ebx, r12d
0x140006207  mov     [rsp+740h+var_6D8], rbx
0x14000620c  mov     [rsp+740h+var_6E0], r12d
0x140006211  xor     edx, edx; hFile
0x140006213  mov     r8d, 800h; dwFlags
0x140006219  lea     rcx, aAudiosesDll; "audioses.dll"
0x140006220  call    cs:__imp_LoadLibraryExW
0x140006226  mov     rdi, rax
0x140006229  test    rax, rax
0x14000622c  jnz     short loc_14000627E
0x14000622e  call    cs:__imp_GetLastError
0x140006234  test    eax, eax
0x140006236  jle     short loc_140006240
0x140006238  movzx   eax, ax
0x14000623b  or      eax, 80070000h
0x140006240  lea     r15, WPP_GLOBAL_Control
0x140006247  mov     rcx, cs:WPP_GLOBAL_Control
0x14000624e  cmp     rcx, r15
0x140006251  jz      loc_1400067FF
0x140006257  test    byte ptr [rcx+1Ch], 2
0x14000625b  jz      loc_1400067FF
0x140006261  mov     edx, 0Ch
0x140006266  mov     r9d, eax
0x140006269  lea     r8, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids
0x140006270  mov     rcx, [rcx+10h]
0x140006274  call    WPP_SF_D
0x140006279  jmp     loc_1400067FF
0x14000627e  mov     [rsp+740h+var_700], r12
0x140006283  mov     [rsp+740h+phkResult], r12
0x140006288  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x14000628f  mov     rcx, rdi; hModule
0x140006292  call    cs:__imp_GetProcAddress
0x140006298  test    rax, rax
0x14000629b  jnz     short loc_1400062A4
0x14000629d  mov     esi, 8000FFFFh
0x1400062a2  jmp     short loc_1400062F8
0x1400062a4  lea     r8, [rsp+740h+phkResult]
0x1400062a9  lea     rdx, IID_IClassFactory
0x1400062b0  lea     rcx, CLSID_AudioPlayerFacade
0x1400062b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062bc  mov     esi, eax
0x1400062be  test    eax, eax
0x1400062c0  js      short loc_1400062F4
0x1400062c2  mov     rcx, [rsp+740h+phkResult]
0x1400062c7  mov     rax, [rcx]
0x1400062ca  lea     r9, [rsp+740h+var_700]
0x1400062cf  lea     r8, _GUID_4d19ad40_4049_4c52_aa2a_84e4e52e9ec2
0x1400062d6  xor     edx, edx
0x1400062d8  mov     rax, [rax+18h]
0x1400062dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062e1  mov     esi, eax
0x1400062e3  mov     rcx, [rsp+740h+phkResult]
0x1400062e8  mov     rax, [rcx]
0x1400062eb  mov     rax, [rax+10h]
0x1400062ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062f4  test    esi, esi
0x1400062f6  jns     short loc_140006326
0x1400062f8  lea     r15, WPP_GLOBAL_Control
0x1400062ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140006306  cmp     rcx, r15
0x140006309  jz      loc_1400067FF
0x14000630f  test    byte ptr [rcx+1Ch], 2
0x140006313  jz      loc_1400067FF
0x140006319  mov     edx, 0Dh
0x14000631e  mov     r9d, esi
0x140006321  jmp     loc_140006269
0x140006326  mov     [rsp+740h+var_6D0], 130h
0x14000632f  mov     [rsp+740h+var_6C8], 0A9EF3FD9h
0x140006337  mov     [rsp+740h+var_6C4], 455E4240h
0x14000633f  mov     [rbp+640h+var_6C0], 0B3F2D5A4h
0x140006346  mov     [rbp+640h+var_6BC], 0B2871830h
0x14000634d  mov     [rbp+640h+var_6B8], 10000h
0x140006354  mov     [rbp+640h+var_6B4], 28h ; '('
0x14000635b  mov     [rbp+640h+var_6B0], 1F4h
0x140006362  mov     [rbp+640h+var_6AC], 2710h
0x140006369  mov     [rbp+640h+var_6A8], 0FAh
0x140006370  mov     [rbp+640h+var_6A4], 5
0x140006377  xor     edx, edx; Val
0x140006379  mov     r8d, 100h; Size
0x14000637f  lea     rcx, [rbp+640h+var_6A0]; void *
0x140006383  call    memset_0
0x140006388  lea     rax, [rbp+640h+var_580]
0x14000638f  lea     rcx, [rsp+740h+var_6D0]
0x140006394  mov     edx, 2
0x140006399  movups  xmm0, xmmword ptr [rcx]
0x14000639c  movups  xmmword ptr [rax], xmm0
0x14000639f  movups  xmm1, xmmword ptr [rcx+10h]
0x1400063a3  movups  xmmword ptr [rax+10h], xmm1
0x1400063a7  movups  xmm0, xmmword ptr [rcx+20h]
0x1400063ab  movups  xmmword ptr [rax+20h], xmm0
0x1400063af  movups  xmm1, xmmword ptr [rcx+30h]
0x1400063b3  movups  xmmword ptr [rax+30h], xmm1
0x1400063b7  movups  xmm0, xmmword ptr [rcx+40h]
0x1400063bb  movups  xmmword ptr [rax+40h], xmm0
0x1400063bf  movups  xmm1, xmmword ptr [rcx+50h]
0x1400063c3  movups  xmmword ptr [rax+50h], xmm1
0x1400063c7  movups  xmm0, xmmword ptr [rcx+60h]
0x1400063cb  movups  xmmword ptr [rax+60h], xmm0
0x1400063cf  movups  xmm1, xmmword ptr [rcx+70h]
0x1400063d3  movups  xmmword ptr [rax+70h], xmm1
0x1400063d7  lea     rax, [rax+80h]
0x1400063de  lea     rcx, [rcx+80h]
0x1400063e5  sub     rdx, 1
0x1400063e9  jnz     short loc_140006399
0x1400063eb  movups  xmm0, xmmword ptr [rcx]
0x1400063ee  movups  xmmword ptr [rax], xmm0
0x1400063f1  movups  xmm1, xmmword ptr [rcx+10h]
0x1400063f5  movups  xmmword ptr [rax+10h], xmm1
0x1400063f9  movups  xmm0, xmmword ptr [rcx+20h]
0x1400063fd  movups  xmmword ptr [rax+20h], xmm0
0x140006401  mov     [rbp+640h+var_55C], r12d
0x140006408  mov     rcx, [rsp+740h+var_700]
0x14000640d  mov     rax, [rcx]
0x140006410  lea     r9, [rbp+640h+var_580]
0x140006417  lea     r8, [rsp+740h+var_6E8]
0x14000641c  lea     rdx, _GUID_81ef556b_a13d_4f0c_b88e_5eded83750f7
0x140006423  mov     rax, [rax+18h]
0x140006427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000642c  test    eax, eax
0x14000642e  jns     short loc_14000645B
0x140006430  lea     r15, WPP_GLOBAL_Control
0x140006437  mov     rcx, cs:WPP_GLOBAL_Control
0x14000643e  cmp     rcx, r15
0x140006441  jz      loc_1400067FF
0x140006447  test    byte ptr [rcx+1Ch], 2
0x14000644b  jz      loc_1400067FF
0x140006451  mov     edx, 0Eh
0x140006456  jmp     loc_140006266
0x14000645b  xor     r9d, r9d; lpName
0x14000645e  xor     r8d, r8d; bInitialState
0x140006461  mov     edx, 1; bManualReset
0x140006466  xor     ecx, ecx; lpEventAttributes
0x140006468  call    cs:__imp_CreateEventW
0x14000646e  mov     r14, rax
0x140006471  test    rax, rax
0x140006474  jnz     short loc_1400064B3
0x140006476  call    cs:__imp_GetLastError
0x14000647c  test    eax, eax
0x14000647e  jle     short loc_140006488
0x140006480  movzx   eax, ax
0x140006483  or      eax, 80070000h
0x140006488  lea     r15, WPP_GLOBAL_Control
0x14000648f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006496  cmp     rcx, r15
0x140006499  jz      loc_1400067FF
0x14000649f  test    byte ptr [rcx+1Ch], 2
0x1400064a3  jz      loc_1400067FF
0x1400064a9  mov     edx, 0Fh
0x1400064ae  jmp     loc_140006266
0x1400064b3  mov     rbx, r12
0x1400064b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400064bd  mov     ecx, 18h; unsigned __int64
0x1400064c2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400064c7  mov     rsi, rax
0x1400064ca  test    rax, rax
0x1400064cd  jz      short loc_14000650E
0x1400064cf  mov     rcx, rax
0x1400064d2  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAudioPlaybackEvents@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioPlaybackEvents>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioPlaybackEvents>(void)
0x1400064d7  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAudioPlaybackEvents@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IAudioPlaybackEvents>::`vftable'
0x1400064de  mov     [rsi], rcx
0x1400064e1  mov     rdx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400064e8  test    rdx, rdx
0x1400064eb  jz      short loc_1400064FD
0x1400064ed  mov     rcx, [rdx]
0x1400064f0  mov     rax, [rcx+8]
0x1400064f4  mov     rcx, rdx
0x1400064f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064fc  nop
0x1400064fd  lea     rax, ??_7CAudioPlaybackEventCallback@@6B@; const CAudioPlaybackEventCallback::`vftable'
0x140006504  mov     [rsi], rax
0x140006507  mov     [rsi+10h], r14
0x14000650b  mov     rbx, rsi
0x14000650e  mov     [rsp+740h+var_6D8], rbx
0x140006513  test    rbx, rbx
0x140006516  jnz     short loc_14000654E
0x140006518  lea     r15, WPP_GLOBAL_Control
0x14000651f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006526  cmp     rcx, r15
0x140006529  jz      short loc_140006546
0x14000652b  test    byte ptr [rcx+1Ch], 2
0x14000652f  jz      short loc_140006546
0x140006531  mov     edx, 10h
0x140006536  lea     r8, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids
0x14000653d  mov     rcx, [rcx+10h]
0x140006541  call    WPP_SF_
0x140006546  mov     rcx, r14
0x140006549  jmp     loc_1400067F8
0x14000654e  mov     [rsp+740h+var_6E0], 410h
0x140006556  mov     [rbp+640h+FileName], r12w
0x14000655e  mov     [rsp+740h+phkResult], r12
0x140006563  lea     rdx, [rsp+740h+phkResult]; phkResult
0x140006568  mov     ecx, 1; samDesired
0x14000656d  call    cs:__imp_RegOpenCurrentUser
0x140006573  mov     esi, eax
0x140006575  lea     r15, WPP_GLOBAL_Control
0x14000657c  test    eax, eax
0x14000657e  jz      short loc_140006599
0x140006580  mov     rax, cs:WPP_GLOBAL_Control
0x140006587  cmp     rax, r15
0x14000658a  jz      short loc_140006606
0x14000658c  test    byte ptr [rax+1Ch], 2
0x140006590  jz      short loc_140006606
0x140006592  mov     edx, 0Ah
0x140006597  jmp     short loc_1400065EC
0x140006599  lea     rax, [rsp+740h+var_6E0]
0x14000659e  mov     [rsp+740h+pcbData], rax; pcbData
0x1400065a3  lea     rax, [rbp+640h+FileName]
0x1400065aa  mov     [rsp+740h+pvData], rax; pvData
0x1400065af  mov     [rsp+740h+pdwType], r12; pdwType
0x1400065b4  mov     r9d, 2; dwFlags
0x1400065ba  xor     r8d, r8d; lpValue
0x1400065bd  lea     rdx, SubKey; "AppEvents\\Schemes\\Apps\\.Default\\Win"...
0x1400065c4  mov     rcx, [rsp+740h+phkResult]; hkey
0x1400065c9  call    cs:__imp_RegGetValueW
0x1400065cf  mov     esi, eax
0x1400065d1  test    eax, eax
0x1400065d3  jz      short loc_1400065FF
0x1400065d5  mov     rax, cs:WPP_GLOBAL_Control
0x1400065dc  cmp     rax, r15
0x1400065df  jz      short loc_140006606
0x1400065e1  test    byte ptr [rax+1Ch], 2
0x1400065e5  jz      short loc_140006606
0x1400065e7  mov     edx, 0Bh
0x1400065ec  mov     r9d, esi
0x1400065ef  lea     r8, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids
0x1400065f6  mov     rcx, [rax+10h]
0x1400065fa  call    WPP_SF_D
0x1400065ff  mov     rax, cs:WPP_GLOBAL_Control
0x140006606  mov     rcx, [rsp+740h+phkResult]; hKey
0x14000660b  test    rcx, rcx
0x14000660e  jz      short loc_14000661D
0x140006610  call    cs:__imp_RegCloseKey
0x140006616  mov     rax, cs:WPP_GLOBAL_Control
0x14000661d  test    esi, esi
0x14000661f  jz      short loc_14000665F
0x140006621  jle     short loc_14000662C
0x140006623  movzx   esi, si
0x140006626  or      esi, 80070000h
0x14000662c  cmp     rax, r15
0x14000662f  jz      loc_140006546
0x140006635  test    byte ptr [rax+1Ch], 2
0x140006639  jz      loc_140006546
0x14000663f  mov     edx, 11h
0x140006644  mov     r9d, esi
0x140006647  lea     r8, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids
0x14000664e  mov     rcx, [rax+10h]
0x140006652  call    WPP_SF_D
0x140006657  mov     rcx, r14
0x14000665a  jmp     loc_1400067F8
0x14000665f  mov     [rsp+740h+pcbData], r12; hTemplateFile
0x140006664  mov     dword ptr [rsp+740h+pvData], 60000080h; dwFlagsAndAttributes
0x14000666c  mov     dword ptr [rsp+740h+pdwType], 3; dwCreationDisposition
0x140006674  xor     r9d, r9d; lpSecurityAttributes
0x140006677  mov     edx, 80000000h; dwDesiredAccess
0x14000667c  mov     r8d, 3; dwShareMode
0x140006682  lea     rcx, [rbp+640h+FileName]; lpFileName
0x140006689  call    cs:__imp_CreateFileW
0x14000668f  mov     rsi, rax
0x140006692  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006696  jnz     short loc_1400066E4
0x140006698  call    cs:__imp_GetLastError
0x14000669e  test    eax, eax
0x1400066a0  jle     short loc_1400066AA
0x1400066a2  movzx   eax, ax
0x1400066a5  or      eax, 80070000h
0x1400066aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400066b1  cmp     rcx, r15
0x1400066b4  jz      loc_140006546
0x1400066ba  test    byte ptr [rcx+1Ch], 2
0x1400066be  jz      loc_140006546
0x1400066c4  mov     edx, 12h
0x1400066c9  mov     r9d, eax
0x1400066cc  lea     r8, WPP_daf41cb0ac0e32f2830a41cf5cec412c_Traceguids
0x1400066d3  mov     rcx, [rcx+10h]
0x1400066d7  call    WPP_SF_D
0x1400066dc  mov     rcx, r14
  ... truncated ...
```
