# s_GetPregenKeyState

- ea: `0x18000d910`
- end: `0x18000d9ce`
- name: `s_GetPregenKeyState`
- size: `190`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000b62c`
- `0x18000d910`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d959`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d959`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d9bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d9bd`

## string_xrefs

- `0x18000d93b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000d9a3`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_GetPregenKeyState(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4, __int64 a5)
{
  int PopKeyFunctionTable; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // eax

  if ( g_ngcFuncLoaded
    || (PopKeyFunctionTable = LoadPopKeyFunctionTable(), v9 = PopKeyFunctionTable, PopKeyFunctionTable >= 0) )
  {
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64))qword_1800259E8)(a2, a3, a4, a5);
      v9 = v12;
      if ( v12 >= 0 )
      {
LABEL_9:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return v9;
      }
      v10 = 888;
      v11 = (unsigned int)v12;
    }
    else
    {
      v9 = -2146893779;
      v10 = 877;
      v11 = 2148073517LL;
    }
    DebugTraceError(v11, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v10);
    goto LABEL_9;
  }
  DebugTraceError(
    (unsigned int)PopKeyFunctionTable,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
    866);
  return v9;
}

```

## disassembly

```asm
0x18000d910  push    rbx
0x18000d912  push    rbp
0x18000d913  push    rsi
0x18000d914  push    rdi
0x18000d915  sub     rsp, 38h
0x18000d919  cmp     cs:g_ngcFuncLoaded, 0
0x18000d920  mov     rdi, r9
0x18000d923  mov     esi, r8d
0x18000d926  mov     ebp, edx
0x18000d928  jnz     short loc_18000D952
0x18000d92a  call    LoadPopKeyFunctionTable
0x18000d92f  mov     ebx, eax
0x18000d931  test    eax, eax
0x18000d933  jns     short loc_18000D952
0x18000d935  mov     r9d, 362h
0x18000d93b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d942  lea     rdx, aHr; "hr"
0x18000d949  mov     ecx, eax
0x18000d94b  call    DebugTraceError
0x18000d950  jmp     short loc_18000D9C3
0x18000d952  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d959  call    cs:__imp_AcquireSRWLockShared
0x18000d95f  cmp     cs:g_ngcFuncLoaded, 0
0x18000d966  jnz     short loc_18000D97A
0x18000d968  mov     ebx, 8009002Dh
0x18000d96d  mov     r9d, 36Dh
0x18000d973  mov     ecx, 8009002Dh
0x18000d978  jmp     short loc_18000D9A3
0x18000d97a  mov     r9, [rsp+58h+arg_20]
0x18000d982  mov     r8, rdi
0x18000d985  mov     rax, cs:qword_1800259E8
0x18000d98c  mov     edx, esi
0x18000d98e  mov     ecx, ebp
0x18000d990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d995  mov     ebx, eax
0x18000d997  test    eax, eax
0x18000d999  jns     short loc_18000D9B6
0x18000d99b  mov     r9d, 378h
0x18000d9a1  mov     ecx, eax
0x18000d9a3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d9aa  lea     rdx, aHr; "hr"
0x18000d9b1  call    DebugTraceError
0x18000d9b6  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d9bd  call    cs:__imp_ReleaseSRWLockShared
0x18000d9c3  mov     eax, ebx
0x18000d9c5  add     rsp, 38h
0x18000d9c9  pop     rdi
0x18000d9ca  pop     rsi
0x18000d9cb  pop     rbp
0x18000d9cc  pop     rbx
0x18000d9cd  retn
```
