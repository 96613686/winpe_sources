# ProcessPolicy_Internal(ulong,void *,unsigned __int64,void *,int)

- ea: `0x180013a44`
- end: `0x180013f97`
- name: `?ProcessPolicy_Internal@@YAKKPEAX_K0H@Z`
- size: `1363`
- prototype: `unsigned int(unsigned int, void *, unsigned __int64, void *, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009ac4`
- `0x180013a00`
- `0x180013a20`

## callees

- `0x180002d80`
- `0x1800084e0`
- `0x180009864`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180013088`
- `0x1800130ec`
- `0x180013a44`
- `0x180014394`
- `0x1800144a8`
- `0x18001467c`
- `0x18002a270`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013ddb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180013ddb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180013e74`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180013e74`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013f01`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f1b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180013d72`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180013d72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013e9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013e9c`

## string_xrefs

- `0x180013d51`: `%systemroot%\system32\cscobj.dll`

## pseudocode

```c
__int64 __fastcall ProcessPolicy_Internal(unsigned int a1, void *a2, unsigned __int64 a3, void *a4, unsigned int a5)
{
  __int64 v9; // rcx
  int v10; // eax
  int Error; // ebx
  WCHAR *v12; // rbp
  void *v13; // rdx
  void **v14; // r9
  HMODULE LibraryW; // r14
  int v16; // eax
  WCHAR *v17; // rdi
  int v18; // esi
  __int64 v19; // rdx
  UstVarLib *v20; // rcx
  __int64 v21; // r8
  unsigned int v22; // eax
  HANDLE Thread; // rax
  void *v24; // rdx
  void *v25; // rcx
  UstVarLib *v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  char LastError; // al
  int v31; // edx
  int v32; // r8d
  LPCWSTR lpLibFileName; // [rsp+90h] [rbp+18h] BYREF

  v9 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 65, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, a5);
      v9 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
      {
        WPP_SF_(*(_QWORD *)(v9 + 16), 66, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(v9 + 16), 67, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, a1);
          v9 = WPP_GLOBAL_Control;
        }
        if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
          {
            WPP_SF_d(*(_QWORD *)(v9 + 16), 68, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, a1 & 1);
            v9 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
          {
            if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
            {
              WPP_SF_d(*(_QWORD *)(v9 + 16), 69, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, (a1 >> 4) & 1);
              v9 = WPP_GLOBAL_Control;
            }
            if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
            {
              if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
              {
                WPP_SF_d(*(_QWORD *)(v9 + 16), 70, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, (a1 >> 5) & 1);
                v9 = WPP_GLOBAL_Control;
              }
              if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
              {
                if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                {
                  WPP_SF_d(*(_QWORD *)(v9 + 16), 71, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, (a1 >> 6) & 1);
                  v9 = WPP_GLOBAL_Control;
                }
                if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
                {
                  if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                  {
                    WPP_SF_d(*(_QWORD *)(v9 + 16), 72, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, (a1 >> 7) & 1);
                    v9 = WPP_GLOBAL_Control;
                  }
                  if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
                  {
                    if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                    {
                      WPP_SF_d(*(_QWORD *)(v9 + 16), 73, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, (a1 >> 8) & 1);
                      v9 = WPP_GLOBAL_Control;
                    }
                    if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
                    {
                      if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                      {
                        WPP_SF_d(
                          *(_QWORD *)(v9 + 16),
                          74,
                          WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
                          (a1 >> 9) & 1);
                        v9 = WPP_GLOBAL_Control;
                      }
                      if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
                      {
                        if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                        {
                          WPP_SF_d(
                            *(_QWORD *)(v9 + 16),
                            75,
                            WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
                            (a1 >> 10) & 1);
                          v9 = WPP_GLOBAL_Control;
                        }
                        if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
                        {
                          if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                          {
                            WPP_SF_d(
                              *(_QWORD *)(v9 + 16),
                              76,
                              WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
                              (a1 >> 11) & 1);
                            v9 = WPP_GLOBAL_Control;
                          }
                          if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
                          {
                            if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                            {
                              WPP_SF_d(
                                *(_QWORD *)(v9 + 16),
                                77,
                                WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
                                (a1 >> 12) & 1);
                              v9 = WPP_GLOBAL_Control;
                            }
                            if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
                            {
                              if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                              {
                                WPP_SF_q(*(_QWORD *)(v9 + 16), 78, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, a2);
                                v9 = WPP_GLOBAL_Control;
                              }
                              if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control )
                              {
                                if ( (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                                {
                                  WPP_SF_d(
                                    *(_QWORD *)(v9 + 16),
                                    79,
                                    WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
                                    (unsigned int)a3);
                                  v9 = WPP_GLOBAL_Control;
                                }
                                if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 0x80) != 0 )
                                  WPP_SF_d(
                                    *(_QWORD *)(v9 + 16),
                                    80,
                                    WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
                                    (unsigned int)a4);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  lpLibFileName = 0;
  v10 = CscUtil_ExpandEnvironmentStringsAlloc(
          L"%systemroot%\\system32\\cscobj.dll",
          (unsigned __int16 **)&lpLibFileName);
  Error = v10;
  if ( v10 >= 0 )
  {
    v12 = (WCHAR *)lpLibFileName;
    LibraryW = LoadLibraryW(lpLibFileName);
    if ( !LibraryW )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_Sd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v31, v32, (_DWORD)v12, LastError);
      }
      goto LABEL_75;
    }
    lpLibFileName = 0;
    v16 = UstVarLib::CscUtil_HeapAlloc(0x30u, (__int64)v13, &lpLibFileName, v14);
    Error = v16;
    if ( v16 < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_71;
      v28 = 83;
      v29 = (unsigned int)v16;
    }
    else
    {
      v17 = (WCHAR *)lpLibFileName;
      v18 = a1 & 1;
      if ( v18 )
      {
        *((_QWORD *)lpLibFileName + 4) = 0;
      }
      else
      {
        Error = 0;
        *((_QWORD *)lpLibFileName + 4) = 0;
        if ( !DuplicateTokenEx(a2, 0, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)v17 + 4) )
          Error = UstVarLib::ResultFromLastError(v20);
        if ( Error < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_qD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v19, v21, a2, Error);
          goto LABEL_71;
        }
      }
      v22 = a5;
      *(_QWORD *)v17 = LibraryW;
      *((_QWORD *)v17 + 1) = a3;
      *((_QWORD *)v17 + 2) = a4;
      *((_DWORD *)v17 + 6) = v18;
      *((_DWORD *)v17 + 10) = v22;
      LODWORD(lpLibFileName) = 0;
      Thread = CreateThread(0, 0, CscPolicy_AsyncPolicyThreadProc, v17, 0, (LPDWORD)&lpLibFileName);
      if ( Thread )
      {
        a3 = 0;
        a4 = 0;
        CloseHandle(Thread);
LABEL_75:
        CscUtil_HeapFree(v12, v13);
        goto LABEL_79;
      }
      v25 = (void *)*((_QWORD *)v17 + 4);
      if ( v25 )
        CloseHandle(v25);
      CscUtil_HeapFree(v17, v24);
      Error = UstVarLib::ResultFromLastError(v26);
      v27 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      {
LABEL_71:
        FreeLibrary(LibraryW);
        goto LABEL_75;
      }
      v28 = 81;
      v29 = (unsigned int)Error;
    }
    WPP_SF_d(*(_QWORD *)(v27 + 16), v28, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, v29);
    goto LABEL_71;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      85,
      WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
      (unsigned int)v10);
LABEL_79:
  if ( a3 )
    CscPolicy_ProcessGroupPolicyCompleted(a3, Error);
  if ( a4 )
    CscPolicy_ProcessWMIPolicyCompleted(a4);
  return 0;
}

```

