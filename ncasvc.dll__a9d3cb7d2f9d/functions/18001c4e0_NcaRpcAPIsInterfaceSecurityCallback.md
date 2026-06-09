# NcaRpcAPIsInterfaceSecurityCallback

- ea: `0x18001c4e0`
- end: `0x18001c8d7`
- name: `NcaRpcAPIsInterfaceSecurityCallback`
- size: `1015`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b2a0`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180019784`
- `0x18001c4e0`
- `0x18001c8e0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18001c866`
- `RPCRT4!RpcStringFreeW` at `0x18001c883`
- `RPCRT4!RpcStringFreeW` at `0x18001c866`
- `RPCRT4!RpcStringFreeW` at `0x18001c883`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001c548`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001c548`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18001c5dc`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18001c5dc`
- `RPCRT4!RpcStringBindingParseW` at `0x18001c669`
- `RPCRT4!RpcStringBindingParseW` at `0x18001c669`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18001c76d`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18001c76d`

## pseudocode

```c
__int64 __fastcall NcaRpcAPIsInterfaceSecurityCallback(__int64 a1, __int64 a2, void *a3)
{
  RPC_STATUS IsClientLocal; // eax
  unsigned int v5; // ebx
  PVOID *v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r9
  RPC_STATUS v9; // eax
  RPC_STATUS v10; // eax
  unsigned __int64 i; // rax
  RPC_WSTR v12; // rcx
  int v13; // r10d
  int v14; // r8d
  RPC_STATUS v15; // eax
  int IsAccessGranted; // eax
  unsigned int v17; // eax
  __int64 v18; // r10
  RPC_WSTR Protseq; // [rsp+30h] [rbp-10h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-8h] BYREF
  unsigned int AuthnLevel; // [rsp+70h] [rbp+30h] BYREF
  int v23; // [rsp+74h] [rbp+34h]
  unsigned int ClientLocalFlag; // [rsp+78h] [rbp+38h] BYREF
  int v25; // [rsp+7Ch] [rbp+3Ch]
  int v26; // [rsp+88h] [rbp+48h]

  v25 = HIDWORD(a2);
  v23 = HIDWORD(a1);
  ClientLocalFlag = 0;
  StringBinding = 0;
  Protseq = 0;
  AuthnLevel = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids);
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  v5 = IsClientLocal;
  if ( IsClientLocal )
  {
    if ( IsClientLocal > 0 )
      v5 = (unsigned __int16)IsClientLocal | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 22;
    goto LABEL_10;
  }
  if ( !ClientLocalFlag )
  {
    if ( (_DWORD)xmmword_1800295B0 )
      goto LABEL_18;
LABEL_15:
    v8 = 2147942405LL;
    v5 = -2147024891;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 23;
      goto LABEL_67;
    }
    goto LABEL_69;
  }
  if ( (_DWORD)xmmword_1800295B0 )
    goto LABEL_15;
LABEL_18:
  v9 = RpcBindingToStringBindingW(a3, &StringBinding);
  v5 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 24;
    goto LABEL_10;
  }
  if ( !StringBinding )
  {
    v8 = 2147942414LL;
    v5 = -2147024882;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 25;
      goto LABEL_67;
    }
    goto LABEL_69;
  }
  v10 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
  v5 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 26;
    goto LABEL_10;
  }
  if ( !Protseq )
  {
    v8 = 2147942414LL;
    v5 = -2147024882;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_71;
    v7 = 27;
    goto LABEL_67;
  }
  for ( i = 0; i < *((_QWORD *)&xmmword_1800295B0 + 1); ++i )
  {
    v12 = Protseq;
    do
    {
      v13 = *(RPC_WSTR)((char *)v12 + *((_QWORD *)xmmword_1800295C0 + i) - (_QWORD)Protseq);
      v14 = *v12 - v13;
      if ( v14 )
        break;
      ++v12;
    }
    while ( v13 );
    if ( !v14 )
      break;
  }
  if ( i == *((_QWORD *)&xmmword_1800295B0 + 1) )
  {
    v8 = 2147942405LL;
    v5 = -2147024891;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 28;
      goto LABEL_67;
    }
    goto LABEL_69;
  }
  v15 = RpcBindingInqAuthClientW(a3, 0, 0, &AuthnLevel, 0, 0);
  v5 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v5 = (unsigned __int16)v15 | 0x80070000;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_69;
    v7 = 29;
LABEL_10:
    v8 = v5;
LABEL_67:
    WPP_SF_d(v6[2], v7, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, v8);
    goto LABEL_68;
  }
  if ( AuthnLevel >= 6 )
  {
    v5 = 0;
    if ( *(&gNcaRpcAPIs + 1) )
    {
      IsAccessGranted = NcaRpcAPIsIsAccessGranted(*(&gNcaRpcAPIs + 1), a3, 0x20000u);
      v5 = IsAccessGranted;
      if ( IsAccessGranted < 0 )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 31;
          v8 = (unsigned int)IsAccessGranted;
          goto LABEL_67;
        }
        goto LABEL_69;
      }
      if ( !v26 )
      {
        v8 = 2147942405LL;
        v5 = -2147024891;
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 32;
          goto LABEL_67;
        }
        goto LABEL_69;
      }
    }
LABEL_68:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_69;
  }
  v8 = 2147942405LL;
  v5 = -2147024891;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 30;
    goto LABEL_67;
  }
LABEL_69:
  if ( Protseq )
  {
    RpcStringFreeW(&Protseq);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_71:
  if ( StringBinding )
  {
    RpcStringFreeW(&StringBinding);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
  {
    v17 = NcaHResultToWindowsError(v5);
    WPP_SF_d(*(_QWORD *)(v18 + 16), 33, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, v17);
  }
  return NcaHResultToWindowsError(v5);
}

```

