# RemoteChallengeAsyncRpcCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18005d350`
- end: `0x18005d44a`
- name: `?RemoteChallengeAsyncRpcCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `250`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007500`
- `0x180022434`
- `0x18005d350`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d371`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005d371`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d39b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d423`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d39b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d423`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18005d3ab`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18005d3ab`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18005d42c`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x18005d42c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005d380`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005d380`

## pseudocode

```c
void __fastcall RemoteChallengeAsyncRpcCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  RPC_STATUS v7; // eax
  int v8; // edx
  int v9; // r8d
  int Reply; // [rsp+68h] [rbp+10h] BYREF

  Reply = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(Context + 296);
  while ( 1 )
  {
    EnterCriticalSection(v6);
    v7 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(Context + 88), &Reply);
    if ( !v7 )
    {
      *((_DWORD *)Context + 54) = 3;
      goto LABEL_10;
    }
    if ( v7 == 1818 )
    {
      *((_DWORD *)Context + 54) = 2;
      goto LABEL_10;
    }
    if ( v7 != 997 )
      break;
    LeaveCriticalSection(v6);
    SleepEx(0x1F4u, 1);
  }
  *((_DWORD *)Context + 54) = 4;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v8,
      v9,
      40,
      &WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids,
      v7);
LABEL_10:
  if ( *((_DWORD *)Context + 84) )
    DevicePresenceChallengeOnCompleteStub(Context, Reply);
  LeaveCriticalSection(v6);
  DisassociateCurrentThreadFromCallback(Instance);
  (*(void (__fastcall **)(char *))(*(_QWORD *)Context + 16LL))(Context);
}

```

## disassembly

```asm
0x18005d350  push    rbx
0x18005d352  push    rbp
0x18005d353  push    rsi
0x18005d354  push    rdi
0x18005d355  sub     rsp, 38h
0x18005d359  mov     rbx, rdx
0x18005d35c  mov     [rsp+58h+Reply], 0
0x18005d364  mov     rbp, rcx
0x18005d367  lea     rdi, [rdx+128h]
0x18005d36e  mov     rcx, rdi; lpCriticalSection
0x18005d371  call    cs:__imp_EnterCriticalSection
0x18005d377  lea     rdx, [rsp+58h+Reply]; Reply
0x18005d37c  lea     rcx, [rbx+58h]; pAsync
0x18005d380  call    cs:__imp_RpcAsyncCompleteCall
0x18005d386  test    eax, eax
0x18005d388  jz      short loc_18005D401
0x18005d38a  cmp     eax, 71Ah
0x18005d38f  jz      short loc_18005D3F5
0x18005d391  cmp     eax, 3E5h
0x18005d396  jnz     short loc_18005D3B3
0x18005d398  mov     rcx, rdi; lpCriticalSection
0x18005d39b  call    cs:__imp_LeaveCriticalSection
0x18005d3a1  mov     edx, 1; bAlertable
0x18005d3a6  mov     ecx, 1F4h; dwMilliseconds
0x18005d3ab  call    cs:__imp_SleepEx
0x18005d3b1  jmp     short loc_18005D36E
0x18005d3b3  mov     dword ptr [rbx+0D8h], 4
0x18005d3bd  lea     rcx, WPP_RECORDER_INITIALIZED
0x18005d3c4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18005d3cb  jz      short loc_18005D40B
0x18005d3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d3d4  mov     r9d, 28h ; '('; int
0x18005d3da  mov     dword ptr [rsp+58h+var_30], eax; char
0x18005d3de  lea     rax, WPP_f2e0a728fe33339f22cf999e8124d653_Traceguids
0x18005d3e5  mov     [rsp+58h+MessageGuid], rax; MessageGuid
0x18005d3ea  mov     rcx, [rcx+28h]; int
0x18005d3ee  call    WPP_RECORDER_SF_D
0x18005d3f3  jmp     short loc_18005D40B
0x18005d3f5  mov     dword ptr [rbx+0D8h], 2
0x18005d3ff  jmp     short loc_18005D40B
0x18005d401  mov     dword ptr [rbx+0D8h], 3
0x18005d40b  cmp     dword ptr [rbx+150h], 0
0x18005d412  jz      short loc_18005D420
0x18005d414  mov     edx, [rsp+58h+Reply]; int
0x18005d418  mov     rcx, rbx; void *
0x18005d41b  call    ?DevicePresenceChallengeOnCompleteStub@@YAJPEAXJ@Z; DevicePresenceChallengeOnCompleteStub(void *,long)
0x18005d420  mov     rcx, rdi; lpCriticalSection
0x18005d423  call    cs:__imp_LeaveCriticalSection
0x18005d429  mov     rcx, rbp; pci
0x18005d42c  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x18005d432  mov     rax, [rbx]
0x18005d435  mov     rcx, rbx
0x18005d438  mov     rax, [rax+10h]
0x18005d43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d441  add     rsp, 38h
0x18005d445  pop     rdi
0x18005d446  pop     rsi
0x18005d447  pop     rbp
0x18005d448  pop     rbx
0x18005d449  retn
```
