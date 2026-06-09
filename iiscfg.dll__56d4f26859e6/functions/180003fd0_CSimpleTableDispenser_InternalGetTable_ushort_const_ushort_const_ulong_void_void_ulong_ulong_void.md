# CSimpleTableDispenser::InternalGetTable(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,void * *)

- ea: `0x180003fd0`
- end: `0x1800043dd`
- name: `?InternalGetTable@CSimpleTableDispenser@@AEAAJPEBG0KPEAX1KKPEAPEAX@Z`
- size: `1037`
- prototype: `__int64 __fastcall(CSimpleTableDispenser *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, _DWORD *, unsigned int *, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003ad0`

## callees

- `0x180002d6c`
- `0x180003fd0`
- `0x18002e0ca`
- `0x180030010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x1800040a1`
- `IisRTL!PuDbgPrint` at `0x1800040f3`
- `IisRTL!PuDbgPrint` at `0x1800041b4`
- `IisRTL!PuDbgPrint` at `0x1800042a1`
- `IisRTL!PuDbgPrint` at `0x1800040a1`
- `IisRTL!PuDbgPrint` at `0x1800040f3`
- `IisRTL!PuDbgPrint` at `0x1800041b4`
- `IisRTL!PuDbgPrint` at `0x1800042a1`

## string_xrefs

- `0x18000409a`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`
- `0x1800040e7`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`
- `0x1800041a2`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`
- `0x180004288`: `inetsrv\iis\mb\config\src\core\dispenser\cstdisp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CSimpleTableDispenser::InternalGetTable(
        CSimpleTableDispenser *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned int *a6,
        unsigned int a7,
        unsigned int a8,
        void **a9)
{
  void **v13; // r14
  void *v15; // r13
  unsigned int *v16; // r12
  unsigned int i; // edx
  unsigned int v18; // esi
  __int64 v19; // rcx
  int v20; // ebx
  unsigned int v21; // r15d
  int v22; // eax
  int TableObjectByID; // eax
  int v24; // eax
  int v25; // eax
  __int64 v26; // [rsp+68h] [rbp-91h] BYREF
  __int64 v27; // [rsp+70h] [rbp-89h] BYREF
  __int128 v28; // [rsp+78h] [rbp-81h] BYREF
  _BYTE v29[64]; // [rsp+88h] [rbp-71h] BYREF
  _BYTE *v30; // [rsp+C8h] [rbp-31h]
  unsigned int v34; // [rsp+160h] [rbp+67h] BYREF

  v34 = a4;
  v26 = 0;
  v28 = 0;
  memset_0(v29, 0, 0x68u);
  v27 = 0;
  if ( (!a2 || !a3) && !a4 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
        316,
        "CSimpleTableDispenser::InternalGetTable",
        "GetTable either needs Database/TableName OR TableID.");
    return 2147942487LL;
  }
  v13 = a9;
  *a9 = 0;
  if ( a7 == 3 )
  {
    v15 = a5;
    v16 = a6;
    if ( a5 )
    {
      if ( !a6 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
            335,
            "CSimpleTableDispenser::InternalGetTable",
            "Invalid query");
        return 2147942487LL;
      }
      for ( i = 0; i < *a6; ++i )
      {
        if ( (unsigned int)(a5[6 * i + 3] + 268435454) <= 1 )
        {
          v18 = a8 | 1;
          goto LABEL_21;
        }
      }
    }
    v18 = a8;
