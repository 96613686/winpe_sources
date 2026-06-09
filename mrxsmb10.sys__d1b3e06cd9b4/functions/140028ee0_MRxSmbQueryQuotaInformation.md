# MRxSmbQueryQuotaInformation

- ea: `0x140028ee0`
- end: `0x140029166`
- name: `MRxSmbQueryQuotaInformation`
- size: `646`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x14000a340`
- `0x14000dfa8`
- `0x140016560`
- `0x1400166c0`
- `0x1400169c0`
- `0x140028ee0`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140028f85`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140028f85`
- `ntoskrnl!ExAllocatePool2` at `0x140028ff6`
- `ntoskrnl!ExAllocatePool2` at `0x140028ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400290ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400290ec`

## pseudocode

```c
__int64 __fastcall MRxSmbQueryQuotaInformation(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rax
  __int64 v4; // rdi
  unsigned __int8 *v5; // rsi
  ULONG v6; // r14d
  __int16 v7; // ax
  __int64 v8; // rcx
  char *v9; // rdi
  unsigned int v10; // r15d
  char *Pool2; // rax
  int v12; // esi
  __int64 v13; // rax
  __int16 v15; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v16; // [rsp+84h] [rbp-7Ch] BYREF
  __int16 v17; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v18[22]; // [rsp+8Ah] [rbp-76h]
  _BYTE v19[112]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v20; // [rsp+110h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  v15 = 7;
  v20 = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_025766dafd213e249d026318cd94f89a_Traceguids);
  if ( !v1 || (v3 = *(_QWORD *)(v1 + 32)) == 0 || (v4 = *(_QWORD *)(v3 + 48)) == 0 )
  {
    v12 = -1073741811;
    goto LABEL_20;
  }
  v5 = *(unsigned __int8 **)(a1 + 520);
  if ( v5 )
    v6 = RtlLengthRequiredSid(v5[1]);
  else
    v6 = 0;
  v7 = *(_WORD *)(v4 + 8);
  v8 = *(unsigned int *)(a1 + 536);
  v9 = *(char **)(a1 + 528);
  LOWORD(v20) = v7;
  BYTE2(v20) = *(_BYTE *)(a1 + 541);
  LOBYTE(v7) = *(_BYTE *)(a1 + 540);
  *(_QWORD *)((char *)&v20 + 4) = __PAIR64__(v6, v8);
  BYTE3(v20) = v7;
  v8 += 3;
  HIDWORD(v20) = v8 & 0xFFFFFFFC;
  v10 = (v8 & 0xFFFFFFFC) + v6;
  if ( &v9[v8 & 0xFFFFFFFFFFFFFFFCuLL] != *(char **)(a1 + 520) )
  {
    Pool2 = (char *)ExAllocatePool2(258, v10, 1934454099);
    v9 = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, *(const void **)(a1 + 528), *(unsigned int *)(a1 + 536));
      memmove(&v9[HIDWORD(v20)], v5, v6);
      goto LABEL_13;
    }
    v12 = -1073741670;
LABEL_20:
    v13 = 0;
    goto LABEL_21;
  }
LABEL_13:
  *(_OWORD *)v18 = *(__int128 *)((char *)&RxDefaultTransactionOptions + 2);
  *(_QWORD *)&v18[14] = qword_14001F6B0;
  memset(v19, 0, 0x68u);
  v17 = 7;
  v12 = SmbCeTransact(
          a1,
          (int)&v17,
          (int)&v15,
          2,
          0,
          0,
          (__int64)&v20,
          16,
          (__int64)&v16,
          4,
          (__int64)v9,
          v10,
          *(_QWORD *)(a1 + 456),
          *(_DWORD *)(a1 + 472),
          (__int64)v19);
  if ( v9 && v9 != *(char **)(a1 + 528) )
    ExFreePoolWithTag(v9, 0);
  if ( v12 < 0 )
    goto LABEL_20;
  v13 = v16;
LABEL_21:
  *(_QWORD *)(a1 + 184) = v13;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_025766dafd213e249d026318cd94f89a_Traceguids);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140028ee0  push    rbp
