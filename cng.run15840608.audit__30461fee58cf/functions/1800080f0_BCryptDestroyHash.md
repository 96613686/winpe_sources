# BCryptDestroyHash

- ea: `0x1800080f0`
- end: `0x1800082a8`
- name: `BCryptDestroyHash`
- size: `440`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash)`
- caller_count: `12`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001890`
- `0x180001ab0`
- `0x180049084`
- `0x180058070`
- `0x180067ec4`
- `0x180068500`
- `0x1800687b8`
- `0x180068d98`
- `0x180082888`
- `0x180082a40`
- `0x180083724`
- `0x180083a3c`

## callees

- `0x18000421c`
- `0x180006470`
- `0x18000743c`
- `0x1800080f0`
- `0x1800082b0`
- `0x18005b260`
- `0x18009d860`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180008146`
- `ntoskrnl!KeGetCurrentIrql` at `0x180008146`

## string_xrefs

- `0x1800081e8`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000825f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000828e`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDestroyHash(BCRYPT_HASH_HANDLE hHash)
{
  int v1; // edx
  __int64 v2; // r8
  __int64 v4; // rsi
  void *v5; // rbp
  int v6; // edi
  int v7; // r8d
  __int64 v8; // rax
  int v10; // edx
  int v11; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 36, v2);
  if ( hHash
    && *(_DWORD *)hHash >= 0x28u
    && *((_DWORD *)hHash + 1) == 1431655763
    && (*(_DWORD *)(*((_QWORD *)hHash + 1) + 32LL) || KeGetCurrentIrql() < 2u) )
  {
    v4 = *((_QWORD *)hHash + 1);
    v5 = (void *)*((_QWORD *)hHash + 4);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(v4 + 120))(*((_QWORD *)hHash + 2));
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v10 = *((_DWORD *)WPP_GLOBAL_Control + 11);
        if ( (v10 & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v10,
            v7,
            (unsigned int)"Status",
            v6,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
            5);
      }
    }
    else if ( (*(_DWORD *)(v4 + 8) & 8) != 0
           && (v11 = (*(__int64 (__fastcall **)(_QWORD))(v4 + 120))(*((_QWORD *)hHash + 3)), v6 = v11, v11 < 0) )
    {
      DebugTraceError((unsigned int)v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 6416);
    }
    else
    {
      v8 = *(unsigned int *)hHash;
      if ( *(_DWORD *)hHash )
      {
        do
        {
          *(_BYTE *)hHash = 0;
          hHash = (char *)hHash + 1;
          --v8;
        }
        while ( v8 );
      }
      if ( v5 )
        MSCryptFree(v5);
      v6 = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 16), 0xFFFFFFFF) == 1 )
        DestroyAlgorithmHeader((PVOID)v4);
    }
  }
  else
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v1,
        v2,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
        248);
  }
  return v6;
}

