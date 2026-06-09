# NatEnableGroupExceptionForICS(void)

- ea: `0x180040cf4`
- end: `0x180040ff9`
- name: `?NatEnableGroupExceptionForICS@@YAJXZ`
- size: `773`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d4c8`
- `0x180042a44`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180034f2c`
- `0x180037cf4`
- `0x180040cf4`

## import_xrefs

- `FirewallAPI!FWSetFirewallRule` at `0x180040efa`
- `FirewallAPI!FWSetFirewallRule` at `0x180040efa`
- `FirewallAPI!FWQueryFirewallRules` at `0x180040e4d`
- `FirewallAPI!FWQueryFirewallRules` at `0x180040e4d`
- `FirewallAPI!FWClosePolicyStore` at `0x180040fb0`
- `FirewallAPI!FWClosePolicyStore` at `0x180040fb0`
- `FirewallAPI!FWFreeFirewallRules` at `0x180040f97`
- `FirewallAPI!FWFreeFirewallRules` at `0x180040f97`
- `FirewallAPI!FWOpenPolicyStore` at `0x180040d96`
- `FirewallAPI!FWOpenPolicyStore` at `0x180040d96`

## string_xrefs

- `0x180040dff`: `@ipnathlp.dll,-140`

## pseudocode

```c
__int64 NatEnableGroupExceptionForICS(void)
{
  int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 *v6; // rdi
  __int16 v7; // ax
  int v8; // eax
  __int128 v10; // [rsp+30h] [rbp-40h] BYREF
  __int128 v11; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v12; // [rsp+50h] [rbp-20h]
  __int128 v13; // [rsp+58h] [rbp-18h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h]
  unsigned int v15; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+38h] BYREF
  __int64 *v17; // [rsp+B0h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_213010f39927376708ca656d45278473_Traceguids);
  }
  v16 = 0;
  v12 = 0;
  v14 = 0;
  v17 = 0;
  v15 = 0;
  v11 = 0;
  v10 = 0;
  v13 = 0;
  v0 = FWOpenPolicyStore(545, 0, 5, 2, 0, &v16);
  if ( v0 )
  {
    if ( v0 > 0 )
      v3 = (unsigned __int16)v0 | 0x80070000;
    else
      v3 = v0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 28;
LABEL_13:
      WPP_SF_d(v4[2], v5, &WPP_213010f39927376708ca656d45278473_Traceguids, (unsigned int)v0);
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  *(_QWORD *)&v11 = 0x100000008LL;
  v12 = L"@ipnathlp.dll,-140";
  LODWORD(v10) = 1;
  *((_QWORD *)&v10 + 1) = &v11;
  DWORD1(v13) = 1;
  *((_QWORD *)&v13 + 1) = &v10;
  DWORD2(v11) = 5;
  LODWORD(v14) = 0x10000;
  LOWORD(v13) = 545;
  v0 = FWQueryFirewallRules(v16, &v13, 0, &v15, &v17);
  if ( !v0 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v3 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_213010f39927376708ca656d45278473_Traceguids, v15);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v6 = v17;
    if ( !v17 )
      goto LABEL_44;
    v1 = 1;
    while ( 1 )
    {
      v7 = *((_WORD *)v6 + 146);
      if ( (v7 & 1) == 0 )
        break;
LABEL_43:
      v6 = (__int64 *)*v6;
      if ( !v6 )
        goto LABEL_44;
    }
    *((_WORD *)v6 + 146) = v7 | 1;
    v8 = FWSetFirewallRule(v16, v6);
    if ( v8 )
    {
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      else
        v3 = v8;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_213010f39927376708ca656d45278473_Traceguids,
        v6[2],
        v8);
    }
    else
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_42;
      }
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_213010f39927376708ca656d45278473_Traceguids, v6[2]);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_42:
    v1 = 1;
    goto LABEL_43;
  }
  if ( v0 > 0 )
    v3 = (unsigned __int16)v0 | 0x80070000;
  else
    v3 = v0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = 29;
    goto LABEL_13;
  }
LABEL_44:
  if ( v17 )
  {
    FWFreeFirewallRules(v17);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 )
  {
    FWClosePolicyStore(v16, v1, v2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 33, &WPP_213010f39927376708ca656d45278473_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180040cf4  mov     [rsp-28h+arg_18], rbx
0x180040cf9  push    rbp
0x180040cfa  push    rdi
0x180040cfb  push    r12
0x180040cfd  push    r14
0x180040cff  push    r15
0x180040d01  mov     rbp, rsp
0x180040d04  sub     rsp, 70h
0x180040d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d0f  lea     r15, WPP_GLOBAL_Control
0x180040d16  lea     r12, WPP_213010f39927376708ca656d45278473_Traceguids
0x180040d1d  mov     r14d, 200h
0x180040d23  cmp     rcx, r15
0x180040d26  jz      short loc_180040D45
0x180040d28  test    [rcx+1Ch], r14d
0x180040d2c  jz      short loc_180040D45
0x180040d2e  cmp     byte ptr [rcx+19h], 6
0x180040d32  jb      short loc_180040D45
0x180040d34  mov     rcx, [rcx+10h]
0x180040d38  mov     edx, 1Bh
0x180040d3d  mov     r8, r12
0x180040d40  call    WPP_SF_
0x180040d45  xor     eax, eax
0x180040d47  mov     [rbp+arg_8], 0
0x180040d4f  xor     edx, edx
0x180040d51  mov     [rbp+var_20], rax
0x180040d55  xorps   xmm0, xmm0
0x180040d58  mov     [rbp+var_8], rax
0x180040d5c  mov     [rbp+arg_10], rax
0x180040d60  xorps   xmm1, xmm1
0x180040d63  lea     rax, [rbp+arg_8]
0x180040d67  mov     [rbp+arg_0], 0
0x180040d6e  mov     [rsp+70h+var_48], rax
0x180040d73  lea     r9d, [rdx+2]
0x180040d77  mov     ebx, 221h
0x180040d7c  mov     dword ptr [rsp+70h+var_50], 0
0x180040d84  lea     r8d, [rdx+5]
0x180040d88  mov     ecx, ebx
0x180040d8a  movups  [rbp+var_30], xmm0
0x180040d8e  movups  [rbp+var_40], xmm0
0x180040d92  movups  [rbp+var_18], xmm1
0x180040d96  call    cs:__imp_FWOpenPolicyStore
0x180040d9c  test    eax, eax
0x180040d9e  jz      short loc_180040DF3
0x180040da0  jg      short loc_180040DA6
0x180040da2  mov     ebx, eax
0x180040da4  jmp     short loc_180040DAF
0x180040da6  movzx   ebx, ax
0x180040da9  or      ebx, 80070000h
0x180040daf  mov     rcx, cs:WPP_GLOBAL_Control
0x180040db6  cmp     rcx, r15
0x180040db9  jz      loc_180040F8B
0x180040dbf  test    [rcx+1Ch], r14d
0x180040dc3  jz      loc_180040F8B
0x180040dc9  cmp     byte ptr [rcx+19h], 2
0x180040dcd  jb      loc_180040F8B
0x180040dd3  mov     edx, 1Ch
0x180040dd8  mov     rcx, [rcx+10h]
0x180040ddc  mov     r9d, eax
0x180040ddf  mov     r8, r12
0x180040de2  call    WPP_SF_d
0x180040de7  mov     rcx, cs:WPP_GLOBAL_Control
0x180040dee  jmp     loc_180040F8B
0x180040df3  mov     ecx, 1
0x180040df8  mov     dword ptr [rbp+var_30], 8
0x180040dff  lea     rax, aIpnathlpDll140; "@ipnathlp.dll,-140"
0x180040e06  mov     dword ptr [rbp+var_30+4], ecx
0x180040e09  mov     [rbp+var_20], rax
0x180040e0d  lea     r9, [rbp+arg_0]
0x180040e11  lea     rax, [rbp+var_30]
0x180040e15  mov     dword ptr [rbp+var_40], ecx
0x180040e18  mov     qword ptr [rbp+var_40+8], rax
0x180040e1c  lea     rdx, [rbp+var_18]
0x180040e20  lea     rax, [rbp+var_40]
0x180040e24  mov     dword ptr [rbp+var_18+4], ecx
0x180040e27  mov     rcx, [rbp+arg_8]
0x180040e2b  xor     r8d, r8d
0x180040e2e  mov     qword ptr [rbp+var_18+8], rax
0x180040e32  lea     rax, [rbp+arg_10]
0x180040e36  mov     [rsp+70h+var_50], rax
0x180040e3b  mov     dword ptr [rbp+var_30+8], 5
0x180040e42  mov     dword ptr [rbp+var_8], 10000h
0x180040e49  mov     word ptr [rbp+var_18], bx
0x180040e4d  call    cs:__imp_FWQueryFirewallRules
0x180040e53  test    eax, eax
0x180040e55  jz      short loc_180040E94
0x180040e57  jg      short loc_180040E5D
0x180040e59  mov     ebx, eax
0x180040e5b  jmp     short loc_180040E66
0x180040e5d  movzx   ebx, ax
0x180040e60  or      ebx, 80070000h
0x180040e66  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e6d  cmp     rcx, r15
0x180040e70  jz      loc_180040F8B
0x180040e76  test    [rcx+1Ch], r14d
0x180040e7a  jz      loc_180040F8B
0x180040e80  cmp     byte ptr [rcx+19h], 2
0x180040e84  jb      loc_180040F8B
0x180040e8a  mov     edx, 1Dh
0x180040e8f  jmp     loc_180040DD8
0x180040e94  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e9b  xor     ebx, ebx
0x180040e9d  cmp     rcx, r15
0x180040ea0  jz      short loc_180040EC8
0x180040ea2  test    [rcx+1Ch], r14d
0x180040ea6  jz      short loc_180040EC8
0x180040ea8  cmp     byte ptr [rcx+19h], 5
0x180040eac  jb      short loc_180040EC8
0x180040eae  mov     r9d, [rbp+arg_0]
0x180040eb2  lea     edx, [rbx+1Eh]
0x180040eb5  mov     rcx, [rcx+10h]
0x180040eb9  mov     r8, r12
0x180040ebc  call    WPP_SF_d
0x180040ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ec8  mov     rdi, [rbp+arg_10]
0x180040ecc  test    rdi, rdi
0x180040ecf  jz      loc_180040F8B
0x180040ed5  mov     edx, 1
0x180040eda  movzx   eax, word ptr [rdi+124h]
0x180040ee1  test    dl, al
0x180040ee3  jnz     loc_180040F7F
0x180040ee9  or      ax, dx
0x180040eec  mov     rdx, rdi
0x180040eef  mov     [rdi+124h], ax
0x180040ef6  mov     rcx, [rbp+arg_8]
0x180040efa  call    cs:__imp_FWSetFirewallRule
0x180040f00  test    eax, eax
0x180040f02  jz      short loc_180040F46
0x180040f04  jg      short loc_180040F0A
0x180040f06  mov     ebx, eax
0x180040f08  jmp     short loc_180040F13
0x180040f0a  movzx   ebx, ax
0x180040f0d  or      ebx, 80070000h
0x180040f13  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f1a  cmp     rcx, r15
0x180040f1d  jz      short loc_180040F7A
0x180040f1f  test    [rcx+1Ch], r14d
0x180040f23  jz      short loc_180040F7A
0x180040f25  cmp     byte ptr [rcx+19h], 2
0x180040f29  jb      short loc_180040F7A
0x180040f2b  mov     r9, [rdi+10h]
0x180040f2f  mov     edx, 1Fh
0x180040f34  mov     rcx, [rcx+10h]
0x180040f38  mov     r8, r12
0x180040f3b  mov     dword ptr [rsp+70h+var_50], eax
0x180040f3f  call    WPP_SF_SD
0x180040f44  jmp     short loc_180040F73
0x180040f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f4d  cmp     rcx, r15
0x180040f50  jz      short loc_180040F7A
0x180040f52  test    [rcx+1Ch], r14d
0x180040f56  jz      short loc_180040F7A
0x180040f58  cmp     byte ptr [rcx+19h], 5
0x180040f5c  jb      short loc_180040F7A
0x180040f5e  mov     r9, [rdi+10h]
0x180040f62  mov     edx, 20h ; ' '
0x180040f67  mov     rcx, [rcx+10h]
0x180040f6b  mov     r8, r12
0x180040f6e  call    WPP_SF_S
0x180040f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f7a  mov     edx, 1
0x180040f7f  mov     rdi, [rdi]
0x180040f82  test    rdi, rdi
0x180040f85  jnz     loc_180040EDA
0x180040f8b  mov     rax, [rbp+arg_10]
0x180040f8f  test    rax, rax
0x180040f92  jz      short loc_180040FA4
0x180040f94  mov     rcx, rax
0x180040f97  call    cs:__imp_FWFreeFirewallRules
0x180040f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fa4  mov     rax, [rbp+arg_8]
0x180040fa8  test    rax, rax
0x180040fab  jz      short loc_180040FBD
0x180040fad  mov     rcx, rax
0x180040fb0  call    cs:__imp_FWClosePolicyStore
0x180040fb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fbd  cmp     rcx, r15
0x180040fc0  jz      short loc_180040FE2
0x180040fc2  test    [rcx+1Ch], r14d
0x180040fc6  jz      short loc_180040FE2
0x180040fc8  cmp     byte ptr [rcx+19h], 6
0x180040fcc  jb      short loc_180040FE2
0x180040fce  mov     rcx, [rcx+10h]
0x180040fd2  mov     edx, 21h ; '!'
0x180040fd7  mov     r9d, ebx
0x180040fda  mov     r8, r12
0x180040fdd  call    WPP_SF_d
0x180040fe2  mov     eax, ebx
0x180040fe4  mov     rbx, [rsp+70h+arg_18]
0x180040fec  add     rsp, 70h
0x180040ff0  pop     r15
0x180040ff2  pop     r14
0x180040ff4  pop     r12
0x180040ff6  pop     rdi
0x180040ff7  pop     rbp
0x180040ff8  retn
```
