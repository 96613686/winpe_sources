# RasDialFunc2

- ea: `0x180087230`
- end: `0x180088cca`
- name: `RasDialFunc2`
- size: `6810`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParameter@<rcx>, int, int, int)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18006f7f0`
- `0x1800769b0`
- `0x18007e5f0`
- `0x18007efdc`
- `0x18007f18c`
- `0x180084d10`
- `0x180085184`
- `0x1800859c4`
- `0x180085aec`
- `0x180085c1c`
- `0x18008665c`
- `0x180087230`
- `0x180089eac`
- `0x18008d31c`
- `0x18008d66c`
- `0x18008ec1c`
- `0x18008efc0`
- `0x18008f0fc`
- `0x18008f888`
- `0x18008fb30`
- `0x180091300`
- `0x1800a749c`
- `0x1800af5b4`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800876a0`
- `msvcrt!wcscpy_s` at `0x1800878c6`
- `msvcrt!wcscpy_s` at `0x1800878df`
- `msvcrt!wcscpy_s` at `0x1800878f8`
- `msvcrt!wcscpy_s` at `0x1800876a0`
- `msvcrt!wcscpy_s` at `0x1800878c6`
- `msvcrt!wcscpy_s` at `0x1800878df`
- `msvcrt!wcscpy_s` at `0x1800878f8`
- `msvcrt!memcpy_s` at `0x180088a82`
- `msvcrt!memcpy_s` at `0x180088a82`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180087bc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180087c2a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180087bc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180087c2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180087d00`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180087d00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180087ce7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180087ce7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087643`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087841`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087643`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180087841`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800879ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800879be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800879ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800879be`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180087d6c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180087d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087c3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180087db2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800872ff`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18008739b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800883ea`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800872ff`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18008739b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800883ea`
- `WS2_32!__imp_WSAStartup` at `0x180087f3e`
- `WS2_32!__imp_WSAStartup` at `0x180087f3e`

## pseudocode

