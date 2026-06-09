# KamDecreaseKeepAliveIntervalTime

- ea: `0x18001f618`
- end: `0x18001f948`
- name: `KamDecreaseKeepAliveIntervalTime`
- size: `816`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180021900`

## callees

- `0x180001c48`
- `0x180005120`
- `0x180008920`
- `0x1800097d0`
- `0x18000a0a0`
- `0x1800103a8`
- `0x180011120`
- `0x18001c500`
- `0x18001d09c`
- `0x18001f618`
- `0x1800204e0`
- `0x180022fc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f67e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f68e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f731`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f67e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f68e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f731`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f854`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f8ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f854`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f8ef`

## string_xrefs

- `0x18001f7de`: `Kam: could not write to nlm cache`
- `0x18001f815`: `Kam: Getting current NLM signature from cached failed with status`

## pseudocode

```c
__int64 __fastcall KamDecreaseKeepAliveIntervalTime(__int64 a1)
{
  int v2; // ecx
  unsigned int v3; // eax
  int v4; // r8d
  unsigned int v5; // edx
  __int64 v6; // r9
  unsigned int CurrentSignature; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  int v16; // edx
  int v17; // ecx
  unsigned int updated; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_ddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      99,
      &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids,
      *(unsigned int *)(a1 + 376),
      *(_DWORD *)(a1 + 372),
      g_KamFloorTime);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  EnterCriticalSection(&g_NlmSignatureLock);
  if ( g_NlmSignature && (unsigned int)StubNlmCacheContainsMbbNetwork() )
  {
    v2 = g_KamFloorTime;
    v3 = g_KamFloorTime;
    v4 = g_KamFloorTimeOnCell;
    v5 = *(_DWORD *)(a1 + 372) >> 1;
    if ( v5 > g_KamFloorTime )
      v3 = *(_DWORD *)(a1 + 372) >> 1;
    if ( g_KamFloorTimeOnCell <= v3 )
    {
      if ( v5 > g_KamFloorTime )
        v2 = *(_DWORD *)(a1 + 372) >> 1;
      v4 = v2;
    }
  }
  else
  {
    v4 = g_KamFloorTime;
    if ( *(_DWORD *)(a1 + 372) >> 1 > (unsigned int)g_KamFloorTime )
      v4 = *(_DWORD *)(a1 + 372) >> 1;
  }
  *(_DWORD *)(a1 + 376) = v4;
  LeaveCriticalSection(&g_NlmSignatureLock);
  v6 = *(unsigned int *)(a1 + 376);
  *(_DWORD *)(a1 + 372) = v6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v6);
  }
  EnterCriticalSection(&g_NlmSignatureLock);
  if ( g_NlmSignature )
  {
    StubNlmCacheSignatureDereference(g_NlmCache);
    g_NlmSignature = 0;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
  }
  CurrentSignature = StubNlmCacheGetCurrentSignature(g_NlmCache, &g_NlmSignature);
  v10 = CurrentSignature;
  if ( CurrentSignature )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v9,
        v8,
        L"Kam: Getting current NLM signature from cached failed with status",
        CurrentSignature);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 103;
      goto LABEL_39;
    }
  }
  else
  {
    v11 = StubNlmCacheStoreValue(g_NlmCache, 4, a1 + 376);
    v10 = v11;
    if ( v11 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v13, v12, L"Kam: could not write to nlm cache", v11);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 102;
LABEL_39:
        WPP_SF_d(v14[2], v15, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, v10);
      }
    }
  }
  LeaveCriticalSection(&g_NlmSignatureLock);
  if ( *(_BYTE *)(a1 + 361) )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 4) != 0 )
      McTemplateU0zqqqq_EventWriteTransfer(
        v17,
        v16,
        (unsigned int)L"Kam:DecreaseKeepaliveInterval",
        *(_DWORD *)(a1 + 368),
        *(_DWORD *)(a1 + 372),
        *(_DWORD *)(a1 + 376));
    updated = KampUpdateTimeEventHelper(a1);
    if ( updated
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, updated);
    }
    if ( *(_DWORD *)(a1 + 372) == g_KamFloorTime )
      NcbSqmKeepaliveStream(*(_QWORD *)(a1 + 280), *(unsigned int *)(a1 + 300));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v20, v19, L"Kam: decreased keepalive interval ", 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f618  push    rbx
