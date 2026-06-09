# APP_POOL_HASH_MAPPER::CheckAndAddAppPool(ushort const *,STRU *)

- ea: `0x180060160`
- end: `0x1800603db`
- name: `?CheckAndAddAppPool@APP_POOL_HASH_MAPPER@@QEAAJPEBGPEAVSTRU@@@Z`
- size: `635`
- prototype: `int(APP_POOL_HASH_MAPPER *__hidden this, const unsigned __int16 *, struct STRU *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002d780`

## callees

- `0x180001234`
- `0x180001274`
- `0x180060160`
- `0x18006048c`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180060198`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18006028d`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180060198`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18006028d`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180060360`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800603bc`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180060360`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800603bc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180060239`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180060239`
- `iisutil!PuDbgPrintError` at `0x180060208`
- `iisutil!PuDbgPrintError` at `0x1800603a2`
- `iisutil!PuDbgPrintError` at `0x180060208`
- `iisutil!PuDbgPrintError` at `0x1800603a2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180060317`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180060317`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800601ad`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800602a2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180060342`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800601ad`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800602a2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180060342`

## string_xrefs

- `0x1800601fa`: `servercommon\inetsrv\iis\iisrearc\core\common\apppoolhashmapper\app_pool_hash_mapper.cxx`
- `0x180060394`: `servercommon\inetsrv\iis\iisrearc\core\common\apppoolhashmapper\app_pool_hash_mapper.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall APP_POOL_HASH_MAPPER::CheckAndAddAppPool(
        APP_POOL_HASH_MAPPER *this,
        const unsigned __int16 *a2,
        struct STRU *a3)
{
  int Key; // eax
  char *v7; // rbx
  int v8; // edi
  struct APP_POOL_HASH *v10; // r15
  int v11; // eax
  char *v12; // rax
  __int64 v13; // r8
  void *Block; // [rsp+60h] [rbp+8h] BYREF
  struct APP_POOL_HASH *v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  Block = 0;
  Key = CLKRHashTable::FindKey((char *)this + 8, a2, &Block);
  v7 = (char *)Block;
  if ( !Key )
  {
    v8 = STRU::Copy(a3, a2);
    if ( v8 >= 0 )
    {
      v8 = -2147024844;
      *((_DWORD *)v7 + 18) = 0;
      goto LABEL_9;
    }
LABEL_8:
    if ( !v7 )
      return (unsigned int)v8;
    goto LABEL_9;
  }
  if ( Key != 2 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\apppoolhashmapper\\app_pool_hash_mapper.cxx",
        144,
        "APP_POOL_HASH_MAPPER::CheckAndAddAppPool",
        -2147467259,
        "AppPoolToHash hash table lookup failed\n");
LABEL_7:
    v8 = -2147467259;
    goto LABEL_8;
  }
  v8 = CalculateAppPoolHash(a2, &v15);
  if ( v8 < 0 )
    goto LABEL_8;
  Block = 0;
  v10 = v15;
  v11 = CLKRHashTable::FindKey((char *)this + 80, v15, &Block);
  v7 = (char *)Block;
  if ( !v11 )
  {
    v8 = STRU::Copy(a3, a2);
    if ( v8 >= 0 )
    {
      v8 = -2147022882;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 && v7 )
        goto LABEL_10;
      return (unsigned int)v8;
    }
    goto LABEL_8;
  }
  if ( v11 != 2 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\apppoolhashmapper\\app_pool_hash_mapper.cxx",
        181,
        "APP_POOL_HASH_MAPPER::CheckAndAddAppPool",
        -2147467259,
        "AppPool hash table lookup failed\n");
    goto LABEL_7;
  }
  v12 = (char *)operator new(0x60u);
  v7 = v12;
  Block = v12;
  if ( v12 )
  {
    *(_DWORD *)v12 = 1;
    STRU::STRU((STRU *)(v12 + 8));
    *((_QWORD *)v7 + 8) = 0;
    *((_DWORD *)v7 + 18) = 1;
  }
  else
  {
    v7 = 0;
  }
  if ( !v7 )
    return (unsigned int)-2147024882;
  v8 = STRU::Copy((STRU *)(v7 + 8), a2);
  if ( v8 >= 0 )
  {
    *((_QWORD *)v7 + 8) = v10;
    if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 8, v7, 0) )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
      {
LABEL_31:
        v8 = -2147467259;
        goto LABEL_9;
      }
      v13 = 211;
LABEL_30:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\apppoolhashmapper\\app_pool_hash_mapper.cxx",
        v13,
        "APP_POOL_HASH_MAPPER::CheckAndAddAppPool",
        -2147467259,
        "Inserting application into hashtable failed\n");
      goto LABEL_31;
    }
    if ( (unsigned int)CLKRHashTable::InsertRecord((char *)this + 80, v7, 0) )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_31;
      v13 = 226;
      goto LABEL_30;
    }
  }
LABEL_9:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
  {
LABEL_10:
    operator delete(*((void **)v7 + 8));
    *((_QWORD *)v7 + 8) = 0;
    STRU::~STRU((STRU *)(v7 + 8));
    operator delete(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180060160  mov     rax, rsp
0x180060163  mov     [rax+10h], rbx
0x180060167  mov     [rax+18h], rbp
0x18006016b  push    rsi
0x18006016c  push    rdi
0x18006016d  push    r12
0x18006016f  push    r14
0x180060171  push    r15
0x180060173  sub     rsp, 30h
0x180060177  mov     rbp, r8
0x18006017a  mov     rsi, rdx
0x18006017d  mov     r14, rcx
0x180060180  mov     qword ptr [rax+20h], 0
0x180060188  mov     qword ptr [rax+8], 0
0x180060190  lea     r8, [rax+8]
0x180060194  add     rcx, 8
0x180060198  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18006019e  mov     rbx, [rsp+58h+Block]
0x1800601a3  test    eax, eax
0x1800601a5  jnz     short loc_1800601C7
0x1800601a7  mov     rdx, rsi
0x1800601aa  mov     rcx, rbp
0x1800601ad  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800601b3  mov     edi, eax
0x1800601b5  test    eax, eax
0x1800601b7  js      short loc_180060213
0x1800601b9  mov     edi, 80070034h
0x1800601be  mov     dword ptr [rbx+48h], 0
0x1800601c5  jmp     short loc_180060218
0x1800601c7  cmp     eax, 2
0x1800601ca  jz      loc_180060260
0x1800601d0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800601d7  jz      short loc_18006020E
0x1800601d9  lea     rax, aApppooltohashH; "AppPoolToHash hash table lookup failed"...
0x1800601e0  mov     r8d, 90h
0x1800601e6  mov     [rsp+58h+var_30], rax
0x1800601eb  lea     r9, aAppPoolHashMap; "APP_POOL_HASH_MAPPER::CheckAndAddAppPoo"...
0x1800601f2  mov     [rsp+58h+var_38], 80004005h
0x1800601fa  lea     rdx, aServercommonIn_27; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180060201  mov     rcx, cs:g_pDebug
0x180060208  call    cs:__imp_PuDbgPrintError
0x18006020e  mov     edi, 80004005h
0x180060213  test    rbx, rbx
0x180060216  jz      short loc_180060247
0x180060218  or      eax, 0FFFFFFFFh
0x18006021b  lock xadd [rbx], eax
0x18006021f  cmp     eax, 1
0x180060222  jnz     short loc_180060247
0x180060224  mov     rcx, [rbx+40h]; Block
0x180060228  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006022d  mov     qword ptr [rbx+40h], 0
0x180060235  lea     rcx, [rbx+8]
0x180060239  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18006023f  mov     rcx, rbx; Block
0x180060242  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180060247  mov     eax, edi
0x180060249  mov     rbx, [rsp+58h+arg_8]
0x18006024e  mov     rbp, [rsp+58h+arg_10]
0x180060253  add     rsp, 30h
0x180060257  pop     r15
0x180060259  pop     r14
0x18006025b  pop     r12
0x18006025d  pop     rdi
0x18006025e  pop     rsi
0x18006025f  retn
0x180060260  lea     rdx, [rsp+58h+arg_18]; struct APP_POOL_HASH **
0x180060265  mov     rcx, rsi; Src
0x180060268  call    ?CalculateAppPoolHash@@YAJPEBGPEAPEAUAPP_POOL_HASH@@@Z; CalculateAppPoolHash(ushort const *,APP_POOL_HASH * *)
0x18006026d  mov     edi, eax
0x18006026f  test    eax, eax
0x180060271  js      short loc_180060213
0x180060273  mov     [rsp+58h+Block], 0
0x18006027c  lea     r8, [rsp+58h+Block]
0x180060281  mov     r15, [rsp+58h+arg_18]
0x180060286  mov     rdx, r15
0x180060289  lea     rcx, [r14+50h]
0x18006028d  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180060293  mov     rbx, [rsp+58h+Block]
0x180060298  test    eax, eax
0x18006029a  jnz     short loc_1800602D1
0x18006029c  mov     rdx, rsi
0x18006029f  mov     rcx, rbp
0x1800602a2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800602a8  mov     edi, eax
0x1800602aa  test    eax, eax
0x1800602ac  js      loc_180060213
0x1800602b2  mov     edi, 800707DEh
0x1800602b7  or      eax, 0FFFFFFFFh
0x1800602ba  lock xadd [rbx], eax
0x1800602be  cmp     eax, 1
0x1800602c1  jnz     short loc_180060247
0x1800602c3  test    rbx, rbx
0x1800602c6  jz      loc_180060247
0x1800602cc  jmp     loc_180060224
0x1800602d1  cmp     eax, 2
0x1800602d4  jz      short loc_1800602F5
0x1800602d6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800602dd  jz      loc_18006020E
0x1800602e3  lea     rax, aApppoolHashTab; "AppPool hash table lookup failed\n"
0x1800602ea  mov     r8d, 0B5h
0x1800602f0  jmp     loc_1800601E6
0x1800602f5  mov     ecx, 60h ; '`'; Size
0x1800602fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800602ff  mov     rbx, rax
0x180060302  mov     [rsp+58h+Block], rax
0x180060307  test    rax, rax
0x18006030a  jz      short loc_18006032A
0x18006030c  mov     edi, 1
0x180060311  mov     [rax], edi
0x180060313  lea     rcx, [rax+8]
0x180060317  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18006031d  mov     qword ptr [rbx+40h], 0
0x180060325  mov     [rbx+48h], edi
0x180060328  jmp     short loc_18006032C
0x18006032a  xor     ebx, ebx
0x18006032c  test    rbx, rbx
0x18006032f  jnz     short loc_18006033B
0x180060331  mov     edi, 8007000Eh
0x180060336  jmp     loc_180060247
0x18006033b  lea     rcx, [rbx+8]
0x18006033f  mov     rdx, rsi
0x180060342  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180060348  mov     edi, eax
0x18006034a  test    eax, eax
0x18006034c  js      loc_180060218
0x180060352  mov     [rbx+40h], r15
0x180060356  xor     r8d, r8d
0x180060359  mov     rdx, rbx
0x18006035c  lea     rcx, [r14+8]
0x180060360  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180060366  test    eax, eax
0x180060368  jz      short loc_1800603B2
0x18006036a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180060371  jz      short loc_1800603A8
0x180060373  mov     r8d, 0D3h
0x180060379  lea     rax, aInsertingAppli; "Inserting application into hashtable fa"...
0x180060380  mov     [rsp+58h+var_30], rax
0x180060385  lea     r9, aAppPoolHashMap; "APP_POOL_HASH_MAPPER::CheckAndAddAppPoo"...
0x18006038c  mov     [rsp+58h+var_38], 80004005h
0x180060394  lea     rdx, aServercommonIn_27; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18006039b  mov     rcx, cs:g_pDebug
0x1800603a2  call    cs:__imp_PuDbgPrintError
0x1800603a8  mov     edi, 80004005h
0x1800603ad  jmp     loc_180060218
0x1800603b2  xor     r8d, r8d
0x1800603b5  mov     rdx, rbx
0x1800603b8  lea     rcx, [r14+50h]
0x1800603bc  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800603c2  test    eax, eax
0x1800603c4  jz      loc_180060218
0x1800603ca  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800603d1  jz      short loc_1800603A8
0x1800603d3  mov     r8d, 0E2h
0x1800603d9  jmp     short loc_180060379
```
