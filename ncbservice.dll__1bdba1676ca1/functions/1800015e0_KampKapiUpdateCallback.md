# KampKapiUpdateCallback

- ea: `0x1800015e0`
- end: `0x180001af6`
- name: `KampKapiUpdateCallback`
- size: `1302`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800015e0`
- `0x180001afc`
- `0x180001c48`
- `0x180005120`
- `0x18000a160`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`
- `0x1800205b4`

## import_xrefs

- `ntdll!RtlInitEnumerationHashTable` at `0x180001674`
- `ntdll!RtlInitEnumerationHashTable` at `0x180001674`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800017a7`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800017a7`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180001686`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180001779`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180001686`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180001779`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001662`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800016b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800016cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001662`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800016b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800016cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001738`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001738`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001767`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800017cc`

## string_xrefs

- `0x1800017db`: `Kam: processed kapi update`
- `0x1800016a8`: `Kam:KapiUpdateCallback`

## pseudocode

```c
void __fastcall KampKapiUpdateCallback(unsigned int a1)
{
  __int64 i; // rdi
  unsigned int v3; // edx
  unsigned int v4; // eax
  unsigned int v5; // r9d
  unsigned int v6; // eax
  int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // r8
  SocketBrokerTable *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  _QWORD *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // edx
  int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // r9d
  unsigned int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h]
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  int *v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  int *v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  int *v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  int *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, a1);
  }
  v31 = 0;
  memset(v30, 0, sizeof(v30));
  _InterlockedExchange(&g_Twns, a1 / 0x3C);
  if ( _InterlockedCompareExchange(&g_KamInitialized, 0, 0) )
  {
    EnterCriticalSection(&g_ControlChannelTriggerContextTableLock);
    RtlInitEnumerationHashTable(g_ControlChannelTriggerContextTable, v30);
    for ( i = RtlEnumerateEntryHashTable(g_ControlChannelTriggerContextTable, v30);
          i;
          i = RtlEnumerateEntryHashTable(g_ControlChannelTriggerContextTable, v30) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(i + 24));
      if ( *(_BYTE *)(i + 361) )
      {
        EnterCriticalSection(&g_NlmSignatureLock);
        if ( g_NlmSignature && (unsigned int)StubNlmCacheContainsMbbNetwork() )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
          }
          v15 = *(_DWORD *)(i + 368);
          v16 = g_Twns;
          v17 = g_Twns;
          v18 = *(_DWORD *)(i + 376);
          if ( v15 < g_Twns )
            v17 = *(_DWORD *)(i + 368);
          if ( v18 >= v17 )
          {
            v19 = g_Twns;
            if ( v15 < g_Twns )
              v19 = *(_DWORD *)(i + 368);
          }
          else
          {
            v19 = *(_DWORD *)(i + 376);
          }
          if ( g_KamFloorTime <= v19 )
          {
            v22 = g_Twns;
            if ( v15 < g_Twns )
              v22 = *(_DWORD *)(i + 368);
            if ( v18 >= v22 )
            {
              v21 = g_Twns;
              if ( v15 < g_Twns )
                v21 = *(_DWORD *)(i + 368);
            }
            else
            {
              v21 = *(_DWORD *)(i + 376);
            }
          }
          else
          {
            v21 = g_KamFloorTime;
          }
          v7 = g_KamFloorTimeOnCell;
          if ( g_KamFloorTimeOnCell <= v21 )
          {
            v23 = g_Twns;
            if ( v15 < g_Twns )
              v23 = *(_DWORD *)(i + 368);
            if ( v18 >= v23 )
            {
              v24 = g_Twns;
              if ( v15 < g_Twns )
                v24 = *(_DWORD *)(i + 368);
            }
            else
            {
              v24 = *(_DWORD *)(i + 376);
            }
            if ( g_KamFloorTime <= v24 )
            {
              v25 = g_Twns;
              if ( v15 < g_Twns )
                v25 = *(_DWORD *)(i + 368);
              if ( v18 >= v25 )
              {
                if ( v15 < g_Twns )
                  v16 = *(_DWORD *)(i + 368);
                v7 = v16;
              }
              else
              {
                v7 = *(_DWORD *)(i + 376);
              }
            }
            else
            {
              v7 = g_KamFloorTime;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
          }
          v3 = *(_DWORD *)(i + 368);
          v4 = g_Twns;
          v5 = *(_DWORD *)(i + 376);
          if ( v3 < g_Twns )
            v4 = *(_DWORD *)(i + 368);
          if ( v5 < v4 )
          {
            v6 = *(_DWORD *)(i + 376);
          }
          else
          {
            v6 = g_Twns;
            if ( v3 < g_Twns )
              v6 = *(_DWORD *)(i + 368);
          }
          v7 = g_KamFloorTime;
          if ( g_KamFloorTime <= v6 )
          {
            v14 = g_Twns;
            if ( v3 < g_Twns )
              v14 = *(_DWORD *)(i + 368);
            if ( v5 < v14 )
            {
              v7 = *(_DWORD *)(i + 376);
            }
            else
            {
              v7 = g_Twns;
              if ( v3 < g_Twns )
                v7 = *(_DWORD *)(i + 368);
            }
          }
        }
        *(_DWORD *)(i + 372) = v7;
        LeaveCriticalSection(&g_NlmSignatureLock);
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 4) != 0 )
        {
          v26 = g_Twns;
          v29 = *(_DWORD *)(i + 376);
          v28 = *(_DWORD *)(i + 372);
          v27 = *(_DWORD *)(i + 368);
          v35 = &v27;
          v37 = &v28;
          v39 = &v29;
          v41 = &v26;
          v33 = L"Kam:KapiUpdateCallback";
          v34 = 46;
          v36 = 4;
          v38 = 4;
          v40 = 4;
          v42 = 4;
          McGenEventWrite_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)NcbKamTimerUpdate, v9, 6u, &v32);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_ddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            v9,
            *(unsigned int *)(i + 372),
            g_KamFloorTime,
            *(_DWORD *)(i + 376),
            *(_DWORD *)(i + 368));
        }
        KampUpdateTimeEventHelper(i);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(i + 24));
    }
    RtlEndEnumerationHashTable(g_ControlChannelTriggerContextTable, v30);
    if ( g_SocketBrokerTable )
      SocketBrokerTable::UpdateKeepAliveTimeout(v10, a1);
    LeaveCriticalSection(&g_ControlChannelTriggerContextTableLock);
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      v26 = 0;
      v33 = L"Kam: processed kapi update";
      v34 = 54;
      v35 = &v26;
      v36 = 4;
      McGenEventWrite_EventWriteTransfer(v11, (const EVENT_DESCRIPTOR *)NcbApiStatus, v12, 3u, &v32);
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v20 = 29;
      goto LABEL_83;
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v20 = 25;
LABEL_83:
      WPP_SF_(v13[2], v20, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x1800015e0  push    rbp
0x1800015e2  push    rbx
0x1800015e3  push    r14
0x1800015e5  push    r15
0x1800015e7  lea     rbp, [rsp-8]
0x1800015ec  sub     rsp, 108h
0x1800015f3  mov     rax, cs:__security_cookie
0x1800015fa  xor     rax, rsp
0x1800015fd  mov     [rbp+20h+var_30], rax
0x180001601  mov     ebx, ecx
0x180001603  mov     rcx, cs:WPP_GLOBAL_Control
0x18000160a  lea     r15, WPP_GLOBAL_Control
0x180001611  cmp     rcx, r15
0x180001614  jnz     loc_18000184F
0x18000161a  xor     eax, eax
0x18000161c  xorps   xmm0, xmm0
0x18000161f  mov     [rbp+20h+var_A0], rax
0x180001623  xor     r14d, r14d
0x180001626  mov     eax, 88888889h
0x18000162b  mov     ecx, r14d
0x18000162e  mul     ebx
0x180001630  movups  [rsp+120h+var_C0], xmm0
0x180001635  movups  [rsp+120h+var_B0], xmm0
0x18000163a  shr     edx, 5
0x18000163d  xchg    edx, cs:g_Twns
0x180001643  xor     eax, eax
0x180001645  lock cmpxchg cs:g_KamInitialized, ecx
0x18000164d  jz      loc_180001A16
0x180001653  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x18000165a  mov     [rsp+120h+arg_10], rdi
0x180001662  call    cs:__imp_EnterCriticalSection
0x180001668  lea     rdx, [rsp+120h+var_C0]
0x18000166d  lea     rcx, g_ControlChannelTriggerContextTable
0x180001674  call    cs:__imp_RtlInitEnumerationHashTable
0x18000167a  lea     rdx, [rsp+120h+var_C0]
0x18000167f  lea     rcx, g_ControlChannelTriggerContextTable
0x180001686  call    cs:__imp_RtlEnumerateEntryHashTable
0x18000168c  mov     rdi, rax
0x18000168f  test    rax, rax
0x180001692  jz      loc_18000179B
0x180001698  mov     [rsp+120h+arg_8], rsi
0x1800016a0  mov     [rsp+120h+var_20], r12
0x1800016a8  lea     r12, aKamKapiupdatec; "Kam:KapiUpdateCallback"
0x1800016af  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800016b3  call    cs:__imp_EnterCriticalSection
0x1800016b9  cmp     [rdi+169h], r14b
0x1800016c0  jz      loc_180001763
0x1800016c6  lea     rcx, g_NlmSignatureLock; lpCriticalSection
0x1800016cd  call    cs:__imp_EnterCriticalSection
0x1800016d3  cmp     cs:g_NlmSignature, r14
0x1800016da  jnz     loc_1800019B0
0x1800016e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016e7  cmp     rcx, r15
0x1800016ea  jnz     loc_180001982
0x1800016f0  mov     edx, [rdi+170h]
0x1800016f6  mov     ecx, cs:g_Twns
0x1800016fc  mov     eax, ecx
0x1800016fe  mov     r9d, [rdi+178h]
0x180001705  cmp     edx, ecx
0x180001707  cmovb   eax, edx
0x18000170a  cmp     r9d, eax
0x18000170d  jb      loc_180001A0E
0x180001713  cmp     edx, ecx
0x180001715  mov     eax, ecx
0x180001717  cmovb   eax, edx
0x18000171a  mov     r8d, cs:g_KamFloorTime
0x180001721  cmp     r8d, eax
0x180001724  jbe     loc_180001964
0x18000172a  lea     rcx, g_NlmSignatureLock; lpCriticalSection
0x180001731  mov     [rdi+174h], r8d
0x180001738  call    cs:__imp_LeaveCriticalSection
0x18000173e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 4
0x180001745  jnz     loc_1800018CC
0x18000174b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001752  cmp     rcx, r15
0x180001755  jnz     loc_180001880
0x18000175b  mov     rcx, rdi
0x18000175e  call    KampUpdateTimeEventHelper
0x180001763  lea     rcx, [rdi+18h]; lpCriticalSection
0x180001767  call    cs:__imp_LeaveCriticalSection
0x18000176d  lea     rdx, [rsp+120h+var_C0]
0x180001772  lea     rcx, g_ControlChannelTriggerContextTable
0x180001779  call    cs:__imp_RtlEnumerateEntryHashTable
0x18000177f  mov     rdi, rax
0x180001782  test    rax, rax
0x180001785  jnz     loc_1800016AF
0x18000178b  mov     r12, [rsp+120h+var_20]
0x180001793  mov     rsi, [rsp+120h+arg_8]
0x18000179b  lea     rdx, [rsp+120h+var_C0]
0x1800017a0  lea     rcx, g_ControlChannelTriggerContextTable
0x1800017a7  call    cs:__imp_RtlEndEnumerationHashTable
0x1800017ad  cmp     cs:?g_SocketBrokerTable@@3PEAVSocketBrokerTable@@EA, r14; SocketBrokerTable * g_SocketBrokerTable
0x1800017b4  mov     rdi, [rsp+120h+arg_10]
0x1800017bc  jz      short loc_1800017C5
0x1800017be  mov     edx, ebx; unsigned int
0x1800017c0  call    ?UpdateKeepAliveTimeout@SocketBrokerTable@@QEAAXK@Z; SocketBrokerTable::UpdateKeepAliveTimeout(ulong)
0x1800017c5  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x1800017cc  call    cs:__imp_LeaveCriticalSection
0x1800017d2  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800017d9  jz      short loc_18000181F
0x1800017db  lea     rax, aKamProcessedKa; "Kam: processed kapi update"
0x1800017e2  mov     [rsp+120h+var_E0], r14d
0x1800017e7  mov     [rbp+20h+var_80], rax
0x1800017eb  lea     rdx, NcbApiStatus
0x1800017f2  lea     rax, [rsp+120h+var_E0]
0x1800017f7  mov     [rbp+20h+var_78], 36h ; '6'
0x1800017ff  mov     [rbp+20h+var_70], rax
0x180001803  mov     r9d, 3
0x180001809  lea     rax, [rbp+20h+var_90]
0x18000180d  mov     [rbp+20h+var_68], 4
0x180001815  mov     [rsp+120h+var_100], rax
0x18000181a  call    McGenEventWrite_EventWriteTransfer
0x18000181f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001826  cmp     rcx, r15
0x180001829  jz      short loc_180001835
0x18000182b  test    byte ptr [rcx+1Ch], 1
0x18000182f  jnz     loc_180001AD2
0x180001835  mov     rcx, [rbp+20h+var_30]
0x180001839  xor     rcx, rsp; StackCookie
0x18000183c  call    __security_check_cookie
0x180001841  add     rsp, 108h
0x180001848  pop     r15
0x18000184a  pop     r14
0x18000184c  pop     rbx
0x18000184d  pop     rbp
0x18000184e  retn
0x18000184f  test    byte ptr [rcx+1Ch], 1
0x180001853  jz      loc_18000161A
0x180001859  cmp     byte ptr [rcx+19h], 6
0x18000185d  jb      loc_18000161A
0x180001863  mov     rcx, [rcx+10h]
0x180001867  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x18000186e  mov     edx, 18h
0x180001873  mov     r9d, ebx
0x180001876  call    WPP_SF_d
0x18000187b  jmp     loc_18000161A
0x180001880  test    byte ptr [rcx+1Ch], 1
0x180001884  jz      loc_18000175B
0x18000188a  cmp     byte ptr [rcx+19h], 5
0x18000188e  jb      loc_18000175B
0x180001894  mov     eax, [rdi+170h]
0x18000189a  mov     edx, 1Ch
0x18000189f  mov     r9d, [rdi+174h]
0x1800018a6  mov     rcx, [rcx+10h]
0x1800018aa  mov     [rsp+120h+var_F0], eax
0x1800018ae  mov     eax, [rdi+178h]
0x1800018b4  mov     [rsp+120h+var_F8], eax
0x1800018b8  mov     eax, cs:g_KamFloorTime
0x1800018be  mov     dword ptr [rsp+120h+var_100], eax
0x1800018c2  call    WPP_SF_ddddd
0x1800018c7  jmp     loc_18000175B
0x1800018cc  mov     eax, cs:g_Twns
0x1800018d2  lea     rdx, NcbKamTimerUpdate
0x1800018d9  mov     [rsp+120h+var_E0], eax
0x1800018dd  mov     r9d, 6
0x1800018e3  mov     eax, [rdi+178h]
0x1800018e9  mov     [rsp+120h+var_C8], eax
0x1800018ed  mov     eax, [rdi+174h]
0x1800018f3  mov     [rsp+120h+var_D0], eax
0x1800018f7  mov     eax, [rdi+170h]
0x1800018fd  mov     [rsp+120h+var_D8], eax
0x180001901  lea     rax, [rsp+120h+var_D8]
0x180001906  mov     [rbp+20h+var_70], rax
0x18000190a  lea     rax, [rsp+120h+var_D0]
0x18000190f  mov     [rbp+20h+var_60], rax
0x180001913  lea     rax, [rsp+120h+var_C8]
0x180001918  mov     [rbp+20h+var_50], rax
0x18000191c  lea     rax, [rsp+120h+var_E0]
0x180001921  mov     [rbp+20h+var_40], rax
0x180001925  lea     rax, [rbp+20h+var_90]
0x180001929  mov     [rsp+120h+var_100], rax
0x18000192e  mov     [rbp+20h+var_80], r12
0x180001932  mov     [rbp+20h+var_78], 2Eh ; '.'
0x18000193a  mov     [rbp+20h+var_68], 4
0x180001942  mov     [rbp+20h+var_58], 4
0x18000194a  mov     [rbp+20h+var_48], 4
0x180001952  mov     [rbp+20h+var_38], 4
0x18000195a  call    McGenEventWrite_EventWriteTransfer
0x18000195f  jmp     loc_18000174B
0x180001964  cmp     edx, ecx
0x180001966  mov     eax, ecx
0x180001968  cmovb   eax, edx
0x18000196b  cmp     r9d, eax
0x18000196e  jb      loc_180001ACA
0x180001974  cmp     edx, ecx
0x180001976  mov     r8d, ecx
0x180001979  cmovb   r8d, edx
0x18000197d  jmp     loc_18000172A
0x180001982  test    byte ptr [rcx+1Ch], 1
0x180001986  jz      loc_1800016F0
0x18000198c  cmp     byte ptr [rcx+19h], 5
0x180001990  jb      loc_1800016F0
0x180001996  mov     rcx, [rcx+10h]
0x18000199a  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800019a1  mov     edx, 1Bh
0x1800019a6  call    WPP_SF_
0x1800019ab  jmp     loc_1800016F0
0x1800019b0  call    StubNlmCacheContainsMbbNetwork
0x1800019b5  test    eax, eax
0x1800019b7  jz      loc_1800016E0
0x1800019bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019c4  cmp     rcx, r15
0x1800019c7  jz      short loc_1800019EA
0x1800019c9  test    byte ptr [rcx+1Ch], 1
0x1800019cd  jz      short loc_1800019EA
0x1800019cf  cmp     byte ptr [rcx+19h], 5
0x1800019d3  jb      short loc_1800019EA
0x1800019d5  mov     rcx, [rcx+10h]
0x1800019d9  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x1800019e0  mov     edx, 1Ah
0x1800019e5  call    WPP_SF_
0x1800019ea  mov     edx, [rdi+170h]
0x1800019f0  mov     ecx, cs:g_Twns
0x1800019f6  mov     eax, ecx
0x1800019f8  mov     r9d, [rdi+178h]
0x1800019ff  cmp     edx, ecx
0x180001a01  cmovb   eax, edx
0x180001a04  cmp     r9d, eax
0x180001a07  jnb     short loc_180001A44
0x180001a09  mov     eax, r9d
0x180001a0c  jmp     short loc_180001A4B
0x180001a0e  mov     eax, r9d
0x180001a11  jmp     loc_18000171A
0x180001a16  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a1d  cmp     rcx, r15
0x180001a20  jz      loc_180001835
0x180001a26  test    byte ptr [rcx+1Ch], 1
0x180001a2a  jz      loc_180001835
0x180001a30  cmp     byte ptr [rcx+19h], 6
0x180001a34  jb      loc_180001835
0x180001a3a  mov     edx, 19h
0x180001a3f  jmp     loc_180001AE1
0x180001a44  cmp     edx, ecx
0x180001a46  mov     eax, ecx
0x180001a48  cmovb   eax, edx
0x180001a4b  mov     r10d, cs:g_KamFloorTime
0x180001a52  cmp     r10d, eax
0x180001a55  jbe     short loc_180001A5C
0x180001a57  mov     eax, r10d
0x180001a5a  jmp     short loc_180001A74
0x180001a5c  cmp     edx, ecx
0x180001a5e  mov     eax, ecx
0x180001a60  cmovb   eax, edx
0x180001a63  cmp     r9d, eax
0x180001a66  jnb     short loc_180001A6D
0x180001a68  mov     eax, r9d
0x180001a6b  jmp     short loc_180001A74
0x180001a6d  cmp     edx, ecx
0x180001a6f  mov     eax, ecx
0x180001a71  cmovb   eax, edx
0x180001a74  mov     r8d, cs:g_KamFloorTimeOnCell
0x180001a7b  cmp     r8d, eax
0x180001a7e  ja      loc_18000172A
0x180001a84  cmp     edx, ecx
0x180001a86  mov     eax, ecx
0x180001a88  cmovb   eax, edx
0x180001a8b  cmp     r9d, eax
0x180001a8e  jnb     short loc_180001A95
0x180001a90  mov     eax, r9d
0x180001a93  jmp     short loc_180001A9C
0x180001a95  cmp     edx, ecx
0x180001a97  mov     eax, ecx
0x180001a99  cmovb   eax, edx
0x180001a9c  cmp     r10d, eax
0x180001a9f  jbe     short loc_180001AA9
0x180001aa1  mov     r8d, r10d
0x180001aa4  jmp     loc_18000172A
0x180001aa9  cmp     edx, ecx
0x180001aab  mov     eax, ecx
0x180001aad  cmovb   eax, edx
0x180001ab0  cmp     r9d, eax
0x180001ab3  jnb     short loc_180001ABD
0x180001ab5  mov     r8d, r9d
0x180001ab8  jmp     loc_18000172A
0x180001abd  cmp     edx, ecx
0x180001abf  cmovb   ecx, edx
0x180001ac2  mov     r8d, ecx
0x180001ac5  jmp     loc_18000172A
0x180001aca  mov     r8d, r9d
0x180001acd  jmp     loc_18000172A
0x180001ad2  cmp     byte ptr [rcx+19h], 6
0x180001ad6  jb      loc_180001835
0x180001adc  mov     edx, 1Dh
0x180001ae1  mov     rcx, [rcx+10h]
0x180001ae5  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180001aec  call    WPP_SF_
0x180001af1  jmp     loc_180001835
```