LABEL_21:
    if ( (v18 & 1) != 0 )
    {
      return 2149648397LL;
    }
    else
    {
      v19 = *((_QWORD *)this + 4);
      *(_QWORD *)&v28 = &v34;
      *((_QWORD *)&v28 + 1) = (char *)&v26 + 4;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int64 *))(*(_QWORD *)v19 + 24LL))(
              v19,
              0,
              &v28,
              &v26);
      if ( v20 >= 0 )
      {
        v21 = v26;
        while ( 1 )
        {
          v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 4) + 32LL))(
                  *((_QWORD *)this + 4),
                  v21++,
                  13);
          v20 = v22;
          if ( v22 == -2145318890 )
            break;
          if ( v22 < 0 )
            goto LABEL_48;
          TableObjectByID = CSimpleTableDispenser::CreateTableObjectByID(
                              this,
                              a2,
                              a3,
                              v34,
                              v15,
                              v16,
                              3u,
                              v18,
                              0,
                              (struct tSERVERWIRINGMETARow *)v29,
                              v13);
          v20 = TableObjectByID;
          if ( !TableObjectByID )
            break;
          if ( TableObjectByID != -2145318896 )
          {
            if ( TableObjectByID == -2145318895 )
            {
              v20 = 0;
            }
            else if ( (g_dwDebugFlags & 3) != 0 )
            {
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
                397,
                "CSimpleTableDispenser::InternalGetTable",
                "%x error in the interceptor",
                TableObjectByID);
            }
            goto LABEL_48;
          }
        }
        if ( (v18 & 0x10000) != 0 )
          goto LABEL_57;
        while ( 1 )
        {
          v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 4) + 32LL))(
                  *((_QWORD *)this + 4),
                  v21,
                  13);
          if ( v20 )
            break;
          if ( (*v30 & 1) == 0 )
          {
            v24 = CSimpleTableDispenser::CreateTableObjectByID(
                    this,
                    a2,
                    a3,
                    v34,
                    v15,
                    v16,
                    3u,
                    v18,
                    *v13,
                    (struct tSERVERWIRINGMETARow *)v29,
                    v13);
            v20 = v24;
            if ( v24 < 0 )
              goto LABEL_48;
            if ( v24 )
              break;
          }
          ++v21;
        }
        v25 = 0;
        if ( v20 != -2145318890 )
          v25 = v20;
        v20 = v25;
        if ( v25 >= 0 )
        {
LABEL_57:
          if ( *v13 )
          {
            v20 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))*v13)(*v13, &IID_ISimpleTableAdvanced, &v27);
            if ( v20 >= 0 )
              v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
          }
          else
          {
            v20 = -2147467259;
          }
        }
LABEL_48:
        if ( v27 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        if ( v20 < 0 )
        {
          if ( *v13 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)*v13 + 16LL))(*v13);
          *v13 = 0;
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
          365,
          "CSimpleTableDispenser::InternalGetTable",
          "No wiring was found for tid = %d",
          v34);
      }
      return (unsigned int)v20;
    }
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\core\\dispenser\\cstdisp.cpp",
        327,
        "CSimpleTableDispenser::InternalGetTable",
        "Query format not supported");
    return 2149648396LL;
  }
}