## disassembly

```asm
0x180013a44  push    rbx
0x180013a46  push    rbp
0x180013a47  push    rsi
0x180013a48  push    rdi
0x180013a49  push    r12
0x180013a4b  push    r13
0x180013a4d  push    r14
0x180013a4f  push    r15
0x180013a51  sub     rsp, 38h
0x180013a55  mov     r15, r9
0x180013a58  mov     r12, r8
0x180013a5b  mov     r13, rdx
0x180013a5e  mov     esi, ecx
0x180013a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a67  lea     rdi, WPP_GLOBAL_Control
0x180013a6e  lea     rbp, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180013a75  mov     r14d, 1
0x180013a7b  cmp     rcx, rdi
0x180013a7e  jz      loc_180013D3D
0x180013a84  mov     bl, 80h
0x180013a86  test    [rcx+1Ch], bl
0x180013a89  jz      short loc_180013AAA
0x180013a8b  mov     r9d, [rsp+78h+arg_20]
0x180013a93  lea     edx, [r14+40h]
0x180013a97  mov     rcx, [rcx+10h]
0x180013a9b  mov     r8, rbp
0x180013a9e  call    WPP_SF_d
0x180013aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013aaa  cmp     rcx, rdi
0x180013aad  jz      loc_180013D3D
0x180013ab3  test    [rcx+1Ch], bl
0x180013ab6  jz      short loc_180013AD0
0x180013ab8  mov     rcx, [rcx+10h]
0x180013abc  mov     edx, 42h ; 'B'
0x180013ac1  mov     r8, rbp
0x180013ac4  call    WPP_SF_
0x180013ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ad0  cmp     rcx, rdi
0x180013ad3  jz      loc_180013D3D
0x180013ad9  test    [rcx+1Ch], bl
0x180013adc  jz      short loc_180013AF9
0x180013ade  mov     rcx, [rcx+10h]
0x180013ae2  mov     edx, 43h ; 'C'
0x180013ae7  mov     r9d, esi
0x180013aea  mov     r8, rbp
0x180013aed  call    WPP_SF_d
0x180013af2  mov     rcx, cs:WPP_GLOBAL_Control
0x180013af9  cmp     rcx, rdi
0x180013afc  jz      loc_180013D3D
0x180013b02  test    [rcx+1Ch], bl
0x180013b05  jz      short loc_180013B25
0x180013b07  mov     rcx, [rcx+10h]
0x180013b0b  mov     r9d, esi
0x180013b0e  and     r9d, r14d
0x180013b11  mov     edx, 44h ; 'D'
0x180013b16  mov     r8, rbp
0x180013b19  call    WPP_SF_d
0x180013b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b25  cmp     rcx, rdi
0x180013b28  jz      loc_180013D3D
0x180013b2e  test    [rcx+1Ch], bl
0x180013b31  jz      short loc_180013B55
0x180013b33  mov     rcx, [rcx+10h]
0x180013b37  mov     r9d, esi
0x180013b3a  shr     r9d, 4
0x180013b3e  mov     edx, 45h ; 'E'
0x180013b43  and     r9d, r14d
0x180013b46  mov     r8, rbp
0x180013b49  call    WPP_SF_d
0x180013b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b55  cmp     rcx, rdi
0x180013b58  jz      loc_180013D3D
0x180013b5e  test    [rcx+1Ch], bl
0x180013b61  jz      short loc_180013B85
0x180013b63  mov     rcx, [rcx+10h]
0x180013b67  mov     r9d, esi
0x180013b6a  shr     r9d, 5
0x180013b6e  mov     edx, 46h ; 'F'
0x180013b73  and     r9d, r14d
0x180013b76  mov     r8, rbp
0x180013b79  call    WPP_SF_d
0x180013b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b85  cmp     rcx, rdi
0x180013b88  jz      loc_180013D3D
0x180013b8e  test    [rcx+1Ch], bl
0x180013b91  jz      short loc_180013BB5
0x180013b93  mov     rcx, [rcx+10h]
0x180013b97  mov     r9d, esi
0x180013b9a  shr     r9d, 6
0x180013b9e  mov     edx, 47h ; 'G'
0x180013ba3  and     r9d, r14d
0x180013ba6  mov     r8, rbp
0x180013ba9  call    WPP_SF_d
0x180013bae  mov     rcx, cs:WPP_GLOBAL_Control
0x180013bb5  cmp     rcx, rdi
0x180013bb8  jz      loc_180013D3D
0x180013bbe  test    [rcx+1Ch], bl
0x180013bc1  jz      short loc_180013BE5
0x180013bc3  mov     rcx, [rcx+10h]
0x180013bc7  mov     r9d, esi
0x180013bca  shr     r9d, 7
0x180013bce  mov     edx, 48h ; 'H'
0x180013bd3  and     r9d, r14d
0x180013bd6  mov     r8, rbp
0x180013bd9  call    WPP_SF_d
0x180013bde  mov     rcx, cs:WPP_GLOBAL_Control
0x180013be5  cmp     rcx, rdi
0x180013be8  jz      loc_180013D3D
0x180013bee  test    [rcx+1Ch], bl
0x180013bf1  jz      short loc_180013C15
0x180013bf3  mov     rcx, [rcx+10h]
0x180013bf7  mov     r9d, esi
0x180013bfa  shr     r9d, 8
0x180013bfe  mov     edx, 49h ; 'I'
0x180013c03  and     r9d, r14d
0x180013c06  mov     r8, rbp
0x180013c09  call    WPP_SF_d
0x180013c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c15  cmp     rcx, rdi
0x180013c18  jz      loc_180013D3D
0x180013c1e  test    [rcx+1Ch], bl
0x180013c21  jz      short loc_180013C45
0x180013c23  mov     rcx, [rcx+10h]
0x180013c27  mov     r9d, esi
0x180013c2a  shr     r9d, 9
0x180013c2e  mov     edx, 4Ah ; 'J'
0x180013c33  and     r9d, r14d
0x180013c36  mov     r8, rbp
0x180013c39  call    WPP_SF_d
0x180013c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c45  cmp     rcx, rdi
0x180013c48  jz      loc_180013D3D
0x180013c4e  test    [rcx+1Ch], bl
0x180013c51  jz      short loc_180013C75
0x180013c53  mov     rcx, [rcx+10h]
0x180013c57  mov     r9d, esi
0x180013c5a  shr     r9d, 0Ah
0x180013c5e  mov     edx, 4Bh ; 'K'
0x180013c63  and     r9d, r14d
0x180013c66  mov     r8, rbp
0x180013c69  call    WPP_SF_d
0x180013c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c75  cmp     rcx, rdi
0x180013c78  jz      loc_180013D3D
0x180013c7e  test    [rcx+1Ch], bl
0x180013c81  jz      short loc_180013CA5
0x180013c83  mov     rcx, [rcx+10h]
0x180013c87  mov     r9d, esi
0x180013c8a  shr     r9d, 0Bh
0x180013c8e  mov     edx, 4Ch ; 'L'
0x180013c93  and     r9d, r14d
0x180013c96  mov     r8, rbp
0x180013c99  call    WPP_SF_d
0x180013c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ca5  cmp     rcx, rdi
0x180013ca8  jz      loc_180013D3D
0x180013cae  test    [rcx+1Ch], bl
0x180013cb1  jz      short loc_180013CD5
0x180013cb3  mov     rcx, [rcx+10h]
0x180013cb7  mov     r9d, esi
0x180013cba  shr     r9d, 0Ch
0x180013cbe  mov     edx, 4Dh ; 'M'
0x180013cc3  and     r9d, r14d
0x180013cc6  mov     r8, rbp
0x180013cc9  call    WPP_SF_d
0x180013cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cd5  cmp     rcx, rdi
0x180013cd8  jz      short loc_180013D3D
0x180013cda  test    [rcx+1Ch], bl
0x180013cdd  jz      short loc_180013CFA
0x180013cdf  mov     rcx, [rcx+10h]
0x180013ce3  mov     edx, 4Eh ; 'N'
0x180013ce8  mov     r9, r13
0x180013ceb  mov     r8, rbp
0x180013cee  call    WPP_SF_q
0x180013cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cfa  cmp     rcx, rdi
0x180013cfd  jz      short loc_180013D3D
0x180013cff  test    [rcx+1Ch], bl
0x180013d02  jz      short loc_180013D1F
0x180013d04  mov     rcx, [rcx+10h]
0x180013d08  mov     r9d, r12d
0x180013d0b  mov     edx, 4Fh ; 'O'
0x180013d10  mov     r8, rbp
0x180013d13  call    WPP_SF_d
0x180013d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d1f  cmp     rcx, rdi
0x180013d22  jz      short loc_180013D3D
0x180013d24  test    [rcx+1Ch], bl
0x180013d27  jz      short loc_180013D3D
0x180013d29  mov     rcx, [rcx+10h]
0x180013d2d  mov     r9d, r15d
0x180013d30  mov     edx, 50h ; 'P'
0x180013d35  mov     r8, rbp
0x180013d38  call    WPP_SF_d
0x180013d3d  lea     rdx, [rsp+78h+lpLibFileName]; unsigned __int16 **
0x180013d45  mov     [rsp+78h+lpLibFileName], 0
0x180013d51  lea     rcx, aSystemrootSyst_0; "%systemroot%\\system32\\cscobj.dll"
0x180013d58  call    ?CscUtil_ExpandEnvironmentStringsAlloc@@YAJPEBGPEAPEAG@Z; CscUtil_ExpandEnvironmentStringsAlloc(ushort const *,ushort * *)
0x180013d5d  mov     ebx, eax
0x180013d5f  test    eax, eax
0x180013d61  js      loc_180013F42
0x180013d67  mov     rbp, [rsp+78h+lpLibFileName]
0x180013d6f  mov     rcx, rbp; lpLibFileName
0x180013d72  call    cs:__imp_LoadLibraryW
0x180013d78  mov     r14, rax
0x180013d7b  test    rax, rax
0x180013d7e  jz      loc_180013F09
0x180013d84  lea     r8, [rsp+78h+lpLibFileName]; int
0x180013d8c  mov     [rsp+78h+lpLibFileName], 0
0x180013d98  mov     ecx, 30h ; '0'; dwBytes
0x180013d9d  call    ?CscUtil_HeapAlloc@UstVarLib@@YAJ_KHPEAPEAXPEAX@Z; UstVarLib::CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x180013da2  mov     ebx, eax
0x180013da4  test    eax, eax
0x180013da6  js      loc_180013ED4
0x180013dac  mov     rdi, [rsp+78h+lpLibFileName]
0x180013db4  and     esi, 1
0x180013db7  jnz     short loc_180013E26
0x180013db9  lea     rax, [rdi+20h]
0x180013dbd  xor     ebx, ebx
0x180013dbf  mov     [rsp+78h+phNewToken], rax; phNewToken
0x180013dc4  xor     r8d, r8d; lpTokenAttributes
0x180013dc7  xor     edx, edx; dwDesiredAccess
0x180013dc9  mov     [rax], rbx
0x180013dcc  mov     rcx, r13; hExistingToken
0x180013dcf  mov     [rsp+78h+TokenType], 2; TokenType
0x180013dd7  lea     r9d, [rbx+2]; ImpersonationLevel
0x180013ddb  call    cs:__imp_DuplicateTokenEx
0x180013de1  test    eax, eax
0x180013de3  jnz     short loc_180013DEC
0x180013de5  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x180013dea  mov     ebx, eax
0x180013dec  test    ebx, ebx
0x180013dee  jns     short loc_180013E2E
0x180013df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180013df7  lea     rax, WPP_GLOBAL_Control
0x180013dfe  cmp     rcx, rax
0x180013e01  jz      loc_180013EFE
0x180013e07  test    byte ptr [rcx+1Ch], 2
0x180013e0b  jz      loc_180013EFE
0x180013e11  mov     rcx, [rcx+10h]
0x180013e15  mov     r9, r13
0x180013e18  mov     [rsp+78h+TokenType], ebx
0x180013e1c  call    WPP_SF_qD
0x180013e21  jmp     loc_180013EFE
0x180013e26  mov     qword ptr [rdi+20h], 0
0x180013e2e  mov     eax, [rsp+78h+arg_20]
0x180013e35  lea     r8, ?CscPolicy_AsyncPolicyThreadProc@@YAKPEAX@Z; lpStartAddress
0x180013e3c  mov     [rdi], r14
0x180013e3f  mov     r9, rdi; lpParameter
0x180013e42  mov     [rdi+8], r12
0x180013e46  xor     edx, edx; dwStackSize
0x180013e48  mov     [rdi+10h], r15
0x180013e4c  xor     ecx, ecx; lpThreadAttributes
0x180013e4e  mov     [rdi+18h], esi
0x180013e51  mov     [rdi+28h], eax
0x180013e54  lea     rax, [rsp+78h+lpLibFileName]
0x180013e5c  mov     [rsp+78h+phNewToken], rax; lpThreadId
0x180013e61  mov     [rsp+78h+TokenType], 0; dwCreationFlags
0x180013e69  mov     dword ptr [rsp+78h+lpLibFileName], 0
0x180013e74  call    cs:__imp_CreateThread
0x180013e7a  test    rax, rax
0x180013e7d  jz      short loc_180013E93
0x180013e7f  xor     r12d, r12d
0x180013e82  xor     r15d, r15d
0x180013e85  mov     rcx, rax; hObject
0x180013e88  call    cs:__imp_CloseHandle
0x180013e8e  jmp     loc_180013F38
0x180013e93  mov     rcx, [rdi+20h]; hObject
0x180013e97  test    rcx, rcx
0x180013e9a  jz      short loc_180013EA2
0x180013e9c  call    cs:__imp_CloseHandle
0x180013ea2  mov     rcx, rdi; lpMem
0x180013ea5  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180013eaa  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x180013eaf  mov     ebx, eax
0x180013eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013eb8  lea     rax, WPP_GLOBAL_Control
0x180013ebf  cmp     rcx, rax
0x180013ec2  jz      short loc_180013EFE
0x180013ec4  test    byte ptr [rcx+1Ch], 2
0x180013ec8  jz      short loc_180013EFE
0x180013eca  mov     edx, 51h ; 'Q'
0x180013ecf  mov     r9d, ebx
0x180013ed2  jmp     short loc_180013EEE
0x180013ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180013edb  cmp     rcx, rdi
0x180013ede  jz      short loc_180013EFE
0x180013ee0  test    byte ptr [rcx+1Ch], 2
0x180013ee4  jz      short loc_180013EFE
0x180013ee6  mov     edx, 53h ; 'S'
0x180013eeb  mov     r9d, eax
0x180013eee  mov     rcx, [rcx+10h]
0x180013ef2  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180013ef9  call    WPP_SF_d
0x180013efe  mov     rcx, r14; hLibModule
0x180013f01  call    cs:__imp_FreeLibrary
0x180013f07  jmp     short loc_180013F38
0x180013f09  mov     rax, cs:WPP_GLOBAL_Control
0x180013f10  cmp     rax, rdi
  ... truncated ...
```
