# CHNetCfgMgr::GetPossiblePrivateConnections(IHNetConnection *,ulong *,IHNetConnection * * * const,long *)

- ea: `0x180015200`
- end: `0x180015ac1`
- name: `?GetPossiblePrivateConnections@CHNetCfgMgr@@UEAAJPEAUIHNetConnection@@PEAKQEAPEAPEAU2@PEAJ@Z`
- size: `2241`
- prototype: `__int64 __fastcall(CHNetCfgMgr *__hidden this, struct IHNetConnection *, unsigned int *, struct IHNetConnection ***const, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180015200`
- `0x180028380`
- `0x18002a6a0`
- `0x18002ab30`
- `0x18002aef4`
- `0x18002d1d2`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800153ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800153ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015a69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001535b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001535b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001534d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800153ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015a5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001534d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800153ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015a5b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180015339`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180015386`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180015339`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180015386`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800154ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800154ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800155ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800155ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001584d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800158d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015982`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800159bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001584d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800158d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015982`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800159bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015a44`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::GetPossiblePrivateConnections(
        CHNetCfgMgr *this,
        struct IHNetConnection *a2,
        unsigned int *a3,
        struct IHNetConnection ***const a4,
        int *a5)
{
  PVOID *v8; // rbx
  void *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // r9
  signed int AdaptersAddresses; // ebx
  ULONG v13; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  HRESULT v19; // eax
  int v20; // ebx
  int v21; // eax
  int v22; // eax
  int v23; // ebx
  __int64 v24; // r12
  char *j; // r14
  int v26; // r15d
  char *v27; // rsi
  char *v28; // r13
  ULONG v29; // edx
  __int64 i; // r13
  struct IUnknown *v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  char v34; // bl
  struct IHNetConnection **v35; // rbx
  int v36; // eax
  struct IHNetConnection *v37; // rcx
  struct _GUID *v38; // rdx
  __int64 v39; // rbx
  __int64 v40; // rbx
  __int64 k; // rbx
  __int64 v42; // rcx
  void *v43; // rdi
  HANDLE v44; // rax
  ULONG SizePointer; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-C0h]
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v50; // [rsp+50h] [rbp-B0h] BYREF
  NETCON_PROPERTIES *pProps; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID *v52; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v53; // [rsp+68h] [rbp-98h] BYREF
  int *v54; // [rsp+70h] [rbp-90h]
  CHNetCfgMgr *v55; // [rsp+78h] [rbp-88h]
  unsigned int *v56; // [rsp+80h] [rbp-80h]
  struct IHNetConnection ***v57; // [rsp+88h] [rbp-78h]
  struct IUnknown *v58[16]; // [rsp+90h] [rbp-70h] BYREF

  v54 = a5;
  v57 = a4;
  v56 = a3;
  v55 = this;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = 0;
  ppv = 0;
  v50 = 0;
  memset_0(v58, 0, sizeof(v58));
  v53 = 0;
  pv = 0;
  lpMem = 0;
  pProps = 0;
  if ( !a4 )
  {
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 8) == 0 || *((_BYTE *)v8 + 25) < 2u )
      goto LABEL_138;
    v10 = 171;
LABEL_136:
    v11 = 2147500035LL;
    goto LABEL_137;
  }
  *a4 = 0;
  if ( !a2 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 169;
      v11 = 2147942487LL;
LABEL_137:
      WPP_SF_d(v8[2], v10, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v11);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_138:
    if ( !a5 )
      goto LABEL_141;
    goto LABEL_139;
  }
  if ( !a3 || !a5 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_138;
    }
    v10 = 170;
    goto LABEL_136;
  }
  *a3 = 0;
  *a5 = -1;
  lpMem = 0;
  SizePointer = 0;
  AdaptersAddresses = GetAdaptersAddresses(0, 0, 0, 0, &SizePointer);
  if ( AdaptersAddresses == 111 )
  {
    v13 = SizePointer;
    ProcessHeap = GetProcessHeap();
    lpMem = HeapAlloc(ProcessHeap, 0, v13);
    v9 = lpMem;
    if ( !lpMem )
    {
      LOWORD(AdaptersAddresses) = 8;
      goto LABEL_19;
    }
    AdaptersAddresses = GetAdaptersAddresses(0, 0, 0, (PIP_ADAPTER_ADDRESSES)lpMem, &SizePointer);
  }
  if ( AdaptersAddresses )
  {
    lpMem = v9;
    if ( AdaptersAddresses <= 0 )
    {
LABEL_20:
      if ( v9 )
      {
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v9);
        lpMem = 0;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_139;
      }
      v17 = 172;
      v18 = (unsigned int)AdaptersAddresses;
      goto LABEL_33;
    }
    lpMem = v9;
LABEL_19:
    AdaptersAddresses = (unsigned __int16)AdaptersAddresses | 0x80070000;
    goto LABEL_20;
  }
  v19 = (*(__int64 (__fastcall **)(struct IHNetConnection *, LPVOID *))(*(_QWORD *)a2 + 56LL))(a2, &pv);
  v20 = v19;
  if ( v19 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_139;
    }
    v17 = 173;
    goto LABEL_32;
  }
  if ( *(_BYTE *)pv )
  {
    v21 = (*(__int64 (__fastcall **)(struct IHNetConnection *, LPVOID *))(*(_QWORD *)a2 + 32LL))(a2, &v53);
    v20 = v21;
    if ( v21 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        174,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v21);
    }
  }
  CoTaskMemFree(pv);
  if ( v20 < 0 )
    goto LABEL_139;
  v19 = CoCreateInstance(&CLSID_ConnectionManager, 0, 0x8005u, &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e, &ppv);
  if ( v19 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_139;
    }
    v17 = 175;
LABEL_32:
    v18 = (unsigned int)v19;
LABEL_33:
    WPP_SF_d(v16[2], v17, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v18);
    goto LABEL_139;
  }
  SetProxyBlanket((struct IUnknown *)ppv);
  v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IUnknown **))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v50);
  v23 = v22;
  if ( v22 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      176,
      &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
      (unsigned int)v22);
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v23 < 0 )
    goto LABEL_139;
  v24 = 0;
  j = 0;
  SizePointer = 0;
  SetProxyBlanket(v50);
  while ( 1 )
  {
    v26 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **, ULONG *))v50->lpVtbl[1].QueryInterface)(
            v50,
            16,
            v58,
            &SizePointer);
    if ( v26 < 0 )
      break;
    if ( !SizePointer )
      goto LABEL_117;
    v27 = j;
    v28 = j;
    j = (char *)CoTaskMemRealloc(j, 8LL * ((unsigned int)v24 + SizePointer));
    if ( j )
    {
      v29 = SizePointer;
      for ( i = 0; (unsigned int)i < SizePointer; i = (unsigned int)(i + 1) )
      {
        SetProxyBlanket(v58[i]);
        v31 = v58[i];
        pProps = 0;
        v26 = ((__int64 (__fastcall *)(struct IUnknown *, NETCON_PROPERTIES **))v31->lpVtbl[2].AddRef)(v31, &pProps);
        if ( v26 >= 0 )
        {
          if ( pProps )
          {
            if ( pProps->MediaType == NCM_SHAREDACCESSHOST_LAN
              || (v34 = 0, pProps->MediaType == NCM_SHAREDACCESSHOST_RAS) )
            {
              v34 = 1;
            }
            NcFreeNetconProperties(pProps);
            if ( v34 )
              goto LABEL_97;
          }
          v35 = (struct IHNetConnection **)&j[8 * v24];
          v36 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, struct IHNetConnection **))(*((_QWORD *)v55 - 3)
                                                                                                 + 24LL))(
                  (__int64)v55 - 24,
                  v58[i],
                  v35);
          if ( v36 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                179,
                &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
                (unsigned int)v36);
            }
            v26 = 0;
            *v35 = 0;
            goto LABEL_97;
          }
          v26 = (*(__int64 (__fastcall **)(struct IHNetConnection *, LPVOID *))(*(_QWORD *)*v35 + 56LL))(*v35, &pv);
          if ( v26 >= 0 )
          {
            UpdatePropertiesWithNetcon2(*v35, (struct tagHNET_CONN_PROPERTIES *)pv);
            v37 = *v35;
            if ( !*((_BYTE *)pv + 9) )
              goto LABEL_80;
            v52 = 0;
            v26 = (*(__int64 (__fastcall **)(struct IHNetConnection *, struct _GUID **))(*(_QWORD *)v37 + 32LL))(
                    v37,
                    &v52);
            if ( v26 >= 0 )
            {
              v38 = v52;
              if ( v53 && *(_QWORD *)v53 == *(_QWORD *)&v52->Data1 && *((_QWORD *)v53 + 1) == *(_QWORD *)v52->Data4
                || !ConnectionIsBoundToTcp((struct _IP_ADAPTER_ADDRESSES_LH *)lpMem, v52) )
              {
                (*(void (__fastcall **)(struct IHNetConnection *, struct _GUID *))(*(_QWORD *)*v35 + 16LL))(*v35, v38);
                *v35 = 0;
              }
              else
              {
                if ( *((_BYTE *)pv + 3) )
                  *v54 = v24;
                v24 = (unsigned int)(v24 + 1);
              }
              CoTaskMemFree(v52);
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  181,
                  &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
                  (unsigned int)v26);
              }
              v37 = *v35;
LABEL_80:
              (*(void (__fastcall **)(struct IHNetConnection *))(*(_QWORD *)v37 + 16LL))(v37);
              *v35 = 0;
            }
            CoTaskMemFree(pv);
            goto LABEL_97;
          }
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_97;
          }
          v33 = 180;
        }
        else
        {
          v32 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_97;
          }
          v33 = 178;
        }
        WPP_SF_d(v32[2], v33, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v26);
LABEL_97:
        v29 = SizePointer;
      }
    }
    else
    {
      v26 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          182,
          &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
          2147942414LL);
      }
      if ( v27 )
      {
        v39 = 0;
        for ( j = v27; (unsigned int)v39 < (unsigned int)v24; v39 = (unsigned int)(v39 + 1) )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v28[8 * v39] + 16LL))(*(_QWORD *)&v28[8 * v39]);
        CoTaskMemFree(v27);
      }
      v29 = SizePointer;
    }
    v40 = 0;
    if ( v29 )
    {
      do
      {
        ((void (__fastcall *)(struct IUnknown *))v58[v40]->lpVtbl->Release)(v58[v40]);
        v29 = SizePointer;
        v40 = (unsigned int)(v40 + 1);
      }
      while ( (unsigned int)v40 < SizePointer );
    }
    if ( v26 < 0 || !v29 )
      goto LABEL_117;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      177,
      &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
      (unsigned int)v26);
  }
LABEL_117:
  ((void (__fastcall *)(struct IUnknown *))v50->lpVtbl->Release)(v50);
  if ( v26 >= 0 )
  {
    if ( (_DWORD)v24 )
    {
      *v56 = v24;
      *v57 = (struct IHNetConnection **)j;
    }
    else if ( j )
    {
      CoTaskMemFree(j);
    }
    goto LABEL_140;
  }
  if ( j )
  {
    for ( k = 0; (unsigned int)k < (unsigned int)v24; k = (unsigned int)(k + 1) )
    {
      v42 = *(_QWORD *)&j[8 * k];
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    CoTaskMemFree(j);
  }
LABEL_139:
  *v54 = -1;
LABEL_140:
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_141:
  if ( v53 )
  {
    CoTaskMemFree(v53);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v43 = lpMem;
  if ( lpMem )
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v43);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 183, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180015200  push    rbp
0x180015202  push    rbx
0x180015203  push    rsi
0x180015204  push    rdi
0x180015205  push    r12
0x180015207  push    r13
0x180015209  push    r14
0x18001520b  push    r15
0x18001520d  lea     rbp, [rsp-28h]
0x180015212  sub     rsp, 128h
0x180015219  mov     rax, cs:__security_cookie
0x180015220  xor     rax, rsp
0x180015223  mov     [rbp+60h+var_50], rax
0x180015227  mov     r15, [rbp+60h+arg_20]
0x18001522e  mov     r13, r9
0x180015231  mov     [rsp+160h+var_F0], r15
0x180015236  mov     rdi, r8
0x180015239  mov     [rbp+60h+var_D8], r9
0x18001523d  mov     rsi, rdx
0x180015240  mov     [rbp+60h+var_E0], r8
0x180015244  mov     [rsp+160h+var_E8], rcx
0x180015249  mov     rbx, cs:WPP_GLOBAL_Control
0x180015250  lea     r12, WPP_GLOBAL_Control
0x180015257  cmp     rbx, r12
0x18001525a  jz      short loc_180015284
0x18001525c  test    byte ptr [rbx+1Ch], 8
0x180015260  jz      short loc_180015284
0x180015262  cmp     byte ptr [rbx+19h], 6
0x180015266  jb      short loc_180015284
0x180015268  mov     rcx, [rbx+10h]
0x18001526c  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180015273  mov     edx, 0A8h
0x180015278  call    WPP_SF_
0x18001527d  mov     rbx, cs:WPP_GLOBAL_Control
0x180015284  xor     r14d, r14d
0x180015287  lea     rcx, [rbp+60h+var_D0]; void *
0x18001528b  xor     edx, edx; Val
0x18001528d  mov     [rsp+160h+ppv], r14
0x180015292  mov     r8d, 80h; Size
0x180015298  mov     [rsp+160h+var_110], r14
0x18001529d  call    memset_0
0x1800152a2  mov     [rsp+160h+var_F8], r14
0x1800152a7  mov     [rsp+160h+pv], r14
0x1800152ac  mov     [rsp+160h+lpMem], r14
0x1800152b1  mov     [rsp+160h+pProps], r14
0x1800152b6  test    r13, r13
0x1800152b9  jz      loc_1800159E6
0x1800152bf  mov     [r13+0], r14
0x1800152c3  test    rsi, rsi
0x1800152c6  jnz     short loc_1800152FF
0x1800152c8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800152cf  cmp     rbx, r12
0x1800152d2  jz      loc_180015A1C
0x1800152d8  test    byte ptr [rbx+1Ch], 8
0x1800152dc  jz      loc_180015A1C
0x1800152e2  mov     dil, 2
0x1800152e5  cmp     [rbx+19h], dil
0x1800152e9  jb      loc_180015A1C
0x1800152ef  mov     edx, 0A9h
0x1800152f4  mov     r9d, 80070057h
0x1800152fa  jmp     loc_180015A05
0x1800152ff  test    rdi, rdi
0x180015302  jz      loc_1800159C4
0x180015308  test    r15, r15
0x18001530b  jz      loc_1800159C4
0x180015311  lea     rax, [rsp+160h+var_130]
0x180015316  mov     [rdi], r14d
0x180015319  xor     r9d, r9d; AdapterAddresses
0x18001531c  mov     [rsp+160h+SizePointer], rax; SizePointer
0x180015321  xor     r8d, r8d; Reserved
0x180015324  mov     dword ptr [r15], 0FFFFFFFFh
0x18001532b  xor     edx, edx; Flags
0x18001532d  mov     [rsp+160h+lpMem], r14
0x180015332  xor     ecx, ecx; Family
0x180015334  mov     [rsp+160h+var_130], r14d
0x180015339  call    cs:__imp_GetAdaptersAddresses
0x18001533f  mov     ebx, eax
0x180015341  mov     dil, 2
0x180015344  cmp     eax, 6Fh ; 'o'
0x180015347  jnz     short loc_18001538E
0x180015349  mov     ebx, [rsp+160h+var_130]
0x18001534d  call    cs:__imp_GetProcessHeap
0x180015353  mov     r8d, ebx; dwBytes
0x180015356  xor     edx, edx; dwFlags
0x180015358  mov     rcx, rax; hHeap
0x18001535b  call    cs:__imp_HeapAlloc
0x180015361  mov     [rsp+160h+lpMem], rax
0x180015366  mov     r14, rax
0x180015369  test    rax, rax
0x18001536c  jz      loc_1800153FB
0x180015372  lea     rax, [rsp+160h+var_130]
0x180015377  mov     r9, r14; AdapterAddresses
0x18001537a  xor     r8d, r8d; Reserved
0x18001537d  mov     [rsp+160h+SizePointer], rax; SizePointer
0x180015382  xor     edx, edx; Flags
0x180015384  xor     ecx, ecx; Family
0x180015386  call    cs:__imp_GetAdaptersAddresses
0x18001538c  mov     ebx, eax
0x18001538e  test    ebx, ebx
0x180015390  jz      short loc_180015408
0x180015392  mov     [rsp+160h+lpMem], r14
0x180015397  jle     short loc_1800153A7
0x180015399  mov     [rsp+160h+lpMem], r14
0x18001539e  movzx   ebx, bx
0x1800153a1  or      ebx, 80070000h
0x1800153a7  test    r14, r14
0x1800153aa  jz      short loc_1800153C9
0x1800153ac  call    cs:__imp_GetProcessHeap
0x1800153b2  mov     r8, r14; lpMem
0x1800153b5  xor     edx, edx; dwFlags
0x1800153b7  mov     rcx, rax; hHeap
0x1800153ba  call    cs:__imp_HeapFree
0x1800153c0  mov     [rsp+160h+lpMem], 0
0x1800153c9  test    ebx, ebx
0x1800153cb  jns     short loc_180015402
0x1800153cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153d4  cmp     rcx, r12
0x1800153d7  jz      loc_180015A21
0x1800153dd  test    byte ptr [rcx+1Ch], 8
0x1800153e1  jz      loc_180015A21
0x1800153e7  cmp     [rcx+19h], dil
0x1800153eb  jb      loc_180015A21
0x1800153f1  mov     edx, 0ACh
0x1800153f6  mov     r9d, ebx
0x1800153f9  jmp     short loc_18001544E
0x1800153fb  mov     ebx, 8
0x180015400  jmp     short loc_18001539E
0x180015402  jnz     loc_1800154CA
0x180015408  mov     rax, [rsi]
0x18001540b  lea     rdx, [rsp+160h+pv]
0x180015410  mov     rcx, rsi
0x180015413  mov     rax, [rax+38h]
0x180015417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001541c  mov     ebx, eax
0x18001541e  test    eax, eax
0x180015420  jns     short loc_180015463
0x180015422  mov     rcx, cs:WPP_GLOBAL_Control
0x180015429  cmp     rcx, r12
0x18001542c  jz      loc_180015A21
0x180015432  test    byte ptr [rcx+1Ch], 8
0x180015436  jz      loc_180015A21
0x18001543c  cmp     [rcx+19h], dil
0x180015440  jb      loc_180015A21
0x180015446  mov     edx, 0ADh
0x18001544b  mov     r9d, eax
0x18001544e  mov     rcx, [rcx+10h]
0x180015452  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x180015459  call    WPP_SF_d
0x18001545e  jmp     loc_180015A21
0x180015463  mov     rax, [rsp+160h+pv]
0x180015468  cmp     byte ptr [rax], 0
0x18001546b  jz      short loc_1800154B7
0x18001546d  mov     rax, [rsi]
0x180015470  lea     rdx, [rsp+160h+var_F8]
0x180015475  mov     rcx, rsi
0x180015478  mov     rax, [rax+20h]
0x18001547c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015481  mov     ebx, eax
0x180015483  test    eax, eax
0x180015485  jns     short loc_1800154B7
0x180015487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001548e  cmp     rcx, r12
0x180015491  jz      short loc_1800154B7
0x180015493  test    byte ptr [rcx+1Ch], 8
0x180015497  jz      short loc_1800154B7
0x180015499  cmp     [rcx+19h], dil
0x18001549d  jb      short loc_1800154B7
0x18001549f  mov     rcx, [rcx+10h]
0x1800154a3  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x1800154aa  mov     edx, 0AEh
0x1800154af  mov     r9d, eax
0x1800154b2  call    WPP_SF_d
0x1800154b7  mov     rcx, [rsp+160h+pv]; pv
0x1800154bc  call    cs:__imp_CoTaskMemFree
0x1800154c2  test    ebx, ebx
0x1800154c4  js      loc_180015A21
0x1800154ca  lea     rax, [rsp+160h+ppv]
0x1800154cf  xor     edx, edx; pUnkOuter
0x1800154d1  lea     r9, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; riid
0x1800154d8  mov     [rsp+160h+SizePointer], rax; ppv
0x1800154dd  mov     r8d, 8005h; dwClsContext
0x1800154e3  lea     rcx, CLSID_ConnectionManager; rclsid
0x1800154ea  call    cs:__imp_CoCreateInstance
0x1800154f0  test    eax, eax
0x1800154f2  jns     short loc_180015522
0x1800154f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154fb  cmp     rcx, r12
0x1800154fe  jz      loc_180015A21
0x180015504  test    byte ptr [rcx+1Ch], 8
0x180015508  jz      loc_180015A21
0x18001550e  cmp     [rcx+19h], dil
0x180015512  jb      loc_180015A21
0x180015518  mov     edx, 0AFh
0x18001551d  jmp     loc_18001544B
0x180015522  mov     rcx, [rsp+160h+ppv]; struct IUnknown *
0x180015527  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x18001552c  mov     rcx, [rsp+160h+ppv]
0x180015531  lea     r8, [rsp+160h+var_110]
0x180015536  xor     edx, edx
0x180015538  mov     rax, [rcx]
0x18001553b  mov     rax, [rax+18h]
0x18001553f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015544  mov     ebx, eax
0x180015546  test    eax, eax
0x180015548  jns     short loc_18001557A
0x18001554a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015551  cmp     rcx, r12
0x180015554  jz      short loc_18001557A
0x180015556  test    byte ptr [rcx+1Ch], 8
0x18001555a  jz      short loc_18001557A
0x18001555c  cmp     [rcx+19h], dil
0x180015560  jb      short loc_18001557A
0x180015562  mov     rcx, [rcx+10h]
0x180015566  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001556d  mov     edx, 0B0h
0x180015572  mov     r9d, eax
0x180015575  call    WPP_SF_d
0x18001557a  mov     rcx, [rsp+160h+ppv]
0x18001557f  mov     rax, [rcx]
0x180015582  mov     rax, [rax+10h]
0x180015586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001558b  test    ebx, ebx
0x18001558d  js      loc_180015A21
0x180015593  mov     rcx, [rsp+160h+var_110]; struct IUnknown *
0x180015598  xor     r12d, r12d
0x18001559b  xor     r14d, r14d
0x18001559e  mov     [rsp+160h+var_130], r12d
0x1800155a3  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x1800155a8  mov     rcx, [rsp+160h+var_110]
0x1800155ad  lea     r9, [rsp+160h+var_130]
0x1800155b2  lea     r8, [rbp+60h+var_D0]
0x1800155b6  mov     edx, 10h
0x1800155bb  mov     rax, [rcx]
0x1800155be  mov     rax, [rax+18h]
0x1800155c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155c7  mov     r15d, eax
0x1800155ca  test    eax, eax
0x1800155cc  js      loc_180015911
0x1800155d2  mov     edx, [rsp+160h+var_130]
0x1800155d6  test    edx, edx
0x1800155d8  jz      loc_180015948
0x1800155de  add     edx, r12d
0x1800155e1  mov     rcx, r14; pv
0x1800155e4  shl     rdx, 3; cb
0x1800155e8  mov     rsi, r14
0x1800155eb  mov     r13, r14
0x1800155ee  call    cs:__imp_CoTaskMemRealloc
0x1800155f4  mov     r14, rax
0x1800155f7  test    rax, rax
0x1800155fa  jz      loc_180015870
0x180015600  mov     edx, [rsp+160h+var_130]
0x180015604  xor     r13d, r13d
0x180015607  test    edx, edx
0x180015609  jz      loc_1800158E1
0x18001560f  mov     rcx, [rbp+r13*8+60h+var_D0]; struct IUnknown *
0x180015614  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x180015619  mov     rcx, [rbp+r13*8+60h+var_D0]
0x18001561e  lea     rdx, [rsp+160h+pProps]
0x180015623  mov     [rsp+160h+pProps], 0
0x18001562c  mov     rax, [rcx]
0x18001562f  mov     rax, [rax+38h]
0x180015633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015638  mov     r15d, eax
0x18001563b  test    eax, eax
0x18001563d  jns     short loc_180015687
0x18001563f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015646  lea     rax, WPP_GLOBAL_Control
0x18001564d  cmp     rcx, rax
0x180015650  jz      loc_18001585E
0x180015656  test    byte ptr [rcx+1Ch], 8
0x18001565a  jz      loc_18001585E
0x180015660  cmp     [rcx+19h], dil
0x180015664  jb      loc_18001585E
0x18001566a  mov     edx, 0B2h
0x18001566f  mov     rcx, [rcx+10h]
0x180015673  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18001567a  mov     r9d, r15d
0x18001567d  call    WPP_SF_d
0x180015682  jmp     loc_18001585E
0x180015687  mov     rcx, [rsp+160h+pProps]; pProps
0x18001568c  test    rcx, rcx
0x18001568f  jz      short loc_1800156AE
0x180015691  cmp     dword ptr [rcx+24h], 8
0x180015695  jz      short loc_18001569F
0x180015697  xor     bl, bl
0x180015699  cmp     dword ptr [rcx+24h], 9
0x18001569d  jnz     short loc_1800156A1
0x18001569f  mov     bl, 1
0x1800156a1  call    NcFreeNetconProperties
0x1800156a6  test    bl, bl
0x1800156a8  jnz     loc_18001585E
0x1800156ae  mov     rcx, [rsp+160h+var_E8]
0x1800156b3  lea     rbx, [r14+r12*8]
0x1800156b7  mov     rdx, [rbp+r13*8+60h+var_D0]
0x1800156bc  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1800156c0  mov     r8, rbx
0x1800156c3  mov     rax, [rcx]
0x1800156c6  mov     rax, [rax+18h]
0x1800156ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156cf  xor     esi, esi
  ... truncated ...
```
