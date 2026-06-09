# SynchronizeSidMasterKeys(void *,void *,ulong,int,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)

- ea: `0x18002e310`
- end: `0x18002ea43`
- name: `?SynchronizeSidMasterKeys@@YAKPEAX0KHPEAUDP_KEK@@1KPEAK2@Z`
- size: `1843`
- prototype: `__int64 __fastcall(_DWORD *, void *, unsigned int, int, struct DP_KEK *, struct DP_KEK *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002a03c`
- `0x18002e130`

## callees

- `0x180003080`
- `0x180004d80`
- `0x1800063c0`
- `0x180006510`
- `0x180006c60`
- `0x180007f10`
- `0x18000e9c0`
- `0x18000f910`
- `0x18001444c`
- `0x18001c340`
- `0x18001d810`
- `0x18001e1b4`
- `0x18002d8f0`
- `0x18002e310`
- `0x18002ea4c`
- `0x18002f4ac`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18002e7ae`
- `RPCRT4!UuidFromStringW` at `0x18002e7ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002e501`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e6b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e921`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e99f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e6b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e921`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e99f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e9f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e479`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e479`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002e8d5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002e8d5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002e55e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002e55e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002e9b4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002e9b4`

## string_xrefs

- `0x18002e40e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002e49a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002e57c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall SynchronizeSidMasterKeys(
        _DWORD *a1,
        void *a2,
        unsigned int a3,
        int a4,
        struct DP_KEK *a5,
        struct DP_KEK *a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int *a9)
{
  HLOCAL v10; // rdi
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  unsigned int v16; // ebx
  _WORD *v17; // r12
  __int64 v18; // rax
  size_t v19; // rbx
  char *v20; // rax
  char *v21; // r15
  __int64 v22; // r9
  int v23; // r15d
  HANDLE CurrentThread; // rax
  HANDLE v25; // rdi
  __int64 v26; // rax
  unsigned int v27; // eax
  _BYTE *v28; // rcx
  __int64 v29; // rax
  unsigned __int8 *v30; // rax
  unsigned __int8 *v31; // rcx
  void *v32; // rbx
  __int64 v33; // rax
  unsigned int v34; // eax
  int inserted; // eax
  __int64 v36; // rax
  unsigned int v37; // eax
  __int64 v38; // r9
  __int64 v39; // rax
  __int64 v40; // r9
  __int64 v41; // rcx
  int v42; // eax
  unsigned int v44; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hFindFile; // [rsp+70h] [rbp-90h]
  int v47; // [rsp+78h] [rbp-88h]
  struct _LUID v48; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v49; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v50; // [rsp+8Ch] [rbp-74h]
  int v51; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h] BYREF
  int ThreadAuthenticationId; // [rsp+A0h] [rbp-60h]
  struct DP_KEK *v54; // [rsp+A8h] [rbp-58h]
  void *v55; // [rsp+B0h] [rbp-50h]
  struct DP_KEK *v56; // [rsp+B8h] [rbp-48h]
  HLOCAL v57; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int *v58; // [rsp+C8h] [rbp-38h]
  UUID Uuid; // [rsp+D0h] [rbp-30h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF

  v10 = a2;
  v54 = a5;
  v50 = a3;
  v55 = a2;
  v56 = a6;
  v47 = a4;
  v58 = a9;
  Src = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v48 = 0;
  Uuid = 0;
  v57 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_DdD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v13, v14, a3, a4, a7);
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  v15 = CPSGetUserStorageArea(a1, v10, 0, 0, (unsigned __int16 **)&Src);
  v16 = v15;
  if ( v15 )
  {
    DebugTraceError(v15, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 1040);
    return v16;
  }
  v51 = 0;
  v17 = Src;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, Src);
  v18 = -1;
  do
    ++v18;
  while ( v17[v18] );
  v19 = (unsigned int)(2 * v18);
  v20 = (char *)LocalAlloc(0, (unsigned int)(v19 + 4));
  Src = v20;
  v21 = v20;
  if ( !v20 )
  {
    v16 = 8;
    v22 = 1057;
LABEL_17:
    DebugTraceError(v16, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v22);
    goto LABEL_98;
  }
  memcpy_0(v20, v17, v19);
  *(_DWORD *)&v21[v19] = 42;
  v16 = CPSImpersonateClient(a1);
  if ( v16 )
  {
    v22 = 1070;
    goto LABEL_17;
  }
  v23 = 1;
  if ( !v10 )
  {
    if ( (unsigned int)GetTokenUserSid(0, &v57) )
      v10 = v57;
    v55 = v10;
  }
  CurrentThread = GetCurrentThread();
  ThreadAuthenticationId = GetThreadAuthenticationId(CurrentThread, &v48);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_dd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      22,
      WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
      v48.LowPart,
      v48.HighPart);
  hFindFile = FindFirstFileW((LPCWSTR)Src, &FindFileData);
  v25 = hFindFile;
  if ( hFindFile == (HANDLE)-1LL )
    goto LABEL_91;
  v23 = 0;
  do
  {
    hMem = 0;
    v44 = 0;
    v49 = 0;
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      v26 = -1;
      do
        ++v26;
      while ( FindFileData.cFileName[v26] );
      if ( v26 == 36
        && FindFileData.cFileName[8] == 45
        && FindFileData.cFileName[13] == 45
        && FindFileData.cFileName[18] == 45
        && FindFileData.cFileName[23] == 45 )
      {
        ++v51;
        v27 = CPSRevertToSelf(a1);
        v16 = v27;
        if ( v27 )
        {
          v38 = 1137;
LABEL_88:
          DebugTraceError(v27, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v38);
          v23 = 1;
          goto LABEL_90;
        }
        v23 = 0;
        switch ( a7 )
        {
          case 1u:
            if ( ThreadAuthenticationId )
            {
              v37 = ReencryptMasterKey(a1, &v48, v17, FindFileData.cFileName);
              if ( v37 )
              {
                DebugTraceError(
                  v37,
                  "dwLastError",
                  "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
                  1257);
                goto LABEL_69;
              }
              goto LABEL_66;
            }
            v40 = 1237;
            break;
          case 2u:
            if ( ThreadAuthenticationId )
            {
              v34 = UuidFromStringW(FindFileData.cFileName, &Uuid);
              v16 = v34;
              if ( v34 )
              {
                v40 = 1163;
LABEL_83:
                v41 = v34;
                goto LABEL_80;
              }
              if ( (unsigned int)GetMasterKey(
                                   a1,
                                   v50,
                                   v17,
                                   v55,
                                   &v48,
                                   v47,
                                   FindFileData.cFileName,
                                   v54,
                                   v56,
                                   (unsigned __int8 **)&hMem,
                                   &v44,
                                   &v49) )
              {
                inserted = InsertMasterKeyCache(a1, &v48, v17, &Uuid, (unsigned __int8 *)hMem, v44);
                v28 = hMem;
                if ( inserted )
                {
                  if ( hMem )
                  {
                    v36 = v44;
                    if ( !v44 )
                      goto LABEL_46;
                    do
                    {
                      *v28++ = 0;
                      --v36;
                    }
                    while ( v36 );
                    goto LABEL_45;
                  }
                  goto LABEL_66;
                }
                if ( hMem )
                {
                  v39 = v44;
                  if ( v44 )
                  {
                    do
                    {
                      *v28++ = 0;
                      --v39;
                    }
                    while ( v39 );
                    v28 = hMem;
                  }
                  LocalFree(v28);
                }
                v40 = 1211;
              }
              else
              {
                v40 = 1188;
              }
            }
            else
            {
              v40 = 1156;
            }
            break;
          case 3u:
            if ( v54 )
            {
              v30 = (unsigned __int8 *)v54 + 20;
              v31 = (unsigned __int8 *)v54 + 40;
            }
            else
            {
              v30 = 0;
              v31 = 0;
            }
            v32 = v55;
            if ( UpdateDomainUserMasterKey(a1, v17, v55, v47, FindFileData.cFileName, v30, v31) )
            {
              if ( !(unsigned int)GetMasterKey(
                                    a1,
                                    v50,
                                    v17,
                                    v32,
                                    &v48,
                                    v47,
                                    FindFileData.cFileName,
                                    v54,
                                    v56,
                                    (unsigned __int8 **)&hMem,
                                    &v44,
                                    &v49) )
                goto LABEL_69;
              v28 = hMem;
              if ( hMem )
              {
                v33 = v44;
                if ( !v44 )
                  goto LABEL_46;
                do
                {
                  *v28++ = 0;
                  --v33;
                }
                while ( v33 );
LABEL_45:
                v28 = hMem;
LABEL_46:
                LocalFree(v28);
              }
            }
LABEL_66:
            if ( a8 )
              ++*a8;
            goto LABEL_69;
          default:
            if ( (unsigned int)GetMasterKey(
                                 a1,
                                 v50,
                                 v17,
                                 v55,
                                 &v48,
                                 v47,
                                 FindFileData.cFileName,
                                 v54,
                                 v56,
                                 (unsigned __int8 **)&hMem,
                                 &v44,
                                 &v49) )
            {
              v28 = hMem;
              if ( !hMem )
                goto LABEL_66;
              v29 = v44;
              if ( !v44 )
                goto LABEL_46;
              do
              {
                *v28++ = 0;
                --v29;
              }
              while ( v29 );
              goto LABEL_45;
            }
LABEL_69:
            v34 = CPSImpersonateClient(a1);
            v16 = v34;
            if ( !v34 )
              continue;
            v40 = 1376;
            goto LABEL_83;
        }
        v41 = 5;
        v16 = 5;
LABEL_80:
        DebugTraceError(v41, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v40);
        goto LABEL_90;
      }
    }
  }
  while ( FindNextFileW(hFindFile, &FindFileData) );
  v27 = CPSRevertToSelf(a1);
  v16 = v27;
  if ( v27 )
  {
    v38 = 1391;
    goto LABEL_88;
  }
  v16 = 0;
LABEL_90:
  v25 = hFindFile;
LABEL_91:
  if ( v57 )
    LocalFree(v57);
  if ( v25 != (HANDLE)-1LL )
    FindClose(v25);
  if ( v23 )
    CPSRevertToSelf(a1);
  v21 = (char *)Src;
LABEL_98:
  if ( v17 )
    LocalFree(v17);
  if ( v21 )
    LocalFree(v21);
  if ( !v16 && v58 )
  {
    if ( a8 )
      v42 = *a8;
    else
      v42 = 0;
    *v58 = v51 - v42;
  }
  return v16;
}

```

