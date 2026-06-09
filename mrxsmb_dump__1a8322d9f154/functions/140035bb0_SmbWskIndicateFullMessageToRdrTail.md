# SmbWskIndicateFullMessageToRdrTail

- ea: `0x140035bb0`
- end: `0x140035f7f`
- name: `SmbWskIndicateFullMessageToRdrTail`
- size: `975`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400137f0`

## callees

- `0x14001a008`
- `0x14001a2a0`
- `0x14001a354`
- `0x140035bb0`
- `0x140059dc0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140035f56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035f56`
- `ntoskrnl!IoGetActivityIdThread` at `0x140035cd4`
- `ntoskrnl!IoGetActivityIdThread` at `0x140035cd4`
- `ntoskrnl!EtwProviderEnabled` at `0x140035c6e`
- `ntoskrnl!EtwProviderEnabled` at `0x140035ca0`
- `ntoskrnl!EtwProviderEnabled` at `0x140035c6e`
- `ntoskrnl!EtwProviderEnabled` at `0x140035ca0`
- `NETIO!RtlCopyBufferToMdl` at `0x140035ed7`
- `NETIO!RtlCopyBufferToMdl` at `0x140035ed7`

## pseudocode

```c
__int64 __fastcall SmbWskIndicateFullMessageToRdrTail(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // r13
  _DWORD *v5; // r14
  char v6; // r12
  __int64 v7; // rbx
  bool v8; // zf
  int v9; // esi
  unsigned int v10; // r15d
  unsigned int v11; // edi
  unsigned int v12; // ebx
  __int128 *ActivityIdThread; // rax
  __int64 v14; // rdx
  _DWORD *v15; // r12
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int64 v18; // rdx
  int v19; // ecx
  unsigned int v20; // r14d
  __int64 v21; // r8
  __int64 v22; // rcx
  ULONG v23; // edx
  char v25; // [rsp+68h] [rbp-A0h]
  unsigned int v26; // [rsp+6Ch] [rbp-9Ch] BYREF
  __int64 v27; // [rsp+70h] [rbp-98h] BYREF
  __int64 v28; // [rsp+78h] [rbp-90h] BYREF
  __int128 *v29; // [rsp+80h] [rbp-88h] BYREF
  __int64 v30; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v31; // [rsp+90h] [rbp-78h]
  __int128 *v32; // [rsp+98h] [rbp-70h]
  _DWORD *v33; // [rsp+A0h] [rbp-68h]
  _DWORD *v34; // [rsp+A8h] [rbp-60h]
  __int128 v35; // [rsp+B0h] [rbp-58h] BYREF
  _DWORD v36[2]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v37[28]; // [rsp+C8h] [rbp-40h]
  unsigned int v38; // [rsp+E4h] [rbp-24h]

  v4 = a2;
  v5 = (_DWORD *)a4;
  v6 = *(_BYTE *)(a4 + 52);
  v7 = a1;
  v33 = a2;
  v8 = (*(_DWORD *)a4 & 0x10000000) == 0;
  v9 = 0;
  v10 = a3;
  v25 = v6;
  v34 = (_DWORD *)a4;
  LODWORD(v28) = a3;
  v30 = a1;
  LODWORD(v27) = 0;
  if ( !v8 )
  {
    v9 = RxCeVerifyPostTransformData(a1, a2, a3, *(_QWORD *)(a4 + 8));
    if ( v9 < 0 )
      goto LABEL_31;
  }
  v11 = 0;
  v35 = 0;
  v31 = 0;
  if ( (byte_1400712A4 & 0x20) == 0 )
    goto LABEL_23;
  LOWORD(v26) = *(_WORD *)(v7 + 320);
  if ( !EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x200000000uLL) )
    goto LABEL_23;
  v32 = (__int128 *)(v7 + 428);
  v12 = v10;
  if ( !EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x800000000000uLL) && v10 >= 0x40 && *v4 == 1112364030 )
  {
    v12 = v4[5] + 576;
    if ( v12 > v10 )
      v12 = v10;
  }
  ActivityIdThread = (__int128 *)IoGetActivityIdThread();
  v29 = ActivityIdThread;
  if ( !ActivityIdThread )
  {
    v35 = (unsigned __int64)_InterlockedIncrement64(&Correlation);
    ActivityIdThread = &v35;
    v29 = &v35;
  }
  if ( v12 < 0xF000 )
  {
    Template_qqbqb_ex(REMOTEFS_SMB_Context, v14, 0x200000000LL, ActivityIdThread, (unsigned __int16)v26);
    goto LABEL_22;
  }
  v36[0] = (unsigned __int16)v26;
  v15 = v4;
  v38 = v12;
  v16 = *v32;
  v17 = *(__int128 *)((char *)v32 + 12);
  v36[1] = 28;
  *(_OWORD *)v37 = v16;
  *(_OWORD *)&v37[12] = v17;
  v19 = Template_qqbjqb_ex(REMOTEFS_SMB_Context, v32, 0x240000000LL, ActivityIdThread, 40, v36);
  while ( v19 >= 0 )
  {
    if ( v12 < 0xF000 )
    {
      v20 = v12;
LABEL_19:
      v21 = 0x280000000LL;
      goto LABEL_20;
    }
    v21 = 0x200000000LL;
    v20 = 61440;
    if ( v12 == 61440 )
      goto LABEL_19;
LABEL_20:
    v19 = Template_qqbjqb_ex(REMOTEFS_SMB_Context, v18, v21, v29, v20, v15);
    v15 = (_DWORD *)((char *)v15 + v20);
    v12 -= v20;
    if ( !v12 )
      break;
  }
  v11 = v31;
  v10 = v28;
  v4 = v33;
  v5 = v34;