## disassembly

```asm
0x18001c4e0  mov     [rsp-28h+arg_10], rbx
0x18001c4e5  mov     qword ptr [rsp-28h+ClientLocalFlag], rdx
0x18001c4ea  mov     qword ptr [rsp-28h+AuthnLevel], rcx
0x18001c4ef  push    rbp
0x18001c4f0  push    rsi
0x18001c4f1  push    rdi
0x18001c4f2  push    r14
0x18001c4f4  push    r15
0x18001c4f6  mov     rbp, rsp
0x18001c4f9  sub     rsp, 40h
0x18001c4fd  xor     esi, esi
0x18001c4ff  mov     rdi, r8
0x18001c502  mov     [rbp+ClientLocalFlag], esi
0x18001c505  mov     [rbp+StringBinding], rsi
0x18001c509  mov     [rbp+Protseq], rsi
0x18001c50d  mov     [rbp+AuthnLevel], esi
0x18001c510  mov     [rbp+arg_18], esi
0x18001c513  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c51a  lea     r14, WPP_GLOBAL_Control
0x18001c521  lea     r15, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001c528  cmp     rcx, r14
0x18001c52b  jz      short loc_18001C542
0x18001c52d  test    byte ptr [rcx+1Ch], 8
0x18001c531  jz      short loc_18001C542
0x18001c533  mov     rcx, [rcx+10h]
0x18001c537  lea     edx, [rsi+15h]
0x18001c53a  mov     r8, r15
0x18001c53d  call    WPP_SF_
0x18001c542  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x18001c546  xor     ecx, ecx; BindingHandle
0x18001c548  call    cs:__imp_I_RpcBindingIsClientLocal
0x18001c54f  nop     dword ptr [rax+rax+00h]
0x18001c554  mov     ebx, eax
0x18001c556  test    eax, eax
0x18001c558  jz      short loc_18001C58D
0x18001c55a  jle     short loc_18001C565
0x18001c55c  movzx   ebx, ax
0x18001c55f  or      ebx, 80070000h
0x18001c565  mov     r10, cs:WPP_GLOBAL_Control
0x18001c56c  cmp     r10, r14
0x18001c56f  jz      loc_18001C85C
0x18001c575  test    byte ptr [r10+1Ch], 1
0x18001c57a  jz      loc_18001C85C
0x18001c580  mov     edx, 16h
0x18001c585  mov     r9d, ebx
0x18001c588  jmp     loc_18001C849
0x18001c58d  mov     ecx, [rbp+ClientLocalFlag]
0x18001c590  mov     rax, qword ptr cs:xmmword_1800295B0
0x18001c597  test    ecx, ecx
0x18001c599  jnz     short loc_18001C5A3
0x18001c59b  test    eax, eax
0x18001c59d  jz      short loc_18001C5A7
0x18001c59f  test    ecx, ecx
0x18001c5a1  jz      short loc_18001C5D5
0x18001c5a3  test    eax, eax
0x18001c5a5  jz      short loc_18001C5D5
0x18001c5a7  mov     r9d, 80070005h
0x18001c5ad  mov     ebx, r9d
0x18001c5b0  mov     r10, cs:WPP_GLOBAL_Control
0x18001c5b7  cmp     r10, r14
0x18001c5ba  jz      loc_18001C85C
0x18001c5c0  test    byte ptr [r10+1Ch], 1
0x18001c5c5  jz      loc_18001C85C
0x18001c5cb  mov     edx, 17h
0x18001c5d0  jmp     loc_18001C849
0x18001c5d5  lea     rdx, [rbp+StringBinding]; StringBinding
0x18001c5d9  mov     rcx, rdi; Binding
0x18001c5dc  call    cs:__imp_RpcBindingToStringBindingW
0x18001c5e3  nop     dword ptr [rax+rax+00h]
0x18001c5e8  mov     ebx, eax
0x18001c5ea  test    eax, eax
0x18001c5ec  jz      short loc_18001C61E
0x18001c5ee  jle     short loc_18001C5F9
0x18001c5f0  movzx   ebx, ax
0x18001c5f3  or      ebx, 80070000h
0x18001c5f9  mov     r10, cs:WPP_GLOBAL_Control
0x18001c600  cmp     r10, r14
0x18001c603  jz      loc_18001C85C
0x18001c609  test    byte ptr [r10+1Ch], 1
0x18001c60e  jz      loc_18001C85C
0x18001c614  mov     edx, 18h
0x18001c619  jmp     loc_18001C585
0x18001c61e  cmp     [rbp+StringBinding], rsi
0x18001c622  jnz     short loc_18001C652
0x18001c624  mov     r9d, 8007000Eh
0x18001c62a  mov     ebx, r9d
0x18001c62d  mov     r10, cs:WPP_GLOBAL_Control
0x18001c634  cmp     r10, r14
0x18001c637  jz      loc_18001C85C
0x18001c63d  test    byte ptr [r10+1Ch], 1
0x18001c642  jz      loc_18001C85C
0x18001c648  mov     edx, 19h
0x18001c64d  jmp     loc_18001C849
0x18001c652  mov     rcx, [rbp+StringBinding]; StringBinding
0x18001c656  lea     r8, [rbp+Protseq]; Protseq
0x18001c65a  mov     [rsp+40h+NetworkOptions], rsi; NetworkOptions
0x18001c65f  xor     r9d, r9d; NetworkAddr
0x18001c662  xor     edx, edx; ObjUuid
0x18001c664  mov     [rsp+40h+Endpoint], rsi; Endpoint
0x18001c669  call    cs:__imp_RpcStringBindingParseW
0x18001c670  nop     dword ptr [rax+rax+00h]
0x18001c675  mov     ebx, eax
0x18001c677  test    eax, eax
0x18001c679  jz      short loc_18001C6AB
0x18001c67b  jle     short loc_18001C686
0x18001c67d  movzx   ebx, ax
0x18001c680  or      ebx, 80070000h
0x18001c686  mov     r10, cs:WPP_GLOBAL_Control
0x18001c68d  cmp     r10, r14
0x18001c690  jz      loc_18001C85C
0x18001c696  test    byte ptr [r10+1Ch], 1
0x18001c69b  jz      loc_18001C85C
0x18001c6a1  mov     edx, 1Ah
0x18001c6a6  jmp     loc_18001C585
0x18001c6ab  cmp     [rbp+Protseq], rsi
0x18001c6af  jnz     short loc_18001C6DF
0x18001c6b1  mov     r9d, 8007000Eh
0x18001c6b7  mov     ebx, r9d
0x18001c6ba  mov     r10, cs:WPP_GLOBAL_Control
0x18001c6c1  cmp     r10, r14
0x18001c6c4  jz      loc_18001C879
0x18001c6ca  test    byte ptr [r10+1Ch], 1
0x18001c6cf  jz      loc_18001C879
0x18001c6d5  mov     edx, 1Bh
0x18001c6da  jmp     loc_18001C849
0x18001c6df  mov     rdx, qword ptr cs:xmmword_1800295B0+8
0x18001c6e6  mov     rax, rsi
0x18001c6e9  test    rdx, rdx
0x18001c6ec  jz      short loc_18001C724
0x18001c6ee  mov     r11, qword ptr cs:xmmword_1800295C0
0x18001c6f5  mov     rcx, [rbp+Protseq]
0x18001c6f9  mov     r9, [r11+rax*8]
0x18001c6fd  sub     r9, rcx
0x18001c700  movzx   r8d, word ptr [rcx]
0x18001c704  movzx   r10d, word ptr [rcx+r9]
0x18001c709  sub     r8d, r10d
0x18001c70c  jnz     short loc_18001C717
0x18001c70e  add     rcx, 2
0x18001c712  test    r10d, r10d
0x18001c715  jnz     short loc_18001C700
0x18001c717  test    r8d, r8d
0x18001c71a  jz      short loc_18001C724
0x18001c71c  inc     rax
0x18001c71f  cmp     rax, rdx
0x18001c722  jb      short loc_18001C6F5
0x18001c724  cmp     rax, rdx
0x18001c727  jnz     short loc_18001C757
0x18001c729  mov     r9d, 80070005h
0x18001c72f  mov     ebx, r9d
0x18001c732  mov     r10, cs:WPP_GLOBAL_Control
0x18001c739  cmp     r10, r14
0x18001c73c  jz      loc_18001C85C
0x18001c742  test    byte ptr [r10+1Ch], 1
0x18001c747  jz      loc_18001C85C
0x18001c74d  mov     edx, 1Ch
0x18001c752  jmp     loc_18001C849
0x18001c757  mov     [rsp+40h+NetworkOptions], rsi; AuthzSvc
0x18001c75c  lea     r9, [rbp+AuthnLevel]; AuthnLevel
0x18001c760  xor     r8d, r8d; ServerPrincName
0x18001c763  mov     [rsp+40h+Endpoint], rsi; AuthnSvc
0x18001c768  xor     edx, edx; Privs
0x18001c76a  mov     rcx, rdi; ClientBinding
0x18001c76d  call    cs:__imp_RpcBindingInqAuthClientW
0x18001c774  nop     dword ptr [rax+rax+00h]
0x18001c779  mov     ebx, eax
0x18001c77b  test    eax, eax
0x18001c77d  jz      short loc_18001C7AF
0x18001c77f  jle     short loc_18001C78A
0x18001c781  movzx   ebx, ax
0x18001c784  or      ebx, 80070000h
0x18001c78a  mov     r10, cs:WPP_GLOBAL_Control
0x18001c791  cmp     r10, r14
0x18001c794  jz      loc_18001C85C
0x18001c79a  test    byte ptr [r10+1Ch], 1
0x18001c79f  jz      loc_18001C85C
0x18001c7a5  mov     edx, 1Dh
0x18001c7aa  jmp     loc_18001C585
0x18001c7af  cmp     [rbp+AuthnLevel], 6
0x18001c7b3  jnb     short loc_18001C7E0
0x18001c7b5  mov     r9d, 80070005h
0x18001c7bb  mov     ebx, r9d
0x18001c7be  mov     r10, cs:WPP_GLOBAL_Control
0x18001c7c5  cmp     r10, r14
0x18001c7c8  jz      loc_18001C85C
0x18001c7ce  test    byte ptr [r10+1Ch], 1
0x18001c7d3  jz      loc_18001C85C
0x18001c7d9  mov     edx, 1Eh
0x18001c7de  jmp     short loc_18001C849
0x18001c7e0  mov     rcx, qword ptr cs:?gNcaRpcAPIs@@3UNCA_RPC_APIS_COMPONENT_@@A+8; pSecurityDescriptor
0x18001c7e7  mov     ebx, esi
0x18001c7e9  test    rcx, rcx
0x18001c7ec  jz      short loc_18001C855
0x18001c7ee  lea     r9, [rbp+arg_18]
0x18001c7f2  mov     r8d, 20000h; DesiredAccess
0x18001c7f8  mov     rdx, rdi; BindingHandle
0x18001c7fb  call    NcaRpcAPIsIsAccessGranted
0x18001c800  mov     ebx, eax
0x18001c802  test    eax, eax
0x18001c804  jns     short loc_18001C823
0x18001c806  mov     r10, cs:WPP_GLOBAL_Control
0x18001c80d  cmp     r10, r14
0x18001c810  jz      short loc_18001C85C
0x18001c812  test    byte ptr [r10+1Ch], 1
0x18001c817  jz      short loc_18001C85C
0x18001c819  mov     edx, 1Fh
0x18001c81e  mov     r9d, eax
0x18001c821  jmp     short loc_18001C849
0x18001c823  cmp     [rbp+arg_18], esi
0x18001c826  jnz     short loc_18001C855
0x18001c828  mov     r9d, 80070005h
0x18001c82e  mov     ebx, r9d
0x18001c831  mov     r10, cs:WPP_GLOBAL_Control
0x18001c838  cmp     r10, r14
0x18001c83b  jz      short loc_18001C85C
0x18001c83d  test    byte ptr [r10+1Ch], 1
0x18001c842  jz      short loc_18001C85C
0x18001c844  mov     edx, 20h ; ' '
0x18001c849  mov     rcx, [r10+10h]
0x18001c84d  mov     r8, r15
0x18001c850  call    WPP_SF_d
0x18001c855  mov     r10, cs:WPP_GLOBAL_Control
0x18001c85c  cmp     [rbp+Protseq], rsi
0x18001c860  jz      short loc_18001C879
0x18001c862  lea     rcx, [rbp+Protseq]; String
0x18001c866  call    cs:__imp_RpcStringFreeW
0x18001c86d  nop     dword ptr [rax+rax+00h]
0x18001c872  mov     r10, cs:WPP_GLOBAL_Control
0x18001c879  cmp     [rbp+StringBinding], rsi
0x18001c87d  jz      short loc_18001C896
0x18001c87f  lea     rcx, [rbp+StringBinding]; String
0x18001c883  call    cs:__imp_RpcStringFreeW
0x18001c88a  nop     dword ptr [rax+rax+00h]
0x18001c88f  mov     r10, cs:WPP_GLOBAL_Control
0x18001c896  cmp     r10, r14
0x18001c899  jz      short loc_18001C8BD
0x18001c89b  test    byte ptr [r10+1Ch], 8
0x18001c8a0  jz      short loc_18001C8BD
0x18001c8a2  mov     ecx, ebx
0x18001c8a4  call    NcaHResultToWindowsError
0x18001c8a9  mov     rcx, [r10+10h]
0x18001c8ad  mov     r9d, eax
0x18001c8b0  mov     edx, 21h ; '!'
0x18001c8b5  mov     r8, r15
0x18001c8b8  call    WPP_SF_d
0x18001c8bd  mov     ecx, ebx
0x18001c8bf  mov     rbx, [rsp+40h+arg_10]
0x18001c8c7  add     rsp, 40h
0x18001c8cb  pop     r15
0x18001c8cd  pop     r14
0x18001c8cf  pop     rdi
0x18001c8d0  pop     rsi
0x18001c8d1  pop     rbp
0x18001c8d2  jmp     NcaHResultToWindowsError
```
