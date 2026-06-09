# s_GetTokenBindingAikName

- ea: `0x18000dc60`
- end: `0x18000dd2c`
- name: `s_GetTokenBindingAikName`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000b62c`
- `0x18000dc60`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dca9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dca9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dd1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dd1b`

## string_xrefs

- `0x18000dc8b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000dd01`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_GetTokenBindingAikName(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int PopKeyFunctionTable; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // eax

  if ( g_ngcFuncLoaded
    || (PopKeyFunctionTable = LoadPopKeyFunctionTable(), v10 = PopKeyFunctionTable, PopKeyFunctionTable >= 0) )
  {
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v13 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64, __int64))qword_180025A10)(a2, a3, a4, a5, a6);
      v10 = v13;
      if ( v13 >= 0 )
      {
LABEL_9:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return v10;
      }
      v11 = 1212;
      v12 = (unsigned int)v13;
    }
    else
    {
      v10 = -2146893779;
      v11 = 1199;
      v12 = 2148073517LL;
    }
    DebugTraceError(v12, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v11);
    goto LABEL_9;
  }
  DebugTraceError(
    (unsigned int)PopKeyFunctionTable,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
    1188);
  return v10;
}

```

## disassembly

```asm
0x18000dc60  push    rbx
0x18000dc62  push    rbp
0x18000dc63  push    rsi
0x18000dc64  push    rdi
0x18000dc65  sub     rsp, 38h
0x18000dc69  cmp     cs:g_ngcFuncLoaded, 0
0x18000dc70  mov     rdi, r9
0x18000dc73  mov     rsi, r8
0x18000dc76  mov     ebp, edx
0x18000dc78  jnz     short loc_18000DCA2
0x18000dc7a  call    LoadPopKeyFunctionTable
0x18000dc7f  mov     ebx, eax
0x18000dc81  test    eax, eax
0x18000dc83  jns     short loc_18000DCA2
0x18000dc85  mov     r9d, 4A4h
0x18000dc8b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dc92  lea     rdx, aHr; "hr"
0x18000dc99  mov     ecx, eax
0x18000dc9b  call    DebugTraceError
0x18000dca0  jmp     short loc_18000DD21
0x18000dca2  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000dca9  call    cs:__imp_AcquireSRWLockShared
0x18000dcaf  cmp     cs:g_ngcFuncLoaded, 0
0x18000dcb6  jnz     short loc_18000DCCA
0x18000dcb8  mov     ebx, 8009002Dh
0x18000dcbd  mov     r9d, 4AFh
0x18000dcc3  mov     ecx, 8009002Dh
0x18000dcc8  jmp     short loc_18000DD01
0x18000dcca  mov     rcx, [rsp+58h+arg_28]
0x18000dcd2  mov     r8, rdi
0x18000dcd5  mov     r9, [rsp+58h+arg_20]
0x18000dcdd  mov     rdx, rsi
0x18000dce0  mov     rax, cs:qword_180025A10
0x18000dce7  mov     [rsp+58h+var_38], rcx
0x18000dcec  mov     ecx, ebp
0x18000dcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcf3  mov     ebx, eax
0x18000dcf5  test    eax, eax
0x18000dcf7  jns     short loc_18000DD14
0x18000dcf9  mov     r9d, 4BCh
0x18000dcff  mov     ecx, eax
0x18000dd01  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dd08  lea     rdx, aHr; "hr"
0x18000dd0f  call    DebugTraceError
0x18000dd14  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000dd1b  call    cs:__imp_ReleaseSRWLockShared
0x18000dd21  mov     eax, ebx
0x18000dd23  add     rsp, 38h
0x18000dd27  pop     rdi
0x18000dd28  pop     rsi
0x18000dd29  pop     rbp
0x18000dd2a  pop     rbx
0x18000dd2b  retn
```
