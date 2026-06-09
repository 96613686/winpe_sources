# s_VerifyWithSymmetricPopKey

- ea: `0x180007cb0`
- end: `0x180007dc5`
- name: `s_VerifyWithSymmetricPopKey`
- size: `277`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, __int64, int, __int64, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180007cb0`
- `0x18000b62c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007cd5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007cd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007d59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007d59`

## string_xrefs

- `0x180007d7f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x180007db0`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_VerifyWithSymmetricPopKey(
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
        __int64 a11)
{
  int v14; // eax
  unsigned int v15; // ebx
  int PopKeyFunctionTable; // eax
  __int64 v18; // r9
  __int64 v19; // rcx

  if ( !g_ngcFuncLoaded )
  {
    PopKeyFunctionTable = LoadPopKeyFunctionTable();
    v15 = PopKeyFunctionTable;
    if ( PopKeyFunctionTable < 0 )
    {
      DebugTraceError(
        (unsigned int)PopKeyFunctionTable,
        "hr",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
        455);
      return v15;
    }
  }
  AcquireSRWLockShared(&g_ngcFuncLoadLock);
  if ( !g_ngcFuncLoaded )
  {
    v15 = -2146893779;
    v18 = 466;
    v19 = 2148073517LL;
LABEL_10:
    DebugTraceError(v19, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v18);
    goto LABEL_4;
  }
  v14 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, int, __int64, int))qword_1800259B8)(
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
  v15 = v14;
  if ( v14 < 0 )
  {
    v18 = 483;
    v19 = (unsigned int)v14;
    goto LABEL_10;
  }
LABEL_4:
  ReleaseSRWLockShared(&g_ngcFuncLoadLock);
  return v15;
}

```

## disassembly

```asm
0x180007cb0  push    rbx
0x180007cb2  push    rbp
0x180007cb3  push    rsi
0x180007cb4  push    rdi
0x180007cb5  sub     rsp, 68h
0x180007cb9  cmp     cs:g_ngcFuncLoaded, 0
0x180007cc0  mov     edi, r9d
0x180007cc3  mov     rsi, r8
0x180007cc6  mov     ebp, edx
0x180007cc8  jz      loc_180007D6A
0x180007cce  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x180007cd5  call    cs:__imp_AcquireSRWLockShared
0x180007cdb  cmp     cs:g_ngcFuncLoaded, 0
0x180007ce2  jz      loc_180007D96
0x180007ce8  mov     rcx, [rsp+88h+arg_50]
0x180007cf0  mov     r9d, edi
0x180007cf3  mov     eax, [rsp+88h+arg_48]
0x180007cfa  mov     edx, ebp
0x180007cfc  mov     r8, [rsp+88h+arg_20]
0x180007d04  mov     [rsp+88h+var_40], eax
0x180007d08  mov     rax, cs:qword_1800259B8
0x180007d0f  mov     [rsp+88h+var_48], rcx
0x180007d14  mov     ecx, [rsp+88h+arg_38]
0x180007d1b  mov     [rsp+88h+var_50], ecx
0x180007d1f  mov     rcx, [rsp+88h+arg_40]
0x180007d27  mov     [rsp+88h+var_58], rcx
0x180007d2c  mov     ecx, [rsp+88h+arg_28]
0x180007d33  mov     [rsp+88h+var_60], ecx
0x180007d37  mov     rcx, [rsp+88h+arg_30]
0x180007d3f  mov     [rsp+88h+var_68], rcx
0x180007d44  mov     rcx, rsi
0x180007d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d4c  mov     ebx, eax
0x180007d4e  test    eax, eax
0x180007d50  js      short loc_180007DA8
0x180007d52  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x180007d59  call    cs:__imp_ReleaseSRWLockShared
0x180007d5f  mov     eax, ebx
0x180007d61  add     rsp, 68h
0x180007d65  pop     rdi
0x180007d66  pop     rsi
0x180007d67  pop     rbp
0x180007d68  pop     rbx
0x180007d69  retn
0x180007d6a  call    LoadPopKeyFunctionTable
0x180007d6f  mov     ebx, eax
0x180007d71  test    eax, eax
0x180007d73  jns     loc_180007CCE
0x180007d79  mov     r9d, 1C7h
0x180007d7f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007d86  lea     rdx, aHr; "hr"
0x180007d8d  mov     ecx, eax
0x180007d8f  call    DebugTraceError
0x180007d94  jmp     short loc_180007D5F
0x180007d96  mov     ebx, 8009002Dh
0x180007d9b  mov     r9d, 1D2h
0x180007da1  mov     ecx, 8009002Dh
0x180007da6  jmp     short loc_180007DB0
0x180007da8  mov     r9d, 1E3h
0x180007dae  mov     ecx, eax
0x180007db0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007db7  lea     rdx, aHr; "hr"
0x180007dbe  call    DebugTraceError
0x180007dc3  jmp     short loc_180007D52
```
