# FAXStartServerNotificationInternal

- ea: `0x14001186c`
- end: `0x1400120b0`
- name: `FAXStartServerNotificationInternal`
- size: `2116`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140021e10`
- `0x140021ec0`

## callees

- `0x140001b8c`
- `0x1400023cc`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004d44`
- `0x14001186c`
- `0x1400252a8`
- `0x14002ce80`
- `0x1400452ac`
- `0x140045798`
- `0x14004eb7c`
- `0x1400540a4`
- `0x140054234`
- `0x140054340`
- `0x1400545fc`
- `0x140054c28`
- `0x1400579c8`
- `0x140065dbc`
- `0x140074e28`
- `0x140074f30`
- `0x140075efc`
- `0x14008187e`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140011bfc`
- `KERNEL32!GetLastError` at `0x140011f03`
- `KERNEL32!GetLastError` at `0x140011bfc`
- `KERNEL32!GetLastError` at `0x140011f03`
- `KERNEL32!EnterCriticalSection` at `0x140011ca3`
- `KERNEL32!EnterCriticalSection` at `0x140011ca3`
- `KERNEL32!LeaveCriticalSection` at `0x14001202d`
- `KERNEL32!LeaveCriticalSection` at `0x14001202d`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140011ef9`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140011ef9`
- `RPCRT4!RpcBindingFree` at `0x140011faf`
- `RPCRT4!RpcBindingFree` at `0x140011faf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall FAXStartServerNotificationInternal(
        void *a1,
        wchar_t *a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        struct _OVERLAPPED *a5,
        wchar_t *String1,
        int a7,
        int a8,
        unsigned int a9,
        unsigned __int16 **a10)
{
  __int64 result; // rax
  unsigned int v14; // eax
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  CMapDeviceId *v17; // rcx
  __int64 v18; // rdx
  CMapDeviceId *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // edi
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  wchar_t *v25; // rdi
  void *ClientUserSID; // rax
  DWORD LastError; // eax
  struct _OVERLAPPED *v28; // r13
  int v29; // eax
  unsigned int v30; // eax
  unsigned __int16 *v31; // r12
  CMapDeviceId *v32; // rcx
  __int64 v33; // rdx
  void *v34; // rax
  __int64 v35; // rdx
  RPC_WSTR v36; // rdi
  CMapDeviceId *v37; // rcx
  __int64 v38; // rdx
  void *v39; // rax
  __int64 v40; // rdx
  CClientID *v41; // rax
  CClientsMap *v42; // rcx
  unsigned int v43; // eax
  DWORD v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // [rsp+50h] [rbp-1A8h] BYREF
  unsigned int v47; // [rsp+54h] [rbp-1A4h]
  LPVOID lpMem; // [rsp+58h] [rbp-1A0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-198h] BYREF
  RPC_WSTR Endpoint; // [rsp+68h] [rbp-190h]
  struct _OVERLAPPED *v51; // [rsp+70h] [rbp-188h]
  wchar_t *String2; // [rsp+78h] [rbp-180h]
  void *v53; // [rsp+80h] [rbp-178h]
  unsigned __int16 **v54; // [rsp+88h] [rbp-170h]
  void *v55; // [rsp+90h] [rbp-168h]
  char v56[80]; // [rsp+A0h] [rbp-158h] BYREF
  _BYTE v57[192]; // [rsp+F0h] [rbp-108h] BYREF

  Endpoint = a4;
  String2 = a3;
  v53 = a1;
  v51 = a5;
  v47 = a9;
  v54 = a10;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 542, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  Binding = 0;
  v46 = 0;
  LODWORD(lpMem) = 0;
  result = FaxSvcAccessCheck(0x2000000u, (int *)&lpMem, &v46, 1);
  if ( (_DWORD)result )
    return result;
  v14 = v46;
  if ( (v46 & 0xE03FF) == 0 )
    return 5;
  if ( !a4 || !a3 || !v54 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 87;
    }
    v16 = 543;
LABEL_148:
    WPP_SF_(*((_QWORD *)v15 + 2), v16, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 87;
  }
  if ( v47 > 1 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 544, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v47);
    }
    return 87;
  }
  if ( a7 )
  {
    if ( (a8 & 0x3FF) == 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 87;
      }
      v16 = 545;
      goto LABEL_148;
    }
    if ( (a8 & 0xFFFFFC00) != 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 87;
      }
      v16 = 546;
      goto LABEL_148;
    }
  }
  if ( a2 )
  {
    if ( !(unsigned int)ValidFaxAccountName(a2) )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 87;
      }
      v18 = 548;
      goto LABEL_84;
    }
    v14 = v46;
  }
  if ( a7 != 1 )
  {
    LODWORD(lpMem) = 0;
    if ( a8 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 5;
      }
      v20 = 551;
    }
    else
    {
      v21 = IsLocalRPCConnectionNP(&lpMem);
      v22 = v21;
      if ( v21 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 552, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v21);
        }
        return v22;
      }
      if ( (_DWORD)lpMem )
        goto LABEL_65;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 5;
      }
      v20 = 553;
    }
