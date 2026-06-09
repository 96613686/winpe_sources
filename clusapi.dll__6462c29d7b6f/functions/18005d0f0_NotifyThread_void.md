# NotifyThread(void *)

- ea: `0x18005d0f0`
- end: `0x18005d6dc`
- name: `?NotifyThread@@YAKPEAX@Z`
- size: `1516`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002f50`
- `0x18001236c`
- `0x180025478`
- `0x18005aabc`
- `0x18005c960`
- `0x18005cea0`
- `0x18005cfcc`
- `0x18005d0f0`
- `0x18006f910`
- `0x18009e2d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d597`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d60e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d597`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d60e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d3d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d3d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d58c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d63d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d58c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d63d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d22b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d412`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d4c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d22b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d412`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005d4c0`

## string_xrefs

- `0x18005d678`: `Saw Session 0x%p destroyed in NotifyThread`
- `0x18005d126`: `NotifyThread`
- `0x18005d1c1`: `NotifyThread`
- `0x18005d2b0`: `NotifyThread`
- `0x18005d31a`: `NotifyThread`
- `0x18005d38b`: `NotifyThread`
- `0x18005d4df`: `NotifyThread`
- `0x18005d53d`: `NotifyThread`
- `0x18005d5b4`: `NotifyThread`
- `0x18005d5e4`: `NotifyThread`
- `0x18005d628`: `NotifyThread`
- `0x18005d6ab`: `NotifyThread`
- `0x18005d1af`: `Unknown session notification version in NotifyThread. Setting Status = ERROR_INVALID_PARAMETER to exit.`
- `0x18005d374`: `Received ERROR_INVALID_FUNCTION in NotifyThread. Going to exit..`
- `0x18005d645`: `ERROR_INVALID_PARAMETER detected in NotifyThread, continuing`
- `0x18005d5d2`: `MystrlenW Failed in NotifyThread, posting reconnect packets and continuing.`
- `0x18005d4f2`: `Failed StringCopy in NotifyThread, posting reconnect packets and continuing.`
- `0x18005d59d`: `Unknown session notification version in NotifyThread. NotifyThread exiting.`
- `0x18005d657`: `Unknown session notification version in NotifyThread. NotifyThread exiting.`
- `0x18005d616`: `Cluster is dead, exiting notify thread`
- `0x18005d699`: `NotifyThread broken out of loop, exiting.`

## pseudocode

```c
__int64 __fastcall NotifyThread(_QWORD *Parameter)
{
  __int64 v1; // r13
  unsigned int i; // esi
  _QWORD *v4; // r15
  _DWORD *v5; // r14
  __int64 v6; // rdx
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // r12
  wchar_t *v10; // r15
  __int64 **v11; // r13
  __int64 *j; // rsi
  unsigned int v13; // r15d
  wchar_t *v14; // rax
  __int64 v15; // r8
  __int64 v17; // [rsp+28h] [rbp-D8h]
  __int64 v18; // [rsp+30h] [rbp-D0h]
  _QWORD *v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v21; // [rsp+50h] [rbp-B0h]
  _QWORD v22[7]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v26[6]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+F0h] [rbp-10h]
  __int64 v29; // [rsp+F8h] [rbp-8h]
  __int64 v30; // [rsp+100h] [rbp+0h]
  _QWORD *v31; // [rsp+108h] [rbp+8h]

  v1 = Parameter[6];
  for ( i = 1609; ; i = 0 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( *((_DWORD *)Parameter + 22) )
          {
            TraceMsg(4, 7, L"NotifyThread", 996, L"Saw Session 0x%p destroyed in NotifyThread", Parameter);
            goto LABEL_52;
          }
          v31 = Parameter;
          v4 = Parameter + 7;
          v17 = Parameter[7];
          v23 = 0;
          v29 = 0;
          v28 = 0;
          v27 = 0;
          memset(v26, 0, sizeof(v26));
          v25 = 0;
          v24 = 0;
          v30 = 0;
          TraceMsg(4, 7, L"NotifyThread", 1006, L"Calling ApiGetNotify, hNotify=0x%p", v17);
          v5 = Parameter + 12;
          if ( *((_DWORD *)Parameter + 24) == 1 )
          {
            v6 = Parameter[6];
            v22[0] = "ApiGetNotify";
            v22[1] = Parameter + 7;
            v22[2] = (char *)&v24 + 4;
            v22[3] = &v25;
            v22[4] = (char *)&v25 + 4;
            v22[5] = v26;
            i = ReconnectOnError<GetNotifyFunctor>(v22, v6);
            if ( i == 14 )
            {
              NotifyPortReconnect((struct _CNOTIFY_SESSION *)Parameter);
              goto LABEL_52;
            }
          }
          else
          {
            TraceMsg(
              4,
              7,
              L"NotifyThread",
              1021,
              L"Unknown session notification version in NotifyThread. Setting Status = ERROR_INVALID_PARAMETER to exit.");
            i = 87;
          }
          v7 = LocalAlloc(0, 0x80u);
          v19 = v7;
          v8 = v7;
          if ( v7 )
            break;
          NotifyPortReconnect((struct _CNOTIFY_SESSION *)Parameter);
          if ( i )
            goto LABEL_52;
        }
        v7[15] = Parameter;
        v7[13] = 0;
        v7[12] = 0;
        v7[10] = 0;
        v7[11] = 0;
        v7[4] = 0;
        v7[8] = 0;
        *((_DWORD *)v7 + 18) = 0;
        *((_DWORD *)v7 + 12) = 0;
        v7[7] = 0;
        v7[3] = 0;
        v7[2] = 0;
        v7[5] = 0;
        v7[14] = 0;
        *((_DWORD *)v7 + 5) = HIDWORD(v24);
        v7[3] = v25;
        v7[4] = v26[0];
        if ( i )
          break;
        if ( *v5 != 1 )
        {
          TraceMsg(
            4,
            7,
            L"NotifyThread",
            1247,
            L"Unknown session notification version in NotifyThread. NotifyThread exiting.");
          return 87;
        }
        ClRtlInsertTailQueue(Parameter[10] + 56LL, v7);
      }
      LODWORD(v18) = i;
      TraceMsg(3, 7, L"NotifyThread", 1050, L"ApiGetNotify on hNotify=0x%p returns %u", *v4, v18);
      if ( i != 259 )
        break;
      if ( !*v4 )
        goto LABEL_25;
      i = 0;
      FreePacket(&v19, (unsigned int)*v5, 0);
      TraceMsg(4, 7, L"NotifyThread", 1060, L"mapping error to success");
    }
    if ( i != 1 )
      break;
    FreePacket(&v19, (unsigned int)*v5, 0);
    if ( !*((_DWORD *)Parameter + 23) )
    {
      TraceMsg(4, 7, L"NotifyThread", 1074, L"Received ERROR_INVALID_FUNCTION in NotifyThread. Going to exit..");
      goto LABEL_52;
    }
    *((_DWORD *)Parameter + 23) = 0;
  }
  if ( i == 87 )
  {
    TraceMsg(4, 7, L"NotifyThread", 1080, L"ERROR_INVALID_PARAMETER detected in NotifyThread, continuing");
    goto LABEL_52;
  }
  if ( *v4 && (*(_BYTE *)(Parameter[6] + 32LL) & 2) == 0 && i != 1722 )
  {
    NotifyPortReconnect((struct _CNOTIFY_SESSION *)Parameter);
    goto LABEL_47;
  }
