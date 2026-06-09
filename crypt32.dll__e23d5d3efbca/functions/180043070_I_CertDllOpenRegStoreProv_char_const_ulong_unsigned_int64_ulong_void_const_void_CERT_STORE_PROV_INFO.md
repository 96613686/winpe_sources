# I_CertDllOpenRegStoreProv(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)

- ea: `0x180043070`
- end: `0x180043704`
- name: `?I_CertDllOpenRegStoreProv@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z`
- size: `1684`
- prototype: `__int64 __fastcall(const char *, unsigned int, unsigned __int64, unsigned int, HKEY, void *, struct _CERT_STORE_PROV_INFO *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b450`

## callees

- `0x180028d60`
- `0x180030e60`
- `0x180031b18`
- `0x180043070`
- `0x1800449d4`
- `0x180044a60`
- `0x180044eb4`
- `0x180045014`
- `0x18005a7cc`
- `0x18005dc68`
- `0x18005de50`
- `0x18005ed18`
- `0x18008a464`
- `0x1800b70a8`
- `0x1800b8b18`
- `0x1800c7a84`
- `0x1800df8a8`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800433e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004352b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004356b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800433e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004352b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004356b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004314f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043223`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043565`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004314f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043223`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043565`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180043213`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180043213`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800435f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800435f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800435b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800435b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800431d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800431fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004333b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800431d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800431fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004333b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800430b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043138`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800430b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043138`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043209`

## pseudocode

```c
__int64 __fastcall I_CertDllOpenRegStoreProv(
        const char *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        HKEY a5,
        void *a6,
        struct _CERT_STORE_PROV_INFO *a7)
{
  int v7; // esi
  void **v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  void **v11; // rdi
  _BYTE *v12; // r12
  unsigned int v13; // ebp
  __int64 v14; // rcx
  __int64 v15; // rax
  SIZE_T v16; // r14
  HLOCAL v17; // rax
  DWORD LastError; // ebx
  int v19; // ebx
  int v20; // eax
  HKEY v21; // rcx
  HKEY v22; // rcx
  void *v23; // rcx
  HKEY v25; // rax
  HKEY v26; // rbx
  unsigned int v27; // r12d
  unsigned int *v28; // r8
  int v29; // r13d
  HKEY v30; // r14
  __int64 i; // r15
  HKEY v32; // rcx
  HKEY v33; // rax
  DWORD v34; // ebx
  void (__fastcall **v35)(struct _REG_STORE *, unsigned int); // rcx
  DWORD v36; // edx
  __int64 v37; // rcx
  __int64 v38; // rax
  SIZE_T v39; // rbx
  void *v40; // rax
  const unsigned __int16 *v41; // rcx
  const unsigned __int16 **v42; // rbx
  const unsigned __int16 *v43; // rdx
  HKEY v44; // rcx
  HKEY v45; // rax
  HKEY v46; // rbx
  HKEY v47; // rax
  unsigned int v48; // ebx
  void *v49; // r14
  HKEY v50; // rax
  HKEY v51; // rax
  unsigned int *v52; // [rsp+30h] [rbp-48h]
  _QWORD v53[3]; // [rsp+38h] [rbp-40h] BYREF
  HKEY v54; // [rsp+A0h] [rbp+28h]

