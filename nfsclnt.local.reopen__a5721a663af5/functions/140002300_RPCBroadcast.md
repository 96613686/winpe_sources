# RPCBroadcast

- ea: `0x140002300`
- end: `0x140002648`
- name: `RPCBroadcast`
- size: `840`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140009180`

## callees

- `0x140001b5c`
- `0x140002300`
- `0x140002bd8`
- `0x140002c40`
- `0x140002ddc`
- `0x140002fbc`
- `0x140018350`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400023c9`
- `ADVAPI32!RegOpenKeyExW` at `0x1400023c9`
- `ADVAPI32!RegQueryValueExA` at `0x140002400`
- `ADVAPI32!RegQueryValueExA` at `0x140002400`
- `ADVAPI32!RegCloseKey` at `0x140002439`
- `ADVAPI32!RegCloseKey` at `0x140002439`
- `KERNEL32!EnterCriticalSection` at `0x140002473`
- `KERNEL32!EnterCriticalSection` at `0x140002531`
- `KERNEL32!EnterCriticalSection` at `0x140002473`
- `KERNEL32!EnterCriticalSection` at `0x140002531`
- `KERNEL32!GlobalFree` at `0x140002582`
- `KERNEL32!GlobalFree` at `0x140002582`
- `KERNEL32!LeaveCriticalSection` at `0x140002487`
- `KERNEL32!LeaveCriticalSection` at `0x1400024b9`
- `KERNEL32!LeaveCriticalSection` at `0x140002593`
- `KERNEL32!LeaveCriticalSection` at `0x140002487`
- `KERNEL32!LeaveCriticalSection` at `0x1400024b9`
- `KERNEL32!LeaveCriticalSection` at `0x140002593`
- `KERNEL32!GetCurrentThreadId` at `0x14000236e`
- `KERNEL32!GetCurrentThreadId` at `0x14000236e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000249c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000249c`
- `KERNEL32!SetEvent` at `0x1400025c8`
- `KERNEL32!SetEvent` at `0x1400025c8`
- `KERNEL32!GetLastError` at `0x1400025e8`
- `KERNEL32!GetLastError` at `0x1400025e8`

## string_xrefs

- `0x1400023bb`: `SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall RPCBroadcast(char *a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  int v4; // ebx
  char CurrentThreadId; // al
  int v6; // edx
  int v7; // r8d
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  __int64 i; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rbx
  char LastError; // al
  DWORD cbData; // [rsp+40h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-30h] BYREF
  char v26[16]; // [rsp+50h] [rbp-28h] BYREF

  strcpy(v26, "RPCBroadcast");
  cbData = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v2 = *((_QWORD *)a1 + 1);
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v4 = **((_DWORD **)a1 + 3);
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_sSDd(v3, v6, v7, (unsigned int)v26, v2, v4, CurrentThreadId);
  }
  if ( !Data )
  {
    hKey = 0;
    v8 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters",
           0,
           0x20019u,
           &hKey);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)&WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids,
          (unsigned int)v26,
          v8);
    }
    else
    {
      cbData = 260;
      v9 = RegQueryValueExA(hKey, "Domain", 0, 0, &Data, &cbData);
      if ( v9
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)&WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids,
          (unsigned int)v26,
          v9);
      }
      RegCloseKey(hKey);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  *(_DWORD *)a1 &= ~1u;
  if ( (*(_DWORD *)a1 & 2) != 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    return 0;
  }
  *(_DWORD *)a1 |= 2u;
  GetSystemTimeAsFileTime((LPFILETIME)a1 + 5);
  for ( i = *((_QWORD *)a1 + 4); i; i = *(_QWORD *)(i + 16) )
    *(_DWORD *)(i + 12) &= ~0x10000u;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  Broadcast(v12, v11, v13, a1);
  if ( ssStatus.dwCurrentState == 4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    v15 = *((_QWORD *)a1 + 4);
    if ( v15 )
    {
      do
      {
        v16 = *(_QWORD *)(v15 + 16);
        if ( (*(_DWORD *)(v15 + 12) & 0x10000) == 0 )
        {
          v17 = *(_QWORD *)(v15 + 24);
          if ( v17 )
          {
            *(_QWORD *)(v17 + 16) = v16;
            v18 = *(_QWORD *)(v15 + 16);
            if ( v18 )
              *(_QWORD *)(v18 + 24) = *(_QWORD *)(v15 + 24);
          }
          else
          {
            *((_QWORD *)a1 + 4) = v16;
            v19 = *(_QWORD *)(v15 + 16);
            if ( v19 )
              *(_QWORD *)(v19 + 24) = 0;
          }
          GlobalFree((HGLOBAL)v15);
        }
        v15 = v16;
      }
      while ( v16 );
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids);
    v20 = *((_QWORD *)a1 + 3);
    *(_DWORD *)a1 &= ~2u;
    if ( !SetEvent(*(HANDLE *)(v20 + 32)) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_44:
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
          WPP_SF_s(v21[2], 31, &WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids, v26);
        return 0;
      }
      v22 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_sd(v22, 30, (unsigned int)&WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids, (unsigned int)v26, LastError);
    }
    v21 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)&WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids,
      (unsigned int)v26,
      ssStatus.dwCurrentState);
  *(_DWORD *)a1 &= ~2u;
  return 1;
}

```

