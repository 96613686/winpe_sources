# s_DecryptWithSymmetricGcmPopKey

- ea: `0x18000d2d0`
- end: `0x18000d42d`
- name: `s_DecryptWithSymmetricGcmPopKey`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000b62c`
- `0x18000d2d0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d31f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d31f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d419`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d419`

## string_xrefs

- `0x18000d2fe`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000d3ff`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_DecryptWithSymmetricGcmPopKey(
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
        int a12,
        __int64 a13,
        int a14,
        __int64 a15,
        __int64 a16,
        __int64 a17)
{
  int PopKeyFunctionTable; // eax
  unsigned int v21; // ebx
  __int64 v22; // r9
  __int64 v23; // rcx
  int v24; // eax

  if ( g_ngcFuncLoaded
    || (PopKeyFunctionTable = LoadPopKeyFunctionTable(), v21 = PopKeyFunctionTable, PopKeyFunctionTable >= 0) )
  {
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v24 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, int, __int64, int, __int64, int, __int64, int, __int64, __int64))qword_1800259F8)(
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
              a12,
              a15,
              a14,
              a17,
              a16);
      v21 = v24;
      if ( v24 >= 0 )
      {
LABEL_9:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return v21;
      }
      v22 = 1044;
      v23 = (unsigned int)v24;
    }
    else
    {
      v21 = -2146893779;
      v22 = 1021;
      v23 = 2148073517LL;
    }
    DebugTraceError(v23, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v22);
    goto LABEL_9;
  }
  DebugTraceError(
    (unsigned int)PopKeyFunctionTable,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
    1010);
  return v21;
}

```

## disassembly

```asm
0x18000d2d0  push    rbx
0x18000d2d2  push    rbp
0x18000d2d3  push    rsi
0x18000d2d4  push    rdi
0x18000d2d5  sub     rsp, 98h
0x18000d2dc  cmp     cs:g_ngcFuncLoaded, 0
0x18000d2e3  mov     edi, r9d
0x18000d2e6  mov     rsi, r8
0x18000d2e9  mov     ebp, edx
0x18000d2eb  jnz     short loc_18000D318
0x18000d2ed  call    LoadPopKeyFunctionTable
0x18000d2f2  mov     ebx, eax
0x18000d2f4  test    eax, eax
0x18000d2f6  jns     short loc_18000D318
0x18000d2f8  mov     r9d, 3F2h
0x18000d2fe  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d305  lea     rdx, aHr; "hr"
0x18000d30c  mov     ecx, eax
0x18000d30e  call    DebugTraceError
0x18000d313  jmp     loc_18000D41F
0x18000d318  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d31f  call    cs:__imp_AcquireSRWLockShared
0x18000d325  cmp     cs:g_ngcFuncLoaded, 0
0x18000d32c  jnz     short loc_18000D343
0x18000d32e  mov     ebx, 8009002Dh
0x18000d333  mov     r9d, 3FDh
0x18000d339  mov     ecx, 8009002Dh
0x18000d33e  jmp     loc_18000D3FF
0x18000d343  mov     rcx, [rsp+0B8h+arg_50]
0x18000d34b  mov     r9d, edi
0x18000d34e  mov     rax, [rsp+0B8h+arg_78]
0x18000d356  mov     edx, ebp
0x18000d358  mov     r8, [rsp+0B8h+arg_20]
0x18000d360  mov     [rsp+0B8h+var_40], rax
0x18000d365  mov     rax, [rsp+0B8h+arg_80]
0x18000d36d  mov     [rsp+0B8h+var_48], rax
0x18000d372  mov     eax, [rsp+0B8h+arg_68]
0x18000d379  mov     [rsp+0B8h+var_50], eax
0x18000d37d  mov     rax, [rsp+0B8h+arg_70]
0x18000d385  mov     [rsp+0B8h+var_58], rax
0x18000d38a  mov     eax, [rsp+0B8h+arg_58]
0x18000d391  mov     [rsp+0B8h+var_60], eax
0x18000d395  mov     rax, [rsp+0B8h+arg_60]
0x18000d39d  mov     [rsp+0B8h+var_68], rax
0x18000d3a2  mov     eax, [rsp+0B8h+arg_48]
0x18000d3a9  mov     [rsp+0B8h+var_70], eax
0x18000d3ad  mov     rax, cs:qword_1800259F8
0x18000d3b4  mov     [rsp+0B8h+var_78], rcx
0x18000d3b9  mov     ecx, [rsp+0B8h+arg_38]
0x18000d3c0  mov     [rsp+0B8h+var_80], ecx
0x18000d3c4  mov     rcx, [rsp+0B8h+arg_40]
0x18000d3cc  mov     [rsp+0B8h+var_88], rcx
0x18000d3d1  mov     ecx, [rsp+0B8h+arg_28]
0x18000d3d8  mov     [rsp+0B8h+var_90], ecx
0x18000d3dc  mov     rcx, [rsp+0B8h+arg_30]
0x18000d3e4  mov     [rsp+0B8h+var_98], rcx
0x18000d3e9  mov     rcx, rsi
0x18000d3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3f1  mov     ebx, eax
0x18000d3f3  test    eax, eax
0x18000d3f5  jns     short loc_18000D412
0x18000d3f7  mov     r9d, 414h
0x18000d3fd  mov     ecx, eax
0x18000d3ff  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d406  lea     rdx, aHr; "hr"
0x18000d40d  call    DebugTraceError
0x18000d412  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d419  call    cs:__imp_ReleaseSRWLockShared
0x18000d41f  mov     eax, ebx
0x18000d421  add     rsp, 98h
0x18000d428  pop     rdi
0x18000d429  pop     rsi
0x18000d42a  pop     rbp
0x18000d42b  pop     rbx
0x18000d42c  retn
```
