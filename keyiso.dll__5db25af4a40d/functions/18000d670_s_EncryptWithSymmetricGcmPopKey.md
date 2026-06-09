# s_EncryptWithSymmetricGcmPopKey

- ea: `0x18000d670`
- end: `0x18000d7cd`
- name: `s_EncryptWithSymmetricGcmPopKey`
- size: `349`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int, __int64, int, __int64, int, __int64, int, __int64, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000b62c`
- `0x18000d670`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d6bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d6bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d7b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d7b9`

## string_xrefs

- `0x18000d69e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000d79f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_EncryptWithSymmetricGcmPopKey(
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
      v24 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, int, __int64, int, __int64, int, __int64, int, __int64, __int64))qword_1800259F0)(
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
      v22 = 967;
      v23 = (unsigned int)v24;
    }
    else
    {
      v21 = -2146893779;
      v22 = 944;
      v23 = 2148073517LL;
    }
    DebugTraceError(v23, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v22);
    goto LABEL_9;
  }
  DebugTraceError(
    (unsigned int)PopKeyFunctionTable,
    "hr",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
    933);
  return v21;
}

```

## disassembly

```asm
0x18000d670  push    rbx
0x18000d672  push    rbp
0x18000d673  push    rsi
0x18000d674  push    rdi
0x18000d675  sub     rsp, 98h
0x18000d67c  cmp     cs:g_ngcFuncLoaded, 0
0x18000d683  mov     edi, r9d
0x18000d686  mov     rsi, r8
0x18000d689  mov     ebp, edx
0x18000d68b  jnz     short loc_18000D6B8
0x18000d68d  call    LoadPopKeyFunctionTable
0x18000d692  mov     ebx, eax
0x18000d694  test    eax, eax
0x18000d696  jns     short loc_18000D6B8
0x18000d698  mov     r9d, 3A5h
0x18000d69e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d6a5  lea     rdx, aHr; "hr"
0x18000d6ac  mov     ecx, eax
0x18000d6ae  call    DebugTraceError
0x18000d6b3  jmp     loc_18000D7BF
0x18000d6b8  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d6bf  call    cs:__imp_AcquireSRWLockShared
0x18000d6c5  cmp     cs:g_ngcFuncLoaded, 0
0x18000d6cc  jnz     short loc_18000D6E3
0x18000d6ce  mov     ebx, 8009002Dh
0x18000d6d3  mov     r9d, 3B0h
0x18000d6d9  mov     ecx, 8009002Dh
0x18000d6de  jmp     loc_18000D79F
0x18000d6e3  mov     rcx, [rsp+0B8h+arg_50]
0x18000d6eb  mov     r9d, edi
0x18000d6ee  mov     rax, [rsp+0B8h+arg_78]
0x18000d6f6  mov     edx, ebp
0x18000d6f8  mov     r8, [rsp+0B8h+arg_20]
0x18000d700  mov     [rsp+0B8h+var_40], rax
0x18000d705  mov     rax, [rsp+0B8h+arg_80]
0x18000d70d  mov     [rsp+0B8h+var_48], rax
0x18000d712  mov     eax, [rsp+0B8h+arg_68]
0x18000d719  mov     [rsp+0B8h+var_50], eax
0x18000d71d  mov     rax, [rsp+0B8h+arg_70]
0x18000d725  mov     [rsp+0B8h+var_58], rax
0x18000d72a  mov     eax, [rsp+0B8h+arg_58]
0x18000d731  mov     [rsp+0B8h+var_60], eax
0x18000d735  mov     rax, [rsp+0B8h+arg_60]
0x18000d73d  mov     [rsp+0B8h+var_68], rax
0x18000d742  mov     eax, [rsp+0B8h+arg_48]
0x18000d749  mov     [rsp+0B8h+var_70], eax
0x18000d74d  mov     rax, cs:qword_1800259F0
0x18000d754  mov     [rsp+0B8h+var_78], rcx
0x18000d759  mov     ecx, [rsp+0B8h+arg_38]
0x18000d760  mov     [rsp+0B8h+var_80], ecx
0x18000d764  mov     rcx, [rsp+0B8h+arg_40]
0x18000d76c  mov     [rsp+0B8h+var_88], rcx
0x18000d771  mov     ecx, [rsp+0B8h+arg_28]
0x18000d778  mov     [rsp+0B8h+var_90], ecx
0x18000d77c  mov     rcx, [rsp+0B8h+arg_30]
0x18000d784  mov     [rsp+0B8h+var_98], rcx
0x18000d789  mov     rcx, rsi
0x18000d78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d791  mov     ebx, eax
0x18000d793  test    eax, eax
0x18000d795  jns     short loc_18000D7B2
0x18000d797  mov     r9d, 3C7h
0x18000d79d  mov     ecx, eax
0x18000d79f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d7a6  lea     rdx, aHr; "hr"
0x18000d7ad  call    DebugTraceError
0x18000d7b2  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d7b9  call    cs:__imp_ReleaseSRWLockShared
0x18000d7bf  mov     eax, ebx
0x18000d7c1  add     rsp, 98h
0x18000d7c8  pop     rdi
0x18000d7c9  pop     rsi
0x18000d7ca  pop     rbp
0x18000d7cb  pop     rbx
0x18000d7cc  retn
```