0x18001f61a  push    rbp
0x18001f61b  push    rsi
0x18001f61c  push    rdi
0x18001f61d  push    r12
0x18001f61f  push    r13
0x18001f621  sub     rsp, 48h
0x18001f625  mov     rbx, rcx
0x18001f628  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f62f  lea     r12, WPP_GLOBAL_Control
0x18001f636  lea     r13, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x18001f63d  cmp     rcx, r12
0x18001f640  jz      short loc_18001F67A
0x18001f642  test    byte ptr [rcx+1Ch], 1
0x18001f646  jz      short loc_18001F67A
0x18001f648  cmp     byte ptr [rcx+19h], 6
0x18001f64c  jb      short loc_18001F67A
0x18001f64e  mov     eax, cs:g_KamFloorTime
0x18001f654  mov     edx, 63h ; 'c'
0x18001f659  mov     r9d, [rbx+178h]
0x18001f660  mov     r8, r13
0x18001f663  mov     rcx, [rcx+10h]
0x18001f667  mov     dword ptr [rsp+78h+var_50], eax
0x18001f66b  mov     eax, [rbx+174h]
0x18001f671  mov     [rsp+78h+var_58], eax
0x18001f675  call    WPP_SF_ddd
0x18001f67a  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001f67e  call    cs:__imp_EnterCriticalSection
0x18001f684  lea     rdi, g_NlmSignatureLock
0x18001f68b  mov     rcx, rdi; lpCriticalSection
0x18001f68e  call    cs:__imp_EnterCriticalSection
0x18001f694  cmp     cs:g_NlmSignature, 0
0x18001f69c  jz      short loc_18001F6D2
0x18001f69e  call    StubNlmCacheContainsMbbNetwork
0x18001f6a3  test    eax, eax
0x18001f6a5  jz      short loc_18001F6D2
0x18001f6a7  mov     ecx, cs:g_KamFloorTime
0x18001f6ad  mov     eax, ecx
0x18001f6af  mov     edx, [rbx+174h]
0x18001f6b5  mov     r8d, cs:g_KamFloorTimeOnCell
0x18001f6bc  shr     edx, 1
0x18001f6be  cmp     edx, ecx
0x18001f6c0  cmova   eax, edx
0x18001f6c3  cmp     r8d, eax
0x18001f6c6  ja      short loc_18001F6E8
0x18001f6c8  cmp     edx, ecx
0x18001f6ca  cmova   ecx, edx
0x18001f6cd  mov     r8d, ecx
0x18001f6d0  jmp     short loc_18001F6E8
0x18001f6d2  mov     r8d, cs:g_KamFloorTime
0x18001f6d9  mov     eax, [rbx+174h]
0x18001f6df  shr     eax, 1
0x18001f6e1  cmp     eax, r8d
0x18001f6e4  cmova   r8d, eax
0x18001f6e8  lea     rsi, [rbx+178h]
0x18001f6ef  mov     rcx, rdi; lpCriticalSection
0x18001f6f2  mov     [rsi], r8d
0x18001f6f5  call    cs:__imp_LeaveCriticalSection
0x18001f6fb  mov     r9d, [rsi]
0x18001f6fe  mov     [rbx+174h], r9d
0x18001f705  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f70c  cmp     rcx, r12
0x18001f70f  jz      short loc_18001F72E
0x18001f711  test    byte ptr [rcx+1Ch], 1
0x18001f715  jz      short loc_18001F72E
0x18001f717  cmp     byte ptr [rcx+19h], 5
0x18001f71b  jb      short loc_18001F72E
0x18001f71d  mov     rcx, [rcx+10h]
0x18001f721  mov     edx, 64h ; 'd'
0x18001f726  mov     r8, r13
0x18001f729  call    WPP_SF_d
0x18001f72e  mov     rcx, rdi; lpCriticalSection
0x18001f731  call    cs:__imp_EnterCriticalSection
0x18001f737  mov     rdx, cs:g_NlmSignature
0x18001f73e  test    rdx, rdx
0x18001f741  jz      short loc_18001F75C
0x18001f743  mov     rcx, cs:g_NlmCache
0x18001f74a  call    StubNlmCacheSignatureDereference
0x18001f74f  mov     cs:g_NlmSignature, 0
0x18001f75a  jmp     short loc_18001F785
0x18001f75c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f763  cmp     rcx, r12
0x18001f766  jz      short loc_18001F785
0x18001f768  test    byte ptr [rcx+1Ch], 1
0x18001f76c  jz      short loc_18001F785
0x18001f76e  cmp     byte ptr [rcx+19h], 5
0x18001f772  jb      short loc_18001F785
0x18001f774  mov     rcx, [rcx+10h]
0x18001f778  mov     edx, 65h ; 'e'
0x18001f77d  mov     r8, r13
0x18001f780  call    WPP_SF_
0x18001f785  mov     rcx, cs:g_NlmCache
0x18001f78c  lea     rdx, g_NlmSignature
0x18001f793  call    StubNlmCacheGetCurrentSignature
0x18001f798  mov     edi, eax
0x18001f79a  test    eax, eax
0x18001f79c  jnz     short loc_18001F809
0x18001f79e  mov     r9, [rbx+180h]
0x18001f7a5  mov     r8d, [rbx+188h]
0x18001f7ac  mov     rdx, cs:g_NlmSignature
0x18001f7b3  mov     rcx, cs:g_NlmCache; lpCriticalSection
0x18001f7ba  mov     [rsp+78h+var_50], rsi; __int64
0x18001f7bf  mov     [rsp+78h+var_58], 4; int
0x18001f7c7  call    StubNlmCacheStoreValue
0x18001f7cc  mov     edi, eax
0x18001f7ce  test    eax, eax
0x18001f7d0  jz      short loc_18001F84D
0x18001f7d2  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001f7d9  jz      short loc_18001F7EA
0x18001f7db  mov     r9d, eax
0x18001f7de  lea     r8, aKamCouldNotWri; "Kam: could not write to nlm cache"
0x18001f7e5  call    McTemplateU0zq_EventWriteTransfer
0x18001f7ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7f1  cmp     rcx, r12
0x18001f7f4  jz      short loc_18001F84D
0x18001f7f6  test    byte ptr [rcx+1Ch], 1
0x18001f7fa  jz      short loc_18001F84D
0x18001f7fc  cmp     byte ptr [rcx+19h], 2
0x18001f800  jb      short loc_18001F84D
0x18001f802  mov     edx, 66h ; 'f'
0x18001f807  jmp     short loc_18001F83E
0x18001f809  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001f810  jz      short loc_18001F821
0x18001f812  mov     r9d, edi
0x18001f815  lea     r8, aKamGettingCurr; "Kam: Getting current NLM signature from"...
0x18001f81c  call    McTemplateU0zq_EventWriteTransfer
0x18001f821  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f828  cmp     rcx, r12
0x18001f82b  jz      short loc_18001F84D
0x18001f82d  test    byte ptr [rcx+1Ch], 1
0x18001f831  jz      short loc_18001F84D
0x18001f833  cmp     byte ptr [rcx+19h], 2
0x18001f837  jb      short loc_18001F84D
0x18001f839  mov     edx, 67h ; 'g'
0x18001f83e  mov     rcx, [rcx+10h]
0x18001f842  mov     r9d, edi
0x18001f845  mov     r8, r13
0x18001f848  call    WPP_SF_d
0x18001f84d  lea     rcx, g_NlmSignatureLock; lpCriticalSection
0x18001f854  call    cs:__imp_LeaveCriticalSection
0x18001f85a  cmp     byte ptr [rbx+169h], 0
0x18001f861  jz      loc_18001F8EB
0x18001f867  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 4
0x18001f86e  jz      short loc_18001F893
0x18001f870  mov     eax, [rsi]
0x18001f872  lea     r8, aKamDecreasekee; "Kam:DecreaseKeepaliveInterval"
0x18001f879  mov     r9d, [rbx+170h]
0x18001f880  mov     dword ptr [rsp+78h+var_50], eax
0x18001f884  mov     eax, [rbx+174h]
0x18001f88a  mov     [rsp+78h+var_58], eax
0x18001f88e  call    McTemplateU0zqqqq_EventWriteTransfer
0x18001f893  mov     rcx, rbx
0x18001f896  call    KampUpdateTimeEventHelper
0x18001f89b  test    eax, eax
0x18001f89d  jz      short loc_18001F8CB
0x18001f89f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8a6  cmp     rcx, r12
0x18001f8a9  jz      short loc_18001F8CB
0x18001f8ab  test    byte ptr [rcx+1Ch], 1
0x18001f8af  jz      short loc_18001F8CB
0x18001f8b1  cmp     byte ptr [rcx+19h], 3
0x18001f8b5  jb      short loc_18001F8CB
0x18001f8b7  mov     rcx, [rcx+10h]
0x18001f8bb  mov     edx, 68h ; 'h'
0x18001f8c0  mov     r9d, eax
0x18001f8c3  mov     r8, r13
0x18001f8c6  call    WPP_SF_d
0x18001f8cb  mov     eax, cs:g_KamFloorTime
0x18001f8d1  cmp     [rbx+174h], eax
0x18001f8d7  jnz     short loc_18001F8EB
0x18001f8d9  mov     edx, [rbx+12Ch]
0x18001f8df  mov     rcx, [rbx+118h]
0x18001f8e6  call    NcbSqmKeepaliveStream
0x18001f8eb  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001f8ef  call    cs:__imp_LeaveCriticalSection
0x18001f8f5  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001f8fc  jz      short loc_18001F90D
0x18001f8fe  xor     r9d, r9d
0x18001f901  lea     r8, aKamDecreasedKe; "Kam: decreased keepalive interval "
0x18001f908  call    McTemplateU0zq_EventWriteTransfer
0x18001f90d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f914  cmp     rcx, r12
0x18001f917  jz      short loc_18001F939
0x18001f919  test    byte ptr [rcx+1Ch], 1
0x18001f91d  jz      short loc_18001F939
0x18001f91f  cmp     byte ptr [rcx+19h], 6
0x18001f923  jb      short loc_18001F939
0x18001f925  mov     rcx, [rcx+10h]
0x18001f929  mov     edx, 69h ; 'i'
0x18001f92e  xor     r9d, r9d
0x18001f931  mov     r8, r13
0x18001f934  call    WPP_SF_d
0x18001f939  xor     eax, eax
0x18001f93b  add     rsp, 48h
0x18001f93f  pop     r13
0x18001f941  pop     r12
0x18001f943  pop     rdi
0x18001f944  pop     rsi
0x18001f945  pop     rbp
0x18001f946  pop     rbx
0x18001f947  retn
```
