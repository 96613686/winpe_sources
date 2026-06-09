# RTpExtractDomainNameFromDLPath(wchar_t const *)

- ea: `0x180017edc`
- end: `0x18001812b`
- name: `?RTpExtractDomainNameFromDLPath@@YAPEA_WPEB_W@Z`
- size: `591`
- prototype: `wchar_t *__fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000e200`

## callees

- `0x180006f5c`
- `0x180006fdc`
- `0x180007e10`
- `0x1800092c0`
- `0x180013c74`
- `0x180017edc`
- `0x180021010`
- `0x180023ca0`

## import_xrefs

- `msvcrt!free` at `0x180017fa9`
- `msvcrt!free` at `0x180017fd4`
- `msvcrt!free` at `0x18001807a`
- `msvcrt!free` at `0x180018084`
- `msvcrt!free` at `0x1800180d9`
- `msvcrt!free` at `0x1800180e3`
- `msvcrt!free` at `0x1800180f1`
- `msvcrt!free` at `0x1800180fb`
- `msvcrt!free` at `0x180017fa9`
- `msvcrt!free` at `0x180017fd4`
- `msvcrt!free` at `0x18001807a`
- `msvcrt!free` at `0x180018084`
- `msvcrt!free` at `0x1800180d9`
- `msvcrt!free` at `0x1800180e3`
- `msvcrt!free` at `0x1800180f1`
- `msvcrt!free` at `0x1800180fb`
- `msvcrt!wcsstr` at `0x180017fc3`
- `msvcrt!wcsstr` at `0x18001801a`
- `msvcrt!wcsstr` at `0x180017fc3`
- `msvcrt!wcsstr` at `0x18001801a`
- `msvcrt!_wcsnicmp` at `0x180017f43`
- `msvcrt!_wcsnicmp` at `0x180017f43`
- `USER32!CharUpperW` at `0x180017fb5`
- `USER32!CharUpperW` at `0x180017fb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
wchar_t *__fastcall RTpExtractDomainNameFromDLPath(const wchar_t *a1)
{
  unsigned int v3; // edi
  wchar_t *v4; // rbx
  int v5; // eax
  wchar_t *v6; // rbp
  char v7; // r14
  unsigned __int64 v8; // r12
  wchar_t *v9; // rdi
  wchar_t *v10; // rsi
  const wchar_t *i; // rbp
  wchar_t *v12; // rax
  wchar_t *v13; // r15
  unsigned __int64 v14; // r14
  int v15; // eax
  int v16; // eax
  wchar_t SubStr[8]; // [rsp+30h] [rbp-58h] BYREF
  wchar_t String2[8]; // [rsp+40h] [rbp-48h] BYREF

  wcscpy(String2, L"LDAP");
  wcscpy(SubStr, L",DC=");
  if ( _wcsnicmp(a1, String2, 4u) )
    return 0;
  v3 = mqwcslen(a1) + 1;
  v4 = (wchar_t *)MmAllocate(saturated_mul(v3, 2u));
  v5 = StringCchCopyW(v4, v3, a1);
  if ( v5 < 0 )
  {
    LogMsgHR(v5, (wchar_t *)L"rt/rtutil", 0x50u);
    free(v4);
    return 0;
  }
  CharUpperW(v4);
  v6 = wcsstr(v4, SubStr);
  if ( !v6 )
  {
    free(v4);
    return 0;
  }
  v7 = 0;
  v8 = mqwcslen(a1) + 1;
  v9 = (wchar_t *)MmAllocate(saturated_mul(v8, 2u));
  v10 = v9;
  for ( i = v6 + 4; ; i = v13 + 4 )
  {
    v12 = wcsstr(i, SubStr);
    v13 = v12;
    if ( !v12 )
      break;
    if ( v7 )
      *v10++ = 46;
    v14 = v12 - i;
    v15 = StringCchCopyNW(v10, v14 + 1, i, v14);
    if ( v15 < 0 )
    {
      LogMsgHR(v15, (wchar_t *)L"rt/rtutil", 0x5Au);
      free(v9);
      free(v4);
      return 0;
    }
    v10 += v14;
    v7 = 1;
  }
  if ( v7 )
    *v10++ = 46;
  *v10 = 0;
  v16 = StringCchCatW(v10, v8 - (v10 - v9), i);
  if ( v16 < 0 )
  {
    LogMsgHR(v16, (wchar_t *)L"rt/rtutil", 0x55u);
    free(v9);
    free(v4);
    return 0;
  }
  free(0);
  free(v4);
  return v9;
}

```

