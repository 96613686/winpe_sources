# CscEnpEvictAutocacheFiles

- ea: `0x14005888c`
- end: `0x140058c2d`
- name: `CscEnpEvictAutocacheFiles`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x14008eae0`

## callees

- `0x140013eec`
- `0x140016e44`
- `0x1400180dc`
- `0x140018974`
- `0x1400247bc`
- `0x140024a0c`
- `0x140024c40`
- `0x140024d04`
- `0x140024da8`
- `0x14002cc34`
- `0x140048fb8`
- `0x14005837c`
- `0x14005888c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005891f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005891f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058bb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058bb8`

## pseudocode

```c
__int64 __fastcall CscEnpEvictAutocacheFiles(__int64 a1, char a2, __int64 **a3, __int64 *a4)
{
  __int64 **v4; // r14
  __int64 v5; // r13
  int EnumContext; // r12d
  __int64 *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rbx
  int v12; // eax
  _DWORD *v13; // rdi
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rax
  int v21; // eax
  int v22; // edx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r8
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 *v29; // rax
  int v31; // [rsp+38h] [rbp-31h]
  int v32; // [rsp+50h] [rbp-19h]
  unsigned __int64 v33; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int64 v34; // [rsp+60h] [rbp-9h] BYREF
  __int64 v35; // [rsp+68h] [rbp-1h] BYREF
  __int64 v36; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int64 v37; // [rsp+78h] [rbp+Fh]
  int v38; // [rsp+D0h] [rbp+67h] BYREF
  char v39; // [rsp+D8h] [rbp+6Fh]
  __int64 **v40; // [rsp+E0h] [rbp+77h]
  __int64 *v41; // [rsp+E8h] [rbp+7Fh]

  v41 = a4;
  v40 = a3;
  v4 = a3;
  v5 = 0;
  v35 = 0;
  EnumContext = 0;
  v34 = 0;
  v36 = 0;
  v38 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    v9 = *a3;
    if ( *a3 )
      v10 = *v9;
    else
      v10 = 0;
    LOBYTE(a4) = a2 != 0 ? 89 : 78;
    WPP_SF_cqi(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v10, a4, v9, v10);
  }
  KeEnterCriticalRegion();
  CscEnpDbInfoAcquireExclusive(a1);
  v11 = *(_QWORD *)(a1 + 8);
  if ( a2 )
  {
    if ( *v4 )
    {
      if ( (*(_DWORD *)(v11 + 144) & 0x20) != 0 )
        v12 = *(_DWORD *)(v11 + 288);
      else
        v12 = *(_DWORD *)(v11 + 284);
      *(_DWORD *)(v11 + 304) = v12;
    }
    v13 = (_DWORD *)(v11 + 304);
    goto LABEL_39;
  }
  v13 = (_DWORD *)(v11 + 304);
  *(_DWORD *)(v11 + 304) = 0;
  while ( 1 )
  {
    v14 = *(_QWORD *)(v11 + 256);
    v15 = *(_QWORD *)(v11 + 192);
    if ( v15 > v14 )
    {
      v16 = v15 - v14;
      v33 = 0;
      v17 = v16;
    }
    else
    {
      if ( *(_QWORD *)(v11 + 200) <= *(_QWORD *)(v11 + 160) )
        goto LABEL_38;
      v16 = 0;
      v17 = 0;
    }
    v18 = *(_QWORD *)(v11 + 200);
    v19 = *(_QWORD *)(v11 + 160);
    v33 = v17;
    v37 = v18;
    if ( v18 > v19 )
    {
      v20 = v18 - v19;
      if ( v16 <= v20 )
        v17 = v20;
      v33 = v17;
    }
    if ( (unsigned __int8)CscEnpQuotaIsRecovering(a1) || (v21 = *(_DWORD *)(v11 + 144), v39 = 0, (v21 & 0x20) != 0) )
      v39 = 1;
    CscPqQueryItemCount(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL), &v38);
    v32 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 320LL);
    *(_QWORD *)(v11 + 296) = MEMORY[0xFFFFF78000000014];
    CscEnpDbInfoRelease(a1);
    LOBYTE(v22) = 1;
    EnumContext = CscEnEvictAllocateEnumContext((unsigned int)&v35, v22, 0, 0, 0);
    if ( EnumContext < 0 )
    {
      v5 = v35;
      goto LABEL_45;
    }
    CscEnpNotifyQuota(a1, 1, 0, 0, 0);
    v5 = v35;
    EnumContext = CscEnEvict(a1, v35, (unsigned int)&v33, 0, (__int64)&v34, (__int64)&v36);
    if ( EnumContext < 0 )
      goto LABEL_45;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    {
      LOBYTE(v23) = v39 != 0 ? 89 : 78;
      LOBYTE(v31) = v23;
      WPP_SF_iiiicdd(WPP_GLOBAL_Control->AttachedDevice, v23, v24, v17, v34, v36, v37, v31, v38, v32);
    }
    CscEnpNotifyQuota(a1, 2, (unsigned int)&v34, (unsigned int)&v33, (__int64)&v36);
    CscEnpDbInfoAcquireExclusive(a1);
    if ( v34 < v33 )
      break;
    *v13 = 0;
  }
  if ( v39 )
  {
LABEL_38:
    v4 = v40;
    goto LABEL_39;
  }
  if ( v38 == v32 )
  {
    *v13 = *(_DWORD *)(v11 + 284);
    goto LABEL_38;
  }
  LOBYTE(v25) = 1;
  v26 = CscEnpEvictpChangeDbStatus(a1, 32, v25);
  v4 = v40;
  EnumContext = v26;
  if ( v26 >= 0 )
    *v13 = *(_DWORD *)(v11 + 288);
