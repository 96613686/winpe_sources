# CliCryptVerifyClaim

- ea: `0x180044f50`
- end: `0x180045150`
- name: `CliCryptVerifyClaim`
- size: `512`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000e9c8`
- `0x180024f60`
- `0x180044f50`
- `0x180045a14`
- `0x180060f5c`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180062c1e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062c1e`
- `RPCRT4!NdrClientCall3` at `0x180045041`
- `RPCRT4!NdrClientCall3` at `0x180045041`

## string_xrefs

- `0x180045066`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180045090`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x1800450ce`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptVerifyClaim(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9)
{
  __int64 v13; // rdi
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // rdx
  int Pointer; // eax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  unsigned int v21; // edi
  unsigned int i; // edx
  _OWORD v24[3]; // [rsp+80h] [rbp-38h] BYREF

  v13 = 0;
  v24[0] = 0;
  if ( a5 )
  {
    v13 = MapBufferDescToRPC(a5);
    if ( !v13 )
    {
      v14 = 3288;
LABEL_17:
      v19 = -1073741801;
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", v14);
      goto LABEL_18;
    }
  }
  if ( a3 )
    v15 = *a3;
  else
    v15 = 0;
  if ( a2 )
    v16 = *a2;
  else
    v16 = 0;
  if ( a1 )
    v17 = *a1;
  else
    v17 = 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x1Fu,
                            0,
                            g_RpcBindingContext,
                            qword_18007A5E0,
                            v17,
                            v16,
                            v15,
                            a4,
                            v13,
                            a6,
                            a7,
                            v24,
                            a9).Pointer;
  v19 = Pointer;
  if ( Pointer < 0 )
    DebugTraceError(
      (unsigned int)Pointer,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
      3308);
  if ( !(unsigned int)MapRPCToBufferDesc(v24, a8) )
  {
    v14 = 3318;
    goto LABEL_17;
  }
LABEL_18:
  if ( v13 )
    FreeRPCBufferDesc(v13);
  v20 = *((_QWORD *)&v24[0] + 1);
  if ( *((_QWORD *)&v24[0] + 1) )
  {
    v21 = 0;
    for ( i = DWORD1(v24[0]); v21 < i; ++v21 )
    {
      if ( *(_QWORD *)(v20 + 16LL * v21 + 8) )
      {
        MSCryptFree(*(_QWORD *)(v20 + 16LL * v21 + 8));
        v20 = *((_QWORD *)&v24[0] + 1);
        i = DWORD1(v24[0]);
      }
    }
    MSCryptFree(v20);
  }
  return v19;
}

