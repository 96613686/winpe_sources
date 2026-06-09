# ConnectionManager::NotifyClientsOfEvent(CONMAN_EVENT const *)

- ea: `0x18001c148`
- end: `0x18001c993`
- name: `?NotifyClientsOfEvent@ConnectionManager@@SAXPEBUCONMAN_EVENT@@@Z`
- size: `2123`
- prototype: `void __fastcall(const struct CONMAN_EVENT *)`
- caller_count: `4`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001f710`
- `0x18001fdf0`
- `0x180020020`
- `0x180020350`

## callees

- `0x180001710`
- `0x1800052b4`
- `0x18000538c`
- `0x180019200`
- `0x180019c9c`
- `0x18001b110`
- `0x18001c148`
- `0x18001db38`
- `0x18001dc98`
- `0x18001dd44`
- `0x18001ded0`
- `0x18001e014`
- `0x1800306f8`
- `0x1800318ec`
- `0x180032c3c`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001c777`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001c777`
- `KERNEL32!LeaveCriticalSection` at `0x18001c789`
- `KERNEL32!LeaveCriticalSection` at `0x18001c789`
- `KERNEL32!EnterCriticalSection` at `0x18001c6b8`
- `KERNEL32!EnterCriticalSection` at `0x18001c6b8`

## string_xrefs

- `0x18001c4a4`: `UNKNOWN NCSM: Update DBG_NCSMNAMES table.`
- `0x18001c4be`: `UNKNOWN NCM: Update DBG_NCMNAMES table.`

## pseudocode

```c
void __fastcall ConnectionManager::NotifyClientsOfEvent(const struct CONMAN_EVENT *a1)
{
  volatile struct ConnectionManager *volatile v2; // r13
  unsigned int v3; // r12d
  __int64 (__fastcall ****v4)(_QWORD, GUID *, struct IUnknown **); // rsi
  unsigned int v5; // r14d
  int v6; // ebx
  __int64 v7; // r8
  PVOID v8; // rcx
  int v9; // eax
  PVOID *v10; // r10
  const char *v11; // rax
  __int64 v12; // r10
  __int64 v13; // rdx
  __int64 v14; // r8
  char v15; // r10
  const char *v16; // r11
  const char *v17; // r9
  const char *v18; // rcx
  PVOID *v19; // rcx
  __int64 v20; // rdi
  _WORD *v21; // rdi
  __int64 v22; // rcx
  int v23; // ebx
  int v24; // esi
  unsigned __int64 v25; // rbx
  PVOID *v26; // rcx
  _WORD *v27; // rax
  __int64 v28; // rdi
  const wchar_t *v29; // r9
  __int64 *v30; // rbx
  __int64 v31; // r9
  __int64 v32; // r8
  int v33; // esi
  __int64 v34; // rbx
  _QWORD *v35; // r9
  __int64 v36; // [rsp+20h] [rbp-58h]
  __int64 v37; // [rsp+40h] [rbp-38h] BYREF
  void *lpMem; // [rsp+48h] [rbp-30h] BYREF
  struct IUnknown *v39; // [rsp+50h] [rbp-28h] BYREF
  struct IUnknown *v40; // [rsp+58h] [rbp-20h] BYREF
  struct IUnknown *v41; // [rsp+60h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
  if ( ServiceStatus.dwCurrentState == 4 )
  {
    ConnectionManager::g_fInUse = 1;
    v2 = ConnectionManager::g_pConMan;
    if ( ConnectionManager::g_pConMan )
    {
      LODWORD(v40) = 0;
      lpMem = 0;
      if ( (int)HrCopyIUnknownArrayWhileLocked(
                  (char *)ConnectionManager::g_pConMan + 72,
                  (char *)ConnectionManager::g_pConMan + 16,
                  &v40,
                  &lpMem) >= 0 )
      {
        v3 = (unsigned int)v40;
        if ( (_DWORD)v40 )
        {
          v4 = (__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))lpMem;
          if ( lpMem )
          {
            v5 = 0;
            LODWORD(v40) = 0;
            if ( v3 )
            {
              while ( 1 )
              {
                v39 = 0;
                v6 = (**v4[v5])(v4[v5], &GUID_faedcf5c_31fe_11d1_aad2_00805fc1270e, &v39);
                ReleaseObj((struct IUnknown *)v4[v5]);
                if ( v6 >= 0 )
                  break;
LABEL_132:
                LODWORD(v40) = ++v5;
                if ( v5 >= v3 )
                  goto LABEL_133;
              }
              switch ( *((_DWORD *)a1 + 1) )
              {
                case 1:
                  v19 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      40,
                      &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                      *(unsigned int *)(*((_QWORD *)a1 + 2) + 52LL));
                    v19 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  v20 = *((_QWORD *)a1 + 2);
                  if ( (*(_DWORD *)(v20 + 52) & 1) != 0 )
                  {
                    if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
                    {
                      WPP_SF_(v19[2], 45, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
                      v19 = (PVOID *)WPP_GLOBAL_Control;
                    }
                  }
                  else
                  {
                    v21 = *(_WORD **)(v20 + 96);
                    v41 = 0;
                    v23 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v39->lpVtbl->QueryInterface)(
                            v39,
                            &GUID_00000000_0000_0000_c000_000000000046,
                            &v41);
                    if ( v23 < 0 )
                    {
                      MicrosoftTelemetryAssertTriggeredNoArgs(v22);
                      goto LABEL_112;
                    }
                    if ( v21 && *v21 == 20 )
                    {
                      v24 = 0;
                      v25 = *((unsigned int *)a1 + 8) - 22LL + *((_QWORD *)a1 + 3);
                      v26 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          41,
                          &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
                        v26 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      v27 = v21 + 1;
                      v28 = (__int64)(v21 + 1);
                      while ( *v27 )
                      {
                        if ( (unsigned __int64)v27 >= v25 )
                        {
                          v28 = 0;
                          break;
                        }
                        ++v27;
                      }
                      if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 )
                      {
                        v29 = L"TRUE";
                        if ( !v28 )
                          v29 = L"FALSE";
                        WPP_SF_S(v26[2], 42, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v29);
                      }
                      if ( v28 )
                      {
                        EnterCriticalSection((LPCRITICAL_SECTION)v2 + 2);
                        v37 = 0;
                        std::_Tree<std::_Tmap_traits<IUnknown *,NotifySourceInfo *,std::less<IUnknown *>,std::allocator<std::pair<IUnknown * const,NotifySourceInfo *>>,0>>::find(
                          (char *)v2 + 144,
                          &v37,
                          &v41);
                        if ( v37 == *((_QWORD *)v2 + 18) )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                          {
                            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v37, v41);
                          }
                        }
                        else
                        {
                          v30 = (__int64 *)(*(_QWORD *)(v37 + 40) + 32LL);
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                          {
                            if ( *(_QWORD *)(*(_QWORD *)(v37 + 40) + 56LL) <= 7u )
                              v31 = *(_QWORD *)(v37 + 40) + 32LL;
                            else
                              v31 = *v30;
                            WPP_SF_SS(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              43,
                              (unsigned int)&WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                              v31,
                              v28);
                          }
                          v32 = v30[2];
                          if ( (unsigned __int64)v30[3] > 7 )
                            v30 = (__int64 *)*v30;
                          LOBYTE(v24) = (unsigned int)_o__wcsnicmp(v28, v30, v32) == 0;
                        }
                        LeaveCriticalSection((LPCRITICAL_SECTION)v2 + 2);
                        v5 = (unsigned int)v40;
                      }
                    }
                    else
                    {
                      v24 = 1;
                    }
                    ReleaseObj(v41);
                    if ( !v24 )
                      goto LABEL_131;
                    v19 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 8) != 0 )
                    WPP_SF_q(v19[2], 46, v7, v39);
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v39->lpVtbl[1].QueryInterface)(
                         v39,
                         *((_QWORD *)a1 + 2));
                  break;
                case 2:
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, v7, v39);
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, char *))v39->lpVtbl[1].AddRef)(v39, (char *)a1 + 16);
                  break;
                case 3:
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v7, v39);
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, char *))v39->lpVtbl[1].Release)(v39, (char *)a1 + 16);
                  break;
                case 4:
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  {
                    v16 = DbgNcs(*(_DWORD *)(*((_QWORD *)a1 + 2) + 40LL));
                    if ( *(_DWORD *)(v13 + 48) >= 0xCu )
                      v17 = "UNKNOWN NCSM: Update DBG_NCSMNAMES table.";
                    else
                      v17 = (const char *)(&DBG_NCSMNAMES)[*(unsigned int *)(v13 + 48)];
                    if ( *(_DWORD *)(v13 + 44) >= 0xAu )
                      v18 = "UNKNOWN NCM: Update DBG_NCMNAMES table.";
                    else
                      v18 = (const char *)(&DBG_NCMNAMES)[*(unsigned int *)(v13 + 44)];
                    WPP_SF_qsssD(*(_QWORD *)(v14 + 16), (__int64)v18, (__int64)v17, (__int64)v16, v15);
                  }
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v39->lpVtbl[2].QueryInterface)(
                         v39,
                         *((_QWORD *)a1 + 2));
                  break;
                case 5:
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, v7, v39);
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, char *, char *))v39->lpVtbl[2].AddRef)(
                         v39,
                         (char *)a1 + 16,
                         (char *)a1 + 32);
                  break;
                case 6:
                  v10 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, v7, v39);
                      v10 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
                    {
                      v11 = DbgNcs(*((_DWORD *)a1 + 8));
                      WPP_SF_s(*(_QWORD *)(v12 + 16), 52, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v11, v36);
                    }
                  }
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, char *, _QWORD))v39->lpVtbl[2].Release)(
                         v39,
                         (char *)a1 + 16,
                         *((unsigned int *)a1 + 8));
                  break;
                case 7:
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, v7, v39);
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *))v39->lpVtbl[3].QueryInterface)(v39);
                  break;
                case 8:
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v7, v39);
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, char *))v39->lpVtbl[3].AddRef)(v39, (char *)a1 + 16);
                  break;
                case 9:
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, v7, v39);
                  v9 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD))v39->lpVtbl[4].QueryInterface)(
                         v39,
                         *((unsigned int *)a1 + 4),
                         *((unsigned int *)a1 + 5));
                  break;
                default:
                  v8 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      56,
                      &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                      *((unsigned int *)a1 + 1));
                  MicrosoftTelemetryAssertTriggeredNoArgs(v8);
