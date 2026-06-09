# DafStartListenForInboundAssociations

- ea: `0x18000b150`
- end: `0x18000b31a`
- name: `DafStartListenForInboundAssociations`
- size: `458`
- prototype: `__int64 __fastcall(char *pv, int, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002f10`
- `0x18000b150`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18000c0aa`
- `RPCRT4!RpcExceptionFilter` at `0x18000c0aa`
- `RPCRT4!NdrClientCall3` at `0x18000b294`
- `RPCRT4!NdrClientCall3` at `0x18000b294`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000b1d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000b221`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000b1d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000b221`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000b2e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000b301`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000b2e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000b301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1f6`

## pseudocode

```c
__int64 __fastcall DafStartListenForInboundAssociations(
        char *pv,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  int Pointer; // ebx
  PTP_WAIT v15; // rax
  HANDLE v16; // rdx
  HANDLE v17; // rdx
  int v19; // [rsp+20h] [rbp-98h]
  int v20; // [rsp+28h] [rbp-90h]
  HANDLE h; // [rsp+68h] [rbp-50h] BYREF
  HANDLE v23[9]; // [rsp+70h] [rbp-48h] BYREF

  h = 0;
  v23[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_61e63e094b87365e371089d0260af5a5_Traceguids);
  *((_QWORD *)pv + 13) = a8;
  *((_QWORD *)pv + 16) = a7;
  ThreadpoolWait = CreateThreadpoolWait(InboundWaitCallback, pv, 0);
  *((_QWORD *)pv + 20) = ThreadpoolWait;
  if ( ThreadpoolWait
    && (v15 = CreateThreadpoolWait(InboundWaitCallback, pv, 0), v23[1] = pv + 144, (*((_QWORD *)pv + 18) = v15) != 0) )
  {
    v20 = a3;
    v19 = a2;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&Inbound_ProxyInfo,
                              1u,
                              0,
                              pv + 56,
                              v19,
                              v20,
                              a4,
                              a5,
                              a6,
                              &h,
                              v23).Pointer;
    if ( Pointer >= 0 )
    {
      v16 = h;
      *((_QWORD *)pv + 19) = h;
      SetThreadpoolWait(*((PTP_WAIT *)pv + 20), v16, 0);
      v17 = v23[0];
      *((HANDLE *)pv + 17) = v23[0];
      SetThreadpoolWait(*((PTP_WAIT *)pv + 18), v17, 0);
    }
  }
  else
  {
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000b150  mov     [rsp+arg_0], rcx
0x18000b155  push    rbx
0x18000b156  push    rsi
0x18000b157  push    rdi
0x18000b158  push    r12
0x18000b15a  push    r14
0x18000b15c  push    r15
0x18000b15e  sub     rsp, 88h
0x18000b165  mov     rbx, r9
0x18000b168  mov     r15d, r8d
0x18000b16b  mov     r12d, edx
0x18000b16e  mov     rdi, rcx
0x18000b171  mov     [rsp+0B8h+h], 0
0x18000b17a  mov     [rsp+0B8h+var_48], 0
0x18000b183  lea     rax, WPP_GLOBAL_Control
0x18000b18a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b191  cmp     rcx, rax
0x18000b194  jz      short loc_18000B1B1
0x18000b196  cmp     byte ptr [rcx+19h], 4
0x18000b19a  jb      short loc_18000B1B1
0x18000b19c  mov     edx, 0Eh
0x18000b1a1  lea     r8, WPP_61e63e094b87365e371089d0260af5a5_Traceguids
0x18000b1a8  mov     rcx, [rcx+10h]
0x18000b1ac  call    WPP_SF_s
0x18000b1b1  mov     rax, [rsp+0B8h+arg_38]
0x18000b1b9  mov     [rdi+68h], rax
0x18000b1bd  mov     rax, [rsp+0B8h+arg_30]
0x18000b1c5  mov     [rdi+80h], rax
0x18000b1cc  xor     r8d, r8d; pcbe
0x18000b1cf  mov     rdx, rdi; pv
0x18000b1d2  lea     rcx, ?InboundWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18000b1d9  call    cs:__imp_CreateThreadpoolWait
0x18000b1df  lea     r14, [rdi+0A0h]
0x18000b1e6  mov     [rsp+0B8h+arg_30], r14
0x18000b1ee  mov     [r14], rax
0x18000b1f1  test    rax, rax
0x18000b1f4  jnz     short loc_18000B214
0x18000b1f6  call    cs:__imp_GetLastError
0x18000b1fc  mov     ebx, eax
0x18000b1fe  test    eax, eax
0x18000b200  jle     loc_18000B307
0x18000b206  movzx   ebx, ax
0x18000b209  or      ebx, 80070000h
0x18000b20f  jmp     loc_18000B307
0x18000b214  xor     r8d, r8d; pcbe
0x18000b217  mov     rdx, rdi; pv
0x18000b21a  lea     rcx, ?InboundWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18000b221  call    cs:__imp_CreateThreadpoolWait
0x18000b227  lea     rsi, [rdi+90h]
0x18000b22e  mov     [rsp+0B8h+var_40], rsi
0x18000b233  mov     [rsi], rax
0x18000b236  test    rax, rax
0x18000b239  jz      short loc_18000B1F6
0x18000b23b  mov     [rsp+0B8h+arg_38], 0
0x18000b247  lea     r9, [rdi+38h]
0x18000b24b  lea     rax, [rsp+0B8h+var_48]
0x18000b250  mov     [rsp+0B8h+var_68], rax
0x18000b255  lea     rax, [rsp+0B8h+h]
0x18000b25a  mov     [rsp+0B8h+var_70], rax
0x18000b25f  mov     rax, [rsp+0B8h+arg_28]
0x18000b267  mov     [rsp+0B8h+var_78], rax
0x18000b26c  mov     eax, [rsp+0B8h+arg_20]
0x18000b273  mov     [rsp+0B8h+var_80], eax
0x18000b277  mov     [rsp+0B8h+var_88], rbx
0x18000b27c  mov     [rsp+0B8h+var_90], r15d
0x18000b281  mov     [rsp+0B8h+var_98], r12d
0x18000b286  xor     r8d, r8d; pReturnValue
0x18000b289  lea     edx, [r8+1]; nProcNum
0x18000b28d  lea     rcx, ?Inbound_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000b294  call    cs:__imp_NdrClientCall3
0x18000b29a  mov     rbx, rax
0x18000b29d  mov     [rsp+0B8h+arg_38], rax
0x18000b2a5  mov     [rsp+0B8h+var_58], eax
0x18000b2a9  jmp     short loc_18000B2D3
0x18000b2ab  cmp     eax, 1
0x18000b2ae  jl      short loc_18000B2B8
0x18000b2b0  movzx   eax, ax
0x18000b2b3  or      eax, 80010000h
0x18000b2b8  mov     ebx, eax
0x18000b2ba  mov     [rsp+0B8h+var_58], eax
0x18000b2be  mov     rdi, [rsp+0B8h+arg_0]
0x18000b2c6  mov     r14, [rsp+0B8h+arg_30]
0x18000b2ce  mov     rsi, [rsp+0B8h+var_40]
0x18000b2d3  test    ebx, ebx
0x18000b2d5  js      short loc_18000B307
0x18000b2d7  mov     rdx, [rsp+0B8h+h]; h
0x18000b2dc  mov     [rdi+98h], rdx
0x18000b2e3  xor     r8d, r8d; pftTimeout
0x18000b2e6  mov     rcx, [r14]; pwa
0x18000b2e9  call    cs:__imp_SetThreadpoolWait
0x18000b2ef  mov     rdx, [rsp+0B8h+var_48]; h
0x18000b2f4  mov     [rdi+88h], rdx
0x18000b2fb  xor     r8d, r8d; pftTimeout
0x18000b2fe  mov     rcx, [rsi]; pwa
0x18000b301  call    cs:__imp_SetThreadpoolWait
0x18000b307  mov     eax, ebx
0x18000b309  add     rsp, 88h
0x18000b310  pop     r15
0x18000b312  pop     r14
0x18000b314  pop     r12
0x18000b316  pop     rdi
0x18000b317  pop     rsi
0x18000b318  pop     rbx
0x18000b319  retn
0x18000c09c  push    rbp
0x18000c09e  sub     rsp, 60h
0x18000c0a2  mov     rbp, rdx
0x18000c0a5  mov     rcx, [rcx]
0x18000c0a8  mov     ecx, [rcx]; ExceptionCode
0x18000c0aa  call    cs:__imp_RpcExceptionFilter
0x18000c0b0  nop
0x18000c0b1  add     rsp, 60h
0x18000c0b5  pop     rbp
0x18000c0b6  retn
```
