# DhcpRegisterParameterChangeNotificationInternal

- ea: `0x180008dd4`
- end: `0x180009058`
- name: `DhcpRegisterParameterChangeNotificationInternal`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008c50`

## callees

- `0x180002620`
- `0x180008dd4`
- `0x18000f4ec`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`
- `0x180012f40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180008fbc`
- `RPCRT4!NdrClientCall3` at `0x180008fbc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008f49`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008fd8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008ff9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008f49`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008fd8`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008ff9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentProcessId` at `0x180008ed9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentProcessId` at `0x180008ed9`

## pseudocode

```c
__int64 __fastcall DhcpRegisterParameterChangeNotificationInternal(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v7; // r15
  __int64 v8; // r12
  int v9; // esi
  int v10; // r14d
  unsigned int i; // ecx
  __int64 v12; // rax
  int v13; // edx
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v16; // ecx
  CLIENT_CALL_RETURN v17; // rax
  LPWSTR v18; // rax
  int v19; // ecx
  __int64 v21; // [rsp+68h] [rbp-80h] BYREF
  CLIENT_CALL_RETURN v22; // [rsp+70h] [rbp-78h]
  __int128 v23; // [rsp+78h] [rbp-70h]
  __int64 v24; // [rsp+88h] [rbp-60h]
  __int128 v25; // [rsp+90h] [rbp-58h]
  __int128 v26; // [rsp+A0h] [rbp-48h]

  v25 = 0;
  v26 = 0;
  v23 = 0;
  v24 = 0;
  v21 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SqdqdLdq(a1, a2, a3, a1, a2, a3, a4, a5);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  for ( i = 0; i < a5; ++i )
  {
    v12 = 32LL * i;
    v13 = *(_DWORD *)(v12 + a4 + 4);
    if ( v13 == 55 )
    {
      if ( !*(_DWORD *)(v12 + a4 + 8) )
      {
        if ( v9 )
          goto LABEL_16;
        v9 = *(_DWORD *)(v12 + a4 + 24);
        if ( !v9 )
          goto LABEL_16;
        v7 = *(_QWORD *)(v12 + a4 + 16);
      }
    }
    else if ( !v13 && *(_DWORD *)(v12 + a4 + 8) )
    {
      if ( v10 )
        goto LABEL_16;
      v10 = *(_DWORD *)(v12 + a4 + 24);
      if ( !v10 )
        goto LABEL_16;
      v8 = *(_QWORD *)(v12 + a4 + 16);
    }
  }
  if ( !(v9 + v10) )
  {
LABEL_16:
    Pointer = 87;
    goto LABEL_24;
  }
  GetCurrentProcessId();
  LODWORD(v25) = v9;
  *((_QWORD *)&v25 + 1) = v7;
  LODWORD(v26) = v10;
  *((_QWORD *)&v26 + 1) = v8;
  LODWORD(v24) = a3;
  *((_QWORD *)&v23 + 1) = a2;
  if ( a1 )
  {
    Pointer = DhcpAdapterNameToIfId(a1, &v21);
    if ( Pointer )
    {
LABEL_24:
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
        WPP_SF_SD(1028, 82, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
      return Pointer;
    }
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(v16, 80, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
  }
  v22.Simple = 0;
  v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xEu, 0).Pointer;
  Pointer = (unsigned int)v17.Pointer;
  v22.Pointer = v17.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v18 = GetCommandLineW();
    WPP_SF_DSS(v19, 81, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v18);
    goto LABEL_24;
  }
  return Pointer;
}

