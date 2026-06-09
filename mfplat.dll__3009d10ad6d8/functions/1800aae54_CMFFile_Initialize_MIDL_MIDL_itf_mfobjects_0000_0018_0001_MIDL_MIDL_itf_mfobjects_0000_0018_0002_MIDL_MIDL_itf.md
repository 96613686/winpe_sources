# CMFFile::Initialize(__MIDL___MIDL_itf_mfobjects_0000_0018_0001,__MIDL___MIDL_itf_mfobjects_0000_0018_0002,__MIDL___MIDL_itf_mfobjects_0000_0018_0003,int,ushort const *,void *)

- ea: `0x1800aae54`
- end: `0x1800aba95`
- name: `?Initialize@CMFFile@@AEAAJW4__MIDL___MIDL_itf_mfobjects_0000_0018_0001@@W4__MIDL___MIDL_itf_mfobjects_0000_0018_0002@@W4__MIDL___MIDL_itf_mfobjects_0000_0018_0003@@HPEBGPEAX@Z`
- size: `3137`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800b18fc`
- `0x18011bacc`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x18002eba0`
- `0x180038bf0`
- `0x18006fbbc`
- `0x18007ab70`
- `0x18007acb0`
- `0x18007ad60`
- `0x180097a3c`
- `0x180097d40`
- `0x180099ff0`
- `0x1800a02c8`
- `0x1800aae54`
- `0x1800b0724`
- `0x1800b0778`
- `0x18011fff0`
- `0x18012003c`
- `0x1801200d0`
- `0x180124ffc`
- `0x1801250c8`
- `0x180125210`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab634`
- `api-ms-win-core-file-fromapp-l1-1-0!CreateFileFromAppW` at `0x1800ab550`
- `api-ms-win-core-file-fromapp-l1-1-0!CreateFileFromAppW` at `0x1800ab5ee`
- `api-ms-win-core-file-fromapp-l1-1-0!CreateFileFromAppW` at `0x1800ab550`
- `api-ms-win-core-file-fromapp-l1-1-0!CreateFileFromAppW` at `0x1800ab5ee`
- `api-ms-win-core-file-fromapp-l1-1-0!GetFileAttributesExFromAppW` at `0x1800ab351`
- `api-ms-win-core-file-fromapp-l1-1-0!GetFileAttributesExFromAppW` at `0x1800ab351`

## pseudocode

```c
__int64 __fastcall CMFFile::Initialize(
        __int64 a1,
        int a2,
        int a3,
        char a4,
        int a5,
        const WCHAR *lpFileName,
        __int64 a7)
{
  _QWORD *v11; // rax
  CallStackTracing *v12; // rcx
  int v13; // esi
  int PropertyStore; // edi
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  CallStackTracing *v20; // rcx
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  int v24; // ecx
  int v25; // esi
  int v26; // esi
  int v27; // esi
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  int v30; // eax
  signed int LastError; // eax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  HANDLE FileFromAppW; // rax
  int v37; // edx
  int v38; // r8d
  DWORD dwFlagsAndAttributes; // eax
  signed int v40; // eax
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  int v43; // edx
  int v44; // ecx
  CallStackTracing *v45; // rcx
  struct CallStackContext *v46; // rax
  CallStackTracing *v47; // rcx
  struct CallStackContext *v48; // rax
  __int64 v49; // rax
  unsigned __int64 v50; // rdi
  unsigned __int16 *v51; // rax
  CallStackTracing *v52; // rcx
  struct CallStackContext *v53; // rax
  CallStackTracing *v54; // rcx
  struct CallStackContext *v55; // rax
  int v56; // ecx
  int v57; // eax
  void *v58; // rcx
  unsigned int BytesPerSector; // eax
  void *v60; // rcx
  unsigned int Alignment; // eax
  void *v62; // rcx
  char dwCreationDisposition; // [rsp+20h] [rbp-71h]
  int v65; // [rsp+50h] [rbp-41h] BYREF
  CallStackScopeTrace v66; // [rsp+54h] [rbp-3Dh] BYREF
  __int128 FileInformation; // [rsp+58h] [rbp-39h] BYREF
  __int128 v68; // [rsp+68h] [rbp-29h] BYREF
  unsigned int v69; // [rsp+78h] [rbp-19h]

  CallStackScopeTrace::CallStackScopeTrace(&v66, "CMFFile::Initialize", 705);
  FileInformation = 0;
  v69 = 0;
  v68 = 0;
  v11 = operator new(0x18u);
  if ( v11 )
  {
    *(_DWORD *)v11 = 0;
    v11[2] = v11 + 1;
    v11[1] = v11 + 1;
  }
  else
  {
    v11 = 0;
  }
  *(_QWORD *)(a1 + 208) = v11;
  if ( !v11 )
  {
    v12 = CallStackTracing::s_wpInstance;
    v13 = -2147024882;
    PropertyStore = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v12 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v12->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v12);
      if ( ThreadRelativeContext->m_result != -2147024882 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFFile::Initialize", 718, -2147024882);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v16 = 42;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids, a1, v13);
      goto LABEL_186;
    }
    goto LABEL_186;
  }
  PropertyStore = CreatePropertyStore((IPropertyStore **)(a1 + 216));
  if ( PropertyStore < 0 )
  {
    v17 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v17 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v17->m_fEnabled )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v17);
      if ( v18->m_result != PropertyStore )
        CallStackContext::TraceFailure(v18, "CMFFile::Initialize", 723, PropertyStore);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_186;
    v19 = 43;
    goto LABEL_25;
  }
  PropertyStore = CMFFile::UpdateStatistics((CMFFile *)a1);
  if ( PropertyStore < 0 )
  {
    v20 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v20 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v20->m_fEnabled )
    {
      v21 = CallStackTracing::GetThreadRelativeContext(v20);
      if ( v21->m_result != PropertyStore )
        CallStackContext::TraceFailure(v21, "CMFFile::Initialize", 724, PropertyStore);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_186;
    v19 = 44;
    goto LABEL_25;
  }
  switch ( a2 )
  {
    case 1:
      *(_DWORD *)(a1 + 184) = 0x80000000;
      v24 = 0x80000000;
LABEL_51:
      *(_DWORD *)(a1 + 188) = 5;
      if ( a5 )
      {
        v24 |= 0x10000u;
        *(_DWORD *)(a1 + 184) = v24;
      }
      if ( a3 )
      {
        v25 = a3 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 )
          {
            v27 = v26 - 1;
            if ( v27 )
            {
              if ( v27 != 1 )
              {
                v28 = CallStackTracing::s_wpInstance;
                v13 = -2147024809;
                PropertyStore = -2147024809;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::s_wpInstance = &stru_1801FC290;
                  if ( ((unsigned int (__fastcall *)(CallStackTracing *, __int64, __int64, __int64))stru_1801FC290.CheckVersionMatch)(
                         &stru_1801FC290,
                         2032,
                         0x80000000LL,
                         0x40000000) )
                  {
                    v28 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v28 = &stru_1801F8A30;
                    CallStackTracing::s_wpInstance = &stru_1801F8A30;
                  }
                }
                if ( v28->m_fEnabled )
                {
                  v29 = CallStackTracing::GetThreadRelativeContext(v28);
                  if ( v29->m_result != -2147024809 )
                    CallStackContext::TraceFailure(v29, "CMFFile::Initialize", 782, -2147024809);
                }
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                {
                  v16 = 46;
                  goto LABEL_14;
                }
                goto LABEL_186;
              }
              *(_DWORD *)(a1 + 192) = 2;
            }
            else
            {
              *(_DWORD *)(a1 + 192) = 4;
            }
          }
          else
          {
            *(_DWORD *)(a1 + 192) = 5;
          }
        }
        else
        {
          *(_DWORD *)(a1 + 192) = 1;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 192) = 3;
      }
      *(_DWORD *)(a1 + 196) |= 0x40000000u;
      v30 = *(_DWORD *)(a1 + 196);
      if ( a2 == 1 )
      {
        v30 |= 0x20000000u;
        *(_DWORD *)(a1 + 196) = v30;
      }
      if ( a5 )
      {
        v30 |= 0x100u;
        *(_DWORD *)(a1 + 196) = v30;
      }
      if ( (a4 & 1) != 0 )
      {
        if ( (v24 & 0x40000000) != 0 )
        {
          v30 |= 0x80000000;
          *(_DWORD *)(a1 + 196) = v30;
        }
        if ( v24 >= 0 )
        {
LABEL_83:
          if ( a5 )
            *(_DWORD *)(a1 + 196) = v30 | 0x4000000;
          *(_DWORD *)(a1 + 180) = 0;
          if ( a7 == -1 )
          {
            if ( GetFileAttributesExFromAppW(lpFileName, GetFileExInfoStandard, &FileInformation) )
            {
              CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetBlob(
                a1 + 16,
                (__int64)&MF_BYTESTREAM_LAST_MODIFIED_TIME,
                (char *)&v68 + 4,
                8u);
              if ( !HIDWORD(v68) && v69 <= 0xA00000 )
                *(_DWORD *)(a1 + 196) &= ~0x20000000u;
              goto LABEL_104;
            }
            LastError = GetLastError();
            PropertyStore = LastError;
            if ( LastError > 0 )
              PropertyStore = (unsigned __int16)LastError | 0x80070000;
            if ( PropertyStore != -2147024894 )
            {
              if ( PropertyStore < 0 )
              {
                v32 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::s_wpInstance = &stru_1801FC290;
                  if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                  {
                    v32 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v32 = &stru_1801F8A30;
                    CallStackTracing::s_wpInstance = &stru_1801F8A30;
                  }
                }
                if ( v32->m_fEnabled )
                {
                  v33 = CallStackTracing::GetThreadRelativeContext(v32);
                  if ( v33->m_result != PropertyStore )
                    CallStackContext::TraceFailure(v33, "CMFFile::Initialize", 855, PropertyStore);
                }
                if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                  goto LABEL_186;
                v19 = 47;
                goto LABEL_25;
              }
LABEL_104:
              PropertyStore = CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetString(
                                a1 + 16,
                                &MF_BYTESTREAM_ORIGIN_NAME,
                                lpFileName);
              if ( PropertyStore < 0 )
              {
                v34 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::s_wpInstance = &stru_1801FC290;
                  if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                  {
                    v34 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v34 = &stru_1801F8A30;
                    CallStackTracing::s_wpInstance = &stru_1801F8A30;
                  }
                }
                if ( v34->m_fEnabled )
                {
                  v35 = CallStackTracing::GetThreadRelativeContext(v34);
                  if ( v35->m_result != PropertyStore )
                    CallStackContext::TraceFailure(v35, "CMFFile::Initialize", 882, PropertyStore);
                }
                if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                  goto LABEL_186;
                v19 = 48;
                goto LABEL_25;
              }
              if ( a7 == -1 )
              {
                if ( (FileInformation & 0x10) != 0 )
                {
                  *(_DWORD *)(a1 + 180) |= 0x80u;
LABEL_158:
                  v49 = -1;
                  do
                    ++v49;
                  while ( lpFileName[v49] );
                  v50 = v49 + 1;
                  v51 = (unsigned __int16 *)operator new[](saturated_mul(v49 + 1, 2u));
                  *(_QWORD *)(a1 + 152) = v51;
                  if ( !v51 )
                  {
                    v52 = CallStackTracing::s_wpInstance;
                    v13 = -2147024882;
                    PropertyStore = -2147024882;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::s_wpInstance = &stru_1801FC290;
                      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                      {
                        v52 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v52 = &stru_1801F8A30;
                        CallStackTracing::s_wpInstance = &stru_1801F8A30;
                      }
                    }
                    if ( v52->m_fEnabled )
                    {
                      v53 = CallStackTracing::GetThreadRelativeContext(v52);
                      if ( v53->m_result != -2147024882 )
                        CallStackContext::TraceFailure(v53, "CMFFile::Initialize", 971, -2147024882);
                    }
                    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                    {
                      v16 = 54;
                      goto LABEL_14;
                    }
                    goto LABEL_186;
                  }
                  PropertyStore = StringCchCopyW(v51, v50, lpFileName);
                  if ( PropertyStore >= 0 )
                  {
                    v56 = *(_DWORD *)(a1 + 184);
                    v57 = *(_DWORD *)(a1 + 180);
                    *(_DWORD *)(a1 + 176) = a5;
                    if ( v56 < 0 )
                      v57 |= 1u;
                    if ( (v56 & 0x40000000) != 0 )
                      v57 |= 2u;
                    v58 = *(void **)(a1 + 160);
                    *(_DWORD *)(a1 + 180) = v57 | 4;
                    *(_DWORD *)(a1 + 180) |= (unsigned int)IsRemoteFile(v58) != 0 ? 8 : 2048;
                    BytesPerSector = GetBytesPerSector(*(void **)(a1 + 160));
                    v60 = *(void **)(a1 + 160);
                    *(_DWORD *)(a1 + 224) = BytesPerSector;
                    Alignment = GetFileReadAlignment(v60);
                    v62 = *(void **)(a1 + 160);
                    *(_DWORD *)(a1 + 232) = Alignment;
                    if ( (unsigned int)IsDeviceOpticalMedia(v62) )
                      CMFAttributesImpl<IMFAttributes,CMFCSLock>::SetUINT32(a1 + 16, MF_BYTESTREAM_OPTICAL_MEDIA, 1);
                    goto LABEL_186;
                  }
                  v54 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v54 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v54 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v54->m_fEnabled )
                  {
                    v55 = CallStackTracing::GetThreadRelativeContext(v54);
                    if ( v55->m_result != PropertyStore )
                      CallStackContext::TraceFailure(v55, "CMFFile::Initialize", 973, PropertyStore);
                  }
                  if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                    goto LABEL_186;
                  v19 = 55;
LABEL_25:
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v19,
                    &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids,
                    a1,
                    PropertyStore);
                  goto LABEL_186;
                }
                FileFromAppW = CreateFileFromAppW(
                                 lpFileName,
                                 *(_DWORD *)(a1 + 184),
                                 *(_DWORD *)(a1 + 188),
                                 0,
                                 *(_DWORD *)(a1 + 192),
                                 *(_DWORD *)(a1 + 196),
                                 0);
                *(_QWORD *)(a1 + 160) = FileFromAppW;
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 0x10u )
                  WPP_SF_qSDDDq(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v37,
                    v38,
                    a1,
                    (__int64)lpFileName,
                    *(_DWORD *)(a1 + 184),
                    *(_DWORD *)(a1 + 188),
                    *(_DWORD *)(a1 + 196),
                    (char)FileFromAppW);
                if ( *(_QWORD *)(a1 + 160) == -1 && (a4 & 2) != 0 )
                {
                  dwFlagsAndAttributes = *(_DWORD *)(a1 + 196);
                  *(_DWORD *)(a1 + 188) |= 2u;
                  *(_DWORD *)(a1 + 180) |= 0x400u;
                  *(_QWORD *)(a1 + 160) = CreateFileFromAppW(
                                            lpFileName,
                                            *(_DWORD *)(a1 + 184),
                                            *(_DWORD *)(a1 + 188),
                                            0,
                                            *(_DWORD *)(a1 + 192),
                                            dwFlagsAndAttributes,
                                            0);
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM >= 4u )
                    WPP_SF_q(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      50,
                      &WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids,
                      a1);
                }
                if ( *(_QWORD *)(a1 + 160) == -1 )
                {
                  v40 = GetLastError();
                  PropertyStore = v40;
                  if ( v40 > 0 )
                    PropertyStore = (unsigned __int16)v40 | 0x80070000;
                  if ( PropertyStore < 0 )
                  {
                    v41 = CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      CallStackTracing::s_wpInstance = &stru_1801FC290;
                      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                      {
                        v41 = CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v41 = &stru_1801F8A30;
                        CallStackTracing::s_wpInstance = &stru_1801F8A30;
                      }
                    }
                    if ( v41->m_fEnabled )
                    {
                      v42 = CallStackTracing::GetThreadRelativeContext(v41);
                      if ( v42->m_result != PropertyStore )
                        CallStackContext::TraceFailure(v42, "CMFFile::Initialize", 935, PropertyStore);
                    }
                    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                      goto LABEL_186;
                    v19 = 51;
                    goto LABEL_25;
                  }
                }
                *(_DWORD *)(a1 + 180) &= ~0x20u;
                PropertyStore = CMFFile::JoinWorkQueue((CMFFile *)a1);
                if ( PropertyStore < 0 )
                {
                  v45 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v45 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v45 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v45->m_fEnabled )
                  {
                    v46 = CallStackTracing::GetThreadRelativeContext(v45);
                    if ( v46->m_result != PropertyStore )
                      CallStackContext::TraceFailure(v46, "CMFFile::Initialize", 946, PropertyStore);
                  }
                  if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                    goto LABEL_186;
                  v19 = 52;
                  goto LABEL_25;
                }
              }
              else
              {
                *(_DWORD *)(a1 + 180) &= ~0x20u;
                *(_QWORD *)(a1 + 160) = a7;
                PropertyStore = CMFFile::JoinWorkQueue((CMFFile *)a1);
                if ( PropertyStore < 0 )
                {
                  v47 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v47 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v47 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v47->m_fEnabled )
                  {
                    v48 = CallStackTracing::GetThreadRelativeContext(v47);
                    if ( v48->m_result != PropertyStore )
                      CallStackContext::TraceFailure(v48, "CMFFile::Initialize", 961, PropertyStore);
                  }
                  if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                    goto LABEL_186;
                  v19 = 53;
                  goto LABEL_25;
                }
              }
              if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
              {
                dwCreationDisposition = *(_QWORD *)(a1 + 160);
                v65 = 1177695063;
                McTemplateU0s4ppz_EventWriteTransfer(
                  v44,
                  v43,
                  (unsigned int)&v65,
                  a1,
                  dwCreationDisposition,
                  (__int64)lpFileName);
              }
              goto LABEL_158;
            }
          }
          FileInformation = 0;
          v69 = 0;
          v68 = 0;
          goto LABEL_104;
        }
        v30 |= 0x20000000u;
      }
      else
      {
        v30 |= 0x8000000u;
      }
      *(_DWORD *)(a1 + 196) = v30;
      goto LABEL_83;
    case 2:
      *(_DWORD *)(a1 + 184) = 0x40000000;
      v24 = 0x40000000;
      goto LABEL_51;
    case 3:
      v24 = -1073741824;
      *(_DWORD *)(a1 + 184) = -1073741824;
      goto LABEL_51;
  }
  v22 = CallStackTracing::s_wpInstance;
  v13 = -2147024809;
  PropertyStore = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( ((unsigned int (__fastcall *)(CallStackTracing *, __int64, __int64, __int64))stru_1801FC290.CheckVersionMatch)(
           &stru_1801FC290,
           2032,
           0x80000000LL,
           0x40000000) )
    {
      v22 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v22 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v22->m_fEnabled )
  {
    v23 = CallStackTracing::GetThreadRelativeContext(v22);
    if ( v23->m_result != -2147024809 )
      CallStackContext::TraceFailure(v23, "CMFFile::Initialize", 746, -2147024809);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v16 = 45;
    goto LABEL_14;
  }