  v7 = a4;
  if ( (a4 & 0x7EE0002C) != 0 )
  {
    SetLastError(0x80070057);
    LastError = GetLastError();
    goto LABEL_29;
  }
  if ( (a4 & 0x800) != 0 )
  {
    IPR_EnableSecurityPrivilege(17);
    IPR_EnableSecurityPrivilege(18);
  }
  if ( (v7 & 0x10) == 0 )
  {
    v8 = (void **)LocalAlloc(0x40u, 0x80u);
    v11 = v8;
    if ( !v8 )
    {
      SetLastError(0x8007000E);
      LastError = GetLastError();
      goto LABEL_29;
    }
    if ( !(unsigned int)Pki_InitializeCriticalSection(v8 + 1, v9, v10) )
    {
      PkiDefaultCryptFree(v11);
      LastError = GetLastError();
      goto LABEL_29;
    }
    v12 = v11 + 11;
    *v11 = a6;
    v13 = 1;
    *((_DWORD *)v11 + 22) = 1;
    *((_DWORD *)v11 + 18) = v7;
    if ( v7 < 0 )
    {
      v14 = *((_QWORD *)a5 + 1);
      if ( v14 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)(v14 + 2 * v15) );
      }
      else
      {
        LODWORD(v15) = 0;
      }
      v16 = (unsigned int)(2 * v15 + 2);
      v17 = LocalAlloc(0, v16);
      if ( !v17 )
      {
        SetLastError(0x8007000E);
        v11[13] = 0;
        LastError = GetLastError();
LABEL_18:
        FreeRegistryStoreChange((struct _REG_STORE *)v11);
        v20 = *((_DWORD *)v11 + 18);
        if ( v20 >= 0 )
        {
          if ( (v20 & 0x40000) != 0 )
          {
            PkiDefaultCryptFree(v11[12]);
          }
          else if ( (v20 & 0x20000) != 0 && *((_DWORD *)v11 + 21) )
          {
            CommitAllToSerializedRegistry((struct _REG_STORE *)v11, 0);
          }
        }
        else
        {
          FreeGptStoreChangeInfo((struct _GPT_STORE_CHANGE_INFO **)v11 + 15);
          GptStoreSignalAndFreeRegStoreResyncEntries((struct _REG_STORE *)v11);
          PkiDefaultCryptFree(v11[13]);
          v21 = (HKEY)v11[12];
          if ( v21 && v21 != HKEY_LOCAL_MACHINE )
            RegCloseKey(v21);
        }
        v22 = (HKEY)v11[8];
        if ( v22 )
          RegCloseKey(v22);
        v23 = v11[6];
        if ( v23 )
          CloseHandle(v23);
        DeleteCriticalSection((LPCRITICAL_SECTION)(v11 + 1));
        PkiDefaultCryptFree(v11);
        goto LABEL_29;
      }
      v11[13] = v17;
      memcpy_0(v17, *((const void **)a5 + 1), v16);
      if ( *(_QWORD *)a5 == -2147483646 )
      {
        v11[12] = (void *)-2147483646LL;
        goto LABEL_78;
      }
      v51 = OpenSubKeyEx(*(HKEY *)a5, 0, v7 & 0xFFFF9FFF | 0x4000, 0);
      v11[12] = v51;
      if ( v51 )
      {
LABEL_78:
        v48 = *((_DWORD *)v11 + 18);
        if ( (v48 & 0x100000) != 0 )
        {
          v19 = 1;
          goto LABEL_15;
        }
        v49 = *v11;
        EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 1));
        v50 = OpenSubKeyEx((HKEY)v11[12], (const unsigned __int16 *)v11[13], v48, 0);
        v11[8] = v50;
        if ( v50 )
        {
          OpenAllFromRegistryEx((struct _REG_STORE *)v11, v49, v48);
        }
        else if ( GetLastError() != 2 || (v48 & 0x4000) != 0 )
        {
          v19 = 0;
          goto LABEL_82;
        }
        v19 = 1;
LABEL_82:
        ILS_CloseRegistryKey((HKEY)v11[8]);
        v11[8] = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 1));
        goto LABEL_15;
      }