0x140028ee2  push    rbx
0x140028ee3  push    rsi
0x140028ee4  push    rdi
0x140028ee5  push    r14
0x140028ee7  push    r15
0x140028ee9  lea     rbp, [rsp-38h]
0x140028eee  sub     rsp, 138h
0x140028ef5  mov     rax, cs:__security_cookie
0x140028efc  xor     rax, rsp
0x140028eff  mov     [rbp+60h+var_40], rax
0x140028f03  mov     rdi, [rcx+40h]
0x140028f07  mov     eax, 7
0x140028f0c  xorps   xmm0, xmm0
0x140028f0f  mov     [rbp+60h+var_E0], ax
0x140028f13  movups  [rbp+60h+var_50], xmm0
0x140028f17  mov     rbx, rcx
0x140028f1a  mov     [rbp+60h+var_DC], 0
0x140028f21  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028f28  lea     rax, WPP_GLOBAL_Control
0x140028f2f  cmp     rcx, rax
0x140028f32  jz      short loc_140028F52
0x140028f34  test    dword ptr [rcx+2Ch], 400h
0x140028f3b  jz      short loc_140028F52
0x140028f3d  mov     rcx, [rcx+18h]
0x140028f41  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x140028f48  mov     edx, 21h ; '!'
0x140028f4d  call    WPP_SF_
0x140028f52  test    rdi, rdi
0x140028f55  jz      loc_140029108
0x140028f5b  mov     rax, [rdi+20h]
0x140028f5f  test    rax, rax
0x140028f62  jz      loc_140029108
0x140028f68  mov     rdi, [rax+30h]
0x140028f6c  test    rdi, rdi
0x140028f6f  jz      loc_140029108
0x140028f75  mov     rsi, [rbx+208h]
0x140028f7c  test    rsi, rsi
0x140028f7f  jz      short loc_140028F96
0x140028f81  movzx   ecx, byte ptr [rsi+1]; SubAuthorityCount
0x140028f85  call    cs:__imp_RtlLengthRequiredSid
0x140028f8c  nop     dword ptr [rax+rax+00h]
0x140028f91  mov     r14d, eax
0x140028f94  jmp     short loc_140028F99
0x140028f96  xor     r14d, r14d
0x140028f99  movzx   eax, word ptr [rdi+8]
0x140028f9d  mov     ecx, [rbx+218h]
0x140028fa3  mov     rdi, [rbx+210h]
0x140028faa  mov     word ptr [rbp+60h+var_50], ax
0x140028fae  mov     al, [rbx+21Dh]
0x140028fb4  mov     byte ptr [rbp+60h+var_50+2], al
0x140028fb7  mov     al, [rbx+21Ch]
0x140028fbd  mov     dword ptr [rbp+60h+var_50+4], ecx
0x140028fc0  mov     byte ptr [rbp+60h+var_50+3], al
0x140028fc3  lea     eax, [rcx+3]
0x140028fc6  add     rcx, 3
0x140028fca  mov     dword ptr [rbp+60h+var_50+8], r14d
0x140028fce  and     eax, 0FFFFFFFCh
0x140028fd1  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140028fd5  add     rcx, rdi
0x140028fd8  mov     dword ptr [rbp+60h+var_50+0Ch], eax
0x140028fdb  lea     r15d, [rax+r14]
0x140028fdf  cmp     rcx, [rbx+208h]
0x140028fe6  jz      short loc_140029035
0x140028fe8  mov     edx, r15d
0x140028feb  mov     ecx, 102h
0x140028ff0  mov     r8d, 734D6D53h
0x140028ff6  call    cs:__imp_ExAllocatePool2
0x140028ffd  nop     dword ptr [rax+rax+00h]
0x140029002  mov     rdi, rax
0x140029005  test    rax, rax
0x140029008  jz      loc_140029101
0x14002900e  mov     r8d, [rbx+218h]; Size
0x140029015  mov     rcx, rax; void *
0x140029018  mov     rdx, [rbx+210h]; Src
0x14002901f  call    memmove
0x140029024  mov     ecx, dword ptr [rbp+60h+var_50+0Ch]
0x140029027  mov     rdx, rsi; Src
0x14002902a  add     rcx, rdi; void *
0x14002902d  mov     r8d, r14d; Size
0x140029030  call    memmove
0x140029035  movups  xmm0, cs:RxDefaultTransactionOptions+2
0x14002903c  lea     rcx, [rbp+60h+var_C0]; void *
0x140029040  xor     edx, edx; Val
0x140029042  movsd   xmm1, cs:qword_14001F6B0
0x14002904a  movups  xmmword ptr [rbp+60h+var_D6], xmm0
0x14002904e  lea     r8d, [rdx+68h]; Size
0x140029052  movsd   qword ptr [rbp+60h+var_D6+0Eh], xmm1
0x140029057  call    memset
0x14002905c  mov     eax, 7
0x140029061  lea     r8, [rbp+60h+var_E0]
0x140029065  mov     [rbp+60h+var_D8], ax
0x140029069  lea     rdx, [rbp+60h+var_D8]
0x14002906d  lea     rax, [rbp+60h+var_C0]
0x140029071  mov     r9d, 2
0x140029077  mov     [rsp+160h+var_F0], rax
0x14002907c  mov     rcx, rbx
0x14002907f  mov     eax, [rbx+1D8h]
0x140029085  mov     [rsp+160h+var_F8], eax
0x140029089  mov     rax, [rbx+1C8h]
0x140029090  mov     [rsp+160h+var_100], rax
0x140029095  lea     rax, [rbp+60h+var_DC]
0x140029099  mov     [rsp+160h+var_108], r15d
0x14002909e  mov     [rsp+160h+var_110], rdi
0x1400290a3  mov     [rsp+160h+var_118], 4
0x1400290ab  mov     [rsp+160h+var_120], rax
0x1400290b0  lea     rax, [rbp+60h+var_50]
0x1400290b4  mov     [rsp+160h+var_128], 10h
0x1400290bc  mov     [rsp+160h+var_130], rax
0x1400290c1  mov     [rsp+160h+var_138], 0
0x1400290c9  mov     [rsp+160h+var_140], 0
0x1400290d2  call    SmbCeTransact
0x1400290d7  mov     esi, eax
0x1400290d9  test    rdi, rdi
0x1400290dc  jz      short loc_1400290F8
0x1400290de  cmp     rdi, [rbx+210h]
0x1400290e5  jz      short loc_1400290F8
0x1400290e7  xor     edx, edx; Tag
0x1400290e9  mov     rcx, rdi; P
0x1400290ec  call    cs:__imp_ExFreePoolWithTag
0x1400290f3  nop     dword ptr [rax+rax+00h]
0x1400290f8  test    esi, esi
0x1400290fa  js      short loc_14002910D
0x1400290fc  mov     eax, [rbp+60h+var_DC]
0x1400290ff  jmp     short loc_14002910F
0x140029101  mov     esi, 0C000009Ah
0x140029106  jmp     short loc_14002910D
0x140029108  mov     esi, 0C000000Dh
0x14002910d  xor     eax, eax
0x14002910f  mov     [rbx+0B8h], rax; __annotation("TMF:",
0x140029116  lea     rax, WPP_GLOBAL_Control
0x14002911d  mov     rcx, cs:WPP_GLOBAL_Control
0x140029124  cmp     rcx, rax
0x140029127  jz      short loc_140029147
0x140029129  test    dword ptr [rcx+2Ch], 400h
0x140029130  jz      short loc_140029147
0x140029132  mov     rcx, [rcx+18h]
0x140029136  lea     r8, WPP_025766dafd213e249d026318cd94f89a_Traceguids
0x14002913d  mov     edx, 22h ; '"'
0x140029142  call    WPP_SF_
0x140029147  mov     eax, esi
0x140029149  mov     rcx, [rbp+60h+var_40]
0x14002914d  xor     rcx, rsp; StackCookie
0x140029150  call    __security_check_cookie
0x140029155  add     rsp, 138h
0x14002915c  pop     r15
0x14002915e  pop     r14
0x140029160  pop     rdi
0x140029161  pop     rsi
0x140029162  pop     rbx
0x140029163  pop     rbp
0x140029164  retn
```
