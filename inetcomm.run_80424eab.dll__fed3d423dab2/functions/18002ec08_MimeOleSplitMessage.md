# MimeOleSplitMessage

- ea: `0x18002ec08`
- end: `0x18002f722`
- name: `MimeOleSplitMessage`
- size: `2842`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004bb50`

## callees

- `0x180002098`
- `0x180002cf0`
- `0x180005748`
- `0x180019e58`
- `0x180021140`
- `0x180022420`
- `0x18002c75c`
- `0x18002d690`
- `0x18002ec08`
- `0x1800518b4`
- `0x1800c3a9c`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrStreamSeekSet` at `0x18002f190`
- `MSOERT2!HrStreamSeekSet` at `0x18002f190`
- `MSOERT2!PszAllocA` at `0x18002f31b`
- `MSOERT2!PszAllocA` at `0x18002f355`
- `MSOERT2!PszAllocA` at `0x18002f31b`
- `MSOERT2!PszAllocA` at `0x18002f355`
- `MSOERT2!HrSafeGetStreamSize` at `0x18002ee8c`
- `MSOERT2!HrSafeGetStreamSize` at `0x18002ee8c`
- `MSOERT2!HrCopyStreamCBEndOnCRLF` at `0x18002f52e`
- `MSOERT2!HrCopyStreamCBEndOnCRLF` at `0x18002f52e`
- `SHLWAPI!__imp_IStream_Reset` at `0x18002ee76`
- `SHLWAPI!__imp_IStream_Reset` at `0x18002f55c`
- `SHLWAPI!__imp_IStream_Reset` at `0x18002ee76`
- `SHLWAPI!__imp_IStream_Reset` at `0x18002f55c`
- `KERNEL32!SystemTimeToFileTime` at `0x18002f097`
- `KERNEL32!SystemTimeToFileTime` at `0x18002f097`
- `KERNEL32!GetSystemTime` at `0x18002f089`
- `KERNEL32!GetSystemTime` at `0x18002f089`

## pseudocode