LABEL_51:
    WPP_SF_(*((_QWORD *)v19 + 2), v20, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 5;
  }
  if ( (a8 & 0x201) != 0 && !(unsigned int)CanAccessUnAssignedFaxes(v14, 1) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 5;
    }
    v20 = 549;
    goto LABEL_51;
  }
  if ( (a8 & 0x10C) != 0 && (v46 & 0x20) == 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 5;
    }
    v20 = 550;
    goto LABEL_51;
  }
LABEL_65:
  v23 = -1;
  v24 = -1;
  v25 = String2;
  do
    ++v24;
  while ( String2[v24] );
  if ( v24 <= 0xF )
  {
    do
      ++v23;
    while ( a4[v23] );
    if ( v23 < 0xB )
    {
      ClientUserSID = GetClientUserSID();
      lpMem = ClientUserSID;
      if ( !ClientUserSID )
      {
        LastError = GetLastError();
        v22 = LastError;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            555,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            LastError);
        }
LABEL_75:
        if ( v22 == 8 || v22 == 14 )
          return 7001;
        return v22;
      }
      if ( a2 && !(unsigned int)SameNTUser(a2, ClientUserSID) )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 87;
        }
        v18 = 556;
LABEL_84:
        WPP_SF_S(*((_QWORD *)v17 + 2), v18, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a2);
        return 87;
      }
      v28 = 0;
      EnterCriticalSection(&g_CsClients);
      v29 = wcsncmp_0(String1, L"ncalrpc", 7u);
      v30 = RpcBindToFaxClient(v25, Endpoint, v29 == 0, &Binding);
      v22 = v30;
      if ( v30 )
      {
        v31 = 0;
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_126;
        }
        v33 = 557;
        goto LABEL_90;
      }
      v34 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v55 = v34;
      v36 = Endpoint;
      if ( v34 )
        v31 = (unsigned __int16 *)CClientID::CClientID(v34, v35, String2, Endpoint, v51);
      else
        v31 = 0;
      Endpoint = v31;
      if ( v31 )
      {
        v39 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
        v55 = v39;
        if ( v39 )
          v28 = (struct _OVERLAPPED *)CClientID::CClientID(v39, v40, String2, v36, v51);
        else
          v28 = 0;
        v51 = v28;
        if ( v28 )
        {
          FindClientAPIVersion(v53);
          v53 = Binding;
          v41 = CClientID::CClientID((CClientID *)v56, (const struct CClientID *)v31);
          CClient::CClient(v57, v41, lpMem);
          v43 = CClientsMap::AddClient(v42, (const struct CClient *)v57);
          v22 = v43;
          if ( v43 )
          {
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 560, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v43);
            }
            CClient::~CClient((CClient *)v57);
            goto LABEL_126;
          }
          Binding = 0;
          CClient::~CClient((CClient *)v57);
          if ( !PostQueuedCompletionStatus(g_hSendEventsCompPort, 8u, 3u, v28) )
          {
            v44 = GetLastError();
            v22 = v44;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 562, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v44);
            }
            v30 = CClientsMap::ReleaseClient(g_pClientsMap, (const struct CClientID *)v31, 0);
            if ( !v30 )
              goto LABEL_126;
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_126;
            }
            v33 = 563;