LABEL_39:
  v27 = (unsigned int)*v13;
  if ( (_DWORD)v27 )
  {
    v28 = -10000000 * v27;
    v29 = v41;
    *v41 = v28;
  }
  else
  {
    v29 = 0;
  }
  *v4 = v29;
  CscEnpDbInfoRelease(a1);
LABEL_45:
  KeLeaveCriticalRegion();
  if ( v5 )
    CscEnEvictFreeEnumContext(&v35);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_qiDD(WPP_GLOBAL_Control->AttachedDevice);
  return (unsigned int)EnumContext;
}

```

## disassembly

```asm
0x14005888c  mov     [rsp-8+arg_18], r9
0x140058891  mov     [rsp-8+arg_10], r8
0x140058896  push    rbp
0x140058897  push    rbx
0x140058898  push    rsi
0x140058899  push    rdi
0x14005889a  push    r12
0x14005889c  push    r13
0x14005889e  push    r14
0x1400588a0  push    r15
0x1400588a2  lea     rbp, [rsp-1Fh]
0x1400588a7  sub     rsp, 88h
0x1400588ae  xor     r15d, r15d
0x1400588b1  mov     r14, r8
0x1400588b4  mov     r13d, r15d
0x1400588b7  mov     [rbp+57h+var_58], r15
0x1400588bb  mov     r12d, r15d
0x1400588be  mov     [rbp+57h+var_60], r15
0x1400588c2  mov     [rbp+57h+var_50], r15
0x1400588c6  mov     dil, dl
0x1400588c9  mov     [rbp+57h+arg_0], r15d
0x1400588cd  mov     rsi, rcx
0x1400588d0  mov     rdx, cs:WPP_GLOBAL_Control
0x1400588d7  lea     rax, WPP_GLOBAL_Control
0x1400588de  cmp     rdx, rax
0x1400588e1  jz      short loc_14005891F
0x1400588e3  test    dword ptr [rdx+2Ch], 20000h
0x1400588ea  jz      short loc_14005891F
0x1400588ec  mov     rcx, [r8]
0x1400588ef  test    rcx, rcx
0x1400588f2  jz      short loc_1400588F9
0x1400588f4  mov     r8, [rcx]
0x1400588f7  jmp     short loc_1400588FC
0x1400588f9  mov     r8, r15
0x1400588fc  mov     al, dil
0x1400588ff  mov     [rsp+0C0h+var_98], r8
0x140058904  neg     al
0x140058906  mov     [rsp+0C0h+var_A0], rcx
0x14005890b  mov     rcx, [rdx+18h]
0x14005890f  sbb     r9b, r9b
0x140058912  and     r9b, 0Bh
0x140058916  add     r9b, 4Eh ; 'N'
0x14005891a  call    WPP_SF_cqi
0x14005891f  call    cs:__imp_KeEnterCriticalRegion
0x140058926  nop     dword ptr [rax+rax+00h]
0x14005892b  mov     rcx, rsi
0x14005892e  call    CscEnpDbInfoAcquireExclusive
0x140058933  mov     rbx, [rsi+8]
0x140058937  test    dil, dil
0x14005893a  jz      short loc_140058971
0x14005893c  cmp     [r14], r15
0x14005893f  jz      short loc_14005895F
0x140058941  mov     eax, [rbx+90h]
0x140058947  test    al, 20h
0x140058949  jz      short loc_140058953
0x14005894b  mov     eax, [rbx+120h]
0x140058951  jmp     short loc_140058959
0x140058953  mov     eax, [rbx+11Ch]
0x140058959  mov     [rbx+130h], eax
0x14005895f  mov     r15d, 679h
0x140058965  lea     rdi, [rbx+130h]
0x14005896c  jmp     loc_140058B7D
0x140058971  lea     rdi, [rbx+130h]
0x140058978  mov     [rdi], r12d
0x14005897b  mov     rax, [rbx+100h]
0x140058982  mov     rcx, [rbx+0C0h]
0x140058989  cmp     rcx, rax
0x14005898c  ja      short loc_1400589A9
0x14005898e  mov     rax, [rbx+0A0h]
0x140058995  cmp     [rbx+0C8h], rax
0x14005899c  jbe     loc_140058B79
0x1400589a2  xor     ecx, ecx
0x1400589a4  xor     r14d, r14d
0x1400589a7  jmp     short loc_1400589B3
0x1400589a9  sub     rcx, rax
0x1400589ac  mov     [rbp+57h+var_68], r15
0x1400589b0  mov     r14, rcx
0x1400589b3  mov     rax, [rbx+0C8h]
0x1400589ba  mov     rdx, [rbx+0A0h]
0x1400589c1  mov     [rbp+57h+var_68], r14
0x1400589c5  mov     [rbp+57h+var_48], rax
0x1400589c9  cmp     rax, rdx
0x1400589cc  jbe     short loc_1400589DC
0x1400589ce  sub     rax, rdx
0x1400589d1  cmp     rcx, rax
0x1400589d4  cmovbe  r14, rax
0x1400589d8  mov     [rbp+57h+var_68], r14
0x1400589dc  mov     rcx, rsi
0x1400589df  call    CscEnpQuotaIsRecovering
0x1400589e4  test    al, al
0x1400589e6  jnz     short loc_1400589F6
0x1400589e8  mov     eax, [rbx+90h]
0x1400589ee  mov     [rbp+57h+arg_8], r15b
0x1400589f2  test    al, 20h
0x1400589f4  jz      short loc_1400589FA
0x1400589f6  mov     [rbp+57h+arg_8], 1
0x1400589fa  mov     rcx, [rsi+8]
0x1400589fe  lea     rdx, [rbp+57h+arg_0]
0x140058a02  mov     rcx, [rcx+30h]
0x140058a06  call    CscPqQueryItemCount
0x140058a0b  mov     rax, [rsi+8]
0x140058a0f  mov     rcx, rsi
0x140058a12  mov     eax, [rax+140h]
0x140058a18  mov     [rbp+57h+var_70], eax
0x140058a1b  mov     rax, ds:0FFFFF78000000014h
0x140058a25  mov     [rbx+128h], rax
0x140058a2c  call    CscEnpDbInfoRelease
0x140058a31  xor     r9d, r9d
0x140058a34  mov     byte ptr [rsp+0C0h+var_A0], r15b
0x140058a39  xor     r8d, r8d
0x140058a3c  lea     rcx, [rbp+57h+var_58]
0x140058a40  mov     dl, 1
0x140058a42  call    CscEnEvictAllocateEnumContext
0x140058a47  mov     r12d, eax
0x140058a4a  test    eax, eax
0x140058a4c  js      loc_140058BAA
0x140058a52  xor     r9d, r9d
0x140058a55  mov     [rsp+0C0h+var_A0], r15
0x140058a5a  xor     r8d, r8d
0x140058a5d  mov     rcx, rsi
0x140058a60  lea     edx, [r9+1]
0x140058a64  call    CscEnpNotifyQuota
0x140058a69  mov     r13, [rbp+57h+var_58]
0x140058a6d  lea     rax, [rbp+57h+var_50]
0x140058a71  mov     [rsp+0C0h+var_98], rax
0x140058a76  lea     r8, [rbp+57h+var_68]
0x140058a7a  lea     rax, [rbp+57h+var_60]
0x140058a7e  xor     r9d, r9d
0x140058a81  mov     rdx, r13
0x140058a84  mov     [rsp+0C0h+var_A0], rax
0x140058a89  mov     rcx, rsi
0x140058a8c  call    CscEnEvict
0x140058a91  mov     r12d, eax
0x140058a94  test    eax, eax
0x140058a96  js      loc_140058BA2
0x140058a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140058aa3  lea     rax, WPP_GLOBAL_Control
0x140058aaa  cmp     rcx, rax
0x140058aad  jz      short loc_140058AFE
0x140058aaf  test    dword ptr [rcx+2Ch], 20000h
0x140058ab6  jz      short loc_140058AFE
0x140058ab8  mov     al, [rbp+57h+arg_8]
0x140058abb  mov     r9, r14
0x140058abe  mov     rcx, [rcx+18h]
0x140058ac2  neg     al
0x140058ac4  mov     eax, [rbp+57h+var_70]
0x140058ac7  mov     [rsp+0C0h+var_78], eax
0x140058acb  sbb     dl, dl
0x140058acd  mov     eax, [rbp+57h+arg_0]
0x140058ad0  and     dl, 0Bh
0x140058ad3  mov     [rsp+0C0h+var_80], eax
0x140058ad7  add     dl, 4Eh ; 'N'
0x140058ada  mov     rax, [rbp+57h+var_48]
0x140058ade  mov     [rsp+0C0h+var_88], dl
0x140058ae2  mov     [rsp+0C0h+var_90], rax
0x140058ae7  mov     rax, [rbp+57h+var_50]
0x140058aeb  mov     [rsp+0C0h+var_98], rax
0x140058af0  mov     rax, [rbp+57h+var_60]
0x140058af4  mov     [rsp+0C0h+var_A0], rax
0x140058af9  call    WPP_SF_iiiicdd
0x140058afe  lea     rax, [rbp+57h+var_50]
0x140058b02  mov     edx, 2
0x140058b07  lea     r9, [rbp+57h+var_68]
0x140058b0b  mov     [rsp+0C0h+var_A0], rax
0x140058b10  lea     r8, [rbp+57h+var_60]
0x140058b14  mov     rcx, rsi
0x140058b17  call    CscEnpNotifyQuota
0x140058b1c  mov     rcx, rsi
0x140058b1f  call    CscEnpDbInfoAcquireExclusive
0x140058b24  mov     rax, [rbp+57h+var_68]
0x140058b28  cmp     [rbp+57h+var_60], rax
0x140058b2c  jb      short loc_140058B36
0x140058b2e  mov     [rdi], r15d
0x140058b31  jmp     loc_14005897B
0x140058b36  cmp     [rbp+57h+arg_8], r15b
0x140058b3a  jnz     short loc_140058B79
0x140058b3c  mov     eax, [rbp+57h+var_70]
0x140058b3f  cmp     [rbp+57h+arg_0], eax
0x140058b42  jz      short loc_140058B71
0x140058b44  mov     r8b, 1
0x140058b47  mov     edx, 20h ; ' '
0x140058b4c  mov     rcx, rsi
0x140058b4f  call    CscEnpEvictpChangeDbStatus
0x140058b54  mov     r14, [rbp+57h+arg_10]
0x140058b58  mov     r12d, eax
0x140058b5b  test    eax, eax
0x140058b5d  jns     short loc_140058B67
0x140058b5f  mov     r15d, 6E4h
0x140058b65  jmp     short loc_140058B7D
0x140058b67  mov     eax, [rbx+120h]
0x140058b6d  mov     [rdi], eax
0x140058b6f  jmp     short loc_140058B7D
0x140058b71  mov     eax, [rbx+11Ch]
0x140058b77  mov     [rdi], eax
0x140058b79  mov     r14, [rbp+57h+arg_10]
0x140058b7d  mov     eax, [rdi]
0x140058b7f  test    eax, eax
0x140058b81  jz      short loc_140058B93
0x140058b83  imul    rcx, rax, 0FFFFFFFFFF676980h
0x140058b8a  mov     rax, [rbp+57h+arg_18]
0x140058b8e  mov     [rax], rcx
0x140058b91  jmp     short loc_140058B95
0x140058b93  xor     eax, eax
0x140058b95  mov     rcx, rsi
0x140058b98  mov     [r14], rax
0x140058b9b  call    CscEnpDbInfoRelease
0x140058ba0  jmp     short loc_140058BB8
0x140058ba2  mov     r15d, 6C6h
0x140058ba8  jmp     short loc_140058BB4
0x140058baa  mov     r13, [rbp+57h+var_58]
0x140058bae  mov     r15d, 6B4h
0x140058bb4  mov     r14, [rbp+57h+arg_10]
0x140058bb8  call    cs:__imp_KeLeaveCriticalRegion
0x140058bbf  nop     dword ptr [rax+rax+00h]
0x140058bc4  test    r13, r13
0x140058bc7  jz      short loc_140058BD2
0x140058bc9  lea     rcx, [rbp+57h+var_58]
0x140058bcd  call    CscEnEvictFreeEnumContext
0x140058bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140058bd9  lea     rax, WPP_GLOBAL_Control
0x140058be0  cmp     rcx, rax
0x140058be3  jz      short loc_140058C15
0x140058be5  test    dword ptr [rcx+2Ch], 20000h
0x140058bec  jz      short loc_140058C15
0x140058bee  mov     r9, [r14]
0x140058bf1  test    r9, r9
0x140058bf4  jz      short loc_140058BFB
0x140058bf6  mov     rax, [r9]
0x140058bf9  jmp     short loc_140058BFD
0x140058bfb  xor     eax, eax
0x140058bfd  mov     rcx, [rcx+18h]
0x140058c01  mov     dword ptr [rsp+0C0h+var_90], r15d
0x140058c06  mov     dword ptr [rsp+0C0h+var_98], r12d
0x140058c0b  mov     [rsp+0C0h+var_A0], rax
0x140058c10  call    WPP_SF_qiDD
0x140058c15  mov     eax, r12d
0x140058c18  add     rsp, 88h
0x140058c1f  pop     r15
0x140058c21  pop     r14
0x140058c23  pop     r13
0x140058c25  pop     r12
0x140058c27  pop     rdi
0x140058c28  pop     rsi
0x140058c29  pop     rbx
0x140058c2a  pop     rbp
0x140058c2b  retn
```