```c
__int64 __fastcall MimeOleSplitMessage(__int64 *a1, unsigned int a2, struct CMimeMessageParts **a3)
{
  __int64 v7; // rax
  char *v8; // r15
  __int64 v9; // r14
  int v10; // r13d
  void (__fastcall *v11)(__int64 *, __int64, __int128 *); // rax
  unsigned int v12; // ecx
  unsigned int i; // r8d
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rsi
  HRESULT StreamSize; // ebx
  struct CMimeMessageParts *v18; // r14
  int v19; // r13d
  float v20; // xmm1_4
  unsigned int v21; // r12d
  const char *LocalHostName; // rax
  int v23; // eax
  __int64 v24; // rdx
  bool v25; // sf
  __int64 v26; // rax
  __int64 v27; // r9
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned int v31; // edi
  unsigned int v32; // r13d
  unsigned int v33; // esi
  char *v34; // rdi
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rdx
  char *v37; // rsi
  IStream *v38; // rdi
  struct CMessageTree *v39; // rax
  __int64 v40; // [rsp+30h] [rbp-D0h]
  __int64 v41; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v42; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v43; // [rsp+44h] [rbp-BCh] BYREF
  IStream *pstm; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v45; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+60h] [rbp-A0h]
  int v47; // [rsp+68h] [rbp-98h]
  int v48; // [rsp+6Ch] [rbp-94h]
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  IStream *v50; // [rsp+78h] [rbp-88h] BYREF
  struct HCHARSET__ *v51; // [rsp+80h] [rbp-80h] BYREF
  char *v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  int v54; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v55; // [rsp+9Ch] [rbp-64h]
  struct _FILETIME FileTime; // [rsp+A0h] [rbp-60h] BYREF
  struct CMimeMessageParts *Instance; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v58; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-40h]
  __int128 v60; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v61; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+E0h] [rbp-20h]
  char *v63; // [rsp+E8h] [rbp-18h]
  struct CMessageTree *v64; // [rsp+F0h] [rbp-10h] BYREF
  struct CMimeMessageParts **v65; // [rsp+F8h] [rbp-8h]
  __int128 v66; // [rsp+100h] [rbp+0h] BYREF
  __int64 v67; // [rsp+110h] [rbp+10h]
  __int128 v68; // [rsp+118h] [rbp+18h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v70[140]; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v71; // [rsp+1CCh] [rbp+CCh]
  char v72[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v73[64]; // [rsp+200h] [rbp+100h] BYREF
  char v74[256]; // [rsp+240h] [rbp+140h] BYREF

  v65 = a3;
  v42 = 0;
  v54 = 0;
  v43 = 0;
  v53 = 0;
  pstm = 0;
  v50 = 0;
  v41 = 0;
  Instance = 0;
  v52 = 0;
  FileTime = 0;
  SystemTime = 0;
  v49 = 0;
  v68 = 0;
  v46 = 0;
  v45 = 0;
  v51 = 0;
  memset_0(v70, 0, 0x98u);
  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v59 = 0;
  v61 = 0;
  v67 = 0;
  v40 = 0;
  LOWORD(v45) = 19;
  v7 = *a1;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v58 = 0;
  v11 = *(void (__fastcall **)(__int64 *, __int64, __int128 *))(v7 + 296);
  v60 = 0;
  v66 = 0;
  v11(a1, 196627, &v45);
  v47 = DWORD2(v45);
  if ( (*(int (__fastcall **)(__int64 *, struct HCHARSET__ **))(*a1 + 224))(a1, &v51) >= 0
    && (int)MimeOleGetCharsetInfo(v51, v70) >= 0 )
  {
    v12 = v71;
    for ( i = 0; ; ++i )
    {
      v14 = 28LL * i;
      if ( !*(_DWORD *)((char *)&OENonStdCPs + v14) )
        break;
      if ( *(_DWORD *)((char *)&OENonStdCPs + v14) == v71 )
      {
        v15 = *(_DWORD *)((char *)&OENonStdCPs + v14 + 20);
        if ( v15 )
          v12 = v15;
        break;
      }
    }
    if ( v12 != v71 )
    {
      MimeOleMapCodePageToCharset(v12, &v51);
      (*(void (__fastcall **)(__int64 *, struct HCHARSET__ *, __int64))(*a1 + 232))(a1, v51, 2);
    }
  }
  v16 = -1;
  if ( (*(int (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 264))(a1, -1, 16) < 0
    || (v10 = 1,
        StreamSize = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 280))(a1, -1, 16),
        StreamSize >= 0) )
  {
    StreamSize = (*(__int64 (__fastcall **)(__int64 *, IStream **, __int64))(*a1 + 72))(a1, &pstm, 1);
    if ( StreamSize >= 0 )
    {
      if ( !v10
        || !(_WORD)v66
        || (StreamSize = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD, __int128 *))(*a1 + 272))(
                           a1,
                           -1,
                           16,
                           0,
                           &v66),
            StreamSize >= 0) )
      {
        Instance = CMimeMessageParts::CreateInstance();
        v18 = Instance;
        if ( !Instance )
        {
          StreamSize = -2147024882;
          goto LABEL_21;
        }
        StreamSize = IStream_Reset(pstm);
        if ( StreamSize < 0 )
          goto LABEL_21;
        StreamSize = HrSafeGetStreamSize(pstm, &v42);
        if ( StreamSize < 0 )
          goto LABEL_21;
        if ( v42 <= a2 )
        {
          StreamSize = (*(__int64 (__fastcall **)(struct CMimeMessageParts *, __int64 *))(*(_QWORD *)v18 + 32LL))(
                         v18,
                         a1);
          if ( StreamSize < 0 )
            goto LABEL_21;
LABEL_98:
          *v65 = v18;
          (*(void (__fastcall **)(struct CMimeMessageParts *))(*(_QWORD *)v18 + 8LL))(v18);
LABEL_99:
          v9 = v40;
          goto LABEL_100;
        }
        StreamSize = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64 *))(*a1 + 128))(
                       a1,
                       -1,
                       &IID_IMimeBody,
                       &v49);
        if ( StreamSize < 0 )
          goto LABEL_21;
        StreamSize = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v49 + 248LL))(v49, &v68);
        if ( StreamSize < 0 )
          goto LABEL_21;
        v19 = DWORD2(v68) - DWORD1(v68);
        if ( DWORD2(v68) - DWORD1(v68) >= v42 || v19 + 256 >= a2 )
        {
          StreamSize = -2146644445;
          goto LABEL_21;
        }
        StreamSize = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 192LL))(v49, &v41);
        if ( StreamSize < 0 )
        {
LABEL_21:
          v9 = 0;
          goto LABEL_100;
        }
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 112LL))(v41, 18);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 112LL))(v41, 22);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 112LL))(v41, 21);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 112LL))(v41, 20);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 112LL))(v41, 24);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 112LL))(v41, 17);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 112LL))(v41, 19);
        (*(void (__fastcall **)(__int64, const char *))(*(_QWORD *)v41 + 112LL))(v41, "Disposition-Notification-To");
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 112LL))(v41, 7);
        v62 = a2 - v19;
        v20 = (float)(int)v42 / (float)(int)v62;
        v21 = (int)v20;
        if ( (float)(v20 - (float)(int)v20) != 0.0 )
          ++v21;
        StreamSize = (*(__int64 (__fastcall **)(struct CMimeMessageParts *, _QWORD))(*(_QWORD *)v18 + 40LL))(v18, v21);
        if ( StreamSize >= 0 )
        {
          if ( v47 == 1 )
          {
            GetSystemTime(&SystemTime);
            SystemTimeToFileTime(&SystemTime, &FileTime);
            LocalHostName = SzGetLocalHostName();
            StringCchPrintfA(
              v74,
              0xFFu,
              "%08.8lX.%08.8lX@%s",
              FileTime.dwHighDateTime,
              FileTime.dwLowDateTime,
              LocalHostName);
            StringCchPrintfA(v72, 0x1Eu, "%d", v21);
            *((_QWORD *)&v45 + 1) = v72;
            LOWORD(v45) = 30;
            StreamSize = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, __int128 *))(*(_QWORD *)v41 + 96LL))(
                           v41,
                           "par:content-type:total",
                           0,
                           &v45);
            if ( StreamSize < 0 )
              goto LABEL_67;
            *((_QWORD *)&v45 + 1) = v74;
            StreamSize = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, __int128 *))(*(_QWORD *)v41 + 96LL))(
                           v41,
                           "par:content-type:id",
                           0,
                           &v45);
            if ( StreamSize < 0 )
              goto LABEL_67;
            *((_QWORD *)&v45 + 1) = "1.0";
            StreamSize = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v41 + 96LL))(
                           v41,
                           17,
                           0,
                           &v45);
            if ( StreamSize < 0 )
              goto LABEL_67;
          }
          else
          {
            StreamSize = HrStreamSeekSet(pstm, DWORD2(v68));
            if ( StreamSize < 0 )
              goto LABEL_67;
            v42 -= DWORD2(v68);
          }
          LOWORD(v58) = 30;
          v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v49 + 88LL))(
                  v49,
                  5,
                  0,
                  &v58);
          v24 = *((_QWORD *)&v58 + 1);
          v25 = v23 < 0;
          v26 = *a1;
          if ( v25 )
            v24 = 0;
          *((_QWORD *)&v58 + 1) = v24;
          if ( (*(int (__fastcall **)(__int64 *, unsigned int *, __int64 *))(v26 + 384))(a1, &v43, &v53) >= 0 )
          {
            LOWORD(v60) = 30;
            if ( v43 )
            {
              do
              {
                if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64))(*a1 + 264))(
                       a1,
                       *(_QWORD *)(v53 + 8LL * (unsigned int)v8),
                       45) >= 0 )
                  break;
                LODWORD(v8) = (_DWORD)v8 + 1;
              }
              while ( (unsigned int)v8 < v43 );
            }
          }
          StringCchPrintfA(v72, 0x1Eu, "%d", v21);
          v27 = -1;
          do
            ++v27;
          while ( v72[v27] );
          if ( *((_QWORD *)&v60 + 1) )
          {
            StringCchPrintfA(v73, 0x32u, "%%s [%%0%Idd/%d]", v27, v21);
            if ( *((_QWORD *)&v60 + 1) )
            {
              v28 = -1;
              do
                ++v28;
              while ( *(_BYTE *)(*((_QWORD *)&v60 + 1) + v28) );
            }
            else
            {
              LODWORD(v28) = 0;
            }
            v29 = -1;
            do
              ++v29;
            while ( v73[v29] );
            v30 = -1;
            do
              ++v30;
            while ( v72[v30] );
            LODWORD(v28) = v29 + v28;
          }
          else
          {
            StringCchPrintfA(v73, 0x32u, "[%%0%Idd/%d]", v27, v21);
            v30 = -1;
            do
              ++v30;
            while ( v73[v30] );
            v28 = -1;
            do
              ++v28;
            while ( v72[v28] );
          }
          v48 = v30 + v28;
          v31 = v30 + v28 + 1;
          v32 = 0;
          v8 = (char *)PszAllocA(v31);
          if ( v8 )
          {
            if ( *((_QWORD *)&v58 + 1) )
            {
              do
                ++v16;
              while ( *(_BYTE *)(*((_QWORD *)&v58 + 1) + v16) );
              v31 += v16;
            }
            v33 = v31 + 5;
            v55 = v31 + 5;
            v40 = PszAllocA(v31 + 5);
            v34 = (char *)v40;
            if ( !v40 )
            {
              StreamSize = -2147024882;
              v9 = 0;
              goto LABEL_100;
            }
            while ( v32 < v21 )
            {
              OE_SafeReleaseAndNullPtr<IStream>(&v50);
              StreamSize = MimeOleCreateVirtualStream(&v50);
              if ( StreamSize < 0 )
                goto LABEL_99;
              if ( v47 == 1 )
              {
                LOWORD(v45) = 30;
                *((_QWORD *)&v45 + 1) = "message/partial";
                StreamSize = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v41 + 96LL))(
                               v41,
                               18,
                               0,
                               &v45);
                if ( StreamSize < 0 )
                  goto LABEL_99;
                StringCchPrintfA(v72, 0x1Eu, "%d", v32 + 1);
                *((_QWORD *)&v45 + 1) = v72;
                StreamSize = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, __int128 *))(*(_QWORD *)v41 + 96LL))(
                               v41,
                               "par:content-type:number",
                               0,
                               &v45);
                if ( StreamSize < 0 )
                  goto LABEL_99;
              }
              v35 = (unsigned int)(v48 + 1);
              if ( *((_QWORD *)&v60 + 1) )
                StringCchPrintfA(v8, v35, v73);
              else
                StringCchPrintfA(v8, v35, v73, v32 + 1);
              v36 = v33;
              v37 = 0;
              if ( *((_QWORD *)&v58 + 1) )
                StringCchPrintfA(v34, v36, "%s %s", *((const char **)&v58 + 1), v8);
              else
                StringCchPrintfA(v34, v36, "%s", v8);
              *((_QWORD *)&v45 + 1) = v34;
              LOWORD(v45) = 30;
              StreamSize = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v41 + 96LL))(
                             v41,
                             5,
                             0,
                             &v45);
              if ( StreamSize < 0 )
                goto LABEL_99;
              v38 = v50;
              StreamSize = (*(__int64 (__fastcall **)(__int64, IStream *, __int64))(*(_QWORD *)v41 + 48LL))(v41, v50, 1);
              if ( StreamSize < 0 )
                goto LABEL_99;
              StreamSize = ((__int64 (__fastcall *)(IStream *, const char *, __int64))v38->lpVtbl->Write)(
                             v38,
                             "\r\n",
                             2);
              if ( StreamSize < 0 )
                goto LABEL_99;
              StreamSize = HrCopyStreamCBEndOnCRLF(pstm, v38, (unsigned int)v62, &v54);
              if ( StreamSize < 0 )
                goto LABEL_99;
              StreamSize = ((__int64 (__fastcall *)(IStream *, _QWORD))v38->lpVtbl->Commit)(v38, 0);
              if ( StreamSize < 0 )
                goto LABEL_99;
              StreamSize = IStream_Reset(v38);
              if ( StreamSize < 0 )
                goto LABEL_99;
              v52 = 0;
              v39 = CMessageTree::CreateInstance(0);
              v64 = v39;
              if ( v39 )
              {
                v63 = (char *)v39 + 32;
                StreamSize = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v39 + 4) + 64LL))((__int64)v39 + 32);
                if ( StreamSize >= 0 )
                {
                  v37 = v63;
                  v52 = v63;
                  (*(void (__fastcall **)(char *))(*(_QWORD *)v63 + 8LL))(v63);
                }
              }
              else
              {
                StreamSize = -2147024882;
              }
              OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v64);
              if ( StreamSize < 0 )
                goto LABEL_99;
              StreamSize = (*(__int64 (__fastcall **)(char *, IStream *))(*(_QWORD *)v37 + 40LL))(v37, v38);
              if ( StreamSize < 0 )
                goto LABEL_99;
              StreamSize = (*(__int64 (__fastcall **)(struct CMimeMessageParts *, char *))(*(_QWORD *)v18 + 32LL))(
                             v18,
                             v37);
              if ( StreamSize < 0 )
                goto LABEL_99;
              OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v52);
              OE_SafeReleaseAndNullPtr<IStream>(&v50);
              v34 = (char *)v40;
              ++v32;
              v33 = v55;
            }
            goto LABEL_98;
          }
          StreamSize = -2147024882;
        }
LABEL_67:
        v9 = 0;
      }
    }
  }
LABEL_100:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v49);
  OE_SafeReleaseAndNullPtr<IStream>(&pstm);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&Instance);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v41);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v52);
  OE_SafeReleaseAndNullPtr<IStream>(&v50);
  if ( v8 )
    ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v8);
  if ( v9 )
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v9);
  if ( v53 )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    v53 = 0;
  }
  MimeOleVariantFree(&v58);
  MimeOleVariantFree(&v60);
  MimeOleVariantFree(&v66);
  return (unsigned int)StreamSize;
}

```

