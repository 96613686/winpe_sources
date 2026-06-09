# KpsDoSocketConnectAndSend(KpsIoLockedRef &)

- ea: `0x18001f5ec`
- end: `0x18001fd00`
- name: `?KpsDoSocketConnectAndSend@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `1812`
- prototype: `void __fastcall(struct _KPS_IO **)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f5ec`
- `0x1800202d0`
- `0x1800223fc`

## callees

- `0x18001ada8`
- `0x18001ae38`
- `0x18001e728`
- `0x18001f5ec`
- `0x1800202d0`
- `0x180022d38`
- `0x180024be0`
- `0x180026a08`
- `0x180026aa0`
- `0x180026bc0`
- `0x180026d9c`
- `0x18002cc3c`
- `0x18003100e`
- `0x180031040`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f9e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f9e6`
- `WS2_32!FreeAddrInfoW` at `0x18001f72b`
- `WS2_32!FreeAddrInfoW` at `0x18001f72b`
- `WS2_32!WSAIoctl` at `0x18001f961`
- `WS2_32!WSAIoctl` at `0x18001f961`
- `WS2_32!__imp_bind` at `0x18001fa8b`
- `WS2_32!__imp_bind` at `0x18001fa8b`
- `WS2_32!__imp_closesocket` at `0x18001f750`
- `WS2_32!__imp_closesocket` at `0x18001fc49`
- `WS2_32!__imp_closesocket` at `0x18001f750`
- `WS2_32!__imp_closesocket` at `0x18001fc49`
- `WS2_32!__imp_htons` at `0x18001fa5a`
- `WS2_32!__imp_htons` at `0x18001fa5a`
- `WS2_32!__imp_socket` at `0x18001f8ab`
- `WS2_32!__imp_socket` at `0x18001f8ab`
- `WS2_32!__imp_WSAGetLastError` at `0x18001f8d3`
- `WS2_32!__imp_WSAGetLastError` at `0x18001f971`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fa9b`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fb5d`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fb86`
- `WS2_32!__imp_WSAGetLastError` at `0x18001f8d3`
- `WS2_32!__imp_WSAGetLastError` at `0x18001f971`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fa9b`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fb5d`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fb86`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001f775`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001fc6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001f775`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001fc6f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001fae9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001fae9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001fb7a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001fb7a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001f9c4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18001f9c4`
- `ntdll!RtlLeaveCriticalSection` at `0x18001fc08`
- `ntdll!RtlLeaveCriticalSection` at `0x18001fc08`
- `ntdll!RtlFreeUnicodeString` at `0x18001f710`
- `ntdll!RtlFreeUnicodeString` at `0x18001f710`

## string_xrefs

- `0x18001f86e`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18001f90c`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18001fbaa`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoSocketConnectAndSend(struct _KPS_IO **a1)
{
  DWORD Error; // esi
  struct _KPS_IO *v3; // r9
  struct _KPS_IO *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // edx
  __int64 v8; // r8
  struct addrinfoW *v9; // rcx
  SOCKET v10; // rcx
  struct _TP_IO *v11; // rcx
  struct _KPS_IO *v12; // rax
  const wchar_t *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  _QWORD *v16; // rcx
  SOCKET v17; // rcx
  int v18; // edx
  int v19; // ebx
  bool v20; // zf
  struct _KPS_IO *v21; // rbx
  SOCKET v22; // rcx
  struct _TP_IO *v23; // rcx
  DWORD cbOutBuffer[2]; // [rsp+30h] [rbp-D8h]
  DWORD cbOutBuffera[2]; // [rsp+30h] [rbp-D8h]
  int v26; // [rsp+58h] [rbp-B0h] BYREF
  DWORD cbBytesReturned; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD vInBuffer[4]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE name[24]; // [rsp+78h] [rbp-90h] BYREF
  int v30; // [rsp+90h] [rbp-78h]
  _BYTE v31[16]; // [rsp+F8h] [rbp-10h] BYREF
  int *v32; // [rsp+108h] [rbp+0h]
  __int64 v33; // [rsp+110h] [rbp+8h]
  const wchar_t *v34; // [rsp+118h] [rbp+10h]
  int v35; // [rsp+120h] [rbp+18h]
  int v36; // [rsp+124h] [rbp+1Ch]

  vInBuffer[0] = 631375801;
  cbBytesReturned = 0;
  vInBuffer[1] = 1180753395;
  vInBuffer[2] = -445191794;
  vInBuffer[3] = 1040610444;
  Error = 0;
  memset_0(name, 0, 0x80u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *a1);
  if ( !KpsServiceReady() )
    goto LABEL_67;
  v3 = *a1;
  if ( *((_QWORD *)*a1 + 26) )
  {
    v4 = *a1;
    do
    {
      v5 = *((_QWORD *)v4 + 26);
      v3 = v4;
      if ( *(_DWORD *)(v5 + 4) == 23 )
        break;
      if ( *(_DWORD *)(v5 + 4) == 2 )
        break;
      *((_QWORD *)v4 + 26) = *(_QWORD *)(v5 + 40);
      v3 = *a1;
      v4 = *a1;
    }
    while ( *((_QWORD *)*a1 + 26) );
  }
  v6 = *((_QWORD *)v3 + 26);
  if ( v6 )
  {
    *((_QWORD *)*a1 + 27) = socket(*(_DWORD *)(v6 + 4), *(_DWORD *)(v6 + 8), 6);
    v17 = *((_QWORD *)*a1 + 27);
    if ( v17 == -1 )
    {
      Error = WSAGetLastError();
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_68;
      v18 = 60;
      cbOutBuffer[0] = 1360;
    }
    else
    {
      v19 = 16;
      if ( WSAIoctl(v17, 0xC8000006, vInBuffer, 0x10u, (char *)*a1 + 232, 8u, &cbBytesReturned, 0, 0) )
      {
        Error = WSAGetLastError();
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_68;
        v18 = 61;
        cbOutBuffer[0] = 1370;
      }
      else
      {
        *((_QWORD *)*a1 + 28) = CreateThreadpoolIo(*((HANDLE *)*a1 + 27), KpsSocketIoCompletion, 0, &pcbe);
        if ( *((_QWORD *)*a1 + 28) )
        {
          v20 = *(_WORD *)(*((_QWORD *)*a1 + 26) + 4LL) == 23;
          *(_DWORD *)&name[4] = 0;
          if ( v20 )
          {
            *(_WORD *)name = 23;
            *(_OWORD *)&name[8] = 0;
            v30 = 0;
          }
          else
          {
            *(_WORD *)name = 2;
            *(_QWORD *)&name[8] = 0;
          }
          *(_WORD *)&name[2] = htons(0);
          if ( *(_WORD *)name == 23 )
            v19 = 28;
          if ( !bind(*((_QWORD *)*a1 + 27), (const struct sockaddr *)name, v19) )
          {
            *((_DWORD *)*a1 + 8) = 8;
            StartThreadpoolIo(*((PTP_IO *)*a1 + 28));
            if ( *a1 && _InterlockedIncrement64((volatile signed __int64 *)*a1 + 43) <= 1 )
              __fastfail(0xEu);
            if ( (*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, struct _KPS_IO *))*a1
                  + 29))(
                   *((_QWORD *)*a1 + 27),
                   *(_QWORD *)(*((_QWORD *)*a1 + 26) + 32LL),
                   *(unsigned int *)(*((_QWORD *)*a1 + 26) + 16LL),
                   *(_QWORD *)(*((_QWORD *)*a1 + 13) + 16LL),
                   *(_DWORD *)(*((_QWORD *)*a1 + 13) + 8LL),
                   0,
                   *a1)
              || WSAGetLastError() == 997 )
            {
              v21 = *a1;
              KpsStartTimeoutTimer(*a1);
              *((_DWORD *)v21 + 84) = 1;
              if ( *a1 )
              {
                if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a1) )
                  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)*a1 + 288));
                *a1 = 0;
              }
            }
            else
            {
              CancelThreadpoolIo(*((PTP_IO *)*a1 + 28));
              Error = WSAGetLastError();
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                cbOutBuffera[0] = 1414;
                WPP_SF_Dsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  64,
                  (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
                  Error,
                  (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
                  *(_QWORD *)cbOutBuffera);
              }
              KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a1);
            }
            goto LABEL_67;
          }
          Error = WSAGetLastError();
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_68;
          v18 = 63;
          cbOutBuffer[0] = 1392;
        }
        else
        {
          Error = GetLastError();
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_68;
          v18 = 62;
          cbOutBuffer[0] = 1379;
        }
      }
    }
    WPP_SF_Dsd(
      v16[2],
      v18,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      Error,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      *(_QWORD *)cbOutBuffer);
    goto LABEL_67;
  }
  if ( *((_DWORD *)v3 + 60) < (unsigned int)dword_18003A9B8 )
  {
    RtlFreeUnicodeString((PUNICODE_STRING)((char *)v3 + 184));
    v9 = (struct addrinfoW *)*((_QWORD *)*a1 + 25);
    if ( v9 )
    {
      FreeAddrInfoW(v9);
      *((_QWORD *)*a1 + 25) = 0;
    }
    v10 = *((_QWORD *)*a1 + 27);
    if ( v10 != -1 )
    {
      closesocket(v10);
      *((_QWORD *)*a1 + 27) = -1;
    }
    v11 = (struct _TP_IO *)*((_QWORD *)*a1 + 28);
    if ( v11 )
    {
      CloseThreadpoolIo(v11);
      *((_QWORD *)*a1 + 28) = 0;
    }
    ++*((_DWORD *)*a1 + 60);
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 4) != 0 )
    {
      v12 = *a1;
      v33 = 4;
      v13 = (const wchar_t *)*((_QWORD *)v12 + 15);
      v26 = *((_DWORD *)v12 + 60);
      v32 = &v26;
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] );
        v15 = 2 * v14 + 2;
      }
      else
      {
        v15 = 10;
        v13 = L"NULL";
      }
      v35 = v15;
      v34 = v13;
      v36 = 0;
      McGenEventWrite_EventWriteTransfer(v13, RetryKdcConnection, v8, 3, v31);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_LZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, *((_DWORD *)*a1 + 60), (__int64)*a1 + 112);
    KpsForwardKerbRequest(a1);
    goto LABEL_67;
  }
  Error = 1168;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_ZDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      144,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      71);
LABEL_67:
    v16 = WPP_GLOBAL_Control;
  }
LABEL_68:
  if ( *a1 )
  {
    if ( KpsServiceReady() && *((_QWORD *)*a1 + 26) )
    {
      v22 = *((_QWORD *)*a1 + 27);
      if ( v22 != -1 )
      {
        closesocket(v22);
        *((_QWORD *)*a1 + 27) = -1;
      }
      v23 = (struct _TP_IO *)*((_QWORD *)*a1 + 28);
      if ( v23 )
      {
        CloseThreadpoolIo(v23);
        *((_QWORD *)*a1 + 28) = 0;
      }
      *((_QWORD *)*a1 + 26) = *(_QWORD *)(*((_QWORD *)*a1 + 26) + 40LL);
      KpsDoSocketConnectAndSend((struct KpsIoLockedRef *)a1);
    }
    else
    {
      KpsDoHttpCancelRequest((struct KpsIoLockedRef *)a1);
    }
    v16 = WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 0x20) != 0 )
    WPP_SF_D(v16[2], 65, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, Error);
}

```

