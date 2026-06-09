# ScPolicyCheckForSmartcardAuth

- ea: `0x18001af6c`
- end: `0x18001b270`
- name: `ScPolicyCheckForSmartcardAuth`
- size: `772`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b490`
- `0x18001b5c0`

## callees

- `0x180004600`
- `0x18000e740`
- `0x180018bb4`
- `0x180018d78`
- `0x18001aee0`
- `0x18001af6c`
- `0x18001b438`
- `0x180021a08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b1c5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b1c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b1a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b1a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b117`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b117`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b1fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b1fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b192`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b192`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001b136`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001b136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b02e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b02e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b20a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b20a`
- `WINSTA!WinStationQueryInformationW` at `0x18001b024`
- `WINSTA!WinStationQueryInformationW` at `0x18001b024`

## pseudocode

```c
__int64 __fastcall ScPolicyCheckForSmartcardAuth(__int64 a1, int a2)
{
  unsigned int v3; // r14d
  _QWORD *v4; // rdi
  int v5; // r9d
  __int64 v6; // rcx
  unsigned int LastError; // esi
  int v8; // r9d
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  char *v12; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  HANDLE v14; // rcx
  PVOID pv; // [rsp+30h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-30h] BYREF
  HANDLE hObject[5]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v19; // [rsp+78h] [rbp+10h] BYREF
  int v20; // [rsp+80h] [rbp+18h] BYREF
  int v21; // [rsp+88h] [rbp+20h] BYREF

  v3 = a1;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  lpMem = 0;
  hObject[0] = 0;
  v4 = 0;
  pv = 0;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
      v5,
      v3);
  }
  if ( a2 == 8 )
    goto LABEL_17;
  v20 = 4;
  if ( !(unsigned __int8)WinStationQueryInformationW(0, v3, 37, &v19, 4, &v20) )
  {
LABEL_7:
    LastError = GetLastError();
    goto LABEL_28;
  }
  WppTraceIndent(v6, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
      v8,
      v19);
  }
  v9 = v19;
  if ( v19 == -1 && a2 != 3 )
  {
LABEL_17:
    v9 = v3;
    v19 = v3;
  }
  else if ( ((a2 - 1) & 0xFFFFFFFD) == 0 && !v19 )
  {
    v9 = 0xFFFFFFFFLL;
    v19 = -1;
  }
  LastError = ScPolicyCheckForAutoReConnect(v3, v9, &pv);
  v4 = pv;
  if ( !LastError )
  {
    if ( !pv )
    {
      LastError = CommonGetImpersonationToken(v3, hObject);
      if ( LastError )
        goto LABEL_28;
      LastError = ScPolicyRetrieveLogonReaderInfo(v11, v10, v19, &v21, (BYTE **)&lpMem);
      if ( LastError )
        goto LABEL_28;
      v12 = (char *)HeapAlloc(g_hScPolicyHeap, 8u, 0x58u);
      v4 = v12;
      pv = v12;
      if ( !v12 )
      {
        LastError = 8;
        goto LABEL_28;
      }
      InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
      *((_DWORD *)v4 + 12) = 1;
      *((_DWORD *)v4 + 19) = v21;
      v4[8] = lpMem;
      lpMem = 0;
      *((_DWORD *)v4 + 13) = v3;
      v4[7] = hObject[0];
      hObject[0] = 0;
    }
    EnterCriticalSection(&g_csScPolicyList);
    ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)ScPolicyThreadProc, v4, &pcbe);
    if ( !ThreadpoolWork )
    {
      LeaveCriticalSection(&g_csScPolicyList);
      goto LABEL_7;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
    *v4 = g_pScPolicyList;
    g_pScPolicyList = (__int64)v4;
    LeaveCriticalSection(&g_csScPolicyList);
    v4 = 0;
  }
LABEL_28:
  if ( lpMem )
    HeapFree(g_hScPolicyHeap, 0, lpMem);
  v14 = hObject[0];
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( v4 )
    ScPolicyFreeListNode(v4);
  WppTraceIndent(v14, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001af6c  mov     rax, rsp
0x18001af6f  mov     [rax+8], rsi
0x18001af73  push    rdi
0x18001af74  push    r14
0x18001af76  push    r15
0x18001af78  sub     rsp, 50h
0x18001af7c  mov     esi, edx
0x18001af7e  mov     r14d, ecx
0x18001af81  mov     dword ptr [rax+10h], 0
0x18001af88  mov     dword ptr [rax+18h], 0
0x18001af8f  mov     dword ptr [rax+20h], 0
0x18001af96  mov     qword ptr [rax-30h], 0
0x18001af9e  mov     qword ptr [rax-28h], 0
0x18001afa6  xor     edi, edi
0x18001afa8  mov     [rax-38h], rdi
0x18001afac  lea     edx, [rdi+2]
0x18001afaf  call    WppTraceIndent
0x18001afb4  lea     r15, WPP_GLOBAL_Control
0x18001afbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afc2  cmp     rcx, r15
0x18001afc5  jz      short loc_18001AFEB
0x18001afc7  test    byte ptr [rcx+1Ch], 1
0x18001afcb  jz      short loc_18001AFEB
0x18001afcd  cmp     byte ptr [rcx+19h], 4
0x18001afd1  jb      short loc_18001AFEB
0x18001afd3  lea     edx, [rdi+14h]
0x18001afd6  mov     dword ptr [rsp+68h+var_48], r14d
0x18001afdb  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001afe2  mov     rcx, [rcx+10h]
0x18001afe6  call    WPP_SF_sd
0x18001afeb  cmp     esi, 8
0x18001afee  jz      loc_18001B0A0
0x18001aff4  mov     [rsp+68h+arg_10], 4
0x18001afff  lea     rax, [rsp+68h+arg_10]
0x18001b007  mov     [rsp+68h+var_40], rax
0x18001b00c  mov     dword ptr [rsp+68h+var_48], 4
0x18001b014  lea     r9, [rsp+68h+arg_8]
0x18001b019  mov     r8d, 25h ; '%'
0x18001b01f  mov     edx, r14d
0x18001b022  xor     ecx, ecx
0x18001b024  call    cs:__imp_WinStationQueryInformationW
0x18001b02a  test    al, al
0x18001b02c  jnz     short loc_18001B03B
0x18001b02e  call    cs:__imp_GetLastError
0x18001b034  mov     esi, eax
0x18001b036  jmp     loc_18001B1E7
0x18001b03b  mov     edx, 2
0x18001b040  call    WppTraceIndent
0x18001b045  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b04c  cmp     rcx, r15
0x18001b04f  jz      short loc_18001B07A
0x18001b051  test    byte ptr [rcx+1Ch], 1
0x18001b055  jz      short loc_18001B07A
0x18001b057  cmp     byte ptr [rcx+19h], 4
0x18001b05b  jb      short loc_18001B07A
0x18001b05d  mov     edx, 15h
0x18001b062  mov     eax, [rsp+68h+arg_8]
0x18001b066  mov     dword ptr [rsp+68h+var_48], eax
0x18001b06a  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001b071  mov     rcx, [rcx+10h]
0x18001b075  call    WPP_SF_sd
0x18001b07a  mov     edx, [rsp+68h+arg_8]
0x18001b07e  or      ecx, 0FFFFFFFFh
0x18001b081  cmp     edx, ecx
0x18001b083  jnz     short loc_18001B08A
0x18001b085  cmp     esi, 3
0x18001b088  jnz     short loc_18001B0A0
0x18001b08a  lea     eax, [rsi-1]
0x18001b08d  test    eax, 0FFFFFFFDh
0x18001b092  jnz     short loc_18001B0A7
0x18001b094  test    edx, edx
0x18001b096  jnz     short loc_18001B0A7
0x18001b098  mov     edx, ecx
0x18001b09a  mov     [rsp+68h+arg_8], ecx
0x18001b09e  jmp     short loc_18001B0A7
0x18001b0a0  mov     edx, r14d
0x18001b0a3  mov     [rsp+68h+arg_8], edx
0x18001b0a7  lea     r8, [rsp+68h+pv]
0x18001b0ac  mov     ecx, r14d
0x18001b0af  call    ScPolicyCheckForAutoReConnect
0x18001b0b4  mov     esi, eax
0x18001b0b6  mov     rdi, [rsp+68h+pv]
0x18001b0bb  test    eax, eax
0x18001b0bd  jnz     loc_18001B1E7
0x18001b0c3  test    rdi, rdi
0x18001b0c6  jnz     loc_18001B188
0x18001b0cc  lea     rdx, [rsp+68h+hObject]
0x18001b0d1  mov     ecx, r14d
0x18001b0d4  call    CommonGetImpersonationToken
0x18001b0d9  mov     esi, eax
0x18001b0db  test    eax, eax
0x18001b0dd  jnz     loc_18001B1E7
0x18001b0e3  lea     rax, [rsp+68h+lpMem]
0x18001b0e8  mov     [rsp+68h+var_48], rax
0x18001b0ed  lea     r9, [rsp+68h+arg_18]
0x18001b0f5  mov     r8d, [rsp+68h+arg_8]
0x18001b0fa  call    ScPolicyRetrieveLogonReaderInfo
0x18001b0ff  mov     esi, eax
0x18001b101  test    eax, eax
0x18001b103  jnz     loc_18001B1E7
0x18001b109  lea     edx, [rdi+8]; dwFlags
0x18001b10c  lea     r8d, [rdi+58h]; dwBytes
0x18001b110  mov     rcx, cs:g_hScPolicyHeap; hHeap
0x18001b117  call    cs:__imp_HeapAlloc
0x18001b11d  mov     rdi, rax
0x18001b120  mov     [rsp+68h+pv], rax
0x18001b125  test    rax, rax
0x18001b128  jnz     short loc_18001B132
0x18001b12a  lea     esi, [rax+8]
0x18001b12d  jmp     loc_18001B1E7
0x18001b132  lea     rcx, [rax+8]; lpCriticalSection
0x18001b136  call    cs:__imp_InitializeCriticalSection
0x18001b13c  nop
0x18001b13d  mov     dword ptr [rdi+30h], 1
0x18001b144  mov     eax, [rsp+68h+arg_18]
0x18001b14b  mov     [rdi+4Ch], eax
0x18001b14e  mov     rax, [rsp+68h+lpMem]
0x18001b153  mov     [rdi+40h], rax
0x18001b157  mov     [rsp+68h+lpMem], 0
0x18001b160  mov     [rdi+34h], r14d
0x18001b164  mov     rax, [rsp+68h+hObject]
0x18001b169  mov     [rdi+38h], rax
0x18001b16d  mov     [rsp+68h+hObject], 0
0x18001b176  jmp     short loc_18001B188
0x18001b178  mov     esi, eax
0x18001b17a  lea     r15, WPP_GLOBAL_Control
0x18001b181  mov     rdi, [rsp+68h+pv]
0x18001b186  jmp     short loc_18001B1E7
0x18001b188  lea     r14, g_csScPolicyList
0x18001b18f  mov     rcx, r14; lpCriticalSection
0x18001b192  call    cs:__imp_EnterCriticalSection
0x18001b198  lea     r8, pcbe; pcbe
0x18001b19f  mov     rdx, rdi; pv
0x18001b1a2  lea     rcx, ScPolicyThreadProc; pfnwk
0x18001b1a9  call    cs:__imp_CreateThreadpoolWork
0x18001b1af  test    rax, rax
0x18001b1b2  jnz     short loc_18001B1C2
0x18001b1b4  mov     rcx, r14; lpCriticalSection
0x18001b1b7  call    cs:__imp_LeaveCriticalSection
0x18001b1bd  jmp     loc_18001B02E
0x18001b1c2  mov     rcx, rax; pwk
0x18001b1c5  call    cs:__imp_SubmitThreadpoolWork
0x18001b1cb  mov     rax, cs:g_pScPolicyList
0x18001b1d2  mov     [rdi], rax
0x18001b1d5  mov     cs:g_pScPolicyList, rdi
0x18001b1dc  mov     rcx, r14; lpCriticalSection
0x18001b1df  call    cs:__imp_LeaveCriticalSection
0x18001b1e5  xor     edi, edi
0x18001b1e7  mov     r8, [rsp+68h+lpMem]; lpMem
0x18001b1ec  test    r8, r8
0x18001b1ef  jz      short loc_18001B200
0x18001b1f1  xor     edx, edx; dwFlags
0x18001b1f3  mov     rcx, cs:g_hScPolicyHeap; hHeap
0x18001b1fa  call    cs:__imp_HeapFree
0x18001b200  mov     rcx, [rsp+68h+hObject]; hObject
0x18001b205  test    rcx, rcx
0x18001b208  jz      short loc_18001B210
0x18001b20a  call    cs:__imp_CloseHandle
0x18001b210  test    rdi, rdi
0x18001b213  jz      short loc_18001B21D
0x18001b215  mov     rcx, rdi
0x18001b218  call    ScPolicyFreeListNode
0x18001b21d  mov     edx, 2
0x18001b222  call    WppTraceIndent
0x18001b227  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b22e  cmp     rcx, r15
0x18001b231  jz      short loc_18001B25F
0x18001b233  test    byte ptr [rcx+1Ch], 1
0x18001b237  jz      short loc_18001B25F
0x18001b239  cmp     byte ptr [rcx+19h], 4
0x18001b23d  jb      short loc_18001B25F
0x18001b23f  mov     edx, 16h
0x18001b244  mov     dword ptr [rsp+68h+var_48], esi
0x18001b248  mov     r9, cs:WPP_pszIndent
0x18001b24f  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001b256  mov     rcx, [rcx+10h]
0x18001b25a  call    WPP_SF_sD
0x18001b25f  mov     eax, esi
0x18001b261  mov     rsi, [rsp+68h+arg_0]
0x18001b266  add     rsp, 50h
0x18001b26a  pop     r15
0x18001b26c  pop     r14
0x18001b26e  pop     rdi
0x18001b26f  retn
```
