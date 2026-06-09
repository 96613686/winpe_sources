# SPSslGenerateSessionKeys

- ea: `0x180005ec0`
- end: `0x180006063`
- name: `SPSslGenerateSessionKeys`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005ec0`
- `0x1800068e0`
- `0x180006b60`
- `0x180007960`
- `0x18000b594`
- `0x18000b654`

## string_xrefs

- `0x180005f56`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005fa2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005fe1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000604b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslGenerateSessionKeys(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  _QWORD *v8; // r8
  _QWORD *v9; // r9
  __int64 v10; // r10
  int v11; // edx
  unsigned int SessionKeys; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rcx
  char v17; // [rsp+30h] [rbp-18h]

  if ( !SslpValidateProvHandle(a1) )
  {
    SessionKeys = -2146893786;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return SessionKeys;
    v17 = 0;
LABEL_13:
    WPP_SF_sDsd(
      v14[2],
      v6,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      v17);
    return SessionKeys;
  }
  v7 = SslpValidateMasterKeyHandle(v6);
  LODWORD(v6) = v7;
  if ( !v7 )
  {
    SessionKeys = -2146893786;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return SessionKeys;
    v17 = 9;
    goto LABEL_13;
  }
  if ( !v8 || !v9 )
  {
    SessionKeys = -2146893785;
    v15 = 3088;
    v16 = 2148073511LL;
    goto LABEL_26;
  }
  if ( a6 )
  {
    SessionKeys = -2146893815;
    v15 = 3095;
    v16 = 2148073481LL;
LABEL_26:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v15);
    return SessionKeys;
  }
  if ( *(_DWORD *)(v7 + 8) == 2 )
  {
    SessionKeys = -2146893783;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        35);
  }
  else
  {
    SessionKeys = TlsGenerateSessionKeys(v10, v7, v8, v9, a5);
    if ( (SessionKeys & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          (unsigned int)"Status",
          SessionKeys,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          48);
    }
    else
    {
      return 0;
    }
  }
  return SessionKeys;
}

```

## disassembly

```asm
0x180005ec0  push    rbx
0x180005ec2  sub     rsp, 40h
0x180005ec6  call    SslpValidateProvHandle
0x180005ecb  mov     r10, rax
0x180005ece  test    rax, rax
0x180005ed1  jz      loc_180005FF6
0x180005ed7  mov     rcx, rdx
0x180005eda  call    SslpValidateMasterKeyHandle
0x180005edf  mov     rdx, rax
0x180005ee2  test    rax, rax
0x180005ee5  jz      short loc_180005F30
0x180005ee7  test    r8, r8
0x180005eea  jz      loc_18000603B
0x180005ef0  test    r9, r9
0x180005ef3  jz      loc_18000603B
0x180005ef9  cmp     [rsp+48h+arg_28], 0
0x180005efe  jnz     loc_180006029
0x180005f04  cmp     dword ptr [rax+8], 2
0x180005f08  jz      short loc_180005F7C
0x180005f0a  mov     rax, [rsp+48h+arg_20]
0x180005f0f  mov     rcx, r10
0x180005f12  mov     [rsp+48h+var_28], rax
0x180005f17  call    TlsGenerateSessionKeys
0x180005f1c  mov     ebx, eax
0x180005f1e  test    eax, eax
0x180005f20  js      loc_180005FB8
0x180005f26  xor     ebx, ebx
0x180005f28  mov     eax, ebx
0x180005f2a  add     rsp, 40h
0x180005f2e  pop     rbx
0x180005f2f  retn
0x180005f30  mov     ebx, 80090026h
0x180005f35  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f3c  lea     rax, WPP_GLOBAL_Control
0x180005f43  cmp     rcx, rax
0x180005f46  jz      short loc_180005F28
0x180005f48  test    byte ptr [rcx+1Ch], 1
0x180005f4c  jz      short loc_180005F28
0x180005f4e  mov     dword ptr [rsp+48h+var_18], 0C09h
0x180005f56  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005f5d  mov     [rsp+48h+var_20], r8
0x180005f62  mov     dword ptr [rsp+48h+var_28], 80090026h
0x180005f6a  mov     rcx, [rcx+10h]
0x180005f6e  lea     r9, aStatus; "Status"
0x180005f75  call    WPP_SF_sDsd
0x180005f7a  jmp     short loc_180005F28
0x180005f7c  mov     ebx, 80090029h
0x180005f81  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f88  lea     rax, WPP_GLOBAL_Control
0x180005f8f  cmp     rcx, rax
0x180005f92  jz      short loc_180005F28
0x180005f94  test    byte ptr [rcx+1Ch], 1
0x180005f98  jz      short loc_180005F28
0x180005f9a  mov     dword ptr [rsp+48h+var_18], 0C23h
0x180005fa2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005fa9  mov     [rsp+48h+var_20], r8
0x180005fae  mov     dword ptr [rsp+48h+var_28], 80090029h
0x180005fb6  jmp     short loc_180005F6A
0x180005fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fbf  lea     rax, WPP_GLOBAL_Control
0x180005fc6  cmp     rcx, rax
0x180005fc9  jz      loc_180005F28
0x180005fcf  test    byte ptr [rcx+1Ch], 1
0x180005fd3  jz      loc_180005F28
0x180005fd9  mov     dword ptr [rsp+48h+var_18], 0C30h
0x180005fe1  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005fe8  mov     [rsp+48h+var_20], r8
0x180005fed  mov     dword ptr [rsp+48h+var_28], ebx
0x180005ff1  jmp     loc_180005F6A
0x180005ff6  mov     ebx, 80090026h
0x180005ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006002  lea     rax, WPP_GLOBAL_Control
0x180006009  cmp     rcx, rax
0x18000600c  jz      loc_180005F28
0x180006012  test    byte ptr [rcx+1Ch], 1
0x180006016  jz      loc_180005F28
0x18000601c  mov     dword ptr [rsp+48h+var_18], 0C00h
0x180006024  jmp     loc_180005F56
0x180006029  mov     ebx, 80090009h
0x18000602e  mov     r9d, 0C17h
0x180006034  mov     ecx, 80090009h
0x180006039  jmp     short loc_18000604B
0x18000603b  mov     ebx, 80090027h
0x180006040  mov     r9d, 0C10h
0x180006046  mov     ecx, 80090027h
0x18000604b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006052  lea     rdx, aStatus; "Status"
0x180006059  call    DebugTraceError
0x18000605e  jmp     loc_180005F28
```
