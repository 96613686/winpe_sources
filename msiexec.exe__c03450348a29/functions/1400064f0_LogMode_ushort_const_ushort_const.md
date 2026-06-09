# LogMode(ushort const *,ushort const *)

- ea: `0x1400064f0`
- end: `0x140006694`
- name: `?LogMode@@YAHPEBG0@Z`
- size: `420`
- prototype: `__int64 __fastcall(LPCWSTR lpString1, LPCWSTR szLogFile)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400011e4`

## callees

- `0x1400064f0`
- `0x1400087bc`
- `0x140009820`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x140006615`
- `KERNEL32!lstrcmpW` at `0x140006629`
- `KERNEL32!lstrcmpW` at `0x14000663d`
- `KERNEL32!lstrcmpW` at `0x140006615`
- `KERNEL32!lstrcmpW` at `0x140006629`
- `KERNEL32!lstrcmpW` at `0x14000663d`
- `msi!__imp_MsiEnableLogW` at `0x140006664`
- `msi!__imp_MsiEnableLogW` at `0x140006664`

## pseudocode

```c
UINT __fastcall LogMode(WCHAR *lpString1, LPCWSTR szLogFile)
{
  int v4; // r11d
  int v5; // edx
  WCHAR v6; // cx
  LPCWSTR v7; // r10
  unsigned __int16 *v8; // r8
  int v9; // r9d
  int v10; // r14d
  int v11; // ebp
  int v12; // edi
  DWORD v13; // edi
  int v14; // edx
  unsigned __int16 v16[17]; // [rsp+20h] [rbp-78h] BYREF
  int v17; // [rsp+42h] [rbp-56h]
  int v18; // [rsp+46h] [rbp-52h]

  v4 = 1;
  if ( !szLogFile || !*szLogFile || StringCchCopyW(v16, 0x15u, L"mewuifsoarpcvxgh!") < 0 )
    return v4;
  v17 = 2818090;
  v18 = 100;
  v5 = 0;
  if ( lpString1 )
  {
    v6 = *lpString1;
    if ( *lpString1 )
    {
      v7 = lpString1;
LABEL_7:
      if ( v6 )
      {
        v8 = v16;
        v9 = v4;
        while ( *v8 )
        {
          if ( *v8 == (v6 | 0x20) )
          {
            v5 |= v9;
            v6 = *++v7;
            goto LABEL_7;
          }
          v9 *= 2;
          ++v8;
        }
        return v4;
      }
    }
  }
  v10 = v5 & 0x40000;
  v11 = v5 & 0x10000;
  v12 = v5 | 0x10FFF;
  if ( (v5 & 0x20000) == 0 )
    v12 = v5;
  if ( !v12 )
    v12 = 919;
  v13 = v12 & 0xFFF0FFFF;
  if ( lpString1 && *lpString1 && !v13 )
  {
    v14 = *lpString1 - (v4 + 42);
    if ( !v14 )
      v14 = lpString1[1];
    if ( !v14 || !lstrcmpW(lpString1, L"!") || !lstrcmpW(lpString1, L"+!") || !lstrcmpW(lpString1, L"!+") )
      v13 = 919;
  }
  return MsiEnableLogW(v13, szLogFile, (v10 != 0) | (v11 != 0 ? 2 : 0));
}

