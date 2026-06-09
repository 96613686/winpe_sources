# CShadowRpcUtils::s_Bind(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x1400b1938`
- end: `0x1400b1a71`
- name: `?s_Bind@CShadowRpcUtils@@SAJPEBG0000PEAPEAX@Z`
- size: `313`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, RPC_WSTR StringBinding, RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400b0804`
- `0x1400b1b38`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x1400b1938`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400b19dc`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400b19dc`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400b195f`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400b195f`
- `RPCRT4!RpcStringFreeW` at `0x1400b1a5e`
- `RPCRT4!RpcStringFreeW` at `0x1400b1a5e`

## string_xrefs

- `0x1400b1954`: `Security=Impersonation Dynamic False`

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
0x1400b1938  mov     r11, rsp
0x1400b193b  mov     [r11+8], rbx
0x1400b193f  push    rdi
0x1400b1940  sub     rsp, 30h
0x1400b1944  lea     rax, [r11+28h]
0x1400b1948  mov     qword ptr [r11+28h], 0
0x1400b1950  mov     [r11-10h], rax
0x1400b1954  lea     rax, aSecurityImpers; "Security=Impersonation Dynamic False"
0x1400b195b  mov     [r11-18h], rax
0x1400b195f  call    cs:__imp_RpcStringBindingComposeW
0x1400b1965  mov     ebx, eax
0x1400b1967  test    eax, eax
0x1400b1969  jz      short loc_1400B19D0
0x1400b196b  mov     rax, cs:WPP_GLOBAL_Control
0x1400b1972  lea     rcx, WPP_GLOBAL_Control
0x1400b1979  cmp     rax, rcx
0x1400b197c  jz      short loc_1400B19C3
0x1400b197e  test    byte ptr [rax+1Ch], 8
0x1400b1982  jz      short loc_1400B19C3
0x1400b1984  cmp     byte ptr [rax+19h], 2
0x1400b1988  jb      short loc_1400B19C3
0x1400b198a  test    ebx, ebx
0x1400b198c  jg      short loc_1400B1992
0x1400b198e  mov     edi, ebx
0x1400b1990  jmp     short loc_1400B199B
0x1400b1992  movzx   edi, bx
0x1400b1995  or      edi, 80070000h
0x1400b199b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b19a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b19a7  lea     r8, WPP_c8772b2815e43409a67effa2e76dee09_Traceguids
0x1400b19ae  mov     edx, 0Ah
0x1400b19b3  mov     [rsp+38h+var_18], edi
0x1400b19b7  mov     r9d, eax
0x1400b19ba  mov     rcx, [rcx+10h]
0x1400b19be  call    WPP_SF_Dd
0x1400b19c3  test    ebx, ebx
0x1400b19c5  jle     loc_1400B1A51
0x1400b19cb  movzx   ebx, bx
0x1400b19ce  jmp     short loc_1400B1A4B
0x1400b19d0  mov     rdx, [rsp+38h+Binding]; Binding
0x1400b19d5  xor     ebx, ebx
0x1400b19d7  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x1400b19dc  call    cs:__imp_RpcBindingFromStringBindingW
0x1400b19e2  mov     edi, eax
0x1400b19e4  test    eax, eax
0x1400b19e6  jz      short loc_1400B1A51
0x1400b19e8  mov     rax, cs:WPP_GLOBAL_Control
0x1400b19ef  lea     rcx, WPP_GLOBAL_Control
0x1400b19f6  cmp     rax, rcx
0x1400b19f9  jz      short loc_1400B1A40
0x1400b19fb  test    byte ptr [rax+1Ch], 8
0x1400b19ff  jz      short loc_1400B1A40
0x1400b1a01  cmp     byte ptr [rax+19h], 2
0x1400b1a05  jb      short loc_1400B1A40
0x1400b1a07  test    edi, edi
0x1400b1a09  jg      short loc_1400B1A0F
0x1400b1a0b  mov     ebx, edi
0x1400b1a0d  jmp     short loc_1400B1A18
0x1400b1a0f  movzx   ebx, di
0x1400b1a12  or      ebx, 80070000h
0x1400b1a18  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b1a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1a24  lea     r8, WPP_c8772b2815e43409a67effa2e76dee09_Traceguids
0x1400b1a2b  mov     edx, 0Bh
0x1400b1a30  mov     [rsp+38h+var_18], ebx
0x1400b1a34  mov     r9d, eax
0x1400b1a37  mov     rcx, [rcx+10h]
0x1400b1a3b  call    WPP_SF_Dd
0x1400b1a40  test    edi, edi
0x1400b1a42  jg      short loc_1400B1A48
0x1400b1a44  mov     ebx, edi
0x1400b1a46  jmp     short loc_1400B1A51
0x1400b1a48  movzx   ebx, di
0x1400b1a4b  or      ebx, 80070000h
0x1400b1a51  cmp     [rsp+38h+StringBinding], 0
0x1400b1a57  jz      short loc_1400B1A64
0x1400b1a59  lea     rcx, [rsp+38h+StringBinding]; String
0x1400b1a5e  call    cs:__imp_RpcStringFreeW
0x1400b1a64  mov     eax, ebx
0x1400b1a66  mov     rbx, [rsp+38h+arg_0]
0x1400b1a6b  add     rsp, 30h
0x1400b1a6f  pop     rdi
0x1400b1a70  retn
```
