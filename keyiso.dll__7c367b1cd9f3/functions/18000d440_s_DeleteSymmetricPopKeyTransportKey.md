# s_DeleteSymmetricPopKeyTransportKey

- ea: `0x18000d440`
- end: `0x18000d596`
- name: `s_DeleteSymmetricPopKeyTransportKey`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180008690`
- `0x18000b62c`
- `0x18000d440`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d50d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d50d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d572`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d572`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d582`

## string_xrefs

- `0x18000d4aa`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000d558`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_DeleteSymmetricPopKeyTransportKey(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        unsigned int a6)
{
  int PopKeyFunctionTable; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  HLOCAL v12; // rdi
  __int64 v13; // r9
  __int64 v14; // rcx
  int v15; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-48h] BYREF
  __int128 v18; // [rsp+48h] [rbp-40h] BYREF
  __int64 v19; // [rsp+58h] [rbp-30h]

  v18 = 0;
  v19 = 0;
  hMem = 0;
  PopKeyFunctionTable = CheckKeyAccessRight(a1, a2, (__int64)a5, a6, 1u, 0, 0, &hMem);
  v10 = PopKeyFunctionTable;
  if ( PopKeyFunctionTable < 0 )
  {
    v11 = 228;
LABEL_3:
    DebugTraceError(
      (unsigned int)PopKeyFunctionTable,
      "hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      v11);
    goto LABEL_15;
  }
  v12 = hMem;
  if ( a5 )
    v12 = a5;
  *(_QWORD *)&v18 = a2;
  *((_QWORD *)&v18 + 1) = a3;
  v19 = a4;
  if ( !g_ngcFuncLoaded )
  {
    PopKeyFunctionTable = LoadPopKeyFunctionTable();
    v10 = PopKeyFunctionTable;
    if ( PopKeyFunctionTable < 0 )
    {
      v11 = 242;
      goto LABEL_3;
    }
  }
  AcquireSRWLockShared(&g_ngcFuncLoadLock);
  if ( !g_ngcFuncLoaded )
  {
    v10 = -2146893779;
    v13 = 253;
    v14 = 2148073517LL;
LABEL_13:
    DebugTraceError(v14, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v13);
    goto LABEL_14;
  }
  v15 = ((__int64 (__fastcall *)(__int128 *, HLOCAL, _QWORD))g_NgcPopKeyFunctions)(&v18, v12, a6);
  v10 = v15;
  if ( v15 < 0 )
  {
    v13 = 263;
    v14 = (unsigned int)v15;
    goto LABEL_13;
  }
LABEL_14:
  ReleaseSRWLockShared(&g_ngcFuncLoadLock);
LABEL_15:
  if ( hMem )
    LocalFree(hMem);
  return v10;
}

```

## disassembly

```asm
0x18000d440  mov     r11, rsp
0x18000d443  push    rbx
0x18000d444  push    rbp
0x18000d445  push    rdi
0x18000d446  push    r14
0x18000d448  push    r15
0x18000d44a  sub     rsp, 60h
0x18000d44e  xor     eax, eax
0x18000d450  xorps   xmm0, xmm0
0x18000d453  movups  [rsp+88h+var_40], xmm0
0x18000d458  mov     [r11-30h], rax
0x18000d45c  mov     rbp, r9
0x18000d45f  mov     r9d, [rsp+88h+arg_28]
0x18000d467  mov     r14, r8
0x18000d46a  mov     r8, [rsp+88h+arg_20]
0x18000d472  mov     r15, rdx
0x18000d475  mov     [r11-48h], rax
0x18000d479  lea     rax, [r11-48h]
0x18000d47d  mov     [r11-50h], rax
0x18000d481  mov     qword ptr [r11-58h], 0
0x18000d489  mov     qword ptr [r11-60h], 0
0x18000d491  mov     [rsp+88h+var_68], 1
0x18000d499  call    CheckKeyAccessRight
0x18000d49e  mov     ebx, eax
0x18000d4a0  test    eax, eax
0x18000d4a2  jns     short loc_18000D4C4
0x18000d4a4  mov     r9d, 0E4h
0x18000d4aa  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d4b1  mov     ecx, eax
0x18000d4b3  lea     rdx, aHr; "hr"
0x18000d4ba  call    DebugTraceError
0x18000d4bf  jmp     loc_18000D578
0x18000d4c4  cmp     [rsp+88h+arg_20], 0
0x18000d4cd  mov     rdi, [rsp+88h+hMem]
0x18000d4d2  cmovnz  rdi, [rsp+88h+arg_20]
0x18000d4db  cmp     cs:g_ngcFuncLoaded, 0
0x18000d4e2  mov     qword ptr [rsp+88h+var_40], r15
0x18000d4e7  mov     qword ptr [rsp+88h+var_40+8], r14
0x18000d4ec  mov     [rsp+88h+var_30], rbp
0x18000d4f1  jnz     short loc_18000D506
0x18000d4f3  call    LoadPopKeyFunctionTable
0x18000d4f8  mov     ebx, eax
0x18000d4fa  test    eax, eax
0x18000d4fc  jns     short loc_18000D506
0x18000d4fe  mov     r9d, 0F2h
0x18000d504  jmp     short loc_18000D4AA
0x18000d506  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d50d  call    cs:__imp_AcquireSRWLockShared
0x18000d513  cmp     cs:g_ngcFuncLoaded, 0
0x18000d51a  jnz     short loc_18000D52E
0x18000d51c  mov     ebx, 8009002Dh
0x18000d521  mov     r9d, 0FDh
0x18000d527  mov     ecx, 8009002Dh
0x18000d52c  jmp     short loc_18000D558
0x18000d52e  mov     r8d, [rsp+88h+arg_28]
0x18000d536  lea     rcx, [rsp+88h+var_40]
0x18000d53b  mov     rax, cs:g_NgcPopKeyFunctions
0x18000d542  mov     rdx, rdi
0x18000d545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d54a  mov     ebx, eax
0x18000d54c  test    eax, eax
0x18000d54e  jns     short loc_18000D56B
0x18000d550  mov     r9d, 107h
0x18000d556  mov     ecx, eax
0x18000d558  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d55f  lea     rdx, aHr; "hr"
0x18000d566  call    DebugTraceError
0x18000d56b  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000d572  call    cs:__imp_ReleaseSRWLockShared
0x18000d578  mov     rcx, [rsp+88h+hMem]; hMem
0x18000d57d  test    rcx, rcx
0x18000d580  jz      short loc_18000D588
0x18000d582  call    cs:__imp_LocalFree
0x18000d588  mov     eax, ebx
0x18000d58a  add     rsp, 60h
0x18000d58e  pop     r15
0x18000d590  pop     r14
0x18000d592  pop     rdi
0x18000d593  pop     rbp
0x18000d594  pop     rbx
0x18000d595  retn
```
