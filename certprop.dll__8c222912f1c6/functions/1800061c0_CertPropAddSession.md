# CertPropAddSession

- ea: `0x1800061c0`
- end: `0x1800062cc`
- name: `CertPropAddSession`
- size: `268`
- prototype: `__int64 __fastcall(__int64 SessionId, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000fe80`
- `0x1800178a4`

## callees

- `0x180002690`
- `0x180002ee0`
- `0x180004600`
- `0x1800061c0`
- `0x180006750`
- `0x180014fa8`
- `0x180018bb4`
- `0x180018dec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000626c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000626c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006279`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006279`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006217`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006217`

## pseudocode

```c
__int64 __fastcall CertPropAddSession(__int64 SessionId, int a2)
{
  unsigned int v3; // esi
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rcx
  unsigned int started; // ebx
  unsigned int v9; // r8d
  int v10; // r9d
  LPVOID *v11; // rdi
  __int64 v12; // rcx
  LPVOID *v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = 0;
  v3 = SessionId;
  WppTraceIndent(SessionId, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v5, v6, v3, a2);
  }
  EnterCriticalSection(&g_csSessionList);
  started = CertPropInitializeSession(v3, &v14);
  if ( !started )
  {
    v10 = a2;
    v11 = v14;
    started = CertPropSynchronizeSingleRootStore(v7, v14, v9, v10);
    if ( started || (started = CertPropStartMonitoringSession(v11)) != 0 )
      CertPropDeleteSession(v3);
    else
      SubmitThreadpoolWork((PTP_WORK)v11[76]);
  }
  LeaveCriticalSection(&g_csSessionList);
  WppTraceIndent(v12, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      started);
  }
  return started;
}

```

## disassembly

```asm
0x1800061c0  push    rbx
0x1800061c2  push    rbp
0x1800061c3  push    rsi
0x1800061c4  push    rdi
0x1800061c5  sub     rsp, 38h
0x1800061c9  mov     edi, edx
0x1800061cb  mov     [rsp+58h+arg_10], 0
0x1800061d4  mov     edx, 2
0x1800061d9  mov     esi, ecx
0x1800061db  call    WppTraceIndent
0x1800061e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061e7  lea     rbp, WPP_GLOBAL_Control
0x1800061ee  cmp     rcx, rbp
0x1800061f1  jz      short loc_180006210
0x1800061f3  test    byte ptr [rcx+1Ch], 1
0x1800061f7  jz      short loc_180006210
0x1800061f9  cmp     byte ptr [rcx+19h], 4
0x1800061fd  jb      short loc_180006210
0x1800061ff  mov     rcx, [rcx+10h]
0x180006203  mov     [rsp+58h+var_30], edi
0x180006207  mov     [rsp+58h+var_38], esi
0x18000620b  call    WPP_SF_sdd
0x180006210  lea     rcx, g_csSessionList; lpCriticalSection
0x180006217  call    cs:__imp_EnterCriticalSection
0x18000621d  lea     rdx, [rsp+58h+arg_10]
0x180006222  mov     ecx, esi; SessionId
0x180006224  call    CertPropInitializeSession
0x180006229  mov     ebx, eax
0x18000622b  test    eax, eax
0x18000622d  jnz     short loc_180006272
0x18000622f  mov     r9d, edi
0x180006232  mov     rdi, [rsp+58h+arg_10]
0x180006237  mov     rdx, rdi
0x18000623a  call    CertPropSynchronizeSingleRootStore
0x18000623f  mov     ebx, eax
0x180006241  test    eax, eax
0x180006243  jz      short loc_18000624E
0x180006245  mov     ecx, esi
0x180006247  call    CertPropDeleteSession
0x18000624c  jmp     short loc_180006272
0x18000624e  mov     rcx, rdi
0x180006251  call    CertPropStartMonitoringSession
0x180006256  mov     ebx, eax
0x180006258  test    eax, eax
0x18000625a  jz      short loc_180006265
0x18000625c  mov     ecx, esi
0x18000625e  call    CertPropDeleteSession
0x180006263  jmp     short loc_180006272
0x180006265  mov     rcx, [rdi+260h]; pwk
0x18000626c  call    cs:__imp_SubmitThreadpoolWork
0x180006272  lea     rcx, g_csSessionList; lpCriticalSection
0x180006279  call    cs:__imp_LeaveCriticalSection
0x18000627f  mov     edx, 2
0x180006284  call    WppTraceIndent
0x180006289  mov     rcx, cs:WPP_GLOBAL_Control
0x180006290  cmp     rcx, rbp
0x180006293  jz      short loc_1800062C1
0x180006295  test    byte ptr [rcx+1Ch], 1
0x180006299  jz      short loc_1800062C1
0x18000629b  cmp     byte ptr [rcx+19h], 4
0x18000629f  jb      short loc_1800062C1
0x1800062a1  mov     r9, cs:WPP_pszIndent
0x1800062a8  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x1800062af  mov     rcx, [rcx+10h]
0x1800062b3  mov     edx, 2Ch ; ','
0x1800062b8  mov     [rsp+58h+var_38], ebx
0x1800062bc  call    WPP_SF_sD
0x1800062c1  mov     eax, ebx
0x1800062c3  add     rsp, 38h
0x1800062c7  pop     rdi
0x1800062c8  pop     rsi
0x1800062c9  pop     rbp
0x1800062ca  pop     rbx
0x1800062cb  retn
```
