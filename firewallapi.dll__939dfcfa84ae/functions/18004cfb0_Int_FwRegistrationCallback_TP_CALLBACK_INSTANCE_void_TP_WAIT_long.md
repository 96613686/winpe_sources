# Int_FwRegistrationCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18004cfb0`
- end: `0x18004d240`
- name: `?Int_FwRegistrationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `656`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x180026c9c`
- `0x1800294b0`
- `0x18003336c`
- `0x18004cfb0`
- `0x18004d248`
- `0x180062010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18004d030`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004d030`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004d1be`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18004d1be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004d158`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004d158`
- `FWPolicyIOMgr!FwAppContainerChangeFree` at `0x18004d0c1`
- `FWPolicyIOMgr!FwAppContainerChangeFree` at `0x18004d0c1`

## pseudocode

```c
void __fastcall Int_FwRegistrationCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int64 v5; // r9
  FwPolicy2 *v6; // rcx
  __int64 v7; // rdx
  RPC_STATUS v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int inited; // eax
  unsigned int Reply; // [rsp+48h] [rbp-20h] BYREF

  Reply = 0;
  if ( Context )
  {
    v8 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(Context + 8), &Reply);
    *((_DWORD *)Context + 30) = v8;
    if ( v8 == 997 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11);
    _InterlockedExchange((volatile __int32 *)Context + 46, 0);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)Context + 45, 0, 0) != 1 )
    {
      v5 = *((unsigned int *)Context + 30);
      Reply = v5;
      if ( (_DWORD)v5 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 477;
          goto LABEL_5;
        }
      }
      else
      {
        (*((void (__fastcall **)(_QWORD, _QWORD))Context + 16))(*((_QWORD *)Context + 17), *((_QWORD *)Context + 21));
        FwAppContainerChangeFree(*((_QWORD *)Context + 21));
        *((_QWORD *)Context + 21) = 0;
        v5 = Reply;
        if ( Reply )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 478;
            goto LABEL_5;
          }
        }
        else
        {
          inited = Int_NetworkIsolationInitRegistrationRpcAsync((struct FW_INTCLIENT_REG_HANDLE_ *)Context);
          v5 = inited;
          Reply = inited;
          if ( inited )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 479;
              goto LABEL_5;
            }
          }
          else
          {
            SetThreadpoolWait(*((PTP_WAIT *)Context + 19), *((HANDLE *)Context + 18), 0);
            if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 480, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
            }
            Ndr64AsyncClientCall(
              (MIDL_STUBLESS_PROXY_INFO *)&FW_RESOURCE_INDICATION_ProxyInfo,
              9u,
              0,
              Context + 8,
              *(_QWORD *)Context,
              *((_QWORD *)Context + 20),
              Context + 168);
            *((_DWORD *)Context + 46) = 1;
          }
        }
      }
    }
  }
  else
  {
    v5 = 87;
    Reply = 87;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 476;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v5);
    }
  }
}

```

## disassembly