```

## disassembly

```asm
0x180003fd0  mov     rax, rsp
0x180003fd3  mov     [rax+20h], r9d
0x180003fd7  mov     [rax+18h], r8
0x180003fdb  mov     [rax+10h], rdx
0x180003fdf  mov     [rax+8], rcx
0x180003fe3  push    rbp
0x180003fe4  push    rbx
0x180003fe5  push    rsi
0x180003fe6  push    rdi
0x180003fe7  push    r12
0x180003fe9  push    r13
0x180003feb  push    r14
0x180003fed  push    r15
0x180003fef  lea     rbp, [rax-47h]
0x180003ff3  sub     rsp, 0F8h
0x180003ffa  mov     rsi, rdx
0x180003ffd  mov     dword ptr [rsp+130h+var_D0], 0
0x180004005  xor     edx, edx; Val
0x180004007  mov     rdi, r8
0x18000400a  mov     r15, rcx
0x18000400d  xorps   xmm0, xmm0
0x180004010  lea     rcx, [rbp+3Fh+var_B0]; void *
0x180004014  mov     ebx, r9d
0x180004017  movups  [rsp+130h+var_C8+8], xmm0
0x18000401c  lea     r8d, [rdx+68h]; Size
0x180004020  call    memset_0
0x180004025  xor     eax, eax
0x180004027  mov     qword ptr [rsp+130h+var_C8], rax
0x18000402c  mov     dword ptr [rsp+130h+var_D0+4], eax
0x180004030  test    rsi, rsi
0x180004033  jz      short loc_18000403A
0x180004035  test    rdi, rdi
0x180004038  jnz     short loc_18000405D
0x18000403a  test    ebx, ebx
0x18000403c  jnz     short loc_18000405D
0x18000403e  lea     edi, [rbx+3]
0x180004041  test    byte ptr cs:g_dwDebugFlags, dil
0x180004048  jz      loc_1800040F9
0x18000404e  lea     rax, aGettableEither; "GetTable either needs Database/TableNam"...
0x180004055  mov     r8d, 13Ch
0x18000405b  jmp     short loc_1800040D9
0x18000405d  mov     r14, [rbp+3Fh+arg_40]
0x180004064  mov     edi, 3
0x180004069  mov     [r14], rax
0x18000406c  cmp     [rbp+3Fh+arg_30], edi
0x18000406f  jz      short loc_1800040B1
0x180004071  test    byte ptr cs:g_dwDebugFlags, dil
0x180004078  jz      short loc_1800040A7
0x18000407a  mov     rcx, cs:g_pDebug
0x180004081  lea     rax, aQueryFormatNot; "Query format not supported"
0x180004088  lea     r9, aCsimpletabledi_0; "CSimpleTableDispenser::InternalGetTable"
0x18000408f  mov     [rsp+130h+var_110], rax
0x180004094  mov     r8d, 147h
0x18000409a  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x1800040a1  call    cs:__imp_PuDbgPrint
0x1800040a7  mov     eax, 8021080Ch
0x1800040ac  jmp     loc_1800043C9
0x1800040b1  mov     r13, [rbp+3Fh+arg_20]
0x1800040b5  mov     r12, [rbp+3Fh+arg_28]
0x1800040b9  test    r13, r13
0x1800040bc  jz      short loc_18000412F
0x1800040be  test    r12, r12
0x1800040c1  jnz     short loc_180004103
0x1800040c3  test    byte ptr cs:g_dwDebugFlags, dil
0x1800040ca  jz      short loc_1800040F9
0x1800040cc  lea     rax, aInvalidQuery; "Invalid query"
0x1800040d3  mov     r8d, 14Fh
0x1800040d9  mov     rcx, cs:g_pDebug
0x1800040e0  lea     r9, aCsimpletabledi_0; "CSimpleTableDispenser::InternalGetTable"
0x1800040e7  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x1800040ee  mov     [rsp+130h+var_110], rax
0x1800040f3  call    cs:__imp_PuDbgPrint
0x1800040f9  mov     eax, 80070057h
0x1800040fe  jmp     loc_1800043C9
0x180004103  mov     edx, eax
0x180004105  cmp     edx, [r12]
0x180004109  jnb     short loc_18000412F
0x18000410b  mov     eax, edx
0x18000410d  lea     rcx, [rax+rax*2]
0x180004111  mov     eax, [r13+rcx*8+0Ch]
0x180004116  add     eax, 0FFFFFFEh
0x18000411b  cmp     eax, 1
0x18000411e  jbe     short loc_180004124
0x180004120  inc     edx
0x180004122  jmp     short loc_180004105
0x180004124  mov     esi, [rbp+3Fh+arg_38]
0x18000412a  or      esi, 1
0x18000412d  jmp     short loc_180004135
0x18000412f  mov     esi, [rbp+3Fh+arg_38]
0x180004135  test    sil, 1
0x180004139  jz      short loc_180004145
0x18000413b  mov     eax, 8021080Dh
0x180004140  jmp     loc_1800043C9
0x180004145  mov     rcx, [r15+20h]
0x180004149  lea     rax, [rbp+3Fh+arg_18]
0x18000414d  mov     qword ptr [rsp+130h+var_C8+8], rax
0x180004152  lea     r9, [rsp+130h+var_D0]
0x180004157  lea     rax, [rsp+130h+var_D0+4]
0x18000415c  xor     edx, edx
0x18000415e  mov     [rbp+3Fh+var_B8], rax
0x180004162  lea     r8, [rsp+130h+var_C8+8]
0x180004167  mov     rax, [rcx]
0x18000416a  mov     rax, [rax+18h]
0x18000416e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004173  mov     ebx, eax
0x180004175  test    eax, eax
0x180004177  jns     short loc_1800041BF
0x180004179  test    byte ptr cs:g_dwDebugFlags, dil
0x180004180  jz      loc_1800043C7
0x180004186  mov     ecx, [rbp+3Fh+arg_18]
0x180004189  lea     rax, aNoWiringWasFou; "No wiring was found for tid = %d"
0x180004190  mov     dword ptr [rsp+130h+var_108], ecx
0x180004194  lea     r9, aCsimpletabledi_0; "CSimpleTableDispenser::InternalGetTable"
0x18000419b  mov     rcx, cs:g_pDebug
0x1800041a2  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x1800041a9  mov     r8d, 16Dh
0x1800041af  mov     [rsp+130h+var_110], rax
0x1800041b4  call    cs:__imp_PuDbgPrint
0x1800041ba  jmp     loc_1800043C7
0x1800041bf  mov     r15d, dword ptr [rsp+130h+var_D0]
0x1800041c4  mov     rcx, [rbp+3Fh+arg_0]
0x1800041c8  lea     rdx, [rbp+3Fh+var_B0]
0x1800041cc  mov     [rsp+130h+var_108], rdx
0x1800041d1  xor     r9d, r9d
0x1800041d4  mov     edx, r15d
0x1800041d7  mov     [rsp+130h+var_110], 0
0x1800041e0  mov     rcx, [rcx+20h]
0x1800041e4  lea     r8d, [r9+0Dh]
0x1800041e8  mov     rax, [rcx]
0x1800041eb  mov     rax, [rax+20h]
0x1800041ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041f4  inc     r15d
0x1800041f7  mov     ebx, eax
0x1800041f9  cmp     eax, 80210816h
0x1800041fe  jz      loc_1800042AC
0x180004204  test    eax, eax
0x180004206  js      loc_180004392
0x18000420c  mov     r9d, [rbp+3Fh+arg_18]; unsigned int
0x180004210  lea     rax, [rbp+3Fh+var_B0]
0x180004214  mov     r8, [rbp+3Fh+arg_10]; unsigned __int16 *
0x180004218  mov     rdx, [rbp+3Fh+arg_8]; unsigned __int16 *
0x18000421c  mov     rcx, [rbp+3Fh+arg_0]; this
0x180004220  mov     [rsp+50h], r14; void **
0x180004225  mov     [rsp+130h+var_E8], rax; struct tSERVERWIRINGMETARow *
0x18000422a  mov     [rsp+130h+var_F0], 0; void *
0x180004233  mov     [rsp+130h+var_F8], esi; unsigned int
0x180004237  mov     [rsp+130h+var_100], edi; unsigned int
0x18000423b  mov     [rsp+130h+var_108], r12; void *
0x180004240  mov     [rsp+130h+var_110], r13; void *
0x180004245  call    ?CreateTableObjectByID@CSimpleTableDispenser@@AEAAJPEBG0KPEAX1KK1PEAUtSERVERWIRINGMETARow@@PEAPEAX@Z; CSimpleTableDispenser::CreateTableObjectByID(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,void *,tSERVERWIRINGMETARow *,void * *)
0x18000424a  mov     ebx, eax
0x18000424c  test    eax, eax
0x18000424e  jz      short loc_1800042AC
0x180004250  cmp     eax, 80210810h
0x180004255  jz      loc_1800041C4
0x18000425b  cmp     eax, 80210811h
0x180004260  jnz     short loc_180004269
0x180004262  xor     ebx, ebx
0x180004264  jmp     loc_180004392
0x180004269  test    byte ptr cs:g_dwDebugFlags, dil
0x180004270  jz      loc_180004392
0x180004276  mov     rcx, cs:g_pDebug
0x18000427d  lea     r9, aCsimpletabledi_0; "CSimpleTableDispenser::InternalGetTable"
0x180004284  mov     dword ptr [rsp+130h+var_108], eax
0x180004288  lea     rdx, aInetsrvIisMbCo_15; "inetsrv\\iis\\mb\\config\\src\\core\\di"...
0x18000428f  lea     rax, aXErrorInTheInt; "%x error in the interceptor"
0x180004296  mov     r8d, 18Dh
0x18000429c  mov     [rsp+130h+var_110], rax
0x1800042a1  call    cs:__imp_PuDbgPrint
0x1800042a7  jmp     loc_180004392
0x1800042ac  bt      esi, 10h
0x1800042b0  jb      loc_180004353
0x1800042b6  mov     rax, [rbp+3Fh+arg_0]
0x1800042ba  lea     rdx, [rbp+3Fh+var_B0]
0x1800042be  mov     [rsp+130h+var_108], rdx
0x1800042c3  xor     r9d, r9d
0x1800042c6  mov     edx, r15d
0x1800042c9  mov     [rsp+130h+var_110], 0
0x1800042d2  mov     rcx, [rax+20h]
0x1800042d6  lea     r8d, [r9+0Dh]
0x1800042da  mov     rax, [rcx]
0x1800042dd  mov     rax, [rax+20h]
0x1800042e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042e6  mov     ebx, eax
0x1800042e8  test    eax, eax
0x1800042ea  jnz     short loc_180004342
0x1800042ec  mov     rax, [rbp+3Fh+var_70]
0x1800042f0  test    byte ptr [rax], 1
0x1800042f3  jnz     short loc_18000433A
0x1800042f5  mov     r9d, [rbp+3Fh+arg_18]; unsigned int
0x1800042f9  lea     rax, [rbp+3Fh+var_B0]
0x1800042fd  mov     r8, [rbp+3Fh+arg_10]; unsigned __int16 *
0x180004301  mov     rdx, [rbp+3Fh+arg_8]; unsigned __int16 *
0x180004305  mov     rcx, [rbp+3Fh+arg_0]; this
0x180004309  mov     [rsp+50h], r14; void **
0x18000430e  mov     [rsp+130h+var_E8], rax; struct tSERVERWIRINGMETARow *
0x180004313  mov     rax, [r14]
0x180004316  mov     [rsp+130h+var_F0], rax; void *
0x18000431b  mov     [rsp+130h+var_F8], esi; unsigned int
0x18000431f  mov     [rsp+130h+var_100], edi; unsigned int
0x180004323  mov     [rsp+130h+var_108], r12; void *
0x180004328  mov     [rsp+130h+var_110], r13; void *
0x18000432d  call    ?CreateTableObjectByID@CSimpleTableDispenser@@AEAAJPEBG0KPEAX1KK1PEAUtSERVERWIRINGMETARow@@PEAPEAX@Z; CSimpleTableDispenser::CreateTableObjectByID(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,void *,tSERVERWIRINGMETARow *,void * *)
0x180004332  mov     ebx, eax
0x180004334  test    eax, eax
0x180004336  js      short loc_180004392
0x180004338  jnz     short loc_180004342
0x18000433a  inc     r15d
0x18000433d  jmp     loc_1800042B6
0x180004342  xor     eax, eax
0x180004344  cmp     ebx, 80210816h
0x18000434a  cmovnz  eax, ebx
0x18000434d  mov     ebx, eax
0x18000434f  test    eax, eax
0x180004351  js      short loc_180004392
0x180004353  mov     rcx, [r14]
0x180004356  test    rcx, rcx
0x180004359  jnz     short loc_180004362
0x18000435b  mov     ebx, 80004005h
0x180004360  jmp     short loc_180004392
0x180004362  mov     rax, [rcx]
0x180004365  lea     r8, [rsp+130h+var_C8]
0x18000436a  lea     rdx, IID_ISimpleTableAdvanced
0x180004371  mov     rax, [rax]
0x180004374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004379  mov     ebx, eax
0x18000437b  test    eax, eax
0x18000437d  js      short loc_180004392
0x18000437f  mov     rcx, qword ptr [rsp+130h+var_C8]
0x180004384  mov     rax, [rcx]
0x180004387  mov     rax, [rax+18h]
0x18000438b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004390  mov     ebx, eax
0x180004392  mov     rcx, qword ptr [rsp+130h+var_C8]
0x180004397  test    rcx, rcx
0x18000439a  jz      short loc_1800043A8
0x18000439c  mov     rax, [rcx]
0x18000439f  mov     rax, [rax+10h]
0x1800043a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a8  test    ebx, ebx
0x1800043aa  jns     short loc_1800043C7
0x1800043ac  mov     rcx, [r14]
0x1800043af  test    rcx, rcx
0x1800043b2  jz      short loc_1800043C0
0x1800043b4  mov     rax, [rcx]
0x1800043b7  mov     rax, [rax+10h]
0x1800043bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c0  mov     qword ptr [r14], 0
0x1800043c7  mov     eax, ebx
0x1800043c9  add     rsp, 0F8h
0x1800043d0  pop     r15
0x1800043d2  pop     r14
0x1800043d4  pop     r13
0x1800043d6  pop     r12
0x1800043d8  pop     rdi
0x1800043d9  pop     rsi
0x1800043da  pop     rbx
0x1800043db  pop     rbp
0x1800043dc  retn
```
