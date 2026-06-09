# CShadowRpcUtils::s_Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x1400b3aa8`
- end: `0x1400b3be1`
- name: `?s_Bind@CShadowRpcUtils@@SAJPEBG0000PEAPEAX@Z`
- size: `313`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, RPC_WSTR StringBinding, RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400b2974`
- `0x1400b3ca8`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x1400b3aa8`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400b3b4c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400b3b4c`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400b3acf`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400b3acf`
- `RPCRT4!RpcStringFreeW` at `0x1400b3bce`
- `RPCRT4!RpcStringFreeW` at `0x1400b3bce`

## string_xrefs

- `0x1400b3ac4`: `Security=Impersonation Dynamic False`

## pseudocode

```c
__int64 __fastcall CShadowRpcUtils::s_Bind(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        RPC_WSTR StringBinding,
        RPC_BINDING_HANDLE *Binding)
{
  RPC_STATUS v6; // ebx
  unsigned int v7; // edi
  unsigned int v8; // eax
  RPC_STATUS v9; // edi
  unsigned int v10; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax

  StringBinding = 0;
  v6 = RpcStringBindingComposeW(a1, a2, a3, a4, L"Security=Impersonation Dynamic False", &StringBinding);
  if ( !v6 )
  {
    v6 = 0;
    v9 = RpcBindingFromStringBindingW(StringBinding, Binding);
    if ( !v9 )
      goto LABEL_23;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      else
        v10 = v9;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_c8772b2815e43409a67effa2e76dee09_Traceguids,
        CurrentThreadActivityIdPrefix,
        v10);
    }
    if ( v9 <= 0 )
    {
      v6 = v9;
      goto LABEL_23;
    }
    v6 = (unsigned __int16)v9;
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    else
      v7 = v6;
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c8772b2815e43409a67effa2e76dee09_Traceguids, v8, v7);
  }
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6;
LABEL_22:
    v6 |= 0x80070000;
  }
LABEL_23:
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400b3aa8  mov     r11, rsp
0x1400b3aab  mov     [r11+8], rbx
0x1400b3aaf  push    rdi
0x1400b3ab0  sub     rsp, 30h
0x1400b3ab4  lea     rax, [r11+28h]
0x1400b3ab8  mov     qword ptr [r11+28h], 0
0x1400b3ac0  mov     [r11-10h], rax
0x1400b3ac4  lea     rax, aSecurityImpers; "Security=Impersonation Dynamic False"
0x1400b3acb  mov     [r11-18h], rax
0x1400b3acf  call    cs:__imp_RpcStringBindingComposeW
0x1400b3ad5  mov     ebx, eax
0x1400b3ad7  test    eax, eax
0x1400b3ad9  jz      short loc_1400B3B40
0x1400b3adb  mov     rax, cs:WPP_GLOBAL_Control
0x1400b3ae2  lea     rcx, WPP_GLOBAL_Control
0x1400b3ae9  cmp     rax, rcx
0x1400b3aec  jz      short loc_1400B3B33
0x1400b3aee  test    byte ptr [rax+1Ch], 8
0x1400b3af2  jz      short loc_1400B3B33
0x1400b3af4  cmp     byte ptr [rax+19h], 2
0x1400b3af8  jb      short loc_1400B3B33
0x1400b3afa  test    ebx, ebx
0x1400b3afc  jg      short loc_1400B3B02
0x1400b3afe  mov     edi, ebx
0x1400b3b00  jmp     short loc_1400B3B0B
0x1400b3b02  movzx   edi, bx
0x1400b3b05  or      edi, 80070000h
0x1400b3b0b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b3b10  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3b17  lea     r8, WPP_c8772b2815e43409a67effa2e76dee09_Traceguids
0x1400b3b1e  mov     edx, 0Ah
0x1400b3b23  mov     [rsp+38h+var_18], edi
0x1400b3b27  mov     r9d, eax
0x1400b3b2a  mov     rcx, [rcx+10h]
0x1400b3b2e  call    WPP_SF_Dd
0x1400b3b33  test    ebx, ebx
0x1400b3b35  jle     loc_1400B3BC1
0x1400b3b3b  movzx   ebx, bx
0x1400b3b3e  jmp     short loc_1400B3BBB
0x1400b3b40  mov     rdx, [rsp+38h+Binding]; Binding
0x1400b3b45  xor     ebx, ebx
0x1400b3b47  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x1400b3b4c  call    cs:__imp_RpcBindingFromStringBindingW
0x1400b3b52  mov     edi, eax
0x1400b3b54  test    eax, eax
0x1400b3b56  jz      short loc_1400B3BC1
0x1400b3b58  mov     rax, cs:WPP_GLOBAL_Control
0x1400b3b5f  lea     rcx, WPP_GLOBAL_Control
0x1400b3b66  cmp     rax, rcx
0x1400b3b69  jz      short loc_1400B3BB0
0x1400b3b6b  test    byte ptr [rax+1Ch], 8
0x1400b3b6f  jz      short loc_1400B3BB0
0x1400b3b71  cmp     byte ptr [rax+19h], 2
0x1400b3b75  jb      short loc_1400B3BB0
0x1400b3b77  test    edi, edi
0x1400b3b79  jg      short loc_1400B3B7F
0x1400b3b7b  mov     ebx, edi
0x1400b3b7d  jmp     short loc_1400B3B88
0x1400b3b7f  movzx   ebx, di
0x1400b3b82  or      ebx, 80070000h
0x1400b3b88  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b3b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3b94  lea     r8, WPP_c8772b2815e43409a67effa2e76dee09_Traceguids
0x1400b3b9b  mov     edx, 0Bh
0x1400b3ba0  mov     [rsp+38h+var_18], ebx
0x1400b3ba4  mov     r9d, eax
0x1400b3ba7  mov     rcx, [rcx+10h]
0x1400b3bab  call    WPP_SF_Dd
0x1400b3bb0  test    edi, edi
0x1400b3bb2  jg      short loc_1400B3BB8
0x1400b3bb4  mov     ebx, edi
0x1400b3bb6  jmp     short loc_1400B3BC1
0x1400b3bb8  movzx   ebx, di
0x1400b3bbb  or      ebx, 80070000h
0x1400b3bc1  cmp     [rsp+38h+StringBinding], 0
0x1400b3bc7  jz      short loc_1400B3BD4
0x1400b3bc9  lea     rcx, [rsp+38h+StringBinding]; String
0x1400b3bce  call    cs:__imp_RpcStringFreeW
0x1400b3bd4  mov     eax, ebx
0x1400b3bd6  mov     rbx, [rsp+38h+arg_0]
0x1400b3bdb  add     rsp, 30h
0x1400b3bdf  pop     rdi
0x1400b3be0  retn
```
