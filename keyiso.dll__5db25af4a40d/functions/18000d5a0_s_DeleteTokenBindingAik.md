# s_DeleteTokenBindingAik

- ea: `0x18000d5a0`
- end: `0x18000d65f`
- name: `s_DeleteTokenBindingAik`
- size: `191`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000b62c`
- `0x18000d5a0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d5e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d5e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d64e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d64e`

## string_xrefs

- `0x18000d5cb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000d634`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_DeleteTokenBindingAik(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5)
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
      v12 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64))qword_180025A08)(a2, a3, a4, a5);
      v9 = v12;
      if ( v12 >= 0 )
      {
LABEL_9:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return v9;
      }
      v10 = 1156;
      v11 = (unsigned int)v12;
    }
    else
    {
      v9 = -2146893779;
      v10 = 1144;
      v11 = 2148073517LL;
    }
    DebugTraceError(v11, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v10);
    goto LABEL_9;
  }
  DebugTraceError(
    (unsigned int)PopKeyFunctionTable,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
    1133);
  return v9;
}

```

## disassembly

```asm
0x18000d5a0  push    rbx
0x18000d5a2  push    rbp
0x18000d5a3  push    rsi
0x18000d5a4  push    rdi
0x18000d5a5  sub     rsp, 38h
0x18000d5a9  cmp     cs:g_ngcFuncLoaded, 0
0x18000d5b0  mov     rdi, r9
0x18000d5b3  mov     rsi, r8
0x18000d5b6  mov     ebp, edx
0x18000d5b8  jnz     short loc_18000D5E2
0x18000d5ba  call    LoadPopKeyFunctionTable
0x18000d5bf  mov     ebx, eax
0x18000d5c1  test    eax, eax
0x18000d5c3  jns     short loc_18000D5E2
0x18000d5c5  mov     r9d, 46Dh
0x18000d5cb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d5d2  lea     rdx, aHr; "hr"
0x18000d5d9  mov     ecx, eax
0x18000d5db  call    DebugTraceError
0x18000d5e0  jmp     short loc_18000D654
0x18000d5e2  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d5e9  call    cs:__imp_AcquireSRWLockShared
0x18000d5ef  cmp     cs:g_ngcFuncLoaded, 0
0x18000d5f6  jnz     short loc_18000D60A
0x18000d5f8  mov     ebx, 8009002Dh
0x18000d5fd  mov     r9d, 478h
0x18000d603  mov     ecx, 8009002Dh
0x18000d608  jmp     short loc_18000D634
0x18000d60a  mov     r9, [rsp+58h+arg_20]
0x18000d612  mov     r8, rdi
0x18000d615  mov     rax, cs:qword_180025A08
0x18000d61c  mov     rdx, rsi
0x18000d61f  mov     ecx, ebp
0x18000d621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d626  mov     ebx, eax
0x18000d628  test    eax, eax
0x18000d62a  jns     short loc_18000D647
0x18000d62c  mov     r9d, 484h
0x18000d632  mov     ecx, eax
0x18000d634  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d63b  lea     rdx, aHr; "hr"
0x18000d642  call    DebugTraceError
0x18000d647  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d64e  call    cs:__imp_ReleaseSRWLockShared
0x18000d654  mov     eax, ebx
0x18000d656  add     rsp, 38h
0x18000d65a  pop     rdi
0x18000d65b  pop     rsi
0x18000d65c  pop     rbp
0x18000d65d  pop     rbx
0x18000d65e  retn
```