```

## disassembly

```asm
0x180044f50  mov     rax, rsp
0x180044f53  push    rbx
0x180044f54  push    rsi
0x180044f55  push    rdi
0x180044f56  push    r14
0x180044f58  push    r15
0x180044f5a  sub     rsp, 90h
0x180044f61  mov     r15d, r9d
0x180044f64  mov     rbx, r8
0x180044f67  mov     rsi, rdx
0x180044f6a  mov     r14, rcx
0x180044f6d  xor     edi, edi
0x180044f6f  mov     [rsp+0B8h+var_40], rdi
0x180044f74  xorps   xmm0, xmm0
0x180044f77  movups  xmmword ptr [rax-38h], xmm0
0x180044f7b  mov     rcx, [rsp+0B8h+arg_20]
0x180044f83  test    rcx, rcx
0x180044f86  jz      short loc_180044FA5
0x180044f88  call    _MapBufferDescToRPC
0x180044f8d  mov     rdi, rax
0x180044f90  mov     [rsp+0B8h+var_40], rax
0x180044f95  test    rax, rax
0x180044f98  jnz     short loc_180044FA5
0x180044f9a  mov     r9d, 0CD8h
0x180044fa0  jmp     loc_1800450C9
0x180044fa5  test    rbx, rbx
0x180044fa8  jz      short loc_180044FAF
0x180044faa  mov     r9, [rbx]
0x180044fad  jmp     short loc_180044FB2
0x180044faf  xor     r9d, r9d
0x180044fb2  test    rsi, rsi
0x180044fb5  jz      short loc_180044FBC
0x180044fb7  mov     r8, [rsi]
0x180044fba  jmp     short loc_180044FBF
0x180044fbc  xor     r8d, r8d
0x180044fbf  test    r14, r14
0x180044fc2  jz      short loc_180044FC9
0x180044fc4  mov     rdx, [r14]
0x180044fc7  jmp     short loc_180044FCB
0x180044fc9  xor     edx, edx
0x180044fcb  mov     rcx, cs:qword_18007A5E0
0x180044fd2  mov     [rsp+0B8h+arg_20], 0
0x180044fde  mov     eax, [rsp+0B8h+arg_40]
0x180044fe5  mov     [rsp+0B8h+var_50], eax
0x180044fe9  lea     rax, [rsp+0B8h+var_38]
0x180044ff1  mov     [rsp+0B8h+var_58], rax
0x180044ff6  mov     eax, [rsp+0B8h+arg_30]
0x180044ffd  mov     [rsp+0B8h+var_60], eax
0x180045001  mov     rax, [rsp+0B8h+arg_28]
0x180045009  mov     [rsp+0B8h+var_68], rax
0x18004500e  mov     [rsp+0B8h+var_70], rdi
0x180045013  mov     [rsp+0B8h+var_78], r15d
0x180045018  mov     [rsp+0B8h+var_80], r9
0x18004501d  mov     [rsp+0B8h+var_88], r8
0x180045022  mov     [rsp+0B8h+var_90], rdx
0x180045027  mov     [rsp+0B8h+var_98], rcx
0x18004502c  mov     r9, cs:g_RpcBindingContext
0x180045033  xor     r8d, r8d; pReturnValue
0x180045036  lea     edx, [r8+1Fh]; nProcNum
0x18004503a  lea     rcx, pProxyInfo; pProxyInfo
0x180045041  call    cs:__imp_NdrClientCall3
0x180045048  nop     dword ptr [rax+rax+00h]
0x18004504d  mov     rbx, rax
0x180045050  mov     [rsp+0B8h+arg_20], rax
0x180045058  mov     [rsp+0B8h+var_48], eax
0x18004505c  test    eax, eax
0x18004505e  jns     short loc_18004507B
0x180045060  mov     r9d, 0CECh
0x180045066  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004506d  lea     rdx, aStatus; "Status"
0x180045074  mov     ecx, eax
0x180045076  call    DebugTraceError
0x18004507b  jmp     short loc_1800450AA
0x18004507d  mov     ecx, eax
0x18004507f  call    HResultFromRpcException
0x180045084  mov     ebx, eax
0x180045086  mov     [rsp+0B8h+var_48], eax
0x18004508a  mov     r9d, 0CF0h
0x180045090  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045097  lea     rdx, aStatus; "Status"
0x18004509e  mov     ecx, eax
0x1800450a0  call    DebugTraceError
0x1800450a5  mov     rdi, [rsp+0B8h+var_40]
0x1800450aa  mov     rdx, [rsp+0B8h+arg_38]
0x1800450b2  lea     rcx, [rsp+0B8h+var_38]
0x1800450ba  call    _MapRPCToBufferDesc
0x1800450bf  test    eax, eax
0x1800450c1  jnz     short loc_1800450E6
0x1800450c3  mov     r9d, 0CF6h
0x1800450c9  mov     ebx, 0C0000017h
0x1800450ce  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800450d5  lea     rdx, aStatus; "Status"
0x1800450dc  mov     ecx, 0C0000017h
0x1800450e1  call    DebugTraceError
0x1800450e6  test    rdi, rdi
0x1800450e9  jz      short loc_1800450F3
0x1800450eb  mov     rcx, rdi
0x1800450ee  call    _FreeRPCBufferDesc
0x1800450f3  mov     rcx, [rsp+0B8h+var_30]
0x1800450fb  test    rcx, rcx
0x1800450fe  jz      short loc_18004513E
0x180045100  xor     edi, edi
0x180045102  mov     edx, [rsp+0B8h+var_34]
0x180045109  test    edx, edx
0x18004510b  jz      short loc_180045139
0x18004510d  mov     eax, edi
0x18004510f  add     rax, rax
0x180045112  mov     r8, [rcx+rax*8+8]
0x180045117  test    r8, r8
0x18004511a  jz      short loc_180045133
0x18004511c  mov     rcx, r8
0x18004511f  call    MSCryptFree
0x180045124  mov     rcx, [rsp+0B8h+var_30]
0x18004512c  mov     edx, [rsp+0B8h+var_34]
0x180045133  inc     edi
0x180045135  cmp     edi, edx
0x180045137  jb      short loc_18004510D
0x180045139  call    MSCryptFree
0x18004513e  mov     eax, ebx
0x180045140  add     rsp, 90h
0x180045147  pop     r15
0x180045149  pop     r14
0x18004514b  pop     rdi
0x18004514c  pop     rsi
0x18004514d  pop     rbx
0x18004514e  retn
0x180062c10  push    rbp
0x180062c12  sub     rsp, 70h
0x180062c16  mov     rbp, rdx
0x180062c19  mov     rcx, [rcx]
0x180062c1c  mov     ecx, [rcx]; ExceptionCode
0x180062c1e  call    cs:__imp_I_RpcExceptionFilter
0x180062c25  nop     dword ptr [rax+rax+00h]
0x180062c2a  nop
0x180062c2b  add     rsp, 70h
0x180062c2f  pop     rbp
0x180062c30  retn
```