## disassembly

```asm
0x18001f5ec  mov     rax, rsp
0x18001f5ef  mov     [rax+10h], rbx
0x18001f5f3  mov     [rax+18h], rsi
0x18001f5f7  mov     [rax+20h], rdi
0x18001f5fb  push    rbp
0x18001f5fc  push    r12
0x18001f5fe  push    r13
0x18001f600  push    r14
0x18001f602  push    r15
0x18001f604  lea     rbp, [rax-58h]
0x18001f608  sub     rsp, 130h
0x18001f60f  mov     rax, cs:__security_cookie
0x18001f616  xor     rax, rsp
0x18001f619  mov     [rbp+50h+var_30], rax
0x18001f61d  xor     r14d, r14d
0x18001f620  mov     [rsp+150h+vInBuffer], 25A207B9h
0x18001f628  mov     rdi, rcx
0x18001f62b  mov     [rsp+150h+cbBytesReturned], r14d
0x18001f630  lea     rcx, [rsp+150h+name]; void *
0x18001f635  mov     [rsp+150h+var_EC], 4660DDF3h
0x18001f63d  xor     edx, edx; Val
0x18001f63f  mov     dword ptr [rsp+150h+var_E8], 0E576E98Eh
0x18001f647  mov     r8d, 80h; Size
0x18001f64d  mov     [rsp+150h+var_E4], 3E06748Ch
0x18001f655  mov     esi, r14d
0x18001f658  call    memset_0
0x18001f65d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f664  lea     r15, WPP_GLOBAL_Control
0x18001f66b  lea     r13, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001f672  cmp     rcx, r15
0x18001f675  jz      short loc_18001F690
0x18001f677  test    byte ptr [rcx+1Ch], 20h
0x18001f67b  jz      short loc_18001F690
0x18001f67d  mov     r9, [rdi]
0x18001f680  lea     edx, [r14+39h]
0x18001f684  mov     rcx, [rcx+10h]
0x18001f688  mov     r8, r13
0x18001f68b  call    WPP_SF_q
0x18001f690  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18001f695  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001f699  test    al, al
0x18001f69b  jz      loc_18001FC17
0x18001f6a1  mov     r9, [rdi]
0x18001f6a4  lea     edx, [rbx+3]
0x18001f6a7  lea     r12d, [rbx+18h]
0x18001f6ab  cmp     [r9+0D0h], r14
0x18001f6b2  jz      short loc_18001F6E6
0x18001f6b4  mov     rcx, r9
0x18001f6b7  mov     rax, [rcx+0D0h]
0x18001f6be  mov     r9, rcx
0x18001f6c1  cmp     [rax+4], r12d
0x18001f6c5  jz      short loc_18001F6E6
0x18001f6c7  cmp     [rax+4], edx
0x18001f6ca  jz      short loc_18001F6E6
0x18001f6cc  mov     rax, [rax+28h]
0x18001f6d0  mov     [rcx+0D0h], rax
0x18001f6d7  mov     r9, [rdi]
0x18001f6da  mov     rcx, r9
0x18001f6dd  cmp     [r9+0D0h], r14
0x18001f6e4  jnz     short loc_18001F6B7
0x18001f6e6  mov     rcx, [r9+0D0h]
0x18001f6ed  test    rcx, rcx
0x18001f6f0  jnz     loc_18001F89F
0x18001f6f6  mov     eax, cs:dword_18003A9B8
0x18001f6fc  cmp     [r9+0F0h], eax
0x18001f703  jnb     loc_18001F84B
0x18001f709  lea     rcx, [r9+0B8h]; UnicodeString
0x18001f710  call    cs:__imp_RtlFreeUnicodeString
0x18001f717  nop     dword ptr [rax+rax+00h]
0x18001f71c  mov     rax, [rdi]
0x18001f71f  mov     rcx, [rax+0C8h]; pAddrInfo
0x18001f726  test    rcx, rcx
0x18001f729  jz      short loc_18001F741
0x18001f72b  call    cs:__imp_FreeAddrInfoW
0x18001f732  nop     dword ptr [rax+rax+00h]
0x18001f737  mov     rax, [rdi]
0x18001f73a  mov     [rax+0C8h], r14
0x18001f741  mov     rax, [rdi]
0x18001f744  mov     rcx, [rax+0D8h]; s
0x18001f74b  cmp     rcx, rbx
0x18001f74e  jz      short loc_18001F766
0x18001f750  call    cs:__imp_closesocket
0x18001f757  nop     dword ptr [rax+rax+00h]
0x18001f75c  mov     rax, [rdi]
0x18001f75f  mov     [rax+0D8h], rbx
0x18001f766  mov     rax, [rdi]
0x18001f769  mov     rcx, [rax+0E0h]; pio
0x18001f770  test    rcx, rcx
0x18001f773  jz      short loc_18001F78B
0x18001f775  call    cs:__imp_CloseThreadpoolIo
0x18001f77c  nop     dword ptr [rax+rax+00h]
0x18001f781  mov     rax, [rdi]
0x18001f784  mov     [rax+0E0h], r14
0x18001f78b  mov     rax, [rdi]
0x18001f78e  inc     dword ptr [rax+0F0h]
0x18001f794  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 4
0x18001f79b  jz      short loc_18001F80C
0x18001f79d  mov     rax, [rdi]
0x18001f7a0  mov     [rbp+50h+var_48], 4
0x18001f7a8  mov     rcx, [rax+78h]
0x18001f7ac  mov     eax, [rax+0F0h]
0x18001f7b2  mov     [rsp+150h+var_100], eax
0x18001f7b6  lea     rax, [rsp+150h+var_100]
0x18001f7bb  mov     [rbp+50h+var_50], rax
0x18001f7bf  test    rcx, rcx
0x18001f7c2  jz      short loc_18001F7DA
0x18001f7c4  mov     rax, rbx
0x18001f7c7  inc     rax
0x18001f7ca  cmp     [rcx+rax*2], r14w
0x18001f7cf  jnz     short loc_18001F7C7
0x18001f7d1  lea     eax, ds:2[rax*2]
0x18001f7d8  jmp     short loc_18001F7E6
0x18001f7da  mov     eax, 0Ah
0x18001f7df  lea     rcx, aNull_0; "NULL"
0x18001f7e6  mov     [rbp+50h+var_38], eax
0x18001f7e9  lea     rdx, RetryKdcConnection
0x18001f7f0  lea     rax, [rbp+50h+var_60]
0x18001f7f4  mov     [rbp+50h+var_40], rcx
0x18001f7f8  mov     r9d, 3
0x18001f7fe  mov     [rsp+150h+lpvOutBuffer], rax
0x18001f803  mov     [rbp+50h+var_34], r14d
0x18001f807  call    McGenEventWrite_EventWriteTransfer
0x18001f80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f813  cmp     rcx, r15
0x18001f816  jz      short loc_18001F83E
0x18001f818  mov     ebx, 10h
0x18001f81d  test    [rcx+1Ch], bl
0x18001f820  jz      short loc_18001F83E
0x18001f822  mov     r9, [rdi]
0x18001f825  mov     rcx, [rcx+10h]
0x18001f829  lea     rax, [r9+70h]
0x18001f82d  mov     r9d, [r9+0F0h]
0x18001f834  mov     [rsp+150h+lpvOutBuffer], rax
0x18001f839  call    WPP_SF_LZ
0x18001f83e  mov     rcx, rdi; struct KpsIoLockedRef *
0x18001f841  call    ?KpsForwardKerbRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsForwardKerbRequest(KpsIoLockedRef &)
0x18001f846  jmp     loc_18001FC17
0x18001f84b  mov     esi, 490h
0x18001f850  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f857  cmp     rcx, r15
0x18001f85a  jz      loc_18001FC1E
0x18001f860  test    byte ptr [rcx+1Ch], 1
0x18001f864  jz      loc_18001FC1E
0x18001f86a  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f86e  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001f875  mov     dword ptr [rsp+150h+lpcbBytesReturned], 547h; char
0x18001f87d  add     r9, 0B8h
0x18001f884  mov     qword ptr [rsp+150h+cbOutBuffer], rax; __int64
0x18001f889  mov     edx, 3Bh ; ';'
0x18001f88e  mov     r8, r13
0x18001f891  mov     dword ptr [rsp+150h+lpvOutBuffer], esi; char
0x18001f895  call    WPP_SF_ZDsd
0x18001f89a  jmp     loc_18001FC17
0x18001f89f  mov     edx, [rcx+8]; type
0x18001f8a2  mov     r8d, 6; protocol
0x18001f8a8  mov     ecx, [rcx+4]; af
0x18001f8ab  call    cs:__imp_socket
0x18001f8b2  nop     dword ptr [rax+rax+00h]
0x18001f8b7  mov     rcx, rax
0x18001f8ba  mov     rax, [rdi]
0x18001f8bd  mov     [rax+0D8h], rcx
0x18001f8c4  mov     rax, [rdi]
0x18001f8c7  mov     rcx, [rax+0D8h]; s
0x18001f8ce  cmp     rcx, rbx
0x18001f8d1  jnz     short loc_18001F928
0x18001f8d3  call    cs:__imp_WSAGetLastError
0x18001f8da  nop     dword ptr [rax+rax+00h]
0x18001f8df  mov     esi, eax
0x18001f8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8e8  cmp     rcx, r15
0x18001f8eb  jz      loc_18001FC1E
0x18001f8f1  test    byte ptr [rcx+1Ch], 1
0x18001f8f5  jz      loc_18001FC1E
0x18001f8fb  mov     edx, 3Ch ; '<'
0x18001f900  mov     [rsp+150h+cbOutBuffer], 550h
0x18001f908  mov     rcx, [rcx+10h]
0x18001f90c  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001f913  mov     r9d, esi
0x18001f916  mov     [rsp+150h+lpvOutBuffer], rax
0x18001f91b  mov     r8, r13
0x18001f91e  call    WPP_SF_Dsd
0x18001f923  jmp     loc_18001FC17
0x18001f928  mov     [rsp+150h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18001f92d  lea     rdx, [rsp+150h+cbBytesReturned]
0x18001f932  mov     [rsp+150h+lpOverlapped], r14; lpOverlapped
0x18001f937  lea     r8, [rsp+150h+vInBuffer]; lpvInBuffer
0x18001f93c  mov     [rsp+150h+lpcbBytesReturned], rdx; lpcbBytesReturned
0x18001f941  add     rax, 0E8h
0x18001f947  mov     ebx, 10h
0x18001f94c  mov     [rsp+150h+cbOutBuffer], 8; cbOutBuffer
0x18001f954  mov     edx, 0C8000006h; dwIoControlCode
0x18001f959  mov     [rsp+150h+lpvOutBuffer], rax; lpvOutBuffer
0x18001f95e  mov     r9d, ebx; cbInBuffer
0x18001f961  call    cs:__imp_WSAIoctl
0x18001f968  nop     dword ptr [rax+rax+00h]
0x18001f96d  test    eax, eax
0x18001f96f  jz      short loc_18001F9A9
0x18001f971  call    cs:__imp_WSAGetLastError
0x18001f978  nop     dword ptr [rax+rax+00h]
0x18001f97d  mov     esi, eax
0x18001f97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f986  cmp     rcx, r15
0x18001f989  jz      loc_18001FC1E
0x18001f98f  test    byte ptr [rcx+1Ch], 1
0x18001f993  jz      loc_18001FC1E
0x18001f999  lea     edx, [rbx+2Dh]
0x18001f99c  mov     [rsp+150h+cbOutBuffer], 55Ah
0x18001f9a4  jmp     loc_18001F908
0x18001f9a9  mov     rcx, [rdi]
0x18001f9ac  lea     r9, pcbe; pcbe
0x18001f9b3  xor     r8d, r8d; pv
0x18001f9b6  lea     rdx, ?KpsSocketIoCompletion@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18001f9bd  mov     rcx, [rcx+0D8h]; fl
0x18001f9c4  call    cs:__imp_CreateThreadpoolIo
0x18001f9cb  nop     dword ptr [rax+rax+00h]
0x18001f9d0  mov     rcx, [rdi]
0x18001f9d3  mov     [rcx+0E0h], rax
0x18001f9da  mov     rax, [rdi]
0x18001f9dd  cmp     [rax+0E0h], r14
0x18001f9e4  jnz     short loc_18001FA20
0x18001f9e6  call    cs:__imp_GetLastError
0x18001f9ed  nop     dword ptr [rax+rax+00h]
0x18001f9f2  mov     esi, eax
0x18001f9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9fb  cmp     rcx, r15
0x18001f9fe  jz      loc_18001FC1E
0x18001fa04  test    byte ptr [rcx+1Ch], 1
0x18001fa08  jz      loc_18001FC1E
0x18001fa0e  mov     edx, 3Eh ; '>'
0x18001fa13  mov     [rsp+150h+cbOutBuffer], 563h
0x18001fa1b  jmp     loc_18001F908
0x18001fa20  mov     rax, [rax+0D0h]
0x18001fa27  cmp     [rax+4], r12w
0x18001fa2c  mov     dword ptr [rsp+150h+name+4], r14d
0x18001fa31  jnz     short loc_18001FA47
0x18001fa33  xorps   xmm0, xmm0
0x18001fa36  mov     word ptr [rsp+150h+name], r12w
0x18001fa3c  movups  xmmword ptr [rsp+150h+name+8], xmm0
0x18001fa41  mov     [rbp+50h+var_C8], r14d
0x18001fa45  jmp     short loc_18001FA58
0x18001fa47  mov     eax, 2
0x18001fa4c  mov     word ptr [rsp+150h+name], ax
0x18001fa51  xor     eax, eax
0x18001fa53  mov     qword ptr [rsp+150h+name+8], rax
0x18001fa58  xor     ecx, ecx; hostshort
0x18001fa5a  call    cs:__imp_htons
0x18001fa61  nop     dword ptr [rax+rax+00h]
0x18001fa66  cmp     word ptr [rsp+150h+name], r12w
0x18001fa6c  lea     rdx, [rsp+150h+name]; name
0x18001fa71  mov     word ptr [rsp+150h+name+2], ax
0x18001fa76  mov     eax, 1Ch
0x18001fa7b  cmovz   ebx, eax
0x18001fa7e  mov     rax, [rdi]
0x18001fa81  mov     r8d, ebx; namelen
0x18001fa84  mov     rcx, [rax+0D8h]; s
0x18001fa8b  call    cs:__imp_bind
0x18001fa92  nop     dword ptr [rax+rax+00h]
0x18001fa97  test    eax, eax
0x18001fa99  jz      short loc_18001FAD5
0x18001fa9b  call    cs:__imp_WSAGetLastError
0x18001faa2  nop     dword ptr [rax+rax+00h]
0x18001faa7  mov     esi, eax
0x18001faa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fab0  cmp     rcx, r15
0x18001fab3  jz      loc_18001FC1E
0x18001fab9  test    byte ptr [rcx+1Ch], 1
0x18001fabd  jz      loc_18001FC1E
0x18001fac3  mov     edx, 3Fh ; '?'
0x18001fac8  mov     [rsp+150h+cbOutBuffer], 570h
0x18001fad0  jmp     loc_18001F908
0x18001fad5  mov     rax, [rdi]
0x18001fad8  mov     dword ptr [rax+20h], 8
0x18001fadf  mov     rcx, [rdi]
0x18001fae2  mov     rcx, [rcx+0E0h]; pio
0x18001fae9  call    cs:__imp_StartThreadpoolIo
0x18001faf0  nop     dword ptr [rax+rax+00h]
0x18001faf5  mov     rcx, [rdi]
0x18001faf8  test    rcx, rcx
0x18001fafb  jz      short loc_18001FB1B
0x18001fafd  mov     eax, 1
0x18001fb02  lock xadd [rcx+158h], rax
0x18001fb0b  inc     rax
0x18001fb0e  cmp     rax, 1
0x18001fb12  jg      short loc_18001FB1B
0x18001fb14  mov     ecx, 0Eh
0x18001fb19  int     29h; Win8: RtlFailFast(ecx)
0x18001fb1b  mov     r10, [rdi]
0x18001fb1e  mov     [rsp+150h+lpcbBytesReturned], r10
0x18001fb23  mov     qword ptr [rsp+150h+cbOutBuffer], r14
0x18001fb28  mov     rcx, [r10+68h]
0x18001fb2c  mov     rax, [r10+0E8h]
0x18001fb33  mov     edx, [rcx+8]
0x18001fb36  mov     r9, [rcx+10h]
0x18001fb3a  mov     rcx, [r10+0D0h]
0x18001fb41  mov     dword ptr [rsp+150h+lpvOutBuffer], edx
0x18001fb45  mov     r8d, [rcx+10h]
0x18001fb49  mov     rdx, [rcx+20h]
0x18001fb4d  mov     rcx, [r10+0D8h]
0x18001fb54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb59  test    eax, eax
  ... truncated ...
```