LABEL_56:
      LastError = GetLastError();
      goto LABEL_18;
    }
    if ( (v7 & 0x40000) != 0 )
    {
      v37 = *((_QWORD *)a5 + 1);
      if ( v37 )
      {
        v38 = -1;
        do
          ++v38;
        while ( *(_WORD *)(v37 + 2 * v38) );
      }
      else
      {
        LODWORD(v38) = 0;
      }
      v39 = (unsigned int)(2 * v38 + 2);
      v40 = (void *)PkiNonzeroAlloc(v39);
      v11[12] = v40;
      if ( v40 )
      {
        memcpy_0(v40, *((const void **)a5 + 1), v39);
        v7 = v7 & 0xFFFF9FFF | 0x4000;
        *((_DWORD *)v11 + 18) = v7;
        if ( !*(_QWORD *)a5 || (v47 = OpenSubKeyEx(*(HKEY *)a5, 0, v7, 0), (v11[8] = v47) != 0) )
        {
          v19 = OpenAllFromRegistryEx((struct _REG_STORE *)v11, *v11, *((_DWORD *)v11 + 18));
LABEL_16:
          if ( v19 )
          {
            if ( (v7 & 0x100000) != 0 )
            {
              a7->dwStoreProvFlags |= 1u;
              v35 = &off_180122D00;
              v36 = 15;
            }
            else
            {
              v35 = &off_180122C50;
              v36 = 14;
            }
            a7->cStoreProvFunc = v36;
            a7->rgpvStoreProvFunc = (void **)v35;
            a7->hStoreProv = v11;
            if ( (*v12 & 2) != 0 )
              a7->dwStoreProvFlags |= 4u;
            *(_DWORD *)v12 &= ~1u;
            return v13;
          }
          LastError = GetLastError();
          if ( v11 )
            goto LABEL_18;
LABEL_29:
          SetLastError(LastError);
          return 0;
        }
      }
      goto LABEL_56;
    }
    v25 = OpenSubKeyEx(a5, 0, v7 & 0xFFFF9FFF | 0x4000, 0);
    v11[8] = v25;
    if ( !v25 )
      goto LABEL_56;
    v26 = (HKEY)*v11;
    v27 = *((_DWORD *)v11 + 18);
    v54 = (HKEY)*v11;
    if ( (v7 & 0x20000) != 0 )
    {
      v19 = OpenAllFromSerializedRegistryEx((struct _REG_STORE *)v11, v26, v27);
      goto LABEL_15;
    }
    v28 = (unsigned int *)(v11 + 11);
    v29 = v27 & 0x40000;
    if ( (v27 & 0x40000) != 0 )
      v28 = 0;
    v52 = v28;
    if ( (v27 & 0x100000) != 0 )
    {
LABEL_14:
      v19 = 1;
LABEL_15:
      *((_DWORD *)v11 + 18) &= 0xFFFF9FFF;
      v12 = v11 + 11;
      goto LABEL_16;
    }
    v30 = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= 3 )
      {
        if ( v29 )
        {
          v44 = (HKEY)v11[8];
          if ( v44 )
          {
            if ( (v27 & 0x8000) == 0 )
            {
              v45 = OpenSubKeyEx(v44, L"Keys", v27, 0);
              v46 = v45;
              if ( v45 )
              {
                MoveFromRegistryToRoamingFiles(v45, (const unsigned __int16 *)v11[12], L"Keys", v27);
                ILS_CloseRegistryKey(v46);
              }
            }
          }
        }
        goto LABEL_14;
      }
      v32 = (HKEY)v11[8];
      if ( v32 )
      {
        v33 = OpenSubKeyEx(v32, (&off_1801234F0)[i], v27, v28);
        v30 = v33;
        if ( v33 )
        {
          OpenFromRegistry(v26, v33, v27);
        }
        else if ( GetLastError() != 2 )
        {
          goto LABEL_64;
        }
      }
      if ( v29 )
      {
        v41 = (const unsigned __int16 *)v11[12];
        v53[1] = v26;
        v42 = (const unsigned __int16 **)&(&off_1801234F0)[i];
        v43 = *v42;
        v53[0] = 1;
        if ( !(unsigned int)ILS_OpenAllElementsFromDirectory(
                              v41,
                              v43,
                              v27,
                              v53,
                              (int (*)(const unsigned __int16 *const, const unsigned __int8 *, unsigned int, void *))ReadContextCallback,
                              0)
          && GetLastError() - 2 > 1 )
        {
LABEL_64:
          ILS_CloseRegistryKey(v30);
          v19 = 0;
          goto LABEL_15;
        }
        if ( !v30 )
          goto LABEL_45;
        if ( (v27 & 0x8000) == 0 )
          MoveFromRegistryToRoamingFiles(v30, (const unsigned __int16 *)v11[12], *v42, v27);
      }
      else if ( !v30 )
      {
        goto LABEL_46;
      }
      v34 = GetLastError();
      RegCloseKey(v30);
      SetLastError(v34);
      v30 = 0;
LABEL_45:
      v26 = v54;
LABEL_46:
      v28 = v52;
    }
  }
  if ( !(unsigned int)DeleteAllFromRegistry(a5, v7) )
    return 0;
  a7->dwStoreProvFlags |= 2u;
  return 1;
}