LABEL_22:
  v6 = v25;
  v7 = v30;
LABEL_23:
  if ( v10 )
  {
    do
    {
      *v5 |= 0x400u;
      v22 = *(_QWORD *)(v7 + 392);
      v30 = 0;
      v26 = 0;
      v29 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, _QWORD, _QWORD, __int64 *, char *, __int64 *, __int128 **, unsigned int *))(v22 + 16))(
             v7,
             v5,
             v10 - v11,
             v10 - v11,
             v10 - v5[12],
             &v27,
             (char *)v4 + v11,
             &v30,
             &v29,
             &v26);
      if ( ((v9 + 0x80000000) & 0x80000000) == 0 && v9 != -1073741802 )
        break;
      v11 += v27;
      if ( v9 == -1073741802 && v11 < v10 )
      {
        v28 = 0;
        RtlCopyBufferToMdl((char *)v4 + v11, v30, 0, v26, &v28);
        (*(void (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)(v7 + 392) + 24LL))(
          v7,
          v29,
          (unsigned int)v28,
          0);
        v11 += v28;
      }
      v9 = 0;
    }
    while ( v11 < v10 );
    v6 = v25;
  }
LABEL_31:
  if ( (v6 & 2) != 0 )
  {
    v23 = 1834184772;
    if ( (*v5 & 0x20000000) == 0 )
      v23 = 1834181966;
    ExFreePoolWithTag(v4, v23);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140035bb0  mov     r11, rsp
0x140035bb3  push    rbp
0x140035bb4  push    rsi
0x140035bb5  push    r13
0x140035bb7  push    r14
0x140035bb9  lea     rbp, [r11-38h]
0x140035bbd  sub     rsp, 118h
0x140035bc4  mov     rax, cs:__security_cookie
0x140035bcb  xor     rax, rsp
0x140035bce  mov     [rbp+30h+var_50], rax
0x140035bd2  mov     [r11-28h], rbx
0x140035bd6  mov     r13, rdx
0x140035bd9  mov     [r11-38h], r12
0x140035bdd  mov     r14, r9
0x140035be0  movzx   r12d, byte ptr [r9+34h]
0x140035be5  mov     rbx, rcx
0x140035be8  mov     [rbp+30h+var_98], rdx
0x140035bec  xor     edx, edx
0x140035bee  test    dword ptr [r9], 10000000h
0x140035bf5  mov     esi, edx
0x140035bf7  mov     [r11-40h], r15
0x140035bfb  mov     r15d, r8d
0x140035bfe  mov     byte ptr [rsp+130h+var_D0], r12b
0x140035c03  mov     [rbp+30h+var_90], r9
0x140035c07  mov     dword ptr [rsp+130h+var_C0], r8d
0x140035c0c  mov     [rbp+30h+var_B0], rcx
0x140035c10  mov     dword ptr [rsp+130h+var_C8], edx
0x140035c14  jz      short loc_140035C2E
0x140035c16  mov     r9, [r9+8]
0x140035c1a  mov     rdx, r13
0x140035c1d  call    RxCeVerifyPostTransformData
0x140035c22  mov     esi, eax
0x140035c24  test    eax, eax
0x140035c26  js      loc_140035F22
0x140035c2c  xor     edx, edx
0x140035c2e  test    cs:byte_1400712A4, 20h
0x140035c35  xorps   xmm0, xmm0
0x140035c38  mov     [rsp+130h+var_28], rdi
0x140035c40  mov     edi, edx
0x140035c42  movups  [rbp+30h+var_88], xmm0
0x140035c46  mov     [rbp+30h+var_A8], edx
0x140035c49  jz      loc_140035E12
0x140035c4f  movzx   eax, word ptr [rbx+140h]
0x140035c56  xor     edx, edx; Level
0x140035c58  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x140035c5f  mov     r8, 200000000h; Keyword
0x140035c69  mov     word ptr [rsp+130h+var_CC], ax
0x140035c6e  call    cs:__imp_EtwProviderEnabled
0x140035c75  nop     dword ptr [rax+rax+00h]
0x140035c7a  test    al, al
0x140035c7c  jz      loc_140035E10
0x140035c82  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x140035c89  lea     r12, [rbx+1ACh]
0x140035c90  xor     edx, edx; Level
0x140035c92  mov     [rbp+30h+var_A0], r12
0x140035c96  mov     r8, 800000000000h; Keyword
0x140035ca0  call    cs:__imp_EtwProviderEnabled
0x140035ca7  nop     dword ptr [rax+rax+00h]
0x140035cac  mov     ebx, r15d
0x140035caf  test    al, al
0x140035cb1  jnz     short loc_140035CD4
0x140035cb3  cmp     r15d, 40h ; '@'
0x140035cb7  jb      short loc_140035CD4
0x140035cb9  cmp     dword ptr [r13+0], 424D53FEh
0x140035cc1  jnz     short loc_140035CD4
0x140035cc3  mov     ebx, [r13+14h]
0x140035cc7  add     ebx, 240h
0x140035ccd  cmp     ebx, r15d
0x140035cd0  cmova   ebx, r15d
0x140035cd4  call    cs:__imp_IoGetActivityIdThread
0x140035cdb  nop     dword ptr [rax+rax+00h]
0x140035ce0  mov     [rsp+130h+var_B8], rax
0x140035ce5  test    rax, rax
0x140035ce8  jnz     short loc_140035D0F
0x140035cea  xorps   xmm0, xmm0
0x140035ced  mov     eax, 1
0x140035cf2  movups  [rbp+30h+var_88], xmm0
0x140035cf6  lock xadd cs:Correlation, rax
0x140035cff  inc     rax
0x140035d02  mov     qword ptr [rbp+30h+var_88], rax
0x140035d06  lea     rax, [rbp+30h+var_88]
0x140035d0a  mov     [rsp+130h+var_B8], rax
0x140035d0f  movzx   ecx, word ptr [rsp+130h+var_CC]
0x140035d14  mov     r9, rax
0x140035d17  cmp     ebx, 0F000h
0x140035d1d  jnb     short loc_140035D4C
0x140035d1f  mov     [rsp+130h+var_F0], r13
0x140035d24  mov     r8, 200000000h
0x140035d2e  mov     dword ptr [rsp+130h+var_F8], ebx
0x140035d32  mov     [rsp+130h+var_100], r12
0x140035d37  mov     dword ptr [rsp+130h+var_110], ecx
0x140035d3b  mov     rcx, cs:REMOTEFS_SMB_Context
0x140035d42  call    Template_qqbqb_ex
0x140035d47  jmp     loc_140035E06
0x140035d4c  mov     rdx, [rbp+30h+var_A0]
0x140035d50  mov     r8, 240000000h
0x140035d5a  mov     [rbp+30h+var_78], ecx
0x140035d5d  mov     r12, r13
0x140035d60  lea     rcx, [rbp+30h+var_78]
0x140035d64  mov     [rbp+30h+var_54], ebx
0x140035d67  mov     [rsp+130h+var_108], rcx
0x140035d6c  movups  xmm0, xmmword ptr [rdx]
0x140035d6f  mov     rcx, cs:REMOTEFS_SMB_Context
0x140035d76  movups  xmm1, xmmword ptr [rdx+0Ch]
0x140035d7a  mov     [rbp+30h+var_74], 1Ch
0x140035d81  movups  xmmword ptr [rbp+30h+var_70], xmm0
0x140035d85  mov     dword ptr [rsp+130h+var_110], 28h ; '('
0x140035d8d  movups  xmmword ptr [rbp+30h+var_70+0Ch], xmm1
0x140035d91  call    Template_qqbjqb_ex
0x140035d96  mov     rdi, [rsp+130h+var_B8]
0x140035d9b  mov     ecx, eax
0x140035d9d  mov     r15, 200000000h
0x140035da7  mov     r13, 280000000h
0x140035db1  test    ecx, ecx
0x140035db3  js      short loc_140035DF6
0x140035db5  cmp     ebx, 0F000h
0x140035dbb  jnb     short loc_140035DC2
0x140035dbd  mov     r14d, ebx
0x140035dc0  jmp     short loc_140035DCD
0x140035dc2  mov     r8, r15
0x140035dc5  mov     r14d, 0F000h
0x140035dcb  jnz     short loc_140035DD0
0x140035dcd  mov     r8, r13
0x140035dd0  mov     rcx, cs:REMOTEFS_SMB_Context
0x140035dd7  mov     r9, rdi
0x140035dda  mov     [rsp+130h+var_108], r12
0x140035ddf  mov     dword ptr [rsp+130h+var_110], r14d
0x140035de4  call    Template_qqbjqb_ex
0x140035de9  mov     ecx, eax
0x140035deb  mov     eax, r14d
0x140035dee  add     r12, rax
0x140035df1  sub     ebx, r14d
0x140035df4  jnz     short loc_140035DB1
0x140035df6  mov     edi, [rbp+30h+var_A8]
0x140035df9  mov     r15d, dword ptr [rsp+130h+var_C0]
0x140035dfe  mov     r13, [rbp+30h+var_98]
0x140035e02  mov     r14, [rbp+30h+var_90]
0x140035e06  movzx   r12d, byte ptr [rsp+130h+var_D0]
0x140035e0c  mov     rbx, [rbp+30h+var_B0]
0x140035e10  xor     edx, edx
0x140035e12  test    r15d, r15d
0x140035e15  jz      loc_140035F1A
0x140035e1b  mov     r12d, 80000000h
0x140035e21  or      dword ptr [r14], 400h
0x140035e28  mov     r8d, r15d
0x140035e2b  mov     rcx, [rbx+188h]
0x140035e32  sub     r8d, edi
0x140035e35  mov     [rbp+30h+var_B0], rdx
0x140035e39  mov     [rsp+130h+var_CC], edx
0x140035e3d  mov     [rsp+130h+var_B8], rdx
0x140035e42  mov     edx, r15d
0x140035e45  mov     rax, [rcx+10h]
0x140035e49  lea     rcx, [rsp+130h+var_CC]
0x140035e4e  sub     edx, [r14+30h]
0x140035e52  mov     [rsp+48h], rcx
0x140035e57  lea     rcx, [rsp+130h+var_B8]
0x140035e5c  mov     [rsp+130h+var_F0], rcx
0x140035e61  lea     rcx, [rbp+30h+var_B0]
0x140035e65  mov     [rsp+130h+var_F8], rcx
0x140035e6a  lea     rcx, [rsp+130h+var_C8]
0x140035e6f  mov     r9d, edi
0x140035e72  add     r9, r13
0x140035e75  mov     [rsp+130h+var_100], r9
0x140035e7a  mov     r9d, r8d
0x140035e7d  mov     [rsp+130h+var_108], rcx
0x140035e82  mov     rcx, rbx
0x140035e85  mov     [rsp+130h+var_110], rdx
0x140035e8a  mov     rdx, r14
0x140035e8d  call    _guard_dispatch_icall
0x140035e92  mov     esi, eax
0x140035e94  add     eax, r12d
0x140035e97  test    r12d, eax
0x140035e9a  jnz     short loc_140035EA4
0x140035e9c  cmp     esi, 0C0000016h
0x140035ea2  jnz     short loc_140035F14
0x140035ea4  add     edi, dword ptr [rsp+130h+var_C8]
0x140035ea8  cmp     esi, 0C0000016h
0x140035eae  jnz     short loc_140035F07
0x140035eb0  cmp     edi, r15d
0x140035eb3  jnb     short loc_140035F07
0x140035eb5  mov     r9d, [rsp+130h+var_CC]
0x140035eba  lea     rax, [rsp+130h+var_C0]
0x140035ebf  xor     edx, edx
0x140035ec1  mov     ecx, edi
0x140035ec3  mov     [rsp+130h+var_C0], rdx
0x140035ec8  add     rcx, r13
0x140035ecb  mov     rdx, [rbp+30h+var_B0]
0x140035ecf  xor     r8d, r8d
0x140035ed2  mov     [rsp+130h+var_110], rax
0x140035ed7  call    cs:__imp_RtlCopyBufferToMdl
0x140035ede  nop     dword ptr [rax+rax+00h]
0x140035ee3  mov     rax, [rbx+188h]
0x140035eea  xor     r9d, r9d
0x140035eed  mov     r8d, dword ptr [rsp+130h+var_C0]
0x140035ef2  mov     rcx, rbx
0x140035ef5  mov     rdx, [rsp+130h+var_B8]
0x140035efa  mov     rax, [rax+18h]
0x140035efe  call    _guard_dispatch_icall
0x140035f03  add     edi, dword ptr [rsp+130h+var_C0]
0x140035f07  xor     edx, edx
0x140035f09  mov     esi, edx
0x140035f0b  cmp     edi, r15d
0x140035f0e  jb      loc_140035E21
0x140035f14  movzx   r12d, byte ptr [rsp+130h+var_D0]
0x140035f1a  mov     rdi, [rsp+130h+var_28]
0x140035f22  mov     r15, [rsp+130h+var_38]
0x140035f2a  test    r12b, 2
0x140035f2e  mov     r12, [rsp+130h+var_30]
0x140035f36  mov     rbx, [rsp+110h]
0x140035f3e  jz      short loc_140035F62
0x140035f40  test    dword ptr [r14], 20000000h
0x140035f47  mov     rcx, r13; P
0x140035f4a  mov     edx, 6D537044h
0x140035f4f  jnz     short loc_140035F56
0x140035f51  mov     edx, 6D53654Eh; Tag
0x140035f56  call    cs:__imp_ExFreePoolWithTag
0x140035f5d  nop     dword ptr [rax+rax+00h]
0x140035f62  mov     eax, esi
0x140035f64  mov     rcx, [rbp+30h+var_50]
0x140035f68  xor     rcx, rsp; StackCookie
0x140035f6b  call    __security_check_cookie
0x140035f70  add     rsp, 118h
0x140035f77  pop     r14
0x140035f79  pop     r13
0x140035f7b  pop     rsi
0x140035f7c  pop     rbp
0x140035f7d  retn
```
