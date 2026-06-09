# CliCryptVerifySignature

- ea: `0x180022bd0`
- end: `0x180022e0b`
- name: `CliCryptVerifySignature`
- size: `571`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x180022bd0`
- `0x180060f5c`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18006291a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006291a`
- `RPCRT4!NdrClientCall3` at `0x180022cb6`
- `RPCRT4!NdrClientCall3` at `0x180022cb6`

## string_xrefs

- `0x180022c2f`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180022d12`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180022d4b`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180022db1`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptVerifySignature(
        __int64 *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7,
        int a8)
{
  __int128 *v11; // r12
  __int64 v12; // r8
  __int64 v13; // rdx
  int Pointer; // eax
  unsigned int v15; // ebx
  int v17; // esi
  __int128 v18; // [rsp+78h] [rbp-40h] BYREF

  DWORD2(v18) = 0;
  *(_QWORD *)&v18 = 0;
  if ( !a3 )
  {
    v11 = 0;
LABEL_14:
    v17 = 0;
    goto LABEL_15;
  }
  v11 = &v18;
  v18 = 0;
  if ( (a8 & 2) != 0 )
  {
    LODWORD(v18) = 2;
    *((_QWORD *)&v18 + 1) = a3;
LABEL_4:
    if ( a2 )
      v12 = *a2;
    else
      v12 = 0;
    if ( a1 )
      v13 = *a1;
    else
      v13 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x15u,
                              0,
                              g_RpcBindingContext,
                              qword_18007A5E0,
                              v13,
                              v12,
                              v11,
                              a4,
                              a5,
                              a6,
                              a7,
                              a8).Pointer;
    v15 = Pointer;
    if ( Pointer < 0 )
      DebugTraceError(
        (unsigned int)Pointer,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        2965);
    return v15;
  }
  if ( (a8 & 0xC) != 0 )
  {
    LODWORD(v18) = 4;
    *((_QWORD *)&v18 + 1) = a3;
    goto LABEL_14;
  }
  if ( (a8 & 1) != 0 )
  {
    LODWORD(v18) = 1;
    goto LABEL_4;
  }
  if ( (a8 & 0x20) != 0 )
  {
    LODWORD(v18) = 5;
    *((_QWORD *)&v18 + 1) = a3;
    goto LABEL_4;
  }
  v17 = -2146893815;
  DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 384);
LABEL_15:
  if ( !v17 )
    goto LABEL_4;
  v15 = v17;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      v17,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
      158);
  return v15;
}

```

## disassembly

