# s_SignWithSymmetricPopKey

- ea: `0x1800073e0`
- end: `0x180007567`
- name: `s_SignWithSymmetricPopKey`
- size: `391`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, __int64, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800073e0`
- `0x18000b62c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007405`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007405`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000748b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000748b`

## string_xrefs

- `0x1800074ec`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x180007519`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x180007545`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SignWithSymmetricPopKey(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  int v14; // edx
  int v15; // ebx
  int v16; // r8d
  int v18; // edx
  int PopKeyFunctionTable; // ebp
  int v20; // r8d

  if ( g_ngcFuncLoaded || (PopKeyFunctionTable = LoadPopKeyFunctionTable(), PopKeyFunctionTable >= 0) )
  {
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v15 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, int, __int64, __int64))qword_1800259B0)(
              a3,
              a2,
              a5,
              a4,
              a7,
              a6,
              a9,
              a8,
              a11,
              a10);
      if ( v15 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v16,
          (unsigned int)"hr",
          v15,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
          162);
      }
    }
    else
    {
      v15 = -2146893779;
      DebugTraceError(
        2148073517LL,
        "hr",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
        401);
    }
    ReleaseSRWLockShared(&g_ngcFuncLoadLock);
    return (unsigned int)v15;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        v20,
        (unsigned int)"hr",
        PopKeyFunctionTable,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
        134);
    return (unsigned int)PopKeyFunctionTable;
  }
}

```

## disassembly

```asm
0x1800073e0  push    rbx
0x1800073e2  push    rbp
0x1800073e3  push    rsi
0x1800073e4  push    rdi
0x1800073e5  sub     rsp, 68h
0x1800073e9  cmp     cs:g_ngcFuncLoaded, 0
0x1800073f0  mov     edi, r9d
0x1800073f3  mov     rsi, r8
0x1800073f6  mov     ebx, edx
0x1800073f8  jz      loc_18000749C
0x1800073fe  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x180007405  call    cs:__imp_AcquireSRWLockShared
0x18000740b  cmp     cs:g_ngcFuncLoaded, 0
0x180007412  jz      loc_18000753F
0x180007418  mov     rcx, [rsp+88h+arg_50]
0x180007420  mov     r9d, edi
0x180007423  mov     rax, [rsp+88h+arg_48]
0x18000742b  mov     edx, ebx
0x18000742d  mov     r8, [rsp+88h+arg_20]
0x180007435  mov     [rsp+88h+var_40], rax
0x18000743a  mov     rax, cs:qword_1800259B0
0x180007441  mov     [rsp+88h+var_48], rcx
0x180007446  mov     ecx, [rsp+88h+arg_38]
0x18000744d  mov     [rsp+88h+var_50], ecx
0x180007451  mov     rcx, [rsp+88h+arg_40]
0x180007459  mov     [rsp+88h+var_58], rcx
0x18000745e  mov     ecx, [rsp+88h+arg_28]
0x180007465  mov     dword ptr [rsp+88h+var_60], ecx
0x180007469  mov     rcx, [rsp+88h+arg_30]
0x180007471  mov     [rsp+88h+var_68], rcx
0x180007476  mov     rcx, rsi
0x180007479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000747e  mov     ebx, eax
0x180007480  test    eax, eax
0x180007482  js      short loc_1800074CF
0x180007484  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000748b  call    cs:__imp_ReleaseSRWLockShared
0x180007491  mov     eax, ebx
0x180007493  add     rsp, 68h
0x180007497  pop     rdi
0x180007498  pop     rsi
0x180007499  pop     rbp
0x18000749a  pop     rbx
0x18000749b  retn
0x18000749c  call    LoadPopKeyFunctionTable
0x1800074a1  mov     ebp, eax
0x1800074a3  test    eax, eax
0x1800074a5  jns     loc_1800073FE
0x1800074ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074b2  lea     rax, WPP_GLOBAL_Control
0x1800074b9  cmp     rcx, rax
0x1800074bc  jz      short loc_1800074C4
0x1800074be  test    byte ptr [rcx+1Ch], 1
0x1800074c2  jnz     short loc_180007515
0x1800074c4  mov     eax, ebp
0x1800074c6  add     rsp, 68h
0x1800074ca  pop     rdi
0x1800074cb  pop     rsi
0x1800074cc  pop     rbp
0x1800074cd  pop     rbx
0x1800074ce  retn
0x1800074cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074d6  lea     rax, WPP_GLOBAL_Control
0x1800074dd  cmp     rcx, rax
0x1800074e0  jz      short loc_180007484
0x1800074e2  test    byte ptr [rcx+1Ch], 1
0x1800074e6  jz      short loc_180007484
0x1800074e8  mov     rcx, [rcx+10h]
0x1800074ec  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800074f3  mov     dword ptr [rsp+88h+var_58], 1A2h
0x1800074fb  lea     r9, aHr; "hr"
0x180007502  mov     [rsp+88h+var_60], rax
0x180007507  mov     dword ptr [rsp+88h+var_68], ebx
0x18000750b  call    WPP_SF_sDsd
0x180007510  jmp     loc_180007484
0x180007515  mov     rcx, [rcx+10h]
0x180007519  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007520  mov     dword ptr [rsp+88h+var_58], 186h
0x180007528  lea     r9, aHr; "hr"
0x18000752f  mov     [rsp+88h+var_60], rax
0x180007534  mov     dword ptr [rsp+88h+var_68], ebp
0x180007538  call    WPP_SF_sDsd
0x18000753d  jmp     short loc_1800074C4
0x18000753f  mov     r9d, 191h
0x180007545  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000754c  lea     rdx, aHr; "hr"
0x180007553  mov     ecx, 8009002Dh
0x180007558  mov     ebx, 8009002Dh
0x18000755d  call    DebugTraceError
0x180007562  jmp     loc_180007484
```
