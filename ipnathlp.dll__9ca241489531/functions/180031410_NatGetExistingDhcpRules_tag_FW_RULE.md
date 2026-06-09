# NatGetExistingDhcpRules(_tag_FW_RULE * *)

- ea: `0x180031410`
- end: `0x1800315ba`
- name: `?NatGetExistingDhcpRules@@YAKPEAPEAU_tag_FW_RULE@@@Z`
- size: `426`
- prototype: `unsigned int __fastcall(struct _tag_FW_RULE **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002f690`

## callees

- `0x18000c750`
- `0x180031410`

## import_xrefs

- `FirewallAPI!FWQueryFirewallRules` at `0x1800314d4`
- `FirewallAPI!FWQueryFirewallRules` at `0x1800314d4`
- `FirewallAPI!FWClosePolicyStore` at `0x180031525`
- `FirewallAPI!FWClosePolicyStore` at `0x180031525`
- `FirewallAPI!FWOpenPolicyStore` at `0x180031467`
- `FirewallAPI!FWOpenPolicyStore` at `0x180031467`

## string_xrefs

- `0x18003147b`: `@ipnathlp.dll,-140`

## pseudocode

```c
__int64 __fastcall NatGetExistingDhcpRules(struct _tag_FW_RULE **a1)
{
  __int64 v2; // rdx
  unsigned int v3; // ebx
  __int64 v4; // r8
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int128 v8; // [rsp+30h] [rbp-40h] BYREF
  __int128 v9; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v10; // [rsp+50h] [rbp-20h]
  __int128 v11; // [rsp+58h] [rbp-18h] BYREF
  __int64 v12; // [rsp+68h] [rbp-8h]
  unsigned int v13; // [rsp+98h] [rbp+28h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+30h] BYREF

  v10 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v9 = 0;
  v8 = 0;
  v11 = 0;
  v3 = FWOpenPolicyStore(545, 0, 5, 1, 0, &v14);
  if ( v3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 21;
LABEL_14:
    WPP_SF_d(v6[2], v7, &WPP_213010f39927376708ca656d45278473_Traceguids, v3);
    goto LABEL_7;
  }
  v10 = L"@ipnathlp.dll,-140";
  *((_QWORD *)&v8 + 1) = &v9;
  *(_QWORD *)&v9 = 0x100000008LL;
  *((_QWORD *)&v11 + 1) = &v8;
  DWORD2(v9) = 5;
  LODWORD(v8) = 1;
  DWORD1(v11) = 1;
  LODWORD(v12) = 0x10000;
  LOWORD(v11) = 545;
  v3 = FWQueryFirewallRules(v14, &v11, 0, &v13, a1);
  if ( v3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 22;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_213010f39927376708ca656d45278473_Traceguids, v13);
  }
LABEL_7:
  if ( v14 )
    FWClosePolicyStore(v14, v2, v4);
  return v3;
}

```

## disassembly

