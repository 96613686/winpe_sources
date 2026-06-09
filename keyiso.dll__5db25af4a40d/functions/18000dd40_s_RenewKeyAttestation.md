# s_RenewKeyAttestation

- ea: `0x18000dd40`
- end: `0x18000de72`
- name: `s_RenewKeyAttestation`
- size: `306`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180008690`
- `0x18000b62c`
- `0x18000dd40`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dde1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dde1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000de47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000de47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de57`

## string_xrefs

- `0x18000dd98`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000de2d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_RenewKeyAttestation(void *a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  int PopKeyFunctionTable; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdi
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // eax
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  hMem = 0;
  PopKeyFunctionTable = CheckKeyAccessRight(a1, a2, a4, a5, 0, a2, a3, &hMem);
  v9 = PopKeyFunctionTable;
  if ( PopKeyFunctionTable < 0 )
  {
    v10 = 728;
LABEL_3:
    DebugTraceError(
      (unsigned int)PopKeyFunctionTable,
      "hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      v10);
    goto LABEL_15;
  }
  v11 = (__int64)hMem;
  if ( a4 )
    v11 = a4;
  if ( !g_ngcFuncLoaded )
  {
    PopKeyFunctionTable = LoadPopKeyFunctionTable();
    v9 = PopKeyFunctionTable;
    if ( PopKeyFunctionTable < 0 )
    {
      v10 = 738;
      goto LABEL_3;
    }
  }
  AcquireSRWLockShared(&g_ngcFuncLoadLock);
  if ( !g_ngcFuncLoaded )
  {
    v9 = -2146893779;
    v12 = 749;
    v13 = 2148073517LL;
LABEL_13:
    DebugTraceError(v13, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v12);
    goto LABEL_14;
  }
  v14 = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))qword_1800259D8)(a2, a3, v11, a5);
  v9 = v14;
  if ( v14 < 0 )
  {
    v12 = 760;
    v13 = (unsigned int)v14;
    goto LABEL_13;
  }
LABEL_14:
  ReleaseSRWLockShared(&g_ngcFuncLoadLock);
LABEL_15:
  if ( hMem )
    LocalFree(hMem);
  return v9;
}

```

## disassembly

```asm
0x18000dd40  mov     r11, rsp
0x18000dd43  mov     [r11+8], rbx
0x18000dd47  mov     [r11+10h], rbp
0x18000dd4b  push    rsi
0x18000dd4c  push    rdi
0x18000dd4d  push    r14
0x18000dd4f  sub     rsp, 40h
0x18000dd53  mov     rsi, r9
0x18000dd56  mov     qword ptr [r11+20h], 0
0x18000dd5e  mov     r9d, [rsp+58h+arg_20]
0x18000dd66  lea     rax, [r11+20h]
0x18000dd6a  mov     [r11-20h], rax
0x18000dd6e  mov     rbp, r8
0x18000dd71  mov     [r11-28h], r8
0x18000dd75  mov     r14, rdx
0x18000dd78  mov     [r11-30h], rdx
0x18000dd7c  mov     r8, rsi
0x18000dd7f  mov     [rsp+58h+var_38], 0
0x18000dd87  call    CheckKeyAccessRight
0x18000dd8c  mov     ebx, eax
0x18000dd8e  test    eax, eax
0x18000dd90  jns     short loc_18000DDB2
0x18000dd92  mov     r9d, 2D8h
0x18000dd98  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dd9f  mov     ecx, eax
0x18000dda1  lea     rdx, aHr; "hr"
0x18000dda8  call    DebugTraceError
0x18000ddad  jmp     loc_18000DE4D
0x18000ddb2  mov     rdi, [rsp+58h+hMem]
0x18000ddb7  test    rsi, rsi
0x18000ddba  cmovnz  rdi, rsi
0x18000ddbe  cmp     cs:g_ngcFuncLoaded, 0
0x18000ddc5  jnz     short loc_18000DDDA
0x18000ddc7  call    LoadPopKeyFunctionTable
0x18000ddcc  mov     ebx, eax
0x18000ddce  test    eax, eax
0x18000ddd0  jns     short loc_18000DDDA
0x18000ddd2  mov     r9d, 2E2h
0x18000ddd8  jmp     short loc_18000DD98
0x18000ddda  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000dde1  call    cs:__imp_AcquireSRWLockShared
0x18000dde7  cmp     cs:g_ngcFuncLoaded, 0
0x18000ddee  jnz     short loc_18000DE02
0x18000ddf0  mov     ebx, 8009002Dh
0x18000ddf5  mov     r9d, 2EDh
0x18000ddfb  mov     ecx, 8009002Dh
0x18000de00  jmp     short loc_18000DE2D
0x18000de02  mov     r9d, [rsp+58h+arg_20]
0x18000de0a  mov     r8, rdi
0x18000de0d  mov     rax, cs:qword_1800259D8
0x18000de14  mov     rdx, rbp
0x18000de17  mov     rcx, r14
0x18000de1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de1f  mov     ebx, eax
0x18000de21  test    eax, eax
0x18000de23  jns     short loc_18000DE40
0x18000de25  mov     r9d, 2F8h
0x18000de2b  mov     ecx, eax
0x18000de2d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000de34  lea     rdx, aHr; "hr"
0x18000de3b  call    DebugTraceError
0x18000de40  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000de47  call    cs:__imp_ReleaseSRWLockShared
0x18000de4d  mov     rcx, [rsp+58h+hMem]; hMem
0x18000de52  test    rcx, rcx
0x18000de55  jz      short loc_18000DE5D
0x18000de57  call    cs:__imp_LocalFree
0x18000de5d  mov     rbp, [rsp+58h+arg_8]
0x18000de62  mov     eax, ebx
0x18000de64  mov     rbx, [rsp+58h+arg_0]
0x18000de69  add     rsp, 40h
0x18000de6d  pop     r14
0x18000de6f  pop     rdi
0x18000de70  pop     rsi
0x18000de71  retn
```
