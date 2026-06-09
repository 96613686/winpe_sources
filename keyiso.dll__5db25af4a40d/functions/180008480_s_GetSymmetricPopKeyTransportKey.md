# s_GetSymmetricPopKeyTransportKey

- ea: `0x180008480`
- end: `0x180008688`
- name: `s_GetSymmetricPopKeyTransportKey`
- size: `520`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, void *, unsigned int, unsigned int, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x180008480`
- `0x180008690`
- `0x18000b62c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008596`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008596`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008661`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008661`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008671`

## string_xrefs

- `0x18000850c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x180008575`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x180008647`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_GetSymmetricPopKeyTransportKey(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  int v17; // edx
  int v18; // ebx
  HLOCAL v19; // rdi
  int PopKeyFunctionTable; // eax
  __int64 v21; // r9
  __int64 v22; // rcx
  int v23; // eax
  HLOCAL hMem; // [rsp+60h] [rbp-48h] BYREF
  __int128 v26; // [rsp+68h] [rbp-40h] BYREF
  __int64 v27; // [rsp+78h] [rbp-30h]

  v26 = 0;
  v27 = 0;
  hMem = 0;
  v18 = CheckKeyAccessRight(a1, a2, (__int64)a5, a7, 1u, 0, 0, &hMem);
  if ( v18 >= 0 )
  {
    v19 = hMem;
    if ( a5 )
      v19 = a5;
    *(_QWORD *)&v26 = a2;
    *((_QWORD *)&v26 + 1) = a3;
    v27 = a4;
    if ( !g_ngcFuncLoaded )
    {
      PopKeyFunctionTable = LoadPopKeyFunctionTable();
      v18 = PopKeyFunctionTable;
      if ( PopKeyFunctionTable < 0 )
      {
        DebugTraceError(
          (unsigned int)PopKeyFunctionTable,
          "hr",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
          71);
        goto LABEL_16;
      }
    }
    AcquireSRWLockShared(&g_ngcFuncLoadLock);
    if ( g_ngcFuncLoaded )
    {
      v23 = ((__int64 (__fastcall *)(__int128 *, HLOCAL, _QWORD, _QWORD, __int64, __int64, __int64, __int64, __int64, __int64, __int64))qword_180025998)(
              &v26,
              v19,
              a6,
              a7,
              a9,
              a8,
              a11,
              a10,
              a13,
              a12,
              a14);
      v18 = v23;
      if ( v23 >= 0 )
      {
LABEL_15:
        ReleaseSRWLockShared(&g_ngcFuncLoadLock);
        goto LABEL_16;
      }
      v21 = 100;
      v22 = (unsigned int)v23;
    }
    else
    {
      v18 = -2146893779;
      v21 = 82;
      v22 = 2148073517LL;
    }
    DebugTraceError(v22, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v21);
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      (unsigned int)"hr",
      v18,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      57);
LABEL_16:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180008480  mov     r11, rsp
0x180008483  push    rbx
0x180008484  push    rbp
0x180008485  push    rdi
0x180008486  push    r14
0x180008488  push    r15
0x18000848a  sub     rsp, 80h
0x180008491  xor     eax, eax
0x180008493  xorps   xmm0, xmm0
0x180008496  movups  [rsp+0A8h+var_40], xmm0
0x18000849b  mov     [r11-30h], rax
0x18000849f  mov     rbp, r9
0x1800084a2  mov     r9d, [rsp+0A8h+arg_30]
0x1800084aa  mov     r14, r8
0x1800084ad  mov     r8, [rsp+0A8h+arg_20]
0x1800084b5  mov     r15, rdx
0x1800084b8  mov     [r11-48h], rax
0x1800084bc  lea     rax, [r11-48h]
0x1800084c0  mov     [r11-70h], rax
0x1800084c4  mov     qword ptr [r11-78h], 0
0x1800084cc  mov     qword ptr [r11-80h], 0
0x1800084d4  mov     dword ptr [rsp+0A8h+var_88], 1
0x1800084dc  call    CheckKeyAccessRight
0x1800084e1  mov     ebx, eax
0x1800084e3  test    eax, eax
0x1800084e5  jns     short loc_180008535
0x1800084e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084ee  lea     rax, WPP_GLOBAL_Control
0x1800084f5  cmp     rcx, rax
0x1800084f8  jz      loc_180008667
0x1800084fe  test    byte ptr [rcx+1Ch], 1
0x180008502  jz      loc_180008667
0x180008508  mov     rcx, [rcx+10h]
0x18000850c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008513  mov     dword ptr [rsp+0A8h+var_78], 39h ; '9'
0x18000851b  lea     r9, aHr; "hr"
0x180008522  mov     [rsp+0A8h+var_80], r8
0x180008527  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18000852b  call    WPP_SF_sDsd
0x180008530  jmp     loc_180008667
0x180008535  cmp     [rsp+0A8h+arg_20], 0
0x18000853e  mov     rdi, [rsp+0A8h+hMem]
0x180008543  cmovnz  rdi, [rsp+0A8h+arg_20]
0x18000854c  cmp     cs:g_ngcFuncLoaded, 0
0x180008553  mov     qword ptr [rsp+0A8h+var_40], r15
0x180008558  mov     qword ptr [rsp+0A8h+var_40+8], r14
0x18000855d  mov     [rsp+0A8h+var_30], rbp
0x180008562  jnz     short loc_18000858F
0x180008564  call    LoadPopKeyFunctionTable
0x180008569  mov     ebx, eax
0x18000856b  test    eax, eax
0x18000856d  jns     short loc_18000858F
0x18000856f  mov     r9d, 47h ; 'G'
0x180008575  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000857c  lea     rdx, aHr; "hr"
0x180008583  mov     ecx, eax
0x180008585  call    DebugTraceError
0x18000858a  jmp     loc_180008667
0x18000858f  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x180008596  call    cs:__imp_AcquireSRWLockShared
0x18000859c  cmp     cs:g_ngcFuncLoaded, 0
0x1800085a3  jnz     short loc_1800085BA
0x1800085a5  mov     ebx, 8009002Dh
0x1800085aa  mov     r9d, 52h ; 'R'
0x1800085b0  mov     ecx, 8009002Dh
0x1800085b5  jmp     loc_180008647
0x1800085ba  mov     rax, [rsp+0A8h+arg_68]
0x1800085c2  mov     rdx, rdi
0x1800085c5  mov     rcx, [rsp+0A8h+arg_60]
0x1800085cd  mov     r9d, [rsp+0A8h+arg_30]
0x1800085d5  mov     r8d, [rsp+0A8h+arg_28]
0x1800085dd  mov     [rsp+0A8h+var_58], rax
0x1800085e2  mov     rax, [rsp+0A8h+arg_58]
0x1800085ea  mov     [rsp+0A8h+var_60], rax
0x1800085ef  mov     rax, cs:qword_180025998
0x1800085f6  mov     [rsp+0A8h+var_68], rcx
0x1800085fb  mov     rcx, [rsp+0A8h+arg_48]
0x180008603  mov     [rsp+0A8h+var_70], rcx
0x180008608  mov     rcx, [rsp+0A8h+arg_50]
0x180008610  mov     [rsp+0A8h+var_78], rcx
0x180008615  mov     rcx, [rsp+0A8h+arg_38]
0x18000861d  mov     [rsp+0A8h+var_80], rcx
0x180008622  mov     rcx, [rsp+0A8h+arg_40]
0x18000862a  mov     [rsp+0A8h+var_88], rcx
0x18000862f  lea     rcx, [rsp+0A8h+var_40]
0x180008634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008639  mov     ebx, eax
0x18000863b  test    eax, eax
0x18000863d  jns     short loc_18000865A
0x18000863f  mov     r9d, 64h ; 'd'
0x180008645  mov     ecx, eax
0x180008647  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000864e  lea     rdx, aHr; "hr"
0x180008655  call    DebugTraceError
0x18000865a  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x180008661  call    cs:__imp_ReleaseSRWLockShared
0x180008667  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18000866c  test    rcx, rcx
0x18000866f  jz      short loc_180008677
0x180008671  call    cs:__imp_LocalFree
0x180008677  mov     eax, ebx
0x180008679  add     rsp, 80h
0x180008680  pop     r15
0x180008682  pop     r14
0x180008684  pop     rdi
0x180008685  pop     rbp
0x180008686  pop     rbx
0x180008687  retn
```
