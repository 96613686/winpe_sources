# IASLogonMSCHAPv2

- ea: `0x180028ce0`
- end: `0x180029020`
- name: `IASLogonMSCHAPv2`
- size: `832`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000ec4c`

## callees

- `0x180027aa0`
- `0x180027ae8`
- `0x180027b30`
- `0x180028b14`
- `0x180028ce0`
- `0x18002b472`
- `0x18002b4a0`

## string_xrefs

- `0x180028faa`: `On the client side, this is the receive key; on the server side, it is the send key.`
- `0x180028f3c`: `On the client side, this is the send key; on the server side, it is the receive key.`

## pseudocode

```c
__int64 __fastcall IASLogonMSCHAPv2(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  int v13; // esi
  __int64 v14; // r8
  __int64 result; // rax
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v22; // [rsp+48h] [rbp-99h]
  __int64 v23; // [rsp+50h] [rbp-91h]
  wchar_t Destination[8]; // [rsp+60h] [rbp-81h] BYREF
  __int128 v25; // [rsp+70h] [rbp-71h]
  _BYTE v26[24]; // [rsp+80h] [rbp-61h] BYREF
  __int64 v27; // [rsp+98h] [rbp-49h]
  __int128 v28; // [rsp+A0h] [rbp-41h] BYREF
  int v29; // [rsp+B0h] [rbp-31h]
  int v30[2]; // [rsp+B8h] [rbp-29h] BYREF
  _BYTE v31[24]; // [rsp+C0h] [rbp-21h] BYREF

  v23 = a8;
  v22 = a9;
  phHash = 0;
  memset_0(Destination, 0, 0x40u);
  v13 = 5136;
  if ( isNTLMv2CompatibilityEnabled )
    v13 = 70672;
  CngRsa32Compat_SHAInit(&phHash);
  CngRsa32Compat_SHAUpdate(&phHash, a7, 16);
  CngRsa32Compat_SHAUpdate(&phHash, a4, a5);
  v14 = -1;
  do
    ++v14;
  while ( *(_BYTE *)(a3 + v14) );
  CngRsa32Compat_SHAUpdate(&phHash, a3, v14);
  CngRsa32Compat_SHAFinal(&phHash, &v28);
  *(_QWORD *)v30 = v28;
  result = IASLogonMSCHAPWithParameterControl(a1, a2, (int)v30, a6, 0, v13, Destination, v22);
  if ( !(_DWORD)result )
  {
    CngRsa32Compat_SHAInit(&phHash);
    CngRsa32Compat_SHAUpdate(&phHash, v26, 16);
    CngRsa32Compat_SHAUpdate(&phHash, a6, 24);
    CngRsa32Compat_SHAUpdate(&phHash, AuthMagic1, 39);
    CngRsa32Compat_SHAFinal(&phHash, &v28);
    CngRsa32Compat_SHAInit(&phHash);
    CngRsa32Compat_SHAUpdate(&phHash, &v28, 20);
    CngRsa32Compat_SHAUpdate(&phHash, v30, 8);
    CngRsa32Compat_SHAUpdate(&phHash, AuthMagic2, 41);
    CngRsa32Compat_SHAFinal(&phHash, &v28);
    v16 = v23;
    v17 = v29;
    *(_OWORD *)(v23 + 32) = v28;
    *(_DWORD *)(v16 + 48) = v17;
    CngRsa32Compat_SHAInit(&phHash);
    CngRsa32Compat_SHAUpdate(&phHash, v26, 16);
    CngRsa32Compat_SHAUpdate(&phHash, a6, 24);
    CngRsa32Compat_SHAUpdate(&phHash, KeyMagic1, 27);
    CngRsa32Compat_SHAFinal(&phHash, v31);
    CngRsa32Compat_SHAInit(&phHash);
    CngRsa32Compat_SHAUpdate(&phHash, v31, 16);
    CngRsa32Compat_SHAUpdate(&phHash, SHSpad1, 40);
    CngRsa32Compat_SHAUpdate(&phHash, KeyMagic2, 84);
    CngRsa32Compat_SHAUpdate(&phHash, SHSpad2, 40);
    CngRsa32Compat_SHAFinal(&phHash, &v28);
    *(_OWORD *)(v16 + 52) = v28;
    CngRsa32Compat_SHAInit(&phHash);
    CngRsa32Compat_SHAUpdate(&phHash, v31, 16);
    CngRsa32Compat_SHAUpdate(&phHash, SHSpad1, 40);
    CngRsa32Compat_SHAUpdate(&phHash, KeyMagic3, 84);
    CngRsa32Compat_SHAUpdate(&phHash, SHSpad2, 40);
    CngRsa32Compat_SHAFinal(&phHash, &v28);
    v18 = v27;
    v19 = *(_OWORD *)Destination;
    *(_OWORD *)(v16 + 68) = v28;
    *(_QWORD *)(v16 + 88) = v18;
    result = 0;
    v20 = v25;
    *(_OWORD *)v16 = v19;
    *(_OWORD *)(v16 + 16) = v20;
  }
  return result;
}