```asm
0x18004cfb0  mov     [rsp+arg_0], rbx
0x18004cfb5  mov     [rsp+arg_10], rsi
0x18004cfba  push    rdi
0x18004cfbb  sub     rsp, 60h
0x18004cfbf  mov     rax, cs:__security_cookie
0x18004cfc6  xor     rax, rsp
0x18004cfc9  mov     [rsp+68h+var_18], rax
0x18004cfce  mov     rbx, rdx
0x18004cfd1  mov     [rsp+68h+var_28], rdx
0x18004cfd6  mov     [rsp+68h+Reply], 0
0x18004cfde  test    rdx, rdx
0x18004cfe1  jnz     short loc_18004D027
0x18004cfe3  lea     r9d, [rdx+57h]
0x18004cfe7  mov     [rsp+68h+Reply], r9d
0x18004cfec  lea     rax, WPP_GLOBAL_Control
0x18004cff3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cffa  cmp     rcx, rax
0x18004cffd  jz      loc_18004D220
0x18004d003  test    byte ptr [rcx+1Ch], 1
0x18004d007  jz      loc_18004D220
0x18004d00d  mov     edx, 1DCh
0x18004d012  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004d019  mov     rcx, [rcx+10h]
0x18004d01d  call    WPP_SF_d
0x18004d022  jmp     loc_18004D220
0x18004d027  lea     rdx, [rsp+68h+Reply]; Reply
0x18004d02c  lea     rcx, [rbx+8]; pAsync
0x18004d030  call    cs:__imp_RpcAsyncCompleteCall
0x18004d037  nop     dword ptr [rax+rax+00h]
0x18004d03c  mov     [rbx+78h], eax
0x18004d03f  cmp     eax, 3E5h
0x18004d044  jnz     short loc_18004D04B
0x18004d046  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "phClntSubscription->Status != RPC_S_ASYNC_CALL_PENDING")
0x18004d04b  xor     eax, eax
0x18004d04d  xchg    eax, [rbx+0B8h]
0x18004d053  xor     ecx, ecx
0x18004d055  xor     eax, eax
0x18004d057  lock cmpxchg [rbx+0B4h], ecx
0x18004d05f  cmp     eax, 1
0x18004d062  jz      loc_18004D220
0x18004d068  mov     r9d, [rbx+78h]
0x18004d06c  mov     [rsp+68h+Reply], r9d
0x18004d071  test    r9d, r9d
0x18004d074  jz      short loc_18004D0A1
0x18004d076  lea     rax, WPP_GLOBAL_Control
0x18004d07d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d084  cmp     rcx, rax
0x18004d087  jz      loc_18004D220
0x18004d08d  test    byte ptr [rcx+1Ch], 1
0x18004d091  jz      loc_18004D220
0x18004d097  mov     edx, 1DDh
0x18004d09c  jmp     loc_18004D012
0x18004d0a1  lea     rdi, [rbx+0A8h]
0x18004d0a8  mov     rdx, [rdi]
0x18004d0ab  mov     rcx, [rbx+88h]
0x18004d0b2  mov     rax, [rbx+80h]
0x18004d0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0be  mov     rcx, [rdi]
0x18004d0c1  call    cs:__imp_FwAppContainerChangeFree
0x18004d0c8  nop     dword ptr [rax+rax+00h]
0x18004d0cd  mov     qword ptr [rdi], 0
0x18004d0d4  mov     r9d, [rsp+68h+Reply]
0x18004d0d9  test    r9d, r9d
0x18004d0dc  jz      short loc_18004D109
0x18004d0de  lea     rax, WPP_GLOBAL_Control
0x18004d0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d0ec  cmp     rcx, rax
0x18004d0ef  jz      loc_18004D220
0x18004d0f5  test    byte ptr [rcx+1Ch], 1
0x18004d0f9  jz      loc_18004D220
0x18004d0ff  mov     edx, 1DEh
0x18004d104  jmp     loc_18004D012
0x18004d109  mov     rcx, rbx; struct FW_INTCLIENT_REG_HANDLE_ *
0x18004d10c  call    ?Int_NetworkIsolationInitRegistrationRpcAsync@@YAKPEAUFW_INTCLIENT_REG_HANDLE_@@@Z; Int_NetworkIsolationInitRegistrationRpcAsync(FW_INTCLIENT_REG_HANDLE_ *)
0x18004d111  mov     r9d, eax
0x18004d114  mov     [rsp+68h+Reply], eax
0x18004d118  test    eax, eax
0x18004d11a  jz      short loc_18004D147
0x18004d11c  lea     rax, WPP_GLOBAL_Control
0x18004d123  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d12a  cmp     rcx, rax
0x18004d12d  jz      loc_18004D220
0x18004d133  test    byte ptr [rcx+1Ch], 1
0x18004d137  jz      loc_18004D220
0x18004d13d  mov     edx, 1DFh
0x18004d142  jmp     loc_18004D012
0x18004d147  xor     r8d, r8d; pftTimeout
0x18004d14a  mov     rdx, [rbx+90h]; h
0x18004d151  mov     rcx, [rbx+98h]; pwa
0x18004d158  call    cs:__imp_SetThreadpoolWait
0x18004d15f  nop     dword ptr [rax+rax+00h]
0x18004d164  nop
0x18004d165  lea     rax, WPP_GLOBAL_Control
0x18004d16c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d173  cmp     rcx, rax
0x18004d176  jz      short loc_18004D193
0x18004d178  test    byte ptr [rcx+1Ch], 4
0x18004d17c  jz      short loc_18004D193
0x18004d17e  mov     edx, 1E0h
0x18004d183  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004d18a  mov     rcx, [rcx+10h]
0x18004d18e  call    WPP_SF_
0x18004d193  mov     [rsp+68h+var_38], rdi
0x18004d198  mov     rax, [rbx+0A0h]
0x18004d19f  mov     [rsp+68h+var_40], rax
0x18004d1a4  mov     rax, [rbx]
0x18004d1a7  mov     [rsp+68h+var_48], rax
0x18004d1ac  lea     r9, [rbx+8]
0x18004d1b0  xor     r8d, r8d; pReturnValue
0x18004d1b3  lea     edx, [r8+9]; nProcNum
0x18004d1b7  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004d1be  call    cs:__imp_Ndr64AsyncClientCall
0x18004d1c5  nop     dword ptr [rax+rax+00h]
0x18004d1ca  jmp     short loc_18004D216
0x18004d1cc  mov     rbx, [rsp+68h+var_28]
0x18004d1d1  mov     dword ptr [rbx+0B8h], 0
0x18004d1db  mov     [rsp+68h+Reply], eax
0x18004d1df  test    eax, eax
0x18004d1e1  jz      short loc_18004D216
0x18004d1e3  lea     rdx, WPP_GLOBAL_Control
0x18004d1ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d1f1  cmp     rcx, rdx
0x18004d1f4  jz      short loc_18004D214
0x18004d1f6  test    byte ptr [rcx+1Ch], 1
0x18004d1fa  jz      short loc_18004D214
0x18004d1fc  mov     edx, 1E1h
0x18004d201  mov     r9d, eax
0x18004d204  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18004d20b  mov     rcx, [rcx+10h]
0x18004d20f  call    WPP_SF_d
0x18004d214  jmp     short loc_18004D220
0x18004d216  mov     dword ptr [rbx+0B8h], 1
0x18004d220  mov     rcx, [rsp+68h+var_18]
0x18004d225  xor     rcx, rsp; StackCookie
0x18004d228  call    __security_check_cookie
0x18004d22d  lea     r11, [rsp+68h+var_8]
0x18004d232  mov     rbx, [r11+10h]
0x18004d236  mov     rsi, [r11+20h]
0x18004d23a  mov     rsp, r11
0x18004d23d  pop     rdi
0x18004d23e  retn
0x18005fda6  push    rbp
0x18005fda8  sub     rsp, 40h
0x18005fdac  mov     rbp, rdx
0x18005fdaf  mov     rcx, [rcx]
0x18005fdb2  mov     ecx, [rcx]; ExceptionCode
0x18005fdb4  call    cs:__imp_RpcExceptionFilter
0x18005fdbb  nop     dword ptr [rax+rax+00h]
0x18005fdc0  nop
0x18005fdc1  add     rsp, 40h
0x18005fdc5  pop     rbp
0x18005fdc6  retn
```
