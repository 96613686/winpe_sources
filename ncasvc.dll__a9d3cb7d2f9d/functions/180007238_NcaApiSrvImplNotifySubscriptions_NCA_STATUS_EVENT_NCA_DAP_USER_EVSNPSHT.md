# NcaApiSrvImplNotifySubscriptions(NCA_STATUS_EVENT_ *,NCA_DAP_USER_EVSNPSHT_ *)

- ea: `0x180007238`
- end: `0x180007334`
- name: `?NcaApiSrvImplNotifySubscriptions@@YAKPEAUNCA_STATUS_EVENT_@@PEAUNCA_DAP_USER_EVSNPSHT_@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct NCA_STATUS_EVENT_ *, struct NCA_DAP_USER_EVSNPSHT_ *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006c28`
- `0x180015f20`

## callees

- `0x180007238`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000731b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000731b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007257`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007257`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800072d0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800072d0`

## pseudocode

```c
__int64 __fastcall NcaApiSrvImplNotifySubscriptions(struct NCA_STATUS_EVENT_ *a1, struct NCA_DAP_USER_EVSNPSHT_ *a2)
{
  __int64 v4; // rbx
  int v5; // edx
  struct _RPC_ASYNC_STATE *v6; // rcx
  RPC_STATUS v7; // eax
  int Reply; // [rsp+60h] [rbp+18h] BYREF

  Reply = 0;
  EnterCriticalSection(&gNcaApiSrvImpl);
  do
  {
LABEL_2:
    v4 = qword_180028C70;
    v5 = 0;
    dword_180028CA8 = 0;
    if ( (__int64 *)qword_180028C70 == &qword_180028C70 )
      break;
    do
    {
      if ( *(_DWORD *)(v4 + 44)
        && *(_QWORD *)(v4 + 24)
        && (!a2 || *(_DWORD *)(v4 + 40) == *((_DWORD *)a2 + 153) && *(_QWORD *)(v4 + 16) < *((_QWORD *)a2 + 77)) )
      {
        *(_OWORD *)*(_QWORD *)(v4 + 32) = *(_OWORD *)a1;
        v6 = *(struct _RPC_ASYNC_STATE **)(v4 + 24);
        *(_QWORD *)(v4 + 24) = 0;
        *(_QWORD *)(v4 + 32) = 0;
        v7 = RpcAsyncCompleteCall(v6, &Reply);
        v5 = dword_180028CA8;
        if ( dword_180028CA8 )
          goto LABEL_2;
        if ( !v7 && a2 )
        {
          *(_QWORD *)(v4 + 16) = *((_QWORD *)a2 + 77);
          v5 = dword_180028CA8;
        }
      }
      v4 = *(_QWORD *)v4;
    }
    while ( (__int64 *)v4 != &qword_180028C70 );
  }
  while ( v5 );
  LeaveCriticalSection(&gNcaApiSrvImpl);
  return 0;
}

```

## disassembly

```asm
0x180007238  push    rbx
0x18000723a  push    rsi
0x18000723b  push    rdi
0x18000723c  push    r14
0x18000723e  sub     rsp, 28h
0x180007242  mov     rsi, rcx
0x180007245  mov     [rsp+48h+Reply], 0
0x18000724d  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x180007254  mov     rdi, rdx
0x180007257  call    cs:__imp_EnterCriticalSection
0x18000725e  nop     dword ptr [rax+rax+00h]
0x180007263  lea     r14, qword_180028C70
0x18000726a  mov     rbx, cs:qword_180028C70
0x180007271  xor     edx, edx
0x180007273  mov     cs:dword_180028CA8, edx
0x180007279  cmp     rbx, r14
0x18000727c  jz      loc_180007314
0x180007282  cmp     dword ptr [rbx+2Ch], 0
0x180007286  jz      short loc_180007300
0x180007288  cmp     qword ptr [rbx+18h], 0
0x18000728d  jz      short loc_180007300
0x18000728f  test    rdi, rdi
0x180007292  jz      short loc_1800072AC
0x180007294  mov     eax, [rdi+264h]
0x18000729a  cmp     [rbx+28h], eax
0x18000729d  jnz     short loc_180007300
0x18000729f  mov     rax, [rdi+268h]
0x1800072a6  cmp     [rbx+10h], rax
0x1800072aa  jnb     short loc_180007300
0x1800072ac  mov     rax, [rbx+20h]
0x1800072b0  lea     rdx, [rsp+48h+Reply]; Reply
0x1800072b5  movups  xmm0, xmmword ptr [rsi]
0x1800072b8  movdqu  xmmword ptr [rax], xmm0
0x1800072bc  mov     rcx, [rbx+18h]; pAsync
0x1800072c0  mov     qword ptr [rbx+18h], 0
0x1800072c8  mov     qword ptr [rbx+20h], 0
0x1800072d0  call    cs:__imp_RpcAsyncCompleteCall
0x1800072d7  nop     dword ptr [rax+rax+00h]
0x1800072dc  mov     edx, cs:dword_180028CA8
0x1800072e2  test    edx, edx
0x1800072e4  jnz     short loc_18000726A
0x1800072e6  test    eax, eax
0x1800072e8  jnz     short loc_180007300
0x1800072ea  test    rdi, rdi
0x1800072ed  jz      short loc_180007300
0x1800072ef  mov     rax, [rdi+268h]
0x1800072f6  mov     [rbx+10h], rax
0x1800072fa  mov     edx, cs:dword_180028CA8
0x180007300  mov     rbx, [rbx]
0x180007303  cmp     rbx, r14
0x180007306  jnz     loc_180007282
0x18000730c  test    edx, edx
0x18000730e  jnz     loc_18000726A
0x180007314  lea     rcx, ?gNcaApiSrvImpl@@3UNCA_API_SRV_IMPL_COMPONENT_@@A; lpCriticalSection
0x18000731b  call    cs:__imp_LeaveCriticalSection
0x180007322  nop     dword ptr [rax+rax+00h]
0x180007327  xor     eax, eax
0x180007329  add     rsp, 28h
0x18000732d  pop     r14
0x18000732f  pop     rdi
0x180007330  pop     rsi
0x180007331  pop     rbx
0x180007332  retn
```
