# Tls1ComputeMasterKey

- ea: `0x180005cb0`
- end: `0x180005e3b`
- name: `Tls1ComputeMasterKey`
- size: `395`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007990`
- `0x180007de4`
- `0x18001355c`

## callees

- `0x180005cb0`
- `0x180008810`
- `0x18000b594`
- `0x18000b654`
- `0x180012cdc`
- `0x180024ef0`
- `0x180025660`

## string_xrefs

- `0x180005ddb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180005e21`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls1ComputeMasterKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        _BYTE *a8,
        int a9)
{
  int v11; // edi
  _BYTE *v13; // r11
  const char *v14; // rcx
  int v15; // r10d
  int v16; // eax
  int v17; // ebx
  int v19; // edx
  _BYTE v20[64]; // [rsp+60h] [rbp-68h] BYREF

  v11 = 64;
  memset(v20, 0, sizeof(v20));
  v13 = a8;
  if ( a8 )
  {
    v11 = a9;
    v14 = "extended master secret";
    v15 = 22;
    goto LABEL_3;
  }
  v17 = Tls1CombineRandomSeeds(a4, a5, a6, a7, (__int64)v20);
  if ( v17 >= 0 )
  {
    v13 = v20;
    v15 = 13;
    v14 = "master secret";
LABEL_3:
    v16 = Tls1Prf(
            *(_DWORD *)(a2 + 8),
            *(const WCHAR **)(*(_QWORD *)(a2 + 16) + 104LL),
            *(_QWORD *)(*(_QWORD *)(a2 + 16) + 136LL),
            (UCHAR *)(a3 + 12),
            *(_DWORD *)a3 - 12,
            (__int64)v14,
            v15,
            (__int64)v13,
            v11,
            a2 + 28,
            0x30u);
    v17 = v16;
    if ( v16 < 0 )
      DebugTraceError((unsigned int)v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 192);
    return (unsigned int)v17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      (unsigned int)"Status",
      v17,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      158);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180005cb0  mov     [rsp+arg_0], rbx
0x180005cb5  push    rsi
0x180005cb6  push    rdi
0x180005cb7  push    r14
0x180005cb9  sub     rsp, 0B0h
0x180005cc0  mov     rax, cs:__security_cookie
0x180005cc7  xor     rax, rsp
0x180005cca  mov     [rsp+0C8h+var_28], rax
0x180005cd2  mov     r14, r8
0x180005cd5  lea     rcx, [rsp+0C8h+var_68]; void *
0x180005cda  mov     rsi, rdx
0x180005cdd  mov     edi, 40h ; '@'
0x180005ce2  mov     r8d, edi; Size
0x180005ce5  xor     edx, edx; Val
0x180005ce7  mov     rbx, r9
0x180005cea  call    memset
0x180005cef  mov     r11, [rsp+0C8h+arg_38]
0x180005cf7  test    r11, r11
0x180005cfa  jz      loc_180005D8F
0x180005d00  mov     edi, [rsp+0C8h+arg_40]
0x180005d07  lea     rcx, TLS_EXTENDED_MASTER_SECRET_LABEL; "extended master secret"
0x180005d0e  mov     r10d, 16h
0x180005d14  mov     rdx, [rsi+10h]
0x180005d18  lea     rax, [rsi+1Ch]
0x180005d1c  mov     r8d, [r14]
0x180005d1f  lea     r9, [r14+0Ch]
0x180005d23  mov     [rsp+0C8h+var_78], 30h ; '0'
0x180005d2b  sub     r8d, 0Ch
0x180005d2f  mov     [rsp+0C8h+var_80], rax
0x180005d34  mov     [rsp+0C8h+var_88], edi
0x180005d38  mov     [rsp+0C8h+var_90], r11
0x180005d3d  mov     [rsp+0C8h+var_98], r10d
0x180005d42  mov     [rsp+0C8h+var_A0], rcx
0x180005d47  mov     ecx, [rsi+8]
0x180005d4a  mov     dword ptr [rsp+0C8h+var_A8], r8d
0x180005d4f  mov     r8, [rdx+88h]
0x180005d56  mov     rdx, [rdx+68h]
0x180005d5a  call    Tls1Prf
0x180005d5f  mov     ebx, eax
0x180005d61  test    eax, eax
0x180005d63  js      loc_180005E1B
0x180005d69  mov     eax, ebx
0x180005d6b  mov     rcx, [rsp+0C8h+var_28]
0x180005d73  xor     rcx, rsp; StackCookie
0x180005d76  call    __security_check_cookie
0x180005d7b  mov     rbx, [rsp+0C8h+arg_0]
0x180005d83  add     rsp, 0B0h
0x180005d8a  pop     r14
0x180005d8c  pop     rdi
0x180005d8d  pop     rsi
0x180005d8e  retn
0x180005d8f  mov     r9d, [rsp+0C8h+arg_30]
0x180005d97  lea     rax, [rsp+0C8h+var_68]
0x180005d9c  mov     r8, [rsp+0C8h+arg_28]
0x180005da4  mov     rcx, rbx
0x180005da7  mov     edx, [rsp+0C8h+arg_20]
0x180005dae  mov     [rsp+0C8h+var_A8], rax
0x180005db3  call    Tls1CombineRandomSeeds
0x180005db8  mov     ebx, eax
0x180005dba  test    eax, eax
0x180005dbc  jns     short loc_180005E04
0x180005dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dc5  lea     rax, WPP_GLOBAL_Control
0x180005dcc  cmp     rcx, rax
0x180005dcf  jz      short loc_180005D69
0x180005dd1  test    byte ptr [rcx+1Ch], 1
0x180005dd5  jz      short loc_180005D69
0x180005dd7  mov     rcx, [rcx+10h]
0x180005ddb  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005de2  mov     [rsp+0C8h+var_98], 9Eh
0x180005dea  lea     r9, aStatus; "Status"
0x180005df1  mov     [rsp+0C8h+var_A0], r8
0x180005df6  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x180005dfa  call    WPP_SF_sDsd
0x180005dff  jmp     loc_180005D69
0x180005e04  lea     r11, [rsp+0C8h+var_68]
0x180005e09  mov     r10d, 0Dh
0x180005e0f  lea     rcx, TLS_MASTER_SECRET_LABEL; "master secret"
0x180005e16  jmp     loc_180005D14
0x180005e1b  mov     r9d, 0C0h
0x180005e21  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005e28  lea     rdx, aStatus; "Status"
0x180005e2f  mov     ecx, eax
0x180005e31  call    DebugTraceError
0x180005e36  jmp     loc_180005D69
```