LABEL_131:
                  ReleaseObj(v39);
                  v4 = (__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))lpMem;
                  goto LABEL_132;
              }
              v23 = v9;
              if ( v9 >= 0 )
              {
LABEL_115:
                if ( v23 == -2147023174
                  || v23 == -2147417848
                  || v23 == -2147418105
                  || (unsigned int)(v23 + 2147023170) <= 1 )
                {
                  v40 = 0;
                  v33 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v39->lpVtbl->QueryInterface)(
                          v39,
                          &GUID_00000000_0000_0000_c000_000000000046,
                          &v40);
                  if ( v33 >= 0 )
                  {
                    v37 = 0;
                    std::_Tree<std::_Tmap_traits<IUnknown *,NotifySourceInfo *,std::less<IUnknown *>,std::allocator<std::pair<IUnknown * const,NotifySourceInfo *>>,0>>::find(
                      (char *)v2 + 144,
                      &v37,
                      &v40);
                    v34 = v37;
                    if ( v37 != *((_QWORD *)v2 + 18) )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        v35 = *(_QWORD **)(v37 + 40);
                        if ( v35[3] > 7u )
                          v35 = (_QWORD *)*v35;
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          58,
                          &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                          v35);
                      }
                      v33 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v2 + 1) + 48LL))(
                              (__int64)v2 + 8,
                              *(unsigned int *)(*(_QWORD *)(v34 + 40) + 64LL));
                    }
                    ReleaseObj(v40);
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      59,
                      &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                      (unsigned int)v33);
                }
                goto LABEL_131;
              }