## disassembly

```asm
0x18002ec08  mov     [rsp-8+arg_18], rbx
0x18002ec0d  push    rbp
0x18002ec0e  push    rsi
0x18002ec0f  push    rdi
0x18002ec10  push    r12
0x18002ec12  push    r13
0x18002ec14  push    r14
0x18002ec16  push    r15
0x18002ec18  lea     rbp, [rsp-250h]
0x18002ec20  sub     rsp, 350h
0x18002ec27  mov     rax, cs:__security_cookie
0x18002ec2e  xor     rax, rsp
0x18002ec31  mov     [rbp+280h+var_40], rax
0x18002ec38  xor     esi, esi
0x18002ec3a  mov     rbx, r8
0x18002ec3d  xorps   xmm0, xmm0
0x18002ec40  mov     [rbp+280h+var_288], rbx
0x18002ec44  mov     r12d, edx
0x18002ec47  mov     [rsp+380h+var_340], esi
0x18002ec4b  mov     rdi, rcx
0x18002ec4e  mov     [rbp+280h+var_2E8], esi
0x18002ec51  xorps   xmm1, xmm1
0x18002ec54  mov     [rsp+380h+var_33C], esi
0x18002ec58  xor     eax, eax
0x18002ec5a  mov     [rbp+280h+var_2F0], rsi
0x18002ec5e  xor     edx, edx; Val
0x18002ec60  mov     [rsp+380h+pstm], rsi
0x18002ec65  mov     r8d, 98h; Size
0x18002ec6b  mov     [rsp+380h+var_308], rsi
0x18002ec70  lea     rcx, [rbp+280h+var_240]; void *
0x18002ec74  mov     [rsp+380h+var_348], rsi
0x18002ec79  mov     [rbp+280h+var_2D8], rsi
0x18002ec7d  mov     [rbp+280h+var_2F8], rsi
0x18002ec81  mov     qword ptr [rbp+280h+FileTime.dwLowDateTime], rsi
0x18002ec85  movups  xmmword ptr [rbp+280h+SystemTime.wYear], xmm0
0x18002ec89  mov     [rsp+380h+var_310], rsi
0x18002ec8e  movups  [rbp+280h+var_268], xmm1
0x18002ec92  mov     [rsp+380h+var_320], rax
0x18002ec97  movups  [rsp+380h+var_330], xmm0
0x18002ec9c  mov     [rbp+280h+var_300], rsi
0x18002eca0  call    memset_0
0x18002eca5  test    rbx, rbx
0x18002eca8  jnz     short loc_18002ECB4
0x18002ecaa  mov     eax, 80070057h
0x18002ecaf  jmp     loc_18002F6EE
0x18002ecb4  xor     eax, eax
0x18002ecb6  mov     [rbx], rsi
0x18002ecb9  mov     [rbp+280h+var_2C0], rax
0x18002ecbd  lea     r8, [rsp+380h+var_330]
0x18002ecc2  mov     [rbp+280h+var_2A8], rax
0x18002ecc6  xorps   xmm0, xmm0
0x18002ecc9  mov     [rbp+280h+var_270], rax
0x18002eccd  xorps   xmm1, xmm1
0x18002ecd0  mov     eax, 13h
0x18002ecd5  mov     [rsp+380h+var_350], rsi
0x18002ecda  mov     word ptr [rsp+380h+var_330], ax
0x18002ecdf  mov     edx, 30013h
0x18002ece4  mov     rax, [rdi]
0x18002ece7  mov     rcx, rdi
0x18002ecea  mov     r15, rsi
0x18002eced  mov     r14, rsi
0x18002ecf0  mov     r13d, esi
0x18002ecf3  movups  [rbp+280h+var_2D0], xmm0
0x18002ecf7  mov     rax, [rax+128h]
0x18002ecfe  movups  [rbp+280h+var_2B8], xmm1
0x18002ed02  movups  [rbp+280h+var_280], xmm0
0x18002ed06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed0b  mov     eax, dword ptr [rsp+380h+var_330+8]
0x18002ed0f  lea     rdx, [rbp+280h+var_300]
0x18002ed13  mov     [rsp+380h+var_318], eax
0x18002ed17  mov     rcx, rdi
0x18002ed1a  mov     rax, [rdi]
0x18002ed1d  mov     rax, [rax+0E0h]
0x18002ed24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed29  test    eax, eax
0x18002ed2b  js      short loc_18002ED9B
0x18002ed2d  mov     rcx, [rbp+280h+var_300]
0x18002ed31  lea     rdx, [rbp+280h+var_240]
0x18002ed35  call    MimeOleGetCharsetInfo
0x18002ed3a  test    eax, eax
0x18002ed3c  js      short loc_18002ED9B
0x18002ed3e  mov     edx, [rbp+280h+var_1B4]
0x18002ed44  lea     r9, ?OENonStdCPs@@3QBU_tagOENonStdCP@@B; _tagOENonStdCP const near * const OENonStdCPs
0x18002ed4b  mov     ecx, edx
0x18002ed4d  mov     r8d, esi
0x18002ed50  mov     eax, r8d
0x18002ed53  imul    rax, 1Ch
0x18002ed57  cmp     [rax+r9], esi
0x18002ed5b  jz      short loc_18002ED72
0x18002ed5d  cmp     [rax+r9], edx
0x18002ed61  jz      short loc_18002ED68
0x18002ed63  inc     r8d
0x18002ed66  jmp     short loc_18002ED50
0x18002ed68  mov     eax, [rax+r9+14h]
0x18002ed6d  test    eax, eax
0x18002ed6f  cmovnz  ecx, eax; unsigned int
0x18002ed72  cmp     ecx, edx
0x18002ed74  jz      short loc_18002ED9B
0x18002ed76  lea     rdx, [rbp+280h+var_300]; struct HCHARSET__ **
0x18002ed7a  call    ?MimeOleMapCodePageToCharset@@YAJKPEAPEAUHCHARSET__@@@Z; MimeOleMapCodePageToCharset(ulong,HCHARSET__ * *)
0x18002ed7f  mov     rax, [rdi]
0x18002ed82  mov     r8d, 2
0x18002ed88  mov     rdx, [rbp+280h+var_300]
0x18002ed8c  mov     rcx, rdi
0x18002ed8f  mov     rax, [rax+0E8h]
0x18002ed96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed9b  mov     rax, [rdi]
0x18002ed9e  lea     rcx, [rbp+280h+var_280]
0x18002eda2  xor     r9d, r9d
0x18002eda5  mov     [rsp+380h+var_360], rcx
0x18002edaa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002edae  mov     rcx, rdi
0x18002edb1  mov     rdx, rsi
0x18002edb4  mov     rax, [rax+108h]
0x18002edbb  lea     ebx, [r9+10h]
0x18002edbf  mov     r8d, ebx
0x18002edc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edc7  test    eax, eax
0x18002edc9  js      short loc_18002EDF1
0x18002edcb  mov     rax, [rdi]
0x18002edce  lea     r13d, [rbx-0Fh]
0x18002edd2  mov     r8d, ebx
0x18002edd5  mov     rdx, rsi
0x18002edd8  mov     rcx, rdi
0x18002eddb  mov     rax, [rax+118h]
0x18002ede2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ede7  mov     ebx, eax
0x18002ede9  test    eax, eax
0x18002edeb  js      loc_18002F63E
0x18002edf1  mov     rax, [rdi]
0x18002edf4  lea     rdx, [rsp+380h+pstm]
0x18002edf9  mov     r8d, 1
0x18002edff  mov     rcx, rdi
0x18002ee02  mov     rax, [rax+48h]
0x18002ee06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee0b  mov     ebx, eax
0x18002ee0d  test    eax, eax
0x18002ee0f  js      loc_18002F63E
0x18002ee15  test    r13d, r13d
0x18002ee18  jz      short loc_18002EE53
0x18002ee1a  xor     r13d, r13d
0x18002ee1d  cmp     word ptr [rbp+280h+var_280], r13w
0x18002ee22  jz      short loc_18002EE53
0x18002ee24  mov     rax, [rdi]
0x18002ee27  lea     rcx, [rbp+280h+var_280]
0x18002ee2b  mov     [rsp+380h+var_360], rcx
0x18002ee30  lea     r8d, [r13+10h]
0x18002ee34  xor     r9d, r9d
0x18002ee37  mov     rdx, rsi
0x18002ee3a  mov     rcx, rdi
0x18002ee3d  mov     rax, [rax+110h]
0x18002ee44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee49  mov     ebx, eax
0x18002ee4b  test    eax, eax
0x18002ee4d  js      loc_18002F63E
0x18002ee53  call    ?CreateInstance@CMimeMessageParts@@SAPEAV1@XZ; CMimeMessageParts::CreateInstance(void)
0x18002ee58  mov     [rbp+280h+var_2D8], rax
0x18002ee5c  mov     r14, rax
0x18002ee5f  test    rax, rax
0x18002ee62  jnz     short loc_18002EE71
0x18002ee64  mov     ebx, 8007000Eh
0x18002ee69  mov     r14, r15
0x18002ee6c  jmp     loc_18002F63E
0x18002ee71  mov     rcx, [rsp+380h+pstm]; pstm
0x18002ee76  call    cs:__imp_IStream_Reset
0x18002ee7c  mov     ebx, eax
0x18002ee7e  test    eax, eax
0x18002ee80  js      short loc_18002EE69
0x18002ee82  mov     rcx, [rsp+380h+pstm]
0x18002ee87  lea     rdx, [rsp+380h+var_340]
0x18002ee8c  call    cs:__imp_HrSafeGetStreamSize
0x18002ee92  mov     ebx, eax
0x18002ee94  test    eax, eax
0x18002ee96  js      short loc_18002EE69
0x18002ee98  cmp     [rsp+380h+var_340], r12d
0x18002ee9d  ja      short loc_18002EEBC
0x18002ee9f  mov     rax, [r14]
0x18002eea2  mov     rdx, rdi
0x18002eea5  mov     rcx, r14
0x18002eea8  mov     rax, [rax+20h]
0x18002eeac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeb1  mov     ebx, eax
0x18002eeb3  test    eax, eax
0x18002eeb5  js      short loc_18002EE69
0x18002eeb7  jmp     loc_18002F623
0x18002eebc  mov     rax, [rdi]
0x18002eebf  lea     r9, [rsp+380h+var_310]
0x18002eec4  lea     r8, IID_IMimeBody
0x18002eecb  mov     rdx, rsi
0x18002eece  mov     rcx, rdi
0x18002eed1  mov     rax, [rax+80h]
0x18002eed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eedd  mov     ebx, eax
0x18002eedf  test    eax, eax
0x18002eee1  js      short loc_18002EE69
0x18002eee3  mov     rcx, [rsp+380h+var_310]
0x18002eee8  lea     rdx, [rbp+280h+var_268]
0x18002eeec  mov     rax, [rcx]
0x18002eeef  mov     rax, [rax+0F8h]
0x18002eef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eefb  mov     ebx, eax
0x18002eefd  test    eax, eax
0x18002eeff  js      loc_18002EE69
0x18002ef05  mov     r13d, dword ptr [rbp+280h+var_268+8]
0x18002ef09  sub     r13d, dword ptr [rbp+280h+var_268+4]
0x18002ef0d  cmp     r13d, [rsp+380h+var_340]
0x18002ef12  jnb     loc_18002F718
0x18002ef18  lea     eax, [r13+100h]
0x18002ef1f  cmp     eax, r12d
0x18002ef22  jnb     loc_18002F718
0x18002ef28  mov     rcx, [rsp+380h+var_310]
0x18002ef2d  lea     rdx, [rsp+380h+var_348]
0x18002ef32  mov     rax, [rcx]
0x18002ef35  mov     rax, [rax+0C0h]
0x18002ef3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef41  mov     ebx, eax
0x18002ef43  test    eax, eax
0x18002ef45  js      loc_18002EE69
0x18002ef4b  mov     rcx, [rsp+380h+var_348]
0x18002ef50  mov     edx, 12h
0x18002ef55  mov     rax, [rcx]
0x18002ef58  mov     rax, [rax+70h]
0x18002ef5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef61  mov     rcx, [rsp+380h+var_348]
0x18002ef66  mov     edx, 16h
0x18002ef6b  mov     rax, [rcx]
0x18002ef6e  mov     rax, [rax+70h]
0x18002ef72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef77  mov     rcx, [rsp+380h+var_348]
0x18002ef7c  mov     edx, 15h
0x18002ef81  mov     rax, [rcx]
0x18002ef84  mov     rax, [rax+70h]
0x18002ef88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef8d  mov     rcx, [rsp+380h+var_348]
0x18002ef92  mov     edx, 14h
0x18002ef97  mov     rax, [rcx]
0x18002ef9a  mov     rax, [rax+70h]
0x18002ef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efa3  mov     rcx, [rsp+380h+var_348]
0x18002efa8  mov     edx, 18h
0x18002efad  mov     rax, [rcx]
0x18002efb0  mov     rax, [rax+70h]
0x18002efb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efb9  mov     rcx, [rsp+380h+var_348]
0x18002efbe  mov     edx, 11h
0x18002efc3  mov     rax, [rcx]
0x18002efc6  mov     rax, [rax+70h]
0x18002efca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efcf  mov     rcx, [rsp+380h+var_348]
0x18002efd4  mov     edx, 13h
0x18002efd9  mov     rax, [rcx]
0x18002efdc  mov     rax, [rax+70h]
0x18002efe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efe5  mov     rcx, [rsp+380h+var_348]
0x18002efea  lea     rdx, aDispositionNot; "Disposition-Notification-To"
0x18002eff1  mov     rax, [rcx]
0x18002eff4  mov     rax, [rax+70h]
0x18002eff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002effd  mov     rcx, [rsp+380h+var_348]
0x18002f002  mov     edx, 7
0x18002f007  mov     rax, [rcx]
0x18002f00a  mov     rax, [rax+70h]
0x18002f00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f013  mov     eax, [rsp+380h+var_340]
0x18002f017  sub     r12d, r13d
0x18002f01a  mov     ecx, r12d
0x18002f01d  xorps   xmm1, xmm1
0x18002f020  xorps   xmm0, xmm0
0x18002f023  mov     [rbp+280h+var_2A0], rcx
0x18002f027  cvtsi2ss xmm1, rax
0x18002f02c  cvtsi2ss xmm0, rcx
0x18002f031  divss   xmm1, xmm0
0x18002f035  xorps   xmm0, xmm0
0x18002f038  cvttss2si r12, xmm1
0x18002f03d  mov     eax, r12d
0x18002f040  cvtsi2ss xmm0, rax
0x18002f045  subss   xmm1, xmm0
0x18002f049  ucomiss xmm1, cs:__real@00000000
0x18002f050  jp      short loc_18002F054
0x18002f052  jz      short loc_18002F057
0x18002f054  inc     r12d
0x18002f057  mov     rax, [r14]
0x18002f05a  mov     edx, r12d
0x18002f05d  mov     rcx, r14
0x18002f060  mov     rax, [rax+28h]
0x18002f064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f069  xor     r13d, r13d
0x18002f06c  mov     ebx, eax
0x18002f06e  test    eax, eax
0x18002f070  js      loc_18002F331
0x18002f076  cmp     [rsp+380h+var_318], 1
0x18002f07b  lea     ebx, [r13+1Eh]
0x18002f07f  jnz     loc_18002F188
0x18002f085  lea     rcx, [rbp+280h+SystemTime]; lpSystemTime
0x18002f089  call    cs:__imp_GetSystemTime
0x18002f08f  lea     rdx, [rbp+280h+FileTime]; lpFileTime
0x18002f093  lea     rcx, [rbp+280h+SystemTime]; lpSystemTime
0x18002f097  call    cs:__imp_SystemTimeToFileTime
0x18002f09d  call    ?SzGetLocalHostName@@YAPEADXZ; SzGetLocalHostName(void)
0x18002f0a2  mov     r9d, [rbp+280h+FileTime.dwHighDateTime]
  ... truncated ...
```