LABEL_25:
  v9 = (struct _RTL_CRITICAL_SECTION *)(v1 + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 232));
  v10 = *(wchar_t **)(v1 + 16);
  v11 = (__int64 **)(v1 + 152);
  v21 = v10;
  for ( j = *v11; j != (__int64 *)v11; j = (__int64 *)*j )
  {
    if ( (j[3] & 0x20000000) == 0 )
      continue;
    if ( !v8 )
    {
      v8 = LocalAlloc(0, 0x80u);
      v19 = v8;
      if ( !v8 )
      {
        LocalFree(0);
LABEL_45:
        NotifyPortReconnect((struct _CNOTIFY_SESSION *)Parameter);
        break;
      }
      v8[15] = Parameter;
      v8[13] = 0;
      v8[12] = 0;
      v8[10] = 0;
      v8[11] = 0;
      v8[4] = 0;
      v8[8] = 0;
      *((_DWORD *)v8 + 18) = 0;
      *((_DWORD *)v8 + 12) = 0;
      v8[7] = 0;
      v8[3] = 0;
      v8[2] = 0;
      v8[5] = 0;
      v8[14] = 0;
    }
    if ( (unsigned int)MIDLAllocateUnusedStringPacketValuesToEmpty(&v19, (unsigned int)*v5) )
      goto LABEL_45;
    *((_DWORD *)v8 + 4) = 0;
    v20 = 0;
    if ( MylstrlenW(v10, 0x7FFFFFFFu, &v20) )
    {
      TraceMsg(
        4,
        7,
        L"NotifyThread",
        1151,
        L"MystrlenW Failed in NotifyThread, posting reconnect packets and continuing.");
      FreePacket(&v19, (unsigned int)*v5, 0);
      goto LABEL_45;
    }
    if ( *v5 != 1 )
    {
      LeaveCriticalSection(v9);
      TraceMsg(
        4,
        7,
        L"NotifyThread",
        1193,
        L"Unknown session notification version in NotifyThread. NotifyThread exiting.");
      return 87;
    }
    *((_DWORD *)v8 + 6) = 0x20000000;
    *((_DWORD *)v8 + 5) = *((_DWORD *)j + 11);
    v13 = v20 + 1;
    v14 = (wchar_t *)LocalAlloc(0x40u, 2LL * (v20 + 1));
    v8[4] = v14;
    if ( v14 )
    {
      if ( (int)StringCchCopyW(v14, v13, v21) >= 0 )
      {
        TraceMsg(4, 7, L"NotifyThread", 1200, L"Posting CLUSTER_CHANGE_CLUSTER_STATE to notify queue");
        ClRtlInsertTailQueue(Parameter[10] + 56LL, v8);
        goto LABEL_38;
      }
      TraceMsg(
        4,
        7,
        L"NotifyThread",
        1173,
        L"Failed StringCopy in NotifyThread, posting reconnect packets and continuing.");
    }
    LOBYTE(v15) = 0;
    FreePacket(&v19, (unsigned int)*v5, v15);
    NotifyPortReconnect((struct _CNOTIFY_SESSION *)Parameter);
    TraceMsg(4, 7, L"NotifyThread", 1206, L"Filling out packet failed");
LABEL_38:
    v10 = v21;
    v8 = 0;
    v19 = 0;
  }
  LeaveCriticalSection(v9);
  i = 0;
  TraceMsg(4, 7, L"NotifyThread", 1217, L"Cluster is dead, exiting notify thread");
