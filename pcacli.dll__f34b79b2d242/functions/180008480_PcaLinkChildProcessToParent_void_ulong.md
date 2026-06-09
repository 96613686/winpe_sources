# PcaLinkChildProcessToParent(void *,ulong)

- ea: `0x180008480`
- end: `0x1800085ce`
- name: `?PcaLinkChildProcessToParent@@YAKPEAXK@Z`
- size: `334`
- prototype: `unsigned int __fastcall(HANDLE Process, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callees

- `0x180001870`
- `0x180002180`
- `0x180002210`
- `0x180002ca0`
- `0x180002ee8`
- `0x180007738`
- `0x180008480`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000c4d6`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c4d6`
- `RPCRT4!NdrClientCall3` at `0x180008539`
- `RPCRT4!NdrClientCall3` at `0x180008539`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800084bb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800084bb`

## string_xrefs

- `0x18000855d`: `PcaClient`
- `0x1800084ef`: `Failed to create binding handle [%d]`
- `0x1800084fc`: `PcaLinkChildProcessToParent`
- `0x180008551`: `LinkChildToParent,Time,%llu`

## pseudocode

```c
__int64 __fastcall PcaLinkChildProcessToParent(HANDLE Process, int a2)
{
  unsigned __int64 v4; // r15
  unsigned int v5; // edi
  DWORD ProcessId; // eax
  unsigned int started; // ebx
  int v8; // eax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v13; // [rsp+28h] [rbp-40h]
  unsigned __int64 v14; // [rsp+38h] [rbp-30h]
  void *v15; // [rsp+88h] [rbp+20h] BYREF

  v4 = PcaTimeStart();
  v14 = v4;
  v5 = 0;
  v15 = 0;
  ProcessId = GetProcessId(Process);
  if ( (unsigned int)PcapCheckEnablePca(0, 0, ProcessId) )
  {
    v8 = PcapCreateBindingHandle(&v15);
    started = v8;
    if ( !v8 )
      goto LABEL_5;
    AslLogCallPrintf(1, "PcaLinkChildProcessToParent", 1322, "Failed to create binding handle [%d]", v8);
  }
  else
  {
    started = 0;
  }
  while ( started )
  {
    if ( v5 > 1 )
      break;
    v10 = started - 1708;
    if ( (unsigned int)v10 > 0x2D )
      break;
    v11 = 0x200000004201LL;
    if ( !_bittest64(&v11, v10) )
      break;
    started = PcacpStartPCAService();
    ++v5;
    if ( !started )
    {
LABEL_5:
      LODWORD(v13) = a2;
      NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 4u, 0, v15, Process, v13, 0, v14);
      v9 = PcaTimeStart();
      PcaTracePrintf("PcaClient", 0, 0, "LinkChildToParent,Time,%llu", v9 - v4);
    }
  }
  return started;
}

```

## disassembly

