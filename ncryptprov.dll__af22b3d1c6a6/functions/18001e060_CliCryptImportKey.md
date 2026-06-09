# CliCryptImportKey

- ea: `0x18001e060`
- end: `0x18001e2a1`
- name: `CliCryptImportKey`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000e9c8`
- `0x18001e060`
- `0x180024f60`
- `0x180060f5c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001e097`
- `ntdll!RtlAllocateHeap` at `0x18001e097`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800627b8`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800627b8`
- `RPCRT4!NdrClientCall3` at `0x18001e141`
- `RPCRT4!NdrClientCall3` at `0x18001e141`

## string_xrefs

- `0x18001e166`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18001e1a1`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18001e220`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18001e26a`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptImportKey(
        __int64 *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        int a7,
        int a8)
{
  __int64 v12; // rdi
  int v13; // edx
  PVOID Heap; // rsi
  __int64 v15; // r8
  __int64 v16; // rdx
  int Pointer; // eax
  int v18; // ebx

  v12 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8u);
  if ( Heap )
  {
    if ( !a4 || (v12 = MapBufferDescToRPC(a4)) != 0 )
    {
      if ( a2 )
        v15 = *a2;
      else
        v15 = 0;
      if ( a1 )
        v16 = *a1;
      else
        v16 = 0;
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x12u,
                                0,
                                g_RpcBindingContext,
                                qword_18007A5E0,
                                v16,
                                v15,
                                a3,
                                v12,
                                Heap,
                                a6,
                                a7,
                                a8).Pointer;
      v18 = Pointer;
      if ( Pointer < 0 )
        DebugTraceError(
          (unsigned int)Pointer,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
          2171);
      if ( v18 >= 0 )
      {
        *a5 = Heap;
        Heap = 0;
      }
    }
    else
    {
      v18 = -1073741801;
      DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 2152);
    }
  }
  else
  {
    v18 = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        94);
  }
  if ( v12 )
    FreeRPCBufferDesc(v12);
  if ( Heap )
    MSCryptFree(Heap);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18001e060  push    rbx
