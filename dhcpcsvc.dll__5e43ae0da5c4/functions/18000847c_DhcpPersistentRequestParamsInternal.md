# DhcpPersistentRequestParamsInternal

- ea: `0x18000847c`
- end: `0x1800086f6`
- name: `DhcpPersistentRequestParamsInternal`
- size: `634`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008390`

## callees

- `0x180002620`
- `0x18000847c`
- `0x18000f4ec`
- `0x180011afc`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180008655`
- `RPCRT4!NdrClientCall3` at `0x180008655`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800085fc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008671`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008692`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800085fc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008671`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008692`

## pseudocode

```c
__int64 __fastcall DhcpPersistentRequestParamsInternal(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        char a6)
{
  unsigned int Pointer; // ebx
  int v11; // r12d
  int v12; // r11d
  unsigned int v13; // ecx
  unsigned int v14; // r9d
  unsigned int i; // edx
  __int64 v16; // rax
  unsigned int v17; // r8d
  int v18; // r10d
  LPWSTR CommandLineW; // rax
  int v20; // ecx
  LPWSTR v21; // rax
  int v22; // ecx
  __int64 v24; // [rsp+C8h] [rbp+10h] BYREF

  v24 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SqdqdL(a1, a2, a3, a1, a2, a3, a4, a5, a6);
  if ( (a2 == 0) != (a3 == 0) || (a4 == 0) != (a5 == 0) || !a1 )
    goto LABEL_4;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  for ( i = 0; i < a5; ++i )
  {
    v16 = 32LL * i;
    v17 = *(_DWORD *)(v16 + a4 + 24);
    if ( v17 > 0xFF || v17 && !*(_QWORD *)(v16 + a4 + 16) )
      goto LABEL_4;
    v18 = *(_DWORD *)(v16 + a4 + 4);
    if ( v18 == 55 )
    {
      if ( *(_DWORD *)(v16 + a4 + 8) )
        continue;
      v11 = *(_DWORD *)(v16 + a4 + 24);
      ++v14;
    }
    if ( !v18 && *(_DWORD *)(v16 + a4 + 8) )
    {
      v12 = *(_DWORD *)(v16 + a4 + 24);
      ++v13;
    }
  }
  if ( (v13 || v14) && v13 <= 1 && v14 <= 1 )
  {
    Pointer = 0;
    if ( !(v12 + v11) )
      goto LABEL_29;
    Pointer = DhcpAdapterNameToIfId(a1, &v24);
    if ( Pointer )
      goto LABEL_29;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      CommandLineW = GetCommandLineW();
      WPP_SF_SS(
        v20,
        Pointer + 76,
        (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
        a1,
        (__int64)CommandLineW);
    }
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xDu, 0).Pointer;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
    {
      v21 = GetCommandLineW();
      WPP_SF_DSS(v22, 77, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v21);
      goto LABEL_29;
    }
    return Pointer;
  }
LABEL_4:
  Pointer = 87;
LABEL_29:
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 78, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000847c  mov     r11, rsp
0x18000847f  mov     [r11+18h], rbx
0x180008483  mov     [r11+8], rcx
0x180008487  push    rsi
0x180008488  push    rdi
0x180008489  push    r12
0x18000848b  push    r14
0x18000848d  push    r15
0x18000848f  sub     rsp, 90h
0x180008496  mov     rsi, r9
0x180008499  mov     r14d, r8d
0x18000849c  mov     r15, rdx
0x18000849f  mov     rdi, rcx
0x1800084a2  xorps   xmm0, xmm0
0x1800084a5  xor     eax, eax
0x1800084a7  movups  [rsp+0B8h+var_48], xmm0
0x1800084ac  mov     [r11-38h], rax
0x1800084b0  movups  [rsp+0B8h+var_58], xmm0
0x1800084b5  mov     [r11+10h], rax
0x1800084b9  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800084c0  jz      short loc_1800084EF
0x1800084c2  mov     eax, [rsp+0B8h+arg_28]
0x1800084c9  mov     [rsp+0B8h+var_78], eax
0x1800084cd  mov     eax, [rsp+0B8h+arg_20]
0x1800084d4  mov     [rsp+0B8h+var_80], eax
0x1800084d8  mov     [rsp+0B8h+var_88], r9
0x1800084dd  mov     dword ptr [rsp+0B8h+var_90], r8d
0x1800084e2  mov     [rsp+0B8h+var_98], rdx
0x1800084e7  mov     r9, rcx
0x1800084ea  call    WPP_SF_SqdqdL
0x1800084ef  xor     ecx, ecx
0x1800084f1  test    r15, r15
0x1800084f4  setz    cl
0x1800084f7  xor     eax, eax
0x1800084f9  test    r14d, r14d
0x1800084fc  setz    al
0x1800084ff  cmp     ecx, eax
0x180008501  jz      short loc_18000850D
0x180008503  mov     ebx, 57h ; 'W'
0x180008508  jmp     loc_1800086B6
0x18000850d  xor     ecx, ecx
0x18000850f  test    rsi, rsi
0x180008512  setz    cl
0x180008515  xor     eax, eax
0x180008517  cmp     [rsp+0B8h+arg_20], eax
0x18000851e  setz    al
0x180008521  cmp     ecx, eax
0x180008523  jnz     short loc_180008503
0x180008525  test    rdi, rdi
0x180008528  jz      short loc_180008503
0x18000852a  xor     r12d, r12d
0x18000852d  xor     r11d, r11d
0x180008530  xor     ecx, ecx
0x180008532  xor     r9d, r9d
0x180008535  xor     edx, edx
0x180008537  cmp     edx, [rsp+0B8h+arg_20]
0x18000853e  jnb     short loc_18000858E
0x180008540  mov     eax, edx
0x180008542  shl     rax, 5
0x180008546  mov     r8d, [rax+rsi+18h]
0x18000854b  cmp     r8d, 0FFh
0x180008552  ja      short loc_180008503
0x180008554  test    r8d, r8d
0x180008557  jz      short loc_180008561
0x180008559  cmp     qword ptr [rax+rsi+10h], 0
0x18000855f  jz      short loc_180008503
0x180008561  mov     r10d, [rax+rsi+4]
0x180008566  cmp     r10d, 37h ; '7'
0x18000856a  jnz     short loc_180008579
0x18000856c  cmp     dword ptr [rax+rsi+8], 0
0x180008571  jnz     short loc_18000858A
0x180008573  mov     r12d, r8d
0x180008576  inc     r9d
0x180008579  test    r10d, r10d
0x18000857c  jnz     short loc_18000858A
0x18000857e  cmp     [rax+rsi+8], r10d
0x180008583  jz      short loc_18000858A
0x180008585  mov     r11d, r8d
0x180008588  inc     ecx
0x18000858a  inc     edx
0x18000858c  jmp     short loc_180008537
0x18000858e  test    ecx, ecx
0x180008590  jnz     short loc_18000859B
0x180008592  test    r9d, r9d
0x180008595  jz      loc_180008503
0x18000859b  cmp     ecx, 1
0x18000859e  ja      loc_180008503
0x1800085a4  cmp     r9d, 1
0x1800085a8  ja      loc_180008503
0x1800085ae  xor     ebx, ebx
0x1800085b0  lea     eax, [r11+r12]
0x1800085b4  test    eax, eax
0x1800085b6  jz      loc_1800086B6
0x1800085bc  mov     [rsp+0B8h+var_38], r14d
0x1800085c4  mov     qword ptr [rsp+0B8h+var_48+8], r15
0x1800085c9  mov     eax, [rsp+0B8h+arg_20]
0x1800085d0  mov     dword ptr [rsp+0B8h+var_58], eax
0x1800085d4  mov     qword ptr [rsp+0B8h+var_58+8], rsi
0x1800085d9  lea     rdx, [rsp+0B8h+arg_8]
0x1800085e1  mov     rcx, rdi
0x1800085e4  call    DhcpAdapterNameToIfId
0x1800085e9  mov     ebx, eax
0x1800085eb  test    eax, eax
0x1800085ed  jnz     loc_1800086B6
0x1800085f3  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800085fa  jz      short loc_18000861A
0x1800085fc  call    cs:__imp_GetCommandLineW
0x180008602  lea     edx, [rbx+4Ch]
0x180008605  mov     [rsp+0B8h+var_98], rax
0x18000860a  mov     r9, rdi
0x18000860d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008614  call    WPP_SF_SS
0x180008619  nop
0x18000861a  mov     [rsp+0B8h+var_60], 0
0x180008623  lea     rax, [rsp+0B8h+var_58]
0x180008628  mov     [rsp+0B8h+var_88], rax
0x18000862d  lea     rax, [rsp+0B8h+var_48]
0x180008632  mov     [rsp+0B8h+var_90], rax
0x180008637  lea     rax, [rsp+0B8h+arg_8]
0x18000863f  mov     [rsp+0B8h+var_98], rax
0x180008644  xor     r9d, r9d
0x180008647  xor     r8d, r8d; pReturnValue
0x18000864a  lea     edx, [r9+0Dh]; nProcNum
0x18000864e  lea     rcx, pProxyInfo; pProxyInfo
0x180008655  call    cs:__imp_NdrClientCall3
0x18000865b  mov     rbx, rax
0x18000865e  mov     [rsp+0B8h+var_60], rax
0x180008663  mov     [rsp+0B8h+var_68], eax
0x180008667  jmp     short loc_180008689
0x180008669  mov     edi, eax
0x18000866b  mov     ebx, eax
0x18000866d  mov     [rsp+0B8h+var_68], eax
0x180008671  call    cs:__imp_GetCommandLineW
0x180008677  mov     rdx, rax
0x18000867a  mov     ecx, ebx
0x18000867c  call    TraceRpcException
0x180008681  mov     rdi, [rsp+0B8h+arg_0]
0x180008689  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008690  jz      short loc_1800086DC
0x180008692  call    cs:__imp_GetCommandLineW
0x180008698  mov     edx, 4Dh ; 'M'
0x18000869d  mov     [rsp+0B8h+var_90], rax
0x1800086a2  mov     [rsp+0B8h+var_98], rdi
0x1800086a7  mov     r9d, ebx
0x1800086aa  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800086b1  call    WPP_SF_DSS
0x1800086b6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800086bd  jz      short loc_1800086DC
0x1800086bf  mov     edx, 4Eh ; 'N'
0x1800086c4  mov     ecx, 404h
0x1800086c9  mov     dword ptr [rsp+0B8h+var_98], ebx
0x1800086cd  mov     r9, rdi
0x1800086d0  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800086d7  call    WPP_SF_SD
0x1800086dc  mov     eax, ebx
0x1800086de  mov     rbx, [rsp+0B8h+arg_10]
0x1800086e6  add     rsp, 90h
0x1800086ed  pop     r15
0x1800086ef  pop     r14
0x1800086f1  pop     r12
0x1800086f3  pop     rdi
0x1800086f4  pop     rsi
0x1800086f5  retn
0x180010cec  push    rbp
0x180010cee  sub     rsp, 50h
0x180010cf2  mov     rbp, rdx
0x180010cf5  mov     rcx, [rcx]
0x180010cf8  mov     ecx, [rcx]; ExceptionCode
0x180010cfa  call    cs:__imp_I_RpcExceptionFilter
0x180010d00  nop
0x180010d01  add     rsp, 50h
0x180010d05  pop     rbp
0x180010d06  retn
```
