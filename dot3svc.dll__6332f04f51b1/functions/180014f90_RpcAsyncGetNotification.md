# RpcAsyncGetNotification

- ea: `0x180014f90`
- end: `0x18001514e`
- name: `RpcAsyncGetNotification`
- size: `446`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, struct _RPC_CLIENT_INFO *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180013bec`
- `0x180014a40`
- `0x180014f90`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800150d2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800150d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001502c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001502c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150a3`

## pseudocode

```c
void __fastcall RpcAsyncGetNotification(PRPC_ASYNC_STATE pAsync, struct _RTL_CRITICAL_SECTION *a2, _QWORD *a3)
{
  struct _LIST_ENTRY *v6; // rcx
  __int64 OwningThread_low; // rax
  int v8; // esi
  __int64 v9; // rax
  unsigned int Reply; // [rsp+40h] [rbp+8h] BYREF

  Reply = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 51, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, a2);
    v6 = WPP_GLOBAL_Control;
  }
  if ( pAsync && a2 && a3 )
  {
    if ( !g_bRpcServerStarted )
    {
      Reply = 1722;
      goto LABEL_20;
    }
    EnterCriticalSection(a2 + 53);
    if ( LODWORD(a2[1].DebugInfo) )
    {
      OwningThread_low = LODWORD(a2[52].OwningThread);
      if ( (_DWORD)OwningThread_low == HIDWORD(a2[52].OwningThread) )
      {
        a2->SpinCount = (ULONG_PTR)a3;
        a2->LockSemaphore = pAsync;
        *a3 = 0;
        v8 = 0;
LABEL_16:
        LeaveCriticalSection(a2 + 53);
        if ( !v8 )
          goto LABEL_26;
        v6 = WPP_GLOBAL_Control;
        goto LABEL_19;
      }
      *a3 = *((_QWORD *)&a2[1].LockCount + OwningThread_low);
      v9 = LODWORD(a2[52].OwningThread);
      a2->LockSemaphore = pAsync;
      a2->SpinCount = (ULONG_PTR)a3;
      *((_QWORD *)&a2[1].LockCount + v9) = 0;
      LODWORD(a2[52].OwningThread) = (unsigned __int8)(LODWORD(a2[52].OwningThread) + 1);
    }
    else
    {
      Reply = 13;
    }
    v8 = 1;
    LocalSendNotificaton((struct _RPC_CLIENT_INFO *)a2);
    goto LABEL_16;
  }
  Reply = 87;
LABEL_19:
  if ( !pAsync )
    goto LABEL_27;
LABEL_20:
  if ( !Reply )
    goto LABEL_27;
  if ( !RpcAsyncCompleteCall(pAsync, &Reply) )
  {
LABEL_26:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 52, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
    goto LABEL_26;
  }
LABEL_27:
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v6[1].Blink) >= 4u && (BYTE4(v6[1].Blink) & 1) != 0 )
    WPP_SF_d(v6[1].Flink, 53, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, Reply);
}

```

## disassembly