LABEL_112:
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  57,
                  &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
                  (unsigned int)v23);
              goto LABEL_115;
            }
LABEL_133:
            MemFree(v4);
          }
        }
      }
    }
    ConnectionManager::g_fInUse = 0;
  }
}

```

## disassembly

```asm
0x18001c148  push    rbp
0x18001c14a  push    rbx
0x18001c14b  push    rsi
0x18001c14c  push    rdi
0x18001c14d  push    r12
0x18001c14f  push    r13
0x18001c151  push    r14
0x18001c153  push    r15
0x18001c155  mov     rbp, rsp
0x18001c158  sub     rsp, 78h
0x18001c15c  mov     rax, cs:__security_cookie
0x18001c163  xor     rax, rsp
0x18001c166  mov     [rbp+var_10], rax
0x18001c16a  mov     r15, rcx
0x18001c16d  lea     rax, WPP_GLOBAL_Control
0x18001c174  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c17b  cmp     rcx, rax
0x18001c17e  jz      short loc_18001C19B
0x18001c180  test    byte ptr [rcx+1Ch], 8
0x18001c184  jz      short loc_18001C19B
0x18001c186  mov     edx, 26h ; '&'
0x18001c18b  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001c192  mov     rcx, [rcx+10h]
0x18001c196  call    WPP_SF_
0x18001c19b  cmp     cs:ServiceStatus.dwCurrentState, 4
0x18001c1a2  jnz     loc_18001C976
0x18001c1a8  mov     cs:?g_fInUse@ConnectionManager@@0HC, 1; int volatile ConnectionManager::g_fInUse
0x18001c1b2  mov     r13, cs:?g_pConMan@ConnectionManager@@0PECV1@EC; ConnectionManager volatile * volatile ConnectionManager::g_pConMan
0x18001c1b9  xor     edi, edi
0x18001c1bb  test    r13, r13
0x18001c1be  jz      loc_18001C970
0x18001c1c4  mov     dword ptr [rbp+var_20], edi
0x18001c1c7  mov     [rbp+lpMem], rdi
0x18001c1cb  lea     rdx, [r13+10h]
0x18001c1cf  lea     rcx, [r13+48h]
0x18001c1d3  lea     r9, [rbp+lpMem]
0x18001c1d7  lea     r8, [rbp+var_20]
0x18001c1db  call    ?HrCopyIUnknownArrayWhileLocked@@YAJPEAV?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@PEAVCComDynamicUnkArray@2@PEAKPEAPEAPEAUIUnknown@@@Z; HrCopyIUnknownArrayWhileLocked(ATL::CComObjectRootEx<ATL::CComMultiThreadModel> *,ATL::CComDynamicUnkArray *,ulong *,IUnknown * * *)
0x18001c1e0  test    eax, eax
0x18001c1e2  js      loc_18001C970
0x18001c1e8  mov     r12d, dword ptr [rbp+var_20]
0x18001c1ec  test    r12d, r12d
0x18001c1ef  jz      loc_18001C970
0x18001c1f5  mov     rsi, [rbp+lpMem]
0x18001c1f9  test    rsi, rsi
0x18001c1fc  jz      loc_18001C970
0x18001c202  mov     r14d, edi
0x18001c205  mov     dword ptr [rbp+var_20], edi
0x18001c208  test    r12d, r12d
0x18001c20b  jz      loc_18001C968
0x18001c211  mov     [rbp+var_28], rdi
0x18001c215  mov     edi, r14d
0x18001c218  mov     rcx, [rsi+rdi*8]
0x18001c21c  mov     rax, [rcx]
0x18001c21f  lea     r8, [rbp+var_28]
0x18001c223  lea     rdx, _GUID_faedcf5c_31fe_11d1_aad2_00805fc1270e
0x18001c22a  mov     rax, [rax]
0x18001c22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c232  mov     ebx, eax
0x18001c234  mov     rcx, [rsi+rdi*8]; struct IUnknown *
0x18001c238  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001c23d  xor     edi, edi
0x18001c23f  test    ebx, ebx
0x18001c241  js      loc_18001C958
0x18001c247  mov     r9d, [r15+4]
0x18001c24b  mov     ecx, r9d
0x18001c24e  sub     ecx, 1
0x18001c251  jz      loc_18001C574
0x18001c257  sub     ecx, 1
0x18001c25a  jz      loc_18001C535
0x18001c260  sub     ecx, 1
0x18001c263  jz      loc_18001C4F6
0x18001c269  sub     ecx, 1
0x18001c26c  jz      loc_18001C45D
0x18001c272  sub     ecx, 1
0x18001c275  jz      loc_18001C415
0x18001c27b  sub     ecx, 1
0x18001c27e  jz      loc_18001C398
0x18001c284  sub     ecx, 1
0x18001c287  jz      loc_18001C358
0x18001c28d  sub     ecx, 1
0x18001c290  jz      loc_18001C319
0x18001c296  cmp     ecx, 1
0x18001c299  jz      short loc_18001C2D1
0x18001c29b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2a2  lea     rsi, WPP_GLOBAL_Control
0x18001c2a9  cmp     rcx, rsi
0x18001c2ac  jz      short loc_18001C2C7
0x18001c2ae  test    byte ptr [rcx+1Ch], 8
0x18001c2b2  jz      short loc_18001C2C7
0x18001c2b4  lea     edx, [rdi+38h]
0x18001c2b7  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001c2be  mov     rcx, [rcx+10h]
0x18001c2c2  call    WPP_SF_d
0x18001c2c7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c2cc  jmp     loc_18001C94B
0x18001c2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2d8  lea     rsi, WPP_GLOBAL_Control
0x18001c2df  cmp     rcx, rsi
0x18001c2e2  jz      short loc_18001C2FC
0x18001c2e4  test    byte ptr [rcx+1Ch], 8
0x18001c2e8  jz      short loc_18001C2FC
0x18001c2ea  mov     edx, 37h ; '7'
0x18001c2ef  mov     r9, [rbp+var_28]
0x18001c2f3  mov     rcx, [rcx+10h]
0x18001c2f7  call    WPP_SF_q
0x18001c2fc  mov     rcx, [rbp+var_28]
0x18001c300  mov     rax, [rcx]
0x18001c303  mov     r8d, [r15+14h]
0x18001c307  mov     edx, [r15+10h]
0x18001c30b  mov     rax, [rax+60h]
0x18001c30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c314  jmp     loc_18001C817
0x18001c319  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c320  lea     rsi, WPP_GLOBAL_Control
0x18001c327  cmp     rcx, rsi
0x18001c32a  jz      short loc_18001C344
0x18001c32c  test    byte ptr [rcx+1Ch], 8
0x18001c330  jz      short loc_18001C344
0x18001c332  mov     edx, 36h ; '6'
0x18001c337  mov     r9, [rbp+var_28]
0x18001c33b  mov     rcx, [rcx+10h]
0x18001c33f  call    WPP_SF_q
0x18001c344  mov     rcx, [rbp+var_28]
0x18001c348  mov     rax, [rcx]
0x18001c34b  lea     rdx, [r15+10h]
0x18001c34f  mov     rax, [rax+50h]
0x18001c353  jmp     loc_18001C812
0x18001c358  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c35f  lea     rsi, WPP_GLOBAL_Control
0x18001c366  cmp     rcx, rsi
0x18001c369  jz      short loc_18001C383
0x18001c36b  test    byte ptr [rcx+1Ch], 8
0x18001c36f  jz      short loc_18001C383
0x18001c371  mov     edx, 35h ; '5'
0x18001c376  mov     r9, [rbp+var_28]
0x18001c37a  mov     rcx, [rcx+10h]
0x18001c37e  call    WPP_SF_q
0x18001c383  mov     rcx, [rbp+var_28]
0x18001c387  mov     rax, [rcx]
0x18001c38a  mov     rax, [rax+48h]
0x18001c38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c393  jmp     loc_18001C817
0x18001c398  mov     r10, cs:WPP_GLOBAL_Control
0x18001c39f  lea     rsi, WPP_GLOBAL_Control
0x18001c3a6  cmp     r10, rsi
0x18001c3a9  jz      short loc_18001C3F8
0x18001c3ab  test    byte ptr [r10+1Ch], 8
0x18001c3b0  jz      short loc_18001C3CB
0x18001c3b2  mov     edx, 33h ; '3'
0x18001c3b7  mov     r9, [rbp+var_28]
0x18001c3bb  mov     rcx, [r10+10h]
0x18001c3bf  call    WPP_SF_q
0x18001c3c4  mov     r10, cs:WPP_GLOBAL_Control
0x18001c3cb  cmp     r10, rsi
0x18001c3ce  jz      short loc_18001C3F8
0x18001c3d0  test    byte ptr [r10+1Ch], 8
0x18001c3d5  jz      short loc_18001C3F8
0x18001c3d7  mov     ecx, [r15+20h]; unsigned int
0x18001c3db  call    ?DbgNcs@@YAPEBDK@Z; DbgNcs(ulong)
0x18001c3e0  mov     r9, rax
0x18001c3e3  mov     edx, 34h ; '4'
0x18001c3e8  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001c3ef  mov     rcx, [r10+10h]
0x18001c3f3  call    WPP_SF_s
0x18001c3f8  mov     rcx, [rbp+var_28]
0x18001c3fc  mov     rax, [rcx]
0x18001c3ff  lea     rdx, [r15+10h]
0x18001c403  mov     r8d, [r15+20h]
0x18001c407  mov     rax, [rax+40h]
0x18001c40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c410  jmp     loc_18001C817
0x18001c415  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c41c  lea     rsi, WPP_GLOBAL_Control
0x18001c423  cmp     rcx, rsi
0x18001c426  jz      short loc_18001C440
0x18001c428  test    byte ptr [rcx+1Ch], 8
0x18001c42c  jz      short loc_18001C440
0x18001c42e  mov     edx, 32h ; '2'
0x18001c433  mov     r9, [rbp+var_28]
0x18001c437  mov     rcx, [rcx+10h]
0x18001c43b  call    WPP_SF_q
0x18001c440  mov     rcx, [rbp+var_28]
0x18001c444  mov     rax, [rcx]
0x18001c447  lea     r8, [r15+20h]
0x18001c44b  lea     rdx, [r15+10h]
0x18001c44f  mov     rax, [rax+38h]
0x18001c453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c458  jmp     loc_18001C817
0x18001c45d  mov     r8, cs:WPP_GLOBAL_Control
0x18001c464  lea     rsi, WPP_GLOBAL_Control
0x18001c46b  cmp     r8, rsi
0x18001c46e  jz      short loc_18001C4E6
0x18001c470  test    byte ptr [r8+1Ch], 8
0x18001c475  jz      short loc_18001C4E6
0x18001c477  mov     rdx, [r15+10h]
0x18001c47b  mov     r10d, [rdx+34h]
0x18001c47f  mov     ecx, [rdx+28h]; unsigned int
0x18001c482  call    ?DbgNcs@@YAPEBDK@Z; DbgNcs(ulong)
0x18001c487  mov     r11, rax
0x18001c48a  lea     rbx, __ImageBase
0x18001c491  cmp     dword ptr [rdx+30h], 0Ch
0x18001c495  jnb     short loc_18001C4A4
0x18001c497  mov     ecx, [rdx+30h]
0x18001c49a  mov     r9, ds:rva ?DBG_NCSMNAMES@@3PAPEBDA[rbx+rcx*8]; char const * near * DBG_NCSMNAMES ...
0x18001c4a2  jmp     short loc_18001C4AB
0x18001c4a4  lea     r9, aUnknownNcsmUpd; "UNKNOWN NCSM: Update DBG_NCSMNAMES tabl"...
0x18001c4ab  cmp     dword ptr [rdx+2Ch], 0Ah
0x18001c4af  jnb     short loc_18001C4BE
0x18001c4b1  mov     eax, [rdx+2Ch]
0x18001c4b4  mov     rcx, ds:rva ?DBG_NCMNAMES@@3PAPEBDA[rbx+rax*8]; char const * near * DBG_NCMNAMES ...
0x18001c4bc  jmp     short loc_18001C4C5
0x18001c4be  lea     rcx, aUnknownNcmUpda; "UNKNOWN NCM: Update DBG_NCMNAMES table."
0x18001c4c5  mov     dword ptr [rsp+78h+var_40], r10d; char
0x18001c4ca  mov     [rsp+78h+var_48], r11; __int64
0x18001c4cf  mov     [rsp+78h+var_50], r9; __int64
0x18001c4d4  mov     [rsp+78h+var_58], rcx; __int64
0x18001c4d9  mov     r9, [rbp+var_28]
0x18001c4dd  mov     rcx, [r8+10h]; LoggerHandle
0x18001c4e1  call    WPP_SF_qsssD
0x18001c4e6  mov     rcx, [rbp+var_28]
0x18001c4ea  mov     rax, [rcx]
0x18001c4ed  mov     rax, [rax+30h]
0x18001c4f1  jmp     loc_18001C80E
0x18001c4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4fd  lea     rsi, WPP_GLOBAL_Control
0x18001c504  cmp     rcx, rsi
0x18001c507  jz      short loc_18001C521
0x18001c509  test    byte ptr [rcx+1Ch], 8
0x18001c50d  jz      short loc_18001C521
0x18001c50f  mov     edx, 30h ; '0'
0x18001c514  mov     r9, [rbp+var_28]
0x18001c518  mov     rcx, [rcx+10h]
0x18001c51c  call    WPP_SF_q
0x18001c521  mov     rcx, [rbp+var_28]
0x18001c525  mov     rax, [rcx]
0x18001c528  lea     rdx, [r15+10h]
0x18001c52c  mov     rax, [rax+28h]
0x18001c530  jmp     loc_18001C812
0x18001c535  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c53c  lea     rsi, WPP_GLOBAL_Control
0x18001c543  cmp     rcx, rsi
0x18001c546  jz      short loc_18001C560
0x18001c548  test    byte ptr [rcx+1Ch], 8
0x18001c54c  jz      short loc_18001C560
0x18001c54e  mov     edx, 2Fh ; '/'
0x18001c553  mov     r9, [rbp+var_28]
0x18001c557  mov     rcx, [rcx+10h]
0x18001c55b  call    WPP_SF_q
0x18001c560  mov     rcx, [rbp+var_28]
0x18001c564  mov     rax, [rcx]
0x18001c567  lea     rdx, [r15+10h]
0x18001c56b  mov     rax, [rax+20h]
0x18001c56f  jmp     loc_18001C812
0x18001c574  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c57b  lea     rsi, WPP_GLOBAL_Control
0x18001c582  cmp     rcx, rsi
0x18001c585  jz      short loc_18001C5B1
0x18001c587  test    byte ptr [rcx+1Ch], 8
0x18001c58b  jz      short loc_18001C5B1
0x18001c58d  mov     r9, [r15+10h]
0x18001c591  mov     edx, 28h ; '('
0x18001c596  mov     r9d, [r9+34h]
0x18001c59a  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001c5a1  mov     rcx, [rcx+10h]
0x18001c5a5  call    WPP_SF_d
0x18001c5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5b1  mov     rdi, [r15+10h]
0x18001c5b5  mov     eax, [rdi+34h]
0x18001c5b8  xor     edx, edx
0x18001c5ba  test    al, 1
0x18001c5bc  jnz     loc_18001C7BD
0x18001c5c2  mov     rdi, [rdi+60h]
0x18001c5c6  mov     [rbp+var_18], rdx
0x18001c5ca  mov     rcx, [rbp+var_28]
0x18001c5ce  mov     rax, [rcx]
0x18001c5d1  lea     r8, [rbp+var_18]
0x18001c5d5  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001c5dc  mov     rax, [rax]
0x18001c5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5e4  mov     ebx, eax
0x18001c5e6  xor     edx, edx
0x18001c5e8  test    eax, eax
0x18001c5ea  jns     short loc_18001C5F8
0x18001c5ec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c5f1  xor     edi, edi
0x18001c5f3  jmp     loc_18001C81D
0x18001c5f8  test    rdi, rdi
0x18001c5fb  jz      loc_18001C795
0x18001c601  mov     eax, 14h
0x18001c606  cmp     ax, [rdi]
0x18001c609  jnz     loc_18001C795
0x18001c60f  mov     esi, edx
0x18001c611  mov     ecx, [r15+20h]
0x18001c615  mov     rbx, [r15+18h]
0x18001c619  add     rcx, 0FFFFFFFFFFFFFFEAh
0x18001c61d  add     rbx, rcx
0x18001c620  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c627  lea     r8, WPP_GLOBAL_Control
0x18001c62e  cmp     rcx, r8
  ... truncated ...
```
