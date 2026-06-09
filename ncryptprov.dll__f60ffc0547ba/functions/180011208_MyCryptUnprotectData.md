# MyCryptUnprotectData

- ea: `0x180011208`
- end: `0x180011542`
- name: `MyCryptUnprotectData`
- size: `826`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwMilliseconds, __int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016218`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x180010fac`
- `0x180011208`
- `0x180011548`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180011447`
- `ntdll!RtlNtStatusToDosError` at `0x180011479`
- `ntdll!RtlNtStatusToDosError` at `0x180011447`
- `ntdll!RtlNtStatusToDosError` at `0x180011479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001139c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001139c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001133d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001133d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800113e3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800113e3`
- `DPAPI!CryptUnprotectDataNoUI` at `0x1800112fa`
- `DPAPI!CryptUnprotectDataNoUI` at `0x1800112fa`

## string_xrefs

- `0x1800112bf`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x1800114be`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180011511`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`

## pseudocode

```c
__int64 __fastcall MyCryptUnprotectData(
        __int64 a1,
        int a2,
        __int64 a3,
        int *a4,
        int dwMilliseconds,
        __int64 a6,
        int a7,
        int a8,
        __int64 a9,
        _DWORD *a10)
{
  void *v10; // rdi
  __int64 v12; // rax
  _DWORD *v13; // rsi
  int v14; // r13d
  int v15; // r15d
  ULONG v16; // ebx
  NTSTATUS v18; // eax
  int v19; // edx
  int v20; // r8d
  NTSTATUS v21; // ebx
  DWORD LastError; // eax
  int v23; // edx
  int v24; // r8d
  int v25; // ebx
  int v26; // eax
  NTSTATUS v27; // esi
  ULONG v28; // eax
  __int64 v29; // [rsp+50h] [rbp-48h]
  int v30; // [rsp+A0h] [rbp+8h]
  void *v31; // [rsp+A8h] [rbp+10h] BYREF
  __int64 v32; // [rsp+B0h] [rbp+18h]

  v32 = a3;
  v10 = 0;
  v31 = 0;
  if ( a1 && (v12 = a9) != 0 && *(_QWORD *)(a1 + 8) )
  {
    v13 = a10;
    v14 = 0;
    v15 = a7;
    v29 = 0;
    v30 = 0;
    if ( a10 )
    {
      *a10 = 0;
      v15 |= 0x41u;
    }
    if ( a4 )
    {
      v29 = *((_QWORD *)a4 + 1);
      v30 = *a4;
    }
    if ( !a8 )
    {
LABEL_9:
      LODWORD(v31) = 0;
      dwMilliseconds = 10;
      while ( !(unsigned int)CryptUnprotectDataNoUI(a1, 0, a3, 0, a6, v15, v29, v30, v12) )
      {
        LastError = GetLastError();
        v16 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v23,
            v24,
            (unsigned int)"dwSts",
            LastError,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
            21);
        if ( v16 != 1723 || (unsigned int)v31 >= 5 )
          goto LABEL_15;
        v25 = dwMilliseconds;
        Sleep(dwMilliseconds);
        v12 = a9;
        LODWORD(v31) = (_DWORD)v31 + 1;
        a3 = v32;
        dwMilliseconds = 2 * v25;
      }
      if ( v13 && GetLastError() == 593938 )
        *v13 |= 8u;
      v16 = 0;
LABEL_15:
      if ( v14 )
      {
        v26 = RevertBackToCallerToken((__int64)v10);
        v27 = v26;
        if ( v26 < 0 )
        {
          DebugTraceError(
            (unsigned int)v26,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
            572);
          if ( !v16 )
            v16 = RtlNtStatusToDosError(v27);
        }
      }
      goto LABEL_16;
    }
    v18 = RevertToLocalSystem(&v31);
    v21 = v18;
    if ( !v18 )
    {
      v10 = v31;
      v14 = 1;
      v12 = a9;
      a3 = v32;
      goto LABEL_9;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        v20,
        (unsigned int)"Status",
        v18,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
        254);
    v28 = RtlNtStatusToDosError(v21);
    v10 = v31;
    v16 = v28;
  }
  else
  {
    v16 = 87;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v16;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)"dwReturn",
      87,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
      232);
  }
LABEL_16:
  if ( v10 )
    CloseHandle(v10);
  return v16;
}

```

## disassembly