```asm
0x180031410  mov     [rsp-18h+arg_0], rbx
0x180031415  push    rbp
0x180031416  push    rsi
0x180031417  push    rdi
0x180031418  mov     rbp, rsp
0x18003141b  sub     rsp, 70h
0x18003141f  xor     eax, eax
0x180031421  xor     edx, edx
0x180031423  xorps   xmm0, xmm0
0x180031426  mov     [rbp+var_20], rax
0x18003142a  mov     [rbp+var_8], rax
0x18003142e  mov     rdi, rcx
0x180031431  lea     rax, [rbp+arg_10]
0x180031435  mov     [rbp+arg_10], rdx
0x180031439  xorps   xmm1, xmm1
0x18003143c  mov     [rsp+70h+var_48], rax
0x180031441  mov     esi, 221h
0x180031446  mov     dword ptr [rsp+70h+var_50], edx
0x18003144a  mov     ecx, esi
0x18003144c  mov     [rbp+arg_8], edx
0x18003144f  mov     r9d, 1
0x180031455  mov     r8d, 5
0x18003145b  movups  [rbp+var_30], xmm0
0x18003145f  movups  [rbp+var_40], xmm0
0x180031463  movups  [rbp+var_18], xmm1
0x180031467  call    cs:__imp_FWOpenPolicyStore
0x18003146d  mov     ebx, eax
0x18003146f  test    eax, eax
0x180031471  jnz     loc_18003152D
0x180031477  mov     rcx, [rbp+arg_10]
0x18003147b  lea     rax, aIpnathlpDll140; "@ipnathlp.dll,-140"
0x180031482  mov     [rbp+var_20], rax
0x180031486  lea     r9, [rbp+arg_8]
0x18003148a  lea     rax, [rbp+var_30]
0x18003148e  mov     dword ptr [rbp+var_30+4], 1
0x180031495  mov     qword ptr [rbp+var_40+8], rax
0x180031499  lea     rdx, [rbp+var_18]
0x18003149d  lea     rax, [rbp+var_40]
0x1800314a1  mov     dword ptr [rbp+var_30], 8
0x1800314a8  xor     r8d, r8d
0x1800314ab  mov     qword ptr [rbp+var_18+8], rax
0x1800314af  mov     dword ptr [rbp+var_30+8], 5
0x1800314b6  mov     dword ptr [rbp+var_40], 1
0x1800314bd  mov     dword ptr [rbp+var_18+4], 1
0x1800314c4  mov     dword ptr [rbp+var_8], 10000h
0x1800314cb  mov     word ptr [rbp+var_18], si
0x1800314cf  mov     [rsp+70h+var_50], rdi
0x1800314d4  call    cs:__imp_FWQueryFirewallRules
0x1800314da  mov     ebx, eax
0x1800314dc  test    eax, eax
0x1800314de  jnz     loc_180031570
0x1800314e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800314eb  lea     rax, WPP_GLOBAL_Control
0x1800314f2  cmp     rcx, rax
0x1800314f5  jz      short loc_18003150A
0x1800314f7  test    dword ptr [rcx+1Ch], 200h
0x1800314fe  jz      short loc_18003150A
0x180031500  cmp     byte ptr [rcx+19h], 5
0x180031504  jnb     loc_18003159C
0x18003150a  mov     rcx, [rbp+arg_10]
0x18003150e  test    rcx, rcx
0x180031511  jnz     short loc_180031525
0x180031513  mov     eax, ebx
0x180031515  mov     rbx, [rsp+70h+arg_0]
0x18003151d  add     rsp, 70h
0x180031521  pop     rdi
0x180031522  pop     rsi
0x180031523  pop     rbp
0x180031524  retn
0x180031525  call    cs:__imp_FWClosePolicyStore
0x18003152b  jmp     short loc_180031513
0x18003152d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031534  lea     rax, WPP_GLOBAL_Control
0x18003153b  cmp     rcx, rax
0x18003153e  jz      short loc_18003150A
0x180031540  test    dword ptr [rcx+1Ch], 200h
0x180031547  jz      short loc_18003150A
0x180031549  cmp     byte ptr [rcx+19h], 2
0x18003154d  jb      short loc_18003150A
0x18003154f  mov     edx, 15h
0x180031554  jmp     short loc_18003155B
0x180031556  mov     edx, 16h
0x18003155b  mov     rcx, [rcx+10h]
0x18003155f  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x180031566  mov     r9d, ebx
0x180031569  call    WPP_SF_d
0x18003156e  jmp     short loc_18003150A
0x180031570  mov     rcx, cs:WPP_GLOBAL_Control
0x180031577  lea     rax, WPP_GLOBAL_Control
0x18003157e  cmp     rcx, rax
0x180031581  jz      short loc_18003150A
0x180031583  test    dword ptr [rcx+1Ch], 200h
0x18003158a  jz      loc_18003150A
0x180031590  cmp     byte ptr [rcx+19h], 2
0x180031594  jb      loc_18003150A
0x18003159a  jmp     short loc_180031556
0x18003159c  mov     r9d, [rbp+arg_8]
0x1800315a0  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x1800315a7  mov     rcx, [rcx+10h]
0x1800315ab  mov     edx, 17h
0x1800315b0  call    WPP_SF_d
0x1800315b5  jmp     loc_18003150A
```
