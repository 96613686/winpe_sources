# FwMoneisValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)

- ea: `0x1800511b4`
- end: `0x180051469`
- name: `?FwMoneisValidateAppContainerOperation@@YAKPEAXHHPEAU_SID@@1PEAH@Z`
- size: `693`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, int@<edx>, int@<r8d>, struct _SID *@<r9>, struct _SID *, int *)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800350b4`
- `0x180037aa0`
- `0x180057bd0`
- `0x180070e74`
- `0x1800bd22c`
- `0x1800be1ec`

## callees

- `0x18000a710`
- `0x1800511b4`
- `0x180051470`
- `0x1800515e8`
- `0x1800729c0`

## import_xrefs

- `ntdll!RtlIsParentOfChildAppContainer` at `0x180051426`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x180051426`
- `ntdll!RtlEqualSid` at `0x180051266`
- `ntdll!RtlEqualSid` at `0x1800512de`
- `ntdll!RtlEqualSid` at `0x18005135f`
- `ntdll!RtlEqualSid` at `0x180051266`
- `ntdll!RtlEqualSid` at `0x1800512de`
- `ntdll!RtlEqualSid` at `0x18005135f`
- `fwbase!FwHResultToWindowsError` at `0x1800512bd`
- `fwbase!FwHResultToWindowsError` at `0x1800512bd`
- `fwbase!FwFree` at `0x18005123b`
- `fwbase!FwFree` at `0x18005124c`
- `fwbase!FwFree` at `0x18005123b`
- `fwbase!FwFree` at `0x18005124c`

## pseudocode

```c
__int64 __fastcall FwMoneisValidateAppContainerOperation(
        void *a1,
        int a2,
        int a3,
        struct _SID *a4,
        struct _SID *Sid1,
        int *a6)
{
  unsigned int v9; // r15d
  unsigned int v10; // ebx
  struct _SID_AND_ATTRIBUTES *v11; // r13
  unsigned int RpcClientAppContainerSid; // ebx
  unsigned int RPCClientUserSid; // eax
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rdx
  struct _TOKEN_APPCONTAINER_INFORMATION *v19; // [rsp+28h] [rbp-50h] BYREF
  struct _TOKEN_USER *v20; // [rsp+30h] [rbp-48h] BYREF

  v20 = 0;
  *a6 = 1;
  v19 = 0;
  if ( !a4 || !Sid1 )
    goto LABEL_10;
  v9 = dword_18012FBD8;
  v10 = 0;
  v11 = qword_18012FBE0;
  while ( 1 )
  {
    if ( v10 >= v9 )
      goto LABEL_5;
    if ( RtlEqualSid(Sid1, v11[v10].Sid) == 1 )
      break;
    ++v10;
  }
  if ( RtlEqualSid(a4, Sid2) )
  {
LABEL_5:
    if ( a2 )
    {
LABEL_6:
      RpcClientAppContainerSid = 0;
LABEL_7:
      FwFree(v19);
      FwFree(v20);
      return RpcClientAppContainerSid;
    }
    RPCClientUserSid = FwGetRPCClientUserSid(a1, &v20);
    RpcClientAppContainerSid = FwHResultToWindowsError(RPCClientUserSid);
    if ( RpcClientAppContainerSid )
    {
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_7;
      v17 = 38;
    }
    else
    {
      if ( !RtlEqualSid(a4, v20->User.Sid) )
      {
        v15 = 5;
        RpcClientAppContainerSid = 5;
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_7;
        v17 = 39;
        goto LABEL_26;
      }
      RpcClientAppContainerSid = FwGetRpcClientAppContainerSid(a1, &v19);
      if ( !RpcClientAppContainerSid )
      {
        if ( !v19->TokenAppContainer )
          goto LABEL_6;
        if ( a3 == RpcClientAppContainerSid )
        {
          v15 = RpcClientAppContainerSid + 5;
          RpcClientAppContainerSid += 5;
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_7;
          v17 = (unsigned int)(v15 + 36);
        }
        else
        {
          if ( (unsigned __int8)RtlIsParentOfChildAppContainer(v19->TokenAppContainer, Sid1) )
            goto LABEL_6;
          v15 = 5;
          RpcClientAppContainerSid = 5;
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_7;
          v17 = 42;
        }
LABEL_26:
        WPP_SF_d(*(_QWORD *)(v16 + 16), v17, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, v15);
        goto LABEL_7;
      }
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_7;
      v17 = 40;
    }
    v15 = RpcClientAppContainerSid;
    goto LABEL_26;
  }
  if ( a2 == 1 )
  {
LABEL_10:
    *a6 = 0;
    return 0;
  }
  return 5;
}

```

