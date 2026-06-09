# SvrImpl_NcaStatusEventSubscriptionGetLastEvent(_RPC_ASYNC_STATE *,void *,void *,NCA_STATUS_EVENT_ *)

- ea: `0x180008774`
- end: `0x180008a43`
- name: `?SvrImpl_NcaStatusEventSubscriptionGetLastEvent@@YAXPEAU_RPC_ASYNC_STATE@@PEAX1PEAUNCA_STATUS_EVENT_@@@Z`
- size: `719`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, void *, struct NCA_INTSERVER_EVENTS_HANDLE_ *, struct NCA_STATUS_EVENT_ *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001b9a0`

## callees

- `0x180003540`
- `0x1800043bc`
- `0x180004f04`
- `0x180004f34`
- `0x180006544`
- `0x1800065c8`
- `0x1800071a8`
- `0x180008774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008965`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800089d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800088f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008965`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800089d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800088c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800088c1`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008815`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008815`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180008908`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180008908`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800089b9`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800089b9`

## pseudocode

```c
void __fastcall SvrImpl_NcaStatusEventSubscriptionGetLastEvent(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        struct NCA_INTSERVER_EVENTS_HANDLE_ *a3,
        struct NCA_STATUS_EVENT_ *a4)
{
  PVOID v7; // rcx
  DWORD v8; // eax
  struct _tag_NCA_CANCELABLE_LOCK *v9; // rcx
  int v10; // r14d
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int IsSubscriptionsValid; // eax
  __int64 v16; // rax
  __int64 v17; // rsi
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  __int64 v19; // rsi
  PVOID v20; // rcx
  int Reply; // [rsp+58h] [rbp+10h] BYREF
  int v22; // [rsp+5Ch] [rbp+14h]

  v22 = HIDWORD(a2);
  Reply = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v7, ApiActivityStart, L"NcaStatusEventSubscriptionGetLastEvent");
  EnterCriticalSection(&gNcaApiSrvImpl);
  _InterlockedIncrement(&dword_180028AE8);
  v8 = WaitForMultipleObjects(2u, &gNcaMain, 0, 0xFFFFFFFF);
  if ( !v8 )
  {
    NcaReleaseCancelableLock(v9);
LABEL_9:
    v10 = 0;
    v11 = 1115;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 52;
LABEL_12:
      v14 = v11;
LABEL_13:
      WPP_SF_d(v12[2], v13, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, v14);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  if ( v8 != 1 )
    goto LABEL_9;
  v10 = 1;
  IsSubscriptionsValid = NcaApiSrvImplIsSubscriptionsValid(a3);
  v11 = IsSubscriptionsValid;
  if ( IsSubscriptionsValid )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 53;
      v14 = IsSubscriptionsValid;
      goto LABEL_13;
    }
  }
  else
  {
    v16 = NcaDAPEvidenceUserSnapshotFind(*((unsigned int *)a3 + 10));
    v17 = v16;
    if ( v16 )
    {
      v18 = (struct _RTL_CRITICAL_SECTION *)(v16 + 64);
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 64));
      if ( *(_QWORD *)(v17 + 616) > *((_QWORD *)a3 + 2) )
      {
        *(_OWORD *)a4 = *(_OWORD *)(v17 + 632);
        v19 = *(_QWORD *)(v17 + 616);
        LeaveCriticalSection(v18);
        v11 = RpcAsyncCompleteCall(pAsync, &Reply);
        if ( !v11 )
          *((_QWORD *)a3 + 2) = v19;
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !v11 )
          goto LABEL_37;
        if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
          goto LABEL_36;
        v13 = 55;
        goto LABEL_12;
      }
      LeaveCriticalSection(v18);
      v11 = 0;
    }
    if ( !*((_QWORD *)a3 + 3) )
    {
      *((_QWORD *)a3 + 3) = pAsync;
      *((_QWORD *)a3 + 4) = a4;
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids);
      goto LABEL_37;
    }
    v11 = 183;
  }
LABEL_36:
  RpcAsyncAbortCall(pAsync, v11);
  if ( v10 )
LABEL_37:
    NcaReleaseCancelableLock((struct _tag_NCA_CANCELABLE_LOCK *)v12);
  LeaveCriticalSection(&gNcaApiSrvImpl);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, v11);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0zx_EventWriteTransfer(v20, ApiActivityEnd, L"NcaStatusEventSubscriptionGetLastEvent", v11);
}