## disassembly

```asm
0x180017edc  mov     [rsp+arg_8], rbx
0x180017ee1  mov     [rsp+arg_10], rbp
0x180017ee6  push    rsi
0x180017ee7  push    rdi
0x180017ee8  push    r12
0x180017eea  push    r14
0x180017eec  push    r15
0x180017eee  sub     rsp, 60h
0x180017ef2  mov     rax, cs:__security_cookie
0x180017ef9  xor     rax, rsp
0x180017efc  mov     [rsp+88h+var_38], rax
0x180017f01  mov     rsi, rcx
0x180017f04  movsd   xmm0, qword ptr cs:aLdap; "LDAP"
0x180017f0c  movsd   qword ptr [rsp+88h+String2], xmm0
0x180017f12  movzx   eax, word ptr cs:aLdap+8; ""
0x180017f19  mov     [rsp+88h+var_40], ax
0x180017f1e  movsd   xmm0, qword ptr cs:aDc; ",DC="
0x180017f26  movsd   qword ptr [rsp+88h+SubStr], xmm0
0x180017f2c  movzx   eax, word ptr cs:aDc+8; ""
0x180017f33  mov     [rsp+88h+var_50], ax
0x180017f38  mov     r8d, 4; MaxCount
0x180017f3e  lea     rdx, [rsp+88h+String2]; String2
0x180017f43  call    cs:__imp__wcsnicmp
0x180017f49  test    eax, eax
0x180017f4b  jz      short loc_180017F54
0x180017f4d  xor     eax, eax
0x180017f4f  jmp     loc_180018105
0x180017f54  mov     rcx, rsi; wchar_t *
0x180017f57  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180017f5c  lea     edi, [rax+1]
0x180017f5f  mov     eax, 2
0x180017f64  mul     rdi
0x180017f67  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180017f6e  cmovb   rax, r15
0x180017f72  mov     rcx, rax; unsigned __int64
0x180017f75  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180017f7a  mov     rbx, rax
0x180017f7d  mov     [rsp+88h+var_68], rax
0x180017f82  mov     r8, rsi; wchar_t *
0x180017f85  mov     edx, edi; unsigned __int64
0x180017f87  mov     rcx, rax; wchar_t *
0x180017f8a  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180017f8f  test    eax, eax
0x180017f91  jns     short loc_180017FB2
0x180017f93  lea     r8d, [r15+51h]; unsigned __int16
0x180017f97  lea     rdx, aRtRtutil; "rt/rtutil"
0x180017f9e  mov     ecx, eax; int
0x180017fa0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017fa5  nop
0x180017fa6  mov     rcx, rbx; Block
0x180017fa9  call    cs:__imp_free
0x180017faf  nop
0x180017fb0  jmp     short loc_180017F4D
0x180017fb2  mov     rcx, rbx; lpsz
0x180017fb5  call    cs:__imp_CharUpperW
0x180017fbb  lea     rdx, [rsp+88h+SubStr]; SubStr
0x180017fc0  mov     rcx, rbx; Str
0x180017fc3  call    cs:__imp_wcsstr
0x180017fc9  mov     rbp, rax
0x180017fcc  test    rax, rax
0x180017fcf  jnz     short loc_180017FE0
0x180017fd1  mov     rcx, rbx; Block
0x180017fd4  call    cs:__imp_free
0x180017fda  nop
0x180017fdb  jmp     loc_180017F4D
0x180017fe0  xor     r14b, r14b
0x180017fe3  mov     rcx, rsi; wchar_t *
0x180017fe6  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180017feb  lea     r12d, [rax+1]
0x180017fef  mov     eax, 2
0x180017ff4  mul     r12
0x180017ff7  cmovb   rax, r15
0x180017ffb  mov     rcx, rax; unsigned __int64
0x180017ffe  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180018003  mov     rdi, rax
0x180018006  mov     [rsp+88h+var_60], rax
0x18001800b  mov     rsi, rax
0x18001800e  add     rbp, 8
0x180018012  lea     rdx, [rsp+88h+SubStr]; SubStr
0x180018017  mov     rcx, rbp; Str
0x18001801a  call    cs:__imp_wcsstr
0x180018020  mov     r15, rax
0x180018023  test    rax, rax
0x180018026  jz      short loc_180018090
0x180018028  test    r14b, r14b
0x18001802b  jz      short loc_180018036
0x18001802d  mov     word ptr [rsi], 2Eh ; '.'
0x180018032  add     rsi, 2
0x180018036  mov     r14, r15
0x180018039  sub     r14, rbp
0x18001803c  sar     r14, 1
0x18001803f  lea     rdx, [r14+1]; unsigned __int64
0x180018043  mov     r9, r14; unsigned __int64
0x180018046  mov     r8, rbp; wchar_t *
0x180018049  mov     rcx, rsi; wchar_t *
0x18001804c  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x180018051  test    eax, eax
0x180018053  js      short loc_180018062
0x180018055  lea     rsi, [rsi+r14*2]
0x180018059  mov     r14b, 1
0x18001805c  lea     rbp, [r15+8]
0x180018060  jmp     short loc_180018012
0x180018062  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x180018068  lea     rdx, aRtRtutil; "rt/rtutil"
0x18001806f  mov     ecx, eax; int
0x180018071  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018076  nop
0x180018077  mov     rcx, rdi; Block
0x18001807a  call    cs:__imp_free
0x180018080  nop
0x180018081  mov     rcx, rbx; Block
0x180018084  call    cs:__imp_free
0x18001808a  nop
0x18001808b  jmp     loc_180017F4D
0x180018090  test    r14b, r14b
0x180018093  jz      short loc_18001809E
0x180018095  mov     word ptr [rsi], 2Eh ; '.'
0x18001809a  add     rsi, 2
0x18001809e  xor     eax, eax
0x1800180a0  mov     [rsi], ax
0x1800180a3  mov     rax, rsi
0x1800180a6  sub     rax, rdi
0x1800180a9  sar     rax, 1
0x1800180ac  sub     r12, rax
0x1800180af  mov     r8, rbp; wchar_t *
0x1800180b2  mov     rdx, r12; unsigned __int64
0x1800180b5  mov     rcx, rsi; wchar_t *
0x1800180b8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800180bd  test    eax, eax
0x1800180bf  jns     short loc_1800180EF
0x1800180c1  mov     r8d, 55h ; 'U'; unsigned __int16
0x1800180c7  lea     rdx, aRtRtutil; "rt/rtutil"
0x1800180ce  mov     ecx, eax; int
0x1800180d0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800180d5  nop
0x1800180d6  mov     rcx, rdi; Block
0x1800180d9  call    cs:__imp_free
0x1800180df  nop
0x1800180e0  mov     rcx, rbx; Block
0x1800180e3  call    cs:__imp_free
0x1800180e9  nop
0x1800180ea  jmp     loc_180017F4D
0x1800180ef  xor     ecx, ecx; Block
0x1800180f1  call    cs:__imp_free
0x1800180f7  nop
0x1800180f8  mov     rcx, rbx; Block
0x1800180fb  call    cs:__imp_free
0x180018101  nop
0x180018102  mov     rax, rdi
0x180018105  mov     rcx, [rsp+88h+var_38]
0x18001810a  xor     rcx, rsp; StackCookie
0x18001810d  call    __security_check_cookie
0x180018112  lea     r11, [rsp+88h+var_28]
0x180018117  mov     rbx, [r11+38h]
0x18001811b  mov     rbp, [r11+40h]
0x18001811f  mov     rsp, r11
0x180018122  pop     r15
0x180018124  pop     r14
0x180018126  pop     r12
0x180018128  pop     rdi
0x180018129  pop     rsi
0x18001812a  retn
```
