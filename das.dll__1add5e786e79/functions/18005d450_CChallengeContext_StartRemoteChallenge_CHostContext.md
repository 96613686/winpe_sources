# CChallengeContext::StartRemoteChallenge(CHostContext *)

- ea: `0x18005d450`
- end: `0x18005d6b2`
- name: `?StartRemoteChallenge@CChallengeContext@@IEAAJPEAVCHostContext@@@Z`
- size: `610`
- prototype: `__int64 __fastcall(PVOID pv, struct CHostContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b24c`

## callees

- `0x18002394c`
- `0x18005d450`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d5b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d5b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d593`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005d581`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005d581`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d5d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d5d5`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005d629`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18005d629`
- `RPCRT4!NdrClientCall3` at `0x18005d49b`
- `RPCRT4!NdrClientCall3` at `0x18005d49b`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18005d516`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18005d516`

## pseudocode

```c
__int64 __fastcall CChallengeContext::StartRemoteChallenge(char *pv, struct CHostContext *a2)
{
  unsigned int Pointer; // ebx
  int v4; // eax
  int v5; // edx
  int v6; // r8d
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  HANDLE EventW; // rax

  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_180083280,
                            0x1Au,
                            0,
                            *(_QWORD *)a2,
                            pv + 8,
                            *((_QWORD *)pv + 9),
                            pv + 80).Pointer;
  if ( !Pointer )
  {
    v4 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(pv + 88), 0x70u);
    if ( v4 )
    {
      if ( v4 >= 0 )
        v4 = (unsigned __int16)v4 | 0x80010000;
      Pointer = v4;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v5,
          v6,
          13,
          &WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids,
          *((_QWORD *)pv + 9),
          v4);
    }
    else
    {
      ThreadpoolWait = CreateThreadpoolWait(RemoteChallengeAsyncRpcCallback, pv, 0);
      *((_QWORD *)pv + 26) = ThreadpoolWait;
      if ( ThreadpoolWait && (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)pv + 25) = EventW) != 0) )
      {
        SetThreadpoolWait(*((PTP_WAIT *)pv + 26), EventW, 0);
        *((_QWORD *)pv + 14) = pv;
        *((_DWORD *)pv + 33) = 1;
        *((_QWORD *)pv + 17) = *((_QWORD *)pv + 25);
        *((_DWORD *)pv + 54) = 1;
        (*(void (__fastcall **)(char *))(*(_QWORD *)pv + 8LL))(pv);
        Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&stru_180083280, 0x1Bu, 0, pv + 88, pv + 80);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return (unsigned int)LastError;
      }
    }
  }
  return Pointer;
}

```

## disassembly

