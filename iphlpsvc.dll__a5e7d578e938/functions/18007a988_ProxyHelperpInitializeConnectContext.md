# ProxyHelperpInitializeConnectContext

- ea: `0x18007a988`
- end: `0x18007ad22`
- name: `ProxyHelperpInitializeConnectContext`
- size: `922`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007a2dc`
- `0x18007add8`

## callees

- `0x18000d7c0`
- `0x1800159d4`
- `0x180079f24`
- `0x18007a220`
- `0x18007a988`
- `0x18007aefc`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ab47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ac78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ab47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ac78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ab70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ac05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ac9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ab70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ac05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ac9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aa1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aa1f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007aa0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007aa0a`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientAllocateMemory` at `0x18007a9bc`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientAllocateMemory` at `0x18007a9bc`
- `webio!__imp_WebCreateHttpRequest` at `0x18007ab1e`
- `webio!__imp_WebCreateHttpRequest` at `0x18007ab1e`
- `webio!__imp_WebCreateSession` at `0x18007aa68`
- `webio!__imp_WebCreateSession` at `0x18007aa68`
- `webio!__imp_WebCreateUri` at `0x18007aadb`
- `webio!__imp_WebCreateUri` at `0x18007aadb`
- `webio!__imp_WebSendHttpRequest` at `0x18007ac51`
- `webio!__imp_WebSendHttpRequest` at `0x18007ac51`
- `webio!__imp_WebSetSessionOption` at `0x18007aab6`
- `webio!__imp_WebSetSessionOption` at `0x18007aab6`

## string_xrefs

- `0x18007aa2e`: `ConnCtx: CreateThreadpoolWork failed context %p, status = 0x%x\n`

## pseudocode

