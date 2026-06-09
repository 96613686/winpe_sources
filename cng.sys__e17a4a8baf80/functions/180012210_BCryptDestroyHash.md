# BCryptDestroyHash

- ea: `0x180012210`
- end: `0x1800123c8`
- name: `BCryptDestroyHash`
- size: `440`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash)`
- caller_count: `12`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000b9b0`
- `0x18000bbd0`
- `0x180053184`
- `0x180062240`
- `0x180072064`
- `0x1800726a0`
- `0x180072958`
- `0x180072f38`
- `0x18008ca78`
- `0x18008cc30`
- `0x18008d914`
- `0x18008dc2c`

## callees

- `0x18000e33c`
- `0x180010590`
- `0x18001155c`
- `0x180012210`
- `0x1800123d0`
- `0x180065430`
- `0x1800a4300`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180012266`
- `ntoskrnl!KeGetCurrentIrql` at `0x180012266`

## string_xrefs

- `0x180012308`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18001237f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800123ae`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x180012210  push    rbx
0x180012212  push    rdi
0x180012213  push    r14
0x180012215  sub     rsp, 40h
0x180012219  mov     rbx, rcx
0x18001221c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012223  lea     r14, WPP_GLOBAL_Control
0x18001222a  cmp     rcx, r14
0x18001222d  jnz     loc_180012342
0x180012233  mov     [rsp+58h+arg_8], rbp
0x180012238  mov     [rsp+58h+arg_10], rsi
0x18001223d  test    rbx, rbx
0x180012240  jz      loc_1800122E8
0x180012246  cmp     dword ptr [rbx], 28h ; '('
0x180012249  jb      loc_1800122E8
0x18001224f  cmp     dword ptr [rbx+4], 55555553h
0x180012256  jnz     loc_1800122E8
0x18001225c  mov     rax, [rbx+8]
0x180012260  cmp     dword ptr [rax+20h], 0
0x180012264  jnz     short loc_180012276
0x180012266  call    cs:__imp_KeGetCurrentIrql
0x18001226d  nop     dword ptr [rax+rax+00h]
0x180012272  cmp     al, 2
0x180012274  jnb     short loc_1800122E8
0x180012276  mov     rsi, [rbx+8]
0x18001227a  mov     rcx, [rbx+10h]
0x18001227e  mov     rbp, [rbx+20h]
0x180012282  mov     rax, [rsi+78h]
0x180012286  call    _guard_dispatch_icall
0x18001228b  mov     edi, eax
0x18001228d  test    eax, eax
0x18001228f  js      loc_180012363
0x180012295  mov     eax, [rsi+8]
0x180012298  test    al, 8
0x18001229a  jnz     loc_180012391
0x1800122a0  mov     eax, [rbx]
0x1800122a2  test    rax, rax
0x1800122a5  jz      short loc_1800122BD
0x1800122a7  nop     word ptr [rax+rax+00000000h]
0x1800122b0  mov     byte ptr [rbx], 0
0x1800122b3  lea     rbx, [rbx+1]
0x1800122b7  sub     rax, 1
0x1800122bb  jnz     short loc_1800122B0
0x1800122bd  test    rbp, rbp
0x1800122c0  jz      short loc_1800122CA
0x1800122c2  mov     rcx, rbp; P
0x1800122c5  call    MSCryptFree
0x1800122ca  mov     eax, 0FFFFFFFFh
0x1800122cf  lock xadd [rsi+10h], eax
0x1800122d4  mov     edi, 0
0x1800122d9  cmp     eax, 1
0x1800122dc  jnz     short loc_18001232C
0x1800122de  mov     rcx, rsi; P
0x1800122e1  call    DestroyAlgorithmHeader
0x1800122e6  jmp     short loc_18001232C
0x1800122e8  mov     edi, 0C000000Dh
0x1800122ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122f4  cmp     rcx, r14
0x1800122f7  jz      short loc_18001232C
0x1800122f9  mov     eax, [rcx+2Ch]
0x1800122fc  test    al, 1
0x1800122fe  jz      short loc_18001232C
0x180012300  mov     [rsp+58h+var_28], 18F8h
0x180012308  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001230f  mov     [rsp+58h+var_30], rax
0x180012314  mov     [rsp+58h+var_38], 0C000000Dh
0x18001231c  mov     rcx, [rcx+18h]
0x180012320  lea     r9, aStatus; "Status"
0x180012327  call    WPP_SF_sDsd
0x18001232c  mov     rsi, [rsp+58h+arg_10]
0x180012331  mov     eax, edi
0x180012333  mov     rbp, [rsp+58h+arg_8]
0x180012338  add     rsp, 40h
0x18001233c  pop     r14
0x18001233e  pop     rdi
0x18001233f  pop     rbx
0x180012340  retn
0x180012342  mov     eax, [rcx+2Ch]
0x180012345  test    al, 4
0x180012347  jz      loc_180012233
0x18001234d  mov     rcx, [rcx+18h]
0x180012351  mov     edx, 24h ; '$'
0x180012356  mov     r9, rbx
0x180012359  call    WPP_SF_q
0x18001235e  jmp     loc_180012233
0x180012363  mov     rcx, cs:WPP_GLOBAL_Control
0x18001236a  cmp     rcx, r14
0x18001236d  jz      short loc_18001232C
0x18001236f  mov     edx, [rcx+2Ch]
0x180012372  test    dl, 1
0x180012375  jz      short loc_18001232C
0x180012377  mov     [rsp+58h+var_28], 1905h
0x18001237f  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012386  mov     [rsp+58h+var_30], rax
0x18001238b  mov     [rsp+58h+var_38], edi
0x18001238f  jmp     short loc_18001231C
0x180012391  mov     rax, [rsi+78h]
0x180012395  mov     rcx, [rbx+18h]
0x180012399  call    _guard_dispatch_icall
0x18001239e  mov     edi, eax
0x1800123a0  test    eax, eax
0x1800123a2  jns     loc_1800122A0
0x1800123a8  mov     r9d, 1910h
0x1800123ae  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800123b5  lea     rdx, aStatus; "Status"
0x1800123bc  mov     ecx, eax
0x1800123be  call    DebugTraceError
0x1800123c3  jmp     loc_18001232C
```
