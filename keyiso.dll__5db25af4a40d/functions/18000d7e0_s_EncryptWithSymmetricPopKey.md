# s_EncryptWithSymmetricPopKey

- ea: `0x18000d7e0`
- end: `0x18000d907`
- name: `s_EncryptWithSymmetricPopKey`
- size: `295`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, __int64, int, __int64, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000b62c`
- `0x18000d7e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d82c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d82c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d8f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d8f6`

## string_xrefs

- `0x18000d80b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000d8dc`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_EncryptWithSymmetricPopKey(
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
  int PopKeyFunctionTable; // eax
  unsigned int v17; // ebx
  __int64 v18; // r9
  __int64 v19; // rcx
  int v20; // eax

  if ( g_ngcFuncLoaded
    || (PopKeyFunctionTable = LoadPopKeyFunctionTable(), v17 = PopKeyFunctionTable, PopKeyFunctionTable >= 0) )
  {
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v20 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, int, __int64, int, __int64, __int64))qword_1800259C0)(
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
      v17 = v20;
      if ( v20 >= 0 )
      {
LABEL_9:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return v17;
      }
      v18 = 552;
      v19 = (unsigned int)v20;
    }
    else
    {
      v17 = -2146893779;
      v18 = 533;
      v19 = 2148073517LL;
    }
    DebugTraceError(v19, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v18);
    goto LABEL_9;
  }
  DebugTraceError(
    (unsigned int)PopKeyFunctionTable,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
    522);
  return v17;
}

```

## disassembly

```asm
0x18000d7e0  push    rbx
0x18000d7e2  push    rbp
0x18000d7e3  push    rsi
0x18000d7e4  push    rdi
0x18000d7e5  sub     rsp, 78h
0x18000d7e9  cmp     cs:g_ngcFuncLoaded, 0
0x18000d7f0  mov     edi, r9d
0x18000d7f3  mov     rsi, r8
0x18000d7f6  mov     ebp, edx
0x18000d7f8  jnz     short loc_18000D825
0x18000d7fa  call    LoadPopKeyFunctionTable
0x18000d7ff  mov     ebx, eax
0x18000d801  test    eax, eax
0x18000d803  jns     short loc_18000D825
0x18000d805  mov     r9d, 20Ah
0x18000d80b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d812  lea     rdx, aHr; "hr"
0x18000d819  mov     ecx, eax
0x18000d81b  call    DebugTraceError
0x18000d820  jmp     loc_18000D8FC
0x18000d825  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d82c  call    cs:__imp_AcquireSRWLockShared
0x18000d832  cmp     cs:g_ngcFuncLoaded, 0
0x18000d839  jnz     short loc_18000D850
0x18000d83b  mov     ebx, 8009002Dh
0x18000d840  mov     r9d, 215h
0x18000d846  mov     ecx, 8009002Dh
0x18000d84b  jmp     loc_18000D8DC
0x18000d850  mov     rcx, [rsp+98h+arg_50]
0x18000d858  mov     r9d, edi
0x18000d85b  mov     rax, [rsp+98h+arg_58]
0x18000d863  mov     edx, ebp
0x18000d865  mov     r8, [rsp+98h+arg_20]
0x18000d86d  mov     [rsp+98h+var_40], rax
0x18000d872  mov     rax, [rsp+98h+arg_60]
0x18000d87a  mov     [rsp+98h+var_48], rax
0x18000d87f  mov     eax, [rsp+98h+arg_48]
0x18000d886  mov     [rsp+98h+var_50], eax
0x18000d88a  mov     rax, cs:qword_1800259C0
0x18000d891  mov     [rsp+98h+var_58], rcx
0x18000d896  mov     ecx, [rsp+98h+arg_38]
0x18000d89d  mov     [rsp+98h+var_60], ecx
0x18000d8a1  mov     rcx, [rsp+98h+arg_40]
0x18000d8a9  mov     [rsp+98h+var_68], rcx
0x18000d8ae  mov     ecx, [rsp+98h+arg_28]
0x18000d8b5  mov     [rsp+98h+var_70], ecx
0x18000d8b9  mov     rcx, [rsp+98h+arg_30]
0x18000d8c1  mov     [rsp+98h+var_78], rcx
0x18000d8c6  mov     rcx, rsi
0x18000d8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ce  mov     ebx, eax
0x18000d8d0  test    eax, eax
0x18000d8d2  jns     short loc_18000D8EF
0x18000d8d4  mov     r9d, 228h
0x18000d8da  mov     ecx, eax
0x18000d8dc  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d8e3  lea     rdx, aHr; "hr"
0x18000d8ea  call    DebugTraceError
0x18000d8ef  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d8f6  call    cs:__imp_ReleaseSRWLockShared
0x18000d8fc  mov     eax, ebx
0x18000d8fe  add     rsp, 78h
0x18000d902  pop     rdi
0x18000d903  pop     rsi
0x18000d904  pop     rbp
0x18000d905  pop     rbx
0x18000d906  retn
```
