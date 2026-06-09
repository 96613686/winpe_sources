# s_DecryptWithSymmetricPopKey

- ea: `0x180007570`
- end: `0x1800076a1`
- name: `s_DecryptWithSymmetricPopKey`
- size: `305`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, __int64, int, __int64, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180007570`
- `0x18000b62c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007595`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007595`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007633`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007633`

## string_xrefs

- `0x180007659`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000768c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_DecryptWithSymmetricPopKey(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        int a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  int v16; // eax
  unsigned int v17; // ebx
  int PopKeyFunctionTable; // eax
  unsigned int v20; // ebp
  __int64 v21; // r9
  __int64 v22; // rcx

  if ( g_ngcFuncLoaded
    || (PopKeyFunctionTable = LoadPopKeyFunctionTable(), v20 = PopKeyFunctionTable, PopKeyFunctionTable >= 0) )
  {
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v16 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, int, __int64, int, __int64, __int64))qword_1800259C8)(
              a3,
              a2,
              a5,
              a4,
              a7,
              a6,
              a9,
              a8,
              a11,
              a10,
              a13,
              a12);
      v17 = v16;
      if ( v16 >= 0 )
      {
LABEL_4:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return v17;
      }
      v21 = 621;
      v22 = (unsigned int)v16;
    }
    else
    {
      v17 = -2146893779;
      v21 = 602;
      v22 = 2148073517LL;
    }
    DebugTraceError(v22, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v21);
    goto LABEL_4;
  }
  DebugTraceError(
    (unsigned int)PopKeyFunctionTable,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
    591);
  return v20;
}

```

## disassembly

```asm
0x180007570  push    rbx
0x180007572  push    rbp
0x180007573  push    rsi
0x180007574  push    rdi
0x180007575  sub     rsp, 78h
0x180007579  cmp     cs:g_ngcFuncLoaded, 0
0x180007580  mov     ebx, r9d
0x180007583  mov     rdi, r8
0x180007586  mov     esi, edx
0x180007588  jz      loc_180007644
0x18000758e  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x180007595  call    cs:__imp_AcquireSRWLockShared
0x18000759b  cmp     cs:g_ngcFuncLoaded, 0
0x1800075a2  jz      loc_180007672
0x1800075a8  mov     rcx, [rsp+98h+arg_50]
0x1800075b0  mov     r9d, ebx
0x1800075b3  mov     rax, [rsp+98h+arg_58]
0x1800075bb  mov     edx, esi
0x1800075bd  mov     r8, [rsp+98h+arg_20]
0x1800075c5  mov     [rsp+98h+var_40], rax
0x1800075ca  mov     rax, [rsp+98h+arg_60]
0x1800075d2  mov     [rsp+98h+var_48], rax
0x1800075d7  mov     eax, [rsp+98h+arg_48]
0x1800075de  mov     [rsp+98h+var_50], eax
0x1800075e2  mov     rax, cs:qword_1800259C8
0x1800075e9  mov     [rsp+98h+var_58], rcx
0x1800075ee  mov     ecx, [rsp+98h+arg_38]
0x1800075f5  mov     [rsp+98h+var_60], ecx
0x1800075f9  mov     rcx, [rsp+98h+arg_40]
0x180007601  mov     [rsp+98h+var_68], rcx
0x180007606  mov     ecx, [rsp+98h+arg_28]
0x18000760d  mov     [rsp+98h+var_70], ecx
0x180007611  mov     rcx, [rsp+98h+arg_30]
0x180007619  mov     [rsp+98h+var_78], rcx
0x18000761e  mov     rcx, rdi
0x180007621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007626  mov     ebx, eax
0x180007628  test    eax, eax
0x18000762a  js      short loc_180007684
0x18000762c  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x180007633  call    cs:__imp_ReleaseSRWLockShared
0x180007639  mov     eax, ebx
0x18000763b  add     rsp, 78h
0x18000763f  pop     rdi
0x180007640  pop     rsi
0x180007641  pop     rbp
0x180007642  pop     rbx
0x180007643  retn
0x180007644  call    LoadPopKeyFunctionTable
0x180007649  mov     ebp, eax
0x18000764b  test    eax, eax
0x18000764d  jns     loc_18000758E
0x180007653  mov     r9d, 24Fh
0x180007659  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007660  lea     rdx, aHr; "hr"
0x180007667  mov     ecx, eax
0x180007669  call    DebugTraceError
0x18000766e  mov     eax, ebp
0x180007670  jmp     short loc_18000763B
0x180007672  mov     ebx, 8009002Dh
0x180007677  mov     r9d, 25Ah
0x18000767d  mov     ecx, 8009002Dh
0x180007682  jmp     short loc_18000768C
0x180007684  mov     r9d, 26Dh
0x18000768a  mov     ecx, eax
0x18000768c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007693  lea     rdx, aHr; "hr"
0x18000769a  call    DebugTraceError
0x18000769f  jmp     short loc_18000762C
```
