# CreateAsyncUserContext(_DAC_CLIENT_CONTEXT *,DAC_CALLBACK_TYPE,void *,void *,int *,_DAC_ASYNC_USER_CONTEXT * *)

- ea: `0x180002168`
- end: `0x18000227d`
- name: `?CreateAsyncUserContext@@YAJPEAU_DAC_CLIENT_CONTEXT@@W4DAC_CALLBACK_TYPE@@PEAX2PEAHPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, void *, int *, struct _RPC_ASYNC_STATE **)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x1800090b0`
- `0x1800091e0`
- `0x180009320`
- `0x180009450`
- `0x180009580`
- `0x1800096a0`
- `0x180009890`
- `0x180009fa4`
- `0x18000a4b0`
- `0x18000a5e0`

## callees

- `0x180002168`
- `0x180002c50`
- `0x180002f10`
- `0x18000bbc2`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002268`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002268`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000225a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000225a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180002225`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180002225`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800021cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800021cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800021de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800021de`

## pseudocode

```c
__int64 __fastcall CreateAsyncUserContext(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        void *a4,
        int *a5,
        struct _RPC_ASYNC_STATE **a6)
{
  unsigned int v10; // edi
  HANDLE ProcessHeap; // rax
  struct _RPC_ASYNC_STATE *v12; // rax
  struct _RPC_ASYNC_STATE *v13; // rsi
  RPC_STATUS v14; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 84));
  v10 = PendCall((struct _DAC_CLIENT_CONTEXT *)a1, a5);
  if ( !v10 )
  {
    ProcessHeap = GetProcessHeap();
    v12 = (struct _RPC_ASYNC_STATE *)HeapAlloc(ProcessHeap, 0, 0xA0u);
    v13 = v12;
    *a6 = v12;
    if ( v12 )
    {
      memset_0(v12, 0, 0xA0u);
      v13[1].Size = a2;
      *(_QWORD *)&v13[1].Lock = a3;
      v13[1].StubInfo = a4;
      v14 = RpcAsyncInitializeHandle(v13, 0x70u);
      if ( v14 )
      {
        if ( v14 < 0 )
          return (unsigned int)v14;
        else
          return (unsigned __int16)v14 | 0x80010000;
      }
      else
      {
        v13->UserInfo = (void *)a1;
        v13->u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)DacAsyncCallbackRoutine;
        v13->NotificationType = RpcNotificationTypeCallback;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
        *(_QWORD *)(a1 + 72) = v13;
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180002168  push    rbx
0x18000216a  push    rbp
0x18000216b  push    rsi
0x18000216c  push    rdi
0x18000216d  push    r14
0x18000216f  push    r15
0x180002171  sub     rsp, 28h
0x180002175  mov     rbx, r9
0x180002178  mov     r14, r8
0x18000217b  mov     r15d, edx
0x18000217e  mov     rbp, rcx
0x180002181  mov     rcx, cs:WPP_GLOBAL_Control
0x180002188  lea     rax, WPP_GLOBAL_Control
0x18000218f  cmp     rcx, rax
0x180002192  jz      short loc_1800021AF
0x180002194  cmp     byte ptr [rcx+19h], 4
0x180002198  jb      short loc_1800021AF
0x18000219a  mov     rcx, [rcx+10h]
0x18000219e  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x1800021a5  mov     edx, 1Ch
0x1800021aa  call    WPP_SF_s
0x1800021af  lock inc dword ptr [rbp+54h]
0x1800021b3  mov     rdx, [rsp+58h+arg_20]; int *
0x1800021bb  mov     rcx, rbp; struct _DAC_CLIENT_CONTEXT *
0x1800021be  call    ?PendCall@@YAJPEAU_DAC_CLIENT_CONTEXT@@PEAH@Z; PendCall(_DAC_CLIENT_CONTEXT *,int *)
0x1800021c3  mov     edi, eax
0x1800021c5  test    eax, eax
0x1800021c7  jnz     loc_18000226E
0x1800021cd  call    cs:__imp_GetProcessHeap
0x1800021d3  xor     edx, edx; dwFlags
0x1800021d5  mov     r8d, 0A0h; dwBytes
0x1800021db  mov     rcx, rax; hHeap
0x1800021de  call    cs:__imp_HeapAlloc
0x1800021e4  mov     rcx, [rsp+58h+arg_28]
0x1800021ec  mov     rsi, rax
0x1800021ef  mov     [rcx], rax
0x1800021f2  test    rax, rax
0x1800021f5  jnz     short loc_1800021FE
0x1800021f7  mov     edi, 8007000Eh
0x1800021fc  jmp     short loc_18000226E
0x1800021fe  xor     edx, edx; Val
0x180002200  mov     r8d, 0A0h; Size
0x180002206  mov     rcx, rsi; void *
0x180002209  call    memset_0
0x18000220e  mov     edx, 70h ; 'p'; Size
0x180002213  mov     [rsi+70h], r15d
0x180002217  mov     rcx, rsi; pAsync
0x18000221a  mov     [rsi+78h], r14
0x18000221e  mov     [rsi+80h], rbx
0x180002225  call    cs:__imp_RpcAsyncInitializeHandle
0x18000222b  test    eax, eax
0x18000222d  jz      short loc_180002240
0x18000222f  js      short loc_18000223C
0x180002231  movzx   edi, ax
0x180002234  or      edi, 80010000h
0x18000223a  jmp     short loc_18000226E
0x18000223c  mov     edi, eax
0x18000223e  jmp     short loc_18000226E
0x180002240  lea     rax, ?DacAsyncCallbackRoutine@@YAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z; DacAsyncCallbackRoutine(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)
0x180002247  mov     [rsi+18h], rbp
0x18000224b  lea     rcx, [rbp+10h]; lpCriticalSection
0x18000224f  mov     [rsi+30h], rax
0x180002253  mov     dword ptr [rsi+2Ch], 5
0x18000225a  call    cs:__imp_EnterCriticalSection
0x180002260  lea     rcx, [rbp+10h]; lpCriticalSection
0x180002264  mov     [rbp+48h], rsi
0x180002268  call    cs:__imp_LeaveCriticalSection
0x18000226e  mov     eax, edi
0x180002270  add     rsp, 28h
0x180002274  pop     r15
0x180002276  pop     r14
0x180002278  pop     rdi
0x180002279  pop     rsi
0x18000227a  pop     rbp
0x18000227b  pop     rbx
0x18000227c  retn
```
