# NatGetExistingDhcpRules(_tag_FW_RULE * *)

- ea: `0x180033a50`
- end: `0x180033c0d`
- name: `?NatGetExistingDhcpRules@@YAKPEAPEAU_tag_FW_RULE@@@Z`
- size: `445`
- prototype: `unsigned int __fastcall(struct _tag_FW_RULE **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002259c`

## callees

- `0x18000d090`
- `0x180033a50`

## import_xrefs

- `FirewallAPI!FWQueryFirewallRules` at `0x180033b1a`
- `FirewallAPI!FWQueryFirewallRules` at `0x180033b1a`
- `FirewallAPI!FWClosePolicyStore` at `0x180033b72`
- `FirewallAPI!FWClosePolicyStore` at `0x180033b72`
- `FirewallAPI!FWOpenPolicyStore` at `0x180033aa7`
- `FirewallAPI!FWOpenPolicyStore` at `0x180033aa7`

## string_xrefs

- `0x180033ac1`: `@ipnathlp.dll,-140`

## pseudocode

```c
__int64 __fastcall NatGetExistingDhcpRules(struct _tag_FW_RULE **a1)
{
  unsigned int v2; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int128 v6; // [rsp+30h] [rbp-40h] BYREF
  __int128 v7; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v8; // [rsp+50h] [rbp-20h]
  __int128 v9; // [rsp+58h] [rbp-18h] BYREF
  __int64 v10; // [rsp+68h] [rbp-8h]
  unsigned int v11; // [rsp+98h] [rbp+28h] BYREF
  __int64 v12; // [rsp+A0h] [rbp+30h] BYREF

  v8 = 0;
  v10 = 0;
  v12 = 0;
  v11 = 0;
  v7 = 0;
  v6 = 0;
  v9 = 0;
  v2 = FWOpenPolicyStore(545, 0, 5, 1, 0, &v12, 0);
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v5 = 21;
LABEL_14:
    WPP_SF_d(v4[2], v5, &WPP_213010f39927376708ca656d45278473_Traceguids, v2);
    goto LABEL_7;
  }
  v8 = L"@ipnathlp.dll,-140";
  *((_QWORD *)&v6 + 1) = &v7;
  *(_QWORD *)&v7 = 0x100000008LL;
  *((_QWORD *)&v9 + 1) = &v6;
  DWORD2(v7) = 5;
  LODWORD(v6) = 1;
  DWORD1(v9) = 1;
  LODWORD(v10) = 0x10000;
  LOWORD(v9) = 545;
  v2 = FWQueryFirewallRules(v12, &v9, 0, &v11, a1);
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v5 = 22;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_213010f39927376708ca656d45278473_Traceguids, v11);
  }
LABEL_7:
  if ( v12 )
    FWClosePolicyStore(v12);
  return v2;
}

```

## disassembly