## disassembly

```asm
0x1800511b4  mov     [rsp+arg_8], rbx
0x1800511b9  push    rbp
0x1800511ba  push    rsi
0x1800511bb  push    rdi
0x1800511bc  push    r12
0x1800511be  push    r13
0x1800511c0  push    r14
0x1800511c2  push    r15
0x1800511c4  sub     rsp, 40h
0x1800511c8  mov     rax, cs:__security_cookie
0x1800511cf  xor     rax, rsp
0x1800511d2  mov     [rsp+78h+var_40], rax
0x1800511d7  mov     r14, [rsp+78h+arg_28]
0x1800511df  mov     rbp, r9
0x1800511e2  mov     rsi, [rsp+78h+Sid1]
0x1800511ea  mov     edi, edx
0x1800511ec  mov     [rsp+78h+var_58], r8d
0x1800511f1  mov     r12, rcx
0x1800511f4  mov     [rsp+78h+var_48], 0
0x1800511fd  mov     dword ptr [r14], 1
0x180051204  mov     [rsp+78h+var_50], 0
0x18005120d  test    r9, r9
0x180051210  jz      short loc_18005127F
0x180051212  test    rsi, rsi
0x180051215  jz      short loc_18005127F
0x180051217  mov     r15d, cs:dword_18012FBD8
0x18005121e  xor     ebx, ebx
0x180051220  mov     r13, cs:qword_18012FBE0
0x180051227  cmp     ebx, r15d
0x18005122a  jb      loc_180051352
0x180051230  test    edi, edi
0x180051232  jz      short loc_1800512AE
0x180051234  xor     ebx, ebx
0x180051236  mov     rcx, [rsp+78h+var_50]
0x18005123b  call    cs:__imp_FwFree
0x180051242  nop     dword ptr [rax+rax+00h]
0x180051247  mov     rcx, [rsp+78h+var_48]
0x18005124c  call    cs:__imp_FwFree
0x180051253  nop     dword ptr [rax+rax+00h]
0x180051258  mov     eax, ebx
0x18005125a  jmp     short loc_180051288
0x18005125c  mov     rdx, cs:Sid2; Sid2
0x180051263  mov     rcx, rbp; Sid1
0x180051266  call    cs:__imp_RtlEqualSid
0x18005126d  nop     dword ptr [rax+rax+00h]
0x180051272  test    al, al
0x180051274  jnz     short loc_180051230
0x180051276  cmp     edi, 1
0x180051279  jnz     loc_18005137A
0x18005127f  mov     dword ptr [r14], 0
0x180051286  xor     eax, eax
0x180051288  mov     rcx, [rsp+78h+var_40]
0x18005128d  xor     rcx, rsp; StackCookie
0x180051290  call    __security_check_cookie
0x180051295  mov     rbx, [rsp+78h+arg_8]
0x18005129d  add     rsp, 40h
0x1800512a1  pop     r15
0x1800512a3  pop     r14
0x1800512a5  pop     r13
0x1800512a7  pop     r12
0x1800512a9  pop     rdi
0x1800512aa  pop     rsi
0x1800512ab  pop     rbp
0x1800512ac  retn
0x1800512ae  lea     rdx, [rsp+78h+var_48]; struct _TOKEN_USER **
0x1800512b3  mov     rcx, r12; void *
0x1800512b6  call    ?FwGetRPCClientUserSid@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; FwGetRPCClientUserSid(void *,_TOKEN_USER * *)
0x1800512bb  mov     ecx, eax
0x1800512bd  call    cs:__imp_FwHResultToWindowsError
0x1800512c4  nop     dword ptr [rax+rax+00h]
0x1800512c9  mov     ebx, eax
0x1800512cb  test    eax, eax
0x1800512cd  jnz     loc_180051384
0x1800512d3  mov     rdx, [rsp+78h+var_48]
0x1800512d8  mov     rcx, rbp; Sid1
0x1800512db  mov     rdx, [rdx]; Sid2
0x1800512de  call    cs:__imp_RtlEqualSid
0x1800512e5  nop     dword ptr [rax+rax+00h]
0x1800512ea  test    al, al
0x1800512ec  jz      loc_1800513D0
0x1800512f2  lea     rdx, [rsp+78h+var_50]; struct _TOKEN_APPCONTAINER_INFORMATION **
0x1800512f7  mov     rcx, r12; void *
0x1800512fa  call    ?FwGetRpcClientAppContainerSid@@YAJPEAXPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z; FwGetRpcClientAppContainerSid(void *,_TOKEN_APPCONTAINER_INFORMATION * *)
0x1800512ff  mov     ebx, eax
0x180051301  test    eax, eax
0x180051303  jnz     loc_180051400
0x180051309  mov     rax, [rsp+78h+var_50]
0x18005130e  mov     rcx, [rax]
0x180051311  test    rcx, rcx
0x180051314  jz      loc_180051234
0x18005131a  cmp     [rsp+78h+var_58], ebx
0x18005131e  jnz     loc_180051423
0x180051324  lea     r9d, [rbx+5]
0x180051328  mov     ebx, r9d
0x18005132b  mov     rax, cs:WPP_GLOBAL_Control
0x180051332  lea     rcx, WPP_GLOBAL_Control
0x180051339  cmp     rax, rcx
0x18005133c  jz      loc_180051236
0x180051342  test    byte ptr [rax+1Ch], 1
0x180051346  jz      loc_180051236
0x18005134c  lea     edx, [r9+24h]
0x180051350  jmp     short loc_1800513BB
0x180051352  mov     edx, ebx
0x180051354  mov     rcx, rsi; Sid1
0x180051357  add     rdx, rdx
0x18005135a  mov     rdx, [r13+rdx*8+0]; Sid2
0x18005135f  call    cs:__imp_RtlEqualSid
0x180051366  nop     dword ptr [rax+rax+00h]
0x18005136b  cmp     al, 1
0x18005136d  jz      loc_18005125C
0x180051373  inc     ebx
0x180051375  jmp     loc_180051227
0x18005137a  mov     eax, 5
0x18005137f  jmp     loc_180051288
0x180051384  mov     rax, cs:WPP_GLOBAL_Control
0x18005138b  lea     rcx, WPP_GLOBAL_Control
0x180051392  cmp     rax, rcx
0x180051395  jz      loc_180051236
0x18005139b  test    byte ptr [rax+1Ch], 1
0x18005139f  jz      loc_180051236
0x1800513a5  mov     edx, 26h ; '&'
0x1800513aa  jmp     short loc_1800513B1
0x1800513ac  mov     edx, 28h ; '('
0x1800513b1  mov     r9d, ebx
0x1800513b4  jmp     short loc_1800513BB
0x1800513b6  mov     edx, 2Ah ; '*'
0x1800513bb  mov     rcx, [rax+10h]
0x1800513bf  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800513c6  call    WPP_SF_d
0x1800513cb  jmp     loc_180051236
0x1800513d0  mov     r9d, 5
0x1800513d6  mov     ebx, r9d
0x1800513d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800513e0  lea     rcx, WPP_GLOBAL_Control
0x1800513e7  cmp     rax, rcx
0x1800513ea  jz      loc_180051236
0x1800513f0  test    byte ptr [rax+1Ch], 1
0x1800513f4  jz      loc_180051236
0x1800513fa  lea     edx, [r9+22h]
0x1800513fe  jmp     short loc_1800513BB
0x180051400  mov     rax, cs:WPP_GLOBAL_Control
0x180051407  lea     rcx, WPP_GLOBAL_Control
0x18005140e  cmp     rax, rcx
0x180051411  jz      loc_180051236
0x180051417  test    byte ptr [rax+1Ch], 1
0x18005141b  jz      loc_180051236
0x180051421  jmp     short loc_1800513AC
0x180051423  mov     rdx, rsi
0x180051426  call    cs:__imp_RtlIsParentOfChildAppContainer
0x18005142d  nop     dword ptr [rax+rax+00h]
0x180051432  test    al, al
0x180051434  jnz     loc_180051234
0x18005143a  mov     r9d, 5
0x180051440  mov     ebx, r9d
0x180051443  mov     rax, cs:WPP_GLOBAL_Control
0x18005144a  lea     rcx, WPP_GLOBAL_Control
0x180051451  cmp     rax, rcx
0x180051454  jz      loc_180051236
0x18005145a  test    byte ptr [rax+1Ch], 1
0x18005145e  jz      loc_180051236
0x180051464  jmp     loc_1800513B6
```
