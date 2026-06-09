# s_GetPregenUserKey

- ea: `0x18000d9e0`
- end: `0x18000dad6`
- name: `s_GetPregenUserKey`
- size: `246`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800081ec`
- `0x18000b62c`
- `0x18000d9e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000da47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000da47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dac5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dac5`

## string_xrefs

- `0x18000da11`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000daab`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_GetPregenUserKey(
        void *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  int PopKeyFunctionTable; // eax
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // eax

  if ( (unsigned int)IsCallerLocalServiceOrLocalSystem(a1) )
  {
    if ( !g_ngcFuncLoaded )
    {
      PopKeyFunctionTable = LoadPopKeyFunctionTable();
      v10 = PopKeyFunctionTable;
      if ( PopKeyFunctionTable < 0 )
      {
        v11 = 803;
        v12 = (unsigned int)PopKeyFunctionTable;
        goto LABEL_3;
      }
    }
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v16 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, __int64, __int64))qword_1800259E0)(
              a2,
              a3,
              a5,
              a4,
              a7,
              a6);
      v10 = v16;
      if ( v16 >= 0 )
      {
LABEL_12:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        return v10;
      }
      v14 = 827;
      v15 = (unsigned int)v16;
    }
    else
    {
      v10 = -2146893779;
      v14 = 814;
      v15 = 2148073517LL;
    }
    DebugTraceError(v15, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v14);
    goto LABEL_12;
  }
  v10 = -2146893808;
  v11 = 794;
  v12 = 2148073488LL;
LABEL_3:
  DebugTraceError(v12, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v11);
  return v10;
}

```

## disassembly

```asm
0x18000d9e0  push    rbx
0x18000d9e2  push    rbp
0x18000d9e3  push    rsi
0x18000d9e4  push    rdi
0x18000d9e5  sub     rsp, 48h
0x18000d9e9  mov     rdi, r9
0x18000d9ec  mov     esi, r8d
0x18000d9ef  mov     ebp, edx
0x18000d9f1  call    IsCallerLocalServiceOrLocalSystem
0x18000d9f6  test    eax, eax
0x18000d9f8  jnz     short loc_18000DA22
0x18000d9fa  mov     ebx, 80090010h
0x18000d9ff  mov     r9d, 31Ah
0x18000da05  mov     ecx, 80090010h
0x18000da0a  lea     rdx, aHr; "hr"
0x18000da11  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da18  call    DebugTraceError
0x18000da1d  jmp     loc_18000DACB
0x18000da22  cmp     cs:g_ngcFuncLoaded, 0
0x18000da29  jnz     short loc_18000DA40
0x18000da2b  call    LoadPopKeyFunctionTable
0x18000da30  mov     ebx, eax
0x18000da32  test    eax, eax
0x18000da34  jns     short loc_18000DA40
0x18000da36  mov     r9d, 323h
0x18000da3c  mov     ecx, eax
0x18000da3e  jmp     short loc_18000DA0A
0x18000da40  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000da47  call    cs:__imp_AcquireSRWLockShared
0x18000da4d  cmp     cs:g_ngcFuncLoaded, 0
0x18000da54  jnz     short loc_18000DA68
0x18000da56  mov     ebx, 8009002Dh
0x18000da5b  mov     r9d, 32Eh
0x18000da61  mov     ecx, 8009002Dh
0x18000da66  jmp     short loc_18000DAAB
0x18000da68  mov     rcx, [rsp+68h+arg_28]
0x18000da70  mov     r9, rdi
0x18000da73  mov     r8, [rsp+68h+arg_20]
0x18000da7b  mov     edx, esi
0x18000da7d  mov     rax, cs:qword_1800259E0
0x18000da84  mov     [rsp+68h+var_40], rcx
0x18000da89  mov     rcx, [rsp+68h+arg_30]
0x18000da91  mov     [rsp+68h+var_48], rcx
0x18000da96  mov     ecx, ebp
0x18000da98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da9d  mov     ebx, eax
0x18000da9f  test    eax, eax
0x18000daa1  jns     short loc_18000DABE
0x18000daa3  mov     r9d, 33Bh
0x18000daa9  mov     ecx, eax
0x18000daab  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dab2  lea     rdx, aHr; "hr"
0x18000dab9  call    DebugTraceError
0x18000dabe  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000dac5  call    cs:__imp_ReleaseSRWLockShared
0x18000dacb  mov     eax, ebx
0x18000dacd  add     rsp, 48h
0x18000dad1  pop     rdi
0x18000dad2  pop     rsi
0x18000dad3  pop     rbp
0x18000dad4  pop     rbx
0x18000dad5  retn
```
