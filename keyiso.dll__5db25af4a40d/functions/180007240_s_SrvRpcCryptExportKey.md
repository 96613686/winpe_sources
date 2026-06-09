# s_SrvRpcCryptExportKey

- ea: `0x180007240`
- end: `0x1800073d7`
- name: `s_SrvRpcCryptExportKey`
- size: `407`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, __int64, void *, ULONG, _DWORD *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180007240`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180007264`
- `RPCRT4!RpcImpersonateClient` at `0x180007264`
- `RPCRT4!RpcRevertToSelf` at `0x18000734a`
- `RPCRT4!RpcRevertToSelf` at `0x18000734a`

## string_xrefs

- `0x1800072fe`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007328`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007382`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800073b8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptExportKey(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        void *a8,
        ULONG a9,
        _DWORD *a10,
        int a11)
{
  unsigned int v14; // eax
  int v15; // ebx
  int v16; // r8d

  if ( a10 )
  {
    v14 = RpcImpersonateClient(a1);
    if ( v14 )
    {
      DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1312);
      return (unsigned int)-2146893792;
    }
    else
    {
      *a10 = 0;
      v15 = off_1800250A8(a2, a3, a4, a5, a6, a7, a8, a9, (__int64)a10, a11);
      if ( v15 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          v16,
          (unsigned int)"Status",
          v15,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          54);
      }
      RpcRevertToSelf();
    }
    return (unsigned int)v15;
  }
  v15 = -2146893785;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return (unsigned int)v15;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
    a3,
    (unsigned int)"Status",
    39,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
    25);
  return 2148073511LL;
}

```

## disassembly

```asm
0x180007240  push    rbx
0x180007242  push    rsi
0x180007243  push    rdi
0x180007244  push    r14
0x180007246  sub     rsp, 78h
0x18000724a  mov     rdi, r9
0x18000724d  mov     rsi, r8
0x180007250  mov     r14, rdx
0x180007253  mov     rbx, [rsp+98h+arg_48]
0x18000725b  test    rbx, rbx
0x18000725e  jz      loc_18000735C
0x180007264  call    cs:__imp_RpcImpersonateClient
0x18000726a  test    eax, eax
0x18000726c  jnz     loc_1800073B2
0x180007272  mov     [rbx], eax
0x180007274  mov     eax, [rsp+98h+arg_50]
0x18000727b  mov     [rsp+98h+var_50], eax
0x18000727f  mov     [rsp+98h+var_58], rbx
0x180007284  mov     eax, [rsp+98h+arg_40]
0x18000728b  mov     [rsp+98h+var_60], eax
0x18000728f  mov     rax, [rsp+98h+arg_38]
0x180007297  mov     [rsp+98h+var_68], rax
0x18000729c  mov     rax, [rsp+98h+arg_30]
0x1800072a4  mov     [rsp+98h+var_70], rax
0x1800072a9  mov     rax, [rsp+98h+arg_28]
0x1800072b1  mov     [rsp+98h+var_78], rax
0x1800072b6  mov     r9, [rsp+98h+arg_20]
0x1800072be  mov     r8, rdi
0x1800072c1  mov     rdx, rsi
0x1800072c4  mov     rcx, r14
0x1800072c7  mov     rax, cs:off_1800250A8
0x1800072ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d3  mov     ebx, eax
0x1800072d5  mov     [rsp+98h+var_38], eax
0x1800072d9  test    eax, eax
0x1800072db  jns     short loc_18000731E
0x1800072dd  lea     rax, WPP_GLOBAL_Control
0x1800072e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072eb  cmp     rcx, rax
0x1800072ee  jz      short loc_18000731E
0x1800072f0  test    byte ptr [rcx+1Ch], 1
0x1800072f4  jz      short loc_18000731E
0x1800072f6  mov     dword ptr [rsp+98h+var_68], 536h
0x1800072fe  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007305  mov     [rsp+98h+var_70], rdx
0x18000730a  mov     dword ptr [rsp+98h+var_78], ebx
0x18000730e  lea     r9, aStatus; "Status"
0x180007315  mov     rcx, [rcx+10h]
0x180007319  call    WPP_SF_sDsd
0x18000731e  jmp     short loc_18000734A
0x180007320  mov     ebx, eax
0x180007322  mov     r9d, 53Ch
0x180007328  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000732f  lea     rdx, aNtstatus; "ntStatus"
0x180007336  mov     ecx, eax
0x180007338  call    DebugTraceError
0x18000733d  mov     ecx, ebx
0x18000733f  call    NormalizeNteStatus
0x180007344  mov     ebx, eax
0x180007346  mov     [rsp+98h+var_38], eax
0x18000734a  call    cs:__imp_RpcRevertToSelf
0x180007350  mov     eax, ebx
0x180007352  add     rsp, 78h
0x180007356  pop     r14
0x180007358  pop     rdi
0x180007359  pop     rsi
0x18000735a  pop     rbx
0x18000735b  retn
0x18000735c  mov     ebx, 80090027h
0x180007361  lea     rax, WPP_GLOBAL_Control
0x180007368  mov     rcx, cs:WPP_GLOBAL_Control
0x18000736f  cmp     rcx, rax
0x180007372  jz      short loc_180007350
0x180007374  test    byte ptr [rcx+1Ch], 1
0x180007378  jz      short loc_180007350
0x18000737a  mov     dword ptr [rsp+98h+var_68], 519h
0x180007382  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007389  mov     [rsp+98h+var_70], rdx
0x18000738e  mov     dword ptr [rsp+98h+var_78], 80090027h
0x180007396  lea     r9, aStatus; "Status"
0x18000739d  mov     rcx, [rcx+10h]
0x1800073a1  call    WPP_SF_sDsd
0x1800073a6  mov     eax, ebx
0x1800073a8  add     rsp, 78h
0x1800073ac  pop     r14
0x1800073ae  pop     rdi
0x1800073af  pop     rsi
0x1800073b0  pop     rbx
0x1800073b1  retn
0x1800073b2  mov     r9d, 520h
0x1800073b8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800073bf  lea     rdx, aStatus; "Status"
0x1800073c6  mov     ecx, eax
0x1800073c8  call    DebugTraceError
0x1800073cd  mov     ebx, 80090020h
0x1800073d2  jmp     loc_180007350
```
