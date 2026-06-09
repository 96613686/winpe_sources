# CliCryptCreatePersistedKey

- ea: `0x18001de80`
- end: `0x18001e052`
- name: `CliCryptCreatePersistedKey`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18001de80`
- `0x180060f5c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18001deba`
- `ntdll!RtlAllocateHeap` at `0x18001deba`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062790`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062790`
- `RPCRT4!NdrClientCall3` at `0x18001df37`
- `RPCRT4!NdrClientCall3` at `0x18001df37`

## string_xrefs

- `0x18001df76`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18001dfb4`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18001e022`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptCreatePersistedKey(__int64 *a1, _QWORD *a2, __int64 a3, __int64 a4, int a5, int a6)
{
  int v10; // edx
  PVOID Heap; // rdi
  int v12; // r8d
  __int64 v13; // rdx
  int Pointer; // eax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // ebx

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8u);
  if ( Heap )
  {
    if ( a1 )
      v13 = *a1;
    else
      v13 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0xAu,
                              0,
                              g_RpcBindingContext,
                              qword_18007A5E0,
                              v13,
                              Heap,
                              a3,
                              a4,
                              a5,
                              a6).Pointer;
    v17 = Pointer;
    if ( Pointer >= 0 )
    {
      *a2 = Heap;
      Heap = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v16,
        (unsigned int)"Status",
        Pointer,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        40);
    }
  }
  else
  {
    v17 = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v12,
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
        24);
  }
  if ( Heap )
    MSCryptFree(Heap);
  return v17;
}

```

## disassembly