```c
__int64 __fastcall ProxyHelperpInitializeConnectContext(__int64 a1)
{
  __int64 Memory; // rax
  volatile signed __int32 *v3; // rdi
  __int64 LastError; // rbx
  unsigned __int8 v5; // r15
  PTP_WORK ThreadpoolWork; // rax
  unsigned int Session; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-50h]
  int v12; // [rsp+20h] [rbp-50h]
  __int128 v13; // [rsp+40h] [rbp-30h] BYREF
  __int128 v14; // [rsp+50h] [rbp-20h]
  __int64 v15; // [rsp+60h] [rbp-10h]
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF

  v15 = 0;
  v13 = 0;
  v16 = 0;
  v14 = 0;
  Memory = ProxyHelperClientAllocateMemory(56);
  v3 = (volatile signed __int32 *)Memory;
  if ( !Memory )
  {
    LODWORD(LastError) = 8;
    return (unsigned int)LastError;
  }
  v5 = 0;
  *(_OWORD *)Memory = 0;
  *(_OWORD *)(Memory + 16) = 0;
  *(_OWORD *)(Memory + 32) = 0;
  *(_QWORD *)(Memory + 48) = 0;
  _InterlockedAdd((volatile signed __int32 *)(Memory + 24), 1u);
  _InterlockedAdd((volatile signed __int32 *)(Memory + 24), 1u);
  ThreadpoolWork = CreateThreadpoolWork(ProxyHelperpFreeConnectContextWorker, (PVOID)Memory, 0);
  *((_QWORD *)v3 + 4) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    EventWrite0(0x40000000, L"ConnCtx: CreateThreadpoolWork failed context %p, status = 0x%x\n", v3, LastError);
LABEL_5:
    LeaveCriticalSection(&g_ClientConnectionStateLock);
    goto LABEL_28;
  }
  Session = WebCreateSession(g_WebIoHandle, 0, v3);
  LODWORD(LastError) = Session;
  if ( Session )
  {
    v12 = 1115;
LABEL_8:
    EventWrite0(
      0x40000000,
      L"ConnCtx: Failure status %d; FILE = %s, LINE = %d\n",
      Session,
      "onecoreuap\\net\\netio\\iphlpsvc\\httpprox\\probe\\httpconn.c",
      v12);
    goto LABEL_28;
  }
  v16 = 1;
  Session = WebSetSessionOption(*(_QWORD *)v3, 1, &v16, 8);
  LODWORD(LastError) = Session;
  if ( Session )
  {
    v12 = 1128;
    goto LABEL_8;
  }
  Session = WebCreateUri(*(_QWORD *)a1, 0, v3 + 4);
  LODWORD(LastError) = Session;
  if ( Session )
  {
    v12 = 1135;
    goto LABEL_8;
  }
  *(_QWORD *)&v13 = "GET";
  *((_QWORD *)&v13 + 1) = *((_QWORD *)v3 + 2);
  LODWORD(v14) = 65537;
  Session = WebCreateHttpRequest(*(_QWORD *)v3, 0, &v13, v3 + 2);
  LODWORD(LastError) = Session;
  if ( Session )
  {
    v12 = 1148;
    goto LABEL_8;
  }
  EnterCriticalSection(&g_ClientConnectionStateLock);
  if ( *(_DWORD *)(a1 + 24) == 3 )
  {
    EventWrite0(0x40000000, L"ConnCtx: canceled state trying to initialize, wrapper = %p\n", a1);
LABEL_17:
    LeaveCriticalSection(&g_ClientConnectionStateLock);
    LODWORD(LastError) = 1223;
    goto LABEL_28;
  }
  if ( *(_QWORD *)(a1 + 56) )
  {
    v8 = ProxyHelperpSetProxyInfo(a1, v3);
    LODWORD(LastError) = v8;
    if ( v8 )
    {
      EventWrite0(0x40000000, L"ConnCtx: set proxy info failed 0x%x, wrapper = %p\n", v8, a1);
      goto LABEL_5;
    }
  }
  EventWrite0(0x40000000, L"ConnCtx: InitConnContext wrapper %p context %p\n", a1, v3);
  *(_QWORD *)(a1 + 32) = v3;
  *(_DWORD *)(a1 + 24) = 2;
  v5 = 1;
  if ( (unsigned __int8)RoReferenceEx(a1 + 104) )
  {
    *((_QWORD *)v3 + 5) = a1;
    *((_QWORD *)v3 + 6) = a1;
    *(_DWORD *)(a1 + 24) = 0;
    LeaveCriticalSection(&g_ClientConnectionStateLock);
    _InterlockedIncrement(v3 + 6);
    EventWrite0(0x40000000, L"ConnCtx: SendHttpRequest context %p, wrapper = %p\n", v3, a1);
    v9 = WebSendHttpRequest(*((_QWORD *)v3 + 1), 0, 0, 0, 0, ProxyHelperpWebRequestCompletionRoutine, v3);
    LODWORD(LastError) = v9;
    if ( v9 == 997 )
    {
      EnterCriticalSection(&g_ClientConnectionStateLock);
      if ( *(_DWORD *)(a1 + 24) != 3 )
        goto LABEL_5;
      EventWrite0(0x40000000, L"ConnCtx: cancelled request; wrapper = %p\n", a1);
      goto LABEL_17;
    }
    ProxyHelperpWebRequestCompletionRoutine(v3, v9, 0);
  }
  else
  {
    LeaveCriticalSection(&g_ClientConnectionStateLock);
    LODWORD(LastError) = 5023;
    EventWrite0(0x40000000, L"ConnCtx: Roreference failed context %p, wrapper = %p\n", v3, a1);
  }
LABEL_28:
  DerefConnectContext(v3);
  if ( (_DWORD)LastError != 997 )
  {
    if ( !v5 )
      DerefConnectContext(v3);
    LODWORD(v11) = v5;
    EventWrite0(
      0x40000000,
      L"ConnCtx: Calling Cancel Connect from init wrapper = %p; status = 0x%x, inserted = %d\n",
      a1,
      (unsigned int)LastError,
      v11);
    ProxyHelperClientCancelConnect(a1);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18007a988  mov     [rsp-28h+arg_0], rbx
0x18007a98d  mov     [rsp-28h+arg_10], rsi
0x18007a992  push    rbp
0x18007a993  push    rdi
0x18007a994  push    r12
0x18007a996  push    r14
0x18007a998  push    r15
0x18007a99a  mov     rbp, rsp
0x18007a99d  sub     rsp, 70h
0x18007a9a1  xor     eax, eax
0x18007a9a3  xorps   xmm0, xmm0
0x18007a9a6  mov     rsi, rcx
0x18007a9a9  mov     [rbp+var_10], rax
0x18007a9ad  movups  [rbp+var_30], xmm0
0x18007a9b1  mov     [rbp+arg_8], rax
0x18007a9b5  lea     ecx, [rax+38h]
0x18007a9b8  movups  [rbp+var_20], xmm0
0x18007a9bc  call    cs:__imp_ProxyHelperClientAllocateMemory
0x18007a9c3  nop     dword ptr [rax+rax+00h]
0x18007a9c8  mov     rdi, rax
0x18007a9cb  test    rax, rax
0x18007a9ce  jnz     short loc_18007A9D8
0x18007a9d0  lea     ebx, [rax+8]
0x18007a9d3  jmp     loc_18007AD06
0x18007a9d8  xorps   xmm0, xmm0
0x18007a9db  xor     r15b, r15b
0x18007a9de  movups  xmmword ptr [rdi], xmm0
0x18007a9e1  xor     eax, eax
0x18007a9e3  movups  xmmword ptr [rdi+10h], xmm0
0x18007a9e7  movups  xmmword ptr [rdi+20h], xmm0
0x18007a9eb  lea     r12d, [rax+1]
0x18007a9ef  mov     [rdi+30h], rax
0x18007a9f3  lock add [rdi+18h], r12d
0x18007a9f8  lock add [rdi+18h], r12d
0x18007a9fd  xor     r8d, r8d; pcbe
0x18007aa00  lea     rcx, ProxyHelperpFreeConnectContextWorker; pfnwk
0x18007aa07  mov     rdx, rdi; pv
0x18007aa0a  call    cs:__imp_CreateThreadpoolWork
0x18007aa11  nop     dword ptr [rax+rax+00h]
0x18007aa16  mov     [rdi+20h], rax
0x18007aa1a  test    rax, rax
0x18007aa1d  jnz     short loc_18007AA5C
0x18007aa1f  call    cs:__imp_GetLastError
0x18007aa26  nop     dword ptr [rax+rax+00h]
0x18007aa2b  mov     r8, rdi
0x18007aa2e  lea     rdx, aConnctxCreatet; "ConnCtx: CreateThreadpoolWork failed co"...
0x18007aa35  mov     r9d, eax
0x18007aa38  mov     ecx, 40000000h
0x18007aa3d  mov     ebx, eax
0x18007aa3f  call    EventWrite0
0x18007aa44  lea     rcx, g_ClientConnectionStateLock; lpCriticalSection
0x18007aa4b  call    cs:__imp_LeaveCriticalSection
0x18007aa52  nop     dword ptr [rax+rax+00h]
0x18007aa57  jmp     loc_18007ACC2
0x18007aa5c  mov     rcx, cs:g_WebIoHandle
0x18007aa63  mov     r8, rdi
0x18007aa66  xor     edx, edx
0x18007aa68  call    cs:__imp_WebCreateSession
0x18007aa6f  nop     dword ptr [rax+rax+00h]
0x18007aa74  mov     ebx, eax
0x18007aa76  test    eax, eax
0x18007aa78  jz      short loc_18007AAA2
0x18007aa7a  mov     dword ptr [rsp+70h+var_50], 45Bh
0x18007aa82  lea     r9, aOnecoreuapNetN_9; "onecoreuap\\net\\netio\\iphlpsvc\\httpp"...
0x18007aa89  mov     r8d, eax
0x18007aa8c  lea     rdx, aConnctxFailure; "ConnCtx: Failure status %d; FILE = %s, "...
0x18007aa93  mov     ecx, 40000000h
0x18007aa98  call    EventWrite0
0x18007aa9d  jmp     loc_18007ACC2
0x18007aaa2  mov     [rbp+arg_8], r12
0x18007aaa6  lea     r8, [rbp+arg_8]
0x18007aaaa  mov     rcx, [rdi]
0x18007aaad  mov     r9d, 8
0x18007aab3  mov     edx, r12d
0x18007aab6  call    cs:__imp_WebSetSessionOption
0x18007aabd  nop     dword ptr [rax+rax+00h]
0x18007aac2  mov     ebx, eax
0x18007aac4  test    eax, eax
0x18007aac6  jz      short loc_18007AAD2
0x18007aac8  mov     dword ptr [rsp+70h+var_50], 468h
0x18007aad0  jmp     short loc_18007AA82
0x18007aad2  mov     rcx, [rsi]
0x18007aad5  lea     r8, [rdi+10h]
0x18007aad9  xor     edx, edx
0x18007aadb  call    cs:__imp_WebCreateUri
0x18007aae2  nop     dword ptr [rax+rax+00h]
0x18007aae7  mov     ebx, eax
0x18007aae9  test    eax, eax
0x18007aaeb  jz      short loc_18007AAF7
0x18007aaed  mov     dword ptr [rsp+70h+var_50], 46Fh
0x18007aaf5  jmp     short loc_18007AA82
0x18007aaf7  lea     rax, aGet; "GET"
0x18007aafe  xor     edx, edx
0x18007ab00  mov     qword ptr [rbp+var_30], rax
0x18007ab04  lea     r9, [rdi+8]
0x18007ab08  mov     rax, [rdi+10h]
0x18007ab0c  lea     r8, [rbp+var_30]
0x18007ab10  mov     qword ptr [rbp+var_30+8], rax
0x18007ab14  mov     dword ptr [rbp+var_20], 10001h
0x18007ab1b  mov     rcx, [rdi]
0x18007ab1e  call    cs:__imp_WebCreateHttpRequest
0x18007ab25  nop     dword ptr [rax+rax+00h]
0x18007ab2a  mov     ebx, eax
0x18007ab2c  test    eax, eax
0x18007ab2e  jz      short loc_18007AB3D
0x18007ab30  mov     dword ptr [rsp+70h+var_50], 47Ch
0x18007ab38  jmp     loc_18007AA82
0x18007ab3d  lea     r14, g_ClientConnectionStateLock
0x18007ab44  mov     rcx, r14; lpCriticalSection
0x18007ab47  call    cs:__imp_EnterCriticalSection
0x18007ab4e  nop     dword ptr [rax+rax+00h]
0x18007ab53  cmp     dword ptr [rsi+18h], 3
0x18007ab57  jnz     short loc_18007AB86
0x18007ab59  lea     rdx, aConnctxCancele; "ConnCtx: canceled state trying to initi"...
0x18007ab60  mov     r8, rsi
0x18007ab63  mov     ecx, 40000000h
0x18007ab68  call    EventWrite0
0x18007ab6d  mov     rcx, r14; lpCriticalSection
0x18007ab70  call    cs:__imp_LeaveCriticalSection
0x18007ab77  nop     dword ptr [rax+rax+00h]
0x18007ab7c  mov     ebx, 4C7h
0x18007ab81  jmp     loc_18007ACC2
0x18007ab86  cmp     qword ptr [rsi+38h], 0
0x18007ab8b  jz      short loc_18007ABBD
0x18007ab8d  mov     rdx, rdi
0x18007ab90  mov     rcx, rsi
0x18007ab93  call    ProxyHelperpSetProxyInfo
0x18007ab98  mov     ebx, eax
0x18007ab9a  test    eax, eax
0x18007ab9c  jz      short loc_18007ABBD
0x18007ab9e  mov     r9, rsi
0x18007aba1  lea     rdx, aConnctxSetProx; "ConnCtx: set proxy info failed 0x%x, wr"...
0x18007aba8  mov     r8d, eax
0x18007abab  mov     ecx, 40000000h
0x18007abb0  call    EventWrite0
0x18007abb5  mov     rcx, r14
0x18007abb8  jmp     loc_18007AA4B
0x18007abbd  mov     r9, rdi
0x18007abc0  lea     rdx, aConnctxInitcon; "ConnCtx: InitConnContext wrapper %p con"...
0x18007abc7  mov     r8, rsi
0x18007abca  mov     ecx, 40000000h
0x18007abcf  call    EventWrite0
0x18007abd4  lea     rcx, [rsi+68h]
0x18007abd8  mov     [rsi+20h], rdi
0x18007abdc  mov     dword ptr [rsi+18h], 2
0x18007abe3  mov     r15b, r12b
0x18007abe6  call    RoReferenceEx
0x18007abeb  mov     rcx, r14; lpCriticalSection
0x18007abee  test    al, al
0x18007abf0  jz      loc_18007AC9A
0x18007abf6  mov     [rdi+28h], rsi
0x18007abfa  mov     [rdi+30h], rsi
0x18007abfe  mov     dword ptr [rsi+18h], 0
0x18007ac05  call    cs:__imp_LeaveCriticalSection
0x18007ac0c  nop     dword ptr [rax+rax+00h]
0x18007ac11  lock inc dword ptr [rdi+18h]
0x18007ac15  mov     r9, rsi
0x18007ac18  lea     rdx, aConnctxSendhtt; "ConnCtx: SendHttpRequest context %p, wr"...
0x18007ac1f  mov     r8, rdi
0x18007ac22  mov     ecx, 40000000h
0x18007ac27  call    EventWrite0
0x18007ac2c  mov     rcx, [rdi+8]
0x18007ac30  lea     rax, ProxyHelperpWebRequestCompletionRoutine
0x18007ac37  mov     [rsp+70h+var_40], rdi
0x18007ac3c  xor     r9d, r9d
0x18007ac3f  mov     [rsp+70h+var_48], rax
0x18007ac44  xor     r8d, r8d
0x18007ac47  xor     edx, edx
0x18007ac49  mov     dword ptr [rsp+70h+var_50], 0
0x18007ac51  call    cs:__imp_WebSendHttpRequest
0x18007ac58  nop     dword ptr [rax+rax+00h]
0x18007ac5d  mov     ebx, eax
0x18007ac5f  cmp     eax, 3E5h
0x18007ac64  jz      short loc_18007AC75
0x18007ac66  xor     r8d, r8d
0x18007ac69  mov     edx, eax
0x18007ac6b  mov     rcx, rdi
0x18007ac6e  call    ProxyHelperpWebRequestCompletionRoutine
0x18007ac73  jmp     short loc_18007ACC2
0x18007ac75  mov     rcx, r14; lpCriticalSection
0x18007ac78  call    cs:__imp_EnterCriticalSection
0x18007ac7f  nop     dword ptr [rax+rax+00h]
0x18007ac84  cmp     dword ptr [rsi+18h], 3
0x18007ac88  jnz     loc_18007ABB5
0x18007ac8e  lea     rdx, aConnctxCancell; "ConnCtx: cancelled request; wrapper = %"...
0x18007ac95  jmp     loc_18007AB60
0x18007ac9a  call    cs:__imp_LeaveCriticalSection
0x18007aca1  nop     dword ptr [rax+rax+00h]
0x18007aca6  mov     r9, rsi
0x18007aca9  lea     rdx, aConnctxRorefer; "ConnCtx: Roreference failed context %p,"...
0x18007acb0  mov     r8, rdi
0x18007acb3  mov     ecx, 40000000h
0x18007acb8  mov     ebx, 139Fh
0x18007acbd  call    EventWrite0
0x18007acc2  mov     rcx, rdi
0x18007acc5  call    DerefConnectContext
0x18007acca  cmp     ebx, 3E5h
0x18007acd0  jz      short loc_18007AD06
0x18007acd2  test    r15b, r15b
0x18007acd5  jnz     short loc_18007ACDF
0x18007acd7  mov     rcx, rdi
0x18007acda  call    DerefConnectContext
0x18007acdf  movzx   eax, r15b
0x18007ace3  lea     rdx, aConnctxCalling; "ConnCtx: Calling Cancel Connect from in"...
0x18007acea  mov     r9d, ebx
0x18007aced  mov     dword ptr [rsp+70h+var_50], eax
0x18007acf1  mov     r8, rsi
0x18007acf4  mov     ecx, 40000000h
0x18007acf9  call    EventWrite0
0x18007acfe  mov     rcx, rsi
0x18007ad01  call    ProxyHelperClientCancelConnect
0x18007ad06  lea     r11, [rsp+70h+var_s0]
0x18007ad0b  mov     eax, ebx
0x18007ad0d  mov     rbx, [r11+30h]
0x18007ad11  mov     rsi, [r11+40h]
0x18007ad15  mov     rsp, r11
0x18007ad18  pop     r15
0x18007ad1a  pop     r14
0x18007ad1c  pop     r12
0x18007ad1e  pop     rdi
0x18007ad1f  pop     rbp
0x18007ad20  retn
```
