# VmbusTlProcessConnectRequestWorkItem

- ea: `0x14001b98c`
- end: `0x14001bd19`
- name: `VmbusTlProcessConnectRequestWorkItem`
- size: `909`
- prototype: `void __fastcall(char *P)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14001b720`

## callees

- `0x140001008`
- `0x140001164`
- `0x140009df0`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x1400188c4`
- `0x14001b98c`
- `0x14001bd20`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x14001b9ea`
- `ntoskrnl!ExUuidCreate` at `0x14001b9ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bc47`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bcd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bce4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bc47`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bcd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bce4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bc33`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bcbe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bc33`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001bcbe`

## pseudocode

```c
void __fastcall VmbusTlProcessConnectRequestWorkItem(char *P)
{
  NTSTATUS v2; // eax
  __int64 *v3; // rdi
  int v4; // esi
  __int128 v5; // xmm0
  __int64 v6; // rcx
  int v7; // ecx
  int v8; // edi
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rcx
  __int64 v12; // r10
  void (__fastcall *v13)(__int64, __int128 *, __int128 *, _QWORD, int); // rax
  __int128 v14; // xmm1
  __int64 v15; // rdi
  __int64 v16; // rax
  void (__fastcall *v17)(__int64); // rax
  __int64 v18; // rdi
  __int64 v19; // rax
  void (__fastcall *v20)(__int64); // rax
  int v21; // [rsp+20h] [rbp-A9h]
  int v22; // [rsp+40h] [rbp-89h] BYREF
  __int128 v23; // [rsp+50h] [rbp-79h] BYREF
  __int128 v24; // [rsp+60h] [rbp-69h] BYREF
  __int128 v25; // [rsp+70h] [rbp-59h] BYREF
  UUID Uuid; // [rsp+80h] [rbp-49h] BYREF
  __int64 v27[2]; // [rsp+90h] [rbp-39h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-29h]
  __int128 v29; // [rsp+B0h] [rbp-19h]
  __int64 v30; // [rsp+C0h] [rbp-9h]
  __int64 v31; // [rsp+C8h] [rbp-1h]
  char *v32; // [rsp+D0h] [rbp+7h]
  __int64 v33; // [rsp+D8h] [rbp+Fh]
  int *v34; // [rsp+E0h] [rbp+17h]
  __int64 v35; // [rsp+E8h] [rbp+1Fh]

  v25 = 0;
  Uuid = 0;
  if ( !memcmp(P + 48, &HV_GUID_ZERO, 0x10u) )
  {
    v2 = ExUuidCreate(&Uuid);
    if ( v2 < 0 )
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceGuidError("VmbusTlProcessConnectRequestWorkItem", 1025, (unsigned int)v2, P + 32);
      goto LABEL_21;
    }
  }
  else
  {
    Uuid = (UUID)*((_OWORD *)P + 3);
  }
  if ( P[64] )
  {
    v3 = (__int64 *)(P + 80);
    v6 = *((_QWORD *)P + 10);
    v4 = 17;
    LODWORD(v30) = 0;
    *(_OWORD *)v27 = 0;
    v28 = 0;
    v29 = 0;
    if ( (int)HvSocketFindHostedSiloByVmId(v6, P, v27) >= 0 )
    {
LABEL_12:
      v5 = *(_OWORD *)v27;
      goto LABEL_13;
    }
  }
  else
  {
    v3 = (__int64 *)(P + 80);
    if ( memcmp(P + 16, &HV_GUID_ZERO, 0x10u) )
    {
      v5 = *((_OWORD *)P + 1);
      v4 = 13;
LABEL_13:
      v25 = v5;
      goto LABEL_14;
    }
    v4 = 1;
    LODWORD(v30) = 0;
    *(_OWORD *)v27 = 0;
    v28 = 0;
    v29 = 0;
  }
  if ( (int)HvSocketGetVmAddressInfo(*v3, P, v27) >= 0 )
    goto LABEL_12;
LABEL_14:
  v7 = v4 | 0x20;
  if ( P[65] != 2 )
    v7 = v4;
  v8 = VmbusTlProcessNewConnection(
         *v3,
         0,
         (__int64)&HV_GUID_CHILDREN,
         (__int64)P,
         (__int64)&v25,
         (__int64)(P + 32),
         &Uuid,
         v7);
  if ( v8 < 0 && (unsigned int)dword_140013058 > 2 )
  {
    v11 = *((_QWORD *)P + 9);
    *(_QWORD *)&v29 = "A Hyper-V socket connection request failed.";
    *((_QWORD *)&v29 + 1) = 44;
    v30 = v11 + 232;
    v34 = &v22;
    v31 = 16;
    v32 = P + 32;
    v33 = 16;
    v22 = v8;
    v35 = 4;
    tlgWriteTransfer_EtwWriteTransfer((int)&dword_140013058, (int)&byte_14001151D, v9, v10, 6u, (__int64)v27);
  }
  v12 = *((_QWORD *)P + 9);
  v13 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, _QWORD, int))(v12 + 176);
  if ( v13 )
  {
    LOBYTE(v21) = P[65];
    v14 = *((_OWORD *)P + 3);
    v23 = *((_OWORD *)P + 2);
    v24 = v14;
    v13(v12, &v24, &v23, (unsigned int)v8, v21);
  }
LABEL_21:
  v15 = *((_QWORD *)P + 9);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlProcessConnectRequestWorkItem",
      1129,
      *((_QWORD *)P + 9),
      *(_QWORD *)(v15 + 8),
      (__int64)"Dereference object");
  v16 = _InterlockedDecrement64((volatile signed __int64 *)(v15 + 8));
  if ( v16 <= 0 )
  {
    if ( v16 )
      __fastfail(0xEu);
    v17 = *(void (__fastcall **)(__int64))(v15 + 80);
    if ( v17 )
      v17(v15);
    if ( *(_DWORD *)(v15 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v15, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v15 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v15 + 96), (PVOID)v15);
    }
  }
  v18 = *((_QWORD *)P + 10);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlProcessConnectRequestWorkItem",
      1134,
      *((_QWORD *)P + 10),
      *(_QWORD *)(v18 + 8),
      (__int64)"Dereference object");
  v19 = _InterlockedDecrement64((volatile signed __int64 *)(v18 + 8));
  if ( v19 <= 0 )
  {
    if ( v19 )
      __fastfail(0xEu);
    v20 = *(void (__fastcall **)(__int64))(v18 + 80);
    if ( v20 )
      v20(v18);
    if ( *(_DWORD *)(v18 + 88) == 1 )
    {
      ExFreePoolWithTag((PVOID)v18, 0x69706E56u);
    }
    else if ( *(_DWORD *)(v18 + 88) == 2 )
    {
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v18 + 96), (PVOID)v18);
    }
  }
  ExFreePoolWithTag(P, 0x69706E56u);
}

```

