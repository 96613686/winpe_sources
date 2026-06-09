# PsmCreateMatchToken

- ea: `0x180007ec0`
- end: `0x180008146`
- name: `PsmCreateMatchToken`
- size: `646`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001010`
- `0x1800038d0`
- `0x180007ec0`
- `0x180008340`
- `0x180009d86`
- `0x180009dd0`

## import_xrefs

- `ntdll!NtClose` at `0x180008114`
- `ntdll!NtClose` at `0x180008114`
- `ntdll!RtlQueryPackageClaims` at `0x180007fe3`
- `ntdll!RtlQueryPackageClaims` at `0x180007fe3`
- `ntdll!NtDuplicateToken` at `0x180007f84`
- `ntdll!NtDuplicateToken` at `0x180007f84`

## pseudocode

```c
__int64 __fastcall PsmCreateMatchToken(__int64 a1, void *a2, int a3, HANDLE *a4)
{
  char v5; // si
  int v8; // ebx
  int v9; // r14d
  int v10; // eax
  UUID *p_Buf1; // r15
  int v12; // edi
  int HostIdFromProcessToken; // eax
  __int64 *v14; // rcx
  HANDLE v15; // rcx
  signed __int32 v16; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  __int64 v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h] BYREF
  __int128 Buf1; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v23; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[142]; // [rsp+92h] [rbp-6Eh] BYREF
  WCHAR v25[128]; // [rsp+120h] [rbp+20h] BYREF

  v16 = 0;
  v20 = 0;
  v18 = 0;
  v5 = a3;
  Handle = 0;
  v21 = 0;
  v19 = 0;
  Buf1 = 0;
  if ( (a3 & 0xFFFFFFC0) != 0 )
    return 3221225713LL;
  if ( (a3 & 2) == 0 && !NtCurrentTeb()->IsImpersonating )
    return 3221225564LL;
  v8 = NtDuplicateToken(a2, 0, 0, 0, TokenPrimary, &Handle);
  if ( v8 >= 0 )
  {
    v9 = 0;
    v20 = 130;
    v21 = 256;
    v23 = 33;
    v10 = RtlQueryPackageClaims(a1, v25, &v21, v24, &v20, &Buf1, &v19, 0);
    v8 = v10;
    if ( (v5 & 1) == 0 )
      v9 = v19;
    if ( v10 < 0 )
    {
      if ( v10 == -1073741275 )
      {
        v8 = 0;
LABEL_30:
        v15 = 0;
        *a4 = Handle;
        Handle = 0;
        goto LABEL_32;
      }
LABEL_31:
      v15 = Handle;
LABEL_32:
      if ( v15 )
        NtClose(v15);
      return (unsigned int)v8;
    }
    if ( !memcmp_0(&Buf1, NullGuid, 0x10u) || (v5 & 4) == 0 )
    {
      p_Buf1 = 0;
    }
    else
    {
      v9 |= 0x40000000u;
      p_Buf1 = (UUID *)&Buf1;
    }
    v12 = v9 | 0x40;
    if ( (v5 & 8) == 0 )
      v12 = v9;
    if ( (v5 & 0x20) != 0 )
    {
      v12 |= 0x100u;
    }
    else if ( (v5 & 0x10) != 0 )
    {
      v12 |= 0x80u;
    }
    if ( (v5 & 4) != 0 )
    {
      v8 = PsmQueryBackgroundActivationType(a1, &v16);
      if ( v8 < 0 )
        goto LABEL_31;
      HostIdFromProcessToken = PsmpGetHostIdFromProcessToken(a1, &v18);
      v8 = HostIdFromProcessToken;
      if ( HostIdFromProcessToken < 0 )
      {
        if ( HostIdFromProcessToken != -1073741275 )
          goto LABEL_31;
        v14 = 0;
        goto LABEL_29;
      }
    }
    else
    {
      v18 = -1;
    }
    v14 = &v18;
LABEL_29:
    v8 = PsmpAdjustActivationToken(
           Handle,
           v12 | 0x80000000,
           v16,
           v25,
           &v23,
           (PackageOrigin)BYTE4(v19),
           p_Buf1,
           v14,
           0,
           0);
    if ( v8 >= 0 )
      goto LABEL_30;
    goto LABEL_31;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007ec0  mov     [rsp-8+arg_10], rbx
0x180007ec5  push    rbp
0x180007ec6  push    rsi
0x180007ec7  push    rdi
0x180007ec8  push    r12
0x180007eca  push    r13
0x180007ecc  push    r14
0x180007ece  push    r15
0x180007ed0  lea     rbp, [rsp-130h]
0x180007ed8  sub     rsp, 230h
0x180007edf  mov     rax, cs:__security_cookie
0x180007ee6  xor     rax, rsp
0x180007ee9  mov     [rbp+160h+var_40], rax
0x180007ef0  mov     [rsp+260h+var_210], 0
0x180007ef8  xorps   xmm0, xmm0
0x180007efb  mov     [rsp+260h+var_1F0], 0
0x180007f04  mov     r13, r9
0x180007f07  mov     [rsp+260h+var_200], 0
0x180007f10  mov     esi, r8d
0x180007f13  mov     [rsp+260h+Handle], 0
0x180007f1c  mov     r10, rdx
0x180007f1f  mov     [rsp+260h+var_1E8], 0
0x180007f28  mov     r12, rcx
0x180007f2b  mov     [rsp+260h+var_1F8], 0
0x180007f34  movups  [rbp+160h+Buf1], xmm0
0x180007f38  test    r8d, 0FFFFFFC0h
0x180007f3f  jz      short loc_180007F4B
0x180007f41  mov     eax, 0C00000F1h
0x180007f46  jmp     loc_18000811C
0x180007f4b  test    sil, 2
0x180007f4f  jnz     short loc_180007F67
0x180007f51  mov     eax, gs:179Ch
0x180007f59  test    eax, eax
0x180007f5b  jnz     short loc_180007F67
0x180007f5d  mov     eax, 0C000005Ch
0x180007f62  jmp     loc_18000811C
0x180007f67  lea     rax, [rsp+260h+Handle]
0x180007f6c  xor     r9d, r9d; EffectiveOnly
0x180007f6f  mov     [rsp+260h+NewTokenHandle], rax; NewTokenHandle
0x180007f74  xor     r8d, r8d; ObjectAttributes
0x180007f77  xor     edx, edx; DesiredAccess
0x180007f79  mov     [rsp+260h+TokenType], 1; TokenType
0x180007f81  mov     rcx, r10; ExistingTokenHandle
0x180007f84  call    cs:__imp_NtDuplicateToken
0x180007f8a  mov     ebx, eax
0x180007f8c  test    eax, eax
0x180007f8e  js      loc_18000811A
0x180007f94  xor     r14d, r14d
0x180007f97  mov     [rsp+260h+var_1F0], 82h
0x180007fa0  mov     [rsp+260h+var_228], r14
0x180007fa5  lea     r9, [rbp+160h+var_1CE]
0x180007fa9  lea     r8, [rsp+260h+var_1E8]
0x180007fae  mov     [rsp+260h+var_1E8], 100h
0x180007fb7  lea     rdx, [rbp+160h+var_140]
0x180007fbb  mov     rcx, r12
0x180007fbe  lea     eax, [r14+21h]
0x180007fc2  mov     [rbp+160h+var_1D0], ax
0x180007fc6  lea     rax, [rsp+260h+var_1F8]
0x180007fcb  mov     [rsp+260h+var_230], rax
0x180007fd0  lea     rax, [rbp+160h+Buf1]
0x180007fd4  mov     [rsp+260h+NewTokenHandle], rax
0x180007fd9  lea     rax, [rsp+260h+var_1F0]
0x180007fde  mov     qword ptr [rsp+260h+TokenType], rax
0x180007fe3  call    cs:__imp_RtlQueryPackageClaims
0x180007fe9  mov     ebx, eax
0x180007feb  test    sil, 1
0x180007fef  jnz     short loc_180007FF6
0x180007ff1  mov     r14d, dword ptr [rsp+260h+var_1F8]
0x180007ff6  test    eax, eax
0x180007ff8  jns     short loc_18000800C
0x180007ffa  cmp     eax, 0C0000225h
0x180007fff  jnz     loc_18000810A
0x180008005  xor     ebx, ebx
0x180008007  jmp     loc_1800080F8
0x18000800c  mov     r8d, 10h; Size
0x180008012  lea     rdx, NullGuid; Buf2
0x180008019  lea     rcx, [rbp+160h+Buf1]; Buf1
0x18000801d  call    memcmp_0
0x180008022  mov     ecx, esi
0x180008024  and     ecx, 4
0x180008027  test    eax, eax
0x180008029  jz      short loc_18000803A
0x18000802b  test    ecx, ecx
0x18000802d  jz      short loc_18000803A
0x18000802f  bts     r14, 1Eh
0x180008034  lea     r15, [rbp+160h+Buf1]
0x180008038  jmp     short loc_18000803D
0x18000803a  xor     r15d, r15d
0x18000803d  mov     rdi, r14
0x180008040  or      rdi, 40h
0x180008044  test    sil, 8
0x180008048  cmovz   rdi, r14
0x18000804c  test    sil, 20h
0x180008050  jz      short loc_180008059
0x180008052  bts     rdi, 8
0x180008057  jmp     short loc_180008064
0x180008059  test    sil, 10h
0x18000805d  jz      short loc_180008064
0x18000805f  bts     rdi, 7
0x180008064  test    ecx, ecx
0x180008066  jz      short loc_18000809D
0x180008068  lea     rdx, [rsp+260h+var_210]
0x18000806d  mov     rcx, r12
0x180008070  call    PsmQueryBackgroundActivationType
0x180008075  mov     ebx, eax
0x180008077  test    eax, eax
0x180008079  js      loc_18000810A
0x18000807f  lea     rdx, [rsp+260h+var_200]
0x180008084  mov     rcx, r12
0x180008087  call    PsmpGetHostIdFromProcessToken
0x18000808c  mov     ebx, eax
0x18000808e  test    eax, eax
0x180008090  jns     short loc_1800080A6
0x180008092  cmp     eax, 0C0000225h
0x180008097  jnz     short loc_18000810A
0x180008099  xor     ecx, ecx
0x18000809b  jmp     short loc_1800080AB
0x18000809d  mov     [rsp+260h+var_200], 0FFFFFFFFFFFFFFFFh
0x1800080a6  lea     rcx, [rsp+260h+var_200]
0x1800080ab  movzx   eax, byte ptr [rsp+260h+var_1F8+4]
0x1800080b0  lea     r9, [rbp+160h+var_140]
0x1800080b4  mov     r8d, [rsp+260h+var_210]
0x1800080b9  bts     edi, 1Fh
0x1800080bd  mov     [rsp+260h+var_218], 0
0x1800080c6  mov     edx, edi
0x1800080c8  mov     [rsp+260h+var_220], 0
0x1800080d1  mov     [rsp+260h+var_228], rcx
0x1800080d6  mov     rcx, [rsp+260h+Handle]
0x1800080db  mov     [rsp+260h+var_230], r15
0x1800080e0  mov     dword ptr [rsp+260h+NewTokenHandle], eax
0x1800080e4  lea     rax, [rbp+160h+var_1D0]
0x1800080e8  mov     qword ptr [rsp+260h+TokenType], rax
0x1800080ed  call    PsmpAdjustActivationToken
0x1800080f2  mov     ebx, eax
0x1800080f4  test    eax, eax
0x1800080f6  js      short loc_18000810A
0x1800080f8  mov     rax, [rsp+260h+Handle]
0x1800080fd  xor     ecx, ecx
0x1800080ff  mov     [r13+0], rax
0x180008103  mov     [rsp+260h+Handle], rcx
0x180008108  jmp     short loc_18000810F
0x18000810a  mov     rcx, [rsp+260h+Handle]; Handle
0x18000810f  test    rcx, rcx
0x180008112  jz      short loc_18000811A
0x180008114  call    cs:__imp_NtClose
0x18000811a  mov     eax, ebx
0x18000811c  mov     rcx, [rbp+160h+var_40]
0x180008123  xor     rcx, rsp; StackCookie
0x180008126  call    __security_check_cookie
0x18000812b  mov     rbx, [rsp+260h+arg_10]
0x180008133  add     rsp, 230h
0x18000813a  pop     r15
0x18000813c  pop     r14
0x18000813e  pop     r13
0x180008140  pop     r12
0x180008142  pop     rdi
0x180008143  pop     rsi
0x180008144  pop     rbp
0x180008145  retn
```