LABEL_47:
  LocalFree(v8);
LABEL_52:
  TraceMsg(4, 7, L"NotifyThread", 1255, L"NotifyThread broken out of loop, exiting.");
  return i;
}

```

## disassembly

```asm
0x18005d0f0  push    rbp
0x18005d0f2  push    rbx
0x18005d0f3  push    rsi
0x18005d0f4  push    rdi
0x18005d0f5  push    r12
0x18005d0f7  push    r13
0x18005d0f9  push    r14
0x18005d0fb  push    r15
0x18005d0fd  lea     rbp, [rsp-28h]
0x18005d102  sub     rsp, 128h
0x18005d109  mov     rax, cs:__security_cookie
0x18005d110  xor     rax, rsp
0x18005d113  mov     [rbp+60h+var_50], rax
0x18005d117  mov     r13, [rcx+30h]
0x18005d11b  mov     rdi, rcx
0x18005d11e  mov     esi, 649h
0x18005d123  xor     r12d, r12d
0x18005d126  lea     r8, aNotifythread; "NotifyThread"
0x18005d12d  mov     edx, 7
0x18005d132  lea     ecx, [rdx-3]
0x18005d135  cmp     [rdi+58h], r12d
0x18005d139  jnz     loc_18005D678
0x18005d13f  xor     eax, eax
0x18005d141  mov     [rbp+60h+var_58], rdi
0x18005d145  mov     [rbp+60h+var_A0], rax
0x18005d149  lea     r15, [rdi+38h]
0x18005d14d  mov     [rbp+60h+var_88], rax
0x18005d151  xorps   xmm0, xmm0
0x18005d154  mov     rax, [r15]
0x18005d157  mov     r9d, 3EEh
0x18005d15d  mov     [rsp+160h+var_138], rax
0x18005d162  lea     rax, aCallingApigetn; "Calling ApiGetNotify, hNotify=0x%p"
0x18005d169  mov     [rsp+160h+var_140], rax
0x18005d16e  movups  [rbp+60h+var_D0], xmm0
0x18005d172  mov     [rbp+60h+var_68], r12
0x18005d176  mov     [rbp+60h+var_70], r12
0x18005d17a  movdqa  [rbp+60h+var_80], xmm0
0x18005d17f  mov     [rbp+60h+var_B0], r12
0x18005d183  mov     [rbp+60h+var_90], r12
0x18005d187  mov     [rbp+60h+var_98], r12
0x18005d18b  mov     [rbp+60h+var_B8], r12
0x18005d18f  mov     [rbp+60h+var_C0], r12
0x18005d193  mov     [rbp+60h+var_A8], r12
0x18005d197  mov     [rbp+60h+var_60], r12
0x18005d19b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d1a0  lea     r14, [rdi+60h]
0x18005d1a4  cmp     dword ptr [r14], 1
0x18005d1a8  jz      short loc_18005D1D7
0x18005d1aa  mov     edx, 7
0x18005d1af  lea     rax, aUnknownSession_0; "Unknown session notification version in"...
0x18005d1b6  mov     r9d, 3FDh
0x18005d1bc  mov     [rsp+160h+var_140], rax
0x18005d1c1  lea     r8, aNotifythread; "NotifyThread"
0x18005d1c8  lea     ecx, [rdx-3]
0x18005d1cb  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d1d0  mov     esi, 57h ; 'W'
0x18005d1d5  jmp     short loc_18005D224
0x18005d1d7  mov     rdx, [rdi+30h]
0x18005d1db  lea     rax, aApigetnotify; "ApiGetNotify"
0x18005d1e2  mov     [rsp+160h+var_108], rax
0x18005d1e7  lea     rcx, [rsp+160h+var_108]
0x18005d1ec  lea     rax, [rbp+60h+var_C0+4]
0x18005d1f0  mov     [rsp+160h+var_100], r15
0x18005d1f5  mov     [rsp+160h+var_F8], rax
0x18005d1fa  lea     rax, [rbp+60h+var_B8]
0x18005d1fe  mov     [rsp+160h+var_F0], rax
0x18005d203  lea     rax, [rbp+60h+var_B8+4]
0x18005d207  mov     [rsp+160h+var_E8], rax
0x18005d20c  lea     rax, [rbp+60h+var_B0]
0x18005d210  mov     [rbp+60h+var_E0], rax
0x18005d214  call    ??$ReconnectOnError@VGetNotifyFunctor@@@@YAKAEAVGetNotifyFunctor@@PEAU_CLUSTER@@@Z; ReconnectOnError<GetNotifyFunctor>(GetNotifyFunctor &,_CLUSTER *)
0x18005d219  mov     esi, eax
0x18005d21b  cmp     eax, 0Eh
0x18005d21e  jz      loc_18005D66E
0x18005d224  mov     edx, 80h; uBytes
0x18005d229  xor     ecx, ecx; uFlags
0x18005d22b  call    cs:__imp_LocalAlloc
0x18005d231  mov     [rsp+160h+var_120], rax
0x18005d236  mov     rbx, rax
0x18005d239  test    rax, rax
0x18005d23c  jnz     short loc_18005D253
0x18005d23e  mov     rcx, rdi; struct _CNOTIFY_SESSION *
0x18005d241  call    ?NotifyPortReconnect@@YAXPEAU_CNOTIFY_SESSION@@@Z; NotifyPortReconnect(_CNOTIFY_SESSION *)
0x18005d246  test    esi, esi
0x18005d248  jz      loc_18005D126
0x18005d24e  jmp     loc_18005D694
0x18005d253  mov     [rax+78h], rdi
0x18005d257  mov     [rax+68h], r12
0x18005d25b  mov     [rax+60h], r12
0x18005d25f  mov     [rax+50h], r12
0x18005d263  mov     [rax+58h], r12
0x18005d267  mov     [rax+20h], r12
0x18005d26b  mov     [rax+40h], r12
0x18005d26f  mov     [rax+48h], r12d
0x18005d273  mov     [rax+30h], r12d
0x18005d277  mov     [rax+38h], r12
0x18005d27b  mov     [rax+18h], r12
0x18005d27f  mov     [rax+10h], r12
0x18005d283  mov     [rax+28h], r12
0x18005d287  mov     [rax+70h], r12
0x18005d28b  mov     eax, dword ptr [rbp+60h+var_C0+4]
0x18005d28e  mov     [rbx+14h], eax
0x18005d291  mov     eax, dword ptr [rbp+60h+var_B8]
0x18005d294  mov     [rbx+18h], eax
0x18005d297  mov     eax, dword ptr [rbp+60h+var_B8+4]
0x18005d29a  mov     [rbx+1Ch], eax
0x18005d29d  mov     rax, [rbp+60h+var_B0]
0x18005d2a1  mov     [rbx+20h], rax
0x18005d2a5  test    esi, esi
0x18005d2a7  jz      loc_18005D355
0x18005d2ad  mov     rax, [r15]
0x18005d2b0  lea     r8, aNotifythread; "NotifyThread"
0x18005d2b7  mov     edx, 7
0x18005d2bc  mov     [rsp+160h+var_130], esi
0x18005d2c0  mov     [rsp+160h+var_138], rax
0x18005d2c5  mov     r9d, 41Ah
0x18005d2cb  lea     rax, aApigetnotifyOn; "ApiGetNotify on hNotify=0x%p returns %u"
0x18005d2d2  mov     [rsp+160h+var_140], rax
0x18005d2d7  lea     ecx, [rdx-4]
0x18005d2da  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d2df  cmp     esi, 103h
0x18005d2e5  jnz     short loc_18005D32E
0x18005d2e7  cmp     [r15], r12
0x18005d2ea  jz      loc_18005D3CC
0x18005d2f0  mov     edx, [r14]
0x18005d2f3  lea     rcx, [rsp+160h+var_120]
0x18005d2f8  xor     r8d, r8d
0x18005d2fb  mov     esi, r12d
0x18005d2fe  call    ?FreePacket@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@_N@Z; FreePacket(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION,bool)
0x18005d303  mov     edx, 7
0x18005d308  lea     rax, aMappingErrorTo; "mapping error to success"
0x18005d30f  mov     r9d, 424h
0x18005d315  mov     [rsp+160h+var_140], rax
0x18005d31a  lea     r8, aNotifythread; "NotifyThread"
0x18005d321  lea     ecx, [rdx-3]
0x18005d324  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d329  jmp     loc_18005D126
0x18005d32e  cmp     esi, 1
0x18005d331  jnz     short loc_18005D39F
0x18005d333  mov     edx, [r14]
0x18005d336  lea     rcx, [rsp+160h+var_120]
0x18005d33b  xor     r8d, r8d
0x18005d33e  call    ?FreePacket@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@_N@Z; FreePacket(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION,bool)
0x18005d343  cmp     [rdi+5Ch], r12d
0x18005d347  jz      short loc_18005D374
0x18005d349  mov     [rdi+5Ch], r12d
0x18005d34d  mov     esi, r12d
0x18005d350  jmp     loc_18005D126
0x18005d355  cmp     dword ptr [r14], 1
0x18005d359  jnz     loc_18005D657
0x18005d35f  mov     rcx, [rdi+50h]
0x18005d363  mov     rdx, rbx
0x18005d366  add     rcx, 38h ; '8'
0x18005d36a  call    ClRtlInsertTailQueue
0x18005d36f  jmp     loc_18005D126
0x18005d374  lea     rax, aReceivedErrorI; "Received ERROR_INVALID_FUNCTION in Noti"...
0x18005d37b  mov     r9d, 432h
0x18005d381  mov     edx, 7
0x18005d386  mov     [rsp+160h+var_140], rax
0x18005d38b  lea     r8, aNotifythread; "NotifyThread"
0x18005d392  lea     ecx, [rdx-3]
0x18005d395  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d39a  jmp     loc_18005D694
0x18005d39f  cmp     esi, 57h ; 'W'
0x18005d3a2  jz      loc_18005D645
0x18005d3a8  cmp     [r15], r12
0x18005d3ab  jz      short loc_18005D3CC
0x18005d3ad  mov     rax, [rdi+30h]
0x18005d3b1  test    byte ptr [rax+20h], 2
0x18005d3b5  jnz     short loc_18005D3CC
0x18005d3b7  cmp     esi, 6BAh
0x18005d3bd  jz      short loc_18005D3CC
0x18005d3bf  mov     rcx, rdi; struct _CNOTIFY_SESSION *
0x18005d3c2  call    ?NotifyPortReconnect@@YAXPEAU_CNOTIFY_SESSION@@@Z; NotifyPortReconnect(_CNOTIFY_SESSION *)
0x18005d3c7  jmp     loc_18005D63A
0x18005d3cc  lea     r12, [r13+0E8h]
0x18005d3d3  mov     rcx, r12; lpCriticalSection
0x18005d3d6  call    cs:__imp_EnterCriticalSection
0x18005d3dc  mov     r15, [r13+10h]
0x18005d3e0  add     r13, 98h
0x18005d3e7  mov     [rsp+160h+var_110], r15
0x18005d3ec  mov     rsi, [r13+0]
0x18005d3f0  cmp     rsi, r13
0x18005d3f3  jz      loc_18005D60B
0x18005d3f9  test    dword ptr [rsi+18h], 20000000h
0x18005d400  jz      loc_18005D558
0x18005d406  test    rbx, rbx
0x18005d409  jnz     short loc_18005D461
0x18005d40b  mov     edx, 80h; uBytes
0x18005d410  xor     ecx, ecx; uFlags
0x18005d412  call    cs:__imp_LocalAlloc
0x18005d418  mov     rbx, rax
0x18005d41b  mov     [rsp+160h+var_120], rax
0x18005d420  xor     eax, eax
0x18005d422  test    rbx, rbx
0x18005d425  jz      loc_18005D589
0x18005d42b  mov     [rbx+78h], rdi
0x18005d42f  mov     [rbx+68h], rax
0x18005d433  mov     [rbx+60h], rax
0x18005d437  mov     [rbx+50h], rax
0x18005d43b  mov     [rbx+58h], rax
0x18005d43f  mov     [rbx+20h], rax
0x18005d443  mov     [rbx+40h], rax
0x18005d447  mov     [rbx+48h], eax
0x18005d44a  mov     [rbx+30h], eax
0x18005d44d  mov     [rbx+38h], rax
0x18005d451  mov     [rbx+18h], rax
0x18005d455  mov     [rbx+10h], rax
0x18005d459  mov     [rbx+28h], rax
0x18005d45d  mov     [rbx+70h], rax
0x18005d461  mov     edx, [r14]
0x18005d464  lea     rcx, [rsp+160h+var_120]
0x18005d469  call    ?MIDLAllocateUnusedStringPacketValuesToEmpty@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@@Z; MIDLAllocateUnusedStringPacketValuesToEmpty(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION)
0x18005d46e  test    eax, eax
0x18005d470  jnz     loc_18005D603
0x18005d476  lea     r8, [rsp+160h+var_118]; unsigned int *
0x18005d47b  mov     [rbx+10h], eax
0x18005d47e  mov     edx, 7FFFFFFFh; unsigned int
0x18005d483  mov     [rsp+160h+var_118], eax
0x18005d487  mov     rcx, r15; wchar_t *
0x18005d48a  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18005d48f  test    eax, eax
0x18005d491  jnz     loc_18005D5CD
0x18005d497  cmp     dword ptr [r14], 1
0x18005d49b  jnz     loc_18005D594
0x18005d4a1  mov     dword ptr [rbx+18h], 20000000h
0x18005d4a8  mov     ecx, 40h ; '@'; uFlags
0x18005d4ad  mov     eax, [rsi+2Ch]
0x18005d4b0  mov     [rbx+14h], eax
0x18005d4b3  mov     eax, [rsp+160h+var_118]
0x18005d4b7  inc     eax
0x18005d4b9  mov     r15d, eax
0x18005d4bc  lea     rdx, [rax+rax]; uBytes
0x18005d4c0  call    cs:__imp_LocalAlloc
0x18005d4c6  mov     [rbx+20h], rax
0x18005d4ca  test    rax, rax
0x18005d4cd  jz      short loc_18005D509
0x18005d4cf  mov     r8, [rsp+160h+var_110]; wchar_t *
0x18005d4d4  mov     edx, r15d; unsigned __int64
0x18005d4d7  mov     rcx, rax; wchar_t *
0x18005d4da  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18005d4df  lea     r8, aNotifythread; "NotifyThread"
0x18005d4e6  mov     edx, 7
0x18005d4eb  lea     ecx, [rdx-3]
0x18005d4ee  test    eax, eax
0x18005d4f0  jns     short loc_18005D560
0x18005d4f2  lea     rax, aFailedStringco; "Failed StringCopy in NotifyThread, post"...
0x18005d4f9  mov     r9d, 495h
0x18005d4ff  mov     [rsp+160h+var_140], rax
0x18005d504  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d509  mov     rdx, r14
0x18005d50c  lea     rcx, [rsp+160h+var_120]
0x18005d511  xor     r8b, r8b
0x18005d514  mov     rbx, rdi
0x18005d517  mov     edx, [rdx]
0x18005d519  call    ?FreePacket@@YAKAEAPEAU_CNOTIFY_PACKET@@W4CLUSTER_NOTIFICATIONS_VERSION@@_N@Z; FreePacket(_CNOTIFY_PACKET * &,CLUSTER_NOTIFICATIONS_VERSION,bool)
0x18005d51e  mov     rcx, rbx; struct _CNOTIFY_SESSION *
0x18005d521  call    ?NotifyPortReconnect@@YAXPEAU_CNOTIFY_SESSION@@@Z; NotifyPortReconnect(_CNOTIFY_SESSION *)
0x18005d526  mov     edx, 7
0x18005d52b  lea     rax, aFillingOutPack; "Filling out packet failed"
0x18005d532  mov     r9d, 4B6h
0x18005d538  mov     [rsp+160h+var_140], rax
0x18005d53d  lea     r8, aNotifythread; "NotifyThread"
0x18005d544  lea     ecx, [rdx-3]
0x18005d547  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d54c  mov     r15, [rsp+160h+var_110]
0x18005d551  xor     ebx, ebx
0x18005d553  mov     [rsp+160h+var_120], rbx
0x18005d558  mov     rsi, [rsi]
0x18005d55b  jmp     loc_18005D3F0
0x18005d560  lea     rax, aPostingCluster_0; "Posting CLUSTER_CHANGE_CLUSTER_STATE to"...
0x18005d567  mov     r9d, 4B0h
0x18005d56d  mov     [rsp+160h+var_140], rax
0x18005d572  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d577  mov     rcx, [rdi+50h]
0x18005d57b  mov     rdx, rbx
0x18005d57e  add     rcx, 38h ; '8'
0x18005d582  call    ClRtlInsertTailQueue
0x18005d587  jmp     short loc_18005D54C
0x18005d589  mov     rcx, rbx; hMem
0x18005d58c  call    cs:__imp_LocalFree
0x18005d592  jmp     short loc_18005D603
0x18005d594  mov     rcx, r12; lpCriticalSection
0x18005d597  call    cs:__imp_LeaveCriticalSection
0x18005d59d  lea     r9, aUnknownSession; "Unknown session notification version in"...
0x18005d5a4  mov     [rsp+160h+var_140], r9
0x18005d5a9  mov     r9d, 4A9h
0x18005d5af  mov     edx, 7
0x18005d5b4  lea     r8, aNotifythread; "NotifyThread"
0x18005d5bb  lea     ecx, [rdx-3]
0x18005d5be  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005d5c3  mov     eax, 57h ; 'W'
0x18005d5c8  jmp     loc_18005D6BC
0x18005d5cd  mov     edx, 7
0x18005d5d2  lea     rax, aMystrlenwFaile; "MystrlenW Failed in NotifyThread, posti"...
0x18005d5d9  mov     r9d, 47Fh
0x18005d5df  mov     [rsp+160h+var_140], rax
0x18005d5e4  lea     r8, aNotifythread; "NotifyThread"
0x18005d5eb  lea     ecx, [rdx-3]
0x18005d5ee  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
  ... truncated ...
```
