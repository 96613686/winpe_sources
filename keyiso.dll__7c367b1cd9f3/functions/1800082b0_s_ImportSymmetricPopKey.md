# s_ImportSymmetricPopKey

- ea: `0x1800082b0`
- end: `0x180008479`
- name: `s_ImportSymmetricPopKey`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800082b0`
- `0x180008690`
- `0x18000b62c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800083c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800083c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008455`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008455`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008465`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008465`

## string_xrefs

- `0x180008339`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x1800083a2`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000843b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_ImportSymmetricPopKey(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        unsigned int a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  int v13; // edx
  int v14; // ebx
  HLOCAL v15; // rdi
  int PopKeyFunctionTable; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  int v19; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-48h] BYREF
  __int128 v22; // [rsp+48h] [rbp-40h] BYREF
  __int64 v23; // [rsp+58h] [rbp-30h]

  v22 = 0;
  v23 = 0;
  hMem = 0;
  v14 = CheckKeyAccessRight(a1, a2, (__int64)a5, a6, 1u, 0, 0, &hMem);
  if ( v14 >= 0 )
  {
    v15 = hMem;
    if ( a5 )
      v15 = a5;
    *(_QWORD *)&v22 = a2;
    *((_QWORD *)&v22 + 1) = a3;
    v23 = a4;
    if ( !g_ngcFuncLoaded )
    {
      PopKeyFunctionTable = LoadPopKeyFunctionTable();
      v14 = PopKeyFunctionTable;
      if ( PopKeyFunctionTable < 0 )
      {
        DebugTraceError(
          (unsigned int)PopKeyFunctionTable,
          "hr",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
          324);
        goto LABEL_16;
      }
    }
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v19 = ((__int64 (__fastcall *)(__int128 *, HLOCAL, _QWORD, __int64, int, __int64, __int64))qword_1800259A8)(
              &v22,
              v15,
              a6,
              a8,
              a7,
              a10,
              a9);
      v14 = v19;
      if ( v19 >= 0 )
      {
LABEL_15:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        goto LABEL_16;
      }
      v17 = 349;
      v18 = (unsigned int)v19;
    }
    else
    {
      v14 = -2146893779;
      v17 = 335;
      v18 = 2148073517LL;
    }
    DebugTraceError(v18, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v17);
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      (unsigned int)"hr",
      v14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      54);
LABEL_16:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800082b0  mov     r11, rsp
0x1800082b3  push    rbx
0x1800082b4  push    rbp
0x1800082b5  push    rdi
0x1800082b6  push    r14
0x1800082b8  push    r15
0x1800082ba  sub     rsp, 60h
0x1800082be  xor     eax, eax
0x1800082c0  xorps   xmm0, xmm0
0x1800082c3  movups  [rsp+88h+var_40], xmm0
0x1800082c8  mov     [r11-30h], rax
0x1800082cc  mov     rbp, r9
0x1800082cf  mov     r9d, [rsp+88h+arg_28]
0x1800082d7  mov     r14, r8
0x1800082da  mov     r8, [rsp+88h+arg_20]
0x1800082e2  mov     r15, rdx
0x1800082e5  mov     [r11-48h], rax
0x1800082e9  lea     rax, [r11-48h]
0x1800082ed  mov     [r11-50h], rax
0x1800082f1  mov     qword ptr [r11-58h], 0
0x1800082f9  mov     qword ptr [r11-60h], 0
0x180008301  mov     [rsp+88h+var_68], 1
0x180008309  call    CheckKeyAccessRight
0x18000830e  mov     ebx, eax
0x180008310  test    eax, eax
0x180008312  jns     short loc_180008362
0x180008314  mov     rcx, cs:WPP_GLOBAL_Control
0x18000831b  lea     rax, WPP_GLOBAL_Control
0x180008322  cmp     rcx, rax
0x180008325  jz      loc_18000845B
0x18000832b  test    byte ptr [rcx+1Ch], 1
0x18000832f  jz      loc_18000845B
0x180008335  mov     rcx, [rcx+10h]
0x180008339  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008340  mov     dword ptr [rsp+88h+var_58], 136h
0x180008348  lea     r9, aHr; "hr"
0x18000834f  mov     [rsp+88h+var_60], r8
0x180008354  mov     [rsp+88h+var_68], ebx
0x180008358  call    WPP_SF_sDsd
0x18000835d  jmp     loc_18000845B
0x180008362  cmp     [rsp+88h+arg_20], 0
0x18000836b  mov     rdi, [rsp+88h+hMem]
0x180008370  cmovnz  rdi, [rsp+88h+arg_20]
0x180008379  cmp     cs:g_ngcFuncLoaded, 0
0x180008380  mov     qword ptr [rsp+88h+var_40], r15
0x180008385  mov     qword ptr [rsp+88h+var_40+8], r14
0x18000838a  mov     [rsp+88h+var_30], rbp
0x18000838f  jnz     short loc_1800083BC
0x180008391  call    LoadPopKeyFunctionTable
0x180008396  mov     ebx, eax
0x180008398  test    eax, eax
0x18000839a  jns     short loc_1800083BC
0x18000839c  mov     r9d, 144h
0x1800083a2  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800083a9  lea     rdx, aHr; "hr"
0x1800083b0  mov     ecx, eax
0x1800083b2  call    DebugTraceError
0x1800083b7  jmp     loc_18000845B
0x1800083bc  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x1800083c3  call    cs:__imp_AcquireSRWLockShared
0x1800083c9  cmp     cs:g_ngcFuncLoaded, 0
0x1800083d0  jnz     short loc_1800083E4
0x1800083d2  mov     ebx, 8009002Dh
0x1800083d7  mov     r9d, 14Fh
0x1800083dd  mov     ecx, 8009002Dh
0x1800083e2  jmp     short loc_18000843B
0x1800083e4  mov     rcx, [rsp+88h+arg_40]
0x1800083ec  mov     rdx, rdi
0x1800083ef  mov     r9, [rsp+88h+arg_38]
0x1800083f7  mov     r8d, [rsp+88h+arg_28]
0x1800083ff  mov     rax, cs:qword_1800259A8
0x180008406  mov     [rsp+88h+var_58], rcx
0x18000840b  mov     rcx, [rsp+88h+arg_48]
0x180008413  mov     [rsp+88h+var_60], rcx
0x180008418  mov     ecx, [rsp+88h+arg_30]
0x18000841f  mov     [rsp+88h+var_68], ecx
0x180008423  lea     rcx, [rsp+88h+var_40]
0x180008428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842d  mov     ebx, eax
0x18000842f  test    eax, eax
0x180008431  jns     short loc_18000844E
0x180008433  mov     r9d, 15Dh
0x180008439  mov     ecx, eax
0x18000843b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008442  lea     rdx, aHr; "hr"
0x180008449  call    DebugTraceError
0x18000844e  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x180008455  call    cs:__imp_ReleaseSRWLockShared
0x18000845b  mov     rcx, [rsp+88h+hMem]; hMem
0x180008460  test    rcx, rcx
0x180008463  jz      short loc_18000846B
0x180008465  call    cs:__imp_LocalFree
0x18000846b  mov     eax, ebx
0x18000846d  add     rsp, 60h
0x180008471  pop     r15
0x180008473  pop     r14
0x180008475  pop     rdi
0x180008476  pop     rbp
0x180008477  pop     rbx
0x180008478  retn
```