```

## disassembly

```asm
0x1400064f0  mov     [rsp+arg_10], rbx
0x1400064f5  push    rbp
0x1400064f6  push    rsi
0x1400064f7  push    rdi
0x1400064f8  push    r12
0x1400064fa  push    r13
0x1400064fc  push    r14
0x1400064fe  push    r15
0x140006500  sub     rsp, 60h
0x140006504  mov     rax, cs:__security_cookie
0x14000650b  xor     rax, rsp
0x14000650e  mov     [rsp+98h+var_48], rax
0x140006513  xor     r15d, r15d
0x140006516  mov     rsi, rdx
0x140006519  mov     rbx, rcx
0x14000651c  mov     r11d, 1
0x140006522  test    rdx, rdx
0x140006525  jz      loc_14000666C
0x14000652b  cmp     r15w, [rdx]
0x14000652f  jz      loc_14000666C
0x140006535  lea     r8, aMewuifsoarpcvx; "mewuifsoarpcvxgh!"
0x14000653c  lea     edx, [r11+14h]; unsigned __int64
0x140006540  lea     rcx, [rsp+98h+var_78]; unsigned __int16 *
0x140006545  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000654a  test    eax, eax
0x14000654c  js      loc_14000666C
0x140006552  mov     [rsp+98h+var_56], 2B002Ah
0x14000655a  lea     r12d, [r11+2Ah]
0x14000655e  mov     [rsp+98h+var_52], 64h ; 'd'
0x140006566  mov     edx, r15d
0x140006569  test    rbx, rbx
0x14000656c  jz      short loc_1400065B3
0x14000656e  movzx   ecx, word ptr [rbx]
0x140006571  test    cx, cx
0x140006574  jz      short loc_1400065B3
0x140006576  mov     r10, rbx
0x140006579  test    cx, cx
0x14000657c  jz      short loc_1400065B3
0x14000657e  lea     r8, [rsp+98h+var_78]
0x140006583  mov     r9d, r11d
0x140006586  cmp     [r8], r15w
0x14000658a  jz      loc_14000666C
0x140006590  movzx   eax, cx
0x140006593  or      ax, 20h
0x140006597  cmp     [r8], ax
0x14000659b  jz      short loc_1400065A6
0x14000659d  add     r9d, r9d
0x1400065a0  add     r8, 2
0x1400065a4  jmp     short loc_140006586
0x1400065a6  or      edx, r9d
0x1400065a9  add     r10, 2
0x1400065ad  movzx   ecx, word ptr [r10]
0x1400065b1  jmp     short loc_140006579
0x1400065b3  mov     r14d, edx
0x1400065b6  mov     ebp, edx
0x1400065b8  and     r14d, 40000h
0x1400065bf  and     ebp, 10000h
0x1400065c5  mov     edi, edx
0x1400065c7  mov     r13d, 397h
0x1400065cd  or      edi, 10FFFh
0x1400065d3  bt      edx, 11h
0x1400065d7  cmovnb  edi, edx
0x1400065da  test    edi, edi
0x1400065dc  cmovz   edi, r13d
0x1400065e0  and     edi, 0FFF0FFFFh
0x1400065e6  test    rbx, rbx
0x1400065e9  jz      short loc_14000664A
0x1400065eb  cmp     [rbx], r15w
0x1400065ef  jz      short loc_14000664A
0x1400065f1  test    edi, edi
0x1400065f3  jnz     short loc_14000664A
0x1400065f5  movzx   edx, word ptr [rbx]
0x1400065f8  sub     edx, r12d
0x1400065fb  jnz     short loc_140006607
0x1400065fd  movzx   edx, word ptr [rbx+2]
0x140006601  movzx   ecx, r15w
0x140006605  sub     edx, ecx
0x140006607  test    edx, edx
0x140006609  jz      short loc_140006647
0x14000660b  lea     rdx, asc_14000B940; "!"
0x140006612  mov     rcx, rbx; lpString1
0x140006615  call    cs:__imp_lstrcmpW
0x14000661b  test    eax, eax
0x14000661d  jz      short loc_140006647
0x14000661f  lea     rdx, asc_14000B944; "+!"
0x140006626  mov     rcx, rbx; lpString1
0x140006629  call    cs:__imp_lstrcmpW
0x14000662f  test    eax, eax
0x140006631  jz      short loc_140006647
0x140006633  lea     rdx, asc_14000B94C; "!+"
0x14000663a  mov     rcx, rbx; lpString1
0x14000663d  call    cs:__imp_lstrcmpW
0x140006643  test    eax, eax
0x140006645  jnz     short loc_14000664A
0x140006647  mov     edi, r13d
0x14000664a  neg     ebp
0x14000664c  mov     eax, r15d
0x14000664f  mov     rdx, rsi; szLogFile
0x140006652  mov     ecx, edi; dwLogMode
0x140006654  sbb     r8d, r8d
0x140006657  and     r8d, 2
0x14000665b  test    r14d, r14d
0x14000665e  setnz   al
0x140006661  or      r8d, eax; dwLogAttributes
0x140006664  call    cs:__imp_MsiEnableLogW
0x14000666a  jmp     short loc_14000666F
0x14000666c  mov     eax, r11d
0x14000666f  mov     rcx, [rsp+98h+var_48]
0x140006674  xor     rcx, rsp; StackCookie
0x140006677  call    __security_check_cookie
0x14000667c  mov     rbx, [rsp+98h+arg_10]
0x140006684  add     rsp, 60h
0x140006688  pop     r15
0x14000668a  pop     r14
0x14000668c  pop     r13
0x14000668e  pop     r12
0x140006690  pop     rdi
0x140006691  pop     rsi
0x140006692  pop     rbp
0x140006693  retn
```