LABEL_90:
            WPP_SF_d(*((_QWORD *)v32 + 2), v33, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v30);
            goto LABEL_126;
          }
          v28 = 0;
          *v54 = v31;
          v31 = 0;
LABEL_126:
          if ( Binding )
          {
            v45 = RpcBindingFree(&Binding);
            if ( v45 )
            {
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  564,
                  &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                  v45);
              }
            }
          }
          if ( v31 )
          {
            memset_0(v31, 0, 0x50u);
            operator delete(v31);
          }
          if ( v28 )
          {
            memset_0(v28, 0, 0x50u);
            operator delete(v28);
          }
          if ( !v22 )
            ++g_dwlClientID;
          LeaveCriticalSection(&g_CsClients);
          pMemFree(lpMem);
          goto LABEL_75;
        }
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_100:
          v22 = 14;
          goto LABEL_126;
        }
        v38 = 559;
      }
      else
      {
        v37 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_100;
        }
        v38 = 558;
      }
      WPP_SF_(*((_QWORD *)v37 + 2), v38, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      goto LABEL_100;
    }
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      554,
      (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
      (_DWORD)String2,
      (__int64)a4);
  }
  return 11;
}

```

## disassembly

```asm
0x14001186c  push    rbx
0x14001186e  push    rsi
0x14001186f  push    rdi
0x140011870  push    r12
0x140011872  push    r13
0x140011874  push    r14
0x140011876  push    r15
0x140011878  sub     rsp, 1C0h
0x14001187f  mov     rax, cs:__security_cookie
0x140011886  xor     rax, rsp
0x140011889  mov     [rsp+1F8h+var_48], rax
0x140011891  mov     r13, r9
0x140011894  mov     [rsp+1F8h+Endpoint], r9
0x140011899  mov     rdi, r8
0x14001189c  mov     [rsp+1F8h+String2], r8
0x1400118a1  mov     r12, rdx
0x1400118a4  mov     [rsp+1F8h+var_178], rcx
0x1400118ac  mov     rax, [rsp+1F8h+arg_20]
0x1400118b4  mov     [rsp+1F8h+var_188], rax
0x1400118b9  mov     eax, [rsp+1F8h+arg_40]
0x1400118c0  mov     [rsp+1F8h+var_1A4], eax
0x1400118c4  mov     rax, [rsp+1F8h+arg_48]
0x1400118cc  mov     [rsp+1F8h+var_170], rax
0x1400118d4  lea     r15, WPP_GLOBAL_Control
0x1400118db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118e2  mov     sil, 4
0x1400118e5  cmp     rcx, r15
0x1400118e8  jz      short loc_140011910
0x1400118ea  test    [rcx+1Ch], sil
0x1400118ee  jz      short loc_140011910
0x1400118f0  lea     r14, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400118f7  cmp     byte ptr [rcx+19h], 5
0x1400118fb  jb      short loc_140011917
0x1400118fd  mov     edx, 21Eh
0x140011902  mov     r8, r14
0x140011905  mov     rcx, [rcx+10h]
0x140011909  call    WPP_SF_
0x14001190e  jmp     short loc_140011917
0x140011910  lea     r14, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140011917  xor     ebx, ebx
0x140011919  mov     [rsp+1F8h+Binding], rbx
0x14001191e  mov     [rsp+1F8h+var_1A8], ebx
0x140011922  mov     dword ptr [rsp+1F8h+lpMem], ebx
0x140011926  lea     r9d, [rbx+1]; int
0x14001192a  lea     r8, [rsp+1F8h+var_1A8]; unsigned int *
0x14001192f  lea     rdx, [rsp+1F8h+lpMem]; int *
0x140011934  mov     ecx, 2000000h; unsigned int
0x140011939  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001193e  test    eax, eax
0x140011940  jnz     loc_140011B2A
0x140011946  mov     eax, [rsp+1F8h+var_1A8]
0x14001194a  test    eax, 0E03FFh
0x14001194f  jz      loc_140011B25
0x140011955  test    r13, r13
0x140011958  jz      loc_14001207D
0x14001195e  test    rdi, rdi
0x140011961  jz      loc_14001207D
0x140011967  cmp     [rsp+1F8h+var_170], rbx
0x14001196f  jz      loc_14001207D
0x140011975  mov     r8d, [rsp+1F8h+var_1A4]
0x14001197a  cmp     r8d, 1
0x14001197e  jbe     short loc_1400119BD
0x140011980  mov     rcx, cs:WPP_GLOBAL_Control
0x140011987  cmp     rcx, r15
0x14001198a  jz      loc_1400120A6
0x140011990  test    [rcx+1Ch], sil
0x140011994  jz      loc_1400120A6
0x14001199a  cmp     byte ptr [rcx+19h], 2
0x14001199e  jb      loc_1400120A6
0x1400119a4  mov     edx, 220h
0x1400119a9  mov     r9d, r8d
0x1400119ac  mov     r8, r14
0x1400119af  mov     rcx, [rcx+10h]
0x1400119b3  call    WPP_SF_d
0x1400119b8  jmp     loc_1400120A6
0x1400119bd  mov     edi, [rsp+1F8h+arg_38]
0x1400119c4  cmp     [rsp+1F8h+arg_30], ebx
0x1400119cb  jz      short loc_140011A39
0x1400119cd  test    edi, 3FFh
0x1400119d3  jnz     short loc_140011A03
0x1400119d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400119dc  cmp     rcx, r15
0x1400119df  jz      loc_1400120A6
0x1400119e5  test    [rcx+1Ch], sil
0x1400119e9  jz      loc_1400120A6
0x1400119ef  cmp     byte ptr [rcx+19h], 2
0x1400119f3  jb      loc_1400120A6
0x1400119f9  mov     edx, 221h
0x1400119fe  jmp     loc_14001209A
0x140011a03  test    edi, 0FFFFFC00h
0x140011a09  jz      short loc_140011A39
0x140011a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a12  cmp     rcx, r15
0x140011a15  jz      loc_1400120A6
0x140011a1b  test    [rcx+1Ch], sil
0x140011a1f  jz      loc_1400120A6
0x140011a25  cmp     byte ptr [rcx+19h], 2
0x140011a29  jb      loc_1400120A6
0x140011a2f  mov     edx, 222h
0x140011a34  jmp     loc_14001209A
0x140011a39  test    r12, r12
0x140011a3c  jz      short loc_140011A7C
0x140011a3e  mov     rcx, r12; Str
0x140011a41  call    ValidFaxAccountName
0x140011a46  test    eax, eax
0x140011a48  jnz     short loc_140011A78
0x140011a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a51  cmp     rcx, r15
0x140011a54  jz      loc_1400120A6
0x140011a5a  test    [rcx+1Ch], sil
0x140011a5e  jz      loc_1400120A6
0x140011a64  cmp     byte ptr [rcx+19h], 2
0x140011a68  jb      loc_1400120A6
0x140011a6e  mov     edx, 224h
0x140011a73  jmp     loc_140011C85
0x140011a78  mov     eax, [rsp+1F8h+var_1A8]
0x140011a7c  cmp     [rsp+1F8h+arg_30], 1
0x140011a84  jnz     short loc_140011AF4
0x140011a86  test    edi, 201h
0x140011a8c  jz      short loc_140011ABD
0x140011a8e  mov     edx, 1; int
0x140011a93  mov     ecx, eax; unsigned int
0x140011a95  call    ?CanAccessUnAssignedFaxes@@YAHKH@Z; CanAccessUnAssignedFaxes(ulong,int)
0x140011a9a  test    eax, eax
0x140011a9c  jnz     short loc_140011ABD
0x140011a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011aa5  cmp     rcx, r15
0x140011aa8  jz      short loc_140011B25
0x140011aaa  test    [rcx+1Ch], sil
0x140011aae  jz      short loc_140011B25
0x140011ab0  cmp     byte ptr [rcx+19h], 2
0x140011ab4  jb      short loc_140011B25
0x140011ab6  mov     edx, 225h
0x140011abb  jmp     short loc_140011B19
0x140011abd  test    edi, 10Ch
0x140011ac3  jz      loc_140011BB9
0x140011ac9  mov     eax, [rsp+1F8h+var_1A8]
0x140011acd  test    al, 20h
0x140011acf  jnz     loc_140011BB9
0x140011ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x140011adc  cmp     rcx, r15
0x140011adf  jz      short loc_140011B25
0x140011ae1  test    [rcx+1Ch], sil
0x140011ae5  jz      short loc_140011B25
0x140011ae7  cmp     byte ptr [rcx+19h], 2
0x140011aeb  jb      short loc_140011B25
0x140011aed  mov     edx, 226h
0x140011af2  jmp     short loc_140011B19
0x140011af4  mov     dword ptr [rsp+1F8h+lpMem], ebx
0x140011af8  test    edi, edi
0x140011afa  jz      short loc_140011B4D
0x140011afc  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b03  cmp     rcx, r15
0x140011b06  jz      short loc_140011B25
0x140011b08  test    [rcx+1Ch], sil
0x140011b0c  jz      short loc_140011B25
0x140011b0e  cmp     byte ptr [rcx+19h], 2
0x140011b12  jb      short loc_140011B25
0x140011b14  mov     edx, 227h
0x140011b19  mov     r8, r14
0x140011b1c  mov     rcx, [rcx+10h]
0x140011b20  call    WPP_SF_
0x140011b25  mov     eax, 5
0x140011b2a  mov     rcx, [rsp+1F8h+var_48]
0x140011b32  xor     rcx, rsp; StackCookie
0x140011b35  call    __security_check_cookie
0x140011b3a  add     rsp, 1C0h
0x140011b41  pop     r15
0x140011b43  pop     r14
0x140011b45  pop     r13
0x140011b47  pop     r12
0x140011b49  pop     rdi
0x140011b4a  pop     rsi
0x140011b4b  pop     rbx
0x140011b4c  retn
0x140011b4d  lea     rcx, [rsp+1F8h+lpMem]
0x140011b52  call    IsLocalRPCConnectionNP
0x140011b57  mov     edi, eax
0x140011b59  test    eax, eax
0x140011b5b  jz      short loc_140011B8D
0x140011b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b64  cmp     rcx, r15
0x140011b67  jz      short loc_140011B89
0x140011b69  test    [rcx+1Ch], sil
0x140011b6d  jz      short loc_140011B89
0x140011b6f  cmp     byte ptr [rcx+19h], 2
0x140011b73  jb      short loc_140011B89
0x140011b75  mov     edx, 228h
0x140011b7a  mov     r9d, eax
0x140011b7d  mov     r8, r14
0x140011b80  mov     rcx, [rcx+10h]
0x140011b84  call    WPP_SF_d
0x140011b89  mov     eax, edi
0x140011b8b  jmp     short loc_140011B2A
0x140011b8d  cmp     dword ptr [rsp+1F8h+lpMem], ebx
0x140011b91  jnz     short loc_140011BB9
0x140011b93  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b9a  cmp     rcx, r15
0x140011b9d  jz      short loc_140011B25
0x140011b9f  test    [rcx+1Ch], sil
0x140011ba3  jz      short loc_140011B25
0x140011ba5  cmp     byte ptr [rcx+19h], 2
0x140011ba9  jb      loc_140011B25
0x140011baf  mov     edx, 229h
0x140011bb4  jmp     loc_140011B19
0x140011bb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011bbd  mov     rcx, rax
0x140011bc0  mov     rdi, [rsp+1F8h+String2]
0x140011bc5  inc     rcx
0x140011bc8  cmp     [rdi+rcx*2], bx
0x140011bcc  jnz     short loc_140011BC5
0x140011bce  cmp     rcx, 0Fh
0x140011bd2  ja      loc_140012042
0x140011bd8  inc     rax
0x140011bdb  cmp     [r13+rax*2+0], bx
0x140011be1  jnz     short loc_140011BD8
0x140011be3  cmp     rax, 0Bh
0x140011be7  jnb     loc_140012042
0x140011bed  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x140011bf2  mov     [rsp+1F8h+lpMem], rax
0x140011bf7  test    rax, rax
0x140011bfa  jnz     short loc_140011C48
0x140011bfc  call    cs:__imp_GetLastError
0x140011c02  mov     edi, eax
0x140011c04  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c0b  cmp     rcx, r15
0x140011c0e  jz      short loc_140011C30
0x140011c10  test    [rcx+1Ch], sil
0x140011c14  jz      short loc_140011C30
0x140011c16  cmp     byte ptr [rcx+19h], 2
0x140011c1a  jb      short loc_140011C30
0x140011c1c  mov     edx, 22Bh
0x140011c21  mov     r9d, eax
0x140011c24  mov     r8, r14
0x140011c27  mov     rcx, [rcx+10h]
0x140011c2b  call    WPP_SF_d
0x140011c30  cmp     edi, 8
0x140011c33  jz      short loc_140011C3E
0x140011c35  cmp     edi, 0Eh
0x140011c38  jnz     loc_140011B89
0x140011c3e  mov     edi, 1B59h
0x140011c43  jmp     loc_140011B89
0x140011c48  test    r12, r12
0x140011c4b  jz      short loc_140011C99
0x140011c4d  mov     rdx, rax; Sid
0x140011c50  mov     rcx, r12; String2
0x140011c53  call    SameNTUser
0x140011c58  test    eax, eax
0x140011c5a  jnz     short loc_140011C99
0x140011c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c63  cmp     rcx, r15
0x140011c66  jz      loc_1400120A6
0x140011c6c  test    [rcx+1Ch], sil
0x140011c70  jz      loc_1400120A6
0x140011c76  cmp     byte ptr [rcx+19h], 2
0x140011c7a  jb      loc_1400120A6
0x140011c80  mov     edx, 22Ch
0x140011c85  mov     r9, r12
0x140011c88  mov     r8, r14
0x140011c8b  mov     rcx, [rcx+10h]
0x140011c8f  call    WPP_SF_S
0x140011c94  jmp     loc_1400120A6
0x140011c99  mov     r13, rbx
0x140011c9c  lea     rcx, ?g_CsClients@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140011ca3  call    cs:__imp_EnterCriticalSection
0x140011ca9  mov     r8d, 7; MaxCount
0x140011caf  lea     rdx, aNcalrpc; "ncalrpc"
0x140011cb6  mov     rcx, [rsp+1F8h+String1]; String1
0x140011cbe  call    wcsncmp_0
0x140011cc3  mov     r8d, ebx
0x140011cc6  test    eax, eax
0x140011cc8  setz    r8b; AuthzSvc
0x140011ccc  lea     r9, [rsp+1F8h+Binding]; Binding
0x140011cd1  mov     rdx, [rsp+1F8h+Endpoint]; Endpoint
0x140011cd6  mov     rcx, rdi; String2
0x140011cd9  call    ?RpcBindToFaxClient@@YAKPEBG0HPEAPEAX@Z; RpcBindToFaxClient(ushort const *,ushort const *,int,void * *)
0x140011cde  mov     edi, eax
0x140011ce0  test    eax, eax
0x140011ce2  jz      short loc_140011D24
0x140011ce4  mov     r12, rbx
0x140011ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cee  cmp     rcx, r15
0x140011cf1  jz      loc_140011FA3
0x140011cf7  test    [rcx+1Ch], sil
0x140011cfb  jz      loc_140011FA3
0x140011d01  cmp     byte ptr [rcx+19h], 2
0x140011d05  jb      loc_140011FA3
0x140011d0b  mov     edx, 22Dh
0x140011d10  mov     r9d, eax
0x140011d13  mov     r8, r14
0x140011d16  mov     rcx, [rcx+10h]
0x140011d1a  call    WPP_SF_d
0x140011d1f  jmp     loc_140011FA3
0x140011d24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011d2b  mov     ecx, 50h ; 'P'; unsigned __int64
0x140011d30  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011d35  mov     [rsp+1F8h+var_168], rax
0x140011d3d  mov     rdi, [rsp+1F8h+Endpoint]
0x140011d42  test    rax, rax
0x140011d45  jz      short loc_140011D66
  ... truncated ...
```
