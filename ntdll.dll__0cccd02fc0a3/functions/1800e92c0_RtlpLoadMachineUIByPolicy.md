# RtlpLoadMachineUIByPolicy

- ea: `0x1800e92c0`
- end: `0x1800e9440`
- name: `RtlpLoadMachineUIByPolicy`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180010280`
- `0x1800122d0`
- `0x1800d8a80`
- `0x1800e92c0`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`

## string_xrefs

- `0x1800e930b`: `\Registry\Machine\Software\Policies\Microsoft\MUI\Settings`

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
0x1800e92c0  mov     [rsp-18h+arg_0], rbx
0x1800e92c5  mov     [rsp-18h+arg_10], rsi
0x1800e92ca  push    rbp
0x1800e92cb  push    rdi
0x1800e92cc  push    r15
0x1800e92ce  mov     rbp, rsp
0x1800e92d1  sub     rsp, 70h
0x1800e92d5  xor     eax, eax
0x1800e92d7  mov     [rbp+Handle], 0
0x1800e92df  mov     [rbp+arg_8], 0
0x1800e92e3  xorps   xmm0, xmm0
0x1800e92e6  mov     [rbp+arg_18], ax
0x1800e92ea  mov     rdi, r8
0x1800e92ed  mov     rsi, rdx
0x1800e92f0  movups  [rbp+var_48], xmm0
0x1800e92f4  test    rdx, rdx
0x1800e92f7  jz      loc_1800E942C
0x1800e92fd  test    r8, r8
0x1800e9300  jz      loc_1800E942C
0x1800e9306  test    rcx, rcx
0x1800e9309  jnz     short loc_1800E9386
0x1800e930b  lea     rcx, aRegistryMachin_23; "\\Registry\\Machine\\Software\\Policies"...
0x1800e9312  mov     qword ptr [rbp+var_48+8], rcx
0x1800e9316  call    wcslen
0x1800e931b  add     rax, rax
0x1800e931e  mov     [rbp+var_38], 30h ; '0'
0x1800e9326  cmp     rax, 0FFFEh
0x1800e932c  mov     [rbp+var_20], 40h ; '@'
0x1800e9334  mov     ecx, 0FFFCh
0x1800e9339  lea     r8, [rbp+var_38]
0x1800e933d  cmovnb  rax, rcx
0x1800e9341  xorps   xmm0, xmm0
0x1800e9344  mov     word ptr [rbp+var_48], ax
0x1800e9348  lea     rcx, [rbp+Handle]
0x1800e934c  add     ax, 2
0x1800e9350  mov     edx, 20019h
0x1800e9355  mov     word ptr [rbp+var_48+2], ax
0x1800e9359  xor     eax, eax
0x1800e935b  mov     [rbp+Handle], rax
0x1800e935f  mov     [rbp+var_30], rax
0x1800e9363  lea     rax, [rbp+var_48]
0x1800e9367  mov     [rbp+var_28], rax
0x1800e936b  movdqu  [rbp+var_18], xmm0
0x1800e9370  call    NtOpenKey
0x1800e9375  mov     ebx, eax
0x1800e9377  test    eax, eax
0x1800e9379  js      loc_1800E9406
0x1800e937f  mov     rcx, [rbp+Handle]
0x1800e9383  mov     rdx, rsi
0x1800e9386  lea     r9, [rbp+arg_18]
0x1800e938a  lea     r8, [rbp+arg_8]
0x1800e938e  call    RtlpLoadPolicyLanguageSpec
0x1800e9393  mov     ebx, eax
0x1800e9395  test    eax, eax
0x1800e9397  jnz     short loc_1800E9406
0x1800e9399  mov     r8, [rdi]
0x1800e939c  lea     r15d, [rax+1]
0x1800e93a0  test    r8, r8
0x1800e93a3  jnz     short loc_1800E93C5
0x1800e93a5  mov     r8, rsi
0x1800e93a8  mov     dl, r15b
0x1800e93ab  mov     ecx, r15d
0x1800e93ae  call    RtlpMuiRegCreateLanguageList
0x1800e93b3  mov     [rdi], rax
0x1800e93b6  mov     r8, rax
0x1800e93b9  test    rax, rax
0x1800e93bc  jnz     short loc_1800E93D1
0x1800e93be  mov     ebx, 0C0000017h
0x1800e93c3  jmp     short loc_1800E9406
0x1800e93c5  movzx   eax, word ptr [r8+6]
0x1800e93ca  cmp     [r8+4], ax
0x1800e93cf  jnb     short loc_1800E9433
0x1800e93d1  movzx   eax, word ptr [r8+4]
0x1800e93d6  movzx   edx, [rbp+arg_8]
0x1800e93da  lea     rcx, [rax+rax*2]
0x1800e93de  mov     rax, [r8+18h]
0x1800e93e2  mov     [rax+rcx*2], dx
0x1800e93e6  mov     rcx, [rdi]
0x1800e93e9  movzx   eax, word ptr [rcx+4]
0x1800e93ed  mov     rcx, [rcx+18h]
0x1800e93f1  lea     rdx, [rax+rax*2]
0x1800e93f5  movzx   eax, [rbp+arg_18]
0x1800e93f9  mov     [rcx+rdx*2+4], ax
0x1800e93fe  mov     rax, [rdi]
0x1800e9401  add     [rax+4], r15w
0x1800e9406  mov     rcx, [rbp+Handle]; Handle
0x1800e940a  test    rcx, rcx
0x1800e940d  jz      short loc_1800E9414
0x1800e940f  call    NtClose
0x1800e9414  lea     r11, [rsp+70h+var_s0]
0x1800e9419  mov     eax, ebx
0x1800e941b  mov     rbx, [r11+20h]
0x1800e941f  mov     rsi, [r11+30h]
0x1800e9423  mov     rsp, r11
0x1800e9426  pop     r15
0x1800e9428  pop     rdi
0x1800e9429  pop     rbp
0x1800e942a  retn
0x1800e942c  mov     ebx, 0C000000Dh
0x1800e9431  jmp     short loc_1800E9406
0x1800e9433  mov     rcx, r8
0x1800e9436  call    RtlpMuiRegGrowLanguageList
0x1800e943b  jmp     loc_1800E93B3
```
