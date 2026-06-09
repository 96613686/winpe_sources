# s_GetKeyAttestationForContainerService

- ea: `0x180008090`
- end: `0x1800081e6`
- name: `s_GetKeyAttestationForContainerService`
- size: `342`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x180008090`
- `0x1800081ec`
- `0x18000b62c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000813f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000813f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800081d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800081d8`

## string_xrefs

- `0x1800080b4`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000810f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x1800081be`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_GetKeyAttestationForContainerService(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  unsigned int PopKeyFunctionTable; // ebx
  int v11; // edx
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // eax
  _QWORD v16[5]; // [rsp+40h] [rbp-28h] BYREF

  v16[0] = a2;
  v16[1] = a3;
  v16[2] = a4;
  if ( !(unsigned int)IsCallerLocalServiceOrLocalSystem(a1) )
  {
    PopKeyFunctionTable = -2146893808;
    DebugTraceError(
      2148073488LL,
      "hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      657);
    return PopKeyFunctionTable;
  }
  if ( g_ngcFuncLoaded || (PopKeyFunctionTable = LoadPopKeyFunctionTable(), (PopKeyFunctionTable & 0x80000000) == 0) )
  {
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v14 = ((__int64 (__fastcall *)(_QWORD *, __int64, __int64, __int64, __int64, __int64, __int64))qword_1800259D0)(
              v16,
              a5,
              a7,
              a6,
              a9,
              a8,
              a10);
      PopKeyFunctionTable = v14;
      if ( v14 >= 0 )
      {
LABEL_13:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return PopKeyFunctionTable;
      }
      v12 = 691;
      v13 = (unsigned int)v14;
    }
    else
    {
      PopKeyFunctionTable = -2146893779;
      v12 = 677;
      v13 = 2148073517LL;
    }
    DebugTraceError(v13, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v12);
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      (unsigned int)"hr",
      PopKeyFunctionTable,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      154);
  return PopKeyFunctionTable;
}

```

## disassembly

```asm
0x180008090  push    rbx
0x180008092  sub     rsp, 60h
0x180008096  mov     [rsp+68h+var_28], rdx
0x18000809b  mov     [rsp+68h+var_20], r8
0x1800080a0  mov     [rsp+68h+var_18], r9
0x1800080a5  call    IsCallerLocalServiceOrLocalSystem
0x1800080aa  test    eax, eax
0x1800080ac  jnz     short loc_1800080D6
0x1800080ae  mov     r9d, 291h
0x1800080b4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800080bb  lea     rdx, aHr; "hr"
0x1800080c2  mov     ecx, 80090010h
0x1800080c7  mov     ebx, 80090010h
0x1800080cc  call    DebugTraceError
0x1800080d1  jmp     loc_1800081DE
0x1800080d6  cmp     cs:g_ngcFuncLoaded, 0
0x1800080dd  jnz     short loc_180008138
0x1800080df  call    LoadPopKeyFunctionTable
0x1800080e4  mov     ebx, eax
0x1800080e6  test    eax, eax
0x1800080e8  jns     short loc_180008138
0x1800080ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080f1  lea     rax, WPP_GLOBAL_Control
0x1800080f8  cmp     rcx, rax
0x1800080fb  jz      loc_1800081DE
0x180008101  test    byte ptr [rcx+1Ch], 1
0x180008105  jz      loc_1800081DE
0x18000810b  mov     rcx, [rcx+10h]
0x18000810f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008116  mov     dword ptr [rsp+68h+var_38], 29Ah
0x18000811e  lea     r9, aHr; "hr"
0x180008125  mov     [rsp+68h+var_40], r8
0x18000812a  mov     dword ptr [rsp+68h+var_48], ebx
0x18000812e  call    WPP_SF_sDsd
0x180008133  jmp     loc_1800081DE
0x180008138  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000813f  call    cs:__imp_AcquireSRWLockShared
0x180008145  cmp     cs:g_ngcFuncLoaded, 0
0x18000814c  jnz     short loc_180008160
0x18000814e  mov     ebx, 8009002Dh
0x180008153  mov     r9d, 2A5h
0x180008159  mov     ecx, 8009002Dh
0x18000815e  jmp     short loc_1800081BE
0x180008160  mov     rcx, [rsp+68h+arg_48]
0x180008168  mov     r9, [rsp+68h+arg_28]
0x180008170  mov     r8, [rsp+68h+arg_30]
0x180008178  mov     rdx, [rsp+68h+arg_20]
0x180008180  mov     rax, cs:qword_1800259D0
0x180008187  mov     [rsp+68h+var_38], rcx
0x18000818c  mov     rcx, [rsp+68h+arg_38]
0x180008194  mov     [rsp+68h+var_40], rcx
0x180008199  mov     rcx, [rsp+68h+arg_40]
0x1800081a1  mov     [rsp+68h+var_48], rcx
0x1800081a6  lea     rcx, [rsp+68h+var_28]
0x1800081ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081b0  mov     ebx, eax
0x1800081b2  test    eax, eax
0x1800081b4  jns     short loc_1800081D1
0x1800081b6  mov     r9d, 2B3h
0x1800081bc  mov     ecx, eax
0x1800081be  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800081c5  lea     rdx, aHr; "hr"
0x1800081cc  call    DebugTraceError
0x1800081d1  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x1800081d8  call    cs:__imp_ReleaseSRWLockShared
0x1800081de  mov     eax, ebx
0x1800081e0  add     rsp, 60h
0x1800081e4  pop     rbx
0x1800081e5  retn
```
