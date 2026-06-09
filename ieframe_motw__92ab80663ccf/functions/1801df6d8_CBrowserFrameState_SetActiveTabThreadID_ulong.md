# CBrowserFrameState::SetActiveTabThreadID(ulong)

- ea: `0x1801df6d8`
- end: `0x1801dfd7f`
- name: `?SetActiveTabThreadID@CBrowserFrameState@@QEAAJK@Z`
- size: `1703`
- prototype: `__int64 __fastcall(CBrowserFrameState *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800a4ce8`

## callees

- `0x180009610`
- `0x1800a73ac`
- `0x1801dcc9c`
- `0x1801dd1f0`
- `0x1801df6d8`
- `0x1801e0f1c`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1801df923`
- `KERNEL32!SetEvent` at `0x1801dfabf`
- `KERNEL32!SetEvent` at `0x1801df923`
- `KERNEL32!SetEvent` at `0x1801dfabf`
- `KERNEL32!CreateEventW` at `0x1801df90c`
- `KERNEL32!CreateEventW` at `0x1801df90c`
- `KERNEL32!CloseHandle` at `0x1801df954`
- `KERNEL32!CloseHandle` at `0x1801df954`
- `KERNEL32!GetLastError` at `0x1801df933`
- `KERNEL32!GetLastError` at `0x1801df933`
- `KERNEL32!GetCurrentThreadId` at `0x1801df728`
- `KERNEL32!GetCurrentThreadId` at `0x1801df795`
- `KERNEL32!GetCurrentThreadId` at `0x1801df728`
- `KERNEL32!GetCurrentThreadId` at `0x1801df795`
- `KERNEL32!LeaveCriticalSection` at `0x1801dfb94`
- `KERNEL32!LeaveCriticalSection` at `0x1801dfcdc`
- `KERNEL32!LeaveCriticalSection` at `0x1801dfb94`
- `KERNEL32!LeaveCriticalSection` at `0x1801dfcdc`
- `KERNEL32!EnterCriticalSection` at `0x1801dfa54`
- `KERNEL32!EnterCriticalSection` at `0x1801dfcb9`
- `KERNEL32!EnterCriticalSection` at `0x1801dfa54`
- `KERNEL32!EnterCriticalSection` at `0x1801dfcb9`
- `USER32!IsWindowVisible` at `0x1801df9d5`
- `USER32!IsWindowVisible` at `0x1801dfb21`
- `USER32!IsWindowVisible` at `0x1801df9d5`
- `USER32!IsWindowVisible` at `0x1801dfb21`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801dfb77`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801dfd6e`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801dfb77`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801dfd6e`
- `iertutil!__imp_DSA_Destroy` at `0x1801dfceb`
- `iertutil!__imp_DSA_Destroy` at `0x1801dfceb`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfa86`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfbc1`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfc6e`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfd24`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfd4d`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfa86`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfbc1`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfc6e`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfd24`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801dfd4d`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801df7d2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801df7d2`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1801df8f3`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1801df8f3`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801df7a9`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801dfa3c`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801dfca4`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801df7a9`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801dfa3c`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801dfca4`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801df7fd`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801dfc15`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801df7fd`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801dfc15`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801df758`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801df758`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801df8c1`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801df8c1`

## pseudocode