```asm
0x180014f90  mov     [rsp+arg_8], rbx
0x180014f95  mov     [rsp+arg_10], rbp
0x180014f9a  push    rsi
0x180014f9b  push    rdi
0x180014f9c  push    r12
0x180014f9e  sub     rsp, 20h
0x180014fa2  mov     rsi, r8
0x180014fa5  mov     [rsp+38h+Reply], 0
0x180014fad  mov     rbx, rdx
0x180014fb0  mov     rdi, rcx
0x180014fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fba  lea     r12, WPP_GLOBAL_Control
0x180014fc1  cmp     rcx, r12
0x180014fc4  jz      short loc_180014FF1
0x180014fc6  cmp     byte ptr [rcx+19h], 4
0x180014fca  jb      short loc_180014FF1
0x180014fcc  test    byte ptr [rcx+1Ch], 1
0x180014fd0  jz      short loc_180014FF1
0x180014fd2  mov     rcx, [rcx+10h]
0x180014fd6  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014fdd  mov     edx, 33h ; '3'
0x180014fe2  mov     r9, rbx
0x180014fe5  call    WPP_SF_q
0x180014fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ff1  test    rdi, rdi
0x180014ff4  jz      loc_1800150B6
0x180014ffa  test    rbx, rbx
0x180014ffd  jz      loc_1800150B6
0x180015003  test    rsi, rsi
0x180015006  jz      loc_1800150B6
0x18001500c  cmp     cs:?g_bRpcServerStarted@@3EA, 0; uchar g_bRpcServerStarted
0x180015013  jnz     short loc_180015022
0x180015015  mov     [rsp+38h+Reply], 6BAh
0x18001501d  jmp     loc_1800150C3
0x180015022  lea     rbp, [rbx+848h]
0x180015029  mov     rcx, rbp; lpCriticalSection
0x18001502c  call    cs:__imp_EnterCriticalSection
0x180015032  cmp     dword ptr [rbx+28h], 0
0x180015036  jnz     short loc_180015042
0x180015038  mov     [rsp+38h+Reply], 0Dh
0x180015040  jmp     short loc_180015093
0x180015042  mov     eax, [rbx+830h]
0x180015048  cmp     eax, [rbx+834h]
0x18001504e  jnz     short loc_180015063
0x180015050  mov     [rbx+20h], rsi
0x180015054  mov     [rbx+18h], rdi
0x180015058  mov     qword ptr [rsi], 0
0x18001505f  xor     esi, esi
0x180015061  jmp     short loc_1800150A0
0x180015063  mov     rcx, [rbx+rax*8+30h]
0x180015068  mov     [rsi], rcx
0x18001506b  mov     eax, [rbx+830h]
0x180015071  mov     [rbx+18h], rdi
0x180015075  mov     [rbx+20h], rsi
0x180015079  mov     qword ptr [rbx+rax*8+30h], 0
0x180015082  mov     eax, [rbx+830h]
0x180015088  inc     eax
0x18001508a  movzx   eax, al
0x18001508d  mov     [rbx+830h], eax
0x180015093  mov     rcx, rbx; struct _RPC_CLIENT_INFO *
0x180015096  mov     esi, 1
0x18001509b  call    ?LocalSendNotificaton@@YAKPEAU_RPC_CLIENT_INFO@@@Z; LocalSendNotificaton(_RPC_CLIENT_INFO *)
0x1800150a0  mov     rcx, rbp; lpCriticalSection
0x1800150a3  call    cs:__imp_LeaveCriticalSection
0x1800150a9  test    esi, esi
0x1800150ab  jz      short loc_180015109
0x1800150ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150b4  jmp     short loc_1800150BE
0x1800150b6  mov     [rsp+38h+Reply], 57h ; 'W'
0x1800150be  test    rdi, rdi
0x1800150c1  jz      short loc_180015110
0x1800150c3  cmp     [rsp+38h+Reply], 0
0x1800150c8  jz      short loc_180015110
0x1800150ca  lea     rdx, [rsp+38h+Reply]; Reply
0x1800150cf  mov     rcx, rdi; pAsync
0x1800150d2  call    cs:__imp_RpcAsyncCompleteCall
0x1800150d8  test    eax, eax
0x1800150da  jz      short loc_180015109
0x1800150dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150e3  cmp     rcx, r12
0x1800150e6  jz      short loc_18001513B
0x1800150e8  cmp     byte ptr [rcx+19h], 1
0x1800150ec  jb      short loc_180015110
0x1800150ee  test    byte ptr [rcx+1Ch], 1
0x1800150f2  jz      short loc_180015110
0x1800150f4  mov     rcx, [rcx+10h]
0x1800150f8  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800150ff  mov     edx, 34h ; '4'
0x180015104  call    WPP_SF_
0x180015109  mov     rcx, cs:WPP_GLOBAL_Control
0x180015110  cmp     rcx, r12
0x180015113  jz      short loc_18001513B
0x180015115  cmp     byte ptr [rcx+19h], 4
0x180015119  jb      short loc_18001513B
0x18001511b  test    byte ptr [rcx+1Ch], 1
0x18001511f  jz      short loc_18001513B
0x180015121  mov     r9d, [rsp+38h+Reply]
0x180015126  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x18001512d  mov     rcx, [rcx+10h]
0x180015131  mov     edx, 35h ; '5'
0x180015136  call    WPP_SF_d
0x18001513b  mov     rbx, [rsp+38h+arg_8]
0x180015140  mov     rbp, [rsp+38h+arg_10]
0x180015145  add     rsp, 20h
0x180015149  pop     r12
0x18001514b  pop     rdi
0x18001514c  pop     rsi
0x18001514d  retn
```