LABEL_186:
  CallStackScopeTrace::~CallStackScopeTrace(&v66);
  return (unsigned int)PropertyStore;
}

```

## disassembly

```asm
0x1800aae54  push    rbp
0x1800aae56  push    rbx
0x1800aae57  push    rsi
0x1800aae58  push    rdi
0x1800aae59  push    r12
0x1800aae5b  push    r13
0x1800aae5d  push    r14
0x1800aae5f  push    r15
0x1800aae61  lea     rbp, [rsp-7]
0x1800aae66  sub     rsp, 98h
0x1800aae6d  mov     rax, cs:__security_cookie
0x1800aae74  xor     rax, rsp
0x1800aae77  mov     [rbp+3Fh+var_50], rax
0x1800aae7b  mov     r15, [rbp+3Fh+lpFileName]
0x1800aae7f  mov     esi, r8d
0x1800aae82  mov     r14d, edx
0x1800aae85  mov     rbx, rcx
0x1800aae88  mov     r8d, 2C1h; int
0x1800aae8e  lea     rdx, aCmffileInitial; "CMFFile::Initialize"
0x1800aae95  lea     rcx, [rbp+3Fh+var_7C]; this
0x1800aae99  mov     r13d, r9d
0x1800aae9c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aaea1  xor     eax, eax
0x1800aaea3  xorps   xmm0, xmm0
0x1800aaea6  movups  [rbp+3Fh+FileInformation], xmm0
0x1800aaeaa  mov     [rbp+3Fh+var_58], eax
0x1800aaead  movups  [rbp+3Fh+var_68], xmm0
0x1800aaeb1  lea     ecx, [rax+18h]; Size
0x1800aaeb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800aaeb9  xor     r12d, r12d
0x1800aaebc  test    rax, rax
0x1800aaebf  jz      short loc_1800AAED1
0x1800aaec1  lea     rcx, [rax+8]
0x1800aaec5  mov     [rax], r12d
0x1800aaec8  mov     [rax+10h], rcx
0x1800aaecc  mov     [rcx], rcx
0x1800aaecf  jmp     short loc_1800AAED4
0x1800aaed1  mov     rax, r12
0x1800aaed4  mov     [rbx+0D0h], rax
0x1800aaedb  test    rax, rax
0x1800aaede  jnz     loc_1800AAF95
0x1800aaee4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaeeb  mov     esi, 8007000Eh
0x1800aaef0  mov     edi, esi
0x1800aaef2  test    rcx, rcx
0x1800aaef5  jnz     short loc_1800AAF35
0x1800aaef7  mov     rax, cs:stru_1801FC290.__vftable
0x1800aaefe  lea     rcx, stru_1801FC290
0x1800aaf05  mov     edx, 7F0h
0x1800aaf0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaf11  mov     rax, [rax+8]
0x1800aaf15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aaf1a  test    eax, eax
0x1800aaf1c  jnz     short loc_1800AAF2E
0x1800aaf1e  lea     rcx, stru_1801F8A30
0x1800aaf25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aaf2c  jmp     short loc_1800AAF35
0x1800aaf2e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aaf35  cmp     [rcx+8], r12b
0x1800aaf39  jz      short loc_1800AAF60
0x1800aaf3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aaf40  cmp     [rax+7CCh], esi
0x1800aaf46  jz      short loc_1800AAF60
0x1800aaf48  mov     r9d, esi; int
0x1800aaf4b  lea     rdx, aCmffileInitial; "CMFFile::Initialize"
0x1800aaf52  mov     r8d, 2CEh; int
0x1800aaf58  mov     rcx, rax; this
0x1800aaf5b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aaf60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800aaf67  jb      loc_1800ABA6A
0x1800aaf6d  mov     edx, 2Ah ; '*'
0x1800aaf72  mov     [rsp+0D0h+dwCreationDisposition], esi
0x1800aaf76  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aaf7d  lea     r8, WPP_70dae006293e3f5d25a39c9f8b703438_Traceguids
0x1800aaf84  mov     r9, rbx
0x1800aaf87  mov     rcx, [rcx+10h]
0x1800aaf8b  call    WPP_SF_qD
0x1800aaf90  jmp     loc_1800ABA6A
0x1800aaf95  lea     rcx, [rbx+0D8h]; ppStore
0x1800aaf9c  call    CreatePropertyStore
0x1800aafa1  mov     edi, eax
0x1800aafa3  test    eax, eax
0x1800aafa5  jns     loc_1800AB03B
0x1800aafab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aafb2  test    rcx, rcx
0x1800aafb5  jnz     short loc_1800AAFF5
0x1800aafb7  mov     rax, cs:stru_1801FC290.__vftable
0x1800aafbe  lea     rcx, stru_1801FC290
0x1800aafc5  mov     edx, 7F0h
0x1800aafca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aafd1  mov     rax, [rax+8]
0x1800aafd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aafda  test    eax, eax
0x1800aafdc  jnz     short loc_1800AAFEE
0x1800aafde  lea     rcx, stru_1801F8A30
0x1800aafe5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aafec  jmp     short loc_1800AAFF5
0x1800aafee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800aaff5  cmp     [rcx+8], r12b
0x1800aaff9  jz      short loc_1800AB020
0x1800aaffb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab000  cmp     [rax+7CCh], edi
0x1800ab006  jz      short loc_1800AB020
0x1800ab008  mov     r9d, edi; int
0x1800ab00b  lea     rdx, aCmffileInitial; "CMFFile::Initialize"
0x1800ab012  mov     r8d, 2D3h; int
0x1800ab018  mov     rcx, rax; this
0x1800ab01b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab020  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ab027  jb      loc_1800ABA6A
0x1800ab02d  mov     edx, 2Bh ; '+'
0x1800ab032  mov     [rsp+0D0h+dwCreationDisposition], edi
0x1800ab036  jmp     loc_1800AAF76
0x1800ab03b  mov     rcx, rbx; this
0x1800ab03e  call    ?UpdateStatistics@CMFFile@@AEAAJXZ; CMFFile::UpdateStatistics(void)
0x1800ab043  mov     edi, eax
0x1800ab045  test    eax, eax
0x1800ab047  jns     loc_1800AB0D9
0x1800ab04d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab054  test    rcx, rcx
0x1800ab057  jnz     short loc_1800AB097
0x1800ab059  mov     rax, cs:stru_1801FC290.__vftable
0x1800ab060  lea     rcx, stru_1801FC290
0x1800ab067  mov     edx, 7F0h
0x1800ab06c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab073  mov     rax, [rax+8]
0x1800ab077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab07c  test    eax, eax
0x1800ab07e  jnz     short loc_1800AB090
0x1800ab080  lea     rcx, stru_1801F8A30
0x1800ab087  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab08e  jmp     short loc_1800AB097
0x1800ab090  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab097  cmp     [rcx+8], r12b
0x1800ab09b  jz      short loc_1800AB0C2
0x1800ab09d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab0a2  cmp     [rax+7CCh], edi
0x1800ab0a8  jz      short loc_1800AB0C2
0x1800ab0aa  mov     r9d, edi; int
0x1800ab0ad  lea     rdx, aCmffileInitial; "CMFFile::Initialize"
0x1800ab0b4  mov     r8d, 2D4h; int
0x1800ab0ba  mov     rcx, rax; this
0x1800ab0bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab0c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ab0c9  jb      loc_1800ABA6A
0x1800ab0cf  mov     edx, 2Ch ; ','
0x1800ab0d4  jmp     loc_1800AB032
0x1800ab0d9  mov     ecx, r14d
0x1800ab0dc  mov     r9d, 40000000h
0x1800ab0e2  mov     r8d, 80000000h
0x1800ab0e8  sub     ecx, 1
0x1800ab0eb  jz      loc_1800AB1AF
0x1800ab0f1  sub     ecx, 1
0x1800ab0f4  jz      loc_1800AB1A3
0x1800ab0fa  cmp     ecx, 1
0x1800ab0fd  jz      loc_1800AB196
0x1800ab103  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab10a  mov     esi, 80070057h
0x1800ab10f  mov     edi, esi
0x1800ab111  test    rcx, rcx
0x1800ab114  jnz     short loc_1800AB154
0x1800ab116  mov     rax, cs:stru_1801FC290.__vftable
0x1800ab11d  lea     rcx, stru_1801FC290
0x1800ab124  mov     edx, 7F0h
0x1800ab129  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab130  mov     rax, [rax+8]
0x1800ab134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab139  test    eax, eax
0x1800ab13b  jnz     short loc_1800AB14D
0x1800ab13d  lea     rcx, stru_1801F8A30
0x1800ab144  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab14b  jmp     short loc_1800AB154
0x1800ab14d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab154  cmp     [rcx+8], r12b
0x1800ab158  jz      short loc_1800AB17F
0x1800ab15a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab15f  cmp     [rax+7CCh], esi
0x1800ab165  jz      short loc_1800AB17F
0x1800ab167  mov     r9d, esi; int
0x1800ab16a  lea     rdx, aCmffileInitial; "CMFFile::Initialize"
0x1800ab171  mov     r8d, 2EAh; int
0x1800ab177  mov     rcx, rax; this
0x1800ab17a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab17f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ab186  jb      loc_1800ABA6A
0x1800ab18c  mov     edx, 2Dh ; '-'
0x1800ab191  jmp     loc_1800AAF72
0x1800ab196  mov     ecx, 0C0000000h
0x1800ab19b  mov     [rbx+0B8h], ecx
0x1800ab1a1  jmp     short loc_1800AB1B9
0x1800ab1a3  mov     [rbx+0B8h], r9d
0x1800ab1aa  mov     ecx, r9d
0x1800ab1ad  jmp     short loc_1800AB1B9
0x1800ab1af  mov     [rbx+0B8h], r8d
0x1800ab1b6  mov     ecx, r8d
0x1800ab1b9  mov     r12d, [rbp+3Fh+arg_20]
0x1800ab1bd  mov     edx, 5
0x1800ab1c2  mov     [rbx+0BCh], edx
0x1800ab1c8  test    r12d, r12d
0x1800ab1cb  jz      short loc_1800AB1D7
0x1800ab1cd  bts     ecx, 10h
0x1800ab1d1  mov     [rbx+0B8h], ecx
0x1800ab1d7  test    esi, esi
0x1800ab1d9  jz      loc_1800AB2C2
0x1800ab1df  sub     esi, 1
0x1800ab1e2  jz      loc_1800AB2B6
0x1800ab1e8  sub     esi, 1
0x1800ab1eb  jz      loc_1800AB2AE
0x1800ab1f1  sub     esi, 1
0x1800ab1f4  jz      loc_1800AB2A2
0x1800ab1fa  cmp     esi, 1
0x1800ab1fd  jz      loc_1800AB296
0x1800ab203  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab20a  mov     esi, 80070057h
0x1800ab20f  mov     edi, esi
0x1800ab211  test    rcx, rcx
0x1800ab214  jnz     short loc_1800AB254
0x1800ab216  mov     rax, cs:stru_1801FC290.__vftable
0x1800ab21d  lea     rcx, stru_1801FC290
0x1800ab224  mov     edx, 7F0h
0x1800ab229  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab230  mov     rax, [rax+8]
0x1800ab234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab239  test    eax, eax
0x1800ab23b  jnz     short loc_1800AB24D
0x1800ab23d  lea     rcx, stru_1801F8A30
0x1800ab244  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ab24b  jmp     short loc_1800AB254
0x1800ab24d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800ab254  cmp     byte ptr [rcx+8], 0
0x1800ab258  jz      short loc_1800AB27F
0x1800ab25a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ab25f  cmp     [rax+7CCh], esi
0x1800ab265  jz      short loc_1800AB27F
0x1800ab267  mov     r9d, esi; int
0x1800ab26a  lea     rdx, aCmffileInitial; "CMFFile::Initialize"
0x1800ab271  mov     r8d, 30Eh; int
0x1800ab277  mov     rcx, rax; this
0x1800ab27a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ab27f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ab286  jb      loc_1800ABA6A
0x1800ab28c  mov     edx, 2Eh ; '.'
0x1800ab291  jmp     loc_1800AAF72
0x1800ab296  mov     dword ptr [rbx+0C0h], 2
0x1800ab2a0  jmp     short loc_1800AB2CC
0x1800ab2a2  mov     dword ptr [rbx+0C0h], 4
0x1800ab2ac  jmp     short loc_1800AB2CC
0x1800ab2ae  mov     [rbx+0C0h], edx
0x1800ab2b4  jmp     short loc_1800AB2CC
0x1800ab2b6  mov     dword ptr [rbx+0C0h], 1
0x1800ab2c0  jmp     short loc_1800AB2CC
0x1800ab2c2  mov     dword ptr [rbx+0C0h], 3
0x1800ab2cc  or      [rbx+0C4h], r9d
0x1800ab2d3  mov     edx, 20000000h
0x1800ab2d8  mov     eax, [rbx+0C4h]
0x1800ab2de  cmp     r14d, 1
0x1800ab2e2  jnz     short loc_1800AB2EC
0x1800ab2e4  or      eax, edx
0x1800ab2e6  mov     [rbx+0C4h], eax
0x1800ab2ec  xor     r14d, r14d
0x1800ab2ef  test    r12d, r12d
0x1800ab2f2  jz      short loc_1800AB2FE
0x1800ab2f4  bts     eax, 8
0x1800ab2f8  mov     [rbx+0C4h], eax
0x1800ab2fe  test    r13b, 1
0x1800ab302  jz      short loc_1800AB31A
0x1800ab304  test    r9d, ecx
0x1800ab307  jz      short loc_1800AB312
0x1800ab309  or      eax, r8d
0x1800ab30c  mov     [rbx+0C4h], eax
0x1800ab312  test    ecx, ecx
0x1800ab314  jns     short loc_1800AB324
0x1800ab316  or      eax, edx
0x1800ab318  jmp     short loc_1800AB31E
0x1800ab31a  bts     eax, 1Bh
0x1800ab31e  mov     [rbx+0C4h], eax
0x1800ab324  test    r12d, r12d
0x1800ab327  jz      short loc_1800AB333
0x1800ab329  bts     eax, 1Ah
0x1800ab32d  mov     [rbx+0C4h], eax
0x1800ab333  mov     rsi, [rbp+3Fh+arg_30]
0x1800ab337  mov     [rbx+0B4h], r14d
0x1800ab33e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800ab342  jnz     loc_1800AB447
0x1800ab348  lea     r8, [rbp+3Fh+FileInformation]; lpFileInformation
0x1800ab34c  xor     edx, edx; fInfoLevelId
0x1800ab34e  mov     rcx, r15; lpFileName
0x1800ab351  call    cs:__imp_GetFileAttributesExFromAppW
0x1800ab357  test    eax, eax
0x1800ab359  jnz     loc_1800AB414
0x1800ab35f  call    cs:__imp_GetLastError
0x1800ab365  mov     edi, eax
0x1800ab367  test    eax, eax
0x1800ab369  jle     short loc_1800AB374
0x1800ab36b  movzx   edi, ax
0x1800ab36e  or      edi, 80070000h
0x1800ab374  cmp     edi, 80070002h
0x1800ab37a  jz      loc_1800AB447
0x1800ab380  test    edi, edi
0x1800ab382  jns     loc_1800AB457
  ... truncated ...
```