```asm
0x180008480  mov     [rsp+arg_8], edx
0x180008484  mov     [rsp+arg_0], rcx
0x180008489  push    rbx
0x18000848a  push    rsi
0x18000848b  push    rdi
0x18000848c  push    r14
0x18000848e  push    r15
0x180008490  sub     rsp, 40h
0x180008494  mov     r14d, edx
0x180008497  mov     rsi, rcx
0x18000849a  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x18000849f  mov     r15, rax
0x1800084a2  mov     [rsp+68h+var_30], rax
0x1800084a7  xor     edi, edi
0x1800084a9  mov     [rsp+68h+arg_10], edi
0x1800084b0  mov     [rsp+68h+arg_18], rdi
0x1800084b8  mov     rcx, rsi; Process
0x1800084bb  call    cs:__imp_GetProcessId
0x1800084c1  mov     r8d, eax; unsigned int
0x1800084c4  xor     edx, edx; unsigned __int16 *
0x1800084c6  xor     ecx, ecx; unsigned __int16 *
0x1800084c8  call    ?PcapCheckEnablePca@@YAHPEBG0K@Z; PcapCheckEnablePca(ushort const *,ushort const *,ulong)
0x1800084cd  test    eax, eax
0x1800084cf  jnz     short loc_1800084D8
0x1800084d1  xor     ebx, ebx
0x1800084d3  jmp     loc_180008583
0x1800084d8  lea     rcx, [rsp+68h+arg_18]; void **
0x1800084e0  call    ?PcapCreateBindingHandle@@YAKPEAPEAX@Z; PcapCreateBindingHandle(void * *)
0x1800084e5  mov     ebx, eax
0x1800084e7  test    eax, eax
0x1800084e9  jz      short loc_18000850F
0x1800084eb  mov     dword ptr [rsp+68h+var_48], eax
0x1800084ef  lea     r9, aFailedToCreate_0; "Failed to create binding handle [%d]"
0x1800084f6  mov     r8d, 52Ah
0x1800084fc  lea     rdx, aPcalinkchildpr_0; "PcaLinkChildProcessToParent"
0x180008503  mov     ecx, 1
0x180008508  call    AslLogCallPrintf
0x18000850d  jmp     short loc_180008583
0x18000850f  nop
0x180008510  mov     [rsp+68h+var_38], 0
0x180008519  mov     dword ptr [rsp+68h+var_40], r14d
0x18000851e  mov     [rsp+68h+var_48], rsi
0x180008523  mov     r9, [rsp+68h+arg_18]
0x18000852b  xor     r8d, r8d; pReturnValue
0x18000852e  lea     edx, [r8+4]; nProcNum
0x180008532  lea     rcx, pProxyInfo; pProxyInfo
0x180008539  call    cs:__imp_NdrClientCall3
0x18000853f  mov     [rsp+68h+var_38], rax
0x180008544  call    ?PcaTimeStart@@YA_KXZ; PcaTimeStart(void)
0x180008549  sub     rax, r15
0x18000854c  mov     [rsp+68h+var_48], rax
0x180008551  lea     r9, aLinkchildtopar; "LinkChildToParent,Time,%llu"
0x180008558  xor     r8d, r8d; unsigned int
0x18000855b  xor     edx, edx; unsigned int
0x18000855d  lea     rcx, aPcaclient; "PcaClient"
0x180008564  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180008569  jmp     short loc_180008583
0x18000856b  mov     ebx, eax
0x18000856d  mov     r14d, [rsp+68h+arg_8]
0x180008572  mov     rsi, [rsp+68h+arg_0]
0x180008577  mov     edi, [rsp+68h+arg_10]
0x18000857e  mov     r15, [rsp+68h+var_30]
0x180008583  test    ebx, ebx
0x180008585  jz      short loc_1800085C0
0x180008587  cmp     edi, 1
0x18000858a  ja      short loc_1800085C0
0x18000858c  lea     eax, [rbx-6ACh]
0x180008592  cmp     eax, 2Dh ; '-'
0x180008595  ja      short loc_1800085C0
0x180008597  mov     rcx, 200000004201h
0x1800085a1  bt      rcx, rax
0x1800085a5  jnb     short loc_1800085C0
0x1800085a7  call    ?PcacpStartPCAService@@YAKXZ; PcacpStartPCAService(void)
0x1800085ac  mov     ebx, eax
0x1800085ae  inc     edi
0x1800085b0  mov     [rsp+68h+arg_10], edi
0x1800085b7  test    eax, eax
0x1800085b9  jnz     short loc_180008583
0x1800085bb  jmp     loc_18000850F
0x1800085c0  mov     eax, ebx
0x1800085c2  add     rsp, 40h
0x1800085c6  pop     r15
0x1800085c8  pop     r14
0x1800085ca  pop     rdi
0x1800085cb  pop     rsi
0x1800085cc  pop     rbx
0x1800085cd  retn
0x18000c4c8  push    rbp
0x18000c4ca  sub     rsp, 30h
0x18000c4ce  mov     rbp, rdx
0x18000c4d1  mov     rcx, [rcx]
0x18000c4d4  mov     ecx, [rcx]; ExceptionCode
0x18000c4d6  call    cs:__imp_I_RpcExceptionFilter
0x18000c4dc  nop
0x18000c4dd  add     rsp, 30h
0x18000c4e1  pop     rbp
0x18000c4e2  retn
```