```c
__int64 __fastcall RasDialFunc2(
        char *lpParameter,
        __int64 a2,
        HRASCONN a3,
        int a4,
        int a5,
        unsigned int a6,
        unsigned int a7)
{
  HRASCONN v7; // r15
  int v8; // edi
  unsigned int v10; // r12d
  int v11; // r14d
  __int64 v12; // r13
  _QWORD *v13; // rcx
  DWORD v14; // esi
  __int64 v15; // r9
  DWORD v16; // eax
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  int v19; // r12d
  BOOL v20; // r15d
  int v21; // esi
  wchar_t *v22; // r14
  unsigned int ConnectionErrorStringW; // eax
  wchar_t *v24; // rdi
  __int64 v25; // rax
  rsize_t v26; // rsi
  wchar_t *v27; // rax
  DWORD LastError; // eax
  HRASCONN v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned int v32; // eax
  unsigned int v33; // r13d
  unsigned int v34; // esi
  char *v35; // rax
  wchar_t *v36; // rdi
  DWORD v37; // eax
  unsigned int v38; // eax
  __int64 v39; // rcx
  const wchar_t *v40; // r9
  unsigned int v41; // eax
  _QWORD *v42; // rcx
  HANDLE EventW; // rax
  HANDLE v44; // rax
  DWORD v45; // eax
  HANDLE CurrentThread; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int64 v50; // r9
  unsigned int v51; // eax
  unsigned int v52; // edi
  int v53; // eax
  unsigned int v54; // eax
  _QWORD *v55; // rcx
  int v56; // r13d
  unsigned int v57; // eax
  unsigned int CredentialsFromVan; // edi
  _QWORD *v59; // rcx
  __int64 v60; // rdx
  unsigned int v61; // eax
  int v63; // edx
  __int64 (__fastcall *v64)(HRASCONN, _QWORD, _QWORD); // rax
  unsigned int v65; // eax
  __int64 v66; // rdx
  bool v67; // zf
  __int64 (__fastcall *v68)(HRASCONN, _QWORD, _QWORD); // rax
  unsigned int v69; // eax
  int v70; // r13d
  unsigned int ThirdPartyAuthData; // edi
  _QWORD *v72; // rcx
  __int64 v73; // rdx
  int v74; // r9d
  unsigned int v75; // edi
  _QWORD *v76; // rcx
  __int64 v77; // rdx
  int v78; // [rsp+50h] [rbp-B0h]
  _DWORD SizeInWords[3]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v80; // [rsp+60h] [rbp-A0h]
  wchar_t *Source; // [rsp+68h] [rbp-98h] BYREF
  char *v82; // [rsp+70h] [rbp-90h] BYREF
  GUID v83; // [rsp+78h] [rbp-88h] BYREF
  GUID ActivityId; // [rsp+88h] [rbp-78h] BYREF
  WSAData WSAData; // [rsp+A0h] [rbp-60h] BYREF

  v7 = a3;
  *(_QWORD *)&SizeInWords[1] = a3;
  v8 = a2;
  v78 = a2;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
  {
    v10 = a6;
    v11 = a5;
  }
  else
  {
    v10 = a6;
    v11 = a5;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      WPP_SF_dqddDD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, a3, a4, a5, a6, a7);
  }
  v82 = lpParameter;
  SizeInWords[0] = 1;
  v83 = 0;
  ActivityId = 0;
  EventActivityIdControl(1u, &ActivityId);
  v12 = ValidateHrasconn(v7);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      712,
      WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
      (unsigned int)v11);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v10 != 668 && lpParameter && *((_DWORD *)lpParameter + 2639) == -777928482 )
  {
    v14 = 0;
    if ( v12 )
      v83 = *(GUID *)(v12 + 5540);
    EventActivityIdControl(2u, &v83);
    if ( (unsigned int)(v11 - 4099) <= 1 || v11 == 4097 || v11 == 0x2000 )
    {
      if ( *((_QWORD *)lpParameter + 1302) )
      {
        v8 = v78;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 715, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        }
        v16 = ((__int64 (__fastcall *)(HRASCONN, char *))g_pRasGetHportFromConnection)(v7, lpParameter + 10416);
        v14 = v16;
        if ( v16 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 716, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v16);
          }
          *(_QWORD *)(v12 + 5624) = 0;
          RasHangUpW(v7);
          v17 = WPP_GLOBAL_Control;
          SizeInWords[0] = 0;
          goto LABEL_293;
        }
        v8 = v78;
      }
    }
    if ( v10 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 717, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v10);
        v18 = WPP_GLOBAL_Control;
      }
      if ( v12 )
        v19 = *(_DWORD *)(v12 + 4868);
      else
        v19 = 0;
      v80 = a6;
      v20 = v19 == 0;
      SizeInWords[0] = 0;
      v21 = 0;
      v22 = 0;
      if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x800) != 0 && *((_BYTE *)v18 + 25) >= 2u )
      {
        WPP_SF_d(v18[2], 718, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, a6);
        v18 = WPP_GLOBAL_Control;
      }
      if ( (*((_DWORD *)lpParameter + 1932) & 0x8000000) != 0 )
      {
        if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x800) != 0 && *((_BYTE *)v18 + 25) >= 5u )
          WPP_SF_(v18[2], 719, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        Source = 0;
        ConnectionErrorStringW = RasGetConnectionErrorStringW(*(_QWORD *)&SizeInWords[1], &Source);
        if ( ConnectionErrorStringW )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              720,
              WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
              ConnectionErrorStringW);
          }
        }
        else
        {
          v24 = Source;
          if ( Source )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                721,
                WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                Source);
            }
            v25 = -1;
            do
              ++v25;
            while ( v24[v25] );
            SizeInWords[0] = v25 + 1;
            v26 = (unsigned int)(v25 + 1);
            v27 = (wchar_t *)LocalAlloc(0x40u, 2 * v26);
            v22 = v27;
            if ( v27 )
            {
              wcscpy_s(v27, v26, v24);
            }
            else
            {
              LastError = GetLastError();
              if ( LastError
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  722,
                  WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                  LastError);
              }
            }
            v21 = SizeInWords[0];
          }
        }
      }
      v29 = *(HRASCONN *)&SizeInWords[1];
      *(_QWORD *)(v12 + 5624) = 0;
      RasHangUpW(v29);
      if ( !*((_QWORD *)lpParameter + 1335) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 723, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
        }
        v32 = OpenVanActionRequiredEvent(lpParameter, 2031619, v30, lpParameter + 10680);
        if ( v32 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_79:
            if ( v19 && *((_QWORD *)lpParameter + 1335) )
            {
              v20 = 1;
              v33 = 1223;
              if ( v17 == &WPP_GLOBAL_Control )
                goto LABEL_90;
              if ( (*((_DWORD *)v17 + 7) & 0x800) != 0 && *((_BYTE *)v17 + 25) >= 5u )
              {
                WPP_SF_(v17[2], 725, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
                v17 = WPP_GLOBAL_Control;
              }
            }
            else
            {
              v33 = v80;
            }
            if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x800) != 0 && *((_BYTE *)v17 + 25) >= 5u )
            {
              LOBYTE(v31) = v20;
              WPP_SF_cD(v17[2], &WPP_GLOBAL_Control, v30, v31, v33);
              v17 = WPP_GLOBAL_Control;
            }
LABEL_90:
            if ( *((_DWORD *)lpParameter + 2640) == 1223 || !v20 )
            {
              if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x800) != 0 && *((_BYTE *)v17 + 25) >= 5u )
              {
                v39 = v17[2];
                v40 = L"TRUE";
                if ( !v19 )
                  v40 = L"FALSE";
                WPP_SF_S(v39, 731, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v40);
                v17 = WPP_GLOBAL_Control;
              }
              v14 = 0;
              if ( !*((_QWORD *)lpParameter + 1336) )
                goto LABEL_123;
              if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x800) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                WPP_SF_(v17[2], 732, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
              v41 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))lpParameter + 1336))(
                      *(_QWORD *)&SizeInWords[1],
                      0,
                      0);
              if ( v41 )
              {
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_123;
                }
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 733, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v41);
              }
            }
            else
            {
              if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x800) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                WPP_SF_(v17[2], 727, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
              v34 = 2 * v21 + 1060;
              v35 = (char *)LocalAlloc(0x40u, v34);
              v36 = (wchar_t *)v35;
              if ( v35 )
              {
                *(_DWORD *)v35 = v34;
                *(_OWORD *)(v35 + 4) = *(_OWORD *)(lpParameter + 7188);
                wcscpy_s((wchar_t *)v35 + 10, 0x105u, (const wchar_t *)lpParameter + 409);
                wcscpy_s(v36 + 271, 0x101u, (const wchar_t *)lpParameter + 152);
                if ( v22 )
                  wcscpy_s(v36 + 528, SizeInWords[0], v22);
                LogRasDialEvent(8, 0, lpParameter);
                v38 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD))g_pRasSignalActionRequired)(0, 3, v33);
                if ( v38
                  && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    729,
                    WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                    v38);
                }
                UpdateUIStatus((int)lpParameter, v78, SizeInWords[1], a5, v33, v22);
              }
              else
              {
                v37 = GetLastError();
                if ( v37
                  && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    728,
                    WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                    v37);
                }
              }
              SignalVanActionRequiredEvent(lpParameter, 0);
              if ( v36 )
                LocalFree(v36);
              if ( v22 )
                LocalFree(v22);
              if ( *((_DWORD *)lpParameter + 1794) == 2 && a7 == 703 )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 730, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
                }
                RasShowToastNotification((unsigned __int16 *)lpParameter + 152);
              }
              v14 = a6;
            }
            v17 = WPP_GLOBAL_Control;
LABEL_123:
            v7 = *(HRASCONN *)&SizeInWords[1];
            SizeInWords[0] = 0;
            goto LABEL_292;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 724, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v32);
        }
      }
      v17 = WPP_GLOBAL_Control;
      goto LABEL_79;
    }
    if ( !v11 && v12 && !*(_DWORD *)(v12 + 5644) )
      LaunchTokenBroker(lpParameter);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      LOBYTE(v15) = *((_DWORD *)lpParameter + 2650) != 0;
      WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 734, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v15);
      v42 = WPP_GLOBAL_Control;
    }
    if ( !*((_QWORD *)lpParameter + 1331)
      && (((v11 - 4097) & 0xFFFFFFFC) == 0 && v11 != 4098 || !v11 && *((_DWORD *)lpParameter + 2650)) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)lpParameter + 1331) = EventW;
      if ( !EventW )
      {
        v14 = GetLastError();
        if ( v14 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 735, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v14);
          }
        }
      }
      v44 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)lpParameter + 1332) = v44;
      if ( v44 )
      {
        if ( v14 )
        {
LABEL_166:
          HangUpAndCleanAutoTriggerContext((int)lpParameter, v8, (int)v7, v11, v14, (wchar_t *)SizeInWords);
LABEL_167:
          v17 = WPP_GLOBAL_Control;
          goto LABEL_293;
        }
      }
      else
      {
        v45 = GetLastError();
        v14 = v45;
        if ( v45 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 736, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v45);
          }
          goto LABEL_166;
        }
      }
      v42 = WPP_GLOBAL_Control;
    }
    if ( !*((_QWORD *)lpParameter + 1330) && *((_DWORD *)lpParameter + 2644) )
    {
      *(_QWORD *)&SizeInWords[1] = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 2u, 1, (PHANDLE)&SizeInWords[1]) )
      {
        v14 = GetLastError();
        if ( !v14 )
        {
LABEL_179:
          v17 = WPP_GLOBAL_Control;
LABEL_180:
          SizeInWords[0] = 0;
          goto LABEL_292;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_180;
        }
        v47 = 737;
LABEL_178:
        WPP_SF_d(v17[2], v47, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v14);
        goto LABEL_179;
      }
      if ( !DuplicateToken(*(HANDLE *)&SizeInWords[1], SecurityImpersonation, (PHANDLE)lpParameter + 1330) )
      {
        v14 = GetLastError();
        if ( !v14 )
          goto LABEL_179;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_180;
        }
        v47 = 738;
        goto LABEL_178;
      }
      CloseHandle(*(HANDLE *)&SizeInWords[1]);
      v42 = WPP_GLOBAL_Control;
    }
    v14 = 0;
    v48 = 2048;
    if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
    {
      WPP_SF_d(v42[2], 739, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, (unsigned int)v11);
      v42 = WPP_GLOBAL_Control;
      v48 = 2048;
    }
    if ( v11 <= 4096 )
    {
      if ( v11 == 4096 )
        goto LABEL_204;
      if ( v11 <= 12 )
      {
        if ( v11 == 12 )
          goto LABEL_337;
        if ( v11 <= 6 )
        {
          if ( v11 == 6 )
          {
            if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
              WPP_SF_(v42[2], 756, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            v50 = 6;
            goto LABEL_214;
          }
          if ( v11 )
          {
            if ( v11 == 1 || v11 == 2 || v11 == 3 || v11 == 4 )
            {
              if ( v42 == &WPP_GLOBAL_Control || (*((_DWORD *)v42 + 7) & 0x800) == 0 || *((_BYTE *)v42 + 25) < 5u )
                goto LABEL_213;
              v49 = 755;
              goto LABEL_212;
            }
            if ( v11 == 5 )
            {
LABEL_204:
              if ( v42 == &WPP_GLOBAL_Control || (*((_DWORD *)v42 + 7) & 0x800) == 0 || *((_BYTE *)v42 + 25) < 5u )
                goto LABEL_213;
              v49 = 757;
LABEL_212:
              WPP_SF_(v42[2], v49, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
LABEL_213:
              v50 = (unsigned int)v11;
LABEL_214:
              UpdateAutoTriggerConnectionStatus(v7, lpParameter, 5, v50);
              goto LABEL_290;
            }
LABEL_378:
            if ( v42 != &WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
              {
                WPP_SF_(v42[2], 777, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
                v42 = WPP_GLOBAL_Control;
              }
              if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
                WPP_SF_d(v42[2], 778, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, (unsigned int)v11);
            }
            goto LABEL_290;
          }
          if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
          {
            WPP_SF_(v42[2], 740, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            v42 = WPP_GLOBAL_Control;
          }
          if ( !*((_DWORD *)lpParameter + 2652) )
          {
            if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
              WPP_SF_(v42[2], 741, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            memset_0(&WSAData, 0, sizeof(WSAData));
            v51 = WSAStartup(2u, &WSAData);
            v52 = v51;
            if ( v51 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 742, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v51);
              }
              HangUpAndCleanAutoTriggerContext((int)lpParameter, v78, (int)v7, 0, v52, (wchar_t *)SizeInWords);
              v14 = v52;
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_293;
              }
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 743, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v52);
              goto LABEL_167;
            }
            *((_DWORD *)lpParameter + 2652) = 1;
            v42 = WPP_GLOBAL_Control;
          }
          if ( *((_DWORD *)lpParameter + 2651) )
          {
            if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
              WPP_SF_(v42[2], 744, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            goto LABEL_290;
          }
          if ( v12 )
          {
            *(_DWORD *)(v12 + 5620) = *((_DWORD *)lpParameter + 2644);
          }
          else
          {
            if ( v42 == &WPP_GLOBAL_Control || (*((_DWORD *)v42 + 7) & 0x800) == 0 || *((_BYTE *)v42 + 25) < 2u )
            {
LABEL_246:
              if ( !*((_DWORD *)lpParameter + 2650) )
              {
                if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
                  WPP_SF_(v42[2], 754, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
                *(_DWORD *)(v12 + 5616) = 1;
                UpdateAutoTriggerConnectionStatus(v7, lpParameter, 5, 0);
                UpdateConnectoidStatus(lpParameter, 32);
                goto LABEL_290;
              }
              if ( v42 != &WPP_GLOBAL_Control )
              {
                if ( (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
                {
                  WPP_SF_(v42[2], 746, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
                  v42 = WPP_GLOBAL_Control;
                }
                if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
                  WPP_SF_d(
                    v42[2],
                    747,
                    WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                    *((unsigned int *)lpParameter + 2656));
              }
              v53 = *((_DWORD *)lpParameter + 2656);
              if ( v53 == -895418367 || v53 == -895352829 || v53 == -895352820 || v53 == -894894060 || v53 == -894894003 )
              {
                CredentialsFromVan = GetCredentialsFromVan(lpParameter, (__int64)v7, v48, 6u, 0);
                if ( !CredentialsFromVan )
                {
                  v10 = 691;
                  goto LABEL_290;
                }
                v59 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v60 = 748;
                  goto LABEL_315;
                }
              }
              else
              {
                if ( v53 )
                {
                  UpdateAutoTriggerConnectionStatus(v7, lpParameter, 3, 0);
                  v10 = 1359;
                  v54 = ((__int64 (__fastcall *)(HRASCONN, __int64, _QWORD))g_pRasSignalActionRequired)(v7, 3, 0);
                  if ( v54 )
                  {
                    v55 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    {
LABEL_271:
                      v14 = *((_DWORD *)lpParameter + 2656);
                      if ( (v14 & 0x1FFF0000) == 0x70000 )
                        v14 = (unsigned __int16)v14;
                      if ( !v14 )
                      {
                        if ( v55 != &WPP_GLOBAL_Control
                          && (*((_DWORD *)v55 + 7) & 0x800) != 0
                          && *((_BYTE *)v55 + 25) >= 5u )
                        {
                          WPP_SF_(v55[2], 752, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
                        }
                        v14 = 1359;
                      }
                      v56 = v78;
                      HangUpAndCleanAutoTriggerContext((int)lpParameter, v78, (int)v7, 0, v14, (wchar_t *)SizeInWords);
                      v57 = ShowToastNotification(lpParameter, 0);
                      if ( v57
                        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          753,
                          WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                          v57);
                      }
                      goto LABEL_291;
                    }
                    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    {
LABEL_267:
                      if ( v55 != &WPP_GLOBAL_Control
                        && (*((_DWORD *)v55 + 7) & 0x800) != 0
                        && *((_BYTE *)v55 + 25) >= 5u )
                      {
                        WPP_SF_d(
                          v55[2],
                          751,
                          WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                          *((unsigned int *)lpParameter + 2656));
                        v55 = WPP_GLOBAL_Control;
                      }
                      goto LABEL_271;
                    }
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      750,
                      WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                      v54);
                  }
                  v55 = WPP_GLOBAL_Control;
                  goto LABEL_267;
                }
                CredentialsFromVan = GetCredentialsFromVan(lpParameter, (__int64)v7, v48, 1u, 0);
                if ( !CredentialsFromVan )
                {
                  v10 = 877;
                  goto LABEL_290;
                }
                v59 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v60 = 749;
LABEL_315:
                  WPP_SF_d(v59[2], v60, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, CredentialsFromVan);
                }
              }
              HangUpAndCleanAutoTriggerContext(
                (int)lpParameter,
                v78,
                (int)v7,
                0,
                CredentialsFromVan,
                (wchar_t *)SizeInWords);
              v14 = CredentialsFromVan;
              goto LABEL_167;
            }
            WPP_SF_(v42[2], 745, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
          }
          v42 = WPP_GLOBAL_Control;
          goto LABEL_246;
        }
        if ( v11 == 7 || v11 == 8 || v11 == 9 )
          goto LABEL_204;
        v63 = v11 - 10;
        if ( v11 == 10 )
        {
          if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
            WPP_SF_(v42[2], 767, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
          SignalVanActionRequiredEvent(lpParameter, 0);
          v42 = WPP_GLOBAL_Control;
          goto LABEL_337;
        }
        goto LABEL_352;
      }
      if ( v11 <= 19 )
      {
        switch ( v11 )
        {
          case 19:
          case 13:
            goto LABEL_204;
          case 14:
            goto LABEL_337;
          case 15:
            goto LABEL_204;
          case 16:
            goto LABEL_204;
        }
        v63 = v11 - 17;
        if ( v11 == 17 )
          goto LABEL_204;
LABEL_352:
        if ( v63 != 1 )
          goto LABEL_378;
LABEL_337:
        if ( v42 != &WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
          {
            WPP_SF_(v42[2], 768, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            v42 = WPP_GLOBAL_Control;
          }
          if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
            WPP_SF_d(v42[2], 769, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, (unsigned int)v11);
        }
        goto LABEL_213;
      }
      if ( v11 == 20 || v11 == 21 )
        goto LABEL_204;
      if ( v11 != 22 )
      {
        v63 = v11 - 23;
        if ( v11 != 23 )
          goto LABEL_352;
LABEL_358:
        if ( v42 != &WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
          {
            WPP_SF_(v42[2], 774, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            v42 = WPP_GLOBAL_Control;
          }
          if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
            WPP_SF_d(v42[2], 775, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, (unsigned int)v11);
        }
        v64 = (__int64 (__fastcall *)(HRASCONN, _QWORD, _QWORD))*((_QWORD *)lpParameter + 1336);
        SizeInWords[0] = 0;
        if ( v64 )
        {
          v65 = v64(v7, 0, a7);
          if ( v65 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 776, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v65);
            }
          }
        }
        goto LABEL_213;
      }
      goto LABEL_386;
    }
    v66 = (unsigned int)(v11 - 4097);
    if ( v11 != 4097 )
    {
      switch ( v11 )
      {
        case 4098:
          goto LABEL_204;
        case 4099:
          if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
            WPP_SF_(v42[2], 758, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
          if ( (*((_DWORD *)lpParameter + 1932) & 0xA000000) == 0xA000000 )
          {
            v48 = *((_QWORD *)lpParameter + 1304);
            if ( v48 )
              memcpy_s(*((void *const *)lpParameter + 1303), 0x848u, (const void *const)v48, 0x848u);
          }
          v70 = 4099;
          ThirdPartyAuthData = GetCredentialsFromVan(lpParameter, (__int64)v7, v48, 1u, 0x1003u);
          if ( !ThirdPartyAuthData )
            goto LABEL_290;
          v72 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_436;
          }
          v73 = 759;
          break;
        case 4100:
          if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
          {
            WPP_SF_(v42[2], 764, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            v42 = WPP_GLOBAL_Control;
          }
          if ( v12 && *(_DWORD *)(v12 + 4868) )
          {
            if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 2u )
              WPP_SF_q(v42[2], 765, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
            goto LABEL_290;
          }
          v70 = 4100;
          ThirdPartyAuthData = GetCredentialsFromVan(lpParameter, (__int64)v7, v48, 1u, 0x1004u);
          if ( !ThirdPartyAuthData )
          {
LABEL_290:
            v56 = v78;
LABEL_291:
            UpdateUIStatus((int)lpParameter, v56, (int)v7, v11, v10, 0);
            v17 = WPP_GLOBAL_Control;
LABEL_292:
            if ( !v14 )
            {
LABEL_303:
              if ( !SizeInWords[0] )
                RasTriggerConnectionCleanup(&v82);
              EventActivityIdControl(2u, &ActivityId);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  781,
                  WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                  SizeInWords[0]);
              }
              return SizeInWords[0];
            }
LABEL_293:
            if ( *((_QWORD *)lpParameter + 1336) )
            {
              if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x800) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                WPP_SF_(v17[2], 779, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
              v61 = (*((__int64 (__fastcall **)(HRASCONN, _QWORD, _QWORD))lpParameter + 1336))(v7, v14, a7);
              if ( v61
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 780, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v61);
              }
            }
            goto LABEL_303;
          }
          v72 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_436;
          }
          v73 = 766;
          break;
        case 8192:
LABEL_386:
          if ( v42 != &WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
            {
              WPP_SF_(v42[2], 770, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
              v42 = WPP_GLOBAL_Control;
            }
            if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
              WPP_SF_d(v42[2], 771, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, (unsigned int)v11);
          }
          v67 = (*((_DWORD *)lpParameter + 1932) & 0x2000000) == 0;
          SizeInWords[0] = 0;
          if ( !v67 )
          {
            if ( *((_DWORD *)lpParameter + 2649) )
            {
              CacheAutoTriggerCredentials((__int64)lpParameter);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 772, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
              }
            }
          }
          v68 = (__int64 (__fastcall *)(HRASCONN, _QWORD, _QWORD))*((_QWORD *)lpParameter + 1336);
          if ( v68 )
          {
            v69 = v68(v7, 0, 0);
            if ( v69 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 773, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v69);
              }
            }
          }
          UpdateAutoTriggerConnectionStatus(v7, lpParameter, 5, (unsigned int)v11);
          if ( v11 == 0x2000 )
            SignalVanActionRequiredEvent(lpParameter, 0);
          goto LABEL_290;
        case 8193:
          goto LABEL_358;
        default:
          goto LABEL_378;
      }
      WPP_SF_d(v72[2], v73, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, ThirdPartyAuthData);
LABEL_436:
      v74 = v70;
LABEL_437:
      v56 = v78;
      HangUpAndCleanAutoTriggerContext((int)lpParameter, v78, (int)v7, v74, ThirdPartyAuthData, (wchar_t *)SizeInWords);
      goto LABEL_291;
    }
    if ( v42 != &WPP_GLOBAL_Control && (*((_DWORD *)v42 + 7) & 0x800) != 0 && *((_BYTE *)v42 + 25) >= 5u )
      WPP_SF_(v42[2], 760, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    v75 = 2;
    if ( (*((_DWORD *)lpParameter + 1932) & 0x8000000) != 0 )
    {
      ThirdPartyAuthData = GetThirdPartyAuthData(lpParameter, v66, v48);
      if ( ThirdPartyAuthData )
      {
        v76 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_449;
        }
        v77 = 761;
LABEL_448:
        WPP_SF_d(v76[2], v77, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, ThirdPartyAuthData);
LABEL_449:
        v74 = 4097;
        goto LABEL_437;
      }
      v75 = (*((_DWORD *)lpParameter + 2653) != 0) + 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 762, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v75);
      }
    }
    ThirdPartyAuthData = GetCredentialsFromVan(lpParameter, (__int64)v7, v48, v75, 0x1001u);
    if ( !ThirdPartyAuthData )
      goto LABEL_290;
    v76 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_449;
    }
    v77 = 763;
    goto LABEL_448;
  }
  if ( v13 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v13 + 7) & 0x800) != 0 && *((_BYTE *)v13 + 25) >= 5u )
    {
      WPP_SF_(v13[2], 713, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x800) != 0 && *((_BYTE *)v13 + 25) >= 6u )
      WPP_SF_d(v13[2], 714, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180087230  mov     [rsp-8+arg_18], rbx
0x180087235  push    rbp
0x180087236  push    rsi
0x180087237  push    rdi
0x180087238  push    r12
0x18008723a  push    r13
0x18008723c  push    r14
0x18008723e  push    r15
0x180087240  lea     rbp, [rsp-150h]
0x180087248  sub     rsp, 250h
0x18008724f  mov     rax, cs:__security_cookie
0x180087256  xor     rax, rsp
0x180087259  mov     [rbp+180h+var_40], rax
0x180087260  mov     r15, r8
0x180087263  mov     qword ptr [rsp+280h+SizeInWords+4], r8
0x180087268  mov     edi, edx
0x18008726a  mov     [rsp+280h+var_230], edx
0x18008726e  mov     rbx, rcx
0x180087271  mov     rcx, cs:WPP_GLOBAL_Control
0x180087278  lea     rax, WPP_GLOBAL_Control
0x18008727f  mov     esi, 800h
0x180087284  cmp     rcx, rax
0x180087287  jz      short loc_1800872CE
0x180087289  test    [rcx+1Ch], esi
0x18008728c  jz      short loc_1800872CE
0x18008728e  cmp     byte ptr [rcx+19h], 6
0x180087292  mov     r12d, [rbp+180h+arg_28]
0x180087299  mov     r14d, [rbp+180h+arg_20]
0x1800872a0  jb      short loc_1800872DC
0x1800872a2  mov     eax, [rbp+180h+arg_30]
0x1800872a8  mov     rcx, [rcx+10h]
0x1800872ac  mov     [rsp+280h+var_240], eax
0x1800872b0  mov     [rsp+280h+var_248], r12d
0x1800872b5  mov     [rsp+280h+var_250], r14d
0x1800872ba  mov     dword ptr [rsp+280h+var_258], r9d
0x1800872bf  mov     r9d, edx
0x1800872c2  mov     qword ptr [rsp+280h+var_260], r8
0x1800872c7  call    WPP_SF_dqddDD
0x1800872cc  jmp     short loc_1800872DC
0x1800872ce  mov     r12d, [rbp+180h+arg_28]
0x1800872d5  mov     r14d, [rbp+180h+arg_20]
0x1800872dc  mov     eax, 1
0x1800872e1  mov     [rsp+280h+var_210], rbx
0x1800872e6  xorps   xmm0, xmm0
0x1800872e9  mov     dword ptr [rsp+280h+SizeInWords], eax
0x1800872ed  xorps   xmm1, xmm1
0x1800872f0  lea     rdx, [rbp+180h+ActivityId]; ActivityId
0x1800872f4  mov     ecx, eax; ControlCode
0x1800872f6  movups  xmmword ptr [rsp+280h+var_208.Data1], xmm0
0x1800872fb  movups  xmmword ptr [rbp+180h+ActivityId.Data1], xmm1
0x1800872ff  call    cs:__imp_EventActivityIdControl
0x180087305  mov     rcx, r15
0x180087308  call    ValidateHrasconn
0x18008730d  mov     r13, rax
0x180087310  mov     rcx, cs:WPP_GLOBAL_Control
0x180087317  lea     rdx, WPP_GLOBAL_Control
0x18008731e  cmp     rcx, rdx
0x180087321  jz      short loc_180087354
0x180087323  test    [rcx+1Ch], esi
0x180087326  jz      short loc_180087354
0x180087328  cmp     byte ptr [rcx+19h], 5
0x18008732c  jb      short loc_180087354
0x18008732e  mov     rcx, [rcx+10h]
0x180087332  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180087339  mov     edx, 2C8h
0x18008733e  mov     r9d, r14d
0x180087341  call    WPP_SF_d
0x180087346  mov     rcx, cs:WPP_GLOBAL_Control
0x18008734d  lea     rdx, WPP_GLOBAL_Control
0x180087354  cmp     r12d, 29Ch
0x18008735b  jz      loc_180088C43
0x180087361  xor     eax, eax
0x180087363  test    rbx, rbx
0x180087366  jz      loc_180088C43
0x18008736c  cmp     dword ptr [rbx+293Ch], 0D1A1C0DEh
0x180087376  jnz     loc_180088C43
0x18008737c  mov     esi, eax
0x18008737e  test    r13, r13
0x180087381  jz      short loc_180087391
0x180087383  movups  xmm0, xmmword ptr [r13+15A4h]
0x18008738b  movdqu  xmmword ptr [rsp+280h+var_208.Data1], xmm0
0x180087391  lea     rdx, [rsp+280h+var_208]; ActivityId
0x180087396  mov     ecx, 2; ControlCode
0x18008739b  call    cs:__imp_EventActivityIdControl
0x1800873a1  lea     eax, [r14-1003h]
0x1800873a8  cmp     eax, 1
0x1800873ab  jbe     short loc_1800873C3
0x1800873ad  cmp     r14d, 1001h
0x1800873b4  jz      short loc_1800873C3
0x1800873b6  cmp     r14d, 2000h
0x1800873bd  jnz     loc_180087489
0x1800873c3  lea     rdi, [rbx+28B0h]
0x1800873ca  xor     edx, edx
0x1800873cc  cmp     [rdi], rdx
0x1800873cf  jnz     loc_18008747F
0x1800873d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800873dc  lea     rax, WPP_GLOBAL_Control
0x1800873e3  cmp     rcx, rax
0x1800873e6  jz      short loc_18008740C
0x1800873e8  test    dword ptr [rcx+1Ch], 800h
0x1800873ef  jz      short loc_18008740C
0x1800873f1  cmp     byte ptr [rcx+19h], 5
0x1800873f5  jb      short loc_18008740C
0x1800873f7  mov     rcx, [rcx+10h]
0x1800873fb  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180087402  mov     edx, 2CBh
0x180087407  call    WPP_SF_
0x18008740c  mov     rax, cs:g_pRasGetHportFromConnection
0x180087413  mov     rdx, rdi
0x180087416  mov     rcx, r15
0x180087419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008741e  xor     edi, edi
0x180087420  mov     esi, eax
0x180087422  test    eax, eax
0x180087424  jz      short loc_180087485
0x180087426  mov     rcx, cs:WPP_GLOBAL_Control
0x18008742d  lea     r12, WPP_GLOBAL_Control
0x180087434  cmp     rcx, r12
0x180087437  jz      short loc_180087460
0x180087439  test    dword ptr [rcx+1Ch], 800h
0x180087440  jz      short loc_180087460
0x180087442  cmp     byte ptr [rcx+19h], 2
0x180087446  jb      short loc_180087460
0x180087448  mov     rcx, [rcx+10h]
0x18008744c  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180087453  mov     edx, 2CCh
0x180087458  mov     r9d, eax
0x18008745b  call    WPP_SF_d
0x180087460  mov     rcx, r15; HRASCONN
0x180087463  mov     [r13+15F8h], rdi
0x18008746a  call    RasHangUpW
0x18008746f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087476  mov     dword ptr [rsp+280h+SizeInWords], edi
0x18008747a  jmp     loc_180088350
0x18008747f  mov     edi, [rsp+280h+var_230]
0x180087483  jmp     short loc_18008748B
0x180087485  mov     edi, [rsp+280h+var_230]
0x180087489  xor     edx, edx
0x18008748b  test    r12d, r12d
0x18008748e  jz      loc_180087B20
0x180087494  mov     rcx, cs:WPP_GLOBAL_Control
0x18008749b  lea     r8, WPP_GLOBAL_Control
0x1800874a2  mov     edi, 800h
0x1800874a7  cmp     rcx, r8
0x1800874aa  jz      short loc_1800874DF
0x1800874ac  test    [rcx+1Ch], edi
0x1800874af  jz      short loc_1800874DF
0x1800874b1  cmp     byte ptr [rcx+19h], 5
0x1800874b5  jb      short loc_1800874DF
0x1800874b7  mov     rcx, [rcx+10h]
0x1800874bb  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800874c2  mov     edx, 2CDh
0x1800874c7  mov     r9d, r12d
0x1800874ca  call    WPP_SF_d
0x1800874cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800874d6  lea     r8, WPP_GLOBAL_Control
0x1800874dd  xor     edx, edx
0x1800874df  test    r13, r13
0x1800874e2  jz      short loc_1800874ED
0x1800874e4  mov     r12d, [r13+1304h]
0x1800874eb  jmp     short loc_1800874F0
0x1800874ed  mov     r12d, edx
0x1800874f0  mov     eax, [rbp+180h+arg_28]
0x1800874f6  test    r12d, r12d
0x1800874f9  mov     r15d, edx
0x1800874fc  mov     [rsp+280h+var_220], eax
0x180087500  setz    r15b
0x180087504  mov     dword ptr [rsp+280h+SizeInWords], edx
0x180087508  mov     esi, edx
0x18008750a  mov     r14, rdx
0x18008750d  cmp     rcx, r8
0x180087510  jz      short loc_180087543
0x180087512  test    [rcx+1Ch], edi
0x180087515  jz      short loc_180087543
0x180087517  cmp     byte ptr [rcx+19h], 2
0x18008751b  jb      short loc_180087543
0x18008751d  mov     rcx, [rcx+10h]
0x180087521  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180087528  mov     edx, 2CEh
0x18008752d  mov     r9d, eax
0x180087530  call    WPP_SF_d
0x180087535  mov     rcx, cs:WPP_GLOBAL_Control
0x18008753c  lea     r8, WPP_GLOBAL_Control
0x180087543  test    dword ptr [rbx+1E30h], 8000000h
0x18008754d  jz      loc_1800876AA
0x180087553  cmp     rcx, r8
0x180087556  jz      short loc_180087578
0x180087558  test    [rcx+1Ch], edi
0x18008755b  jz      short loc_180087578
0x18008755d  cmp     byte ptr [rcx+19h], 5
0x180087561  jb      short loc_180087578
0x180087563  mov     rcx, [rcx+10h]
0x180087567  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008756e  mov     edx, 2CFh
0x180087573  call    WPP_SF_
0x180087578  mov     rcx, qword ptr [rsp+280h+SizeInWords+4]
0x18008757d  lea     rdx, [rsp+280h+Source]
0x180087582  mov     [rsp+280h+Source], 0
0x18008758b  call    RasGetConnectionErrorStringW
0x180087590  test    eax, eax
0x180087592  jz      short loc_1800875DB
0x180087594  mov     rcx, cs:WPP_GLOBAL_Control
0x18008759b  lea     rdx, WPP_GLOBAL_Control
0x1800875a2  cmp     rcx, rdx
0x1800875a5  jz      loc_1800876AA
0x1800875ab  test    [rcx+1Ch], edi
0x1800875ae  jz      loc_1800876AA
0x1800875b4  cmp     byte ptr [rcx+19h], 2
0x1800875b8  jb      loc_1800876AA
0x1800875be  mov     rcx, [rcx+10h]
0x1800875c2  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800875c9  mov     edx, 2D0h
0x1800875ce  mov     r9d, eax
0x1800875d1  call    WPP_SF_d
0x1800875d6  jmp     loc_1800876AA
0x1800875db  mov     rdi, [rsp+280h+Source]
0x1800875e0  test    rdi, rdi
0x1800875e3  jz      loc_1800876AA
0x1800875e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800875f0  lea     rax, WPP_GLOBAL_Control
0x1800875f7  cmp     rcx, rax
0x1800875fa  jz      short loc_180087623
0x1800875fc  test    dword ptr [rcx+1Ch], 800h
0x180087603  jz      short loc_180087623
0x180087605  cmp     byte ptr [rcx+19h], 5
0x180087609  jb      short loc_180087623
0x18008760b  mov     rcx, [rcx+10h]
0x18008760f  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180087616  mov     edx, 2D1h
0x18008761b  mov     r9, rdi
0x18008761e  call    WPP_SF_S
0x180087623  or      rax, 0FFFFFFFFFFFFFFFFh
0x180087627  xor     ecx, ecx
0x180087629  inc     rax
0x18008762c  cmp     [rdi+rax*2], cx
0x180087630  jnz     short loc_180087629
0x180087632  inc     eax
0x180087634  mov     ecx, 40h ; '@'; uFlags
0x180087639  mov     dword ptr [rsp+280h+SizeInWords], eax
0x18008763d  mov     esi, eax
0x18008763f  lea     rdx, [rax+rax]; uBytes
0x180087643  call    cs:__imp_LocalAlloc
0x180087649  mov     r14, rax
0x18008764c  test    rax, rax
0x18008764f  jnz     short loc_180087697
0x180087651  call    cs:__imp_GetLastError
0x180087657  test    eax, eax
0x180087659  jz      short loc_1800876A6
0x18008765b  mov     rcx, cs:WPP_GLOBAL_Control
0x180087662  lea     rdx, WPP_GLOBAL_Control
0x180087669  cmp     rcx, rdx
0x18008766c  jz      short loc_1800876A6
0x18008766e  test    dword ptr [rcx+1Ch], 800h
0x180087675  jz      short loc_1800876A6
0x180087677  cmp     byte ptr [rcx+19h], 2
0x18008767b  jb      short loc_1800876A6
0x18008767d  mov     rcx, [rcx+10h]
0x180087681  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180087688  mov     edx, 2D2h
0x18008768d  mov     r9d, eax
0x180087690  call    WPP_SF_d
0x180087695  jmp     short loc_1800876A6
0x180087697  mov     r8, rdi; Source
0x18008769a  mov     rdx, rsi; SizeInWords
0x18008769d  mov     rcx, rax; Destination
0x1800876a0  call    cs:__imp_wcscpy_s
0x1800876a6  mov     esi, dword ptr [rsp+280h+SizeInWords]
0x1800876aa  mov     rcx, qword ptr [rsp+280h+SizeInWords+4]; HRASCONN
0x1800876af  mov     qword ptr [r13+15F8h], 0
0x1800876ba  call    RasHangUpW
0x1800876bf  lea     rdi, [rbx+29B8h]
0x1800876c6  xor     r13d, r13d
0x1800876c9  cmp     [rdi], r13
0x1800876cc  jnz     loc_180087757
0x1800876d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800876d9  lea     rax, WPP_GLOBAL_Control
0x1800876e0  cmp     rcx, rax
0x1800876e3  jz      short loc_180087709
0x1800876e5  test    dword ptr [rcx+1Ch], 800h
0x1800876ec  jz      short loc_180087709
0x1800876ee  cmp     byte ptr [rcx+19h], 5
0x1800876f2  jb      short loc_180087709
0x1800876f4  mov     rcx, [rcx+10h]
0x1800876f8  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800876ff  mov     edx, 2D3h
0x180087704  call    WPP_SF_
0x180087709  mov     r9, rdi
0x18008770c  mov     edx, 1F0003h
0x180087711  mov     rcx, rbx
0x180087714  call    OpenVanActionRequiredEvent
0x180087719  test    eax, eax
0x18008771b  jz      short loc_180087757
0x18008771d  mov     rcx, cs:WPP_GLOBAL_Control
0x180087724  lea     rdx, WPP_GLOBAL_Control
0x18008772b  cmp     rcx, rdx
0x18008772e  jz      short loc_180087765
0x180087730  test    dword ptr [rcx+1Ch], 800h
0x180087737  jz      short loc_180087765
0x180087739  cmp     byte ptr [rcx+19h], 2
0x18008773d  jb      short loc_180087765
  ... truncated ...
```