```

## disassembly

```asm
0x180008774  mov     rax, rsp
0x180008777  mov     [rax+8], rbx
0x18000877b  mov     [rax+18h], rbp
0x18000877f  mov     [rax+10h], rdx
0x180008783  push    rsi
0x180008784  push    rdi
0x180008785  push    r13
0x180008787  push    r14
0x180008789  push    r15
0x18000878b  sub     rsp, 20h
0x18000878f  mov     rbp, r9
0x180008792  mov     dword ptr [rax+10h], 0
0x180008799  mov     rdi, r8
0x18000879c  mov     r15, rcx
0x18000879f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087a6  lea     r13, WPP_GLOBAL_Control
0x1800087ad  cmp     rcx, r13
0x1800087b0  jz      short loc_1800087CD
0x1800087b2  test    byte ptr [rcx+1Ch], 8
0x1800087b6  jz      short loc_1800087CD
0x1800087b8  mov     rcx, [rcx+10h]
0x1800087bc  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x1800087c3  mov     edx, 33h ; '3'
0x1800087c8  call    WPP_SF_
0x1800087cd  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800087d4  jz      short loc_1800087E9
0x1800087d6  lea     r8, aNcastatusevent; "NcaStatusEventSubscriptionGetLastEvent"
0x1800087dd  lea     rdx, ApiActivityStart
0x1800087e4  call    McTemplateU0z_EventWriteTransfer
0x1800087e9  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x1800087f0  call    cs:__imp_EnterCriticalSection
0x1800087f7  nop     dword ptr [rax+rax+00h]
0x1800087fc  lock inc cs:dword_180028AE8
0x180008803  xor     r8d, r8d; bWaitAll
0x180008806  lea     rdx, ?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; lpHandles
0x18000880d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180008811  lea     ecx, [r8+2]; nCount
0x180008815  call    cs:__imp_WaitForMultipleObjects
0x18000881c  nop     dword ptr [rax+rax+00h]
0x180008821  test    eax, eax
0x180008823  jnz     short loc_18000882C
0x180008825  call    ?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x18000882a  jmp     short loc_180008831
0x18000882c  cmp     eax, 1
0x18000882f  jz      short loc_18000886F
0x180008831  xor     r14d, r14d
0x180008834  mov     ebx, 45Bh
0x180008839  mov     rcx, cs:WPP_GLOBAL_Control
0x180008840  cmp     rcx, r13
0x180008843  jz      loc_1800089B4
0x180008849  test    byte ptr [rcx+1Ch], 1
0x18000884d  jz      loc_1800089B4
0x180008853  lea     edx, [r14+34h]
0x180008857  mov     r9d, ebx
0x18000885a  mov     rcx, [rcx+10h]
0x18000885e  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x180008865  call    WPP_SF_d
0x18000886a  jmp     loc_1800089B4
0x18000886f  mov     rcx, rdi; struct NCA_INTSERVER_EVENTS_HANDLE_ *
0x180008872  mov     r14d, 1
0x180008878  call    ?NcaApiSrvImplIsSubscriptionsValid@@YAKPEAUNCA_INTSERVER_EVENTS_HANDLE_@@@Z; NcaApiSrvImplIsSubscriptionsValid(NCA_INTSERVER_EVENTS_HANDLE_ *)
0x18000887d  mov     ebx, eax
0x18000887f  test    eax, eax
0x180008881  jz      short loc_1800088A6
0x180008883  mov     rcx, cs:WPP_GLOBAL_Control
0x18000888a  cmp     rcx, r13
0x18000888d  jz      loc_1800089B4
0x180008893  test    [rcx+1Ch], r14b
0x180008897  jz      loc_1800089B4
0x18000889d  lea     edx, [r14+34h]
0x1800088a1  mov     r9d, eax
0x1800088a4  jmp     short loc_18000885A
0x1800088a6  mov     ecx, [rdi+28h]
0x1800088a9  call    NcaDAPEvidenceUserSnapshotFind
0x1800088ae  mov     rsi, rax
0x1800088b1  test    rax, rax
0x1800088b4  jz      loc_180008973
0x1800088ba  lea     rbx, [rax+40h]
0x1800088be  mov     rcx, rbx; lpCriticalSection
0x1800088c1  call    cs:__imp_EnterCriticalSection
0x1800088c8  nop     dword ptr [rax+rax+00h]
0x1800088cd  mov     rdx, [rdi+10h]
0x1800088d1  mov     rcx, rbx; lpCriticalSection
0x1800088d4  cmp     [rsi+268h], rdx
0x1800088db  jbe     loc_180008965
0x1800088e1  movups  xmm0, xmmword ptr [rsi+278h]
0x1800088e8  movdqu  xmmword ptr [rbp+0], xmm0
0x1800088ed  mov     rsi, [rsi+268h]
0x1800088f4  call    cs:__imp_LeaveCriticalSection
0x1800088fb  nop     dword ptr [rax+rax+00h]
0x180008900  lea     rdx, [rsp+48h+Reply]; Reply
0x180008905  mov     rcx, r15; pAsync
0x180008908  call    cs:__imp_RpcAsyncCompleteCall
0x18000890f  nop     dword ptr [rax+rax+00h]
0x180008914  mov     ebx, eax
0x180008916  test    eax, eax
0x180008918  jnz     short loc_18000891E
0x18000891a  mov     [rdi+10h], rsi
0x18000891e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008925  cmp     rcx, r13
0x180008928  jz      short loc_18000894C
0x18000892a  test    byte ptr [rcx+1Ch], 4
0x18000892e  jz      short loc_18000894C
0x180008930  mov     rcx, [rcx+10h]
0x180008934  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x18000893b  mov     edx, 36h ; '6'
0x180008940  call    WPP_SF_
0x180008945  mov     rcx, cs:WPP_GLOBAL_Control
0x18000894c  test    ebx, ebx
0x18000894e  jz      short loc_1800089CA
0x180008950  cmp     rcx, r13
0x180008953  jz      short loc_1800089B4
0x180008955  test    [rcx+1Ch], r14b
0x180008959  jz      short loc_1800089B4
0x18000895b  mov     edx, 37h ; '7'
0x180008960  jmp     loc_180008857
0x180008965  call    cs:__imp_LeaveCriticalSection
0x18000896c  nop     dword ptr [rax+rax+00h]
0x180008971  xor     ebx, ebx
0x180008973  cmp     qword ptr [rdi+18h], 0
0x180008978  jnz     short loc_1800089AF
0x18000897a  mov     [rdi+18h], r15
0x18000897e  mov     [rdi+20h], rbp
0x180008982  mov     rcx, cs:WPP_GLOBAL_Control
0x180008989  cmp     rcx, r13
0x18000898c  jz      short loc_1800089A9
0x18000898e  test    byte ptr [rcx+1Ch], 4
0x180008992  jz      short loc_1800089A9
0x180008994  mov     rcx, [rcx+10h]
0x180008998  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x18000899f  mov     edx, 38h ; '8'
0x1800089a4  call    WPP_SF_
0x1800089a9  test    ebx, ebx
0x1800089ab  jz      short loc_1800089CA
0x1800089ad  jmp     short loc_1800089B4
0x1800089af  mov     ebx, 0B7h
0x1800089b4  mov     edx, ebx; ExceptionCode
0x1800089b6  mov     rcx, r15; pAsync
0x1800089b9  call    cs:__imp_RpcAsyncAbortCall
0x1800089c0  nop     dword ptr [rax+rax+00h]
0x1800089c5  test    r14d, r14d
0x1800089c8  jz      short loc_1800089CF
0x1800089ca  call    ?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x1800089cf  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x1800089d6  call    cs:__imp_LeaveCriticalSection
0x1800089dd  nop     dword ptr [rax+rax+00h]
0x1800089e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089e9  cmp     rcx, r13
0x1800089ec  jz      short loc_180008A0C
0x1800089ee  test    byte ptr [rcx+1Ch], 8
0x1800089f2  jz      short loc_180008A0C
0x1800089f4  mov     rcx, [rcx+10h]
0x1800089f8  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x1800089ff  mov     edx, 39h ; '9'
0x180008a04  mov     r9d, ebx
0x180008a07  call    WPP_SF_d
0x180008a0c  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180008a13  jz      short loc_180008A2B
0x180008a15  mov     r9d, ebx
0x180008a18  lea     r8, aNcastatusevent; "NcaStatusEventSubscriptionGetLastEvent"
0x180008a1f  lea     rdx, ApiActivityEnd
0x180008a26  call    McTemplateU0zx_EventWriteTransfer
0x180008a2b  mov     rbx, [rsp+48h+arg_0]
0x180008a30  mov     rbp, [rsp+48h+arg_10]
0x180008a35  add     rsp, 20h
0x180008a39  pop     r15
0x180008a3b  pop     r14
0x180008a3d  pop     r13
0x180008a3f  pop     rdi
0x180008a40  pop     rsi
0x180008a41  retn
```
