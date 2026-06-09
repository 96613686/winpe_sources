# UMRDP_SecurityCallback(void *,void *)

- ea: `0x140017630`
- end: `0x14001777d`
- name: `?UMRDP_SecurityCallback@@YAJPEAX0@Z`
- size: `333`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140016b18`
- `0x140017630`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x14001770a`
- `RPCRT4!RpcImpersonateClient` at `0x14001770a`
- `RPCRT4!RpcRevertToSelf` at `0x140017760`
- `RPCRT4!RpcRevertToSelf` at `0x140017768`
- `RPCRT4!RpcRevertToSelf` at `0x140017760`
- `RPCRT4!RpcRevertToSelf` at `0x140017768`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x14001766e`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x14001766e`

## pseudocode

```c
__int64 __fastcall UMRDP_SecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v2; // edi
  RPC_STATUS v3; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  CUmRdp *v6; // rcx
  unsigned int v7; // eax
  unsigned int v9; // [rsp+50h] [rbp+18h] BYREF
  RPC_AUTHZ_HANDLE v10; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v9 = 0;
  v2 = 5;
  v3 = RpcBindingInqAuthClientW(Context, &v10, 0, &v9, 0, 0);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 10;
LABEL_6:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids,
        CurrentThreadActivityIdPrefix,
        v3);
    }
  }
  else
  {
    v3 = v9;
    if ( v9 >= 4 )
    {
      if ( !RpcImpersonateClient(0) )
      {
        if ( (unsigned int)CUmRdp::IsRpcCallerSystem(v6) )
        {
          return (unsigned int)RpcRevertToSelf();
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids, v7);
          }
          RpcRevertToSelf();
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 11;
      goto LABEL_6;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140017630  mov     rax, rsp
0x140017633  mov     [rax+8], rbx
0x140017637  push    rdi
0x140017638  sub     rsp, 30h
0x14001763c  mov     rcx, rdx; ClientBinding
0x14001763f  mov     qword ptr [rax-10h], 0
0x140017647  lea     rdx, [rax+20h]; Privs
0x14001764b  mov     qword ptr [rax+20h], 0
0x140017653  lea     r9, [rax+18h]; AuthnLevel
0x140017657  mov     dword ptr [rax+18h], 0
0x14001765e  xor     r8d, r8d; ServerPrincName
0x140017661  mov     qword ptr [rax-18h], 0
0x140017669  mov     edi, 5
0x14001766e  call    cs:__imp_RpcBindingInqAuthClientW
0x140017674  mov     ebx, eax
0x140017676  test    eax, eax
0x140017678  jz      short loc_1400176D0
0x14001767a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017681  lea     rax, WPP_GLOBAL_Control
0x140017688  cmp     rcx, rax
0x14001768b  jz      loc_140017770
0x140017691  test    byte ptr [rcx+1Ch], 1
0x140017695  jz      loc_140017770
0x14001769b  cmp     byte ptr [rcx+19h], 2
0x14001769f  jb      loc_140017770
0x1400176a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400176aa  lea     edx, [rdi+5]
0x1400176ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176b4  lea     r8, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids
0x1400176bb  mov     r9d, eax
0x1400176be  mov     [rsp+38h+var_18], ebx
0x1400176c2  mov     rcx, [rcx+10h]
0x1400176c6  call    WPP_SF_Dd
0x1400176cb  jmp     loc_140017770
0x1400176d0  mov     ebx, [rsp+38h+arg_10]
0x1400176d4  cmp     ebx, 4
0x1400176d7  jnb     short loc_140017708
0x1400176d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176e0  lea     rax, WPP_GLOBAL_Control
0x1400176e7  cmp     rcx, rax
0x1400176ea  jz      loc_140017770
0x1400176f0  test    byte ptr [rcx+1Ch], 1
0x1400176f4  jz      short loc_140017770
0x1400176f6  cmp     byte ptr [rcx+19h], 2
0x1400176fa  jb      short loc_140017770
0x1400176fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140017701  mov     edx, 0Bh
0x140017706  jmp     short loc_1400176AD
0x140017708  xor     ecx, ecx; BindingHandle
0x14001770a  call    cs:__imp_RpcImpersonateClient
0x140017710  test    eax, eax
0x140017712  jnz     short loc_140017770
0x140017714  call    ?IsRpcCallerSystem@CUmRdp@@QEAAHXZ; CUmRdp::IsRpcCallerSystem(void)
0x140017719  test    eax, eax
0x14001771b  jnz     short loc_140017768
0x14001771d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017724  lea     rax, WPP_GLOBAL_Control
0x14001772b  cmp     rcx, rax
0x14001772e  jz      short loc_140017760
0x140017730  test    byte ptr [rcx+1Ch], 1
0x140017734  jz      short loc_140017760
0x140017736  cmp     byte ptr [rcx+19h], 2
0x14001773a  jb      short loc_140017760
0x14001773c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140017741  mov     rcx, cs:WPP_GLOBAL_Control
0x140017748  lea     r8, WPP_e1878ade8ac733f4c5d20ac7d29e2f6b_Traceguids
0x14001774f  mov     edx, 0Ch
0x140017754  mov     r9d, eax
0x140017757  mov     rcx, [rcx+10h]
0x14001775b  call    WPP_SF_d
0x140017760  call    cs:__imp_RpcRevertToSelf
0x140017766  jmp     short loc_140017770
0x140017768  call    cs:__imp_RpcRevertToSelf
0x14001776e  mov     edi, eax
0x140017770  mov     rbx, [rsp+38h+arg_0]
0x140017775  mov     eax, edi
0x140017777  add     rsp, 30h
0x14001777b  pop     rdi
0x14001777c  retn
```
