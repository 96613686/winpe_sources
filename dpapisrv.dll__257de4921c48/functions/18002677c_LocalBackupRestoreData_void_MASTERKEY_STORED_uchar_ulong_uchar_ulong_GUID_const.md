# LocalBackupRestoreData(void *,MASTERKEY_STORED *,uchar *,ulong,uchar * *,ulong *,_GUID const *)

- ea: `0x18002677c`
- end: `0x180026db5`
- name: `?LocalBackupRestoreData@@YAKPEAXPEAUMASTERKEY_STORED@@PEAEKPEAPEAEPEAKPEBU_GUID@@@Z`
- size: `1593`
- prototype: `__int64 __fastcall(_QWORD *, struct MASTERKEY_STORED *, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *, struct _GUID *)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180019f40`
- `0x180024f38`
- `0x1800261e8`

## callees

- `0x180002f18`
- `0x180004d80`
- `0x180007f10`
- `0x18000c010`
- `0x18000dcb0`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x180025a2c`
- `0x18002629c`
- `0x180026434`
- `0x18002677c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180026833`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ca3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026cc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ca3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026cc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800268f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026a53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800268f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026a53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002688a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002688a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ce3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ce3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d3e`

## string_xrefs

- `0x180026855`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x1800268c8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180026934`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180026a2b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180026a8c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180026bc6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
__int64 __fastcall LocalBackupRestoreData(
        _QWORD *a1,
        struct MASTERKEY_STORED *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        struct _GUID *a7)
{
  int v8; // ebx
  void *v9; // rdi
  void *v10; // r14
  HANDLE CurrentThread; // rax
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rsi
  DWORD v14; // eax
  unsigned __int16 *v15; // rax
  DWORD v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const unsigned __int16 *v20; // r8
  void *v21; // rcx
  DWORD v22; // eax
  HLOCAL v23; // rax
  DWORD v24; // eax
  const unsigned __int16 *v25; // rdi
  char v26; // cl
  __int64 v27; // rax
  __int64 v28; // rax
  const unsigned __int16 *v29; // r8
  struct _LUID *v30; // rcx
  const unsigned __int16 *v31; // r8
  unsigned int i; // ebx
  __int64 v33; // rdx
  unsigned int v34; // edx
  struct MASTERKEY_STORED *v35; // rdx
  __int64 v36; // rcx
  unsigned int v38; // [rsp+50h] [rbp-B0h] BYREF
  int v39; // [rsp+54h] [rbp-ACh]
  unsigned __int16 *v40; // [rsp+58h] [rbp-A8h]
  struct _LUID v41; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h]
  void *v43; // [rsp+70h] [rbp-90h] BYREF
  void *v44; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v45; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  struct MASTERKEY_STORED *v47; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v48; // [rsp+90h] [rbp-70h]
  HANDLE hObject; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v50; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID *v51; // [rsp+A8h] [rbp-58h]
  unsigned __int8 **v52; // [rsp+B0h] [rbp-50h]
  unsigned int *v53; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v54; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v55[40]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v56[256]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v57[256]; // [rsp+320h] [rbp+220h] BYREF

  v52 = a5;
  v53 = a6;
  v54 = a3;
  v47 = a2;
  v51 = a7;
  v45 = a4;
  memset_0(v56, 0, sizeof(v56));
  v8 = 0;
  v41 = 0;
  v9 = 0;
  v43 = 0;
  v10 = 0;
  v44 = 0;
  hObject = 0;
  v50 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids);
  CurrentThread = GetCurrentThread();
  if ( (unsigned int)GetThreadAuthenticationId(CurrentThread, &v41) )
  {
    v13 = 0;
    v40 = 0;
    hMem = 0;
    v48 = 0;
    v39 = 0;
    TickCount = GetTickCount();
    while ( 1 )
    {
      v38 = 256;
      v14 = CPSGetDomainControllerName(v56, &v38, v8, 1);
      v12 = v14;
      if ( v14 )
      {
        DebugTraceError(v14, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 365);
        if ( v38 <= 0x100 )
          goto LABEL_12;
        v15 = (unsigned __int16 *)LocalAlloc(0, 2LL * v38);
        v40 = v15;
        v13 = v15;
        if ( !v15 )
          goto LABEL_12;
        v16 = CPSGetDomainControllerName(v15, &v38, v39, 1);
        v12 = v16;
        if ( v16 )
        {
          DebugTraceError(v16, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 382);
          goto LABEL_12;
        }
      }
      else
      {
        v13 = v56;
      }
      v38 = 256;
      v22 = CPSGetDomainControllerName(v57, &v38, 0, 0);
      v12 = v22;
      if ( !v22 )
      {
        v25 = v57;
        goto LABEL_36;
      }
      DebugTraceError(v22, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 404);
      if ( v38 <= 0x100 )
        goto LABEL_33;
      v23 = LocalAlloc(0, 2LL * v38);
      hMem = v23;
      if ( v23 )
      {
        v24 = CPSGetDomainControllerName((unsigned __int16 *)v23, &v38, 0, 0);
        v12 = v24;
        if ( v24 )
        {
          DebugTraceError(v24, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 421);
LABEL_33:
          v13 = v40;
          goto LABEL_12;
        }
        v25 = (const unsigned __int16 *)hMem;
LABEL_36:
        v48 = v13;
        v12 = CreateDcNameMutexes(&v41, v13, v25, &v43, &v44);
        if ( v12 )
          goto LABEL_61;
        v26 = 0;
        if ( v13 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v13[v27] );
          if ( (int)v27 > 2 && *v13 == 92 && v13[1] == 92 )
          {
            v13 += 2;
            v26 = 1;
          }
        }
        if ( !v25 )
          goto LABEL_50;
        v28 = -1;
        do
          ++v28;
        while ( v25[v28] );
        if ( (int)v28 <= 2 || *v25 != 92 || (v29 = v25 + 2, v25[1] != 92) )
LABEL_50:
          v29 = 0;
        v12 = CreateDcNameMutexes(
                &v41,
                (const unsigned __int16 *)((unsigned __int64)v13 & -(__int64)(v26 != 0)),
                v29,
                &hObject,
                &v50);
        if ( v12 )
          goto LABEL_61;
        if ( a1 && a1[76] && *((_DWORD *)a1 + 154) )
        {
          for ( i = 0; i < *((_DWORD *)a1 + 154); ++i )
          {
            v33 = a1[76];
            v38 = 0;
            if ( !(unsigned int)LsaIfIsDcTargetForRecovery(
                                  &v41,
                                  *(const unsigned __int16 **)(v33 + 8LL * i),
                                  (int *)&v38)
              && v38 )
            {
              v12 = 1131;
              goto LABEL_61;
            }
          }
        }
        v12 = BackupKey(v30, v13, v31, v51, v54, v45, v52, v53);
        if ( v12 )
LABEL_61:
          DebugTraceError(v12, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 512);
        v9 = v43;
        v10 = v44;
        goto LABEL_33;
      }
      v13 = v40;
LABEL_12:
      v17 = *(_QWORD *)&v51->Data1 - 0x499B2FC747270C64LL;
      if ( *(_QWORD *)&v51->Data1 == 0x499B2FC747270C64LL )
        v17 = *(_QWORD *)v51->Data4 + 0x65763132C8F1A454LL;
      if ( !v17 )
        goto LABEL_67;
      v18 = *(_QWORD *)&v51->Data1 - 0x11D1178E7FE94D50LL;
      if ( *(_QWORD *)&v51->Data1 == 0x11D1178E7FE94D50LL )
        v18 = *(_QWORD *)v51->Data4 - 0x40DB145F80008FABLL;
      if ( !v18 )
      {
LABEL_67:
        v35 = v47;
        v55[0] = 0;
        v36 = *((_QWORD *)v47 + 19);
        if ( v36 && *((_DWORD *)v47 + 36) > 0x1Cu )
        {
          MyGuidToStringW(v36 + 12, v55);
          v35 = v47;
        }
        v20 = (const unsigned __int16 *)((char *)v35 + 16);
        if ( a1 )
          v21 = (void *)a1[3];
        else
          v21 = 0;
        v34 = 597;
        goto LABEL_74;
      }
      v19 = *(_QWORD *)&v51->Data1 - 0x11D1178E7F752B10LL;
      if ( *(_QWORD *)&v51->Data1 == 0x11D1178E7F752B10LL )
        v19 = *(_QWORD *)v51->Data4 - 0x40DB145F80008FABLL;
      if ( !v19 )
      {
        v55[0] = 0;
        if ( !v12 && *v52 && *v53 > 0x1C )
          MyGuidToStringW(*v52 + 12, v55);
        v20 = (const unsigned __int16 *)((char *)v47 + 16);
        if ( a1 )
          v21 = (void *)a1[3];
        else
          v21 = 0;
        v34 = 596;
LABEL_74:
        CPSAudit(v21, v34, v20, v48, 0, v55, v12);
      }
      if ( v13 )
      {
        LocalFree(v13);
        v13 = 0;
        v40 = 0;
      }
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      if ( v9 )
      {
        CloseHandle(v9);
        v9 = 0;
        v43 = 0;
      }
      if ( v10 )
      {
        CloseHandle(v10);
        v10 = 0;
        v44 = 0;
      }
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      if ( v50 )
      {
        CloseHandle(v50);
        v50 = 0;
      }
      if ( !v12 || v12 == 5 || v12 == 1131 )
        return v12;
      if ( v39 )
      {
        dword_18004CCE8 = TickCount;
        qword_18004CCF0 = (__int64)v41;
        return v12;
      }
      v8 = 1;
      v39 = 1;
    }
  }
  v12 = 1008;
  DebugTraceError(1008, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 316);
  return v12;
}

```

