# CDeviceNotificationController::RegisterNotification(ushort const *)

- ea: `0x180064934`
- end: `0x180065326`
- name: `?RegisterNotification@CDeviceNotificationController@@QEAAJPEBG@Z`
- size: `2546`
- prototype: `__int64 __fastcall(CDeviceNotificationController *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180070404`

## callees

- `0x180006640`
- `0x18000c7d0`
- `0x18001d7f0`
- `0x180064934`
- `0x18006532c`
- `0x180086910`
- `0x18009e9c8`
- `0x1800a1114`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a3de8`
- `0x1800ab738`
- `0x1800abcd0`
- `0x1800ac634`
- `0x1800acd7c`
- `0x1800b0ef0`
- `0x1800b0f88`
- `0x1800f5574`
- `0x1800f5798`
- `0x1800f5d60`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064d73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064ea2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006528b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064ea2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006528b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064c3e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180064c3e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180064d05`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180064d05`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18006504c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18006517b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18006504c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18006517b`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180065274`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180065274`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180064e2c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180064e3b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180064e45`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180064e2c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180064e3b`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180064e45`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180064e16`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180064e16`

## string_xrefs

- `0x180064ce3`: `CreateFile2`
- `0x180064cb7`: `BITSCreateFile2AsApp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CDeviceNotificationController::RegisterNotification(
        CDeviceNotificationController *this,
        const unsigned __int16 *a2)
{
  volatile signed __int32 *v4; // rbx
  __int64 v5; // r11
  __int64 v6; // rcx
  __int64 v7; // r9
  __int64 v8; // rax
  char *v9; // rax
  signed __int64 v10; // r10
  int v11; // edx
  int v12; // r8d
  char v13; // dl
  __int64 *v14; // rax
  volatile signed __int32 *v15; // r8
  unsigned __int16 *v16; // rax
  signed __int64 v17; // r8
  int v18; // ecx
  int v19; // edx
  unsigned __int64 v21; // rsi
  char *v22; // r13
  __int64 v23; // rsi
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rdx
  int v26; // r8d
  unsigned __int16 *v27; // rdi
  signed int v28; // ecx
  __int64 v29; // rax
  unsigned __int16 *v30; // rcx
  DWORD v31; // eax
  __int64 File2; // rsi
  const wchar_t *v33; // r13
  char LastError; // al
  unsigned int v35; // ecx
  CONFIGRET v36; // eax
  CONFIGRET v37; // r12d
  unsigned int v38; // ecx
  void **v39; // r12
  __int64 v40; // rax
  volatile signed __int32 *v41; // r8
  char *v42; // r10
  const unsigned __int16 *v43; // rsi
  const unsigned __int16 *v44; // rax
  const unsigned __int16 *v45; // r11
  __int64 v46; // rcx
  char *v47; // rcx
  signed __int64 v48; // r10
  int v49; // edx
  int v50; // r9d
  volatile signed __int32 *v51; // rdx
  __int64 v52; // rdx
  int v53; // eax
  int v54; // ecx
  __int64 v55; // rax
  __int64 v56; // rsi
  const unsigned __int16 **v57; // r13
  const unsigned __int16 *v58; // rsi
  const unsigned __int16 *v59; // rax
  const unsigned __int16 *v60; // rcx
  _QWORD *v61; // rax
  unsigned int v62; // edi
  __int64 v63; // [rsp+40h] [rbp-438h] BYREF
  unsigned int v64; // [rsp+48h] [rbp-430h]
  volatile signed __int32 *v65; // [rsp+50h] [rbp-428h] BYREF
  void **v66; // [rsp+58h] [rbp-420h]
  int TokenInformation; // [rsp+60h] [rbp-418h] BYREF
  void *v68; // [rsp+68h] [rbp-410h] BYREF
  CDeviceNotificationController *v69; // [rsp+70h] [rbp-408h] BYREF
  const unsigned __int16 *v70; // [rsp+80h] [rbp-3F8h] BYREF
  int v71; // [rsp+88h] [rbp-3F0h]
  int v72; // [rsp+8Ch] [rbp-3ECh]
  DWORD ReturnLength[2]; // [rsp+90h] [rbp-3E8h] BYREF
  char *v74; // [rsp+98h] [rbp-3E0h]
  HANDLE hObject; // [rsp+A0h] [rbp-3D8h]
  CDeviceNotificationController::CDriveNotify *v76; // [rsp+A8h] [rbp-3D0h]
  CDeviceNotificationController *v77; // [rsp+B0h] [rbp-3C8h]
  volatile signed __int32 *v78; // [rsp+C0h] [rbp-3B8h] BYREF
  unsigned __int64 v79; // [rsp+C8h] [rbp-3B0h]
  CDeviceNotificationController *v80; // [rsp+D0h] [rbp-3A8h]
  _QWORD v81[2]; // [rsp+D8h] [rbp-3A0h] BYREF
  __int128 v82; // [rsp+E8h] [rbp-390h]
  const unsigned __int16 **v83; // [rsp+F8h] [rbp-380h] BYREF
  __int64 v84; // [rsp+100h] [rbp-378h]
  unsigned __int16 *v85; // [rsp+110h] [rbp-368h]
  void **pExceptionObject; // [rsp+120h] [rbp-358h] BYREF
  __int128 v87; // [rsp+128h] [rbp-350h]
  unsigned int v88; // [rsp+138h] [rbp-340h]
  int v89; // [rsp+13Ch] [rbp-33Ch]
  int v90; // [rsp+140h] [rbp-338h]
  void **v91; // [rsp+180h] [rbp-2F8h] BYREF
  __int128 v92; // [rsp+188h] [rbp-2F0h]
  unsigned int v93; // [rsp+198h] [rbp-2E0h]
  int v94; // [rsp+19Ch] [rbp-2DCh]
  int v95; // [rsp+1A0h] [rbp-2D8h]
  void **v96; // [rsp+1E0h] [rbp-298h] BYREF
  __int128 v97; // [rsp+1E8h] [rbp-290h]
  int v98; // [rsp+1F8h] [rbp-280h]
  int v99; // [rsp+1FCh] [rbp-27Ch]
  int v100; // [rsp+200h] [rbp-278h]
  void **v101; // [rsp+240h] [rbp-238h] BYREF
  __int128 v102; // [rsp+248h] [rbp-230h]
  signed int v103; // [rsp+258h] [rbp-220h]
  int v104; // [rsp+25Ch] [rbp-21Ch]
  int v105; // [rsp+260h] [rbp-218h]
  _DWORD v106[4]; // [rsp+2A0h] [rbp-1D8h] BYREF
  __int64 v107; // [rsp+2B0h] [rbp-1C8h]

  v70 = a2;
  v77 = this;
  v80 = this;
  v64 = 0;
  hObject = (HANDLE)-1LL;
  v69 = 0;
  v76 = 0;
  _InterlockedIncrement(&dword_180145058);
  v65 = (volatile signed __int32 *)&GenericStringHandle<unsigned short>::s_EmptyString;
  v4 = (volatile signed __int32 *)GenericStringHandle<unsigned short>::NewString(a2);
  if ( _InterlockedExchangeAdd(&dword_180145058, 0xFFFFFFFF) == 1 )
    operator delete(&GenericStringHandle<unsigned short>::s_EmptyString, 0x10u);
  v65 = v4;
  v74 = (char *)this + 24;
  v5 = *((_QWORD *)this + 3);
  v6 = *(_QWORD *)(v5 + 8);
  HIDWORD(v84) = 0;
  v7 = v5;
  while ( !*(_BYTE *)(v6 + 25) )
  {
    v8 = *(_QWORD *)(v6 + 32);
    if ( (volatile signed __int32 *)v8 == v4 )
      goto LABEL_10;
    v9 = (char *)(v8 + 12);
    v10 = (char *)(v4 + 3) - v9;
    do
    {
      v11 = *(unsigned __int16 *)&v9[v10];
      v12 = *(unsigned __int16 *)v9 - v11;
      if ( v12 )
        break;
      v9 += 2;
    }
    while ( v11 );
    if ( v12 >= 0 )
    {
LABEL_10:
      v13 = 0;
      v7 = v6;
    }
    else
    {
      v13 = 1;
    }
    v14 = (__int64 *)(v6 + 16);
    if ( !v13 )
      v14 = (__int64 *)v6;
    v6 = *v14;
  }
  if ( !*(_BYTE *)(v7 + 25) )
  {
    v15 = *(volatile signed __int32 **)(v7 + 32);
    if ( v4 == v15 )
      goto LABEL_21;
    v16 = (unsigned __int16 *)(v4 + 3);
    v17 = (char *)v15 - (char *)v4;
    do
    {
      v18 = *(unsigned __int16 *)((char *)v16 + v17);
      v19 = *v16 - v18;
      if ( v19 )
        break;
      ++v16;
    }
    while ( v18 );
    if ( v19 >= 0 )
    {
LABEL_21:
      if ( v5 != v7 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, a2);
        GenericStringHandle<unsigned short>::FreeIt(&v65);
        return 0;
      }
    }
  }
  _InterlockedIncrement(v4 + 2);
  v68 = (void *)v4;
  v66 = &v68;
  v21 = *(_QWORD *)v4 + 1LL;
  v22 = (char *)(v4 + 3);
  if ( *(_QWORD *)v4 == -2 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)&v22[2 * v23] );
    v21 = v23 + 1;
  }
  v24 = (unsigned __int16 *)operator new(saturated_mul(v21, 2u));
  v27 = v24;
  *(_QWORD *)ReturnLength = v24;
  if ( !v21 )
  {
    v28 = -2147024809;
    goto LABEL_116;
  }
  if ( v21 <= 0x7FFFFFFF )
  {
    v29 = 2147483646;
    v25 = (unsigned __int16 *)(v4 + 3);
    v30 = v27;
    do
    {
      if ( !v29 )
        break;
      v26 = *v25;
      if ( !(_WORD)v26 )
        break;
      ++v25;
      *v30++ = v26;
      --v29;
      --v21;
    }
    while ( v21 );
    v24 = v30 - 1;
    if ( v21 )
      v24 = v30;
    v28 = v21 == 0 ? 0x8007007A : 0;
  }
  else
  {
    v28 = -2147024809;
  }
  *v24 = 0;
  if ( v28 < 0 )
  {
LABEL_116:
    v102 = 0;
    v101 = &ComError::`vftable';
    v103 = v28;
    v104 = 1027;
    v105 = 1;
    throw (ComError *)&v101;
  }
  if ( v68 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v68 + 2, 0xFFFFFFFF) == 1 )
      operator delete(v68, 0x10u);
    v68 = 0;
  }
  v85 = v27;
  v27[*(_QWORD *)v4 - 1] = 0;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v25, v26, (_DWORD)v27, 0, 3, 3, 0);
  ReturnLength[0] = 0;
  TokenInformation = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, ReturnLength) )
  {
    v81[1] = 0;
    v81[0] = 32;
    v82 = 0;
    if ( TokenInformation && IsAppContainerFileFunctionalitySupported() )
    {
      v33 = L"BITSCreateFile2AsApp";
      File2 = BITSCreateFile2AsApp(v27, 0x80000000, 3, 3, (struct _CREATEFILE2_EXTENDED_PARAMETERS *)v81);
    }
    else
    {
      v33 = L"CreateFile2";
      File2 = CreateFile2(v27, 0x80000000LL, 3, 3, v81);
    }
    if ( File2 == -1
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)&WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        (_DWORD)v33,
        LastError);
    }
    v22 = (char *)(v4 + 3);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v31 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids, v31);
    }
    File2 = -1;
  }
  hObject = (HANDLE)File2;
  if ( File2 == -1 )
  {
    if ( (int)GetLastError() > 0 )
      v35 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v35 = GetLastError();
    v87 = 0;
    pExceptionObject = &ComError::`vftable';
    v88 = v35;
    v89 = 4953;
    v90 = 1;
    throw (ComError *)&pExceptionObject;
  }
  memset_0(v106, 0, 0x1A0u);
  v106[0] = 416;
  v106[2] = 1;
  v107 = File2;
  v36 = CM_Register_Notification(v106, 0, DeviceEventCallback, &v69);
  v37 = v36;
  if ( v36 )
  {
    if ( (int)CM_MapCrToWin32Err(v36, 0xDu) > 0 )
      v38 = (unsigned __int16)CM_MapCrToWin32Err(v37, 0xDu) | 0x80070000;
    else
      v38 = CM_MapCrToWin32Err(v37, 0xDu);
    v92 = 0;
    v91 = &ComError::`vftable';
    v93 = v38;
    v94 = 4970;
    v95 = 1;
    throw (ComError *)&v91;
  }
  CloseHandle((HANDLE)File2);
  hObject = 0;
  v39 = (void **)operator new(0x18u);
  v66 = v39;
  if ( v39 )
  {
    v40 = GenericStringHandle<unsigned short>::NewString(v70);
    v63 = v40;
    *v39 = v69;
    _InterlockedIncrement((volatile signed __int32 *)(v40 + 8));
    v39[1] = (void *)v40;
    v39[2] = 0;
    GenericStringHandle<unsigned short>::FreeIt(&v63);
  }
  else
  {
    v39 = 0;
  }
  v76 = (CDeviceNotificationController::CDriveNotify *)v39;
  if ( !v39 )
  {
    v97 = 0;
    v96 = &ComError::`vftable';
    v98 = -2147024882;
    v99 = 0;
    v100 = 1;
    throw (ComError *)&v96;
  }
  _InterlockedIncrement(v4 + 2);
  v41 = v4;
  v78 = v4;
  v79 = (unsigned __int64)v39;
  v42 = v74;
  v43 = *(const unsigned __int16 **)v74;
  v44 = *(const unsigned __int16 **)(*(_QWORD *)v74 + 8LL);
  LODWORD(v63) = 0;
  v66 = 0;
  v45 = v43;
  if ( *((_BYTE *)v44 + 25) )
  {
    v70 = v44;
  }
  else
  {
    do
    {
      v70 = v44;
      v46 = *((_QWORD *)v44 + 4);
      if ( (volatile signed __int32 *)v46 == v4 )
        goto LABEL_85;
      v47 = (char *)(v46 + 12);
      v48 = v22 - v47;
      do
      {
        v49 = *(unsigned __int16 *)&v47[v48];
        v50 = *(unsigned __int16 *)v47 - v49;
        if ( v50 )
          break;
        v47 += 2;
      }
      while ( v49 );
      if ( v50 >= 0 )
      {
LABEL_85:
        LODWORD(v63) = 1;
        v45 = v44;
      }
      else
      {
        LODWORD(v63) = 0;
        v44 += 8;
      }
      v44 = *(const unsigned __int16 **)v44;
    }
    while ( !*((_BYTE *)v44 + 25) );
    v42 = v74;
  }
  if ( *((_BYTE *)v45 + 25) )
    goto LABEL_95;
  v51 = (volatile signed __int32 *)*((_QWORD *)v45 + 4);
  if ( v4 != v51 )
  {
    v52 = (char *)(v51 + 3) - v22;
    do
    {
      v53 = *(unsigned __int16 *)&v22[v52];
      v54 = *(unsigned __int16 *)v22 - v53;
      if ( v54 )
        break;
      v22 += 2;
    }
    while ( v53 );
    if ( v54 < 0 )
    {
LABEL_95:
      if ( *((_QWORD *)v42 + 1) == 0x555555555555555LL )
        std::_Xlength_error("map/set too long");
      v55 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<GenericStringHandle<unsigned short> const,CDeviceNotificationController::CDriveNotify *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<GenericStringHandle<unsigned short> const,CDeviceNotificationController::CDriveNotify *>,void *>>>(
              &v83,
              v42,
              v43,
              &v78);
      v56 = *(_QWORD *)(v55 + 8);
      *(_QWORD *)(v55 + 8) = 0;
      std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<GenericStringHandle<unsigned short> const,CDeviceNotificationController::CDriveNotify *>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<GenericStringHandle<unsigned short> const,CDeviceNotificationController::CDriveNotify *>,void *>>>(&v83);
      v71 = v63;
      v72 = (int)v66;
      std::_Tree_val<std::_Tree_simple_types<std::pair<GenericStringHandle<unsigned short> const,CDeviceNotificationController::CDriveNotify *>>>::_Insert_node(
        v74,
        &v70,
        v56);
      v41 = v78;
    }
  }
  if ( v41 && _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
    operator delete((void *)v41, 0x10u);
  v57 = (const unsigned __int16 **)((char *)v77 + 8);
  v77 = v69;
  v58 = *v57;
  v59 = (const unsigned __int16 *)*((_QWORD *)*v57 + 1);
  LODWORD(v63) = 0;
  v66 = 0;
  v60 = v58;
  if ( *((_BYTE *)v59 + 25) )
  {
    v70 = v59;
  }
  else
  {
    do
    {
      v70 = v59;
      if ( *((_QWORD *)v59 + 4) >= (unsigned __int64)v69 )
      {
        LODWORD(v63) = 1;
        v60 = v59;
      }
      else
      {
        LODWORD(v63) = 0;
        v59 += 8;
      }
      v59 = *(const unsigned __int16 **)v59;
    }
    while ( !*((_BYTE *)v59 + 25) );
  }
  if ( *((_BYTE *)v60 + 25) || (unsigned __int64)v69 < *((_QWORD *)v60 + 4) )
  {
    if ( v57[1] == (const unsigned __int16 *)0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v83 = v57;
    v84 = 0;
    v61 = operator new(0x30u);
    v61[4] = v77;
    v61[5] = v39;
    *v61 = v58;
    v61[1] = v58;
    v61[2] = v58;
    *((_WORD *)v61 + 12) = 0;
    v78 = (volatile signed __int32 *)v70;
    v79 = __PAIR64__((unsigned int)v66, v63);
    std::_Tree_val<std::_Tree_simple_types<std::pair<enum NotifiableSystemEvent const,ITriggerableNotifier *>>>::_Insert_node(
      v57,
      &v78,
      v61);
  }
  if ( v27 )
    operator delete(v27, 2u);
  v62 = v64;
  if ( v4 && _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    operator delete((void *)v4, 0x10u);
  return v62;
}

```

## disassembly

```asm
0x180064934  mov     [rsp+arg_10], rbx
0x180064939  mov     [rsp+arg_18], rsi
0x18006493e  push    rdi
0x18006493f  push    r12
0x180064941  push    r13
0x180064943  push    r14
0x180064945  push    r15
0x180064947  sub     rsp, 450h
0x18006494e  mov     rax, cs:__security_cookie
0x180064955  xor     rax, rsp
0x180064958  mov     [rsp+478h+var_38], rax
0x180064960  mov     rdi, rdx
0x180064963  mov     [rsp+478h+var_3F8], rdx
0x18006496b  mov     rsi, rcx
0x18006496e  mov     [rsp+478h+var_3C8], rcx
0x180064976  mov     [rsp+478h+var_3A8], rcx
0x18006497e  xor     r14d, r14d
0x180064981  mov     [rsp+478h+var_430], r14d
0x180064986  or      r15, 0FFFFFFFFFFFFFFFFh
0x18006498a  mov     [rsp+478h+hObject], r15
0x180064992  mov     [rsp+478h+var_408], r14
0x180064997  mov     [rsp+478h+var_3D0], r14
0x18006499f  lock inc cs:dword_180145058
0x1800649a6  lea     r12, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x1800649ad  mov     [rsp+478h+var_428], r12
0x1800649b2  mov     rcx, rdx
0x1800649b5  call    ?NewString@?$GenericStringHandle@G@@CAPEAUStringData@1@PEBG@Z; GenericStringHandle<ushort>::NewString(ushort const *)
0x1800649ba  mov     rbx, rax
0x1800649bd  mov     eax, r15d
0x1800649c0  lock xadd cs:dword_180145058, eax
0x1800649c8  add     eax, r15d
0x1800649cb  jnz     short loc_1800649D8
0x1800649cd  lea     edx, [rax+10h]; unsigned __int64
0x1800649d0  mov     rcx, r12; void *
0x1800649d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800649d8  mov     [rsp+478h+var_428], rbx
0x1800649dd  lea     rax, [rsi+18h]
0x1800649e1  mov     [rsp+478h+var_3E0], rax
0x1800649e9  mov     r11, [rax]
0x1800649ec  mov     rcx, [r11+8]
0x1800649f0  xor     eax, eax
0x1800649f2  mov     [rsp+478h+var_374], eax
0x1800649f9  mov     r9, r11
0x1800649fc  jmp     short loc_180064A44
0x1800649fe  mov     rax, [rcx+20h]
0x180064a02  cmp     rax, rbx
0x180064a05  jz      short loc_180064A31
0x180064a07  lea     r10, [rbx+0Ch]
0x180064a0b  add     rax, 0Ch
0x180064a0f  sub     r10, rax
0x180064a12  movzx   r8d, word ptr [rax]
0x180064a16  movzx   edx, word ptr [rax+r10]
0x180064a1b  sub     r8d, edx
0x180064a1e  jnz     short loc_180064A28
0x180064a20  add     rax, 2
0x180064a24  test    edx, edx
0x180064a26  jnz     short loc_180064A12
0x180064a28  test    r8d, r8d
0x180064a2b  jns     short loc_180064A31
0x180064a2d  mov     dl, 1
0x180064a2f  jmp     short loc_180064A37
0x180064a31  mov     dl, r14b
0x180064a34  mov     r9, rcx
0x180064a37  lea     rax, [rcx+10h]
0x180064a3b  test    dl, dl
0x180064a3d  cmovz   rax, rcx
0x180064a41  mov     rcx, [rax]
0x180064a44  cmp     [rcx+19h], r14b
0x180064a48  jz      short loc_1800649FE
0x180064a4a  cmp     [r9+19h], r14b
0x180064a4e  jnz     short loc_180064AC4
0x180064a50  mov     r8, [r9+20h]
0x180064a54  cmp     rbx, r8
0x180064a57  jz      short loc_180064A7C
0x180064a59  add     r8, 0Ch
0x180064a5d  lea     rax, [rbx+0Ch]
0x180064a61  sub     r8, rax
0x180064a64  movzx   edx, word ptr [rax]
0x180064a67  movzx   ecx, word ptr [rax+r8]
0x180064a6c  sub     edx, ecx
0x180064a6e  jnz     short loc_180064A78
0x180064a70  add     rax, 2
0x180064a74  test    ecx, ecx
0x180064a76  jnz     short loc_180064A64
0x180064a78  test    edx, edx
0x180064a7a  js      short loc_180064AC4
0x180064a7c  cmp     r11, r9
0x180064a7f  jz      short loc_180064AC4
0x180064a81  lea     r12, WPP_GLOBAL_Control
0x180064a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180064a8f  cmp     rcx, r12
0x180064a92  jz      short loc_180064AB3
0x180064a94  test    byte ptr [rcx+1Ch], 1
0x180064a98  jz      short loc_180064AB3
0x180064a9a  mov     edx, 0E6h
0x180064a9f  mov     r9, rdi
0x180064aa2  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x180064aa9  mov     rcx, [rcx+10h]
0x180064aad  call    WPP_SF_S
0x180064ab2  nop
0x180064ab3  lea     rcx, [rsp+478h+var_428]
0x180064ab8  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x180064abd  xor     eax, eax
0x180064abf  jmp     loc_1800652F9
0x180064ac4  lock inc dword ptr [rbx+8]
0x180064ac8  mov     [rsp+478h+var_410], rbx
0x180064acd  lea     rax, [rsp+478h+var_410]
0x180064ad2  mov     [rsp+478h+var_420], rax
0x180064ad7  mov     rsi, [rbx]
0x180064ada  inc     rsi
0x180064add  lea     r13, [rbx+0Ch]
0x180064ae1  cmp     rsi, r15
0x180064ae4  jnz     short loc_180064AF7
0x180064ae6  mov     rsi, r15
0x180064ae9  inc     rsi
0x180064aec  cmp     [r13+rsi*2+0], r14w
0x180064af2  jnz     short loc_180064AE9
0x180064af4  inc     rsi
0x180064af7  mov     eax, 2
0x180064afc  mul     rsi
0x180064aff  cmovb   rax, r15
0x180064b03  mov     rcx, rax; dwBytes
0x180064b06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064b0b  mov     rdi, rax
0x180064b0e  mov     qword ptr [rsp+478h+var_3E8], rax
0x180064b16  test    rsi, rsi
0x180064b19  jz      short loc_180064B74
0x180064b1b  cmp     rsi, 7FFFFFFFh
0x180064b22  jbe     short loc_180064B2B
0x180064b24  mov     ecx, 80070057h
0x180064b29  jmp     short loc_180064B82
0x180064b2b  mov     eax, 7FFFFFFEh
0x180064b30  mov     rdx, r13
0x180064b33  mov     rcx, rdi
0x180064b36  test    rax, rax
0x180064b39  jz      short loc_180064B5A
0x180064b3b  movzx   r8d, word ptr [rdx]
0x180064b3f  test    r8w, r8w
0x180064b43  jz      short loc_180064B5A
0x180064b45  add     rdx, 2
0x180064b49  mov     [rcx], r8w
0x180064b4d  add     rcx, 2
0x180064b51  dec     rax
0x180064b54  sub     rsi, 1
0x180064b58  jnz     short loc_180064B36
0x180064b5a  lea     rax, [rcx-2]
0x180064b5e  test    rsi, rsi
0x180064b61  cmovnz  rax, rcx
0x180064b65  neg     rsi
0x180064b68  sbb     ecx, ecx
0x180064b6a  not     ecx
0x180064b6c  and     ecx, 8007007Ah
0x180064b72  jmp     short loc_180064B82
0x180064b74  mov     ecx, 80070057h
0x180064b79  test    rsi, rsi
0x180064b7c  jz      loc_180065213
0x180064b82  mov     [rax], r14w
0x180064b86  test    ecx, ecx
0x180064b88  js      loc_180065213
0x180064b8e  mov     rcx, [rsp+478h+var_410]
0x180064b93  test    rcx, rcx
0x180064b96  jz      short loc_180064BB7
0x180064b98  mov     eax, r15d
0x180064b9b  lock xadd [rcx+8], eax
0x180064ba0  add     eax, r15d
0x180064ba3  jnz     short loc_180064BB2
0x180064ba5  lea     edx, [rax+10h]; unsigned __int64
0x180064ba8  mov     rcx, [rsp+478h+var_410]; void *
0x180064bad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180064bb2  mov     [rsp+478h+var_410], r14
0x180064bb7  mov     [rsp+478h+var_368], rdi
0x180064bbf  mov     rax, [rbx]
0x180064bc2  mov     [rdi+rax*2-2], r14w
0x180064bc8  lea     r12, WPP_GLOBAL_Control
0x180064bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180064bd6  cmp     rcx, r12
0x180064bd9  jz      short loc_180064C09
0x180064bdb  test    byte ptr [rcx+1Ch], 1
0x180064bdf  jz      short loc_180064C09
0x180064be1  mov     [rsp+478h+var_440], r14d
0x180064be6  mov     esi, 3
0x180064beb  mov     [rsp+478h+var_448], esi
0x180064bef  mov     [rsp+478h+var_450], esi
0x180064bf3  mov     dword ptr [rsp+478h+ReturnLength], 80000000h
0x180064bfb  mov     r9, rdi
0x180064bfe  mov     rcx, [rcx+10h]
0x180064c02  call    WPP_SF_SDDDD
0x180064c07  jmp     short loc_180064C0E
0x180064c09  mov     esi, 3
0x180064c0e  mov     [rsp+478h+var_3E8], r14d
0x180064c16  mov     [rsp+478h+TokenInformation], r14d
0x180064c1b  lea     rax, [rsp+478h+var_3E8]
0x180064c23  mov     [rsp+478h+ReturnLength], rax; ReturnLength
0x180064c28  mov     r9d, 4; TokenInformationLength
0x180064c2e  lea     r8, [rsp+478h+TokenInformation]; TokenInformation
0x180064c33  lea     edx, [r9+19h]; TokenInformationClass
0x180064c37  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180064c3e  call    cs:__imp_GetTokenInformation
0x180064c44  test    eax, eax
0x180064c46  jnz     short loc_180064C87
0x180064c48  mov     rax, cs:WPP_GLOBAL_Control
0x180064c4f  cmp     rax, r12
0x180064c52  jz      short loc_180064C7F
0x180064c54  test    byte ptr [rax+1Ch], 4
0x180064c58  jz      short loc_180064C7F
0x180064c5a  call    cs:__imp_GetLastError
0x180064c60  mov     edx, 28h ; '('
0x180064c65  mov     r9d, eax
0x180064c68  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x180064c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180064c76  mov     rcx, [rcx+10h]
0x180064c7a  call    WPP_SF_d
0x180064c7f  mov     rsi, r15
0x180064c82  jmp     loc_180064D52
0x180064c87  mov     [rsp+478h+var_398], r14
0x180064c8f  mov     [rsp+478h+var_3A0], 20h ; ' '
0x180064c9b  xorps   xmm0, xmm0
0x180064c9e  movdqu  [rsp+478h+var_390], xmm0
0x180064ca7  cmp     [rsp+478h+TokenInformation], r14d
0x180064cac  jz      short loc_180064CE3
0x180064cae  call    ?IsAppContainerFileFunctionalitySupported@@YA_NXZ; IsAppContainerFileFunctionalitySupported(void)
0x180064cb3  test    al, al
0x180064cb5  jz      short loc_180064CE3
0x180064cb7  lea     r13, aBitscreatefile; "BITSCreateFile2AsApp"
0x180064cbe  lea     rax, [rsp+478h+var_3A0]
0x180064cc6  mov     [rsp+478h+ReturnLength], rax; struct _CREATEFILE2_EXTENDED_PARAMETERS *
0x180064ccb  mov     r9d, esi; unsigned int
0x180064cce  mov     r8d, esi; unsigned int
0x180064cd1  mov     edx, 80000000h; unsigned int
0x180064cd6  mov     rcx, rdi; unsigned __int16 *
0x180064cd9  call    ?BITSCreateFile2AsApp@@YAPEAXPEBGKKKPEAU_CREATEFILE2_EXTENDED_PARAMETERS@@@Z; BITSCreateFile2AsApp(ushort const *,ulong,ulong,ulong,_CREATEFILE2_EXTENDED_PARAMETERS *)
0x180064cde  mov     rsi, rax
0x180064ce1  jmp     short loc_180064D0E
0x180064ce3  lea     r13, aCreatefile2; "CreateFile2"
0x180064cea  lea     rax, [rsp+478h+var_3A0]
0x180064cf2  mov     [rsp+478h+ReturnLength], rax
0x180064cf7  mov     r9d, esi
0x180064cfa  mov     r8d, esi
0x180064cfd  mov     edx, 80000000h
0x180064d02  mov     rcx, rdi
0x180064d05  call    cs:__imp_CreateFile2
0x180064d0b  mov     rsi, rax
0x180064d0e  cmp     rsi, r15
0x180064d11  jnz     short loc_180064D4E
0x180064d13  mov     rax, cs:WPP_GLOBAL_Control
0x180064d1a  cmp     rax, r12
0x180064d1d  jz      short loc_180064D4E
0x180064d1f  test    byte ptr [rax+1Ch], 2
0x180064d23  jz      short loc_180064D4E
0x180064d25  call    cs:__imp_GetLastError
0x180064d2b  mov     edx, 29h ; ')'
0x180064d30  mov     dword ptr [rsp+478h+ReturnLength], eax
0x180064d34  mov     r9, r13
0x180064d37  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x180064d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180064d45  mov     rcx, [rcx+10h]
0x180064d49  call    WPP_SF_Sd
0x180064d4e  lea     r13, [rbx+0Ch]
0x180064d52  mov     [rsp+478h+hObject], rsi
0x180064d5a  cmp     rsi, r15
0x180064d5d  jnz     short loc_180064DCD
0x180064d5f  call    cs:__imp_GetLastError
0x180064d65  test    eax, eax
0x180064d67  jg      short loc_180064D73
0x180064d69  call    cs:__imp_GetLastError
0x180064d6f  mov     ecx, eax
0x180064d71  jmp     short loc_180064D82
0x180064d73  call    cs:__imp_GetLastError
0x180064d79  movzx   ecx, ax
0x180064d7c  or      ecx, 80070000h
0x180064d82  xorps   xmm0, xmm0
0x180064d85  movups  [rsp+478h+var_350], xmm0
0x180064d8d  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180064d94  mov     [rsp+478h+pExceptionObject], rax
0x180064d9c  mov     [rsp+478h+var_340], ecx
0x180064da3  mov     [rsp+478h+var_33C], 1359h
0x180064dae  mov     [rsp+478h+var_338], 1
0x180064db9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180064dc0  lea     rcx, [rsp+478h+pExceptionObject]; pExceptionObject
0x180064dc8  call    _CxxThrowException_0
0x180064dcd  mov     r12d, 1A0h
0x180064dd3  mov     r8d, r12d; Size
0x180064dd6  xor     edx, edx; Val
0x180064dd8  lea     rcx, [rsp+478h+var_1D8]; void *
0x180064de0  call    memset_0
0x180064de5  mov     [rsp+478h+var_1D8], r12d
0x180064ded  mov     [rsp+478h+var_1D0], 1
0x180064df8  mov     [rsp+478h+var_1C8], rsi
0x180064e00  lea     r9, [rsp+478h+var_408]
0x180064e05  lea     r8, ?DeviceEventCallback@@YAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; DeviceEventCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180064e0c  xor     edx, edx
0x180064e0e  lea     rcx, [rsp+478h+var_1D8]
0x180064e16  call    cs:__imp_CM_Register_Notification
0x180064e1c  mov     r12d, eax
0x180064e1f  test    eax, eax
0x180064e21  jz      short loc_180064E9F
0x180064e23  mov     ebx, 0Dh
0x180064e28  mov     edx, ebx; DefaultErr
0x180064e2a  mov     ecx, eax; CmReturnCode
0x180064e2c  call    cs:__imp_CM_MapCrToWin32Err
  ... truncated ...
```