```c
__int64 __fastcall CBrowserFrameState::SetActiveTabThreadID(CBrowserFrameState *this, int a2)
{
  struct _DSA *v2; // rbx
  unsigned int v5; // edx
  signed int TrustSplitComponent; // r14d
  bool v7; // zf
  struct _IsoUntrustedComponent *v8; // rcx
  int v9; // edi
  unsigned int v10; // ecx
  __int64 v11; // r15
  char *v12; // rdi
  unsigned int v13; // edx
  struct IsoScope *DefaultScope; // rax
  unsigned int *v15; // rax
  HANDLE EventW; // rax
  void *v17; // r13
  signed int LastError; // eax
  int v19; // eax
  HWND *v20; // rdx
  int v21; // eax
  int *v22; // r15
  int v23; // r15d
  HANDLE *ItemPtr; // rax
  HANDLE *v25; // rdi
  HWND *v26; // rdx
  int i; // r15d
  int v28; // eax
  HWND *v29; // rdi
  CBrowserFrameState *v30; // rcx
  unsigned int v31; // ecx
  __int64 j; // rdi
  _DWORD *v33; // r13
  int k; // r15d
  int v35; // eax
  _DWORD *v36; // rax
  int *v37; // rdi
  int v38; // edi
  _QWORD *v40; // r12
  int m; // r15d
  int v42; // ecx
  _DWORD *v43; // rax
  __int64 v44; // [rsp+20h] [rbp-E0h]
  unsigned int v45; // [rsp+30h] [rbp-D0h] BYREF
  struct _DSA *v46; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v47; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v48; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD *v49; // [rsp+48h] [rbp-B8h] BYREF
  struct _IsoUntrustedComponent *v50; // [rsp+50h] [rbp-B0h] BYREF
  HWND v51; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v52; // [rsp+60h] [rbp-A0h]
  HWND v53; // [rsp+68h] [rbp-98h] BYREF
  __int64 v54; // [rsp+70h] [rbp-90h]
  struct _IsoComponent *v55; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v56[28]; // [rsp+80h] [rbp-80h] BYREF
  char v57[100]; // [rsp+9Ch] [rbp-64h] BYREF
  WCHAR Name[128]; // [rsp+100h] [rbp+0h] BYREF

  *((_DWORD *)this + 12) = a2;
  v2 = 0;
  v55 = 0;
  v46 = 0;
  v50 = 0;
  v47 = 0;
  if ( *((_DWORD *)this + 10) == GetCurrentThreadId() )
    v5 = 0;
  else
    v5 = 2;
  TrustSplitComponent = IsoGetTrustSplitComponent(*((_DWORD *)this + 5), v5, &v55, &v47, &v50);
  if ( TrustSplitComponent >= 0 )
  {
    v7 = dword_1806A733C == 0;
    v8 = v50;
    *((_DWORD *)v50 + 17) = *((_DWORD *)this + 12);
    if ( !v7 && !*((_DWORD *)this + 6) && *((_DWORD *)v8 + 25) )
      *((_DWORD *)this + 6) = *((_DWORD *)v8 + 25);
    v9 = *((_DWORD *)this + 10);
    if ( v9 != GetCurrentThreadId() )
      IsoUnlockArtifact(v47);
  }
  if ( !dword_1806A733C )
  {
    EnterCriticalSection(&g_csDll);
    v22 = (int *)*((_QWORD *)this + 9);
    if ( !v22 || a2 == -1 )
    {
LABEL_69:
      LeaveCriticalSection(&g_csDll);
      goto LABEL_70;
    }
    v23 = *v22;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( --v23 < 0 )
          goto LABEL_69;
        ItemPtr = (HANDLE *)DSA_GetItemPtr(*((HDSA *)this + 9), v23);
        v45 = 0;
        v25 = ItemPtr;
        if ( (int)CBrowserFrameState::FindRootTabThreadID(this, *((_DWORD *)ItemPtr + 7), &v45) < 0 || a2 != v45 )
          break;
        if ( ((_BYTE)v25[3] & 2) != 0 )
        {
          SetEvent(v25[2]);
          goto LABEL_67;
        }
        if ( ((_BYTE)v25[3] & 4) != 0 && *((_DWORD *)v25 + 8) )
        {
          if ( v2 )
          {
LABEL_59:
            v26 = &v53;
            v53 = (HWND)*v25;
            v54 = 1;
LABEL_66:
            if ( (int)CDSA_Base<CAddonEntry>::AppendItem(&v46, v26) < 0 )
LABEL_67:
              DSA_DeleteItem(*((HDSA *)this + 9), v23);
          }
          else
          {
            if ( (unsigned int)CDSA_Base<SET_VISIBLITY_DATA>::Create(&v46) )
            {
              v2 = v46;
              goto LABEL_59;
            }
LABEL_73:
            v2 = v46;
          }
        }
      }
      if ( ((_BYTE)v25[3] & 4) != 0 && IsWindowVisible((HWND)*v25) )
      {
        if ( v2 )
          goto LABEL_65;
        if ( (unsigned int)CDSA_Base<SET_VISIBLITY_DATA>::Create(&v46) )
        {
          v2 = v46;
LABEL_65:
          v26 = &v51;
          v51 = (HWND)*v25;
          *((_DWORD *)v25 + 8) = 1;
          v52 = 0;
          goto LABEL_66;
        }
        goto LABEL_73;
      }
    }
  }
  if ( !*((_DWORD *)this + 6) || a2 == -1 && !IsDualEngineProcess() )
    goto LABEL_70;
  v10 = *((_DWORD *)this + 6);
  v49 = 0;
  v48 = 0;
  TrustSplitComponent = IsoLockSharedMemory(v10, (void **)&v49, &v48);
  if ( TrustSplitComponent < 0 )
    goto LABEL_70;
  if ( v48 >= 0x320 )
  {
    v11 = 0;
    while ( 1 )
    {
      v12 = (char *)&v49[10 * v11];
      if ( !v12 )
        goto LABEL_45;
      v13 = *((_DWORD *)v12 + 7);
      if ( !v13 )
        goto LABEL_45;
      v45 = 0;
      if ( (int)CBrowserFrameState::FindRootTabThreadID(this, v13, &v45) >= 0 && a2 == v45 )
      {
        if ( (v12[24] & 2) != 0 )
        {
          *(_OWORD *)v56 = *(_OWORD *)L"IEtd_xxxxxxxx";
          *(_OWORD *)&v56[12] = *(_OWORD *)L"xxxxxxx";
          memset_0(v57, 0, sizeof(v57));
          LODWORD(v44) = *((_DWORD *)v12 + 9);
          StringCchPrintfW((unsigned __int16 *)v56, 0x40u, L"IE_tab_dialog_%08x_%08x", *((_QWORD *)v12 + 1), v44);
          DefaultScope = IsoGetDefaultScope();
          v15 = (unsigned int *)(*(__int64 (__fastcall **)(struct IsoScope *))(*(_QWORD *)DefaultScope + 256LL))(DefaultScope);
          IsoPrefixScopeQualifierToName(v15, Name, 0x80u, (const unsigned __int16 *)v56);
          EventW = CreateEventW(0, 1, 0, Name);
          v17 = EventW;
          if ( EventW )
          {
            if ( !SetEvent(EventW) )
            {
              LastError = GetLastError();
              TrustSplitComponent = LastError;
              if ( LastError > 0 )
                TrustSplitComponent = (unsigned __int16)LastError | 0x80070000;
            }
            CloseHandle(v17);
          }
LABEL_44:
          *((_DWORD *)v12 + 7) = 0;
          goto LABEL_45;
        }
        if ( (v12[24] & 4) == 0 )
          goto LABEL_45;
        if ( !*((_DWORD *)v12 + 8) )
          goto LABEL_45;
        if ( !v2 )
        {
          v19 = CDSA_Base<SET_VISIBLITY_DATA>::Create(&v46);
          v2 = v46;
          if ( !v19 )
            goto LABEL_45;
        }
        v20 = &v51;
        v51 = *(HWND *)v12;
        v52 = 1;
      }
      else
      {
        if ( (v12[24] & 4) == 0
          || CTabBandDragDropHelper::s_spInstance
          && *((_QWORD *)CTabBandDragDropHelper::s_spInstance + 7) == *((_QWORD *)v12 + 1)
          && *((_DWORD *)CTabBandDragDropHelper::s_spInstance + 17) )
        {
          goto LABEL_45;
        }
        if ( !IsWindowVisible(*(HWND *)v12) )
          goto LABEL_45;
        if ( !v2 )
        {
          v21 = CDSA_Base<SET_VISIBLITY_DATA>::Create(&v46);
          v2 = v46;
          if ( !v21 )
            goto LABEL_45;
        }
        v20 = &v53;
        v53 = *(HWND *)v12;
        *((_DWORD *)v12 + 8) = 1;
        v54 = 0;
      }
      if ( (int)CDSA_Base<CAddonEntry>::AppendItem(&v46, v20) < 0 )
        goto LABEL_44;
LABEL_45:
      if ( ++v11 == 20 )
      {
        IsoUnlockArtifact(*((_DWORD *)this + 6));
        goto LABEL_70;
      }
    }
  }
  TrustSplitComponent = -2147467260;
LABEL_70:
  for ( i = 0; ; ++i )
  {
    v28 = v2 ? *(_DWORD *)v2 : 0;
    if ( i >= v28 )
      break;
    v29 = (HWND *)DSA_GetItemPtr(v2, i);
    *((_DWORD *)v29 + 3) = CBrowserFrameState::_SetAssociatedWindowVisibility(v30, *v29, *((_DWORD *)v29 + 2)) >= 0;
  }
  if ( dword_1806A733C )
  {
    v31 = *((_DWORD *)this + 6);
    if ( v31 )
    {
      v49 = 0;
      v45 = 0;
      TrustSplitComponent = IsoLockSharedMemory(v31, (void **)&v49, &v45);
      if ( TrustSplitComponent >= 0 )
      {
        if ( v45 >= 0x320 )
        {
          for ( j = 0; j != 20; ++j )
          {
            v33 = v49;
            if ( v49[10 * j + 7] )
            {
              for ( k = 0; ; ++k )
              {
                v35 = v2 ? *(_DWORD *)v2 : 0;
                if ( k >= v35 )
                  break;
                v36 = DSA_GetItemPtr(v2, k);
                if ( !v36[3] && *(_QWORD *)v36 == *(_QWORD *)&v33[10 * j] )
                  v33[10 * j + 7] = 0;
              }
            }
          }
          IsoUnlockArtifact(*((_DWORD *)this + 6));
        }
        else
        {
          TrustSplitComponent = -2147467260;
        }
      }
    }
  }
  else
  {
    EnterCriticalSection(&g_csDll);
    v37 = (int *)*((_QWORD *)this + 9);
    if ( v37 )
    {
      v38 = *v37;
      while ( --v38 >= 0 )
      {
        v40 = DSA_GetItemPtr(*((HDSA *)this + 9), v38);
        for ( m = 0; ; ++m )
        {
          v42 = v2 ? *(_DWORD *)v2 : 0;
          if ( m >= v42 )
            break;
          v43 = DSA_GetItemPtr(v2, m);
          if ( !v43[3] && *(_QWORD *)v43 == *v40 )
            DSA_DeleteItem(*((HDSA *)this + 9), v38);
        }
      }
    }
    LeaveCriticalSection(&g_csDll);
  }
  DSA_Destroy(v2);
  return (unsigned int)TrustSplitComponent;
}

```

