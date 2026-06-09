# LanSvcStartRPCServer(void)

- ea: `0x1800142f4`
- end: `0x18001464f`
- name: `?LanSvcStartRPCServer@@YAKXZ`
- size: `859`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aac0`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x1800142f4`

## import_xrefs

- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180014457`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180014457`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180014485`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800144ce`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180014514`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180014485`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x1800144ce`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180014514`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180014574`
- `RPCRT4!RpcServerRegisterIfEx` at `0x180014574`
- `RPCRT4!RpcEpRegisterW` at `0x1800145c4`
- `RPCRT4!RpcEpRegisterW` at `0x1800145c4`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180014608`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180014608`
- `RPCRT4!RpcServerUseProtseqW` at `0x180014362`
- `RPCRT4!RpcServerUseProtseqW` at `0x180014362`
- `RPCRT4!RpcStringFreeW` at `0x1800143cc`
- `RPCRT4!RpcStringFreeW` at `0x1800143cc`
- `RPCRT4!RpcBindingVectorFree` at `0x1800143b2`
- `RPCRT4!RpcBindingVectorFree` at `0x1800143b2`
- `RPCRT4!RpcServerInqBindings` at `0x180014413`
- `RPCRT4!RpcServerInqBindings` at `0x180014413`

## string_xrefs

- `0x1800145b3`: `Lan Service`

## pseudocode

```c
__int64 LanSvcStartRPCServer(void)
{
  unsigned int v0; // ebx
  struct _LIST_ENTRY *v1; // rcx
  unsigned int v2; // eax
  __int64 v3; // rdx
  RPC_STATUS v5; // eax
  unsigned int v6; // eax
  RPC_WSTR String; // [rsp+50h] [rbp+8h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+58h] [rbp+10h] BYREF

  v0 = 0;
  BindingVector = 0;
  String = 0;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 30, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  if ( !g_bRpcServerStarted )
  {
    v2 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
    v0 = v2;
    if ( v2 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v3 = 31;
LABEL_11:
        WPP_SF_d(v1[1].Flink, v3, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, v2);
LABEL_12:
        v1 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v2 = RpcServerInqBindings(&BindingVector);
      v0 = v2;
      if ( v2 )
      {
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          v3 = 32;
          goto LABEL_11;
        }
      }
      else
      {
        v5 = RpcServerInqDefaultPrincNameW(0x10u, &String);
        v0 = v5;
        if ( v5 == 1749 )
        {
          String = 0;
        }
        else if ( v5 )
        {
          goto LABEL_12;
        }
        v2 = RpcServerRegisterAuthInfoW(0, 0x10u, 0, 0);
        v0 = v2;
        if ( v2 )
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control[1].Blink)
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v3 = 33;
            goto LABEL_11;
          }
        }
        else
        {
          v2 = RpcServerRegisterAuthInfoW(String, 0x10u, 0, 0);
          v0 = v2;
          if ( v2 )
          {
            v1 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control[1].Blink)
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              v3 = 34;
              goto LABEL_11;
            }
          }
          else
          {
            v2 = RpcServerRegisterAuthInfoW(0, 9u, 0, 0);
            v0 = v2;
            if ( v2 )
            {
              v1 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control[1].Blink)
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                v3 = 35;
                goto LABEL_11;
              }
            }
            else
            {
              v2 = RpcServerRegisterIfEx(qword_180042360, 0, 0, 0x29u, 0x4D2u, LocalSecurityCheckCallback);
              v0 = v2;
              if ( v2 )
              {
                v1 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control[1].Blink)
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                {
                  v3 = 36;
                  goto LABEL_11;
                }
              }
              else
              {
                v6 = RpcEpRegisterW(qword_180042360, BindingVector, 0, (RPC_WSTR)L"Lan Service");
                v0 = v6;
                if ( v6 )
                {
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control[1].Blink)
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 37, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, v6);
                  }
                  RpcServerUnregisterIfEx(qword_180042360, 0, 1);
                  goto LABEL_12;
                }
                v1 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control[1].Flink, 38, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
                  v1 = WPP_GLOBAL_Control;
                }
                g_bRpcServerStarted = 1;
              }
            }
          }
        }
      }
    }
  }
  if ( BindingVector )
  {
    RpcBindingVectorFree(&BindingVector);
    v1 = WPP_GLOBAL_Control;
  }
  if ( String )
  {
    RpcStringFreeW(&String);
    v1 = WPP_GLOBAL_Control;
  }
  if ( v1 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v1[1].Blink) >= 4u && (BYTE4(v1[1].Blink) & 1) != 0 )
    WPP_SF_d(v1[1].Flink, 39, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x1800142f4  mov     [rsp+arg_10], rbx
0x1800142f9  push    rbp
0x1800142fa  push    rdi
0x1800142fb  push    r15
0x1800142fd  sub     rsp, 30h
0x180014301  xor     ebx, ebx
0x180014303  mov     [rsp+48h+BindingVector], rbx
0x180014308  mov     [rsp+48h+String], rbx
0x18001430d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014314  lea     rbp, WPP_GLOBAL_Control
0x18001431b  lea     edi, [rbx+1]
0x18001431e  lea     r15, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014325  cmp     rcx, rbp
0x180014328  jz      short loc_18001434C
0x18001432a  cmp     byte ptr [rcx+19h], 4
0x18001432e  jb      short loc_18001434C
0x180014330  test    [rcx+1Ch], dil
0x180014334  jz      short loc_18001434C
0x180014336  mov     rcx, [rcx+10h]
0x18001433a  lea     edx, [rbx+1Eh]
0x18001433d  mov     r8, r15
0x180014340  call    WPP_SF_
0x180014345  mov     rcx, cs:WPP_GLOBAL_Control
0x18001434c  cmp     cs:?g_bRpcServerStarted@@3EA, bl; uchar g_bRpcServerStarted
0x180014352  jnz     short loc_1800143A5
0x180014354  xor     r8d, r8d; SecurityDescriptor
0x180014357  lea     rcx, aNcalrpc; "ncalrpc"
0x18001435e  lea     edx, [r8+0Ah]; MaxCalls
0x180014362  call    cs:__imp_RpcServerUseProtseqW
0x180014368  mov     ebx, eax
0x18001436a  test    eax, eax
0x18001436c  jz      loc_18001440E
0x180014372  mov     rcx, cs:WPP_GLOBAL_Control
0x180014379  cmp     rcx, rbp
0x18001437c  jz      short loc_1800143A5
0x18001437e  cmp     [rcx+19h], dil
0x180014382  jb      short loc_1800143A5
0x180014384  test    [rcx+1Ch], dil
0x180014388  jz      short loc_1800143A5
0x18001438a  mov     edx, 1Fh
0x18001438f  mov     rcx, [rcx+10h]
0x180014393  mov     r9d, eax
0x180014396  mov     r8, r15
0x180014399  call    WPP_SF_d
0x18001439e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143a5  cmp     [rsp+48h+BindingVector], 0
0x1800143ab  jz      short loc_1800143BF
0x1800143ad  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x1800143b2  call    cs:__imp_RpcBindingVectorFree
0x1800143b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143bf  cmp     [rsp+48h+String], 0
0x1800143c5  jz      short loc_1800143D9
0x1800143c7  lea     rcx, [rsp+48h+String]; String
0x1800143cc  call    cs:__imp_RpcStringFreeW
0x1800143d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143d9  cmp     rcx, rbp
0x1800143dc  jz      short loc_1800143FE
0x1800143de  cmp     byte ptr [rcx+19h], 4
0x1800143e2  jb      short loc_1800143FE
0x1800143e4  test    [rcx+1Ch], dil
0x1800143e8  jz      short loc_1800143FE
0x1800143ea  mov     rcx, [rcx+10h]
0x1800143ee  mov     edx, 27h ; '''
0x1800143f3  mov     r9d, ebx
0x1800143f6  mov     r8, r15
0x1800143f9  call    WPP_SF_d
0x1800143fe  mov     eax, ebx
0x180014400  mov     rbx, [rsp+48h+arg_10]
0x180014405  add     rsp, 30h
0x180014409  pop     r15
0x18001440b  pop     rdi
0x18001440c  pop     rbp
0x18001440d  retn
0x18001440e  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x180014413  call    cs:__imp_RpcServerInqBindings
0x180014419  mov     ebx, eax
0x18001441b  test    eax, eax
0x18001441d  jz      short loc_18001444D
0x18001441f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014426  cmp     rcx, rbp
0x180014429  jz      loc_1800143A5
0x18001442f  cmp     [rcx+19h], dil
0x180014433  jb      loc_1800143A5
0x180014439  test    [rcx+1Ch], dil
0x18001443d  jz      loc_1800143A5
0x180014443  mov     edx, 20h ; ' '
0x180014448  jmp     loc_18001438F
0x18001444d  lea     rdx, [rsp+48h+String]; PrincName
0x180014452  mov     ecx, 10h; AuthnSvc
0x180014457  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x18001445d  mov     ebx, eax
0x18001445f  cmp     eax, 6D5h
0x180014464  jnz     short loc_180014471
0x180014466  mov     [rsp+48h+String], 0
0x18001446f  jmp     short loc_180014479
0x180014471  test    eax, eax
0x180014473  jnz     loc_18001439E
0x180014479  xor     r9d, r9d; Arg
0x18001447c  xor     r8d, r8d; GetKeyFn
0x18001447f  xor     ecx, ecx; ServerPrincName
0x180014481  lea     edx, [r9+10h]; AuthnSvc
0x180014485  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18001448b  mov     ebx, eax
0x18001448d  test    eax, eax
0x18001448f  jz      short loc_1800144BF
0x180014491  mov     rcx, cs:WPP_GLOBAL_Control
0x180014498  cmp     rcx, rbp
0x18001449b  jz      loc_1800143A5
0x1800144a1  cmp     [rcx+19h], dil
0x1800144a5  jb      loc_1800143A5
0x1800144ab  test    [rcx+1Ch], dil
0x1800144af  jz      loc_1800143A5
0x1800144b5  mov     edx, 21h ; '!'
0x1800144ba  jmp     loc_18001438F
0x1800144bf  mov     rcx, [rsp+48h+String]; ServerPrincName
0x1800144c4  xor     r9d, r9d; Arg
0x1800144c7  xor     r8d, r8d; GetKeyFn
0x1800144ca  lea     edx, [r9+10h]; AuthnSvc
0x1800144ce  call    cs:__imp_RpcServerRegisterAuthInfoW
0x1800144d4  mov     ebx, eax
0x1800144d6  test    eax, eax
0x1800144d8  jz      short loc_180014508
0x1800144da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144e1  cmp     rcx, rbp
0x1800144e4  jz      loc_1800143A5
0x1800144ea  cmp     [rcx+19h], dil
0x1800144ee  jb      loc_1800143A5
0x1800144f4  test    [rcx+1Ch], dil
0x1800144f8  jz      loc_1800143A5
0x1800144fe  mov     edx, 22h ; '"'
0x180014503  jmp     loc_18001438F
0x180014508  xor     r9d, r9d; Arg
0x18001450b  xor     r8d, r8d; GetKeyFn
0x18001450e  xor     ecx, ecx; ServerPrincName
0x180014510  lea     edx, [r9+9]; AuthnSvc
0x180014514  call    cs:__imp_RpcServerRegisterAuthInfoW
0x18001451a  mov     ebx, eax
0x18001451c  test    eax, eax
0x18001451e  jz      short loc_18001454E
0x180014520  mov     rcx, cs:WPP_GLOBAL_Control
0x180014527  cmp     rcx, rbp
0x18001452a  jz      loc_1800143A5
0x180014530  cmp     [rcx+19h], dil
0x180014534  jb      loc_1800143A5
0x18001453a  test    [rcx+1Ch], dil
0x18001453e  jz      loc_1800143A5
0x180014544  mov     edx, 23h ; '#'
0x180014549  jmp     loc_18001438F
0x18001454e  lea     rax, ?LocalSecurityCheckCallback@@YAJPEAPEAXPEAX@Z; LocalSecurityCheckCallback(void * *,void *)
0x180014555  mov     r9d, 29h ; ')'; Flags
0x18001455b  mov     [rsp+48h+IfCallback], rax; IfCallback
0x180014560  lea     rcx, qword_180042360; IfSpec
0x180014567  xor     r8d, r8d; MgrEpv
0x18001456a  mov     [rsp+48h+MaxCalls], 4D2h; MaxCalls
0x180014572  xor     edx, edx; MgrTypeUuid
0x180014574  call    cs:__imp_RpcServerRegisterIfEx
0x18001457a  mov     ebx, eax
0x18001457c  test    eax, eax
0x18001457e  jz      short loc_1800145AE
0x180014580  mov     rcx, cs:WPP_GLOBAL_Control
0x180014587  cmp     rcx, rbp
0x18001458a  jz      loc_1800143A5
0x180014590  cmp     [rcx+19h], dil
0x180014594  jb      loc_1800143A5
0x18001459a  test    [rcx+1Ch], dil
0x18001459e  jz      loc_1800143A5
0x1800145a4  mov     edx, 24h ; '$'
0x1800145a9  jmp     loc_18001438F
0x1800145ae  mov     rdx, [rsp+48h+BindingVector]; BindingVector
0x1800145b3  lea     r9, Annotation; "Lan Service"
0x1800145ba  xor     r8d, r8d; UuidVector
0x1800145bd  lea     rcx, qword_180042360; IfSpec
0x1800145c4  call    cs:__imp_RpcEpRegisterW
0x1800145ca  mov     ebx, eax
0x1800145cc  test    eax, eax
0x1800145ce  jz      short loc_180014613
0x1800145d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145d7  cmp     rcx, rbp
0x1800145da  jz      short loc_1800145FC
0x1800145dc  cmp     [rcx+19h], dil
0x1800145e0  jb      short loc_1800145FC
0x1800145e2  test    [rcx+1Ch], dil
0x1800145e6  jz      short loc_1800145FC
0x1800145e8  mov     rcx, [rcx+10h]
0x1800145ec  mov     edx, 25h ; '%'
0x1800145f1  mov     r9d, eax
0x1800145f4  mov     r8, r15
0x1800145f7  call    WPP_SF_d
0x1800145fc  mov     r8d, edi; RundownContextHandles
0x1800145ff  lea     rcx, qword_180042360; IfSpec
0x180014606  xor     edx, edx; MgrTypeUuid
0x180014608  call    cs:__imp_RpcServerUnregisterIfEx
0x18001460e  jmp     loc_18001439E
0x180014613  mov     rcx, cs:WPP_GLOBAL_Control
0x18001461a  cmp     rcx, rbp
0x18001461d  jz      short loc_180014643
0x18001461f  cmp     byte ptr [rcx+19h], 4
0x180014623  jb      short loc_180014643
0x180014625  test    [rcx+1Ch], dil
0x180014629  jz      short loc_180014643
0x18001462b  mov     rcx, [rcx+10h]
0x18001462f  mov     edx, 26h ; '&'
0x180014634  mov     r8, r15
0x180014637  call    WPP_SF_
0x18001463c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014643  mov     cs:?g_bRpcServerStarted@@3EA, dil; uchar g_bRpcServerStarted
0x18001464a  jmp     loc_1800143A5
```