```asm
0x18005d450  mov     r11, rsp
0x18005d453  mov     [r11+10h], rbx
0x18005d457  mov     [r11+20h], rsi
0x18005d45b  mov     [r11+8], rcx
0x18005d45f  push    rdi
0x18005d460  sub     rsp, 50h
0x18005d464  mov     r9, rdx
0x18005d467  mov     rdi, rcx
0x18005d46a  mov     r8, [rcx+48h]
0x18005d46e  mov     qword ptr [r11+18h], 0
0x18005d476  lea     rax, [rcx+50h]
0x18005d47a  lea     rdx, [rcx+8]
0x18005d47e  mov     [r11-28h], rax
0x18005d482  mov     [r11-30h], r8
0x18005d486  mov     [r11-38h], rdx
0x18005d48a  mov     r9, [r9]
0x18005d48d  xor     r8d, r8d; pReturnValue
0x18005d490  lea     edx, [r8+1Ah]; nProcNum
0x18005d494  lea     rcx, stru_180083280; pProxyInfo
0x18005d49b  call    cs:__imp_NdrClientCall3
0x18005d4a1  mov     rbx, rax
0x18005d4a4  mov     [rsp+58h+arg_10], rax
0x18005d4a9  mov     [rsp+58h+var_18], eax
0x18005d4ad  jmp     short loc_18005D507
0x18005d4af  cmp     eax, 1
0x18005d4b2  jl      short loc_18005D4BC
0x18005d4b4  movzx   eax, ax
0x18005d4b7  or      eax, 80010000h
0x18005d4bc  mov     ebx, eax
0x18005d4be  mov     [rsp+58h+var_18], eax
0x18005d4c2  lea     rcx, WPP_RECORDER_INITIALIZED
0x18005d4c9  mov     rdi, [rsp+58h+arg_0]
0x18005d4ce  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005d4d5  jz      short loc_18005D507
0x18005d4d7  mov     r9d, 0Ch; int
0x18005d4dd  mov     dword ptr [rsp+58h+var_28], eax; char
0x18005d4e1  mov     rax, [rdi+48h]
0x18005d4e5  mov     [rsp+58h+var_30], rax; __int64
0x18005d4ea  lea     rax, WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids
0x18005d4f1  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x18005d4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d4fd  mov     rcx, [rcx+28h]; int
0x18005d501  call    WPP_RECORDER_SF_Sd
0x18005d506  nop
0x18005d507  test    ebx, ebx
0x18005d509  jnz     loc_18005D6A0
0x18005d50f  lea     edx, [rbx+70h]; Size
0x18005d512  lea     rcx, [rdi+58h]; pAsync
0x18005d516  call    cs:__imp_RpcAsyncInitializeHandle
0x18005d51c  test    eax, eax
0x18005d51e  jz      short loc_18005D574
0x18005d520  js      short loc_18005D52A
0x18005d522  movzx   eax, ax
0x18005d525  or      eax, 80010000h
0x18005d52a  mov     ebx, eax
0x18005d52c  lea     rcx, WPP_RECORDER_INITIALIZED
0x18005d533  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005d53a  jz      loc_18005D6A0
0x18005d540  mov     r9d, 0Dh; int
0x18005d546  mov     dword ptr [rsp+58h+var_28], eax; char
0x18005d54a  mov     rax, [rdi+48h]
0x18005d54e  mov     [rsp+58h+var_30], rax; __int64
0x18005d553  lea     rax, WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids
0x18005d55a  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x18005d55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d566  mov     rcx, [rcx+28h]; int
0x18005d56a  call    WPP_RECORDER_SF_Sd
0x18005d56f  jmp     loc_18005D6A0
0x18005d574  xor     r8d, r8d; pcbe
0x18005d577  mov     rdx, rdi; pv
0x18005d57a  lea     rcx, ?RemoteChallengeAsyncRpcCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005d581  call    cs:__imp_CreateThreadpoolWait
0x18005d587  mov     [rdi+0D0h], rax
0x18005d58e  test    rax, rax
0x18005d591  jnz     short loc_18005D5AC
0x18005d593  call    cs:__imp_GetLastError
0x18005d599  test    eax, eax
0x18005d59b  jle     short loc_18005D5A5
0x18005d59d  movzx   eax, ax
0x18005d5a0  or      eax, 80070000h
0x18005d5a5  mov     ebx, eax
0x18005d5a7  jmp     loc_18005D6A0
0x18005d5ac  xor     r9d, r9d; lpName
0x18005d5af  xor     r8d, r8d; bInitialState
0x18005d5b2  xor     edx, edx; bManualReset
0x18005d5b4  xor     ecx, ecx; lpEventAttributes
0x18005d5b6  call    cs:__imp_CreateEventW
0x18005d5bc  mov     [rdi+0C8h], rax
0x18005d5c3  test    rax, rax
0x18005d5c6  jz      short loc_18005D593
0x18005d5c8  xor     r8d, r8d; pftTimeout
0x18005d5cb  mov     rdx, rax; h
0x18005d5ce  mov     rcx, [rdi+0D0h]; pwa
0x18005d5d5  call    cs:__imp_SetThreadpoolWait
0x18005d5db  mov     [rdi+70h], rdi
0x18005d5df  mov     ecx, 1
0x18005d5e4  mov     [rdi+84h], ecx
0x18005d5ea  mov     rax, [rdi+0C8h]
0x18005d5f1  mov     [rdi+88h], rax
0x18005d5f8  mov     [rdi+0D8h], ecx
0x18005d5fe  mov     rax, [rdi]
0x18005d601  mov     rcx, rdi
0x18005d604  mov     rax, [rax+8]
0x18005d608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d60d  nop
0x18005d60e  lea     rax, [rdi+50h]
0x18005d612  mov     [rsp+58h+MessageGuid], rax
0x18005d617  lea     r9, [rdi+58h]
0x18005d61b  xor     r8d, r8d; pReturnValue
0x18005d61e  lea     edx, [r8+1Bh]; nProcNum
0x18005d622  lea     rcx, stru_180083280; pProxyInfo
0x18005d629  call    cs:__imp_Ndr64AsyncClientCall
0x18005d62f  jmp     short loc_18005D6A0
0x18005d631  cmp     eax, 1
0x18005d634  jl      short loc_18005D63E
0x18005d636  movzx   eax, ax
0x18005d639  or      eax, 80010000h
0x18005d63e  mov     ebx, eax
0x18005d640  lea     rcx, WPP_RECORDER_INITIALIZED
0x18005d647  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005d64e  jz      short loc_18005D684
0x18005d650  mov     r9d, 0Eh; int
0x18005d656  mov     dword ptr [rsp+58h+var_28], eax; char
0x18005d65a  mov     rax, [rsp+58h+arg_0]
0x18005d65f  mov     rcx, [rax+48h]
0x18005d663  mov     [rsp+58h+var_30], rcx; __int64
0x18005d668  lea     rax, WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids
0x18005d66f  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x18005d674  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d67b  mov     rcx, [rcx+28h]; int
0x18005d67f  call    WPP_RECORDER_SF_Sd
0x18005d684  mov     rcx, [rsp+58h+arg_0]
0x18005d689  mov     dword ptr [rcx+0D8h], 4
0x18005d693  mov     rax, [rcx]
0x18005d696  mov     rax, [rax+10h]
0x18005d69a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d69f  nop
0x18005d6a0  mov     eax, ebx
0x18005d6a2  mov     rbx, [rsp+58h+arg_8]
0x18005d6a7  mov     rsi, [rsp+58h+arg_18]
0x18005d6ac  add     rsp, 50h
0x18005d6b0  pop     rdi
0x18005d6b1  retn
```