```

## disassembly

```asm
0x180028ce0  push    rbp
0x180028ce2  push    rbx
0x180028ce3  push    rsi
0x180028ce4  push    rdi
0x180028ce5  push    r12
0x180028ce7  push    r13
0x180028ce9  push    r14
0x180028ceb  push    r15
0x180028ced  lea     rbp, [rsp-7]
0x180028cf2  sub     rsp, 0E8h
0x180028cf9  mov     rax, cs:__security_cookie
0x180028d00  xor     rax, rsp
0x180028d03  mov     [rbp+3Fh+var_48], rax
0x180028d07  mov     rax, [rbp+3Fh+arg_38]
0x180028d0e  mov     r13, rdx
0x180028d11  mov     r15, [rbp+3Fh+arg_28]
0x180028d15  xor     edx, edx; Val
0x180028d17  mov     rbx, [rbp+3Fh+arg_30]
0x180028d1b  mov     r14, r8
0x180028d1e  mov     [rsp+120h+var_D0], rax
0x180028d23  mov     r12, rcx
0x180028d26  mov     rax, [rbp+3Fh+arg_40]
0x180028d2d  lea     rcx, [rsp+120h+var_C0]; void *
0x180028d32  lea     r8d, [rdx+40h]; Size
0x180028d36  mov     [rsp+120h+var_D8], rax
0x180028d3b  mov     rdi, r9
0x180028d3e  mov     [rsp+120h+phHash], 0
0x180028d47  call    memset_0
0x180028d4c  cmp     cs:isNTLMv2CompatibilityEnabled, 0
0x180028d53  lea     rcx, [rsp+120h+phHash]; phHash
0x180028d58  mov     eax, 11410h
0x180028d5d  mov     esi, 1410h
0x180028d62  cmovnz  esi, eax
0x180028d65  call    CngRsa32Compat_SHAInit
0x180028d6a  mov     r8d, 10h
0x180028d70  lea     rcx, [rsp+120h+phHash]
0x180028d75  mov     rdx, rbx
0x180028d78  call    CngRsa32Compat_SHAUpdate
0x180028d7d  mov     r8d, [rbp+3Fh+arg_20]
0x180028d81  lea     rcx, [rsp+120h+phHash]
0x180028d86  mov     rdx, rdi
0x180028d89  call    CngRsa32Compat_SHAUpdate
0x180028d8e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028d92  inc     r8
0x180028d95  cmp     byte ptr [r14+r8], 0
0x180028d9a  jnz     short loc_180028D92
0x180028d9c  mov     rdx, r14
0x180028d9f  lea     rcx, [rsp+120h+phHash]
0x180028da4  call    CngRsa32Compat_SHAUpdate
0x180028da9  lea     rdx, [rbp+3Fh+var_80]
0x180028dad  lea     rcx, [rsp+120h+phHash]
0x180028db2  call    CngRsa32Compat_SHAFinal
0x180028db7  mov     rax, qword ptr [rbp+3Fh+var_80]
0x180028dbb  lea     r8, [rbp+3Fh+var_68]; int
0x180028dbf  mov     qword ptr [rbp+3Fh+var_68], rax
0x180028dc3  mov     r9, r15; int
0x180028dc6  mov     rax, [rsp+120h+var_D8]
0x180028dcb  mov     rdx, r13; int
0x180028dce  mov     [rsp+120h+var_E8], rax; __int64
0x180028dd3  mov     rcx, r12; int
0x180028dd6  lea     rax, [rsp+120h+var_C0]
0x180028ddb  mov     [rsp+120h+Destination], rax; Destination
0x180028de0  mov     [rsp+120h+var_F8], esi; int
0x180028de4  mov     [rsp+120h+var_100], 0; __int64
0x180028ded  call    IASLogonMSCHAPWithParameterControl
0x180028df2  test    eax, eax
0x180028df4  jnz     loc_180029000
0x180028dfa  lea     rcx, [rsp+120h+phHash]; phHash
0x180028dff  call    CngRsa32Compat_SHAInit
0x180028e04  mov     r14d, 10h
0x180028e0a  lea     rdx, [rbp+3Fh+var_A0]
0x180028e0e  mov     r8d, r14d
0x180028e11  lea     rcx, [rsp+120h+phHash]
0x180028e16  call    CngRsa32Compat_SHAUpdate
0x180028e1b  lea     edi, [r14+8]
0x180028e1f  mov     rdx, r15
0x180028e22  mov     r8d, edi
0x180028e25  lea     rcx, [rsp+120h+phHash]
0x180028e2a  call    CngRsa32Compat_SHAUpdate
0x180028e2f  lea     r8d, [r14+17h]
0x180028e33  lea     rdx, AuthMagic1; "Magic server to client signing constant"
0x180028e3a  lea     rcx, [rsp+120h+phHash]
0x180028e3f  call    CngRsa32Compat_SHAUpdate
0x180028e44  lea     rdx, [rbp+3Fh+var_80]
0x180028e48  lea     rcx, [rsp+120h+phHash]
0x180028e4d  call    CngRsa32Compat_SHAFinal
0x180028e52  lea     rcx, [rsp+120h+phHash]; phHash
0x180028e57  call    CngRsa32Compat_SHAInit
0x180028e5c  lea     r8d, [r14+4]
0x180028e60  lea     rdx, [rbp+3Fh+var_80]
0x180028e64  lea     rcx, [rsp+120h+phHash]
0x180028e69  call    CngRsa32Compat_SHAUpdate
0x180028e6e  lea     r8d, [r14-8]
0x180028e72  lea     rdx, [rbp+3Fh+var_68]
0x180028e76  lea     rcx, [rsp+120h+phHash]
0x180028e7b  call    CngRsa32Compat_SHAUpdate
0x180028e80  lea     r8d, [r14+19h]
0x180028e84  lea     rdx, AuthMagic2; "Pad to make it do more than one iterati"...
0x180028e8b  lea     rcx, [rsp+120h+phHash]
0x180028e90  call    CngRsa32Compat_SHAUpdate
0x180028e95  lea     rdx, [rbp+3Fh+var_80]
0x180028e99  lea     rcx, [rsp+120h+phHash]
0x180028e9e  call    CngRsa32Compat_SHAFinal
0x180028ea3  mov     rbx, [rsp+120h+var_D0]
0x180028ea8  lea     rcx, [rsp+120h+phHash]; phHash
0x180028ead  movups  xmm0, [rbp+3Fh+var_80]
0x180028eb1  mov     eax, [rbp+3Fh+var_70]
0x180028eb4  movups  xmmword ptr [rbx+20h], xmm0
0x180028eb8  mov     [rbx+30h], eax
0x180028ebb  call    CngRsa32Compat_SHAInit
0x180028ec0  mov     r8d, r14d
0x180028ec3  lea     rdx, [rbp+3Fh+var_A0]
0x180028ec7  lea     rcx, [rsp+120h+phHash]
0x180028ecc  call    CngRsa32Compat_SHAUpdate
0x180028ed1  mov     r8d, edi
0x180028ed4  lea     rcx, [rsp+120h+phHash]
0x180028ed9  mov     rdx, r15
0x180028edc  call    CngRsa32Compat_SHAUpdate
0x180028ee1  lea     r8d, [r14+0Bh]
0x180028ee5  lea     rdx, KeyMagic1; "This is the MPPE Master Key"
0x180028eec  lea     rcx, [rsp+120h+phHash]
0x180028ef1  call    CngRsa32Compat_SHAUpdate
0x180028ef6  lea     rdx, [rbp+3Fh+var_60]
0x180028efa  lea     rcx, [rsp+120h+phHash]
0x180028eff  call    CngRsa32Compat_SHAFinal
0x180028f04  lea     rcx, [rsp+120h+phHash]; phHash
0x180028f09  call    CngRsa32Compat_SHAInit
0x180028f0e  mov     r8d, r14d
0x180028f11  lea     rdx, [rbp+3Fh+var_60]
0x180028f15  lea     rcx, [rsp+120h+phHash]
0x180028f1a  call    CngRsa32Compat_SHAUpdate
0x180028f1f  lea     esi, [rdi+10h]
0x180028f22  mov     r8d, esi
0x180028f25  lea     rdx, SHSpad1
0x180028f2c  lea     rcx, [rsp+120h+phHash]
0x180028f31  call    CngRsa32Compat_SHAUpdate
0x180028f36  lea     edi, [rsi+2Ch]
0x180028f39  mov     r8d, edi
0x180028f3c  lea     rdx, KeyMagic2; "On the client side, this is the send ke"...
0x180028f43  lea     rcx, [rsp+120h+phHash]
0x180028f48  call    CngRsa32Compat_SHAUpdate
0x180028f4d  mov     r8d, esi
0x180028f50  lea     rdx, SHSpad2
0x180028f57  lea     rcx, [rsp+120h+phHash]
0x180028f5c  call    CngRsa32Compat_SHAUpdate
0x180028f61  lea     rdx, [rbp+3Fh+var_80]
0x180028f65  lea     rcx, [rsp+120h+phHash]
0x180028f6a  call    CngRsa32Compat_SHAFinal
0x180028f6f  movups  xmm0, [rbp+3Fh+var_80]
0x180028f73  lea     rcx, [rsp+120h+phHash]; phHash
0x180028f78  movdqu  xmmword ptr [rbx+34h], xmm0
0x180028f7d  call    CngRsa32Compat_SHAInit
0x180028f82  mov     r8d, r14d
0x180028f85  lea     rdx, [rbp+3Fh+var_60]
0x180028f89  lea     rcx, [rsp+120h+phHash]
0x180028f8e  call    CngRsa32Compat_SHAUpdate
0x180028f93  mov     r8d, esi
0x180028f96  lea     rdx, SHSpad1
0x180028f9d  lea     rcx, [rsp+120h+phHash]
0x180028fa2  call    CngRsa32Compat_SHAUpdate
0x180028fa7  mov     r8d, edi
0x180028faa  lea     rdx, KeyMagic3; "On the client side, this is the receive"...
0x180028fb1  lea     rcx, [rsp+120h+phHash]
0x180028fb6  call    CngRsa32Compat_SHAUpdate
0x180028fbb  mov     r8d, esi
0x180028fbe  lea     rdx, SHSpad2
0x180028fc5  lea     rcx, [rsp+120h+phHash]
0x180028fca  call    CngRsa32Compat_SHAUpdate
0x180028fcf  lea     rdx, [rbp+3Fh+var_80]
0x180028fd3  lea     rcx, [rsp+120h+phHash]
0x180028fd8  call    CngRsa32Compat_SHAFinal
0x180028fdd  movups  xmm0, [rbp+3Fh+var_80]
0x180028fe1  mov     rax, [rbp+3Fh+var_88]
0x180028fe5  movaps  xmm1, xmmword ptr [rsp+120h+var_C0]
0x180028fea  movdqu  xmmword ptr [rbx+44h], xmm0
0x180028fef  mov     [rbx+58h], rax
0x180028ff3  xor     eax, eax
0x180028ff5  movaps  xmm0, [rbp+3Fh+var_B0]
0x180028ff9  movups  xmmword ptr [rbx], xmm1
0x180028ffc  movups  xmmword ptr [rbx+10h], xmm0
0x180029000  mov     rcx, [rbp+3Fh+var_48]
0x180029004  xor     rcx, rsp; StackCookie
0x180029007  call    __security_check_cookie
0x18002900c  add     rsp, 0E8h
0x180029013  pop     r15
0x180029015  pop     r14
0x180029017  pop     r13
0x180029019  pop     r12
0x18002901b  pop     rdi
0x18002901c  pop     rsi
0x18002901d  pop     rbx
0x18002901e  pop     rbp
0x18002901f  retn
```
