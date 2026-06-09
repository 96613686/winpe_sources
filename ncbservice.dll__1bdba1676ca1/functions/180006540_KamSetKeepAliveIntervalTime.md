# KamSetKeepAliveIntervalTime

- ea: `0x180006540`
- end: `0x180006ea8`
- name: `KamSetKeepAliveIntervalTime`
- size: `2408`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cae0`
- `0x180014430`

## callees

- `0x180001c48`
- `0x180002994`
- `0x180005120`
- `0x180005490`
- `0x180006050`
- `0x18000624c`
- `0x180006540`
- `0x180008920`
- `0x18000a0a0`
- `0x18000a160`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`
- `0x180020538`
- `0x1800205b4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000670c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000670c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800066ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006760`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800067c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800066ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006760`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800067c8`

## string_xrefs

- `0x180006c2a`: `Kam: Nlm cache stored retrieval happened with status -`
- `0x180006e5a`: `Kam:KampCreateTimeEvent for keepalive failed with`
- `0x18000683f`: `Kam:KampUpdateTimeEventHelper for keepalive failed with`

## pseudocode

```c
__int64 __fastcall KamSetKeepAliveIntervalTime(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int NlmCacheKey; // eax
  unsigned int v8; // edi
  char v9; // si
  unsigned int *v10; // rdi
  LPCRITICAL_SECTION v11; // r15
  PVOID *v12; // rcx
  unsigned int CurrentSignature; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // edi
  unsigned int StoredValue; // eax
  __int64 v18; // r8
  unsigned int v19; // edi
  PVOID v20; // rcx
  unsigned int v21; // edx
  unsigned int v22; // eax
  int v23; // r8d
  PVOID *v24; // rcx
  unsigned int TimeEvent; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // r8
  unsigned int updated; // eax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  unsigned int v36; // edx
  int v37; // ecx
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 v42; // r9
  unsigned int v43; // [rsp+40h] [rbp-69h] BYREF
  __int64 v44; // [rsp+48h] [rbp-61h] BYREF
  int v45; // [rsp+50h] [rbp-59h] BYREF
  int v46; // [rsp+58h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+60h] [rbp-49h] BYREF
  const wchar_t *v48; // [rsp+70h] [rbp-39h]
  __int64 v49; // [rsp+78h] [rbp-31h]
  __int64 *v50; // [rsp+80h] [rbp-29h]
  __int64 v51; // [rsp+88h] [rbp-21h]
  int *v52; // [rsp+90h] [rbp-19h]
  __int64 v53; // [rsp+98h] [rbp-11h]
  int *v54; // [rsp+A0h] [rbp-9h]
  __int64 v55; // [rsp+A8h] [rbp-1h]
  __int64 *v56; // [rsp+B0h] [rbp+7h]
  __int64 v57; // [rsp+B8h] [rbp+Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_ddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      a3,
      a2,
      *(_DWORD *)(a1 + 372),
      g_KamFloorTime,
      *(_DWORD *)(a1 + 368));
  }
  v44 = 0;
  if ( _InterlockedCompareExchange(&g_KamInitialized, 0, 0) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
    if ( a2 - 15 > 0x590 )
    {
      v8 = 87;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v6, v5, L"Kam: bad keepalive interval provided ", a2);
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_35;
      }
      v34 = 53;
LABEL_84:
      v35 = v8;
      goto LABEL_85;
    }
    *(_DWORD *)(a1 + 368) = a2;
    NlmCacheKey = KampMakeNlmCacheKey(a1);
    v8 = NlmCacheKey;
    if ( NlmCacheKey )
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_35;
      }
      v34 = 54;
      v35 = NlmCacheKey;
LABEL_85:
      WPP_SF_d(v33[2], v34, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v35);
LABEL_35:
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        LODWORD(v44) = v8;
        v48 = L"Kam: set keepalive interval";
        v49 = 56;
        v50 = &v44;
        v51 = 4;
        McGenEventWrite_EventWriteTransfer(v29, (const EVENT_DESCRIPTOR *)NcbApiStatus, v30, 3u, &v47);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v8);
      }
      return v8;
    }
    v9 = 0;
    EnterCriticalSection(&g_NlmSignatureLock);
    v10 = (unsigned int *)g_NlmSignature;
    if ( !g_NlmSignature )
    {
LABEL_17:
      CurrentSignature = StubNlmCacheGetCurrentSignature(g_NlmCache, &g_NlmSignature);
      v16 = CurrentSignature;
      if ( CurrentSignature )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v15, v14, L"Kam: could not get current NLM signature", CurrentSignature);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v16);
        }
      }
      else
      {
        StoredValue = StubNlmCacheRetrieveStoredValue(g_NlmCache, 4, (__int64)&v44);
        v19 = StoredValue;
        if ( StoredValue )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids,
              StoredValue);
          }
        }
        else
        {
          v9 = 1;
          *(_DWORD *)(a1 + 376) = *(_DWORD *)v44;
          StubNlmCacheFreeValue(g_NlmCache);
        }
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v43 = v19;
          v48 = L"Kam: Nlm cache stored retrieval happened with status -";
          v49 = 110;
          v50 = (__int64 *)&v43;
          v51 = 4;
          McGenEventWrite_EventWriteTransfer((__int64)v20, (const EVENT_DESCRIPTOR *)NcbApiStatus, v18, 3u, &v47);
        }
      }
      LeaveCriticalSection(&g_NlmSignatureLock);
      EnterCriticalSection(&g_NlmSignatureLock);
      if ( g_NlmSignature && (unsigned int)StubNlmCacheContainsMbbNetwork() )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
        }
        v36 = *(_DWORD *)(a1 + 368);
        v37 = g_Twns;
        v38 = g_Twns;
        if ( v36 < g_Twns )
          v38 = *(_DWORD *)(a1 + 368);
        if ( g_KamFloorTime <= v38 )
        {
          v39 = g_Twns;
          if ( v36 < g_Twns )
            v39 = *(_DWORD *)(a1 + 368);
        }
        else
        {
          v39 = g_KamFloorTime;
        }
        v23 = g_KamFloorTimeOnCell;
        if ( g_KamFloorTimeOnCell <= v39 )
        {
          v40 = g_Twns;
          if ( v36 < g_Twns )
            v40 = *(_DWORD *)(a1 + 368);
          if ( g_KamFloorTime <= v40 )
          {
            if ( v36 < g_Twns )
              v37 = *(_DWORD *)(a1 + 368);
            v23 = v37;
          }
          else
          {
            v23 = g_KamFloorTime;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
        }
        v21 = *(_DWORD *)(a1 + 368);
        v22 = g_Twns;
        v23 = g_KamFloorTime;
        if ( v21 < g_Twns )
          v22 = *(_DWORD *)(a1 + 368);
        if ( g_KamFloorTime <= v22 )
        {
          v23 = g_Twns;
          if ( v21 < g_Twns )
            v23 = *(_DWORD *)(a1 + 368);
        }
      }
      *(_DWORD *)(a1 + 372) = v23;
      LeaveCriticalSection(&g_NlmSignatureLock);
      v24 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids,
          *(unsigned int *)(a1 + 372));
        v24 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v9 )
      {
        v41 = *(_DWORD *)(a1 + 372);
        v42 = *(unsigned int *)(a1 + 376);
        if ( (unsigned int)v42 >= v41 )
          v42 = v41;
        *(_DWORD *)(a1 + 372) = v42;
        v24 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v42);
          v24 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      if ( *(_BYTE *)(a1 + 361) )
      {
        if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 && *((_BYTE *)v24 + 25) >= 5u )
          WPP_SF_(v24[2], 63, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
        updated = KampUpdateTimeEventHelper(a1);
        v8 = updated;
        if ( !updated )
          goto LABEL_32;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            v27,
            v26,
            L"Kam:KampUpdateTimeEventHelper for keepalive failed with",
            updated);
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_35;
        }
        v34 = 64;
      }
      else
      {
        if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 && *((_BYTE *)v24 + 25) >= 5u )
          WPP_SF_(v24[2], 61, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
        TimeEvent = KampCreateTimeEvent(a1);
        v8 = TimeEvent;
        if ( !TimeEvent )
        {
LABEL_32:
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 4) != 0 )
          {
            LODWORD(v44) = g_Twns;
            v46 = *(_DWORD *)(a1 + 376);
            v45 = *(_DWORD *)(a1 + 372);
            v43 = *(_DWORD *)(a1 + 368);
            v48 = L"Kam:SetKeepaliveInterval";
            v50 = (__int64 *)&v43;
            v52 = &v45;
            v54 = &v46;
            v56 = &v44;
            v49 = 50;
            v51 = 4;
            v53 = 4;
            v55 = 4;
            v57 = 4;
            McGenEventWrite_EventWriteTransfer(v27, (const EVENT_DESCRIPTOR *)NcbKamTimerUpdate, v28, 6u, &v47);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_dddd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v26,
              v28,
              *(unsigned int *)(a1 + 368),
              *(_DWORD *)(a1 + 372),
              *(_DWORD *)(a1 + 376));
          }
          goto LABEL_35;
        }
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v27, v26, L"Kam:KampCreateTimeEvent for keepalive failed with", TimeEvent);
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_35;
        }
        v34 = 62;
      }
      goto LABEL_84;
    }
    v11 = g_NlmCache;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
      }
      if ( *((_QWORD *)v10 + 1) )
        (*(void (**)(void))&v11[1].LockCount)();
      (*(void (__fastcall **)(unsigned int *))&v11[1].LockCount)(v10);
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_16:
        g_NlmSignature = 0;
        goto LABEL_17;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
LABEL_14:
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 6u )
          WPP_SF_(v12[2], 22, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
        goto LABEL_16;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids, *v10);
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, 21);
  }
  return 21;
}

```