## disassembly

```asm
0x18002e310  push    rbp
0x18002e312  push    rbx
0x18002e313  push    rsi
0x18002e314  push    rdi
0x18002e315  push    r12
0x18002e317  push    r13
0x18002e319  push    r14
0x18002e31b  push    r15
0x18002e31d  lea     rbp, [rsp-248h]
0x18002e325  sub     rsp, 348h
0x18002e32c  mov     rax, cs:__security_cookie
0x18002e333  xor     rax, rsp
0x18002e336  mov     [rbp+280h+var_50], rax
0x18002e33d  mov     rax, [rbp+280h+arg_20]
0x18002e344  mov     r15d, r8d
0x18002e347  mov     rbx, [rbp+280h+arg_40]
0x18002e34e  mov     rdi, rdx
0x18002e351  mov     r14, [rbp+280h+arg_38]
0x18002e358  mov     r13, rcx
0x18002e35b  mov     [rbp+280h+var_2D8], rax
0x18002e35f  lea     rcx, [rbp+280h+FindFileData]; void *
0x18002e363  mov     rax, [rbp+280h+arg_28]
0x18002e36a  xor     r12d, r12d
0x18002e36d  mov     [rbp+280h+var_2F4], r8d
0x18002e371  mov     esi, r9d
0x18002e374  mov     [rbp+280h+var_2D0], rdx
0x18002e378  mov     r8d, 250h; Size
0x18002e37e  xor     edx, edx; Val
0x18002e380  mov     [rbp+280h+var_2C8], rax
0x18002e384  mov     [rsp+380h+var_308], r9d
0x18002e389  mov     [rbp+280h+var_2B8], rbx
0x18002e38d  mov     [rbp+280h+Src], r12
0x18002e391  call    memset_0
0x18002e396  xorps   xmm0, xmm0
0x18002e399  mov     qword ptr [rbp+280h+var_300.LowPart], r12
0x18002e39d  movups  xmmword ptr [rbp+280h+Uuid.Data1], xmm0
0x18002e3a1  mov     [rbp+280h+var_2C0], r12
0x18002e3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3ac  lea     rax, WPP_GLOBAL_Control
0x18002e3b3  cmp     rcx, rax
0x18002e3b6  jz      short loc_18002E3D8
0x18002e3b8  test    byte ptr [rcx+1Ch], 4
0x18002e3bc  jz      short loc_18002E3D8
0x18002e3be  mov     eax, [rbp+280h+arg_30]
0x18002e3c4  mov     r9d, r15d
0x18002e3c7  mov     rcx, [rcx+10h]
0x18002e3cb  mov     dword ptr [rsp+380h+var_358], eax
0x18002e3cf  mov     dword ptr [rsp+380h+var_360], esi
0x18002e3d3  call    WPP_SF_DdD
0x18002e3d8  test    r14, r14
0x18002e3db  jz      short loc_18002E3E0
0x18002e3dd  mov     [r14], r12d
0x18002e3e0  test    rbx, rbx
0x18002e3e3  jz      short loc_18002E3E8
0x18002e3e5  mov     [rbx], r12d
0x18002e3e8  lea     rax, [rbp+280h+Src]
0x18002e3ec  xor     r9d, r9d; int
0x18002e3ef  xor     r8d, r8d; int
0x18002e3f2  mov     [rsp+380h+var_360], rax; unsigned __int16 **
0x18002e3f7  mov     rdx, rdi; void *
0x18002e3fa  mov     rcx, r13; void *
0x18002e3fd  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x18002e402  mov     ebx, eax
0x18002e404  test    eax, eax
0x18002e406  jz      short loc_18002E428
0x18002e408  mov     r9d, 410h
0x18002e40e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002e415  lea     rdx, aDwlasterror; "dwLastError"
0x18002e41c  mov     ecx, eax
0x18002e41e  call    DebugTraceError
0x18002e423  jmp     loc_18002EA1D
0x18002e428  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e42f  lea     rax, WPP_GLOBAL_Control
0x18002e436  mov     [rbp+280h+var_2F0], r12d
0x18002e43a  mov     r12, [rbp+280h+Src]
0x18002e43e  cmp     rcx, rax
0x18002e441  jz      short loc_18002E461
0x18002e443  test    byte ptr [rcx+1Ch], 4
0x18002e447  jz      short loc_18002E461
0x18002e449  mov     rcx, [rcx+10h]
0x18002e44d  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002e454  mov     edx, 15h
0x18002e459  mov     r9, r12
0x18002e45c  call    WPP_SF_S
0x18002e461  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e465  xor     esi, esi
0x18002e467  inc     rax
0x18002e46a  cmp     [r12+rax*2], si
0x18002e46f  jnz     short loc_18002E467
0x18002e471  lea     ebx, [rax+rax]
0x18002e474  xor     ecx, ecx; uFlags
0x18002e476  lea     edx, [rbx+4]; uBytes
0x18002e479  call    cs:__imp_LocalAlloc
0x18002e480  nop     dword ptr [rax+rax+00h]
0x18002e485  mov     [rbp+280h+Src], rax
0x18002e489  mov     r15, rax
0x18002e48c  test    rax, rax
0x18002e48f  jnz     short loc_18002E4B4
0x18002e491  lea     ebx, [rax+8]
0x18002e494  mov     r9d, 421h
0x18002e49a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002e4a1  mov     ecx, ebx
0x18002e4a3  lea     rdx, aDwlasterror; "dwLastError"
0x18002e4aa  call    DebugTraceError
0x18002e4af  jmp     loc_18002E9D1
0x18002e4b4  mov     r8, rbx; Size
0x18002e4b7  mov     rdx, r12; Src
0x18002e4ba  mov     rcx, r15; void *
0x18002e4bd  call    memcpy_0
0x18002e4c2  mov     rcx, r13; void *
0x18002e4c5  mov     dword ptr [rbx+r15], 2Ah ; '*'
0x18002e4cd  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x18002e4d2  mov     ebx, eax
0x18002e4d4  test    eax, eax
0x18002e4d6  jz      short loc_18002E4E0
0x18002e4d8  mov     r9d, 42Eh
0x18002e4de  jmp     short loc_18002E49A
0x18002e4e0  mov     r15d, 1
0x18002e4e6  test    rdi, rdi
0x18002e4e9  jnz     short loc_18002E501
0x18002e4eb  lea     rdx, [rbp+280h+var_2C0]
0x18002e4ef  xor     ecx, ecx
0x18002e4f1  call    GetTokenUserSid
0x18002e4f6  test    eax, eax
0x18002e4f8  cmovnz  rdi, [rbp+280h+var_2C0]
0x18002e4fd  mov     [rbp+280h+var_2D0], rdi
0x18002e501  call    cs:__imp_GetCurrentThread
0x18002e508  nop     dword ptr [rax+rax+00h]
0x18002e50d  mov     rcx, rax
0x18002e510  lea     rdx, [rbp+280h+var_300]
0x18002e514  call    GetThreadAuthenticationId
0x18002e519  mov     [rbp+280h+var_2E0], eax
0x18002e51c  mov     r10, cs:WPP_GLOBAL_Control
0x18002e523  lea     rax, WPP_GLOBAL_Control
0x18002e52a  cmp     r10, rax
0x18002e52d  jz      short loc_18002E556
0x18002e52f  test    byte ptr [r10+1Ch], 4
0x18002e534  jz      short loc_18002E556
0x18002e536  mov     ecx, [rbp+280h+var_300.HighPart]
0x18002e539  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002e540  mov     r9d, [rbp+280h+var_300.LowPart]
0x18002e544  mov     edx, 16h
0x18002e549  mov     dword ptr [rsp+380h+var_360], ecx
0x18002e54d  mov     rcx, [r10+10h]
0x18002e551  call    WPP_SF_dd
0x18002e556  mov     rcx, [rbp+280h+Src]; lpFileName
0x18002e55a  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x18002e55e  call    cs:__imp_FindFirstFileW
0x18002e565  nop     dword ptr [rax+rax+00h]
0x18002e56a  mov     [rsp+380h+hFindFile], rax
0x18002e56f  mov     rdi, rax
0x18002e572  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e576  jz      loc_18002E993
0x18002e57c  lea     rdi, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002e583  xor     r15d, r15d
0x18002e586  lea     rsi, aDwlasterror; "dwLastError"
0x18002e58d  test    byte ptr [rbp+280h+FindFileData.dwFileAttributes], 10h
0x18002e591  mov     [rsp+380h+hMem], r15
0x18002e596  mov     [rsp+380h+var_320], r15d
0x18002e59b  mov     [rbp+280h+var_2F8], r15d
0x18002e59f  jnz     loc_18002E8CC
0x18002e5a5  lea     rcx, [rbp+280h+FindFileData.cFileName]
0x18002e5a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e5ad  inc     rax
0x18002e5b0  cmp     [rcx+rax*2], r15w
0x18002e5b5  jnz     short loc_18002E5AD
0x18002e5b7  cmp     rax, 24h ; '$'
0x18002e5bb  jnz     loc_18002E8CC
0x18002e5c1  cmp     [rbp+280h+FindFileData.cFileName+10h], 2Dh ; '-'
0x18002e5c6  jnz     loc_18002E8CC
0x18002e5cc  cmp     [rbp+280h+FindFileData.cFileName+1Ah], 2Dh ; '-'
0x18002e5d1  jnz     loc_18002E8CC
0x18002e5d7  cmp     [rbp+280h+FindFileData.cFileName+24h], 2Dh ; '-'
0x18002e5dc  jnz     loc_18002E8CC
0x18002e5e2  cmp     [rbp+280h+FindFileData.cFileName+2Eh], 2Dh ; '-'
0x18002e5e7  jnz     loc_18002E8CC
0x18002e5ed  inc     [rbp+280h+var_2F0]
0x18002e5f0  mov     rcx, r13; void *
0x18002e5f3  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x18002e5f8  mov     ebx, eax
0x18002e5fa  test    eax, eax
0x18002e5fc  jnz     loc_18002E971
0x18002e602  mov     eax, [rbp+280h+arg_30]
0x18002e608  xor     ebx, ebx
0x18002e60a  mov     r15d, ebx
0x18002e60d  sub     eax, 1
0x18002e610  jz      loc_18002E87D
0x18002e616  sub     eax, 1
0x18002e619  jz      loc_18002E79D
0x18002e61f  cmp     eax, 1
0x18002e622  jz      loc_18002E6C3
0x18002e628  mov     r9, [rbp+280h+var_2D0]; void *
0x18002e62c  lea     rax, [rbp+280h+var_2F8]
0x18002e630  mov     edx, [rbp+280h+var_2F4]; unsigned int
0x18002e633  mov     r8, r12; unsigned __int16 *
0x18002e636  mov     [rsp+380h+var_328], rax; unsigned int *
0x18002e63b  mov     rcx, r13; void *
0x18002e63e  lea     rax, [rsp+380h+var_320]
0x18002e643  mov     [rsp+380h+var_330], rax; unsigned int *
0x18002e648  lea     rax, [rsp+380h+hMem]
0x18002e64d  mov     [rsp+380h+var_338], rax; unsigned __int8 **
0x18002e652  mov     rax, [rbp+280h+var_2C8]
0x18002e656  mov     [rsp+380h+var_340], rax; struct DP_KEK *
0x18002e65b  mov     rax, [rbp+280h+var_2D8]
0x18002e65f  mov     [rsp+380h+var_348], rax; struct DP_KEK *
0x18002e664  lea     rax, [rbp+280h+FindFileData.cFileName]
0x18002e668  mov     [rsp+380h+var_350], rax; unsigned __int16 *
0x18002e66d  mov     eax, [rsp+380h+var_308]
0x18002e671  mov     dword ptr [rsp+380h+var_358], eax; int
0x18002e675  lea     rax, [rbp+280h+var_300]
0x18002e679  mov     [rsp+380h+var_360], rax; struct _LUID *
0x18002e67e  call    ?GetMasterKey@@YAHPEAXKPEBG0PEAU_LUID@@HQEAGPEAUDP_KEK@@4PEAPEAEPEAK6@Z; GetMasterKey(void *,ulong,ushort const *,void *,_LUID *,int,ushort * const,DP_KEK *,DP_KEK *,uchar * *,ulong *,ulong *)
0x18002e683  test    eax, eax
0x18002e685  jz      loc_18002E8BA
0x18002e68b  mov     rcx, [rsp+380h+hMem]
0x18002e690  test    rcx, rcx
0x18002e693  jz      loc_18002E89D
0x18002e699  mov     eax, [rsp+380h+var_320]
0x18002e69d  test    rax, rax
0x18002e6a0  jz      short loc_18002E6B2
0x18002e6a2  mov     [rcx], bl
0x18002e6a4  inc     rcx
0x18002e6a7  sub     rax, 1
0x18002e6ab  jnz     short loc_18002E6A2
0x18002e6ad  mov     rcx, [rsp+380h+hMem]; hMem
0x18002e6b2  call    cs:__imp_LocalFree
0x18002e6b9  nop     dword ptr [rax+rax+00h]
0x18002e6be  jmp     loc_18002E89D
0x18002e6c3  mov     rcx, [rbp+280h+var_2D8]
0x18002e6c7  test    rcx, rcx
0x18002e6ca  jz      short loc_18002E6D6
0x18002e6cc  lea     rax, [rcx+14h]
0x18002e6d0  add     rcx, 28h ; '('
0x18002e6d4  jmp     short loc_18002E6DC
0x18002e6d6  mov     rax, rbx
0x18002e6d9  mov     rcx, rbx
0x18002e6dc  mov     rbx, [rbp+280h+var_2D0]
0x18002e6e0  mov     rdx, r12; unsigned __int16 *
0x18002e6e3  mov     r9d, [rsp+380h+var_308]; int
0x18002e6e8  mov     r8, rbx; void *
0x18002e6eb  mov     [rsp+380h+var_350], rcx; unsigned __int8 *
0x18002e6f0  mov     rcx, r13; void *
0x18002e6f3  mov     [rsp+380h+var_358], rax; unsigned __int8 *
0x18002e6f8  lea     rax, [rbp+280h+FindFileData.cFileName]
0x18002e6fc  mov     [rsp+380h+var_360], rax; unsigned __int16 *
0x18002e701  call    ?UpdateDomainUserMasterKey@@YAKPEAXPEBG0HQEAGQEAE3@Z; UpdateDomainUserMasterKey(void *,ushort const *,void *,int,ushort * const,uchar * const,uchar * const)
0x18002e706  test    eax, eax
0x18002e708  jz      loc_18002E89D
0x18002e70e  mov     edx, [rbp+280h+var_2F4]; unsigned int
0x18002e711  lea     rax, [rbp+280h+var_2F8]
0x18002e715  mov     [rsp+380h+var_328], rax; unsigned int *
0x18002e71a  mov     r9, rbx; void *
0x18002e71d  lea     rax, [rsp+380h+var_320]
0x18002e722  mov     r8, r12; unsigned __int16 *
0x18002e725  mov     [rsp+380h+var_330], rax; unsigned int *
0x18002e72a  mov     rcx, r13; void *
0x18002e72d  lea     rax, [rsp+380h+hMem]
0x18002e732  mov     [rsp+380h+var_338], rax; unsigned __int8 **
0x18002e737  mov     rax, [rbp+280h+var_2C8]
0x18002e73b  mov     [rsp+380h+var_340], rax; struct DP_KEK *
0x18002e740  mov     rax, [rbp+280h+var_2D8]
0x18002e744  mov     [rsp+380h+var_348], rax; struct DP_KEK *
0x18002e749  lea     rax, [rbp+280h+FindFileData.cFileName]
0x18002e74d  mov     [rsp+380h+var_350], rax; unsigned __int16 *
0x18002e752  mov     eax, [rsp+380h+var_308]
0x18002e756  mov     dword ptr [rsp+380h+var_358], eax; int
0x18002e75a  lea     rax, [rbp+280h+var_300]
0x18002e75e  mov     [rsp+380h+var_360], rax; struct _LUID *
0x18002e763  call    ?GetMasterKey@@YAHPEAXKPEBG0PEAU_LUID@@HQEAGPEAUDP_KEK@@4PEAPEAEPEAK6@Z; GetMasterKey(void *,ulong,ushort const *,void *,_LUID *,int,ushort * const,DP_KEK *,DP_KEK *,uchar * *,ulong *,ulong *)
0x18002e768  xor     ebx, ebx
0x18002e76a  test    eax, eax
0x18002e76c  jz      loc_18002E8BA
0x18002e772  mov     rcx, [rsp+380h+hMem]
0x18002e777  test    rcx, rcx
0x18002e77a  jz      loc_18002E89D
0x18002e780  mov     eax, [rsp+380h+var_320]
0x18002e784  test    rax, rax
0x18002e787  jz      loc_18002E6B2
0x18002e78d  mov     [rcx], bl
0x18002e78f  inc     rcx
0x18002e792  sub     rax, 1
0x18002e796  jnz     short loc_18002E78D
0x18002e798  jmp     loc_18002E6AD
0x18002e79d  cmp     [rbp+280h+var_2E0], ebx
0x18002e7a0  jz      loc_18002E959
0x18002e7a6  lea     rdx, [rbp+280h+Uuid]; Uuid
0x18002e7aa  lea     rcx, [rbp+280h+FindFileData.cFileName]; StringUuid
0x18002e7ae  call    cs:__imp_UuidFromStringW
0x18002e7b5  nop     dword ptr [rax+rax+00h]
0x18002e7ba  mov     ebx, eax
0x18002e7bc  test    eax, eax
0x18002e7be  jnz     loc_18002E94F
0x18002e7c4  mov     r9, [rbp+280h+var_2D0]; void *
0x18002e7c8  lea     rax, [rbp+280h+var_2F8]
0x18002e7cc  mov     edx, [rbp+280h+var_2F4]; unsigned int
0x18002e7cf  mov     r8, r12; unsigned __int16 *
0x18002e7d2  mov     [rsp+380h+var_328], rax; unsigned int *
0x18002e7d7  mov     rcx, r13; void *
0x18002e7da  lea     rax, [rsp+380h+var_320]
0x18002e7df  mov     [rsp+380h+var_330], rax; unsigned int *
  ... truncated ...
```