## disassembly

```asm
0x1801df6d8  push    rbp
0x1801df6da  push    rbx
0x1801df6db  push    rsi
0x1801df6dc  push    rdi
0x1801df6dd  push    r12
0x1801df6df  push    r13
0x1801df6e1  push    r14
0x1801df6e3  push    r15
0x1801df6e5  lea     rbp, [rsp-118h]
0x1801df6ed  sub     rsp, 218h
0x1801df6f4  mov     rax, cs:__security_cookie
0x1801df6fb  xor     rax, rsp
0x1801df6fe  mov     [rbp+150h+var_50], rax
0x1801df705  xor     r13d, r13d
0x1801df708  mov     [rcx+30h], edx
0x1801df70b  mov     ebx, r13d
0x1801df70e  mov     [rsp+250h+var_1D8], r13
0x1801df713  mov     [rsp+250h+var_218], rbx
0x1801df718  mov     r12d, edx
0x1801df71b  mov     rsi, rcx
0x1801df71e  mov     [rsp+250h+var_200], r13
0x1801df723  mov     [rsp+250h+var_210], r13d
0x1801df728  call    cs:__imp_GetCurrentThreadId
0x1801df72f  nop     dword ptr [rax+rax+00h]
0x1801df734  mov     ecx, [rsi+14h]
0x1801df737  lea     r9, [rsp+250h+var_210]
0x1801df73c  cmp     [rsi+28h], eax
0x1801df73f  lea     r8, [rsp+250h+var_1D8]
0x1801df744  lea     rax, [rsp+250h+var_200]
0x1801df749  mov     [rsp+250h+var_230], rax
0x1801df74e  jz      short loc_1801DF756
0x1801df750  lea     edx, [r13+2]
0x1801df754  jmp     short loc_1801DF758
0x1801df756  xor     edx, edx
0x1801df758  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1801df75f  nop     dword ptr [rax+rax+00h]
0x1801df764  mov     r14d, eax
0x1801df767  test    eax, eax
0x1801df769  js      short loc_1801DF7B5
0x1801df76b  cmp     cs:dword_1806A733C, r13d
0x1801df772  mov     rcx, [rsp+250h+var_200]
0x1801df777  mov     eax, [rsi+30h]
0x1801df77a  mov     [rcx+44h], eax
0x1801df77d  jz      short loc_1801DF792
0x1801df77f  cmp     [rsi+18h], r13d
0x1801df783  jnz     short loc_1801DF792
0x1801df785  mov     eax, [rcx+64h]
0x1801df788  test    eax, eax
0x1801df78a  jz      short loc_1801DF792
0x1801df78c  mov     eax, [rcx+64h]
0x1801df78f  mov     [rsi+18h], eax
0x1801df792  mov     edi, [rsi+28h]
0x1801df795  call    cs:__imp_GetCurrentThreadId
0x1801df79c  nop     dword ptr [rax+rax+00h]
0x1801df7a1  cmp     edi, eax
0x1801df7a3  jz      short loc_1801DF7B5
0x1801df7a5  mov     ecx, [rsp+250h+var_210]
0x1801df7a9  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801df7b0  nop     dword ptr [rax+rax+00h]
0x1801df7b5  cmp     cs:dword_1806A733C, r13d
0x1801df7bc  jz      loc_1801DFA4D
0x1801df7c2  cmp     [rsi+18h], r13d
0x1801df7c6  jz      loc_1801DFBA0
0x1801df7cc  cmp     r12d, 0FFFFFFFFh
0x1801df7d0  jnz     short loc_1801DF7E6
0x1801df7d2  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801df7d9  nop     dword ptr [rax+rax+00h]
0x1801df7de  test    al, al
0x1801df7e0  jz      loc_1801DFBA0
0x1801df7e6  mov     ecx, [rsi+18h]
0x1801df7e9  lea     r8, [rsp+250h+var_20C]
0x1801df7ee  lea     rdx, [rsp+250h+var_208]
0x1801df7f3  mov     [rsp+250h+var_208], r13
0x1801df7f8  mov     [rsp+250h+var_20C], r13d
0x1801df7fd  call    cs:__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z; IsoLockSharedMemory(ulong,void * *,ulong *)
0x1801df804  nop     dword ptr [rax+rax+00h]
0x1801df809  mov     r14d, eax
0x1801df80c  test    eax, eax
0x1801df80e  js      loc_1801DFBA0
0x1801df814  cmp     [rsp+250h+var_20C], 320h
0x1801df81c  jnb     short loc_1801DF829
0x1801df81e  mov     r14d, 80004004h
0x1801df824  jmp     loc_1801DFBA0
0x1801df829  mov     r15, r13
0x1801df82c  mov     rax, [rsp+250h+var_208]
0x1801df831  lea     rcx, [r15+r15*4]
0x1801df835  lea     rdi, [rax+rcx*8]
0x1801df839  test    rdi, rdi
0x1801df83c  jz      loc_1801DFA2C
0x1801df842  mov     edx, [rdi+1Ch]; unsigned int
0x1801df845  test    edx, edx
0x1801df847  jz      loc_1801DFA2C
0x1801df84d  lea     r8, [rsp+250h+var_220]; unsigned int *
0x1801df852  mov     [rsp+250h+var_220], r13d
0x1801df857  mov     rcx, rsi; this
0x1801df85a  call    ?FindRootTabThreadID@CBrowserFrameState@@UEAAJKPEAK@Z; CBrowserFrameState::FindRootTabThreadID(ulong,ulong *)
0x1801df85f  test    eax, eax
0x1801df861  js      loc_1801DF9B0
0x1801df867  cmp     r12d, [rsp+250h+var_220]
0x1801df86c  jnz     loc_1801DF9B0
0x1801df872  test    byte ptr [rdi+18h], 2
0x1801df876  jz      loc_1801DF968
0x1801df87c  movups  xmm0, xmmword ptr cs:aIetdXxxxxxxx; "IEtd_xxxxxxxx"
0x1801df883  xor     edx, edx; Val
0x1801df885  lea     rcx, [rbp+150h+var_1B4]; void *
0x1801df889  movups  xmm1, xmmword ptr cs:aIetdXxxxxxxx+0Ch; "xxxxxxx"
0x1801df890  movaps  xmmword ptr [rbp+150h+var_1D0], xmm0
0x1801df894  lea     r8d, [rdx+64h]; Size
0x1801df898  movups  xmmword ptr [rbp+150h+var_1D0+0Ch], xmm1
0x1801df89c  call    memset_0
0x1801df8a1  mov     eax, [rdi+24h]
0x1801df8a4  lea     r8, aIeTabDialog08x; "IE_tab_dialog_%08x_%08x"
0x1801df8ab  mov     r9, [rdi+8]
0x1801df8af  lea     rcx, [rbp+150h+var_1D0]; unsigned __int16 *
0x1801df8b3  mov     edx, 40h ; '@'; unsigned __int64
0x1801df8b8  mov     dword ptr [rsp+250h+var_230], eax
0x1801df8bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801df8c1  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801df8c8  nop     dword ptr [rax+rax+00h]
0x1801df8cd  mov     rdx, rax
0x1801df8d0  mov     rcx, [rax]
0x1801df8d3  mov     rax, [rcx+100h]
0x1801df8da  mov     rcx, rdx
0x1801df8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801df8e2  mov     rcx, rax
0x1801df8e5  lea     r9, [rbp+150h+var_1D0]
0x1801df8e9  mov     r8d, 80h
0x1801df8ef  lea     rdx, [rbp+150h+Name]
0x1801df8f3  call    cs:__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z; IsoPrefixScopeQualifierToName(ulong *,ushort *,ulong,ushort const *)
0x1801df8fa  nop     dword ptr [rax+rax+00h]
0x1801df8ff  xor     r8d, r8d; bInitialState
0x1801df902  lea     r9, [rbp+150h+Name]; lpName
0x1801df906  xor     ecx, ecx; lpEventAttributes
0x1801df908  lea     edx, [r8+1]; bManualReset
0x1801df90c  call    cs:__imp_CreateEventW
0x1801df913  nop     dword ptr [rax+rax+00h]
0x1801df918  mov     r13, rax
0x1801df91b  test    rax, rax
0x1801df91e  jz      short loc_1801DF960
0x1801df920  mov     rcx, rax; hEvent
0x1801df923  call    cs:__imp_SetEvent
0x1801df92a  nop     dword ptr [rax+rax+00h]
0x1801df92f  test    eax, eax
0x1801df931  jnz     short loc_1801DF951
0x1801df933  call    cs:__imp_GetLastError
0x1801df93a  nop     dword ptr [rax+rax+00h]
0x1801df93f  mov     r14d, eax
0x1801df942  test    eax, eax
0x1801df944  jle     short loc_1801DF951
0x1801df946  movzx   r14d, ax
0x1801df94a  or      r14d, 80070000h
0x1801df951  mov     rcx, r13; hObject
0x1801df954  call    cs:__imp_CloseHandle
0x1801df95b  nop     dword ptr [rax+rax+00h]
0x1801df960  xor     r13d, r13d
0x1801df963  jmp     loc_1801DFA28
0x1801df968  test    byte ptr [rdi+18h], 4
0x1801df96c  jz      loc_1801DFA2C
0x1801df972  cmp     [rdi+20h], r13d
0x1801df976  jz      loc_1801DFA2C
0x1801df97c  test    rbx, rbx
0x1801df97f  jnz     short loc_1801DF998
0x1801df981  lea     rcx, [rsp+250h+var_218]
0x1801df986  call    ?Create@?$CDSA_Base@USET_VISIBLITY_DATA@@@@QEAAHH@Z; CDSA_Base<SET_VISIBLITY_DATA>::Create(int)
0x1801df98b  mov     rbx, [rsp+250h+var_218]
0x1801df990  test    eax, eax
0x1801df992  jz      loc_1801DFA2C
0x1801df998  mov     rax, [rdi]
0x1801df99b  lea     rdx, [rsp+250h+var_1F8]
0x1801df9a0  mov     [rsp+250h+var_1F8], rax
0x1801df9a5  mov     [rsp+250h+var_1F0], 1
0x1801df9ae  jmp     short loc_1801DFA1A
0x1801df9b0  test    byte ptr [rdi+18h], 4
0x1801df9b4  jz      short loc_1801DFA2C
0x1801df9b6  mov     rcx, cs:?s_spInstance@CTabBandDragDropHelper@@1V?$CComPtr@VCTabBandDragDropHelper@@@ATL@@A; ATL::CComPtr<CTabBandDragDropHelper> CTabBandDragDropHelper::s_spInstance
0x1801df9bd  test    rcx, rcx
0x1801df9c0  jz      short loc_1801DF9D2
0x1801df9c2  mov     rax, [rdi+8]
0x1801df9c6  cmp     [rcx+38h], rax
0x1801df9ca  jnz     short loc_1801DF9D2
0x1801df9cc  cmp     [rcx+44h], r13d
0x1801df9d0  jnz     short loc_1801DFA2C
0x1801df9d2  mov     rcx, [rdi]; hWnd
0x1801df9d5  call    cs:__imp_IsWindowVisible
0x1801df9dc  nop     dword ptr [rax+rax+00h]
0x1801df9e1  test    eax, eax
0x1801df9e3  jz      short loc_1801DFA2C
0x1801df9e5  test    rbx, rbx
0x1801df9e8  jnz     short loc_1801DF9FD
0x1801df9ea  lea     rcx, [rsp+250h+var_218]
0x1801df9ef  call    ?Create@?$CDSA_Base@USET_VISIBLITY_DATA@@@@QEAAHH@Z; CDSA_Base<SET_VISIBLITY_DATA>::Create(int)
0x1801df9f4  mov     rbx, [rsp+250h+var_218]
0x1801df9f9  test    eax, eax
0x1801df9fb  jz      short loc_1801DFA2C
0x1801df9fd  mov     rax, [rdi]
0x1801dfa00  lea     rdx, [rsp+250h+var_1E8]
0x1801dfa05  mov     [rsp+250h+var_1E8], rax
0x1801dfa0a  mov     dword ptr [rdi+20h], 1
0x1801dfa11  mov     [rsp+250h+var_1E0], 0
0x1801dfa1a  lea     rcx, [rsp+250h+var_218]
0x1801dfa1f  call    ?AppendItem@?$CDSA_Base@VCAddonEntry@@@@QEAAJPEBVCAddonEntry@@PEAH@Z; CDSA_Base<CAddonEntry>::AppendItem(CAddonEntry const *,int *)
0x1801dfa24  test    eax, eax
0x1801dfa26  jns     short loc_1801DFA2C
0x1801dfa28  mov     [rdi+1Ch], r13d
0x1801dfa2c  inc     r15
0x1801dfa2f  cmp     r15, 14h
0x1801dfa33  jnz     loc_1801DF82C
0x1801dfa39  mov     ecx, [rsi+18h]
0x1801dfa3c  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801dfa43  nop     dword ptr [rax+rax+00h]
0x1801dfa48  jmp     loc_1801DFBA0
0x1801dfa4d  lea     rcx, g_csDll; lpCriticalSection
0x1801dfa54  call    cs:__imp_EnterCriticalSection
0x1801dfa5b  nop     dword ptr [rax+rax+00h]
0x1801dfa60  mov     r15, [rsi+48h]
0x1801dfa64  test    r15, r15
0x1801dfa67  jz      loc_1801DFB8D
0x1801dfa6d  cmp     r12d, 0FFFFFFFFh
0x1801dfa71  jz      loc_1801DFB8D
0x1801dfa77  mov     r15d, [r15]
0x1801dfa7a  jmp     loc_1801DFB83
0x1801dfa7f  mov     rcx, [rsi+48h]; hdsa
0x1801dfa83  mov     edx, r15d; i
0x1801dfa86  call    cs:__imp_DSA_GetItemPtr
0x1801dfa8d  nop     dword ptr [rax+rax+00h]
0x1801dfa92  lea     r8, [rsp+250h+var_220]; unsigned int *
0x1801dfa97  mov     [rsp+250h+var_220], r13d
0x1801dfa9c  mov     rcx, rsi; this
0x1801dfa9f  mov     rdi, rax
0x1801dfaa2  mov     edx, [rax+1Ch]; unsigned int
0x1801dfaa5  call    ?FindRootTabThreadID@CBrowserFrameState@@UEAAJKPEAK@Z; CBrowserFrameState::FindRootTabThreadID(ulong,ulong *)
0x1801dfaaa  test    eax, eax
0x1801dfaac  js      short loc_1801DFB18
0x1801dfaae  cmp     r12d, [rsp+250h+var_220]
0x1801dfab3  jnz     short loc_1801DFB18
0x1801dfab5  test    byte ptr [rdi+18h], 2
0x1801dfab9  jz      short loc_1801DFAD0
0x1801dfabb  mov     rcx, [rdi+10h]; hEvent
0x1801dfabf  call    cs:__imp_SetEvent
0x1801dfac6  nop     dword ptr [rax+rax+00h]
0x1801dfacb  jmp     loc_1801DFB70
0x1801dfad0  test    byte ptr [rdi+18h], 4
0x1801dfad4  jz      loc_1801DFB83
0x1801dfada  cmp     [rdi+20h], r13d
0x1801dfade  jz      loc_1801DFB83
0x1801dfae4  test    rbx, rbx
0x1801dfae7  jnz     short loc_1801DFB00
0x1801dfae9  lea     rcx, [rsp+250h+var_218]
0x1801dfaee  call    ?Create@?$CDSA_Base@USET_VISIBLITY_DATA@@@@QEAAHH@Z; CDSA_Base<SET_VISIBLITY_DATA>::Create(int)
0x1801dfaf3  test    eax, eax
0x1801dfaf5  jz      loc_1801DFBAC
0x1801dfafb  mov     rbx, [rsp+250h+var_218]
0x1801dfb00  mov     rax, [rdi]
0x1801dfb03  lea     rdx, [rsp+250h+var_1E8]
0x1801dfb08  mov     [rsp+250h+var_1E8], rax
0x1801dfb0d  mov     [rsp+250h+var_1E0], 1
0x1801dfb16  jmp     short loc_1801DFB62
0x1801dfb18  test    byte ptr [rdi+18h], 4
0x1801dfb1c  jz      short loc_1801DFB83
0x1801dfb1e  mov     rcx, [rdi]; hWnd
0x1801dfb21  call    cs:__imp_IsWindowVisible
0x1801dfb28  nop     dword ptr [rax+rax+00h]
0x1801dfb2d  test    eax, eax
0x1801dfb2f  jz      short loc_1801DFB83
0x1801dfb31  test    rbx, rbx
0x1801dfb34  jnz     short loc_1801DFB49
0x1801dfb36  lea     rcx, [rsp+250h+var_218]
0x1801dfb3b  call    ?Create@?$CDSA_Base@USET_VISIBLITY_DATA@@@@QEAAHH@Z; CDSA_Base<SET_VISIBLITY_DATA>::Create(int)
0x1801dfb40  test    eax, eax
0x1801dfb42  jz      short loc_1801DFBAC
0x1801dfb44  mov     rbx, [rsp+250h+var_218]
0x1801dfb49  mov     rax, [rdi]
0x1801dfb4c  lea     rdx, [rsp+250h+var_1F8]
0x1801dfb51  mov     [rsp+250h+var_1F8], rax
0x1801dfb56  mov     dword ptr [rdi+20h], 1
0x1801dfb5d  mov     [rsp+250h+var_1F0], r13
0x1801dfb62  lea     rcx, [rsp+250h+var_218]
0x1801dfb67  call    ?AppendItem@?$CDSA_Base@VCAddonEntry@@@@QEAAJPEBVCAddonEntry@@PEAH@Z; CDSA_Base<CAddonEntry>::AppendItem(CAddonEntry const *,int *)
0x1801dfb6c  test    eax, eax
0x1801dfb6e  jns     short loc_1801DFB83
0x1801dfb70  mov     rcx, [rsi+48h]; hdsa
0x1801dfb74  mov     edx, r15d; i
0x1801dfb77  call    cs:__imp_DSA_DeleteItem
0x1801dfb7e  nop     dword ptr [rax+rax+00h]
0x1801dfb83  sub     r15d, 1
0x1801dfb87  jns     loc_1801DFA7F
0x1801dfb8d  lea     rcx, g_csDll; lpCriticalSection
0x1801dfb94  call    cs:__imp_LeaveCriticalSection
0x1801dfb9b  nop     dword ptr [rax+rax+00h]
0x1801dfba0  mov     r15d, r13d
0x1801dfba3  test    rbx, rbx
0x1801dfba6  jz      short loc_1801DFBB3
0x1801dfba8  mov     eax, [rbx]
0x1801dfbaa  jmp     short loc_1801DFBB6
0x1801dfbac  mov     rbx, [rsp+250h+var_218]
0x1801dfbb1  jmp     short loc_1801DFB83
0x1801dfbb3  mov     eax, r13d
0x1801dfbb6  cmp     r15d, eax
0x1801dfbb9  jge     short loc_1801DFBE9
0x1801dfbbb  mov     edx, r15d; i
  ... truncated ...
```
