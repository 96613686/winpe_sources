# s_CreateTokenBindingAik

- ea: `0x18000d1e0`
- end: `0x18000d2bc`
- name: `s_CreateTokenBindingAik`
- size: `220`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000b62c`
- `0x18000d1e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d22c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d22c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d2ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d2ab`

## string_xrefs

- `0x18000d20b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000d291`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_CreateTokenBindingAik(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int PopKeyFunctionTable; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // eax

  if ( g_ngcFuncLoaded
    || (PopKeyFunctionTable = LoadPopKeyFunctionTable(), v11 = PopKeyFunctionTable, PopKeyFunctionTable >= 0) )
  {
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v14 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int64, __int64))qword_180025A00)(
              a2,
              a3,
              a4,
              a5,
              a7,
              a6);
      v11 = v14;
      if ( v14 >= 0 )
      {
LABEL_9:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return v11;
      }
      v12 = 1102;
      v13 = (unsigned int)v14;
    }
    else
    {
      v11 = -2146893779;
      v12 = 1088;
      v13 = 2148073517LL;
    }
    DebugTraceError(v13, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v12);
    goto LABEL_9;
  }
  DebugTraceError(
    (unsigned int)PopKeyFunctionTable,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
    1077);
  return v11;
}

```

## disassembly

```asm
0x18000d1e0  push    rbx
0x18000d1e2  push    rbp
0x18000d1e3  push    rsi
0x18000d1e4  push    rdi
0x18000d1e5  sub     rsp, 48h
0x18000d1e9  cmp     cs:g_ngcFuncLoaded, 0
0x18000d1f0  mov     rdi, r9
0x18000d1f3  mov     rsi, r8
0x18000d1f6  mov     ebp, edx
0x18000d1f8  jnz     short loc_18000D225
0x18000d1fa  call    LoadPopKeyFunctionTable
0x18000d1ff  mov     ebx, eax
0x18000d201  test    eax, eax
0x18000d203  jns     short loc_18000D225
0x18000d205  mov     r9d, 435h
0x18000d20b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d212  lea     rdx, aHr; "hr"
0x18000d219  mov     ecx, eax
0x18000d21b  call    DebugTraceError
0x18000d220  jmp     loc_18000D2B1
0x18000d225  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d22c  call    cs:__imp_AcquireSRWLockShared
0x18000d232  cmp     cs:g_ngcFuncLoaded, 0
0x18000d239  jnz     short loc_18000D24D
0x18000d23b  mov     ebx, 8009002Dh
0x18000d240  mov     r9d, 440h
0x18000d246  mov     ecx, 8009002Dh
0x18000d24b  jmp     short loc_18000D291
0x18000d24d  mov     rcx, [rsp+68h+arg_28]
0x18000d255  mov     r8, rdi
0x18000d258  mov     r9, [rsp+68h+arg_20]
0x18000d260  mov     rdx, rsi
0x18000d263  mov     rax, cs:qword_180025A00
0x18000d26a  mov     [rsp+68h+var_40], rcx
0x18000d26f  mov     rcx, [rsp+68h+arg_30]
0x18000d277  mov     [rsp+68h+var_48], rcx
0x18000d27c  mov     ecx, ebp
0x18000d27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d283  mov     ebx, eax
0x18000d285  test    eax, eax
0x18000d287  jns     short loc_18000D2A4
0x18000d289  mov     r9d, 44Eh
0x18000d28f  mov     ecx, eax
0x18000d291  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d298  lea     rdx, aHr; "hr"
0x18000d29f  call    DebugTraceError
0x18000d2a4  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d2ab  call    cs:__imp_ReleaseSRWLockShared
0x18000d2b1  mov     eax, ebx
0x18000d2b3  add     rsp, 48h
0x18000d2b7  pop     rdi
0x18000d2b8  pop     rsi
0x18000d2b9  pop     rbp
0x18000d2ba  pop     rbx
0x18000d2bb  retn
```