```asm
0x180011208  mov     rax, rsp
0x18001120b  mov     [rax+20h], rbx
0x18001120f  mov     [rax+18h], r8
0x180011213  mov     [rax+10h], rdx
0x180011217  push    rbp
0x180011218  push    rsi
0x180011219  push    rdi
0x18001121a  push    r12
0x18001121c  push    r13
0x18001121e  push    r14
0x180011220  push    r15
0x180011222  sub     rsp, 60h
0x180011226  xor     edi, edi
0x180011228  mov     r12, rcx
0x18001122b  mov     [rax+10h], rdi
0x18001122f  test    rcx, rcx
0x180011232  jz      loc_180011494
0x180011238  mov     rax, [rsp+98h+arg_40]
0x180011240  test    rax, rax
0x180011243  jz      loc_180011494
0x180011249  cmp     [rcx+8], rdi
0x18001124d  jz      loc_180011494
0x180011253  mov     rsi, [rsp+98h+arg_48]
0x18001125b  xor     r13d, r13d
0x18001125e  mov     r15d, [rsp+98h+arg_30]
0x180011266  mov     [rsp+98h+var_48], rdi
0x18001126b  mov     [rsp+98h+arg_0], edi
0x180011272  test    rsi, rsi
0x180011275  jz      short loc_18001127D
0x180011277  mov     [rsi], edi
0x180011279  or      r15d, 41h
0x18001127d  test    r9, r9
0x180011280  jz      short loc_180011295
0x180011282  mov     rcx, [r9+8]
0x180011286  mov     [rsp+98h+var_48], rcx
0x18001128b  mov     ecx, [r9]
0x18001128e  mov     [rsp+98h+arg_0], ecx
0x180011295  cmp     [rsp+98h+arg_38], edi
0x18001129c  jnz     loc_180011364
0x1800112a2  mov     dword ptr [rsp+98h+arg_8], 0
0x1800112ad  lea     r14, WPP_GLOBAL_Control
0x1800112b4  mov     [rsp+98h+dwMilliseconds], 0Ah
0x1800112bf  lea     rbp, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800112c6  mov     [rsp+98h+var_58], rax
0x1800112cb  xor     r9d, r9d
0x1800112ce  mov     eax, [rsp+98h+arg_0]
0x1800112d5  xor     edx, edx
0x1800112d7  mov     [rsp+98h+var_60], eax
0x1800112db  mov     rcx, r12
0x1800112de  mov     rax, [rsp+98h+var_48]
0x1800112e3  mov     [rsp+98h+var_68], rax
0x1800112e8  mov     rax, [rsp+98h+arg_28]
0x1800112f0  mov     dword ptr [rsp+98h+var_70], r15d
0x1800112f5  mov     [rsp+98h+var_78], rax
0x1800112fa  call    cs:__imp_CryptUnprotectDataNoUI
0x180011301  nop     dword ptr [rax+rax+00h]
0x180011306  test    eax, eax
0x180011308  jz      loc_18001139C
0x18001130e  test    rsi, rsi
0x180011311  jz      short loc_18001132A
0x180011313  call    cs:__imp_GetLastError
0x18001131a  nop     dword ptr [rax+rax+00h]
0x18001131f  cmp     eax, 91012h
0x180011324  jz      loc_18001153A
0x18001132a  xor     ebx, ebx
0x18001132c  test    r13d, r13d
0x18001132f  jnz     loc_180011414
0x180011335  test    rdi, rdi
0x180011338  jz      short loc_180011349
0x18001133a  mov     rcx, rdi; hObject
0x18001133d  call    cs:__imp_CloseHandle
0x180011344  nop     dword ptr [rax+rax+00h]
0x180011349  mov     eax, ebx
0x18001134b  mov     rbx, [rsp+98h+arg_18]
0x180011353  add     rsp, 60h
0x180011357  pop     r15
0x180011359  pop     r14
0x18001135b  pop     r13
0x18001135d  pop     r12
0x18001135f  pop     rdi
0x180011360  pop     rsi
0x180011361  pop     rbp
0x180011362  retn
0x180011364  lea     rcx, [rsp+98h+arg_8]
0x18001136c  call    RevertToLocalSystem
0x180011371  mov     ebx, eax
0x180011373  test    eax, eax
0x180011375  jnz     loc_18001145A
0x18001137b  mov     rdi, [rsp+98h+arg_8]
0x180011383  lea     r13d, [rax+1]
0x180011387  mov     rax, [rsp+98h+arg_40]
0x18001138f  mov     r8, [rsp+98h+arg_10]
0x180011397  jmp     loc_1800112A2
0x18001139c  call    cs:__imp_GetLastError
0x1800113a3  nop     dword ptr [rax+rax+00h]
0x1800113a8  mov     ebx, eax
0x1800113aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113b1  cmp     rcx, r14
0x1800113b4  jz      short loc_1800113C0
0x1800113b6  test    byte ptr [rcx+1Ch], 1
0x1800113ba  jnz     loc_1800114E7
0x1800113c0  cmp     ebx, 6BBh
0x1800113c6  jnz     loc_18001132C
0x1800113cc  cmp     dword ptr [rsp+98h+arg_8], 5
0x1800113d4  jnb     loc_18001132C
0x1800113da  mov     ebx, [rsp+98h+dwMilliseconds]
0x1800113e1  mov     ecx, ebx; dwMilliseconds
0x1800113e3  call    cs:__imp_Sleep
0x1800113ea  nop     dword ptr [rax+rax+00h]
0x1800113ef  mov     rax, [rsp+98h+arg_40]
0x1800113f7  add     ebx, ebx
0x1800113f9  inc     dword ptr [rsp+98h+arg_8]
0x180011400  mov     r8, [rsp+98h+arg_10]
0x180011408  mov     [rsp+98h+dwMilliseconds], ebx
0x18001140f  jmp     loc_1800112C6
0x180011414  mov     rcx, rdi
0x180011417  call    RevertBackToCallerToken
0x18001141c  mov     esi, eax
0x18001141e  test    eax, eax
0x180011420  jns     loc_180011335
0x180011426  mov     r9d, 23Ch
0x18001142c  lea     rdx, aStatus; "Status"
0x180011433  mov     r8, rbp
0x180011436  mov     ecx, eax
0x180011438  call    DebugTraceError
0x18001143d  test    ebx, ebx
0x18001143f  jnz     loc_180011335
0x180011445  mov     ecx, esi; Status
0x180011447  call    cs:__imp_RtlNtStatusToDosError
0x18001144e  nop     dword ptr [rax+rax+00h]
0x180011453  mov     ebx, eax
0x180011455  jmp     loc_180011335
0x18001145a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011461  lea     r14, WPP_GLOBAL_Control
0x180011468  cmp     rcx, r14
0x18001146b  jz      short loc_180011477
0x18001146d  test    byte ptr [rcx+1Ch], 1
0x180011471  jnz     loc_18001150D
0x180011477  mov     ecx, ebx; Status
0x180011479  call    cs:__imp_RtlNtStatusToDosError
0x180011480  nop     dword ptr [rax+rax+00h]
0x180011485  mov     rdi, [rsp+98h+arg_8]
0x18001148d  mov     ebx, eax
0x18001148f  jmp     loc_180011335
0x180011494  mov     ebx, 57h ; 'W'
0x180011499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114a0  lea     r14, WPP_GLOBAL_Control
0x1800114a7  cmp     rcx, r14
0x1800114aa  jz      loc_180011349
0x1800114b0  test    byte ptr [rcx+1Ch], 1
0x1800114b4  jz      loc_180011349
0x1800114ba  mov     rcx, [rcx+10h]
0x1800114be  lea     rbp, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800114c5  mov     dword ptr [rsp+98h+var_68], 1E8h
0x1800114cd  lea     r9, aDwreturn; "dwReturn"
0x1800114d4  mov     [rsp+98h+var_70], rbp
0x1800114d9  mov     dword ptr [rsp+98h+var_78], ebx
0x1800114dd  call    WPP_SF_sDsd
0x1800114e2  jmp     loc_180011335
0x1800114e7  mov     rcx, [rcx+10h]
0x1800114eb  lea     r9, aDwsts; "dwSts"
0x1800114f2  mov     dword ptr [rsp+98h+var_68], 215h
0x1800114fa  mov     [rsp+98h+var_70], rbp
0x1800114ff  mov     dword ptr [rsp+98h+var_78], ebx
0x180011503  call    WPP_SF_sDsd
0x180011508  jmp     loc_1800113C0
0x18001150d  mov     rcx, [rcx+10h]
0x180011511  lea     rbp, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011518  mov     dword ptr [rsp+98h+var_68], 1FEh
0x180011520  lea     r9, aStatus; "Status"
0x180011527  mov     [rsp+98h+var_70], rbp
0x18001152c  mov     dword ptr [rsp+98h+var_78], ebx
0x180011530  call    WPP_SF_sDsd
0x180011535  jmp     loc_180011477
0x18001153a  or      dword ptr [rsi], 8
0x18001153d  jmp     loc_18001132A
```