```asm
0x180033a50  mov     [rsp-18h+arg_0], rbx
0x180033a55  push    rbp
0x180033a56  push    rsi
0x180033a57  push    rdi
0x180033a58  mov     rbp, rsp
0x180033a5b  sub     rsp, 70h
0x180033a5f  xor     eax, eax
0x180033a61  xor     edx, edx
0x180033a63  xorps   xmm0, xmm0
0x180033a66  mov     [rbp+var_20], rax
0x180033a6a  mov     [rbp+var_8], rax
0x180033a6e  mov     rdi, rcx
0x180033a71  lea     rax, [rbp+arg_10]
0x180033a75  mov     [rbp+arg_10], rdx
0x180033a79  xorps   xmm1, xmm1
0x180033a7c  mov     [rsp+70h+var_48], rax
0x180033a81  mov     esi, 221h
0x180033a86  mov     dword ptr [rsp+70h+var_50], edx
0x180033a8a  mov     ecx, esi
0x180033a8c  mov     [rbp+arg_8], edx
0x180033a8f  mov     r9d, 1
0x180033a95  mov     r8d, 5
0x180033a9b  movups  [rbp+var_30], xmm0
0x180033a9f  movups  [rbp+var_40], xmm0
0x180033aa3  movups  [rbp+var_18], xmm1
0x180033aa7  call    cs:__imp_FWOpenPolicyStore
0x180033aae  nop     dword ptr [rax+rax+00h]
0x180033ab3  mov     ebx, eax
0x180033ab5  test    eax, eax
0x180033ab7  jnz     loc_180033B80
0x180033abd  mov     rcx, [rbp+arg_10]
0x180033ac1  lea     rax, aIpnathlpDll140; "@ipnathlp.dll,-140"
0x180033ac8  mov     [rbp+var_20], rax
0x180033acc  lea     r9, [rbp+arg_8]
0x180033ad0  lea     rax, [rbp+var_30]
0x180033ad4  mov     dword ptr [rbp+var_30+4], 1
0x180033adb  mov     qword ptr [rbp+var_40+8], rax
0x180033adf  lea     rdx, [rbp+var_18]
0x180033ae3  lea     rax, [rbp+var_40]
0x180033ae7  mov     dword ptr [rbp+var_30], 8
0x180033aee  xor     r8d, r8d
0x180033af1  mov     qword ptr [rbp+var_18+8], rax
0x180033af5  mov     dword ptr [rbp+var_30+8], 5
0x180033afc  mov     dword ptr [rbp+var_40], 1
0x180033b03  mov     dword ptr [rbp+var_18+4], 1
0x180033b0a  mov     dword ptr [rbp+var_8], 10000h
0x180033b11  mov     word ptr [rbp+var_18], si
0x180033b15  mov     [rsp+70h+var_50], rdi
0x180033b1a  call    cs:__imp_FWQueryFirewallRules
0x180033b21  nop     dword ptr [rax+rax+00h]
0x180033b26  mov     ebx, eax
0x180033b28  test    eax, eax
0x180033b2a  jnz     loc_180033BC3
0x180033b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b37  lea     rax, WPP_GLOBAL_Control
0x180033b3e  cmp     rcx, rax
0x180033b41  jz      short loc_180033B56
0x180033b43  test    dword ptr [rcx+1Ch], 200h
0x180033b4a  jz      short loc_180033B56
0x180033b4c  cmp     byte ptr [rcx+19h], 5
0x180033b50  jnb     loc_180033BEF
0x180033b56  mov     rcx, [rbp+arg_10]
0x180033b5a  test    rcx, rcx
0x180033b5d  jnz     short loc_180033B72
0x180033b5f  mov     eax, ebx
0x180033b61  mov     rbx, [rsp+70h+arg_0]
0x180033b69  add     rsp, 70h
0x180033b6d  pop     rdi
0x180033b6e  pop     rsi
0x180033b6f  pop     rbp
0x180033b70  retn
0x180033b72  call    cs:__imp_FWClosePolicyStore
0x180033b79  nop     dword ptr [rax+rax+00h]
0x180033b7e  jmp     short loc_180033B5F
0x180033b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b87  lea     rax, WPP_GLOBAL_Control
0x180033b8e  cmp     rcx, rax
0x180033b91  jz      short loc_180033B56
0x180033b93  test    dword ptr [rcx+1Ch], 200h
0x180033b9a  jz      short loc_180033B56
0x180033b9c  cmp     byte ptr [rcx+19h], 2
0x180033ba0  jb      short loc_180033B56
0x180033ba2  mov     edx, 15h
0x180033ba7  jmp     short loc_180033BAE
0x180033ba9  mov     edx, 16h
0x180033bae  mov     rcx, [rcx+10h]
0x180033bb2  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x180033bb9  mov     r9d, ebx
0x180033bbc  call    WPP_SF_d
0x180033bc1  jmp     short loc_180033B56
0x180033bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bca  lea     rax, WPP_GLOBAL_Control
0x180033bd1  cmp     rcx, rax
0x180033bd4  jz      short loc_180033B56
0x180033bd6  test    dword ptr [rcx+1Ch], 200h
0x180033bdd  jz      loc_180033B56
0x180033be3  cmp     byte ptr [rcx+19h], 2
0x180033be7  jb      loc_180033B56
0x180033bed  jmp     short loc_180033BA9
0x180033bef  mov     r9d, [rbp+arg_8]
0x180033bf3  lea     r8, WPP_213010f39927376708ca656d45278473_Traceguids
0x180033bfa  mov     rcx, [rcx+10h]
0x180033bfe  mov     edx, 17h
0x180033c03  call    WPP_SF_d
0x180033c08  jmp     loc_180033B56
```
