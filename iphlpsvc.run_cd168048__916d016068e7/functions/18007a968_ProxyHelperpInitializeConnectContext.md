# ProxyHelperpInitializeConnectContext

- ea: `0x18007a968`
- end: `0x18007ad02`
- name: `ProxyHelperpInitializeConnectContext`
- size: `922`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18007a2bc`
- `0x18007adb8`

## callees

- `0x18000d7b0`
- `0x1800159c4`
- `0x180079f04`
- `0x18007a200`
- `0x18007a968`
- `0x18007aedc`
- `0x18007aff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ab27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ac58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ab27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ac58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ab50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007abe5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ac7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007aa2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ab50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007abe5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ac7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a9ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007a9ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007a9ea`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientAllocateMemory` at `0x18007a99c`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientAllocateMemory` at `0x18007a99c`
- `webio!__imp_WebCreateHttpRequest` at `0x18007aafe`
- `webio!__imp_WebCreateHttpRequest` at `0x18007aafe`
- `webio!__imp_WebCreateSession` at `0x18007aa48`
- `webio!__imp_WebCreateSession` at `0x18007aa48`
- `webio!__imp_WebCreateUri` at `0x18007aabb`
- `webio!__imp_WebCreateUri` at `0x18007aabb`
- `webio!__imp_WebSendHttpRequest` at `0x18007ac31`
- `webio!__imp_WebSendHttpRequest` at `0x18007ac31`
- `webio!__imp_WebSetSessionOption` at `0x18007aa96`
- `webio!__imp_WebSetSessionOption` at `0x18007aa96`

## string_xrefs

- `0x18007aa0e`: `ConnCtx: CreateThreadpoolWork failed context %p, status = 0x%x\n`

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
0x18007a968  mov     [rsp-28h+arg_0], rbx
0x18007a96d  mov     [rsp-28h+arg_10], rsi
0x18007a972  push    rbp
0x18007a973  push    rdi
0x18007a974  push    r12
0x18007a976  push    r14
0x18007a978  push    r15
0x18007a97a  mov     rbp, rsp
0x18007a97d  sub     rsp, 70h
0x18007a981  xor     eax, eax
0x18007a983  xorps   xmm0, xmm0
0x18007a986  mov     rsi, rcx
0x18007a989  mov     [rbp+var_10], rax
0x18007a98d  movups  [rbp+var_30], xmm0
0x18007a991  mov     [rbp+arg_8], rax
0x18007a995  lea     ecx, [rax+38h]
0x18007a998  movups  [rbp+var_20], xmm0
0x18007a99c  call    cs:__imp_ProxyHelperClientAllocateMemory
0x18007a9a3  nop     dword ptr [rax+rax+00h]
0x18007a9a8  mov     rdi, rax
0x18007a9ab  test    rax, rax
0x18007a9ae  jnz     short loc_18007A9B8
0x18007a9b0  lea     ebx, [rax+8]
0x18007a9b3  jmp     loc_18007ACE6
0x18007a9b8  xorps   xmm0, xmm0
0x18007a9bb  xor     r15b, r15b
0x18007a9be  movups  xmmword ptr [rdi], xmm0
0x18007a9c1  xor     eax, eax
0x18007a9c3  movups  xmmword ptr [rdi+10h], xmm0
0x18007a9c7  movups  xmmword ptr [rdi+20h], xmm0
0x18007a9cb  lea     r12d, [rax+1]
0x18007a9cf  mov     [rdi+30h], rax
0x18007a9d3  lock add [rdi+18h], r12d
0x18007a9d8  lock add [rdi+18h], r12d
0x18007a9dd  xor     r8d, r8d; pcbe
0x18007a9e0  lea     rcx, ProxyHelperpFreeConnectContextWorker; pfnwk
0x18007a9e7  mov     rdx, rdi; pv
0x18007a9ea  call    cs:__imp_CreateThreadpoolWork
0x18007a9f1  nop     dword ptr [rax+rax+00h]
0x18007a9f6  mov     [rdi+20h], rax
0x18007a9fa  test    rax, rax
0x18007a9fd  jnz     short loc_18007AA3C
0x18007a9ff  call    cs:__imp_GetLastError
0x18007aa06  nop     dword ptr [rax+rax+00h]
0x18007aa0b  mov     r8, rdi
0x18007aa0e  lea     rdx, aConnctxCreatet; "ConnCtx: CreateThreadpoolWork failed co"...
0x18007aa15  mov     r9d, eax
0x18007aa18  mov     ecx, 40000000h
0x18007aa1d  mov     ebx, eax
0x18007aa1f  call    EventWrite0
0x18007aa24  lea     rcx, g_ClientConnectionStateLock; lpCriticalSection
0x18007aa2b  call    cs:__imp_LeaveCriticalSection
0x18007aa32  nop     dword ptr [rax+rax+00h]
0x18007aa37  jmp     loc_18007ACA2
0x18007aa3c  mov     rcx, cs:g_WebIoHandle
0x18007aa43  mov     r8, rdi
0x18007aa46  xor     edx, edx
0x18007aa48  call    cs:__imp_WebCreateSession
0x18007aa4f  nop     dword ptr [rax+rax+00h]
0x18007aa54  mov     ebx, eax
0x18007aa56  test    eax, eax
0x18007aa58  jz      short loc_18007AA82
0x18007aa5a  mov     dword ptr [rsp+70h+var_50], 45Bh
0x18007aa62  lea     r9, aOnecoreuapNetN_9; "onecoreuap\\net\\netio\\iphlpsvc\\httpp"...
0x18007aa69  mov     r8d, eax
0x18007aa6c  lea     rdx, aConnctxFailure; "ConnCtx: Failure status %d; FILE = %s, "...
0x18007aa73  mov     ecx, 40000000h
0x18007aa78  call    EventWrite0
0x18007aa7d  jmp     loc_18007ACA2
0x18007aa82  mov     [rbp+arg_8], r12
0x18007aa86  lea     r8, [rbp+arg_8]
0x18007aa8a  mov     rcx, [rdi]
0x18007aa8d  mov     r9d, 8
0x18007aa93  mov     edx, r12d
0x18007aa96  call    cs:__imp_WebSetSessionOption
0x18007aa9d  nop     dword ptr [rax+rax+00h]
0x18007aaa2  mov     ebx, eax
0x18007aaa4  test    eax, eax
0x18007aaa6  jz      short loc_18007AAB2
0x18007aaa8  mov     dword ptr [rsp+70h+var_50], 468h
0x18007aab0  jmp     short loc_18007AA62
0x18007aab2  mov     rcx, [rsi]
0x18007aab5  lea     r8, [rdi+10h]
0x18007aab9  xor     edx, edx
0x18007aabb  call    cs:__imp_WebCreateUri
0x18007aac2  nop     dword ptr [rax+rax+00h]
0x18007aac7  mov     ebx, eax
0x18007aac9  test    eax, eax
0x18007aacb  jz      short loc_18007AAD7
0x18007aacd  mov     dword ptr [rsp+70h+var_50], 46Fh
0x18007aad5  jmp     short loc_18007AA62
0x18007aad7  lea     rax, aGet; "GET"
0x18007aade  xor     edx, edx
0x18007aae0  mov     qword ptr [rbp+var_30], rax
0x18007aae4  lea     r9, [rdi+8]
0x18007aae8  mov     rax, [rdi+10h]
0x18007aaec  lea     r8, [rbp+var_30]
0x18007aaf0  mov     qword ptr [rbp+var_30+8], rax
0x18007aaf4  mov     dword ptr [rbp+var_20], 10001h
0x18007aafb  mov     rcx, [rdi]
0x18007aafe  call    cs:__imp_WebCreateHttpRequest
0x18007ab05  nop     dword ptr [rax+rax+00h]
0x18007ab0a  mov     ebx, eax
0x18007ab0c  test    eax, eax
0x18007ab0e  jz      short loc_18007AB1D
0x18007ab10  mov     dword ptr [rsp+70h+var_50], 47Ch
0x18007ab18  jmp     loc_18007AA62
0x18007ab1d  lea     r14, g_ClientConnectionStateLock
0x18007ab24  mov     rcx, r14; lpCriticalSection
0x18007ab27  call    cs:__imp_EnterCriticalSection
0x18007ab2e  nop     dword ptr [rax+rax+00h]
0x18007ab33  cmp     dword ptr [rsi+18h], 3
0x18007ab37  jnz     short loc_18007AB66
0x18007ab39  lea     rdx, aConnctxCancele; "ConnCtx: canceled state trying to initi"...
0x18007ab40  mov     r8, rsi
0x18007ab43  mov     ecx, 40000000h
0x18007ab48  call    EventWrite0
0x18007ab4d  mov     rcx, r14; lpCriticalSection
0x18007ab50  call    cs:__imp_LeaveCriticalSection
0x18007ab57  nop     dword ptr [rax+rax+00h]
0x18007ab5c  mov     ebx, 4C7h
0x18007ab61  jmp     loc_18007ACA2
0x18007ab66  cmp     qword ptr [rsi+38h], 0
0x18007ab6b  jz      short loc_18007AB9D
0x18007ab6d  mov     rdx, rdi
0x18007ab70  mov     rcx, rsi
0x18007ab73  call    ProxyHelperpSetProxyInfo
0x18007ab78  mov     ebx, eax
0x18007ab7a  test    eax, eax
0x18007ab7c  jz      short loc_18007AB9D
0x18007ab7e  mov     r9, rsi
0x18007ab81  lea     rdx, aConnctxSetProx; "ConnCtx: set proxy info failed 0x%x, wr"...
0x18007ab88  mov     r8d, eax
0x18007ab8b  mov     ecx, 40000000h
0x18007ab90  call    EventWrite0
0x18007ab95  mov     rcx, r14
0x18007ab98  jmp     loc_18007AA2B
0x18007ab9d  mov     r9, rdi
0x18007aba0  lea     rdx, aConnctxInitcon; "ConnCtx: InitConnContext wrapper %p con"...
0x18007aba7  mov     r8, rsi
0x18007abaa  mov     ecx, 40000000h
0x18007abaf  call    EventWrite0
0x18007abb4  lea     rcx, [rsi+68h]
0x18007abb8  mov     [rsi+20h], rdi
0x18007abbc  mov     dword ptr [rsi+18h], 2
0x18007abc3  mov     r15b, r12b
0x18007abc6  call    RoReferenceEx
0x18007abcb  mov     rcx, r14; lpCriticalSection
0x18007abce  test    al, al
0x18007abd0  jz      loc_18007AC7A
0x18007abd6  mov     [rdi+28h], rsi
0x18007abda  mov     [rdi+30h], rsi
0x18007abde  mov     dword ptr [rsi+18h], 0
0x18007abe5  call    cs:__imp_LeaveCriticalSection
0x18007abec  nop     dword ptr [rax+rax+00h]
0x18007abf1  lock inc dword ptr [rdi+18h]
0x18007abf5  mov     r9, rsi
0x18007abf8  lea     rdx, aConnctxSendhtt; "ConnCtx: SendHttpRequest context %p, wr"...
0x18007abff  mov     r8, rdi
0x18007ac02  mov     ecx, 40000000h
0x18007ac07  call    EventWrite0
0x18007ac0c  mov     rcx, [rdi+8]
0x18007ac10  lea     rax, ProxyHelperpWebRequestCompletionRoutine
0x18007ac17  mov     [rsp+70h+var_40], rdi
0x18007ac1c  xor     r9d, r9d
0x18007ac1f  mov     [rsp+70h+var_48], rax
0x18007ac24  xor     r8d, r8d
0x18007ac27  xor     edx, edx
0x18007ac29  mov     dword ptr [rsp+70h+var_50], 0
0x18007ac31  call    cs:__imp_WebSendHttpRequest
0x18007ac38  nop     dword ptr [rax+rax+00h]
0x18007ac3d  mov     ebx, eax
0x18007ac3f  cmp     eax, 3E5h
0x18007ac44  jz      short loc_18007AC55
0x18007ac46  xor     r8d, r8d
0x18007ac49  mov     edx, eax
0x18007ac4b  mov     rcx, rdi
0x18007ac4e  call    ProxyHelperpWebRequestCompletionRoutine
0x18007ac53  jmp     short loc_18007ACA2
0x18007ac55  mov     rcx, r14; lpCriticalSection
0x18007ac58  call    cs:__imp_EnterCriticalSection
0x18007ac5f  nop     dword ptr [rax+rax+00h]
0x18007ac64  cmp     dword ptr [rsi+18h], 3
0x18007ac68  jnz     loc_18007AB95
0x18007ac6e  lea     rdx, aConnctxCancell; "ConnCtx: cancelled request; wrapper = %"...
0x18007ac75  jmp     loc_18007AB40
0x18007ac7a  call    cs:__imp_LeaveCriticalSection
0x18007ac81  nop     dword ptr [rax+rax+00h]
0x18007ac86  mov     r9, rsi
0x18007ac89  lea     rdx, aConnctxRorefer; "ConnCtx: Roreference failed context %p,"...
0x18007ac90  mov     r8, rdi
0x18007ac93  mov     ecx, 40000000h
0x18007ac98  mov     ebx, 139Fh
0x18007ac9d  call    EventWrite0
0x18007aca2  mov     rcx, rdi
0x18007aca5  call    DerefConnectContext
0x18007acaa  cmp     ebx, 3E5h
0x18007acb0  jz      short loc_18007ACE6
0x18007acb2  test    r15b, r15b
0x18007acb5  jnz     short loc_18007ACBF
0x18007acb7  mov     rcx, rdi
0x18007acba  call    DerefConnectContext
0x18007acbf  movzx   eax, r15b
0x18007acc3  lea     rdx, aConnctxCalling; "ConnCtx: Calling Cancel Connect from in"...
0x18007acca  mov     r9d, ebx
0x18007accd  mov     dword ptr [rsp+70h+var_50], eax
0x18007acd1  mov     r8, rsi
0x18007acd4  mov     ecx, 40000000h
0x18007acd9  call    EventWrite0
0x18007acde  mov     rcx, rsi
0x18007ace1  call    ProxyHelperClientCancelConnect
0x18007ace6  lea     r11, [rsp+70h+var_s0]
0x18007aceb  mov     eax, ebx
0x18007aced  mov     rbx, [r11+30h]
0x18007acf1  mov     rsi, [r11+40h]
0x18007acf5  mov     rsp, r11
0x18007acf8  pop     r15
0x18007acfa  pop     r14
0x18007acfc  pop     r12
0x18007acfe  pop     rdi
0x18007acff  pop     rbp
0x18007ad00  retn
```