```

## disassembly

```asm
0x180043070  mov     [rsp+arg_8], rbx
0x180043075  mov     [rsp+arg_10], rbp
0x18004307a  push    rsi
0x18004307b  push    rdi
0x18004307c  push    r12
0x18004307e  push    r14
0x180043080  push    r15
0x180043082  sub     rsp, 50h
0x180043086  mov     esi, r9d
0x180043089  test    r9d, 7EE0002Ch
0x180043090  jnz     loc_18004369E
0x180043096  bt      r9d, 0Bh
0x18004309b  jb      loc_1800436B6
0x1800430a1  test    sil, 10h
0x1800430a5  jnz     loc_180043652
0x1800430ab  mov     edx, 80h; uBytes
0x1800430b0  mov     ecx, 40h ; '@'; uFlags
0x1800430b5  call    cs:__imp_LocalAlloc
0x1800430bb  mov     rdi, rax
0x1800430be  test    rax, rax
0x1800430c1  jz      loc_180043560
0x1800430c7  lea     rcx, [rax+8]
0x1800430cb  call    Pki_InitializeCriticalSection
0x1800430d0  test    eax, eax
0x1800430d2  jz      loc_1800436CF
0x1800430d8  mov     rax, [rsp+78h+arg_28]
0x1800430e0  lea     r12, [rdi+58h]
0x1800430e4  mov     [rdi], rax
0x1800430e7  mov     ebp, 1
0x1800430ec  mov     [r12], ebp
0x1800430f0  mov     [rdi+48h], esi
0x1800430f3  test    esi, esi
0x1800430f5  jns     loc_180043246
0x1800430fb  mov     r12, [rsp+78h+arg_20]
0x180043103  mov     rcx, [r12+8]
0x180043108  test    rcx, rcx
0x18004310b  jz      loc_180043682
0x180043111  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180043118  nop     dword ptr [rax+rax+00000000h]
0x180043120  inc     rax
0x180043123  cmp     word ptr [rcx+rax*2], 0
0x180043128  jnz     short loc_180043120
0x18004312a  lea     eax, ds:2[rax*2]
0x180043131  xor     ecx, ecx; uFlags
0x180043133  mov     edx, eax; uBytes
0x180043135  mov     r14d, eax
0x180043138  call    cs:__imp_LocalAlloc
0x18004313e  mov     rbx, rax
0x180043141  test    rax, rax
0x180043144  jnz     loc_180043578
0x18004314a  mov     ecx, 8007000Eh; dwErrCode
0x18004314f  call    cs:__imp_SetLastError
0x180043155  mov     [rdi+68h], rbx
0x180043159  call    cs:__imp_GetLastError
0x18004315f  mov     ebx, eax
0x180043161  jmp     short loc_18004319A
0x180043163  test    r13d, r13d
0x180043166  jnz     loc_1800434D2
0x18004316c  mov     ebx, ebp
0x18004316e  mov     r13, [rsp+78h+arg_0]
0x180043176  and     dword ptr [rdi+48h], 0FFFF9FFFh
0x18004317d  lea     r12, [rdi+58h]
0x180043181  test    ebx, ebx
0x180043183  jnz     loc_180043361
0x180043189  call    cs:__imp_GetLastError
0x18004318f  mov     ebx, eax
0x180043191  test    rdi, rdi
0x180043194  jz      loc_180043221
0x18004319a  mov     rcx, rdi; struct _REG_STORE *
0x18004319d  call    ?FreeRegistryStoreChange@@YAXPEAU_REG_STORE@@@Z; FreeRegistryStoreChange(_REG_STORE *)
0x1800431a2  mov     eax, [rdi+48h]
0x1800431a5  test    eax, eax
0x1800431a7  jns     short loc_1800431DD
0x1800431a9  lea     rcx, [rdi+78h]; struct _GPT_STORE_CHANGE_INFO **
0x1800431ad  call    ?FreeGptStoreChangeInfo@@YAXPEAPEAU_GPT_STORE_CHANGE_INFO@@@Z; FreeGptStoreChangeInfo(_GPT_STORE_CHANGE_INFO * *)
0x1800431b2  mov     rcx, rdi; struct _REG_STORE *
0x1800431b5  call    ?GptStoreSignalAndFreeRegStoreResyncEntries@@YAXPEAU_REG_STORE@@@Z; GptStoreSignalAndFreeRegStoreResyncEntries(_REG_STORE *)
0x1800431ba  mov     rcx, [rdi+68h]; hMem
0x1800431be  call    PkiDefaultCryptFree
0x1800431c3  mov     rcx, [rdi+60h]; hKey
0x1800431c7  test    rcx, rcx
0x1800431ca  jz      short loc_1800431F1
0x1800431cc  cmp     rcx, 0FFFFFFFF80000002h
0x1800431d3  jz      short loc_1800431F1
0x1800431d5  call    cs:__imp_RegCloseKey
0x1800431db  jmp     short loc_1800431F1
0x1800431dd  bt      eax, 12h
0x1800431e1  jb      loc_180043408
0x1800431e7  bt      eax, 11h
0x1800431eb  jb      loc_1800436EB
0x1800431f1  mov     rcx, [rdi+40h]; hKey
0x1800431f5  test    rcx, rcx
0x1800431f8  jz      short loc_180043200
0x1800431fa  call    cs:__imp_RegCloseKey
0x180043200  mov     rcx, [rdi+30h]; hObject
0x180043204  test    rcx, rcx
0x180043207  jz      short loc_18004320F
0x180043209  call    cs:__imp_CloseHandle
0x18004320f  lea     rcx, [rdi+8]; lpCriticalSection
0x180043213  call    cs:__imp_DeleteCriticalSection
0x180043219  mov     rcx, rdi; hMem
0x18004321c  call    PkiDefaultCryptFree
0x180043221  mov     ecx, ebx; dwErrCode
0x180043223  call    cs:__imp_SetLastError
0x180043229  xor     ebp, ebp
0x18004322b  mov     eax, ebp
0x18004322d  lea     r11, [rsp+78h+var_28]
0x180043232  mov     rbx, [r11+38h]
0x180043236  mov     rbp, [r11+40h]
0x18004323a  mov     rsp, r11
0x18004323d  pop     r15
0x18004323f  pop     r14
0x180043241  pop     r12
0x180043243  pop     rdi
0x180043244  pop     rsi
0x180043245  retn
0x180043246  bt      esi, 12h
0x18004324a  jb      loc_18004339F
0x180043250  mov     rcx, [rsp+78h+arg_20]; HKEY
0x180043258  mov     r8d, esi
0x18004325b  btr     r8d, 0Dh
0x180043260  xor     r9d, r9d; unsigned int *
0x180043263  bts     r8d, 0Eh; unsigned int
0x180043268  xor     edx, edx; unsigned __int16 *
0x18004326a  call    ?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z; OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)
0x18004326f  mov     [rdi+40h], rax
0x180043273  test    rax, rax
0x180043276  jz      loc_180043627
0x18004327c  mov     rbx, [rdi]
0x18004327f  mov     r12d, [rdi+48h]
0x180043283  mov     [rsp+78h+arg_20], rbx
0x18004328b  bt      esi, 11h
0x18004328f  jb      loc_180043689
0x180043295  mov     [rsp+78h+arg_0], r13
0x18004329d  lea     r8, [rdi+58h]
0x1800432a1  mov     r13d, r12d
0x1800432a4  mov     eax, 0
0x1800432a9  and     r13d, 40000h
0x1800432b0  cmovnz  r8, rax
0x1800432b4  mov     [rsp+78h+var_48], r8
0x1800432b9  bt      r12d, 14h
0x1800432be  jb      loc_18004316C
0x1800432c4  xor     r14d, r14d
0x1800432c7  xor     r15d, r15d
0x1800432ca  lea     rdx, ?ReadContextCallback@@YAHQEBGPEBEKPEAX@Z; ReadContextCallback(ushort const * const,uchar const *,ulong,void *)
0x1800432d1  lea     r10, off_1801234F0; "Certificates"
0x1800432d8  cmp     r15d, 3
0x1800432dc  jnb     loc_180043163
0x1800432e2  mov     rcx, [rdi+40h]; HKEY
0x1800432e6  test    rcx, rcx
0x1800432e9  jz      short loc_180043322
0x1800432eb  mov     rdx, [r10+r15*8]; unsigned __int16 *
0x1800432ef  mov     r9, r8; unsigned int *
0x1800432f2  mov     r8d, r12d; unsigned int
0x1800432f5  call    ?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z; OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)
0x1800432fa  mov     r14, rax
0x1800432fd  test    rax, rax
0x180043300  jz      loc_180043478
0x180043306  mov     r8d, r12d; unsigned int
0x180043309  mov     rdx, rax; HKEY
0x18004330c  mov     rcx, rbx; void *
0x18004330f  call    ?OpenFromRegistry@@YAHPEAXPEAUHKEY__@@K@Z; OpenFromRegistry(void *,HKEY__ *,ulong)
0x180043314  lea     rdx, ?ReadContextCallback@@YAHQEBGPEBEKPEAX@Z; ReadContextCallback(ushort const * const,uchar const *,ulong,void *)
0x18004331b  lea     r10, off_1801234F0; "Certificates"
0x180043322  test    r13d, r13d
0x180043325  jnz     loc_180043416
0x18004332b  test    r14, r14
0x18004332e  jz      short loc_180043354
0x180043330  call    cs:__imp_GetLastError
0x180043336  mov     rcx, r14; hKey
0x180043339  mov     ebx, eax
0x18004333b  call    cs:__imp_RegCloseKey
0x180043341  mov     ecx, ebx; dwErrCode
0x180043343  call    cs:__imp_SetLastError
0x180043349  xor     r14d, r14d
0x18004334c  mov     rbx, [rsp+78h+arg_20]
0x180043354  mov     r8, [rsp+78h+var_48]
0x180043359  inc     r15d
0x18004335c  jmp     loc_1800432CA
0x180043361  mov     rax, [rsp+78h+arg_30]
0x180043369  bt      esi, 14h
0x18004336d  jb      loc_1800433F4
0x180043373  lea     rcx, off_180122C50
0x18004337a  mov     edx, 0Eh
0x18004337f  mov     [rax+4], edx
0x180043382  mov     [rax+8], rcx
0x180043386  mov     [rax+10h], rdi
0x18004338a  test    byte ptr [r12], 2
0x18004338f  jz      short loc_180043395
0x180043391  or      dword ptr [rax+18h], 4
0x180043395  and     dword ptr [r12], 0FFFFFFFEh
0x18004339a  jmp     loc_18004322B
0x18004339f  mov     r14, [rsp+78h+arg_20]
0x1800433a7  mov     rcx, [r14+8]
0x1800433ab  test    rcx, rcx
0x1800433ae  jz      loc_1800436E4
0x1800433b4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800433bb  nop     dword ptr [rax+rax+00h]
0x1800433c0  inc     rax
0x1800433c3  cmp     word ptr [rcx+rax*2], 0
0x1800433c8  jnz     short loc_1800433C0
0x1800433ca  lea     eax, ds:2[rax*2]
0x1800433d1  mov     ecx, eax; uBytes
0x1800433d3  mov     ebx, eax
0x1800433d5  call    PkiNonzeroAlloc
0x1800433da  mov     [rdi+60h], rax
0x1800433de  test    rax, rax
0x1800433e1  jnz     loc_180043496
0x1800433e7  call    cs:__imp_GetLastError
0x1800433ed  mov     ebx, eax
0x1800433ef  jmp     loc_18004319A
0x1800433f4  or      [rax+18h], ebp
0x1800433f7  lea     rcx, off_180122D00
0x1800433fe  mov     edx, 0Fh
0x180043403  jmp     loc_18004337F
0x180043408  mov     rcx, [rdi+60h]; hMem
0x18004340c  call    PkiDefaultCryptFree
0x180043411  jmp     loc_1800431F1
0x180043416  mov     rcx, [rdi+60h]; unsigned __int16 *
0x18004341a  lea     r9, [rsp+78h+var_40]; void *
0x18004341f  mov     [rsp+78h+var_38], rbx
0x180043424  mov     r8d, r12d; unsigned int
0x180043427  lea     rbx, [r10+r15*8]
0x18004342b  mov     [rsp+78h+var_50], 0; int
0x180043433  mov     [rsp+78h+var_58], rdx; int (*)(const unsigned __int16 *const, const unsigned __int8 *, unsigned int, void *)
0x180043438  mov     rdx, [rbx]; unsigned __int16 *
0x18004343b  mov     [rsp+78h+var_40], rbp
0x180043440  call    ?ILS_OpenAllElementsFromDirectory@@YAHPEBG0KPEAXP6AHQEBGPEBEK1@ZH@Z; ILS_OpenAllElementsFromDirectory(ushort const *,ushort const *,ulong,void *,int (*)(ushort const * const,uchar const *,ulong,void *),int)
0x180043445  test    eax, eax
0x180043447  jz      loc_18004352B
0x18004344d  test    r14, r14
0x180043450  jz      loc_18004334C
0x180043456  bt      r12d, 0Fh
0x18004345b  jb      loc_180043330
0x180043461  mov     r8, [rbx]; unsigned __int16 *
0x180043464  mov     r9d, r12d; unsigned int
0x180043467  mov     rdx, [rdi+60h]; unsigned __int16 *
0x18004346b  mov     rcx, r14; HKEY
0x18004346e  call    ?MoveFromRegistryToRoamingFiles@@YAHPEAUHKEY__@@PEBG1K@Z; MoveFromRegistryToRoamingFiles(HKEY__ *,ushort const *,ushort const *,ulong)
0x180043473  jmp     loc_180043330
0x180043478  call    cs:__imp_GetLastError
0x18004347e  cmp     eax, 2
0x180043481  jz      loc_180043314
0x180043487  mov     rcx, r14; hKey
0x18004348a  call    ?ILS_CloseRegistryKey@@YAXPEAUHKEY__@@@Z; ILS_CloseRegistryKey(HKEY__ *)
0x18004348f  xor     ebx, ebx
0x180043491  jmp     loc_18004316E
0x180043496  mov     rdx, [r14+8]; Src
0x18004349a  mov     r8, rbx; Size
0x18004349d  mov     rcx, rax; void *
0x1800434a0  call    memcpy_0
0x1800434a5  btr     esi, 0Dh
0x1800434a9  bts     esi, 0Eh
0x1800434ad  mov     [rdi+48h], esi
0x1800434b0  mov     rcx, [r14]; HKEY
0x1800434b3  test    rcx, rcx
0x1800434b6  jnz     loc_180043541
0x1800434bc  mov     r8d, [rdi+48h]; unsigned int
0x1800434c0  mov     rcx, rdi; struct _REG_STORE *
0x1800434c3  mov     rdx, [rdi]; void *
0x1800434c6  call    ?OpenAllFromRegistryEx@@YAHPEAU_REG_STORE@@PEAXK@Z; OpenAllFromRegistryEx(_REG_STORE *,void *,ulong)
0x1800434cb  mov     ebx, eax
0x1800434cd  jmp     loc_180043181
0x1800434d2  mov     rcx, [rdi+40h]; HKEY
0x1800434d6  test    rcx, rcx
0x1800434d9  jz      loc_18004316C
0x1800434df  bt      r12d, 0Fh
0x1800434e4  jb      loc_18004316C
0x1800434ea  xor     r9d, r9d; unsigned int *
0x1800434ed  lea     rdx, aKeys; "Keys"
0x1800434f4  mov     r8d, r12d; unsigned int
0x1800434f7  call    ?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z; OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)
0x1800434fc  mov     rbx, rax
0x1800434ff  test    rax, rax
0x180043502  jz      loc_18004316C
0x180043508  mov     rdx, [rdi+60h]; unsigned __int16 *
0x18004350c  lea     r8, aKeys; "Keys"
0x180043513  mov     r9d, r12d; unsigned int
0x180043516  mov     rcx, rax; HKEY
0x180043519  call    ?MoveFromRegistryToRoamingFiles@@YAHPEAUHKEY__@@PEBG1K@Z; MoveFromRegistryToRoamingFiles(HKEY__ *,ushort const *,ushort const *,ulong)
0x18004351e  mov     rcx, rbx; hKey
0x180043521  call    ?ILS_CloseRegistryKey@@YAXPEAUHKEY__@@@Z; ILS_CloseRegistryKey(HKEY__ *)
0x180043526  jmp     loc_18004316C
0x18004352b  call    cs:__imp_GetLastError
0x180043531  add     eax, 0FFFFFFFEh
0x180043534  cmp     eax, ebp
0x180043536  ja      loc_180043487
0x18004353c  jmp     loc_18004344D
0x180043541  xor     r9d, r9d; unsigned int *
0x180043544  mov     r8d, esi; unsigned int
0x180043547  xor     edx, edx; unsigned __int16 *
0x180043549  call    ?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z; OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)
0x18004354e  mov     [rdi+40h], rax
0x180043552  test    rax, rax
0x180043555  jz      loc_180043627
0x18004355b  jmp     loc_1800434BC
0x180043560  mov     ecx, 8007000Eh; dwErrCode
0x180043565  call    cs:__imp_SetLastError
0x18004356b  call    cs:__imp_GetLastError
0x180043571  mov     ebx, eax
  ... truncated ...
```