## disassembly

```asm
0x18002677c  mov     [rsp-8+arg_18], rbx
0x180026781  push    rbp
0x180026782  push    rsi
0x180026783  push    rdi
0x180026784  push    r14
0x180026786  push    r15
0x180026788  lea     rbp, [rsp-430h]
0x180026790  sub     rsp, 530h
0x180026797  mov     rax, cs:__security_cookie
0x18002679e  xor     rax, rsp
0x1800267a1  mov     [rbp+450h+var_30], rax
0x1800267a8  mov     rax, [rbp+450h+arg_20]
0x1800267af  mov     r15, rcx
0x1800267b2  mov     [rbp+450h+var_4A0], rax
0x1800267b6  lea     rcx, [rbp+450h+var_430]; void *
0x1800267ba  mov     rax, [rbp+450h+arg_28]
0x1800267c1  mov     [rbp+450h+var_498], rax
0x1800267c5  mov     rax, [rbp+450h+arg_30]
0x1800267cc  mov     [rbp+450h+var_490], r8
0x1800267d0  mov     r8d, 200h; Size
0x1800267d6  mov     [rbp+450h+var_4C8], rdx
0x1800267da  xor     edx, edx; Val
0x1800267dc  mov     [rbp+450h+var_4A8], rax
0x1800267e0  mov     [rbp+450h+var_4D0], r9d
0x1800267e4  call    memset_0
0x1800267e9  xor     ebx, ebx
0x1800267eb  mov     qword ptr [rsp+550h+var_4F0.LowPart], rbx
0x1800267f0  mov     edi, ebx
0x1800267f2  mov     [rsp+550h+var_4E0], rbx
0x1800267f7  mov     r14d, ebx
0x1800267fa  mov     [rsp+550h+var_4D8], rbx
0x1800267ff  mov     [rbp+450h+hObject], rbx
0x180026803  mov     [rbp+450h+var_4B0], rbx
0x180026807  mov     rcx, cs:WPP_GLOBAL_Control
0x18002680e  lea     rax, WPP_GLOBAL_Control
0x180026815  cmp     rcx, rax
0x180026818  jz      short loc_180026833
0x18002681a  test    byte ptr [rcx+1Ch], 4
0x18002681e  jz      short loc_180026833
0x180026820  mov     rcx, [rcx+10h]
0x180026824  lea     edx, [rbx+0Ah]
0x180026827  lea     r8, WPP_f4b69f1db01237bb0e3a2b08d8c2cb9e_Traceguids
0x18002682e  call    WPP_SF_
0x180026833  call    cs:__imp_GetCurrentThread
0x18002683a  nop     dword ptr [rax+rax+00h]
0x18002683f  mov     rcx, rax
0x180026842  lea     rdx, [rsp+550h+var_4F0]
0x180026847  call    GetThreadAuthenticationId
0x18002684c  test    eax, eax
0x18002684e  jnz     short loc_180026875
0x180026850  mov     ebx, 3F0h
0x180026855  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002685c  mov     ecx, ebx
0x18002685e  lea     rdx, aDwlasterror; "dwLastError"
0x180026865  mov     r9d, 13Ch
0x18002686b  call    DebugTraceError
0x180026870  jmp     loc_180026D8C
0x180026875  mov     rsi, rbx
0x180026878  mov     [rsp+550h+var_4F8], rbx
0x18002687d  mov     [rsp+550h+hMem], rbx
0x180026882  mov     [rbp+450h+var_4C0], rbx
0x180026886  mov     [rsp+550h+var_4FC], ebx
0x18002688a  call    cs:__imp_GetTickCount
0x180026891  nop     dword ptr [rax+rax+00h]
0x180026896  mov     [rbp+450h+var_4CC], eax
0x180026899  mov     r9d, 1; int
0x18002689f  mov     [rsp+550h+var_500], 100h
0x1800268a7  mov     r8d, ebx; int
0x1800268aa  lea     rdx, [rsp+550h+var_500]; unsigned int *
0x1800268af  lea     rcx, [rbp+450h+var_430]; unsigned __int16 *
0x1800268b3  call    ?CPSGetDomainControllerName@@YAKPEAGPEAKHH@Z; CPSGetDomainControllerName(ushort *,ulong *,int,int)
0x1800268b8  mov     ebx, eax
0x1800268ba  test    eax, eax
0x1800268bc  jz      loc_1800269F8
0x1800268c2  mov     r9d, 16Dh
0x1800268c8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800268cf  lea     rdx, aDwlasterror; "dwLastError"
0x1800268d6  mov     ecx, eax
0x1800268d8  call    DebugTraceError
0x1800268dd  cmp     [rsp+550h+var_500], 100h
0x1800268e5  jbe     short loc_180026949
0x1800268e7  mov     edx, [rsp+550h+var_500]
0x1800268eb  xor     ecx, ecx; uFlags
0x1800268ed  add     rdx, rdx; uBytes
0x1800268f0  call    cs:__imp_LocalAlloc
0x1800268f7  nop     dword ptr [rax+rax+00h]
0x1800268fc  xor     r9d, r9d
0x1800268ff  mov     [rsp+550h+var_4F8], rax
0x180026904  mov     rsi, rax
0x180026907  test    rax, rax
0x18002690a  jz      short loc_18002694C
0x18002690c  mov     r8d, [rsp+550h+var_4FC]; int
0x180026911  lea     rdx, [rsp+550h+var_500]; unsigned int *
0x180026916  mov     r9d, 1; int
0x18002691c  mov     rcx, rax; unsigned __int16 *
0x18002691f  call    ?CPSGetDomainControllerName@@YAKPEAGPEAKHH@Z; CPSGetDomainControllerName(ushort *,ulong *,int,int)
0x180026924  mov     ebx, eax
0x180026926  test    eax, eax
0x180026928  jz      loc_1800269FC
0x18002692e  mov     r9d, 17Eh
0x180026934  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002693b  lea     rdx, aDwlasterror; "dwLastError"
0x180026942  mov     ecx, eax
0x180026944  call    DebugTraceError
0x180026949  xor     r9d, r9d
0x18002694c  mov     rcx, [rbp+450h+var_4A8]
0x180026950  mov     rax, [rcx]
0x180026953  sub     rax, qword ptr cs:stru_180042B68.Data1
0x18002695a  jnz     short loc_180026967
0x18002695c  mov     rax, [rcx+8]
0x180026960  sub     rax, qword ptr cs:stru_180042B68.Data4
0x180026967  test    rax, rax
0x18002696a  jz      loc_180026C34
0x180026970  mov     rax, [rcx]
0x180026973  sub     rax, cs:qword_180042B88
0x18002697a  jnz     short loc_180026987
0x18002697c  mov     rax, [rcx+8]
0x180026980  sub     rax, cs:qword_180042B90
0x180026987  test    rax, rax
0x18002698a  jz      loc_180026C34
0x180026990  mov     rax, [rcx]
0x180026993  sub     rax, cs:qword_180042B78
0x18002699a  jnz     short loc_1800269A7
0x18002699c  mov     rax, [rcx+8]
0x1800269a0  sub     rax, cs:qword_180042B80
0x1800269a7  test    rax, rax
0x1800269aa  jnz     loc_180026C9B
0x1800269b0  mov     [rbp+450h+var_480], r9w
0x1800269b5  test    ebx, ebx
0x1800269b7  jnz     short loc_1800269DE
0x1800269b9  mov     rax, [rbp+450h+var_4A0]
0x1800269bd  mov     rcx, [rax]
0x1800269c0  test    rcx, rcx
0x1800269c3  jz      short loc_1800269DE
0x1800269c5  mov     rax, [rbp+450h+var_498]
0x1800269c9  cmp     dword ptr [rax], 1Ch
0x1800269cc  jbe     short loc_1800269DE
0x1800269ce  add     rcx, 0Ch
0x1800269d2  lea     rdx, [rbp+450h+var_480]
0x1800269d6  call    MyGuidToStringW
0x1800269db  xor     r9d, r9d
0x1800269de  mov     r8, [rbp+450h+var_4C8]
0x1800269e2  add     r8, 10h
0x1800269e6  test    r15, r15
0x1800269e9  jz      loc_180026C2A
0x1800269ef  mov     rcx, [r15+18h]
0x1800269f3  jmp     loc_180026C2D
0x1800269f8  lea     rsi, [rbp+450h+var_430]
0x1800269fc  xor     r9d, r9d; int
0x1800269ff  mov     [rsp+550h+var_500], 100h
0x180026a07  xor     r8d, r8d; int
0x180026a0a  lea     rdx, [rsp+550h+var_500]; unsigned int *
0x180026a0f  lea     rcx, [rbp+450h+var_230]; unsigned __int16 *
0x180026a16  call    ?CPSGetDomainControllerName@@YAKPEAGPEAKHH@Z; CPSGetDomainControllerName(ushort *,ulong *,int,int)
0x180026a1b  mov     ebx, eax
0x180026a1d  test    eax, eax
0x180026a1f  jz      loc_180026AB2
0x180026a25  mov     r9d, 194h
0x180026a2b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026a32  lea     rdx, aDwlasterror; "dwLastError"
0x180026a39  mov     ecx, eax
0x180026a3b  call    DebugTraceError
0x180026a40  cmp     [rsp+550h+var_500], 100h
0x180026a48  jbe     short loc_180026AA1
0x180026a4a  mov     edx, [rsp+550h+var_500]
0x180026a4e  xor     ecx, ecx; uFlags
0x180026a50  add     rdx, rdx; uBytes
0x180026a53  call    cs:__imp_LocalAlloc
0x180026a5a  nop     dword ptr [rax+rax+00h]
0x180026a5f  xor     r9d, r9d; int
0x180026a62  mov     [rsp+550h+hMem], rax
0x180026a67  test    rax, rax
0x180026a6a  jz      loc_180026C20
0x180026a70  xor     r8d, r8d; int
0x180026a73  lea     rdx, [rsp+550h+var_500]; unsigned int *
0x180026a78  mov     rcx, rax; unsigned __int16 *
0x180026a7b  call    ?CPSGetDomainControllerName@@YAKPEAGPEAKHH@Z; CPSGetDomainControllerName(ushort *,ulong *,int,int)
0x180026a80  mov     ebx, eax
0x180026a82  test    eax, eax
0x180026a84  jz      short loc_180026AAB
0x180026a86  mov     r9d, 1A5h
0x180026a8c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026a93  lea     rdx, aDwlasterror; "dwLastError"
0x180026a9a  mov     ecx, eax
0x180026a9c  call    DebugTraceError
0x180026aa1  mov     rsi, [rsp+550h+var_4F8]
0x180026aa6  jmp     loc_180026949
0x180026aab  mov     rdi, [rsp+550h+hMem]
0x180026ab0  jmp     short loc_180026AB9
0x180026ab2  lea     rdi, [rbp+450h+var_230]
0x180026ab9  lea     rax, [rsp+550h+var_4D8]
0x180026abe  mov     [rbp+450h+var_4C0], rsi
0x180026ac2  lea     r9, [rsp+550h+var_4E0]; void **
0x180026ac7  mov     [rsp+550h+var_530], rax; void **
0x180026acc  mov     r8, rdi; unsigned __int16 *
0x180026acf  lea     rcx, [rsp+550h+var_4F0]; struct _LUID *
0x180026ad4  mov     rdx, rsi; unsigned __int16 *
0x180026ad7  call    ?CreateDcNameMutexes@@YAKPEAU_LUID@@PEBG1PEAPEAX2@Z; CreateDcNameMutexes(_LUID *,ushort const *,ushort const *,void * *,void * *)
0x180026adc  xor     r14d, r14d
0x180026adf  mov     ebx, eax
0x180026ae1  test    eax, eax
0x180026ae3  jnz     loc_180026BC0
0x180026ae9  mov     cl, r14b
0x180026aec  test    rsi, rsi
0x180026aef  jz      short loc_180026B17
0x180026af1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026af5  inc     rax
0x180026af8  cmp     [rsi+rax*2], r14w
0x180026afd  jnz     short loc_180026AF5
0x180026aff  cmp     eax, 2
0x180026b02  jle     short loc_180026B17
0x180026b04  cmp     word ptr [rsi], 5Ch ; '\'
0x180026b08  jnz     short loc_180026B17
0x180026b0a  cmp     word ptr [rsi+2], 5Ch ; '\'
0x180026b0f  jnz     short loc_180026B17
0x180026b11  add     rsi, 4
0x180026b15  mov     cl, 1
0x180026b17  test    rdi, rdi
0x180026b1a  jz      short loc_180026B40
0x180026b1c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026b20  inc     rax
0x180026b23  cmp     [rdi+rax*2], r14w
0x180026b28  jnz     short loc_180026B20
0x180026b2a  cmp     eax, 2
0x180026b2d  jle     short loc_180026B40
0x180026b2f  cmp     word ptr [rdi], 5Ch ; '\'
0x180026b33  jnz     short loc_180026B40
0x180026b35  cmp     word ptr [rdi+2], 5Ch ; '\'
0x180026b3a  lea     r8, [rdi+4]
0x180026b3e  jz      short loc_180026B43
0x180026b40  mov     r8, r14; unsigned __int16 *
0x180026b43  neg     cl
0x180026b45  lea     rax, [rbp+450h+var_4B0]
0x180026b49  lea     r9, [rbp+450h+hObject]; void **
0x180026b4d  mov     [rsp+550h+var_530], rax; void **
0x180026b52  sbb     rdx, rdx
0x180026b55  lea     rcx, [rsp+550h+var_4F0]; struct _LUID *
0x180026b5a  and     rdx, rsi; unsigned __int16 *
0x180026b5d  call    ?CreateDcNameMutexes@@YAKPEAU_LUID@@PEBG1PEAPEAX2@Z; CreateDcNameMutexes(_LUID *,ushort const *,ushort const *,void * *,void * *)
0x180026b62  mov     ebx, eax
0x180026b64  test    eax, eax
0x180026b66  jnz     short loc_180026BC0
0x180026b68  test    r15, r15
0x180026b6b  jz      short loc_180026BDD
0x180026b6d  cmp     [r15+260h], r14
0x180026b74  jz      short loc_180026BDD
0x180026b76  cmp     [r15+268h], r14d
0x180026b7d  jz      short loc_180026BDD
0x180026b7f  mov     ebx, r14d
0x180026b82  cmp     ebx, [r15+268h]
0x180026b89  jnb     short loc_180026BDD
0x180026b8b  mov     rdx, [r15+260h]
0x180026b92  lea     r8, [rsp+550h+var_500]; int *
0x180026b97  mov     eax, ebx
0x180026b99  lea     rcx, [rsp+550h+var_4F0]; struct _LUID *
0x180026b9e  mov     [rsp+550h+var_500], r14d
0x180026ba3  mov     rdx, [rdx+rax*8]; unsigned __int16 *
0x180026ba7  call    ?LsaIfIsDcTargetForRecovery@@YAJPEAU_LUID@@PEBGPEAH@Z; LsaIfIsDcTargetForRecovery(_LUID *,ushort const *,int *)
0x180026bac  test    eax, eax
0x180026bae  jnz     short loc_180026BB7
0x180026bb0  cmp     [rsp+550h+var_500], r14d
0x180026bb5  jnz     short loc_180026BBB
0x180026bb7  inc     ebx
0x180026bb9  jmp     short loc_180026B82
0x180026bbb  mov     ebx, 46Bh
0x180026bc0  mov     r9d, 200h
0x180026bc6  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026bcd  lea     rdx, aDwlasterror; "dwLastError"
0x180026bd4  mov     ecx, ebx
0x180026bd6  call    DebugTraceError
0x180026bdb  jmp     short loc_180026C11
0x180026bdd  mov     rax, [rbp+450h+var_498]
0x180026be1  mov     rdx, rsi; unsigned __int16 *
0x180026be4  mov     r9, [rbp+450h+var_4A8]; struct _GUID *
0x180026be8  mov     [rsp+550h+var_518], rax; unsigned int *
0x180026bed  mov     rax, [rbp+450h+var_4A0]
0x180026bf1  mov     [rsp+550h+var_520], rax; unsigned __int8 **
0x180026bf6  mov     eax, [rbp+450h+var_4D0]
0x180026bf9  mov     dword ptr [rsp+550h+var_528], eax; unsigned int
0x180026bfd  mov     rax, [rbp+450h+var_490]
0x180026c01  mov     [rsp+550h+var_530], rax; unsigned __int8 *
0x180026c06  call    ?BackupKey@@YAKPEAU_LUID@@PEBG1PEBU_GUID@@PEAEKPEAPEAEPEAKK@Z; BackupKey(_LUID *,ushort const *,ushort const *,_GUID const *,uchar *,ulong,uchar * *,ulong *,ulong)
0x180026c0b  mov     ebx, eax
0x180026c0d  test    eax, eax
0x180026c0f  jnz     short loc_180026BC0
0x180026c11  mov     rdi, [rsp+550h+var_4E0]
0x180026c16  mov     r14, [rsp+550h+var_4D8]
0x180026c1b  jmp     loc_180026AA1
0x180026c20  mov     rsi, [rsp+550h+var_4F8]
0x180026c25  jmp     loc_18002694C
0x180026c2a  mov     rcx, r9
0x180026c2d  mov     edx, 254h
0x180026c32  jmp     short loc_180026C7D
0x180026c34  mov     rdx, [rbp+450h+var_4C8]
0x180026c38  mov     [rbp+450h+var_480], r9w
0x180026c3d  mov     rcx, [rdx+98h]
0x180026c44  test    rcx, rcx
0x180026c47  jz      short loc_180026C66
0x180026c49  cmp     dword ptr [rdx+90h], 1Ch
0x180026c50  jbe     short loc_180026C66
  ... truncated ...
```
