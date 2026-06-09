# CliCryptExportKey

- ea: `0x18000e610`
- end: `0x18000e9c0`
- name: `CliCryptExportKey`
- size: `944`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, int, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000def0`
- `0x18000e610`
- `0x18000e9c8`
- `0x180024f60`
- `0x1800398b0`
- `0x180060f5c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000e82f`
- `ntdll!RtlFreeHeap` at `0x18000e82f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006252e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006252e`
- `RPCRT4!NdrClientCall3` at `0x18000e71c`
- `RPCRT4!NdrClientCall3` at `0x18000e71c`
- `CRYPTBASE!SystemFunction041` at `0x18000e963`
- `CRYPTBASE!SystemFunction041` at `0x18000e963`

## string_xrefs

- `0x18000e76e`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18000e7b5`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18000e8a0`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18000e91f`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18000e994`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptExportKey(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        void *a6,
        int a7,
        unsigned int *a8,
        int a9)
{
  __int64 v13; // rdx
  ULONG v14; // edi
  int v15; // ecx
  void *v16; // rdx
  __int64 v17; // r10
  __int64 v18; // r9
  __int64 v19; // r8
  int Pointer; // eax
  int v21; // edx
  unsigned int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rcx
  _BYTE *v25; // rax
  NTSTATUS v27; // eax
  ULONG v28; // [rsp+70h] [rbp-58h]
  __int64 v29; // [rsp+78h] [rbp-50h]
  PVOID P; // [rsp+80h] [rbp-48h]

  v29 = 0;
  v13 = 0;
  P = 0;
  v14 = 0;
  v28 = 0;
  if ( !a5 )
    goto LABEL_2;
  v23 = MapBufferDescToRPC(a5);
  v29 = v23;
  if ( v23 )
  {
    v13 = 0;
LABEL_2:
    if ( a7 )
    {
      v14 = (a7 + 15) & 0xFFFFFFF0;
      v28 = v14;
      v13 = SafeAllocaAllocateFromHeap(v14);
      P = (PVOID)v13;
      if ( !v13 )
      {
        v22 = -1073741801;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)WPP_GLOBAL_Control,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
            (unsigned int)"Status",
            23,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
            115);
        goto LABEL_22;
      }
    }
    v15 = a7;
    if ( v13 )
      v15 = v14;
    v16 = a6;
    if ( P )
      v16 = P;
    if ( a3 )
      v17 = *a3;
    else
      v17 = 0;
    if ( a2 )
      v18 = *a2;
    else
      v18 = 0;
    if ( a1 )
      v19 = *a1;
    else
      v19 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x13u,
                              0,
                              g_RpcBindingContext,
                              qword_18007A5E0,
                              v19,
                              v18,
                              v17,
                              a4,
                              v29,
                              v16,
                              v15,
                              a8,
                              a9,
                              v28).Pointer;
    v22 = Pointer;
    if ( Pointer >= 0 )
    {
      if ( a7 && !Pointer )
      {
        v27 = SystemFunction041(P, v14, 2u);
        if ( v27 < 0 )
        {
          DebugTraceError(
            (unsigned int)v27,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
            1694);
          v22 = -2146893779;
        }
        else
        {
          memcpy_0(a6, P, *a8);
        }
      }
      goto LABEL_22;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        (unsigned int)"Status",
        Pointer,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        135);
    v23 = v29;
    goto LABEL_23;
  }
  v22 = -1073741801;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)WPP_GLOBAL_Control,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
      (unsigned int)"Status",
      23,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
      99);
LABEL_22:
    v23 = v29;
  }
LABEL_23:
  if ( P )
  {
    v24 = v14;
    v25 = P;
    if ( v14 )
    {
      do
      {
        *v25++ = 0;
        --v24;
      }
      while ( v24 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    v23 = v29;
  }
  if ( v23 )
    FreeRPCBufferDesc(v23);
  return v22;
}

```

## disassembly