## disassembly

```asm
0x140002300  push    rbp
0x140002302  push    rbx
0x140002303  push    rsi
0x140002304  push    rdi
0x140002305  push    r12
0x140002307  push    r14
0x140002309  mov     rbp, rsp
0x14000230c  sub     rsp, 78h
0x140002310  mov     rax, cs:__security_cookie
0x140002317  xor     rax, rsp
0x14000231a  mov     [rbp+var_18], rax
0x14000231e  mov     eax, dword ptr cs:aRpcbroadcast+8; "cast"
0x140002324  mov     r14, rcx
0x140002327  movsd   xmm0, qword ptr cs:aRpcbroadcast; "RPCBroadcast"
0x14000232f  mov     dword ptr [rbp+var_28+8], eax
0x140002332  mov     al, byte ptr cs:aRpcbroadcast+0Ch; ""
0x140002338  mov     [rbp+var_28+0Ch], al
0x14000233b  movsd   qword ptr [rbp+var_28], xmm0
0x140002340  mov     [rbp+cbData], 0
0x140002347  mov     rsi, cs:WPP_GLOBAL_Control
0x14000234e  lea     r12, WPP_GLOBAL_Control
0x140002355  cmp     rsi, r12
0x140002358  jz      short loc_14000238D
0x14000235a  test    byte ptr [rsi+1Ch], 10h
0x14000235e  jz      short loc_14000238D
0x140002360  mov     rax, [rcx+18h]
0x140002364  mov     rdi, [rcx+8]
0x140002368  mov     rsi, [rsi+10h]
0x14000236c  mov     ebx, [rax]
0x14000236e  call    cs:__imp_GetCurrentThreadId
0x140002374  mov     [rsp+78h+var_48], eax
0x140002378  lea     r9, [rbp+var_28]
0x14000237c  mov     dword ptr [rsp+78h+lpcbData], ebx
0x140002380  mov     rcx, rsi
0x140002383  mov     [rsp+78h+phkResult], rdi
0x140002388  call    WPP_SF_sSDd
0x14000238d  cmp     cs:Data, 0
0x140002394  lea     rsi, WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids
0x14000239b  jnz     loc_14000246C
0x1400023a1  lea     rax, [rbp+hKey]
0x1400023a5  mov     [rbp+hKey], 0
0x1400023ad  mov     r9d, 20019h; samDesired
0x1400023b3  mov     [rsp+78h+phkResult], rax; phkResult
0x1400023b8  xor     r8d, r8d; ulOptions
0x1400023bb  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x1400023c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400023c9  call    cs:__imp_RegOpenKeyExW
0x1400023cf  test    eax, eax
0x1400023d1  jnz     short loc_140002441
0x1400023d3  mov     rcx, [rbp+hKey]; hKey
0x1400023d7  lea     rax, [rbp+cbData]
0x1400023db  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1400023e0  lea     rdx, ValueName; "Domain"
0x1400023e7  lea     rax, Data
0x1400023ee  mov     [rbp+cbData], 104h
0x1400023f5  xor     r9d, r9d; lpType
0x1400023f8  mov     [rsp+78h+phkResult], rax; lpData
0x1400023fd  xor     r8d, r8d; lpReserved
0x140002400  call    cs:__imp_RegQueryValueExA
0x140002406  test    eax, eax
0x140002408  jz      short loc_140002435
0x14000240a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002411  cmp     rcx, r12
0x140002414  jz      short loc_140002435
0x140002416  test    byte ptr [rcx+1Ch], 10h
0x14000241a  jz      short loc_140002435
0x14000241c  mov     rcx, [rcx+10h]
0x140002420  lea     r9, [rbp+var_28]
0x140002424  mov     edx, 1Bh
0x140002429  mov     dword ptr [rsp+78h+phkResult], eax
0x14000242d  mov     r8, rsi
0x140002430  call    WPP_SF_sd
0x140002435  mov     rcx, [rbp+hKey]; hKey
0x140002439  call    cs:__imp_RegCloseKey
0x14000243f  jmp     short loc_14000246C
0x140002441  mov     rcx, cs:WPP_GLOBAL_Control
0x140002448  cmp     rcx, r12
0x14000244b  jz      short loc_14000246C
0x14000244d  test    byte ptr [rcx+1Ch], 10h
0x140002451  jz      short loc_14000246C
0x140002453  mov     rcx, [rcx+10h]
0x140002457  lea     r9, [rbp+var_28]
0x14000245b  mov     edx, 1Ch
0x140002460  mov     dword ptr [rsp+78h+phkResult], eax
0x140002464  mov     r8, rsi
0x140002467  call    WPP_SF_sd
0x14000246c  lea     rbx, [r14+40h]
0x140002470  mov     rcx, rbx; lpCriticalSection
0x140002473  call    cs:__imp_EnterCriticalSection
0x140002479  and     dword ptr [r14], 0FFFFFFFEh
0x14000247d  mov     eax, [r14]
0x140002480  test    al, 2
0x140002482  jz      short loc_140002492
0x140002484  mov     rcx, rbx; lpCriticalSection
0x140002487  call    cs:__imp_LeaveCriticalSection
0x14000248d  jmp     loc_14000262D
0x140002492  or      eax, 2
0x140002495  lea     rcx, [r14+28h]; lpSystemTimeAsFileTime
0x140002499  mov     [r14], eax
0x14000249c  call    cs:__imp_GetSystemTimeAsFileTime
0x1400024a2  mov     rax, [r14+20h]
0x1400024a6  jmp     short loc_1400024B1
0x1400024a8  btr     dword ptr [rax+0Ch], 10h
0x1400024ad  mov     rax, [rax+10h]
0x1400024b1  test    rax, rax
0x1400024b4  jnz     short loc_1400024A8
0x1400024b6  mov     rcx, rbx; lpCriticalSection
0x1400024b9  call    cs:__imp_LeaveCriticalSection
0x1400024bf  mov     r9, r14
0x1400024c2  call    Broadcast
0x1400024c7  mov     eax, cs:ssStatus.dwCurrentState
0x1400024cd  cmp     eax, 4
0x1400024d0  jz      short loc_14000250B
0x1400024d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400024d9  cmp     rcx, r12
0x1400024dc  jz      short loc_1400024FD
0x1400024de  test    byte ptr [rcx+1Ch], 2
0x1400024e2  jz      short loc_1400024FD
0x1400024e4  mov     rcx, [rcx+10h]
0x1400024e8  lea     r9, [rbp+var_28]
0x1400024ec  mov     edx, 1Dh
0x1400024f1  mov     dword ptr [rsp+78h+phkResult], eax
0x1400024f5  mov     r8, rsi
0x1400024f8  call    WPP_SF_sd
0x1400024fd  and     dword ptr [r14], 0FFFFFFFDh
0x140002501  mov     eax, 1
0x140002506  jmp     loc_14000262F
0x14000250b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002512  cmp     rcx, r12
0x140002515  jz      short loc_14000252E
0x140002517  test    byte ptr [rcx+1Ch], 1
0x14000251b  jz      short loc_14000252E
0x14000251d  mov     rcx, [rcx+10h]
0x140002521  mov     edx, 13h
0x140002526  mov     r8, rsi
0x140002529  call    WPP_SF_
0x14000252e  mov     rcx, rbx; lpCriticalSection
0x140002531  call    cs:__imp_EnterCriticalSection
0x140002537  mov     rcx, [r14+20h]; hMem
0x14000253b  test    rcx, rcx
0x14000253e  jz      short loc_140002590
0x140002540  test    dword ptr [rcx+0Ch], 10000h
0x140002547  mov     rdi, [rcx+10h]
0x14000254b  jnz     short loc_140002588
0x14000254d  mov     rax, [rcx+18h]
0x140002551  test    rax, rax
0x140002554  jz      short loc_14000256D
0x140002556  mov     [rax+10h], rdi
0x14000255a  mov     rdx, [rcx+10h]
0x14000255e  test    rdx, rdx
0x140002561  jz      short loc_140002582
0x140002563  mov     rax, [rcx+18h]
0x140002567  mov     [rdx+18h], rax
0x14000256b  jmp     short loc_140002582
0x14000256d  mov     [r14+20h], rdi
0x140002571  mov     rax, [rcx+10h]
0x140002575  test    rax, rax
0x140002578  jz      short loc_140002582
0x14000257a  mov     qword ptr [rax+18h], 0
0x140002582  call    cs:__imp_GlobalFree
0x140002588  mov     rcx, rdi
0x14000258b  test    rdi, rdi
0x14000258e  jnz     short loc_140002540
0x140002590  mov     rcx, rbx; lpCriticalSection
0x140002593  call    cs:__imp_LeaveCriticalSection
0x140002599  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025a0  cmp     rcx, r12
0x1400025a3  jz      short loc_1400025BC
0x1400025a5  test    byte ptr [rcx+1Ch], 1
0x1400025a9  jz      short loc_1400025BC
0x1400025ab  mov     rcx, [rcx+10h]
0x1400025af  mov     edx, 14h
0x1400025b4  mov     r8, rsi
0x1400025b7  call    WPP_SF_
0x1400025bc  mov     rcx, [r14+18h]
0x1400025c0  and     dword ptr [r14], 0FFFFFFFDh
0x1400025c4  mov     rcx, [rcx+20h]; hEvent
0x1400025c8  call    cs:__imp_SetEvent
0x1400025ce  test    eax, eax
0x1400025d0  jnz     short loc_140002606
0x1400025d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025d9  cmp     rcx, r12
0x1400025dc  jz      short loc_14000262D
0x1400025de  test    byte ptr [rcx+1Ch], 2
0x1400025e2  jz      short loc_14000260D
0x1400025e4  mov     rbx, [rcx+10h]
0x1400025e8  call    cs:__imp_GetLastError
0x1400025ee  mov     edx, 1Eh
0x1400025f3  lea     r9, [rbp+var_28]
0x1400025f7  mov     r8, rsi
0x1400025fa  mov     dword ptr [rsp+78h+phkResult], eax
0x1400025fe  mov     rcx, rbx
0x140002601  call    WPP_SF_sd
0x140002606  mov     rcx, cs:WPP_GLOBAL_Control
0x14000260d  cmp     rcx, r12
0x140002610  jz      short loc_14000262D
0x140002612  test    byte ptr [rcx+1Ch], 1
0x140002616  jz      short loc_14000262D
0x140002618  mov     rcx, [rcx+10h]
0x14000261c  lea     r9, [rbp+var_28]
0x140002620  mov     edx, 1Fh
0x140002625  mov     r8, rsi
0x140002628  call    WPP_SF_s
0x14000262d  xor     eax, eax
0x14000262f  mov     rcx, [rbp+var_18]
0x140002633  xor     rcx, rsp; StackCookie
0x140002636  call    __security_check_cookie
0x14000263b  add     rsp, 78h
0x14000263f  pop     r14
0x140002641  pop     r12
0x140002643  pop     rdi
0x140002644  pop     rsi
0x140002645  pop     rbx
0x140002646  pop     rbp
0x140002647  retn
```