```asm
0x18001de80  mov     [rsp+arg_0], rbx
0x18001de85  mov     [rsp+arg_10], rsi
0x18001de8a  mov     [rsp+arg_8], rdx
0x18001de8f  push    rdi
0x18001de90  push    r14
0x18001de92  push    r15
0x18001de94  sub     rsp, 80h
0x18001de9b  mov     r14, r9
0x18001de9e  mov     r15, r8
0x18001dea1  mov     rsi, rdx
0x18001dea4  mov     rbx, rcx
0x18001dea7  mov     rcx, gs:60h
0x18001deb0  xor     edx, edx; Flags
0x18001deb2  lea     r8d, [rdx+8]; Size
0x18001deb6  mov     rcx, [rcx+30h]; HeapHandle
0x18001deba  call    cs:__imp_RtlAllocateHeap
0x18001dec1  nop     dword ptr [rax+rax+00h]
0x18001dec6  mov     rdi, rax
0x18001dec9  mov     [rsp+98h+var_28], rax
0x18001dece  test    rax, rax
0x18001ded1  jz      loc_18001DFFC
0x18001ded7  test    rbx, rbx
0x18001deda  jz      loc_18001DF98
0x18001dee0  mov     rdx, [rbx]
0x18001dee3  mov     rcx, cs:qword_18007A5E0
0x18001deea  mov     [rsp+98h+var_30], 0
0x18001def3  mov     eax, [rsp+98h+arg_28]
0x18001defa  mov     [rsp+98h+var_48], eax
0x18001defe  mov     eax, [rsp+98h+arg_20]
0x18001df05  mov     [rsp+98h+var_50], eax
0x18001df09  mov     [rsp+98h+var_58], r14
0x18001df0e  mov     [rsp+98h+var_60], r15
0x18001df13  mov     [rsp+98h+var_68], rdi
0x18001df18  mov     [rsp+98h+var_70], rdx
0x18001df1d  mov     [rsp+98h+var_78], rcx
0x18001df22  mov     r9, cs:g_RpcBindingContext
0x18001df29  xor     r8d, r8d; pReturnValue
0x18001df2c  lea     edx, [r8+0Ah]; nProcNum
0x18001df30  lea     rcx, pProxyInfo; pProxyInfo
0x18001df37  call    cs:__imp_NdrClientCall3
0x18001df3e  nop     dword ptr [rax+rax+00h]
0x18001df43  mov     rbx, rax
0x18001df46  mov     [rsp+98h+var_30], rax
0x18001df4b  mov     [rsp+98h+var_38], ebx
0x18001df4f  test    eax, eax
0x18001df51  jns     short loc_18001DF9F
0x18001df53  lea     rax, WPP_GLOBAL_Control
0x18001df5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df61  cmp     rcx, rax
0x18001df64  jz      short loc_18001DF6C
0x18001df66  test    byte ptr [rcx+1Ch], 1
0x18001df6a  jnz     short loc_18001DF6E
0x18001df6c  jmp     short loc_18001DFDB
0x18001df6e  mov     dword ptr [rsp+98h+var_68], 228h
0x18001df76  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001df7d  mov     [rsp+98h+var_70], rax
0x18001df82  mov     dword ptr [rsp+98h+var_78], ebx
0x18001df86  lea     r9, aStatus; "Status"
0x18001df8d  mov     rcx, [rcx+10h]
0x18001df91  call    WPP_SF_sDsd
0x18001df96  jmp     short loc_18001DF6C
0x18001df98  xor     edx, edx
0x18001df9a  jmp     loc_18001DEE3
0x18001df9f  jmp     short loc_18001DFD6
0x18001dfa1  mov     ecx, eax
0x18001dfa3  call    HResultFromRpcException
0x18001dfa8  mov     ebx, eax
0x18001dfaa  mov     [rsp+98h+var_38], eax
0x18001dfae  mov     r9d, 22Eh
0x18001dfb4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001dfbb  lea     rdx, aStatus; "Status"
0x18001dfc2  mov     ecx, eax
0x18001dfc4  call    DebugTraceError
0x18001dfc9  mov     rsi, [rsp+98h+arg_8]
0x18001dfd1  mov     rdi, [rsp+98h+var_28]
0x18001dfd6  mov     [rsi], rdi
0x18001dfd9  xor     edi, edi
0x18001dfdb  test    rdi, rdi
0x18001dfde  jnz     short loc_18001E048
0x18001dfe0  mov     eax, ebx
0x18001dfe2  lea     r11, [rsp+98h+var_18]
0x18001dfea  mov     rbx, [r11+20h]
0x18001dfee  mov     rsi, [r11+30h]
0x18001dff2  mov     rsp, r11
0x18001dff5  pop     r15
0x18001dff7  pop     r14
0x18001dff9  pop     rdi
0x18001dffa  retn
0x18001dffc  mov     ebx, 8009000Eh
0x18001e001  lea     rax, WPP_GLOBAL_Control
0x18001e008  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e00f  cmp     rcx, rax
0x18001e012  jz      short loc_18001DFDB
0x18001e014  test    byte ptr [rcx+1Ch], 1
0x18001e018  jz      short loc_18001DFDB
0x18001e01a  mov     dword ptr [rsp+98h+var_68], 218h
0x18001e022  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e029  mov     [rsp+98h+var_70], rax
0x18001e02e  mov     dword ptr [rsp+98h+var_78], 8009000Eh
0x18001e036  lea     r9, aStatus; "Status"
0x18001e03d  mov     rcx, [rcx+10h]
0x18001e041  call    WPP_SF_sDsd
0x18001e046  jmp     short loc_18001DFDB
0x18001e048  mov     rcx, rdi
0x18001e04b  call    MSCryptFree
0x18001e050  jmp     short loc_18001DFE0
0x180062782  push    rbp
0x180062784  sub     rsp, 60h
0x180062788  mov     rbp, rdx
0x18006278b  mov     rcx, [rcx]
0x18006278e  mov     ecx, [rcx]; ExceptionCode
0x180062790  call    cs:__imp_I_RpcExceptionFilter
0x180062797  nop     dword ptr [rax+rax+00h]
0x18006279c  nop
0x18006279d  add     rsp, 60h
0x1800627a1  pop     rbp
0x1800627a2  retn
```