```

## disassembly

```asm
0x180008dd4  mov     r11, rsp
0x180008dd7  mov     [r11+18h], r8d
0x180008ddb  mov     [r11+10h], rdx
0x180008ddf  mov     [r11+8], rcx
0x180008de3  push    rbx
0x180008de4  push    rsi
0x180008de5  push    rdi
0x180008de6  push    r12
0x180008de8  push    r13
0x180008dea  push    r14
0x180008dec  push    r15
0x180008dee  sub     rsp, 0B0h
0x180008df5  mov     rbx, r9
0x180008df8  mov     rdi, rcx
0x180008dfb  xorps   xmm0, xmm0
0x180008dfe  movups  xmmword ptr [r11-58h], xmm0
0x180008e03  movups  xmmword ptr [r11-48h], xmm0
0x180008e08  xorps   xmm1, xmm1
0x180008e0b  xor     eax, eax
0x180008e0d  movups  [rsp+0E8h+var_70], xmm1
0x180008e12  mov     [r11-60h], rax
0x180008e16  xor     r13d, r13d
0x180008e19  mov     [r11-80h], r13
0x180008e1d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008e24  jz      short loc_180008E60
0x180008e26  mov     rax, [rsp+0E8h+arg_38]
0x180008e2e  mov     [rsp+0E8h+var_98], rax
0x180008e33  mov     eax, [rsp+0E8h+arg_30]
0x180008e3a  mov     dword ptr [rsp+0E8h+var_A0], eax
0x180008e3e  mov     eax, [rsp+0E8h+arg_20]
0x180008e45  mov     [rsp+0E8h+var_B0], eax
0x180008e49  mov     [rsp+0E8h+var_B8], rbx
0x180008e4e  mov     dword ptr [rsp+0E8h+var_C0], r8d
0x180008e53  mov     [rsp+0E8h+var_C8], rdx
0x180008e58  mov     r9, rcx
0x180008e5b  call    WPP_SF_SqdqdLdq
0x180008e60  mov     r15, r13
0x180008e63  mov     r12, r13
0x180008e66  mov     esi, r13d
0x180008e69  mov     r14d, r13d
0x180008e6c  mov     ecx, r13d
0x180008e6f  cmp     ecx, [rsp+0E8h+arg_20]
0x180008e76  jnb     short loc_180008ECE
0x180008e78  mov     eax, ecx
0x180008e7a  shl     rax, 5
0x180008e7e  mov     edx, [rax+rbx+4]
0x180008e82  cmp     edx, 37h ; '7'
0x180008e85  jnz     short loc_180008EA1
0x180008e87  cmp     [rax+rbx+8], r13d
0x180008e8c  jnz     short loc_180008EC0
0x180008e8e  test    esi, esi
0x180008e90  jnz     short loc_180008EC4
0x180008e92  mov     esi, [rax+rbx+18h]
0x180008e96  test    esi, esi
0x180008e98  jz      short loc_180008EC4
0x180008e9a  mov     r15, [rax+rbx+10h]
0x180008e9f  jmp     short loc_180008EC0
0x180008ea1  test    edx, edx
0x180008ea3  jnz     short loc_180008EC0
0x180008ea5  cmp     [rax+rbx+8], r13d
0x180008eaa  jz      short loc_180008EC0
0x180008eac  test    r14d, r14d
0x180008eaf  jnz     short loc_180008EC4
0x180008eb1  mov     r14d, [rax+rbx+18h]
0x180008eb6  test    r14d, r14d
0x180008eb9  jz      short loc_180008EC4
0x180008ebb  mov     r12, [rax+rbx+10h]
0x180008ec0  inc     ecx
0x180008ec2  jmp     short loc_180008E6F
0x180008ec4  mov     ebx, 57h ; 'W'
0x180008ec9  jmp     loc_18000901D
0x180008ece  lea     eax, [rsi+r14]
0x180008ed2  test    eax, eax
0x180008ed4  jz      short loc_180008EC4
0x180008ed6  mov     rbx, r13
0x180008ed9  call    cs:__imp_GetCurrentProcessId
0x180008edf  mov     r13d, eax
0x180008ee2  mov     [rsp+0E8h+var_58], esi
0x180008ee9  mov     [rsp+0E8h+var_50], r15
0x180008ef1  mov     [rsp+0E8h+var_48], r14d
0x180008ef9  mov     [rsp+0E8h+var_40], r12
0x180008f01  mov     eax, [rsp+0E8h+arg_10]
0x180008f08  mov     dword ptr [rsp+0E8h+var_60], eax
0x180008f0f  mov     rax, [rsp+0E8h+arg_8]
0x180008f17  mov     qword ptr [rsp+0E8h+var_70+8], rax
0x180008f1f  test    rdi, rdi
0x180008f22  jz      short loc_180008F40
0x180008f24  lea     rdx, [rsp+0E8h+var_80]
0x180008f29  mov     rcx, rdi
0x180008f2c  call    DhcpAdapterNameToIfId
0x180008f31  mov     ebx, eax
0x180008f33  test    eax, eax
0x180008f35  jnz     loc_18000901D
0x180008f3b  lea     rbx, [rsp+0E8h+var_80]
0x180008f40  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008f47  jz      short loc_180008F69
0x180008f49  call    cs:__imp_GetCommandLineW
0x180008f4f  mov     edx, 50h ; 'P'
0x180008f54  mov     [rsp+0E8h+var_C8], rax
0x180008f59  mov     r9, rdi
0x180008f5c  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008f63  call    WPP_SF_SS
0x180008f68  nop
0x180008f69  mov     [rsp+0E8h+var_78], 0
0x180008f72  mov     rax, [rsp+0E8h+arg_38]
0x180008f7a  mov     [rsp+0E8h+var_A0], rax
0x180008f7f  mov     eax, [rsp+0E8h+arg_30]
0x180008f86  mov     [rsp+0E8h+var_A8], eax
0x180008f8a  mov     [rsp+0E8h+var_B0], r13d
0x180008f8f  lea     rax, [rsp+0E8h+var_58]
0x180008f97  mov     [rsp+0E8h+var_B8], rax
0x180008f9c  lea     rax, [rsp+0E8h+var_70]
0x180008fa1  mov     [rsp+0E8h+var_C0], rax
0x180008fa6  mov     [rsp+0E8h+var_C8], rbx
0x180008fab  xor     r9d, r9d
0x180008fae  xor     r8d, r8d; pReturnValue
0x180008fb1  lea     edx, [r9+0Eh]; nProcNum
0x180008fb5  lea     rcx, pProxyInfo; pProxyInfo
0x180008fbc  call    cs:__imp_NdrClientCall3
0x180008fc2  mov     rbx, rax
0x180008fc5  mov     [rsp+0E8h+var_78], rax
0x180008fca  mov     [rsp+0E8h+var_88], eax
0x180008fce  jmp     short loc_180008FF0
0x180008fd0  mov     edi, eax
0x180008fd2  mov     ebx, eax
0x180008fd4  mov     [rsp+0E8h+var_88], eax
0x180008fd8  call    cs:__imp_GetCommandLineW
0x180008fde  mov     rdx, rax
0x180008fe1  mov     ecx, ebx
0x180008fe3  call    TraceRpcException
0x180008fe8  mov     rdi, [rsp+0E8h+arg_0]
0x180008ff0  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008ff7  jz      short loc_180009043
0x180008ff9  call    cs:__imp_GetCommandLineW
0x180008fff  mov     edx, 51h ; 'Q'
0x180009004  mov     [rsp+0E8h+var_C0], rax
0x180009009  mov     [rsp+0E8h+var_C8], rdi
0x18000900e  mov     r9d, ebx
0x180009011  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180009018  call    WPP_SF_DSS
0x18000901d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180009024  jz      short loc_180009043
0x180009026  mov     edx, 52h ; 'R'
0x18000902b  mov     ecx, 404h
0x180009030  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x180009034  mov     r9, rdi
0x180009037  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000903e  call    WPP_SF_SD
0x180009043  mov     eax, ebx
0x180009045  add     rsp, 0B0h
0x18000904c  pop     r15
0x18000904e  pop     r14
0x180009050  pop     r13
0x180009052  pop     r12
0x180009054  pop     rdi
0x180009055  pop     rsi
0x180009056  pop     rbx
0x180009057  retn
0x180010d0e  push    rbp
0x180010d10  sub     rsp, 60h
0x180010d14  mov     rbp, rdx
0x180010d17  mov     rcx, [rcx]
0x180010d1a  mov     ecx, [rcx]; ExceptionCode
0x180010d1c  call    cs:__imp_I_RpcExceptionFilter
0x180010d22  nop
0x180010d23  add     rsp, 60h
0x180010d27  pop     rbp
0x180010d28  retn
```