## disassembly

```asm
0x14001b98c  mov     [rsp-8+arg_8], rbx
0x14001b991  mov     [rsp-8+arg_10], rsi
0x14001b996  push    rbp
0x14001b997  push    rdi
0x14001b998  push    r12
0x14001b99a  push    r13
0x14001b99c  push    r14
0x14001b99e  lea     rbp, [rsp-37h]
0x14001b9a3  sub     rsp, 100h
0x14001b9aa  mov     rax, cs:__security_cookie
0x14001b9b1  xor     rax, rsp
0x14001b9b4  mov     [rbp+57h+var_30], rax
0x14001b9b8  mov     rbx, rcx
0x14001b9bb  lea     rdx, HV_GUID_ZERO; Buf2
0x14001b9c2  xorps   xmm0, xmm0
0x14001b9c5  xorps   xmm1, xmm1
0x14001b9c8  mov     r12d, 10h
0x14001b9ce  add     rcx, 30h ; '0'; Buf1
0x14001b9d2  mov     r8d, r12d; Size
0x14001b9d5  movups  [rbp+57h+var_B0], xmm0
0x14001b9d9  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm1
0x14001b9dd  call    memcmp
0x14001b9e2  test    eax, eax
0x14001b9e4  jnz     short loc_14001BA26
0x14001b9e6  lea     rcx, [rbp+57h+Uuid]; Uuid
0x14001b9ea  call    cs:__imp_ExUuidCreate
0x14001b9f1  nop     dword ptr [rax+rax+00h]
0x14001b9f6  test    eax, eax
0x14001b9f8  jns     short loc_14001BA2F
0x14001b9fa  mov     ecx, cs:dword_140013058
0x14001ba00  cmp     ecx, 2
0x14001ba03  jbe     loc_14001BBB3
0x14001ba09  lea     r9, [rbx+20h]
0x14001ba0d  mov     r8d, eax
0x14001ba10  mov     edx, 401h
0x14001ba15  lea     rcx, aVmbustlprocess; "VmbusTlProcessConnectRequestWorkItem"
0x14001ba1c  call    HvsocketTraceGuidError
0x14001ba21  jmp     loc_14001BBB3
0x14001ba26  movups  xmm0, xmmword ptr [rbx+30h]
0x14001ba2a  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x14001ba2f  cmp     byte ptr [rbx+40h], 0
0x14001ba33  jnz     short loc_14001BA74
0x14001ba35  mov     r8, r12; Size
0x14001ba38  lea     rdx, HV_GUID_ZERO; Buf2
0x14001ba3f  lea     rcx, [rbx+10h]; Buf1
0x14001ba43  call    memcmp
0x14001ba48  lea     rdi, [rbx+50h]
0x14001ba4c  test    eax, eax
0x14001ba4e  jnz     short loc_14001BA69
0x14001ba50  xorps   xmm0, xmm0
0x14001ba53  lea     esi, [rax+1]
0x14001ba56  xor     eax, eax
0x14001ba58  mov     dword ptr [rbp+57h+var_60], eax
0x14001ba5b  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14001ba5f  movups  [rbp+57h+var_80], xmm0
0x14001ba63  movups  [rbp+57h+var_70], xmm0
0x14001ba67  jmp     short loc_14001BAA4
0x14001ba69  movups  xmm0, xmmword ptr [rbx+10h]
0x14001ba6d  mov     esi, 0Dh
0x14001ba72  jmp     short loc_14001BABB
0x14001ba74  xorps   xmm0, xmm0
0x14001ba77  lea     rdi, [rbx+50h]
0x14001ba7b  mov     rcx, [rdi]
0x14001ba7e  lea     r8, [rbp+57h+var_90]
0x14001ba82  xor     eax, eax
0x14001ba84  mov     rdx, rbx
0x14001ba87  mov     esi, 11h
0x14001ba8c  mov     dword ptr [rbp+57h+var_60], eax
0x14001ba8f  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14001ba93  movups  [rbp+57h+var_80], xmm0
0x14001ba97  movups  [rbp+57h+var_70], xmm0
0x14001ba9b  call    HvSocketFindHostedSiloByVmId
0x14001baa0  test    eax, eax
0x14001baa2  jns     short loc_14001BAB7
0x14001baa4  mov     rcx, [rdi]
0x14001baa7  lea     r8, [rbp+57h+var_90]
0x14001baab  mov     rdx, rbx
0x14001baae  call    HvSocketGetVmAddressInfo
0x14001bab3  test    eax, eax
0x14001bab5  js      short loc_14001BAC0
0x14001bab7  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x14001babb  movdqu  [rbp+57h+var_B0], xmm0
0x14001bac0  mov     ecx, esi
0x14001bac2  lea     rax, [rbp+57h+Uuid]
0x14001bac6  or      ecx, 20h
0x14001bac9  lea     r14, [rbx+20h]
0x14001bacd  cmp     byte ptr [rbx+41h], 2
0x14001bad1  lea     r8, HV_GUID_CHILDREN
0x14001bad8  mov     r9, rbx
0x14001badb  cmovnz  ecx, esi
0x14001bade  xor     edx, edx
0x14001bae0  mov     [rsp+120h+var_E8], ecx
0x14001bae4  mov     rcx, [rdi]
0x14001bae7  mov     [rsp+120h+var_F0], rax
0x14001baec  lea     rax, [rbp+57h+var_B0]
0x14001baf0  mov     [rsp+120h+var_F8], r14
0x14001baf5  mov     qword ptr [rsp+120h+var_100], rax
0x14001bafa  call    VmbusTlProcessNewConnection
0x14001baff  mov     edi, eax
0x14001bb01  test    eax, eax
0x14001bb03  jns     short loc_14001BB77
0x14001bb05  mov     ecx, cs:dword_140013058
0x14001bb0b  cmp     ecx, 2
0x14001bb0e  jbe     short loc_14001BB77
0x14001bb10  mov     rcx, [rbx+48h]
0x14001bb14  lea     rax, aAHyperVSocketC_0; "A Hyper-V socket connection request fai"...
0x14001bb1b  mov     qword ptr [rbp+57h+var_70], rax
0x14001bb1f  lea     rdx, byte_14001151D; int
0x14001bb26  add     rcx, 0E8h
0x14001bb2d  mov     qword ptr [rbp+57h+var_70+8], 2Ch ; ','
0x14001bb35  lea     rax, [rsp+120h+var_E0]
0x14001bb3a  mov     [rbp+57h+var_60], rcx
0x14001bb3e  mov     [rbp+57h+var_40], rax
0x14001bb42  lea     rcx, dword_140013058; int
0x14001bb49  lea     rax, [rbp+57h+var_90]
0x14001bb4d  mov     [rbp+57h+var_58], r12
0x14001bb51  mov     [rsp+120h+var_F8], rax; __int64
0x14001bb56  mov     [rsp+120h+var_100], 6; ULONG
0x14001bb5e  mov     [rbp+57h+var_50], r14
0x14001bb62  mov     [rbp+57h+var_48], r12
0x14001bb66  mov     [rsp+120h+var_E0], edi
0x14001bb6a  mov     [rbp+57h+var_38], 4
0x14001bb72  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001bb77  mov     r10, [rbx+48h]
0x14001bb7b  mov     rax, [r10+0B0h]
0x14001bb82  test    rax, rax
0x14001bb85  jz      short loc_14001BBB3
0x14001bb87  mov     cl, [rbx+41h]
0x14001bb8a  lea     r8, [rbp+57h+var_D0]
0x14001bb8e  movups  xmm0, xmmword ptr [r14]
0x14001bb92  mov     byte ptr [rsp+120h+var_100], cl
0x14001bb96  mov     rcx, r10
0x14001bb99  movups  xmm1, xmmword ptr [rbx+30h]
0x14001bb9d  mov     r9d, edi
0x14001bba0  lea     rdx, [rbp+57h+var_C0]
0x14001bba4  movdqu  [rbp+57h+var_D0], xmm0
0x14001bba9  movdqu  [rbp+57h+var_C0], xmm1
0x14001bbae  call    _guard_dispatch_icall
0x14001bbb3  mov     eax, cs:dword_140013058
0x14001bbb9  lea     r13, aDereferenceObj; "Dereference object"
0x14001bbc0  mov     rdi, [rbx+48h]
0x14001bbc4  cmp     eax, 5
0x14001bbc7  jbe     short loc_14001BBE6
0x14001bbc9  mov     r9, [rdi+8]
0x14001bbcd  lea     rcx, aVmbustlprocess; "VmbusTlProcessConnectRequestWorkItem"
0x14001bbd4  mov     r8, rdi
0x14001bbd7  mov     qword ptr [rsp+120h+var_100], r13
0x14001bbdc  mov     edx, 469h
0x14001bbe1  call    HvsocketTraceReferenceCount
0x14001bbe6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001bbea  mov     rax, rsi
0x14001bbed  lock xadd [rdi+8], rax
0x14001bbf3  add     rax, rsi
0x14001bbf6  lea     r12d, [rsi+0Fh]
0x14001bbfa  mov     r14d, 69706E56h
0x14001bc00  test    rax, rax
0x14001bc03  jg      short loc_14001BC53
0x14001bc05  jz      short loc_14001BC0E
0x14001bc07  mov     ecx, r12d
0x14001bc0a  int     29h; Win8: RtlFailFast(ecx)
0x14001bc0c  jmp     short loc_14001BC53
0x14001bc0e  mov     rax, [rdi+50h]
0x14001bc12  test    rax, rax
0x14001bc15  jz      short loc_14001BC1F
0x14001bc17  mov     rcx, rdi
0x14001bc1a  call    _guard_dispatch_icall
0x14001bc1f  mov     ecx, [rdi+58h]
0x14001bc22  sub     ecx, 1
0x14001bc25  jz      short loc_14001BC41
0x14001bc27  cmp     ecx, 1
0x14001bc2a  jnz     short loc_14001BC53
0x14001bc2c  mov     rcx, [rdi+60h]; Lookaside
0x14001bc30  mov     rdx, rdi; Entry
0x14001bc33  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001bc3a  nop     dword ptr [rax+rax+00h]
0x14001bc3f  jmp     short loc_14001BC53
0x14001bc41  mov     edx, r14d; Tag
0x14001bc44  mov     rcx, rdi; P
0x14001bc47  call    cs:__imp_ExFreePoolWithTag
0x14001bc4e  nop     dword ptr [rax+rax+00h]
0x14001bc53  mov     eax, cs:dword_140013058
0x14001bc59  mov     rdi, [rbx+50h]
0x14001bc5d  cmp     eax, 5
0x14001bc60  jbe     short loc_14001BC7F
0x14001bc62  mov     r9, [rdi+8]
0x14001bc66  lea     rcx, aVmbustlprocess; "VmbusTlProcessConnectRequestWorkItem"
0x14001bc6d  mov     r8, rdi
0x14001bc70  mov     qword ptr [rsp+120h+var_100], r13
0x14001bc75  mov     edx, 46Eh
0x14001bc7a  call    HvsocketTraceReferenceCount
0x14001bc7f  mov     rax, rsi
0x14001bc82  lock xadd [rdi+8], rax
0x14001bc88  add     rax, rsi
0x14001bc8b  test    rax, rax
0x14001bc8e  jg      short loc_14001BCDE
0x14001bc90  jz      short loc_14001BC99
0x14001bc92  mov     rcx, r12
0x14001bc95  int     29h; Win8: RtlFailFast(ecx)
0x14001bc97  jmp     short loc_14001BCDE
0x14001bc99  mov     rax, [rdi+50h]
0x14001bc9d  test    rax, rax
0x14001bca0  jz      short loc_14001BCAA
0x14001bca2  mov     rcx, rdi
0x14001bca5  call    _guard_dispatch_icall
0x14001bcaa  mov     ecx, [rdi+58h]
0x14001bcad  sub     ecx, 1
0x14001bcb0  jz      short loc_14001BCCC
0x14001bcb2  cmp     ecx, 1
0x14001bcb5  jnz     short loc_14001BCDE
0x14001bcb7  mov     rcx, [rdi+60h]; Lookaside
0x14001bcbb  mov     rdx, rdi; Entry
0x14001bcbe  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001bcc5  nop     dword ptr [rax+rax+00h]
0x14001bcca  jmp     short loc_14001BCDE
0x14001bccc  mov     edx, r14d; Tag
0x14001bccf  mov     rcx, rdi; P
0x14001bcd2  call    cs:__imp_ExFreePoolWithTag
0x14001bcd9  nop     dword ptr [rax+rax+00h]
0x14001bcde  mov     edx, r14d; Tag
0x14001bce1  mov     rcx, rbx; P
0x14001bce4  call    cs:__imp_ExFreePoolWithTag
0x14001bceb  nop     dword ptr [rax+rax+00h]
0x14001bcf0  mov     rcx, [rbp+57h+var_30]
0x14001bcf4  xor     rcx, rsp; StackCookie
0x14001bcf7  call    __security_check_cookie
0x14001bcfc  lea     r11, [rsp+120h+var_20]
0x14001bd04  mov     rbx, [r11+38h]
0x14001bd08  mov     rsi, [r11+40h]
0x14001bd0c  mov     rsp, r11
0x14001bd0f  pop     r14
0x14001bd11  pop     r13
0x14001bd13  pop     r12
0x14001bd15  pop     rdi
0x14001bd16  pop     rbp
0x14001bd17  retn
```