```asm
0x180022bd0  mov     r11, rsp
0x180022bd3  mov     [r11+8], rbx
0x180022bd7  mov     [r11+10h], rsi
0x180022bdb  push    rdi
0x180022bdc  push    r12
0x180022bde  push    r13
0x180022be0  push    r14
0x180022be2  push    r15
0x180022be4  sub     rsp, 90h
0x180022beb  mov     r13, r9
0x180022bee  mov     r14, rdx
0x180022bf1  mov     r15, rcx
0x180022bf4  xor     eax, eax
0x180022bf6  mov     [r11-3Ch], rax
0x180022bfa  mov     [r11-40h], rax
0x180022bfe  mov     ebx, [rsp+0B8h+arg_38]
0x180022c05  test    r8, r8
0x180022c08  jz      loc_180022D48
0x180022c0e  lea     r12, [r11-40h]
0x180022c12  xorps   xmm0, xmm0
0x180022c15  movups  [rsp+0B8h+var_40], xmm0
0x180022c1a  test    bl, 2
0x180022c1d  jz      loc_180022D9A
0x180022c23  mov     dword ptr [rsp+0B8h+var_40], 2
0x180022c2b  mov     [r11-38h], r8
0x180022c2f  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022c36  test    r14, r14
0x180022c39  jz      loc_180022CEE
0x180022c3f  mov     r8, [r14]
0x180022c42  test    r15, r15
0x180022c45  jz      loc_180022CF6
0x180022c4b  mov     rdx, [r15]
0x180022c4e  mov     rcx, cs:qword_18007A5E0
0x180022c55  mov     [rsp+0B8h+arg_10], 0
0x180022c61  mov     [rsp+0B8h+var_58], ebx
0x180022c65  mov     eax, [rsp+0B8h+arg_30]
0x180022c6c  mov     [rsp+0B8h+var_60], eax
0x180022c70  mov     rax, [rsp+0B8h+arg_28]
0x180022c78  mov     [rsp+0B8h+var_68], rax
0x180022c7d  mov     eax, [rsp+0B8h+arg_20]
0x180022c84  mov     [rsp+0B8h+var_70], eax
0x180022c88  mov     [rsp+0B8h+var_78], r13
0x180022c8d  mov     [rsp+0B8h+var_80], r12
0x180022c92  mov     [rsp+0B8h+var_88], r8
0x180022c97  mov     [rsp+0B8h+var_90], rdx
0x180022c9c  mov     [rsp+0B8h+var_98], rcx
0x180022ca1  mov     r9, cs:g_RpcBindingContext
0x180022ca8  xor     r8d, r8d; pReturnValue
0x180022cab  lea     edx, [r8+15h]; nProcNum
0x180022caf  lea     rcx, pProxyInfo; pProxyInfo
0x180022cb6  call    cs:__imp_NdrClientCall3
0x180022cbd  nop     dword ptr [rax+rax+00h]
0x180022cc2  mov     rbx, rax
0x180022cc5  mov     [rsp+0B8h+arg_10], rax
0x180022ccd  mov     [rsp+0B8h+var_48], eax
0x180022cd1  test    eax, eax
0x180022cd3  jns     short loc_180022CFD
0x180022cd5  mov     r9d, 0B95h
0x180022cdb  mov     r8, rdi
0x180022cde  lea     rdx, aStatus; "Status"
0x180022ce5  mov     ecx, eax
0x180022ce7  call    DebugTraceError
0x180022cec  jmp     short loc_180022CFD
0x180022cee  xor     r8d, r8d
0x180022cf1  jmp     loc_180022C42
0x180022cf6  xor     edx, edx
0x180022cf8  jmp     loc_180022C4E
0x180022cfd  jmp     short loc_180022D28
0x180022cff  mov     ecx, eax
0x180022d01  call    HResultFromRpcException
0x180022d06  mov     ebx, eax
0x180022d08  mov     [rsp+0B8h+var_48], eax
0x180022d0c  mov     r9d, 0B99h
0x180022d12  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022d19  lea     rdx, aStatus; "Status"
0x180022d20  mov     ecx, eax
0x180022d22  call    DebugTraceError
0x180022d27  nop
0x180022d28  mov     eax, ebx
0x180022d2a  lea     r11, [rsp+0B8h+var_28]
0x180022d32  mov     rbx, [r11+30h]
0x180022d36  mov     rsi, [r11+38h]
0x180022d3a  mov     rsp, r11
0x180022d3d  pop     r15
0x180022d3f  pop     r14
0x180022d41  pop     r13
0x180022d43  pop     r12
0x180022d45  pop     rdi
0x180022d46  retn
0x180022d48  xor     r12d, r12d
0x180022d4b  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022d52  xor     esi, esi
0x180022d54  test    esi, esi
0x180022d56  jz      loc_180022C36
0x180022d5c  mov     ebx, esi
0x180022d5e  lea     rax, WPP_GLOBAL_Control
0x180022d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d6c  cmp     rcx, rax
0x180022d6f  jz      short loc_180022D28
0x180022d71  test    byte ptr [rcx+1Ch], 1
0x180022d75  jz      short loc_180022D28
0x180022d77  mov     dword ptr [rsp+0B8h+var_88], 0B9Eh
0x180022d7f  mov     [rsp+0B8h+var_90], rdi
0x180022d84  mov     dword ptr [rsp+0B8h+var_98], esi
0x180022d88  lea     r9, aStatus; "Status"
0x180022d8f  mov     rcx, [rcx+10h]
0x180022d93  call    WPP_SF_sDsd
0x180022d98  jmp     short loc_180022D28
0x180022d9a  test    bl, 0Ch
0x180022d9d  jnz     short loc_180022DF6
0x180022d9f  test    bl, 1
0x180022da2  jz      short loc_180022DB1
0x180022da4  mov     dword ptr [rsp+0B8h+var_40], 1
0x180022dac  jmp     loc_180022C2F
0x180022db1  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022db8  test    bl, 20h
0x180022dbb  jz      short loc_180022DD2
0x180022dbd  mov     dword ptr [rsp+0B8h+var_40], 5
0x180022dc5  mov     qword ptr [rsp+0B8h+var_40+8], r8
0x180022dcd  jmp     loc_180022C36
0x180022dd2  mov     esi, 80090009h
0x180022dd7  mov     r9d, 180h
0x180022ddd  mov     r8, rdi
0x180022de0  lea     rdx, aStatus; "Status"
0x180022de7  mov     ecx, 80090009h
0x180022dec  call    DebugTraceError
0x180022df1  jmp     loc_180022D54
0x180022df6  mov     dword ptr [rsp+0B8h+var_40], 4
0x180022dfe  mov     qword ptr [rsp+0B8h+var_40+8], r8
0x180022e06  jmp     loc_180022D4B
0x18006290c  push    rbp
0x18006290e  sub     rsp, 70h
0x180062912  mov     rbp, rdx
0x180062915  mov     rcx, [rcx]
0x180062918  mov     ecx, [rcx]; ExceptionCode
0x18006291a  call    cs:__imp_I_RpcExceptionFilter
0x180062921  nop     dword ptr [rax+rax+00h]
0x180062926  nop
0x180062927  add     rsp, 70h
0x18006292b  pop     rbp
0x18006292c  retn
```