## disassembly

```asm
0x180006540  push    rbp
0x180006542  push    rbx
0x180006543  push    rsi
0x180006544  push    r12
0x180006546  push    r13
0x180006548  lea     rbp, [rsp-37h]
0x18000654d  sub     rsp, 0E0h
0x180006554  mov     rax, cs:__security_cookie
0x18000655b  xor     rax, rsp
0x18000655e  mov     [rbp+57h+var_40], rax
0x180006562  mov     esi, edx
0x180006564  mov     rbx, rcx
0x180006567  mov     rcx, cs:WPP_GLOBAL_Control
0x18000656e  lea     r12, WPP_GLOBAL_Control
0x180006575  cmp     rcx, r12
0x180006578  jnz     loc_180006A2C
0x18000657e  xor     r13d, r13d
0x180006581  mov     [rbp+57h+var_B8], r13
0x180006585  mov     ecx, r13d
0x180006588  xor     eax, eax
0x18000658a  lock cmpxchg cs:g_KamInitialized, ecx
0x180006592  jz      loc_180006CEC
0x180006598  mov     [rsp+100h+arg_10], rdi
0x1800065a0  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800065a4  mov     [rsp+100h+var_28], r14
0x1800065ac  call    cs:__imp_EnterCriticalSection
0x1800065b2  lea     eax, [rsi-0Fh]
0x1800065b5  cmp     eax, 590h
0x1800065ba  ja      loc_180006AFB
0x1800065c0  mov     rcx, rbx
0x1800065c3  mov     [rbx+170h], esi
0x1800065c9  call    KampMakeNlmCacheKey
0x1800065ce  mov     edi, eax
0x1800065d0  test    eax, eax
0x1800065d2  jnz     loc_180006D29
0x1800065d8  lea     rcx, g_NlmSignatureLock; lpCriticalSection
0x1800065df  xor     sil, sil
0x1800065e2  call    cs:__imp_EnterCriticalSection
0x1800065e8  mov     rdi, cs:g_NlmSignature
0x1800065ef  test    rdi, rdi
0x1800065f2  jz      loc_180006682
0x1800065f8  mov     [rsp+100h+var_30], r15
0x180006600  mov     r15, cs:g_NlmCache
0x180006607  mov     rcx, cs:WPP_GLOBAL_Control
0x18000660e  cmp     rcx, r12
0x180006611  jnz     loc_180006941
0x180006617  mov     eax, 0FFFFFFFFh
0x18000661c  lock xadd [rdi], eax
0x180006620  cmp     eax, 1
0x180006623  jnz     loc_18000696F
0x180006629  mov     rcx, cs:WPP_GLOBAL_Control
0x180006630  cmp     rcx, r12
0x180006633  jz      short loc_18000663F
0x180006635  test    byte ptr [rcx+1Ch], 4
0x180006639  jnz     loc_180006D5A
0x18000663f  mov     rcx, [rdi+8]
0x180006643  test    rcx, rcx
0x180006646  jz      short loc_180006651
0x180006648  mov     rax, [r15+30h]
0x18000664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006651  mov     rax, [r15+30h]
0x180006655  mov     rcx, rdi
0x180006658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000665d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006664  cmp     rcx, r12
0x180006667  jz      short loc_180006673
0x180006669  test    byte ptr [rcx+1Ch], 4
0x18000666d  jnz     loc_180006D7E
0x180006673  mov     r15, [rsp+100h+var_30]
0x18000667b  mov     cs:g_NlmSignature, r13
0x180006682  mov     rcx, cs:g_NlmCache
0x180006689  lea     rdx, g_NlmSignature
0x180006690  call    StubNlmCacheGetCurrentSignature
0x180006695  mov     edi, eax
0x180006697  test    eax, eax
0x180006699  jnz     loc_1800069B0
0x18000669f  mov     r9, [rbx+180h]
0x1800066a6  lea     rax, [rbp+57h+var_B8]
0x1800066aa  mov     r8d, [rbx+188h]
0x1800066b1  mov     rdx, cs:g_NlmSignature
0x1800066b8  mov     rcx, cs:g_NlmCache; lpCriticalSection
0x1800066bf  mov     [rsp+100h+var_D8], rax; __int64
0x1800066c4  mov     [rsp+100h+var_E0], 4; int
0x1800066cc  call    StubNlmCacheRetrieveStoredValue
0x1800066d1  mov     edi, eax
0x1800066d3  test    eax, eax
0x1800066d5  jz      loc_180006C70
0x1800066db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066e2  cmp     rcx, r12
0x1800066e5  jnz     loc_180006B94
0x1800066eb  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800066f2  jnz     loc_180006C2A
0x1800066f8  lea     rcx, g_NlmSignatureLock; lpCriticalSection
0x1800066ff  call    cs:__imp_LeaveCriticalSection
0x180006705  lea     rcx, g_NlmSignatureLock; lpCriticalSection
0x18000670c  call    cs:__imp_EnterCriticalSection
0x180006712  cmp     cs:g_NlmSignature, r13
0x180006719  jnz     loc_180006BC5
0x18000671f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006726  cmp     rcx, r12
0x180006729  jnz     loc_1800069FE
0x18000672f  mov     edx, [rbx+170h]
0x180006735  mov     ecx, cs:g_Twns
0x18000673b  mov     eax, ecx
0x18000673d  mov     r8d, cs:g_KamFloorTime
0x180006744  cmp     edx, ecx
0x180006746  cmovb   eax, edx
0x180006749  cmp     r8d, eax
0x18000674c  jbe     loc_180006A74
0x180006752  lea     rcx, g_NlmSignatureLock; lpCriticalSection
0x180006759  mov     [rbx+174h], r8d
0x180006760  call    cs:__imp_LeaveCriticalSection
0x180006766  mov     rcx, cs:WPP_GLOBAL_Control
0x18000676d  cmp     rcx, r12
0x180006770  jnz     loc_180006ABF
0x180006776  test    sil, sil
0x180006779  jnz     loc_180006DEE
0x18000677f  cmp     [rbx+169h], r13b
0x180006786  jnz     loc_180006818
0x18000678c  cmp     rcx, r12
0x18000678f  jnz     loc_180006C90
0x180006795  mov     rcx, rbx
0x180006798  call    KampCreateTimeEvent
0x18000679d  mov     edi, eax
0x18000679f  test    eax, eax
0x1800067a1  jnz     loc_180006E4E
0x1800067a7  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 4
0x1800067ae  jnz     loc_180006879
0x1800067b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067bb  cmp     rcx, r12
0x1800067be  jnz     loc_180006A82
0x1800067c4  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800067c8  call    cs:__imp_LeaveCriticalSection
0x1800067ce  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800067d5  mov     r14, [rsp+100h+var_28]
0x1800067dd  jnz     loc_180006B4E
0x1800067e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067ea  cmp     rcx, r12
0x1800067ed  jnz     loc_180006910
0x1800067f3  mov     eax, edi
0x1800067f5  mov     rdi, [rsp+100h+arg_10]
0x1800067fd  mov     rcx, [rbp+57h+var_40]
0x180006801  xor     rcx, rsp; StackCookie
0x180006804  call    __security_check_cookie
0x180006809  add     rsp, 0E0h
0x180006810  pop     r13
0x180006812  pop     r12
0x180006814  pop     rsi
0x180006815  pop     rbx
0x180006816  pop     rbp
0x180006817  retn
0x180006818  cmp     rcx, r12
0x18000681b  jnz     loc_180006CBE
0x180006821  mov     rcx, rbx
0x180006824  call    KampUpdateTimeEventHelper
0x180006829  mov     edi, eax
0x18000682b  test    eax, eax
0x18000682d  jz      loc_1800067A7
0x180006833  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000683a  jz      short loc_18000684B
0x18000683c  mov     r9d, eax
0x18000683f  lea     r8, aKamKampupdatet_0; "Kam:KampUpdateTimeEventHelper for keepa"...
0x180006846  call    McTemplateU0zq_EventWriteTransfer
0x18000684b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006852  cmp     rcx, r12
0x180006855  jz      loc_1800067C4
0x18000685b  test    byte ptr [rcx+1Ch], 1
0x18000685f  jz      loc_1800067C4
0x180006865  cmp     byte ptr [rcx+19h], 2
0x180006869  jb      loc_1800067C4
0x18000686f  mov     edx, 40h ; '@'
0x180006874  jmp     loc_180006B36
0x180006879  mov     eax, cs:g_Twns
0x18000687f  lea     rdx, NcbKamTimerUpdate
0x180006886  mov     dword ptr [rbp+57h+var_B8], eax
0x180006889  mov     r9d, 6
0x18000688f  mov     eax, [rbx+178h]
0x180006895  mov     [rbp+57h+var_A8], eax
0x180006898  mov     eax, [rbx+174h]
0x18000689e  mov     [rbp+57h+var_B0], eax
0x1800068a1  mov     eax, [rbx+170h]
0x1800068a7  mov     [rbp+57h+var_C0], eax
0x1800068aa  lea     rax, aKamSetkeepaliv; "Kam:SetKeepaliveInterval"
0x1800068b1  mov     [rbp+57h+var_90], rax
0x1800068b5  lea     rax, [rbp+57h+var_C0]
0x1800068b9  mov     [rbp+57h+var_80], rax
0x1800068bd  lea     rax, [rbp+57h+var_B0]
0x1800068c1  mov     [rbp+57h+var_70], rax
0x1800068c5  lea     rax, [rbp+57h+var_A8]
0x1800068c9  mov     [rbp+57h+var_60], rax
0x1800068cd  lea     rax, [rbp+57h+var_B8]
0x1800068d1  mov     [rbp+57h+var_50], rax
0x1800068d5  lea     rax, [rbp+57h+var_A0]
0x1800068d9  mov     qword ptr [rsp+100h+var_E0], rax
0x1800068de  mov     [rbp+57h+var_88], 32h ; '2'
0x1800068e6  mov     [rbp+57h+var_78], 4
0x1800068ee  mov     [rbp+57h+var_68], 4
0x1800068f6  mov     [rbp+57h+var_58], 4
0x1800068fe  mov     [rbp+57h+var_48], 4
0x180006906  call    McGenEventWrite_EventWriteTransfer
0x18000690b  jmp     loc_1800067B4
0x180006910  test    byte ptr [rcx+1Ch], 1
0x180006914  jz      loc_1800067F3
0x18000691a  cmp     byte ptr [rcx+19h], 6
0x18000691e  jb      loc_1800067F3
0x180006924  mov     rcx, [rcx+10h]
0x180006928  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x18000692f  mov     edx, 42h ; 'B'
0x180006934  mov     r9d, edi
0x180006937  call    WPP_SF_d
0x18000693c  jmp     loc_1800067F3
0x180006941  test    byte ptr [rcx+1Ch], 4
0x180006945  jz      loc_180006617
0x18000694b  cmp     byte ptr [rcx+19h], 6
0x18000694f  jb      loc_180006617
0x180006955  mov     rcx, [rcx+10h]
0x180006959  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x180006960  mov     edx, 13h
0x180006965  call    WPP_SF_
0x18000696a  jmp     loc_180006617
0x18000696f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006976  cmp     rcx, r12
0x180006979  jz      loc_180006673
0x18000697f  test    byte ptr [rcx+1Ch], 4
0x180006983  jz      loc_180006664
0x180006989  cmp     byte ptr [rcx+19h], 5
0x18000698d  jb      loc_180006664
0x180006993  mov     r9d, [rdi]
0x180006996  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18000699d  mov     rcx, [rcx+10h]
0x1800069a1  mov     edx, 15h
0x1800069a6  call    WPP_SF_d
0x1800069ab  jmp     loc_18000665D
0x1800069b0  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800069b7  jnz     loc_180006DA2
0x1800069bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069c4  cmp     rcx, r12
0x1800069c7  jz      loc_1800066F8
0x1800069cd  test    byte ptr [rcx+1Ch], 1
0x1800069d1  jz      loc_1800066F8
0x1800069d7  cmp     byte ptr [rcx+19h], 2
0x1800069db  jb      loc_1800066F8
0x1800069e1  mov     rcx, [rcx+10h]
0x1800069e5  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800069ec  mov     edx, 38h ; '8'
0x1800069f1  mov     r9d, edi
0x1800069f4  call    WPP_SF_d
0x1800069f9  jmp     loc_1800066F8
0x1800069fe  test    byte ptr [rcx+1Ch], 1
0x180006a02  jz      loc_18000672F
0x180006a08  cmp     byte ptr [rcx+19h], 5
0x180006a0c  jb      loc_18000672F
0x180006a12  mov     rcx, [rcx+10h]
0x180006a16  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180006a1d  mov     edx, 3Ah ; ':'
0x180006a22  call    WPP_SF_
0x180006a27  jmp     loc_18000672F
0x180006a2c  test    byte ptr [rcx+1Ch], 1
0x180006a30  jz      loc_18000657E
0x180006a36  cmp     byte ptr [rcx+19h], 6
0x180006a3a  jb      loc_18000657E
0x180006a40  mov     eax, [rbx+170h]
0x180006a46  mov     edx, 33h ; '3'
0x180006a4b  mov     rcx, [rcx+10h]
0x180006a4f  mov     r9d, esi
0x180006a52  mov     [rsp+100h+var_D0], eax
0x180006a56  mov     eax, cs:g_KamFloorTime
0x180006a5c  mov     dword ptr [rsp+100h+var_D8], eax
0x180006a60  mov     eax, [rbx+174h]
0x180006a66  mov     [rsp+100h+var_E0], eax
0x180006a6a  call    WPP_SF_ddddd
0x180006a6f  jmp     loc_18000657E
0x180006a74  cmp     edx, ecx
0x180006a76  mov     r8d, ecx
0x180006a79  cmovb   r8d, edx
0x180006a7d  jmp     loc_180006752
0x180006a82  test    byte ptr [rcx+1Ch], 1
0x180006a86  jz      loc_1800067C4
0x180006a8c  cmp     byte ptr [rcx+19h], 5
0x180006a90  jb      loc_1800067C4
0x180006a96  mov     eax, [rbx+178h]
0x180006a9c  mov     r9d, [rbx+170h]
0x180006aa3  mov     rcx, [rcx+10h]
0x180006aa7  mov     dword ptr [rsp+100h+var_D8], eax
0x180006aab  mov     eax, [rbx+174h]
0x180006ab1  mov     [rsp+100h+var_E0], eax
0x180006ab5  call    WPP_SF_dddd
0x180006aba  jmp     loc_1800067C4
0x180006abf  test    byte ptr [rcx+1Ch], 1
0x180006ac3  jz      loc_180006776
0x180006ac9  cmp     byte ptr [rcx+19h], 5
0x180006acd  jb      loc_180006776
0x180006ad3  mov     r9d, [rbx+174h]
0x180006ada  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180006ae1  mov     rcx, [rcx+10h]
0x180006ae5  mov     edx, 3Bh ; ';'
0x180006aea  call    WPP_SF_d
0x180006aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180006af6  jmp     loc_180006776
0x180006afb  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
  ... truncated ...
```
