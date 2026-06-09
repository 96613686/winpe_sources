# RtlpLoadMachineUIByPolicy

- ea: `0x1800e9920`
- end: `0x1800e9aa0`
- name: `RtlpLoadMachineUIByPolicy`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180010280`
- `0x1800122d0`
- `0x1800d9790`
- `0x1800e9920`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`

## string_xrefs

- `0x1800e996b`: `\Registry\Machine\Software\Policies\Microsoft\MUI\Settings`

## pseudocode

```c
__int64 __fastcall RtlpLoadMachineUIByPolicy(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v4; // rsi
  size_t v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 LanguageList; // rax
  __int128 v11; // [rsp+28h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h]
  __int64 v13; // [rsp+40h] [rbp-30h]
  __int128 *v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  __int128 v16; // [rsp+58h] [rbp-18h]
  unsigned __int8 v17; // [rsp+98h] [rbp+28h] BYREF
  __int16 v18; // [rsp+A8h] [rbp+38h] BYREF

  v17 = 0;
  v18 = 0;
  v4 = a2;
  v11 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-1073741811;
  if ( !a1 )
  {
    *((_QWORD *)&v11 + 1) = L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\MUI\\Settings";
    v5 = 2 * wcslen(L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\MUI\\Settings");
    v12 = 48;
    v15 = 64;
    if ( v5 >= 0xFFFE )
      LOWORD(v5) = -4;
    LOWORD(v11) = v5;
    WORD1(v11) = v5 + 2;
    v13 = 0;
    v14 = &v11;
    v16 = 0;
    v6 = NtOpenKey();
    if ( v6 < 0 )
      return (unsigned int)v6;
    a1 = 0;
    a2 = v4;
  }
  v6 = RtlpLoadPolicyLanguageSpec(a1, a2, &v17, &v18);
  if ( !v6 )
  {
    v8 = *a3;
    if ( *a3 )
    {
      if ( *(_WORD *)(v8 + 4) < *(_WORD *)(v8 + 6) )
        goto LABEL_14;
      LanguageList = RtlpMuiRegGrowLanguageList(*a3);
    }
    else
    {
      LOBYTE(v7) = 1;
      LanguageList = RtlpMuiRegCreateLanguageList(1, v7, v4);
    }
    *a3 = LanguageList;
    v8 = LanguageList;
    if ( !LanguageList )
      return (unsigned int)-1073741801;
LABEL_14:
    *(_WORD *)(*(_QWORD *)(v8 + 24) + 6LL * *(unsigned __int16 *)(v8 + 4)) = v17;
    *(_WORD *)(*(_QWORD *)(*a3 + 24) + 6LL * (unsigned __int16)(*(_WORD *)(*a3 + 4))++ + 4) = v18;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800e9920  mov     [rsp-18h+arg_0], rbx
0x1800e9925  mov     [rsp-18h+arg_10], rsi
0x1800e992a  push    rbp
0x1800e992b  push    rdi
0x1800e992c  push    r15
0x1800e992e  mov     rbp, rsp
0x1800e9931  sub     rsp, 70h
0x1800e9935  xor     eax, eax
0x1800e9937  mov     [rbp+Handle], 0
0x1800e993f  mov     [rbp+arg_8], 0
0x1800e9943  xorps   xmm0, xmm0
0x1800e9946  mov     [rbp+arg_18], ax
0x1800e994a  mov     rdi, r8
0x1800e994d  mov     rsi, rdx
0x1800e9950  movups  [rbp+var_48], xmm0
0x1800e9954  test    rdx, rdx
0x1800e9957  jz      loc_1800E9A8C
0x1800e995d  test    r8, r8
0x1800e9960  jz      loc_1800E9A8C
0x1800e9966  test    rcx, rcx
0x1800e9969  jnz     short loc_1800E99E6
0x1800e996b  lea     rcx, aRegistryMachin_23; "\\Registry\\Machine\\Software\\Policies"...
0x1800e9972  mov     qword ptr [rbp+var_48+8], rcx
0x1800e9976  call    wcslen
0x1800e997b  add     rax, rax
0x1800e997e  mov     [rbp+var_38], 30h ; '0'
0x1800e9986  cmp     rax, 0FFFEh
0x1800e998c  mov     [rbp+var_20], 40h ; '@'
0x1800e9994  mov     ecx, 0FFFCh
0x1800e9999  lea     r8, [rbp+var_38]
0x1800e999d  cmovnb  rax, rcx
0x1800e99a1  xorps   xmm0, xmm0
0x1800e99a4  mov     word ptr [rbp+var_48], ax
0x1800e99a8  lea     rcx, [rbp+Handle]
0x1800e99ac  add     ax, 2
0x1800e99b0  mov     edx, 20019h
0x1800e99b5  mov     word ptr [rbp+var_48+2], ax
0x1800e99b9  xor     eax, eax
0x1800e99bb  mov     [rbp+Handle], rax
0x1800e99bf  mov     [rbp+var_30], rax
0x1800e99c3  lea     rax, [rbp+var_48]
0x1800e99c7  mov     [rbp+var_28], rax
0x1800e99cb  movdqu  [rbp+var_18], xmm0
0x1800e99d0  call    NtOpenKey
0x1800e99d5  mov     ebx, eax
0x1800e99d7  test    eax, eax
0x1800e99d9  js      loc_1800E9A66
0x1800e99df  mov     rcx, [rbp+Handle]
0x1800e99e3  mov     rdx, rsi
0x1800e99e6  lea     r9, [rbp+arg_18]
0x1800e99ea  lea     r8, [rbp+arg_8]
0x1800e99ee  call    RtlpLoadPolicyLanguageSpec
0x1800e99f3  mov     ebx, eax
0x1800e99f5  test    eax, eax
0x1800e99f7  jnz     short loc_1800E9A66
0x1800e99f9  mov     r8, [rdi]
0x1800e99fc  lea     r15d, [rax+1]
0x1800e9a00  test    r8, r8
0x1800e9a03  jnz     short loc_1800E9A25
0x1800e9a05  mov     r8, rsi
0x1800e9a08  mov     dl, r15b
0x1800e9a0b  mov     ecx, r15d
0x1800e9a0e  call    RtlpMuiRegCreateLanguageList
0x1800e9a13  mov     [rdi], rax
0x1800e9a16  mov     r8, rax
0x1800e9a19  test    rax, rax
0x1800e9a1c  jnz     short loc_1800E9A31
0x1800e9a1e  mov     ebx, 0C0000017h
0x1800e9a23  jmp     short loc_1800E9A66
0x1800e9a25  movzx   eax, word ptr [r8+6]
0x1800e9a2a  cmp     [r8+4], ax
0x1800e9a2f  jnb     short loc_1800E9A93
0x1800e9a31  movzx   eax, word ptr [r8+4]
0x1800e9a36  movzx   edx, [rbp+arg_8]
0x1800e9a3a  lea     rcx, [rax+rax*2]
0x1800e9a3e  mov     rax, [r8+18h]
0x1800e9a42  mov     [rax+rcx*2], dx
0x1800e9a46  mov     rcx, [rdi]
0x1800e9a49  movzx   eax, word ptr [rcx+4]
0x1800e9a4d  mov     rcx, [rcx+18h]
0x1800e9a51  lea     rdx, [rax+rax*2]
0x1800e9a55  movzx   eax, [rbp+arg_18]
0x1800e9a59  mov     [rcx+rdx*2+4], ax
0x1800e9a5e  mov     rax, [rdi]
0x1800e9a61  add     [rax+4], r15w
0x1800e9a66  mov     rcx, [rbp+Handle]; Handle
0x1800e9a6a  test    rcx, rcx
0x1800e9a6d  jz      short loc_1800E9A74
0x1800e9a6f  call    NtClose
0x1800e9a74  lea     r11, [rsp+70h+var_s0]
0x1800e9a79  mov     eax, ebx
0x1800e9a7b  mov     rbx, [r11+20h]
0x1800e9a7f  mov     rsi, [r11+30h]
0x1800e9a83  mov     rsp, r11
0x1800e9a86  pop     r15
0x1800e9a88  pop     rdi
0x1800e9a89  pop     rbp
0x1800e9a8a  retn
0x1800e9a8c  mov     ebx, 0C000000Dh
0x1800e9a91  jmp     short loc_1800E9A66
0x1800e9a93  mov     rcx, r8
0x1800e9a96  call    RtlpMuiRegGrowLanguageList
0x1800e9a9b  jmp     loc_1800E9A13
```