```asm
0x18000e610  push    rbx
0x18000e612  push    rsi
0x18000e613  push    rdi
0x18000e614  push    r12
0x18000e616  push    r13
0x18000e618  push    r14
0x18000e61a  push    r15
0x18000e61c  sub     rsp, 90h
0x18000e623  mov     r12, r9
0x18000e626  mov     r15, r8
0x18000e629  mov     rbx, rdx
0x18000e62c  mov     rsi, rcx
0x18000e62f  xor     eax, eax
0x18000e631  mov     [rsp+0C8h+var_50], rax
0x18000e636  xor     edx, edx
0x18000e638  mov     [rsp+0C8h+P], rdx
0x18000e640  xor     edi, edi
0x18000e642  mov     [rsp+0C8h+var_58], edi
0x18000e646  mov     rcx, [rsp+0C8h+arg_20]
0x18000e64e  test    rcx, rcx
0x18000e651  jnz     loc_18000E85F
0x18000e657  mov     r14d, [rsp+0C8h+arg_30]
0x18000e65f  test    r14d, r14d
0x18000e662  jnz     loc_18000E8C9
0x18000e668  mov     ecx, r14d
0x18000e66b  test    rdx, rdx
0x18000e66e  cmovnz  ecx, edi
0x18000e671  mov     r13, [rsp+0C8h+arg_28]
0x18000e679  mov     rdx, r13
0x18000e67c  mov     rax, [rsp+0C8h+P]
0x18000e684  test    rax, rax
0x18000e687  cmovnz  rdx, rax
0x18000e68b  test    r15, r15
0x18000e68e  jnz     loc_18000E790
0x18000e694  xor     r10d, r10d
0x18000e697  test    rbx, rbx
0x18000e69a  jz      loc_18000E75E
0x18000e6a0  mov     r9, [rbx]
0x18000e6a3  test    rsi, rsi
0x18000e6a6  jz      loc_18000E798
0x18000e6ac  mov     r8, [rsi]
0x18000e6af  mov     [rsp+0C8h+arg_20], 0
0x18000e6bb  mov     eax, [rsp+0C8h+arg_40]
0x18000e6c2  mov     [rsp+0C8h+var_60], eax
0x18000e6c6  mov     rsi, [rsp+0C8h+arg_38]
0x18000e6ce  mov     [rsp+0C8h+var_68], rsi
0x18000e6d3  mov     [rsp+0C8h+var_70], ecx
0x18000e6d7  mov     [rsp+0C8h+var_78], rdx
0x18000e6dc  mov     rax, [rsp+0C8h+var_50]
0x18000e6e1  mov     [rsp+0C8h+var_80], rax
0x18000e6e6  mov     [rsp+0C8h+var_88], r12
0x18000e6eb  mov     [rsp+0C8h+var_90], r10
0x18000e6f0  mov     [rsp+0C8h+var_98], r9
0x18000e6f5  mov     [rsp+0C8h+var_A0], r8
0x18000e6fa  mov     rax, cs:qword_18007A5E0
0x18000e701  mov     [rsp+0C8h+var_A8], rax
0x18000e706  mov     r9, cs:g_RpcBindingContext
0x18000e70d  xor     r8d, r8d; pReturnValue
0x18000e710  mov     edx, 13h; nProcNum
0x18000e715  lea     rcx, pProxyInfo; pProxyInfo
0x18000e71c  call    cs:__imp_NdrClientCall3
0x18000e723  nop     dword ptr [rax+rax+00h]
0x18000e728  mov     rbx, rax
0x18000e72b  mov     [rsp+0C8h+arg_20], rax
0x18000e733  mov     [rsp+0C8h+var_54], ebx
0x18000e737  test    eax, eax
0x18000e739  jns     short loc_18000E7A0
0x18000e73b  lea     rcx, WPP_GLOBAL_Control
0x18000e742  mov     rax, cs:WPP_GLOBAL_Control
0x18000e749  cmp     rax, rcx
0x18000e74c  jz      short loc_18000E754
0x18000e74e  test    byte ptr [rax+1Ch], 1
0x18000e752  jnz     short loc_18000E766
0x18000e754  mov     rax, [rsp+0C8h+var_50]
0x18000e759  jmp     loc_18000E7F4
0x18000e75e  xor     r9d, r9d
0x18000e761  jmp     loc_18000E6A3
0x18000e766  mov     dword ptr [rsp+0C8h+var_98], 687h
0x18000e76e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e775  mov     [rsp+0C8h+var_A0], r8
0x18000e77a  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x18000e77e  lea     r9, aStatus; "Status"
0x18000e785  mov     rcx, [rax+10h]
0x18000e789  call    WPP_SF_sDsd
0x18000e78e  jmp     short loc_18000E754
0x18000e790  mov     r10, [r15]
0x18000e793  jmp     loc_18000E697
0x18000e798  xor     r8d, r8d
0x18000e79b  jmp     loc_18000E6AF
0x18000e7a0  jmp     short loc_18000E7E6
0x18000e7a2  mov     ecx, eax
0x18000e7a4  call    HResultFromRpcException
0x18000e7a9  mov     ebx, eax
0x18000e7ab  mov     [rsp+0C8h+var_54], eax
0x18000e7af  mov     r9d, 68Ch
0x18000e7b5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e7bc  lea     rdx, aStatus; "Status"
0x18000e7c3  mov     ecx, eax
0x18000e7c5  call    DebugTraceError
0x18000e7ca  mov     rsi, [rsp+0C8h+arg_38]
0x18000e7d2  mov     r14d, [rsp+0C8h+arg_30]
0x18000e7da  mov     r13, [rsp+0C8h+arg_28]
0x18000e7e2  mov     edi, [rsp+0C8h+var_58]
0x18000e7e6  test    r14d, r14d
0x18000e7e9  jnz     loc_18000E948
0x18000e7ef  mov     rax, [rsp+0C8h+var_50]
0x18000e7f4  mov     rdx, [rsp+0C8h+P]
0x18000e7fc  test    rdx, rdx
0x18000e7ff  jz      short loc_18000E840
0x18000e801  mov     ecx, edi
0x18000e803  mov     rax, rdx
0x18000e806  test    edi, edi
0x18000e808  jz      short loc_18000E81D
0x18000e80a  nop     word ptr [rax+rax+00h]
0x18000e810  mov     byte ptr [rax], 0
0x18000e813  lea     rax, [rax+1]
0x18000e817  sub     rcx, 1
0x18000e81b  jnz     short loc_18000E810
0x18000e81d  mov     rcx, gs:60h
0x18000e826  mov     r8, rdx; P
0x18000e829  xor     edx, edx; Flags
0x18000e82b  mov     rcx, [rcx+30h]; HeapHandle
0x18000e82f  call    cs:__imp_RtlFreeHeap
0x18000e836  nop     dword ptr [rax+rax+00h]
0x18000e83b  mov     rax, [rsp+0C8h+var_50]
0x18000e840  test    rax, rax
0x18000e843  jnz     loc_18000E9B3
0x18000e849  mov     eax, ebx
0x18000e84b  add     rsp, 90h
0x18000e852  pop     r15
0x18000e854  pop     r14
0x18000e856  pop     r13
0x18000e858  pop     r12
0x18000e85a  pop     rdi
0x18000e85b  pop     rsi
0x18000e85c  pop     rbx
0x18000e85d  retn
0x18000e85f  call    _MapBufferDescToRPC
0x18000e864  mov     [rsp+0C8h+var_50], rax
0x18000e869  test    rax, rax
0x18000e86c  jnz     loc_18000E986
0x18000e872  mov     ebx, 0C0000017h
0x18000e877  lea     rcx, WPP_GLOBAL_Control
0x18000e87e  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e885  cmp     rdx, rcx
0x18000e888  jz      loc_18000E7F4
0x18000e88e  test    byte ptr [rdx+1Ch], 1
0x18000e892  jz      loc_18000E7F4
0x18000e898  mov     dword ptr [rsp+0C8h+var_98], 663h
0x18000e8a0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e8a7  mov     [rsp+0C8h+var_A0], r8
0x18000e8ac  mov     dword ptr [rsp+0C8h+var_A8], 0C0000017h
0x18000e8b4  lea     r9, aStatus; "Status"
0x18000e8bb  mov     rcx, [rdx+10h]
0x18000e8bf  call    WPP_SF_sDsd
0x18000e8c4  jmp     loc_18000E7EF
0x18000e8c9  lea     eax, [r14+0Fh]
0x18000e8cd  and     eax, 0FFFFFFF0h
0x18000e8d0  mov     edi, eax
0x18000e8d2  mov     [rsp+0C8h+var_58], edi
0x18000e8d6  mov     ecx, eax
0x18000e8d8  call    SafeAllocaAllocateFromHeap
0x18000e8dd  mov     rdx, rax
0x18000e8e0  mov     [rsp+0C8h+P], rax
0x18000e8e8  test    rax, rax
0x18000e8eb  jnz     loc_18000E668
0x18000e8f1  mov     ebx, 0C0000017h
0x18000e8f6  lea     rcx, WPP_GLOBAL_Control
0x18000e8fd  mov     rdx, cs:WPP_GLOBAL_Control
0x18000e904  cmp     rdx, rcx
0x18000e907  jz      loc_18000E7EF
0x18000e90d  test    byte ptr [rdx+1Ch], 1
0x18000e911  jz      loc_18000E7EF
0x18000e917  mov     dword ptr [rsp+0C8h+var_98], 673h
0x18000e91f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e926  mov     [rsp+0C8h+var_A0], r8
0x18000e92b  mov     dword ptr [rsp+0C8h+var_A8], 0C0000017h
0x18000e933  lea     r9, aStatus; "Status"
0x18000e93a  mov     rcx, [rdx+10h]
0x18000e93e  call    WPP_SF_sDsd
0x18000e943  jmp     loc_18000E7EF
0x18000e948  test    ebx, ebx
0x18000e94a  jnz     loc_18000E7EF
0x18000e950  mov     r8d, 2; OptionFlags
0x18000e956  mov     edx, edi; MemorySize
0x18000e958  mov     r14, [rsp+0C8h+P]
0x18000e960  mov     rcx, r14; Memory
0x18000e963  call    cs:__imp_SystemFunction041
0x18000e96a  nop     dword ptr [rax+rax+00h]
0x18000e96f  test    eax, eax
0x18000e971  js      short loc_18000E98E
0x18000e973  mov     r8d, [rsi]; Size
0x18000e976  mov     rdx, r14; Src
0x18000e979  mov     rcx, r13; void *
0x18000e97c  call    memcpy_0
0x18000e981  jmp     loc_18000E7EF
0x18000e986  mov     rdx, rdi
0x18000e989  jmp     loc_18000E657
0x18000e98e  mov     r9d, 69Eh
0x18000e994  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e99b  lea     rdx, aNtstatus; "ntStatus"
0x18000e9a2  mov     ecx, eax
0x18000e9a4  call    DebugTraceError
0x18000e9a9  mov     ebx, 8009002Dh
0x18000e9ae  jmp     loc_18000E7EF
0x18000e9b3  mov     rcx, rax
0x18000e9b6  call    _FreeRPCBufferDesc
0x18000e9bb  jmp     loc_18000E849
0x180062520  push    rbp
0x180062522  sub     rsp, 70h
0x180062526  mov     rbp, rdx
0x180062529  mov     rcx, [rcx]
0x18006252c  mov     ecx, [rcx]; ExceptionCode
0x18006252e  call    cs:__imp_I_RpcExceptionFilter
0x180062535  nop     dword ptr [rax+rax+00h]
0x18006253a  nop
0x18006253b  add     rsp, 70h
0x18006253f  pop     rbp
0x180062540  retn
```
