# RpcGetConfigurationVariables

- ea: `0x180012b20`
- end: `0x180012c56`
- name: `RpcGetConfigurationVariables`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000e510`
- `0x180012b20`
- `0x180017e80`
- `0x18004d090`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180012c36`
- `RPCRT4!RpcRevertToSelf` at `0x180012c36`
- `fwpuclnt!IkeextGetConfigParameters0` at `0x180012bdf`
- `fwpuclnt!IkeextGetConfigParameters0` at `0x180012bdf`

## pseudocode

```c
__int64 __fastcall RpcGetConfigurationVariables(__int64 a1, __int64 a2)
{
  unsigned int ConfigParameters0; // eax
  unsigned int v4; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  bool v8; // zf
  int v10; // [rsp+20h] [rbp-38h] BYREF
  __int128 v11; // [rsp+28h] [rbp-30h] BYREF
  int v12; // [rsp+38h] [rbp-20h]

  v12 = 0;
  v11 = 0;
  v10 = 0;
  ConfigParameters0 = SPDImpersonateClient(&v10);
  v4 = ConfigParameters0;
  if ( ConfigParameters0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 118;
LABEL_5:
      v7 = ConfigParameters0;
LABEL_6:
      WPP_SF_d(v5[2], v6, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids, v7);
    }
  }
  else if ( a2 )
  {
    *(_OWORD *)a2 = 0;
    v12 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    v11 = 0;
    ConfigParameters0 = IkeextGetConfigParameters0(&v11);
    v4 = ConfigParameters0;
    if ( ConfigParameters0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v6 = 120;
        goto LABEL_5;
      }
    }
    else
    {
      v8 = (_DWORD)v11 == 0;
      *(_DWORD *)(a2 + 16) = BYTE12(v11) & 1;
      if ( !v8 )
        *(_DWORD *)(a2 + 24) = 1;
      *(_DWORD *)(a2 + 8) = gcCrlCheck;
    }
  }
  else
  {
    v4 = 87;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 119;
      v7 = 87;
      goto LABEL_6;
    }
  }
  if ( v10 )
    RpcRevertToSelf();
  return v4;
}

```

## disassembly

```asm
0x180012b20  mov     [rsp+arg_0], rbx
0x180012b25  push    rdi
0x180012b26  sub     rsp, 50h
0x180012b2a  mov     rax, cs:__security_cookie
0x180012b31  xor     rax, rsp
0x180012b34  mov     [rsp+58h+var_18], rax
0x180012b39  xor     eax, eax
0x180012b3b  lea     rcx, [rsp+58h+var_38]
0x180012b40  xorps   xmm0, xmm0
0x180012b43  mov     [rsp+58h+var_20], eax
0x180012b47  movups  [rsp+58h+var_30], xmm0
0x180012b4c  mov     [rsp+58h+var_38], eax
0x180012b50  mov     rbx, rdx
0x180012b53  call    SPDImpersonateClient
0x180012b58  mov     edi, eax
0x180012b5a  test    eax, eax
0x180012b5c  jz      short loc_180012B9C
0x180012b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b65  lea     rdx, WPP_GLOBAL_Control
0x180012b6c  cmp     rcx, rdx
0x180012b6f  jz      loc_180012C2F
0x180012b75  test    byte ptr [rcx+1Ch], 10h
0x180012b79  jz      loc_180012C2F
0x180012b7f  mov     edx, 76h ; 'v'
0x180012b84  mov     r9d, eax
0x180012b87  mov     rcx, [rcx+10h]
0x180012b8b  lea     r8, WPP_a44ffbd5c9413be3674bcdc6eabb9c73_Traceguids
0x180012b92  call    WPP_SF_d
0x180012b97  jmp     loc_180012C2F
0x180012b9c  test    rbx, rbx
0x180012b9f  jnz     short loc_180012BC5
0x180012ba1  lea     edi, [rbx+57h]
0x180012ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bab  lea     rdx, WPP_GLOBAL_Control
0x180012bb2  cmp     rcx, rdx
0x180012bb5  jz      short loc_180012C2F
0x180012bb7  test    byte ptr [rcx+1Ch], 10h
0x180012bbb  jz      short loc_180012C2F
0x180012bbd  lea     edx, [rbx+77h]
0x180012bc0  mov     r9d, edi
0x180012bc3  jmp     short loc_180012B87
0x180012bc5  xorps   xmm0, xmm0
0x180012bc8  lea     rcx, [rsp+58h+var_30]
0x180012bcd  xor     eax, eax
0x180012bcf  movups  xmmword ptr [rbx], xmm0
0x180012bd2  mov     [rsp+58h+var_20], eax
0x180012bd6  movups  xmmword ptr [rbx+10h], xmm0
0x180012bda  movups  [rsp+58h+var_30], xmm0
0x180012bdf  call    cs:__imp_IkeextGetConfigParameters0
0x180012be5  mov     edi, eax
0x180012be7  test    eax, eax
0x180012be9  jz      short loc_180012C0E
0x180012beb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bf2  lea     rdx, WPP_GLOBAL_Control
0x180012bf9  cmp     rcx, rdx
0x180012bfc  jz      short loc_180012C2F
0x180012bfe  test    byte ptr [rcx+1Ch], 10h
0x180012c02  jz      short loc_180012C2F
0x180012c04  mov     edx, 78h ; 'x'
0x180012c09  jmp     loc_180012B84
0x180012c0e  mov     eax, dword ptr [rsp+58h+var_30+0Ch]
0x180012c12  and     eax, 1
0x180012c15  cmp     dword ptr [rsp+58h+var_30], 0
0x180012c1a  mov     [rbx+10h], eax
0x180012c1d  jz      short loc_180012C26
0x180012c1f  mov     dword ptr [rbx+18h], 1
0x180012c26  mov     eax, cs:gcCrlCheck
0x180012c2c  mov     [rbx+8], eax
0x180012c2f  cmp     [rsp+58h+var_38], 0
0x180012c34  jz      short loc_180012C3C
0x180012c36  call    cs:__imp_RpcRevertToSelf
0x180012c3c  mov     eax, edi
0x180012c3e  mov     rcx, [rsp+58h+var_18]
0x180012c43  xor     rcx, rsp; StackCookie
0x180012c46  call    __security_check_cookie
0x180012c4b  mov     rbx, [rsp+58h+arg_0]
0x180012c50  add     rsp, 50h
0x180012c54  pop     rdi
0x180012c55  retn
```