0x18001e062  push    rsi
0x18001e063  push    rdi
0x18001e064  push    r12
0x18001e066  push    r14
0x18001e068  push    r15
0x18001e06a  sub     rsp, 98h
0x18001e071  mov     rbx, r9
0x18001e074  mov     r12, r8
0x18001e077  mov     r14, rdx
0x18001e07a  mov     r15, rcx
0x18001e07d  xor     edi, edi
0x18001e07f  mov     [rsp+0C8h+var_50], rdi
0x18001e084  mov     rcx, gs:60h
0x18001e08d  xor     edx, edx; Flags
0x18001e08f  lea     r8d, [rdi+8]; Size
0x18001e093  mov     rcx, [rcx+30h]; HeapHandle
0x18001e097  call    cs:__imp_RtlAllocateHeap
0x18001e09e  nop     dword ptr [rax+rax+00h]
0x18001e0a3  mov     rsi, rax
0x18001e0a6  mov     [rsp+0C8h+var_40], rax
0x18001e0ae  test    rax, rax
0x18001e0b1  jz      loc_18001E1FA
0x18001e0b7  test    rbx, rbx
0x18001e0ba  jnz     loc_18001E246
0x18001e0c0  test    r14, r14
0x18001e0c3  jnz     loc_18001E184
0x18001e0c9  xor     r8d, r8d
0x18001e0cc  test    r15, r15
0x18001e0cf  jz      loc_18001E17D
0x18001e0d5  mov     rdx, [r15]
0x18001e0d8  mov     rcx, cs:qword_18007A5E0
0x18001e0df  mov     [rsp+0C8h+var_48], 0
0x18001e0eb  mov     eax, [rsp+0C8h+arg_38]
0x18001e0f2  mov     [rsp+0C8h+var_68], eax
0x18001e0f6  mov     eax, [rsp+0C8h+arg_30]
0x18001e0fd  mov     [rsp+0C8h+var_70], eax
0x18001e101  mov     rax, [rsp+0C8h+arg_28]
0x18001e109  mov     [rsp+0C8h+var_78], rax
0x18001e10e  mov     [rsp+0C8h+var_80], rsi
0x18001e113  mov     [rsp+0C8h+var_88], rdi
0x18001e118  mov     [rsp+0C8h+var_90], r12
0x18001e11d  mov     [rsp+0C8h+var_98], r8
0x18001e122  mov     [rsp+0C8h+var_A0], rdx
0x18001e127  mov     [rsp+0C8h+var_A8], rcx
0x18001e12c  mov     r9, cs:g_RpcBindingContext
0x18001e133  xor     r8d, r8d; pReturnValue
0x18001e136  lea     edx, [r8+12h]; nProcNum
0x18001e13a  lea     rcx, pProxyInfo; pProxyInfo
0x18001e141  call    cs:__imp_NdrClientCall3
0x18001e148  nop     dword ptr [rax+rax+00h]
0x18001e14d  mov     rbx, rax
0x18001e150  mov     [rsp+0C8h+var_48], rax
0x18001e158  mov     [rsp+0C8h+var_58], eax
0x18001e15c  test    eax, eax
0x18001e15e  jns     short loc_18001E18C
0x18001e160  mov     r9d, 87Bh
0x18001e166  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e16d  lea     rdx, aStatus; "Status"
0x18001e174  mov     ecx, eax
0x18001e176  call    DebugTraceError
0x18001e17b  jmp     short loc_18001E18C
0x18001e17d  xor     edx, edx
0x18001e17f  jmp     loc_18001E0D8
0x18001e184  mov     r8, [r14]
0x18001e187  jmp     loc_18001E0CC
0x18001e18c  jmp     short loc_18001E1C3
0x18001e18e  mov     ecx, eax
0x18001e190  call    HResultFromRpcException
0x18001e195  mov     ebx, eax
0x18001e197  mov     [rsp+0C8h+var_58], eax
0x18001e19b  mov     r9d, 87Fh
0x18001e1a1  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e1a8  lea     rdx, aStatus; "Status"
0x18001e1af  mov     ecx, eax
0x18001e1b1  call    DebugTraceError
0x18001e1b6  mov     rsi, [rsp+0C8h+var_40]
0x18001e1be  mov     rdi, [rsp+0C8h+var_50]
0x18001e1c3  test    ebx, ebx
0x18001e1c5  js      short loc_18001E1D4
0x18001e1c7  mov     rax, [rsp+0C8h+arg_20]
0x18001e1cf  mov     [rax], rsi
0x18001e1d2  xor     esi, esi
0x18001e1d4  test    rdi, rdi
0x18001e1d7  jnz     loc_18001E287
0x18001e1dd  test    rsi, rsi
0x18001e1e0  jnz     loc_18001E294
0x18001e1e6  mov     eax, ebx
0x18001e1e8  add     rsp, 98h
0x18001e1ef  pop     r15
0x18001e1f1  pop     r14
0x18001e1f3  pop     r12
0x18001e1f5  pop     rdi
0x18001e1f6  pop     rsi
0x18001e1f7  pop     rbx
0x18001e1f8  retn
0x18001e1fa  mov     ebx, 8009000Eh
0x18001e1ff  lea     rax, WPP_GLOBAL_Control
0x18001e206  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e20d  cmp     rcx, rax
0x18001e210  jz      short loc_18001E1D4
0x18001e212  test    byte ptr [rcx+1Ch], 1
0x18001e216  jz      short loc_18001E1D4
0x18001e218  mov     dword ptr [rsp+0C8h+var_98], 85Eh
0x18001e220  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e227  mov     [rsp+0C8h+var_A0], r8
0x18001e22c  mov     dword ptr [rsp+0C8h+var_A8], 8009000Eh
0x18001e234  lea     r9, aStatus; "Status"
0x18001e23b  mov     rcx, [rcx+10h]
0x18001e23f  call    WPP_SF_sDsd
0x18001e244  jmp     short loc_18001E1D4
0x18001e246  mov     rcx, rbx
0x18001e249  call    _MapBufferDescToRPC
0x18001e24e  mov     rdi, rax
0x18001e251  mov     [rsp+0C8h+var_50], rax
0x18001e256  test    rax, rax
0x18001e259  jnz     loc_18001E0C0
0x18001e25f  mov     ebx, 0C0000017h
0x18001e264  mov     r9d, 868h
0x18001e26a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e271  lea     rdx, aStatus; "Status"
0x18001e278  mov     ecx, 0C0000017h
0x18001e27d  call    DebugTraceError
0x18001e282  jmp     loc_18001E1D4
0x18001e287  mov     rcx, rdi
0x18001e28a  call    _FreeRPCBufferDesc
0x18001e28f  jmp     loc_18001E1DD
0x18001e294  mov     rcx, rsi
0x18001e297  call    MSCryptFree
0x18001e29c  jmp     loc_18001E1E6
0x1800627aa  push    rbp
0x1800627ac  sub     rsp, 70h
0x1800627b0  mov     rbp, rdx
0x1800627b3  mov     rcx, [rcx]
0x1800627b6  mov     ecx, [rcx]; ExceptionCode
0x1800627b8  call    cs:__imp_I_RpcExceptionFilter
0x1800627bf  nop     dword ptr [rax+rax+00h]
0x1800627c4  nop
0x1800627c5  add     rsp, 70h
0x1800627c9  pop     rbp
0x1800627ca  retn
```
