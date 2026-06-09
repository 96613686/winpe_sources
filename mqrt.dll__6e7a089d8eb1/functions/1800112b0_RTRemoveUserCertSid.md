# RTRemoveUserCertSid

- ea: `0x1800112b0`
- end: `0x180011383`
- name: `RTRemoveUserCertSid`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1800112b0`
- `0x180013c74`
- `0x180014458`
- `0x18001d560`
- `0x180023ca0`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall RTRemoveUserCertSid(__int64 *a1)
{
  int v2; // ebx
  unsigned __int16 v3; // r8
  __int64 v4; // rax
  bool v5; // dl
  void (*v6)(void); // rcx
  bool v7; // r8
  bool v8; // r9
  __int128 v10; // [rsp+40h] [rbp-28h] BYREF

  v2 = RtpOneTimeThreadInit();
  if ( v2 < 0 )
  {
    v3 = 1132;
LABEL_8:
    LogMsgHR(v2, (wchar_t *)L"rt/rtcert", v3);
    return (unsigned int)v2;
  }
  v4 = *a1;
  v10 = 0;
  v2 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v4 + 16))(a1, &v10);
  if ( v2 < 0 )
  {
    v3 = 1678;
    goto LABEL_8;
  }
  v2 = ADInit(v6, v5, v7, v8);
  if ( v2 < 0
    || (v2 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)g_pAD + 32LL))(g_pAD, 4, 0), v2 < 0) )
  {
    v3 = 330;
    goto LABEL_8;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800112b0  mov     [rsp+arg_10], rbx
0x1800112b5  mov     [rsp+arg_18], rsi
0x1800112ba  push    rdi
0x1800112bb  sub     rsp, 60h
0x1800112bf  mov     rax, cs:__security_cookie
0x1800112c6  xor     rax, rsp
0x1800112c9  mov     [rsp+68h+var_18], rax
0x1800112ce  mov     rsi, rdx
0x1800112d1  mov     rdi, rcx
0x1800112d4  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x1800112d9  mov     ebx, eax
0x1800112db  test    eax, eax
0x1800112dd  jns     short loc_1800112E7
0x1800112df  mov     r8d, 46Ch
0x1800112e5  jmp     short loc_180011354
0x1800112e7  mov     rax, [rdi]
0x1800112ea  lea     rdx, [rsp+68h+var_28]
0x1800112ef  xorps   xmm0, xmm0
0x1800112f2  mov     rcx, rdi
0x1800112f5  movups  [rsp+68h+var_28], xmm0
0x1800112fa  mov     rax, [rax+10h]
0x1800112fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011303  mov     ebx, eax
0x180011305  test    eax, eax
0x180011307  jns     short loc_180011311
0x180011309  mov     r8d, 68Eh
0x18001130f  jmp     short loc_180011354
0x180011311  call    ?ADInit@@YAJP6AXXZ_N11@Z; ADInit(void (*)(void),bool,bool,bool)
0x180011316  mov     ebx, eax
0x180011318  test    eax, eax
0x18001131a  js      short loc_18001134E
0x18001131c  mov     rcx, cs:?g_pAD@@3V?$P@VCBaseADProvider@@@@A; P<CBaseADProvider> g_pAD
0x180011323  lea     rdx, [rsp+68h+var_28]
0x180011328  xor     r9d, r9d
0x18001132b  mov     [rsp+68h+var_40], rsi
0x180011330  mov     [rsp+68h+var_48], rdx
0x180011335  xor     r8d, r8d
0x180011338  mov     rax, [rcx]
0x18001133b  lea     edx, [r9+4]
0x18001133f  mov     rax, [rax+20h]
0x180011343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011348  mov     ebx, eax
0x18001134a  test    eax, eax
0x18001134c  jns     short loc_180011362
0x18001134e  mov     r8d, 14Ah; unsigned __int16
0x180011354  lea     rdx, aRtRtcert; "rt/rtcert"
0x18001135b  mov     ecx, ebx; int
0x18001135d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011362  mov     eax, ebx
0x180011364  mov     rcx, [rsp+68h+var_18]
0x180011369  xor     rcx, rsp; StackCookie
0x18001136c  call    __security_check_cookie
0x180011371  lea     r11, [rsp+68h+var_8]
0x180011376  mov     rbx, [r11+20h]
0x18001137a  mov     rsi, [r11+28h]
0x18001137e  mov     rsp, r11
0x180011381  pop     rdi
0x180011382  retn
```
