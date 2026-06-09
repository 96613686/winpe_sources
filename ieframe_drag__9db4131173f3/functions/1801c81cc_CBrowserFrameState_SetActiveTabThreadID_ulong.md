# CBrowserFrameState::SetActiveTabThreadID(ulong)

- ea: `0x1801c81cc`
- end: `0x1801c87be`
- name: `?SetActiveTabThreadID@CBrowserFrameState@@QEAAJK@Z`
- size: `1522`
- prototype: `__int64 __fastcall(CBrowserFrameState *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009de5c`

## callees

- `0x18000c530`
- `0x1800a11dc`
- `0x1801c5c4c`
- `0x1801c6140`
- `0x1801c81cc`
- `0x1801c9730`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1801c83e1`
- `KERNEL32!SetEvent` at `0x1801c8553`
- `KERNEL32!SetEvent` at `0x1801c83e1`
- `KERNEL32!SetEvent` at `0x1801c8553`
- `KERNEL32!CreateEventW` at `0x1801c83d0`
- `KERNEL32!CreateEventW` at `0x1801c83d0`
- `KERNEL32!CloseHandle` at `0x1801c8406`
- `KERNEL32!CloseHandle` at `0x1801c8406`
- `KERNEL32!GetLastError` at `0x1801c83eb`
- `KERNEL32!GetLastError` at `0x1801c83eb`
- `KERNEL32!GetCurrentThreadId` at `0x1801c821c`
- `KERNEL32!GetCurrentThreadId` at `0x1801c827d`
- `KERNEL32!GetCurrentThreadId` at `0x1801c821c`
- `KERNEL32!GetCurrentThreadId` at `0x1801c827d`
- `KERNEL32!LeaveCriticalSection` at `0x1801c8616`
- `KERNEL32!LeaveCriticalSection` at `0x1801c873a`
- `KERNEL32!LeaveCriticalSection` at `0x1801c8616`
- `KERNEL32!LeaveCriticalSection` at `0x1801c873a`
- `KERNEL32!EnterCriticalSection` at `0x1801c84f4`
- `KERNEL32!EnterCriticalSection` at `0x1801c871d`
- `KERNEL32!EnterCriticalSection` at `0x1801c84f4`
- `KERNEL32!EnterCriticalSection` at `0x1801c871d`
- `USER32!IsWindowVisible` at `0x1801c8481`
- `USER32!IsWindowVisible` at `0x1801c85af`
- `USER32!IsWindowVisible` at `0x1801c8481`
- `USER32!IsWindowVisible` at `0x1801c85af`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801c85ff`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801c87b3`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801c85ff`
- `iertutil!__imp_DSA_DeleteItem` at `0x1801c87b3`
- `iertutil!__imp_DSA_Destroy` at `0x1801c8743`
- `iertutil!__imp_DSA_Destroy` at `0x1801c8743`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c8520`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c863d`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c86de`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c8775`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c8798`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c8520`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c863d`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c86de`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c8775`
- `iertutil!__imp_DSA_GetItemPtr` at `0x1801c8798`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801c82ae`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801c82ae`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1801c83bd`
- `msIso!__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z` at `0x1801c83bd`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c828b`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c84e2`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c870e`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c828b`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c84e2`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x1801c870e`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801c82d3`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801c868b`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801c82d3`
- `msIso!__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z` at `0x1801c868b`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801c8246`
- `msIso!__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z` at `0x1801c8246`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801c8391`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1801c8391`

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
    v7 = dword_180663314 == 0;
    v8 = v50;
    *((_DWORD *)v50 + 17) = *((_DWORD *)this + 12);
    if ( !v7 && !*((_DWORD *)this + 6) && *((_DWORD *)v8 + 25) )
      *((_DWORD *)this + 6) = *((_DWORD *)v8 + 25);
    v9 = *((_DWORD *)this + 10);
    if ( v9 != GetCurrentThreadId() )
      IsoUnlockArtifact(v47);
  }
  if ( !dword_180663314 )
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
  if ( dword_180663314 )
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
0x1801c81cc  push    rbp
0x1801c81ce  push    rbx
0x1801c81cf  push    rsi
0x1801c81d0  push    rdi
0x1801c81d1  push    r12
0x1801c81d3  push    r13
0x1801c81d5  push    r14
0x1801c81d7  push    r15
0x1801c81d9  lea     rbp, [rsp-118h]
0x1801c81e1  sub     rsp, 218h
0x1801c81e8  mov     rax, cs:__security_cookie
0x1801c81ef  xor     rax, rsp
0x1801c81f2  mov     [rbp+150h+var_50], rax
0x1801c81f9  xor     r13d, r13d
0x1801c81fc  mov     [rcx+30h], edx
0x1801c81ff  mov     ebx, r13d
0x1801c8202  mov     [rsp+250h+var_1D8], r13
0x1801c8207  mov     [rsp+250h+var_218], rbx
0x1801c820c  mov     r12d, edx
0x1801c820f  mov     rsi, rcx
0x1801c8212  mov     [rsp+250h+var_200], r13
0x1801c8217  mov     [rsp+250h+var_210], r13d
0x1801c821c  call    cs:__imp_GetCurrentThreadId
0x1801c8222  mov     ecx, [rsi+14h]
0x1801c8225  lea     r9, [rsp+250h+var_210]
0x1801c822a  cmp     [rsi+28h], eax
0x1801c822d  lea     r8, [rsp+250h+var_1D8]
0x1801c8232  lea     rax, [rsp+250h+var_200]
0x1801c8237  mov     [rsp+250h+var_230], rax
0x1801c823c  jz      short loc_1801C8244
0x1801c823e  lea     edx, [r13+2]
0x1801c8242  jmp     short loc_1801C8246
0x1801c8244  xor     edx, edx
0x1801c8246  call    cs:__imp_?IsoGetTrustSplitComponent@@YAJKKPEAPEAU_IsoComponent@@PEAKPEAPEAU_IsoUntrustedComponent@@@Z; IsoGetTrustSplitComponent(ulong,ulong,_IsoComponent * *,ulong *,_IsoUntrustedComponent * *)
0x1801c824c  mov     r14d, eax
0x1801c824f  test    eax, eax
0x1801c8251  js      short loc_1801C8291
0x1801c8253  cmp     cs:dword_180663314, r13d
0x1801c825a  mov     rcx, [rsp+250h+var_200]
0x1801c825f  mov     eax, [rsi+30h]
0x1801c8262  mov     [rcx+44h], eax
0x1801c8265  jz      short loc_1801C827A
0x1801c8267  cmp     [rsi+18h], r13d
0x1801c826b  jnz     short loc_1801C827A
0x1801c826d  mov     eax, [rcx+64h]
0x1801c8270  test    eax, eax
0x1801c8272  jz      short loc_1801C827A
0x1801c8274  mov     eax, [rcx+64h]
0x1801c8277  mov     [rsi+18h], eax
0x1801c827a  mov     edi, [rsi+28h]
0x1801c827d  call    cs:__imp_GetCurrentThreadId
0x1801c8283  cmp     edi, eax
0x1801c8285  jz      short loc_1801C8291
0x1801c8287  mov     ecx, [rsp+250h+var_210]
0x1801c828b  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801c8291  cmp     cs:dword_180663314, r13d
0x1801c8298  jz      loc_1801C84ED
0x1801c829e  cmp     [rsi+18h], r13d
0x1801c82a2  jz      loc_1801C861C
0x1801c82a8  cmp     r12d, 0FFFFFFFFh
0x1801c82ac  jnz     short loc_1801C82BC
0x1801c82ae  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801c82b4  test    al, al
0x1801c82b6  jz      loc_1801C861C
0x1801c82bc  mov     ecx, [rsi+18h]
0x1801c82bf  lea     r8, [rsp+250h+var_20C]
0x1801c82c4  lea     rdx, [rsp+250h+var_208]
0x1801c82c9  mov     [rsp+250h+var_208], r13
0x1801c82ce  mov     [rsp+250h+var_20C], r13d
0x1801c82d3  call    cs:__imp_?IsoLockSharedMemory@@YAJKPEAPEAXPEAK@Z; IsoLockSharedMemory(ulong,void * *,ulong *)
0x1801c82d9  mov     r14d, eax
0x1801c82dc  test    eax, eax
0x1801c82de  js      loc_1801C861C
0x1801c82e4  cmp     [rsp+250h+var_20C], 320h
0x1801c82ec  jnb     short loc_1801C82F9
0x1801c82ee  mov     r14d, 80004004h
0x1801c82f4  jmp     loc_1801C861C
0x1801c82f9  mov     r15, r13
0x1801c82fc  mov     rax, [rsp+250h+var_208]
0x1801c8301  lea     rcx, [r15+r15*4]
0x1801c8305  lea     rdi, [rax+rcx*8]
0x1801c8309  test    rdi, rdi
0x1801c830c  jz      loc_1801C84D2
0x1801c8312  mov     edx, [rdi+1Ch]; unsigned int
0x1801c8315  test    edx, edx
0x1801c8317  jz      loc_1801C84D2
0x1801c831d  lea     r8, [rsp+250h+var_220]; unsigned int *
0x1801c8322  mov     [rsp+250h+var_220], r13d
0x1801c8327  mov     rcx, rsi; this
0x1801c832a  call    ?FindRootTabThreadID@CBrowserFrameState@@UEAAJKPEAK@Z; CBrowserFrameState::FindRootTabThreadID(ulong,ulong *)
0x1801c832f  test    eax, eax
0x1801c8331  js      loc_1801C845C
0x1801c8337  cmp     r12d, [rsp+250h+var_220]
0x1801c833c  jnz     loc_1801C845C
0x1801c8342  test    byte ptr [rdi+18h], 2
0x1801c8346  jz      loc_1801C8414
0x1801c834c  movups  xmm0, xmmword ptr cs:aIetdXxxxxxxx; "IEtd_xxxxxxxx"
0x1801c8353  xor     edx, edx; Val
0x1801c8355  lea     rcx, [rbp+150h+var_1B4]; void *
0x1801c8359  movups  xmm1, xmmword ptr cs:aIetdXxxxxxxx+0Ch; "xxxxxxx"
0x1801c8360  movaps  xmmword ptr [rbp+150h+var_1D0], xmm0
0x1801c8364  lea     r8d, [rdx+64h]; Size
0x1801c8368  movups  xmmword ptr [rbp+150h+var_1D0+0Ch], xmm1
0x1801c836c  call    memset_0
0x1801c8371  mov     eax, [rdi+24h]
0x1801c8374  lea     r8, aIeTabDialog08x; "IE_tab_dialog_%08x_%08x"
0x1801c837b  mov     r9, [rdi+8]
0x1801c837f  lea     rcx, [rbp+150h+var_1D0]; unsigned __int16 *
0x1801c8383  mov     edx, 40h ; '@'; unsigned __int64
0x1801c8388  mov     dword ptr [rsp+250h+var_230], eax
0x1801c838c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801c8391  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1801c8397  mov     rdx, rax
0x1801c839a  mov     rcx, [rax]
0x1801c839d  mov     rax, [rcx+100h]
0x1801c83a4  mov     rcx, rdx
0x1801c83a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c83ac  mov     rcx, rax
0x1801c83af  lea     r9, [rbp+150h+var_1D0]
0x1801c83b3  mov     r8d, 80h
0x1801c83b9  lea     rdx, [rbp+150h+Name]
0x1801c83bd  call    cs:__imp_?IsoPrefixScopeQualifierToName@@YAPEBGPEAKPEAGKPEBG@Z; IsoPrefixScopeQualifierToName(ulong *,ushort *,ulong,ushort const *)
0x1801c83c3  xor     r8d, r8d; bInitialState
0x1801c83c6  lea     r9, [rbp+150h+Name]; lpName
0x1801c83ca  xor     ecx, ecx; lpEventAttributes
0x1801c83cc  lea     edx, [r8+1]; bManualReset
0x1801c83d0  call    cs:__imp_CreateEventW
0x1801c83d6  mov     r13, rax
0x1801c83d9  test    rax, rax
0x1801c83dc  jz      short loc_1801C840C
0x1801c83de  mov     rcx, rax; hEvent
0x1801c83e1  call    cs:__imp_SetEvent
0x1801c83e7  test    eax, eax
0x1801c83e9  jnz     short loc_1801C8403
0x1801c83eb  call    cs:__imp_GetLastError
0x1801c83f1  mov     r14d, eax
0x1801c83f4  test    eax, eax
0x1801c83f6  jle     short loc_1801C8403
0x1801c83f8  movzx   r14d, ax
0x1801c83fc  or      r14d, 80070000h
0x1801c8403  mov     rcx, r13; hObject
0x1801c8406  call    cs:__imp_CloseHandle
0x1801c840c  xor     r13d, r13d
0x1801c840f  jmp     loc_1801C84CE
0x1801c8414  test    byte ptr [rdi+18h], 4
0x1801c8418  jz      loc_1801C84D2
0x1801c841e  cmp     [rdi+20h], r13d
0x1801c8422  jz      loc_1801C84D2
0x1801c8428  test    rbx, rbx
0x1801c842b  jnz     short loc_1801C8444
0x1801c842d  lea     rcx, [rsp+250h+var_218]
0x1801c8432  call    ?Create@?$CDSA_Base@USET_VISIBLITY_DATA@@@@QEAAHH@Z; CDSA_Base<SET_VISIBLITY_DATA>::Create(int)
0x1801c8437  mov     rbx, [rsp+250h+var_218]
0x1801c843c  test    eax, eax
0x1801c843e  jz      loc_1801C84D2
0x1801c8444  mov     rax, [rdi]
0x1801c8447  lea     rdx, [rsp+250h+var_1F8]
0x1801c844c  mov     [rsp+250h+var_1F8], rax
0x1801c8451  mov     [rsp+250h+var_1F0], 1
0x1801c845a  jmp     short loc_1801C84C0
0x1801c845c  test    byte ptr [rdi+18h], 4
0x1801c8460  jz      short loc_1801C84D2
0x1801c8462  mov     rcx, cs:?s_spInstance@CTabBandDragDropHelper@@1V?$CComPtr@VCTabBandDragDropHelper@@@ATL@@A; ATL::CComPtr<CTabBandDragDropHelper> CTabBandDragDropHelper::s_spInstance
0x1801c8469  test    rcx, rcx
0x1801c846c  jz      short loc_1801C847E
0x1801c846e  mov     rax, [rdi+8]
0x1801c8472  cmp     [rcx+38h], rax
0x1801c8476  jnz     short loc_1801C847E
0x1801c8478  cmp     [rcx+44h], r13d
0x1801c847c  jnz     short loc_1801C84D2
0x1801c847e  mov     rcx, [rdi]; hWnd
0x1801c8481  call    cs:__imp_IsWindowVisible
0x1801c8487  test    eax, eax
0x1801c8489  jz      short loc_1801C84D2
0x1801c848b  test    rbx, rbx
0x1801c848e  jnz     short loc_1801C84A3
0x1801c8490  lea     rcx, [rsp+250h+var_218]
0x1801c8495  call    ?Create@?$CDSA_Base@USET_VISIBLITY_DATA@@@@QEAAHH@Z; CDSA_Base<SET_VISIBLITY_DATA>::Create(int)
0x1801c849a  mov     rbx, [rsp+250h+var_218]
0x1801c849f  test    eax, eax
0x1801c84a1  jz      short loc_1801C84D2
0x1801c84a3  mov     rax, [rdi]
0x1801c84a6  lea     rdx, [rsp+250h+var_1E8]
0x1801c84ab  mov     [rsp+250h+var_1E8], rax
0x1801c84b0  mov     dword ptr [rdi+20h], 1
0x1801c84b7  mov     [rsp+250h+var_1E0], 0
0x1801c84c0  lea     rcx, [rsp+250h+var_218]
0x1801c84c5  call    ?AppendItem@?$CDSA_Base@VCAddonEntry@@@@QEAAJPEBVCAddonEntry@@PEAH@Z; CDSA_Base<CAddonEntry>::AppendItem(CAddonEntry const *,int *)
0x1801c84ca  test    eax, eax
0x1801c84cc  jns     short loc_1801C84D2
0x1801c84ce  mov     [rdi+1Ch], r13d
0x1801c84d2  inc     r15
0x1801c84d5  cmp     r15, 14h
0x1801c84d9  jnz     loc_1801C82FC
0x1801c84df  mov     ecx, [rsi+18h]
0x1801c84e2  call    cs:__imp_?IsoUnlockArtifact@@YAJK@Z; IsoUnlockArtifact(ulong)
0x1801c84e8  jmp     loc_1801C861C
0x1801c84ed  lea     rcx, g_csDll; lpCriticalSection
0x1801c84f4  call    cs:__imp_EnterCriticalSection
0x1801c84fa  mov     r15, [rsi+48h]
0x1801c84fe  test    r15, r15
0x1801c8501  jz      loc_1801C860F
0x1801c8507  cmp     r12d, 0FFFFFFFFh
0x1801c850b  jz      loc_1801C860F
0x1801c8511  mov     r15d, [r15]
0x1801c8514  jmp     loc_1801C8605
0x1801c8519  mov     rcx, [rsi+48h]; hdsa
0x1801c851d  mov     edx, r15d; i
0x1801c8520  call    cs:__imp_DSA_GetItemPtr
0x1801c8526  lea     r8, [rsp+250h+var_220]; unsigned int *
0x1801c852b  mov     [rsp+250h+var_220], r13d
0x1801c8530  mov     rcx, rsi; this
0x1801c8533  mov     rdi, rax
0x1801c8536  mov     edx, [rax+1Ch]; unsigned int
0x1801c8539  call    ?FindRootTabThreadID@CBrowserFrameState@@UEAAJKPEAK@Z; CBrowserFrameState::FindRootTabThreadID(ulong,ulong *)
0x1801c853e  test    eax, eax
0x1801c8540  js      short loc_1801C85A6
0x1801c8542  cmp     r12d, [rsp+250h+var_220]
0x1801c8547  jnz     short loc_1801C85A6
0x1801c8549  test    byte ptr [rdi+18h], 2
0x1801c854d  jz      short loc_1801C855E
0x1801c854f  mov     rcx, [rdi+10h]; hEvent
0x1801c8553  call    cs:__imp_SetEvent
0x1801c8559  jmp     loc_1801C85F8
0x1801c855e  test    byte ptr [rdi+18h], 4
0x1801c8562  jz      loc_1801C8605
0x1801c8568  cmp     [rdi+20h], r13d
0x1801c856c  jz      loc_1801C8605
0x1801c8572  test    rbx, rbx
0x1801c8575  jnz     short loc_1801C858E
0x1801c8577  lea     rcx, [rsp+250h+var_218]
0x1801c857c  call    ?Create@?$CDSA_Base@USET_VISIBLITY_DATA@@@@QEAAHH@Z; CDSA_Base<SET_VISIBLITY_DATA>::Create(int)
0x1801c8581  test    eax, eax
0x1801c8583  jz      loc_1801C8628
0x1801c8589  mov     rbx, [rsp+250h+var_218]
0x1801c858e  mov     rax, [rdi]
0x1801c8591  lea     rdx, [rsp+250h+var_1E8]
0x1801c8596  mov     [rsp+250h+var_1E8], rax
0x1801c859b  mov     [rsp+250h+var_1E0], 1
0x1801c85a4  jmp     short loc_1801C85EA
0x1801c85a6  test    byte ptr [rdi+18h], 4
0x1801c85aa  jz      short loc_1801C8605
0x1801c85ac  mov     rcx, [rdi]; hWnd
0x1801c85af  call    cs:__imp_IsWindowVisible
0x1801c85b5  test    eax, eax
0x1801c85b7  jz      short loc_1801C8605
0x1801c85b9  test    rbx, rbx
0x1801c85bc  jnz     short loc_1801C85D1
0x1801c85be  lea     rcx, [rsp+250h+var_218]
0x1801c85c3  call    ?Create@?$CDSA_Base@USET_VISIBLITY_DATA@@@@QEAAHH@Z; CDSA_Base<SET_VISIBLITY_DATA>::Create(int)
0x1801c85c8  test    eax, eax
0x1801c85ca  jz      short loc_1801C8628
0x1801c85cc  mov     rbx, [rsp+250h+var_218]
0x1801c85d1  mov     rax, [rdi]
0x1801c85d4  lea     rdx, [rsp+250h+var_1F8]
0x1801c85d9  mov     [rsp+250h+var_1F8], rax
0x1801c85de  mov     dword ptr [rdi+20h], 1
0x1801c85e5  mov     [rsp+250h+var_1F0], r13
0x1801c85ea  lea     rcx, [rsp+250h+var_218]
0x1801c85ef  call    ?AppendItem@?$CDSA_Base@VCAddonEntry@@@@QEAAJPEBVCAddonEntry@@PEAH@Z; CDSA_Base<CAddonEntry>::AppendItem(CAddonEntry const *,int *)
0x1801c85f4  test    eax, eax
0x1801c85f6  jns     short loc_1801C8605
0x1801c85f8  mov     rcx, [rsi+48h]; hdsa
0x1801c85fc  mov     edx, r15d; i
0x1801c85ff  call    cs:__imp_DSA_DeleteItem
0x1801c8605  sub     r15d, 1
0x1801c8609  jns     loc_1801C8519
0x1801c860f  lea     rcx, g_csDll; lpCriticalSection
0x1801c8616  call    cs:__imp_LeaveCriticalSection
0x1801c861c  mov     r15d, r13d
0x1801c861f  test    rbx, rbx
0x1801c8622  jz      short loc_1801C862F
0x1801c8624  mov     eax, [rbx]
0x1801c8626  jmp     short loc_1801C8632
0x1801c8628  mov     rbx, [rsp+250h+var_218]
0x1801c862d  jmp     short loc_1801C8605
0x1801c862f  mov     eax, r13d
0x1801c8632  cmp     r15d, eax
0x1801c8635  jge     short loc_1801C865F
0x1801c8637  mov     edx, r15d; i
0x1801c863a  mov     rcx, rbx; hdsa
0x1801c863d  call    cs:__imp_DSA_GetItemPtr
0x1801c8643  mov     rdi, rax
0x1801c8646  mov     r8d, [rax+8]; int
0x1801c864a  mov     rdx, [rax]; HWND
0x1801c864d  call    ?_SetAssociatedWindowVisibility@CBrowserFrameState@@AEAAJPEAUHWND__@@H@Z; CBrowserFrameState::_SetAssociatedWindowVisibility(HWND__ *,int)
0x1801c8652  not     eax
0x1801c8654  shr     eax, 1Fh
0x1801c8657  mov     [rdi+0Ch], eax
0x1801c865a  inc     r15d
0x1801c865d  jmp     short loc_1801C861F
0x1801c865f  cmp     cs:dword_180663314, r13d
0x1801c8666  jz      loc_1801C8716
0x1801c866c  mov     ecx, [rsi+18h]
0x1801c866f  test    ecx, ecx
0x1801c8671  jz      loc_1801C8740
0x1801c8677  lea     r8, [rsp+250h+var_220]
0x1801c867c  mov     [rsp+250h+var_208], r13
0x1801c8681  lea     rdx, [rsp+250h+var_208]
0x1801c8686  mov     [rsp+250h+var_220], r13d
  ... truncated ...
```
