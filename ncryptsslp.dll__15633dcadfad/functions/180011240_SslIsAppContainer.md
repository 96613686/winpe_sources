# SslIsAppContainer

- ea: `0x180011240`
- end: `0x180011393`
- name: `SslIsAppContainer`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011110`

## callees

- `0x18000b594`
- `0x180011240`
- `0x180011e00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011376`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011376`
- `ntdll!NtQueryInformationToken` at `0x18001131c`
- `ntdll!NtQueryInformationToken` at `0x18001131c`

## string_xrefs

- `0x18001127a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsncryptprovider.c`
- `0x180011354`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsncryptprovider.c`

## pseudocode

```c
__int64 __fastcall SslIsAppContainer(bool *a1, __int64 a2, int a3)
{
  int v5; // eax
  int v6; // r8d
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  int v9; // r8d
  int TokenInformation; // [rsp+50h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( a1 )
  {
    v5 = OpenCallerToken((__int64)a1, &TokenHandle);
    if ( v5 )
    {
      if ( v5 > 0 )
        v7 = (unsigned __int16)v5 | 0x80070000;
      else
        v7 = v5;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
          v6,
          (unsigned int)"dwStatus",
          v5,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
          202);
    }
    else
    {
      v8 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength);
      v7 = v8;
      if ( v8 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
          v9,
          (unsigned int)"Status",
          v8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
          214);
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    *a1 = TokenInformation != 0;
    return v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsncryptprovider.c",
        192);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180011240  push    rsi
0x180011242  sub     rsp, 40h
0x180011246  xor     eax, eax
0x180011248  mov     rsi, rcx
0x18001124b  mov     [rsp+48h+TokenHandle], rax
0x180011250  mov     [rsp+48h+TokenInformation], eax
0x180011254  mov     [rsp+48h+arg_8], eax
0x180011258  test    rcx, rcx
0x18001125b  jnz     short loc_1800112AD
0x18001125d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011264  lea     rdx, WPP_GLOBAL_Control
0x18001126b  cmp     rcx, rdx
0x18001126e  jz      short loc_1800112A2
0x180011270  test    byte ptr [rcx+1Ch], 1
0x180011274  jz      short loc_1800112A2
0x180011276  mov     rcx, [rcx+10h]
0x18001127a  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011281  mov     [rsp+48h+var_18], 0C0h
0x180011289  lea     r9, aStatus; "Status"
0x180011290  mov     [rsp+48h+var_20], rdx
0x180011295  mov     dword ptr [rsp+48h+ReturnLength], 0C000000Dh
0x18001129d  call    WPP_SF_sDsd
0x1800112a2  mov     eax, 0C000000Dh
0x1800112a7  add     rsp, 40h
0x1800112ab  pop     rsi
0x1800112ac  retn
0x1800112ad  lea     rdx, [rsp+48h+TokenHandle]
0x1800112b2  mov     [rsp+48h+arg_18], rbx
0x1800112b7  call    OpenCallerToken
0x1800112bc  test    eax, eax
0x1800112be  jz      short loc_1800112FD
0x1800112c0  jg      short loc_1800112C6
0x1800112c2  mov     ebx, eax
0x1800112c4  jmp     short loc_1800112CF
0x1800112c6  movzx   ebx, ax
0x1800112c9  or      ebx, 80070000h
0x1800112cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112d6  lea     rdx, WPP_GLOBAL_Control
0x1800112dd  cmp     rcx, rdx
0x1800112e0  jz      loc_180011369
0x1800112e6  test    byte ptr [rcx+1Ch], 1
0x1800112ea  jz      short loc_180011369
0x1800112ec  mov     [rsp+48h+var_18], 0CAh
0x1800112f4  lea     r9, aDwstatus; "dwStatus"
0x1800112fb  jmp     short loc_180011350
0x1800112fd  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180011302  lea     rax, [rsp+48h+arg_8]
0x180011307  mov     r9d, 4; TokenInformationLength
0x18001130d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180011312  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180011317  mov     edx, 1Dh; TokenInformationClass
0x18001131c  call    cs:__imp_NtQueryInformationToken
0x180011322  mov     ebx, eax
0x180011324  test    eax, eax
0x180011326  jz      short loc_180011369
0x180011328  mov     rcx, cs:WPP_GLOBAL_Control
0x18001132f  lea     rdx, WPP_GLOBAL_Control
0x180011336  cmp     rcx, rdx
0x180011339  jz      short loc_180011369
0x18001133b  test    byte ptr [rcx+1Ch], 1
0x18001133f  jz      short loc_180011369
0x180011341  mov     [rsp+48h+var_18], 0D6h
0x180011349  lea     r9, aStatus; "Status"
0x180011350  mov     rcx, [rcx+10h]
0x180011354  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001135b  mov     [rsp+48h+var_20], rdx
0x180011360  mov     dword ptr [rsp+48h+ReturnLength], eax
0x180011364  call    WPP_SF_sDsd
0x180011369  cmp     [rsp+48h+TokenHandle], 0
0x18001136f  jz      short loc_18001137C
0x180011371  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180011376  call    cs:__imp_CloseHandle
0x18001137c  cmp     [rsp+48h+TokenInformation], 0
0x180011381  setnz   al
0x180011384  mov     [rsi], al
0x180011386  mov     eax, ebx
0x180011388  mov     rbx, [rsp+48h+arg_18]
0x18001138d  add     rsp, 40h
0x180011391  pop     rsi
0x180011392  retn
```