```

## disassembly

```asm
0x1800080f0  push    rbx
0x1800080f2  push    rdi
0x1800080f3  push    r14
0x1800080f5  sub     rsp, 40h
0x1800080f9  mov     rbx, rcx
0x1800080fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180008103  lea     r14, WPP_GLOBAL_Control
0x18000810a  cmp     rcx, r14
0x18000810d  jnz     loc_180008222
0x180008113  mov     [rsp+58h+arg_8], rbp
0x180008118  mov     [rsp+58h+arg_10], rsi
0x18000811d  test    rbx, rbx
0x180008120  jz      loc_1800081C8
0x180008126  cmp     dword ptr [rbx], 28h ; '('
0x180008129  jb      loc_1800081C8
0x18000812f  cmp     dword ptr [rbx+4], 55555553h
0x180008136  jnz     loc_1800081C8
0x18000813c  mov     rax, [rbx+8]
0x180008140  cmp     dword ptr [rax+20h], 0
0x180008144  jnz     short loc_180008156
0x180008146  call    cs:__imp_KeGetCurrentIrql
0x18000814d  nop     dword ptr [rax+rax+00h]
0x180008152  cmp     al, 2
0x180008154  jnb     short loc_1800081C8
0x180008156  mov     rsi, [rbx+8]
0x18000815a  mov     rcx, [rbx+10h]
0x18000815e  mov     rbp, [rbx+20h]
0x180008162  mov     rax, [rsi+78h]
0x180008166  call    _guard_dispatch_icall
0x18000816b  mov     edi, eax
0x18000816d  test    eax, eax
0x18000816f  js      loc_180008243
0x180008175  mov     eax, [rsi+8]
0x180008178  test    al, 8
0x18000817a  jnz     loc_180008271
0x180008180  mov     eax, [rbx]
0x180008182  test    rax, rax
0x180008185  jz      short loc_18000819D
0x180008187  nop     word ptr [rax+rax+00000000h]
0x180008190  mov     byte ptr [rbx], 0
0x180008193  lea     rbx, [rbx+1]
0x180008197  sub     rax, 1
0x18000819b  jnz     short loc_180008190
0x18000819d  test    rbp, rbp
0x1800081a0  jz      short loc_1800081AA
0x1800081a2  mov     rcx, rbp; P
0x1800081a5  call    MSCryptFree
0x1800081aa  mov     eax, 0FFFFFFFFh
0x1800081af  lock xadd [rsi+10h], eax
0x1800081b4  mov     edi, 0
0x1800081b9  cmp     eax, 1
0x1800081bc  jnz     short loc_18000820C
0x1800081be  mov     rcx, rsi; P
0x1800081c1  call    DestroyAlgorithmHeader
0x1800081c6  jmp     short loc_18000820C
0x1800081c8  mov     edi, 0C000000Dh
0x1800081cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081d4  cmp     rcx, r14
0x1800081d7  jz      short loc_18000820C
0x1800081d9  mov     eax, [rcx+2Ch]
0x1800081dc  test    al, 1
0x1800081de  jz      short loc_18000820C
0x1800081e0  mov     [rsp+58h+var_28], 18F8h
0x1800081e8  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800081ef  mov     [rsp+58h+var_30], rax
0x1800081f4  mov     [rsp+58h+var_38], 0C000000Dh
0x1800081fc  mov     rcx, [rcx+18h]
0x180008200  lea     r9, aStatus; "Status"
0x180008207  call    WPP_SF_sDsd
0x18000820c  mov     rsi, [rsp+58h+arg_10]
0x180008211  mov     eax, edi
0x180008213  mov     rbp, [rsp+58h+arg_8]
0x180008218  add     rsp, 40h
0x18000821c  pop     r14
0x18000821e  pop     rdi
0x18000821f  pop     rbx
0x180008220  retn
0x180008222  mov     eax, [rcx+2Ch]
0x180008225  test    al, 4
0x180008227  jz      loc_180008113
0x18000822d  mov     rcx, [rcx+18h]
0x180008231  mov     edx, 24h ; '$'
0x180008236  mov     r9, rbx
0x180008239  call    WPP_SF_q
0x18000823e  jmp     loc_180008113
0x180008243  mov     rcx, cs:WPP_GLOBAL_Control
0x18000824a  cmp     rcx, r14
0x18000824d  jz      short loc_18000820C
0x18000824f  mov     edx, [rcx+2Ch]
0x180008252  test    dl, 1
0x180008255  jz      short loc_18000820C
0x180008257  mov     [rsp+58h+var_28], 1905h
0x18000825f  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008266  mov     [rsp+58h+var_30], rax
0x18000826b  mov     [rsp+58h+var_38], edi
0x18000826f  jmp     short loc_1800081FC
0x180008271  mov     rax, [rsi+78h]
0x180008275  mov     rcx, [rbx+18h]
0x180008279  call    _guard_dispatch_icall
0x18000827e  mov     edi, eax
0x180008280  test    eax, eax
0x180008282  jns     loc_180008180
0x180008288  mov     r9d, 1910h
0x18000828e  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008295  lea     rdx, aStatus; "Status"
0x18000829c  mov     ecx, eax
0x18000829e  call    DebugTraceError
0x1800082a3  jmp     loc_18000820C
```
