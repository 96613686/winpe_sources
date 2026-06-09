# basessp::BaseSSP::SpAcquireCredentialsHandle(_UNICODE_STRING *,ulong,_LUID *,void *,void *,void *,unsigned __int64 *,_LARGE_INTEGER *)

- ea: `0x180003a10`
- end: `0x18000421b`
- name: `?SpAcquireCredentialsHandle@BaseSSP@basessp@@QEAAJPEAU_UNICODE_STRING@@KPEAU_LUID@@PEAX22PEA_KPEAT_LARGE_INTEGER@@@Z`
- size: `2059`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this, struct _UNICODE_STRING *, unsigned int, struct _LUID *, void *, void *, void *, unsigned __int64 *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800038e0`

## callees

- `0x180003a10`
- `0x180004230`
- `0x1800043e0`
- `0x180004404`
- `0x1800058a4`
- `0x18000e710`
- `0x18000e9e8`
- `0x18000eb80`
- `0x18000ebcc`
- `0x18000ec28`
- `0x18001ece2`
- `0x18001ecee`
- `0x18001ed20`
- `0x180020010`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x180003d01`
- `ntdll!NtDuplicateObject` at `0x180003d01`
- `ntdll!NtQueryInformationToken` at `0x180003b64`
- `ntdll!NtQueryInformationToken` at `0x180003d2f`
- `ntdll!NtQueryInformationToken` at `0x180003b64`
- `ntdll!NtQueryInformationToken` at `0x180003d2f`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180003e85`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180003e85`
- `ntdll!RtlConvertSharedToExclusive` at `0x180003e6c`
- `ntdll!RtlConvertSharedToExclusive` at `0x180003e6c`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180003d94`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180003d94`
- `ntdll!RtlReleaseResource` at `0x180003db6`
- `ntdll!RtlReleaseResource` at `0x180003f11`
- `ntdll!RtlReleaseResource` at `0x180004205`
- `ntdll!RtlReleaseResource` at `0x180003db6`
- `ntdll!RtlReleaseResource` at `0x180003f11`
- `ntdll!RtlReleaseResource` at `0x180004205`
- `ntdll!RtlAcquireResourceShared` at `0x180003d86`
- `ntdll!RtlAcquireResourceShared` at `0x180003d86`
- `ntdll!NtClose` at `0x180004210`
- `ntdll!NtClose` at `0x180004210`

## string_xrefs

- `0x180003bef`: `onecore\ds\security\protocols\basessp\credapi.cxx`
- `0x180003f85`: `onecore\ds\security\protocols\basessp\credapi.cxx`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::SpAcquireCredentialsHandle(
        basessp::BaseSSP *this,
        struct _UNICODE_STRING *a2,
        int a3,
        struct _LUID *a4,
        void *a5,
        void *a6,
        void *a7,
        unsigned __int64 *a8,
        union _LARGE_INTEGER *a9)
{
  basessp::BaseSSP *v10; // r14
  __int64 v11; // rax
  NTSTATUS v13; // ebx
  __int64 v14; // rax
  size_t v15; // rsi
  PVOID v16; // rax
  basessp::BaseSSP *v17; // rcx
  struct basessp::_WST_CREDENTIAL **v18; // rbx
  PVOID inserted; // rax
  basessp::BaseSSP *v21; // rcx
  struct basessp::_WST_CREDENTIAL *v22; // rcx
  struct basessp::_WST_CREDENTIAL *v23; // rbx
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  struct basessp::_WST_CREDENTIAL *v26; // rax
  unsigned __int8 NewElement[8]; // [rsp+48h] [rbp-C0h] BYREF
  struct basessp::_WST_CREDENTIAL *v28; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-B0h] BYREF
  ULONG TokenInformationLength; // [rsp+60h] [rbp-A8h] BYREF
  int v31; // [rsp+64h] [rbp-A4h] BYREF
  int v32; // [rsp+68h] [rbp-A0h]
  ULONG ReturnLength; // [rsp+6Ch] [rbp-9Ch] BYREF
  _QWORD v34[4]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v35; // [rsp+90h] [rbp-78h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-68h]
  __int128 v37; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-50h]
  struct basessp::_WST_CREDENTIAL *Buffer; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v40; // [rsp+D0h] [rbp-38h]
  __int128 v41; // [rsp+E0h] [rbp-28h]
  __int128 v42; // [rsp+F0h] [rbp-18h]
  __int128 v43; // [rsp+100h] [rbp-8h]
  __int128 v44; // [rsp+110h] [rbp+8h]
  __int128 v45; // [rsp+120h] [rbp+18h]
  __int128 v46; // [rsp+130h] [rbp+28h]
  __int128 v47; // [rsp+140h] [rbp+38h]
  __int128 v48; // [rsp+150h] [rbp+48h]
  int TokenInformation; // [rsp+168h] [rbp+60h] BYREF
  __int128 v50; // [rsp+16Ch] [rbp+64h]
  __int128 v51; // [rsp+17Ch] [rbp+74h]
  _BYTE v52[20]; // [rsp+18Ch] [rbp+84h] BYREF

  v10 = WSTGlobalBaseSSP;
  v36 = 0;
  v11 = *((_QWORD *)WSTGlobalBaseSSP + 30);
  memset(v34, 0, sizeof(v34));
  v28 = 0;
  v31 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 4;
  v35 = 0;
  TokenInformationLength = 56;
  v50 = 0;
  v51 = 0;
  v32 = a3;
  memset(v52, 0, sizeof(v52));
  if ( !(*(unsigned __int8 (__fastcall **)(__int128 *))(v11 + 192))(&v35) )
  {
    v13 = -1073741595;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2));
    goto LABEL_30;
  }
  if ( (WORD4(v35) & 0x4000) == 0 )
  {
    v13 = -2146893042;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids);
    goto LABEL_30;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)v10 + 30) + 128LL))(v34);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        (unsigned int)&WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids,
        v13,
        (__int64)"onecore\\ds\\security\\protocols\\basessp\\credapi.cxx",
        243);
    goto LABEL_30;
  }
  if ( (v34[2] & 0x2000000LL) != 0 )
  {
    v13 = -1073741790;
    goto LABEL_30;
  }
  TokenHandle = (HANDLE)v34[3];
  if ( a4 && (a4->LowPart || a4->HighPart) )
  {
    if ( *a4 != v34[0] )
    {
      if ( !LOBYTE(v34[2]) )
      {
        v13 = -1073741727;
        goto LABEL_30;
      }
      v13 = (*(__int64 (__fastcall **)(struct _LUID *, HANDLE *))(*((_QWORD *)v10 + 30) + 368LL))(a4, &TokenHandle);
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_DDDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            (unsigned int)&WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids,
            v13,
            a4->HighPart,
            a4->LowPart,
            (__int64)"onecore\\ds\\security\\protocols\\basessp\\credapi.cxx",
            19);
        goto LABEL_30;
      }
    }
  }
  else
  {
    a4 = (struct _LUID *)v34;
  }
  v13 = NtQueryInformationToken(
          TokenHandle,
          TokenStatistics,
          &TokenInformation,
          TokenInformationLength,
          &TokenInformationLength);
  if ( v13 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_30;
    v25 = 54;
    goto LABEL_58;
  }
  a9->QuadPart = 0x7FFFFF36D5969FFFLL;
  v38 = 0;
  v28 = 0;
  v14 = *((_QWORD *)v10 + 30);
  v37 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(__int128 *))(v14 + 192))(&v37) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
LABEL_53:
    v13 = -1073741670;
    goto LABEL_30;
  }
  if ( a2 )
    v15 = a2->Length + 140LL;
  else
    v15 = 138;
  if ( *((_DWORD *)v10 + 52) == 1 )
  {
    v23 = (struct basessp::_WST_CREDENTIAL *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)v10 + 30) + 384LL))((unsigned int)v15);
  }
  else
  {
    v26 = (struct basessp::_WST_CREDENTIAL *)(**((__int64 (__fastcall ***)(_QWORD))v10 + 31))((unsigned int)v15);
    v23 = v26;
    if ( v26 )
    {
      memset_0(v26, 0, v15);
      goto LABEL_17;
    }
  }
  if ( !v23 )
  {
    v13 = -1073741801;
    goto LABEL_30;
  }
LABEL_17:
  *((_DWORD *)v23 + 2) = 1;
  *((_DWORD *)v23 + 8) = v37;
  *(_QWORD *)v23 = 0x444552434F545357LL;
  *((_WORD *)v23 + 12) = 88;
  *((_QWORD *)v23 + 2) = 201;
  if ( a2 )
  {
    *((_DWORD *)v23 + 7) = a2->Length + 88;
    if ( a2->Length )
    {
      *((_WORD *)v23 + 40) = a2->Length;
      *((_DWORD *)v23 + 19) = 120;
      memcpy_0((char *)v23 + 136, a2->Buffer, a2->Length);
    }
  }
  else
  {
    *((_DWORD *)v23 + 7) = 88;
  }
  v28 = v23;
  if ( a5 )
  {
    v13 = basessp::BaseSSP::WSTCaptureSuppliedCreds(v10, a4, TokenHandle, a5, &v28);
    if ( v13 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_30;
      v25 = 55;
      goto LABEL_58;
    }
    v23 = v28;
  }
  *((struct _LUID *)v23 + 5) = *a4;
  *((_DWORD *)v28 + 8) = v34[1];
  *(_QWORD *)((char *)v28 + 60) = *(_QWORD *)&v52[12];
  *((_DWORD *)v28 + 9) = HIDWORD(v34[1]);
  *((_DWORD *)v28 + 17) = v32;
  if ( LOBYTE(v34[2]) )
    *((_DWORD *)v28 + 18) |= 1u;
  if ( TokenHandle == (HANDLE)v34[3] )
  {
    v13 = NtDuplicateObject(
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            TokenHandle,
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            (PHANDLE)v28 + 6,
            0,
            0,
            2u);
    if ( v13 >= 0 )
      goto LABEL_25;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_30;
    v25 = 56;
LABEL_58:
    WPP_SF_d(v24[2], v25, &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids, (unsigned int)v13);
    goto LABEL_30;
  }
  *((_QWORD *)v28 + 6) = TokenHandle;
  TokenHandle = 0;
LABEL_25:
  v13 = NtQueryInformationToken((HANDLE)v34[3], TokenSessionId, &v31, 4u, &ReturnLength);
  if ( v13 >= 0 )
  {
    v40 = 0;
    NewElement[0] = 0;
    *((_DWORD *)v28 + 14) = v31;
    Buffer = v28;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)v10 + 112), 1u);
    v16 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v10 + 8), &Buffer);
    v18 = (struct basessp::_WST_CREDENTIAL **)v16;
    if ( v16 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v16 + 2);
      basessp::BaseSSP::WSTReferenceCredential(v17, *(struct basessp::_WST_CREDENTIAL **)v16);
      goto LABEL_28;
    }
    RtlConvertSharedToExclusive((PRTL_RESOURCE)((char *)v10 + 112));
    inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v10 + 8), &Buffer, 0x98u, NewElement);
    v18 = (struct basessp::_WST_CREDENTIAL **)inserted;
    if ( inserted )
    {
      _InterlockedIncrement((volatile signed __int32 *)inserted + 2);
      basessp::BaseSSP::WSTReferenceCredential(v21, *(struct basessp::_WST_CREDENTIAL **)inserted);
      if ( NewElement[0] )
      {
        *((_DWORD *)*v18 + 3) = 1;
        v22 = *v18;
        *((_OWORD *)v18 + 1) = *(_OWORD *)*v18;
        *((_OWORD *)v18 + 2) = *((_OWORD *)v22 + 1);
        *((_OWORD *)v18 + 3) = *((_OWORD *)v22 + 2);
        *((_OWORD *)v18 + 4) = *((_OWORD *)v22 + 3);
        *((_OWORD *)v18 + 5) = *((_OWORD *)v22 + 4);
        *((_OWORD *)v18 + 6) = *((_OWORD *)v22 + 5);
        *((_OWORD *)v18 + 7) = *((_OWORD *)v22 + 6);
        *((_OWORD *)v18 + 8) = *((_OWORD *)v22 + 7);
        v18[18] = (struct basessp::_WST_CREDENTIAL *)*((_QWORD *)v22 + 16);
        RtlReleaseResource((PRTL_RESOURCE)((char *)v10 + 112));
        goto LABEL_29;
      }
LABEL_28:
      RtlReleaseResource((PRTL_RESOURCE)((char *)v10 + 112));
      basessp::BaseSSP::WSTDereferenceCredential(v10, v28);
      v28 = *v18;
LABEL_29:
      v13 = 0;
      *a8 = (unsigned __int64)v28;
      goto LABEL_30;
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)v10 + 112));
    goto LABEL_53;
  }
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v25 = 57;
    goto LABEL_58;
  }
LABEL_30:
  if ( v28 )
    basessp::BaseSSP::WSTDereferenceCredential(v10, v28);
  if ( TokenHandle && TokenHandle != (HANDLE)v34[3] )
    NtClose(TokenHandle);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180003a10  mov     r11, rsp
0x180003a13  push    rbp
0x180003a14  push    rbx
0x180003a15  lea     rbp, [r11-0D8h]
0x180003a1c  sub     rsp, 1C8h
0x180003a23  mov     rax, cs:__security_cookie
0x180003a2a  xor     rax, rsp
0x180003a2d  mov     [rbp+0D0h+var_38], rax
0x180003a34  mov     [r11+8], rsi
0x180003a38  xorps   xmm0, xmm0
0x180003a3b  mov     rsi, [rbp+0D0h+arg_40]
0x180003a42  xor     ecx, ecx
0x180003a44  mov     [r11-18h], rdi
0x180003a48  xor     eax, eax
0x180003a4a  mov     [r11-20h], r12
0x180003a4e  mov     rdi, rdx
0x180003a51  mov     r12, [rbp+0D0h+arg_20]
0x180003a58  mov     [r11-28h], r13
0x180003a5c  mov     r13, [rbp+0D0h+arg_38]
0x180003a63  mov     [r11-30h], r14
0x180003a67  mov     r14, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * WSTGlobalBaseSSP
0x180003a6e  mov     [rbp+0D0h+var_138], rax
0x180003a72  mov     [rbp+0D0h+var_3C], eax
0x180003a78  movups  xmmword ptr [rsp+1D0h+var_16C+8], xmm0
0x180003a7d  mov     rax, [r14+0F0h]
0x180003a84  mov     [rsp+1D0h+var_16C+4], ecx
0x180003a88  mov     [rsp+1D0h+var_188], rcx
0x180003a8d  mov     [rsp+1D0h+var_174], ecx
0x180003a91  mov     [rsp+1D0h+TokenHandle], rcx
0x180003a96  mov     [rbp+0D0h+TokenInformation], ecx
0x180003a99  lea     rcx, [rbp+0D0h+var_148]
0x180003a9d  movups  xmmword ptr [rsp+78h], xmm0
0x180003aa2  mov     [rsp+1D0h+var_16C], 4
0x180003aaa  movups  [rbp+0D0h+var_148], xmm0
0x180003aae  mov     [rsp+1D0h+TokenInformationLength], 38h ; '8'
0x180003ab6  movups  [rbp+0D0h+var_6C], xmm0
0x180003aba  mov     [r11-38h], r15
0x180003abe  mov     r15, r9
0x180003ac1  movups  [rbp+0D0h+var_5C], xmm0
0x180003ac5  mov     [rsp+1D0h+var_170], r8d
0x180003aca  movups  [rbp+0D0h+var_4C], xmm0
0x180003ad1  mov     rax, [rax+0C0h]
0x180003ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003add  test    al, al
0x180003adf  jz      loc_180004065
0x180003ae5  test    dword ptr [rbp+0D0h+var_148+8], 4000h
0x180003aec  jz      loc_180004099
0x180003af2  mov     rax, [r14+0F0h]
0x180003af9  lea     rcx, [rsp+1D0h+var_16C+4]
0x180003afe  mov     rax, [rax+80h]
0x180003b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b0a  mov     ebx, eax
0x180003b0c  test    eax, eax
0x180003b0e  js      loc_180003BCA
0x180003b14  test    byte ptr [rsp+7Bh], 2
0x180003b19  jnz     loc_180003FEE
0x180003b1f  mov     rax, [rbp+0D0h+var_150]
0x180003b23  mov     [rsp+1D0h+TokenHandle], rax
0x180003b28  test    r15, r15
0x180003b2b  jz      short loc_180003B42
0x180003b2d  mov     eax, [r15]
0x180003b30  test    eax, eax
0x180003b32  jnz     loc_180003F1C
0x180003b38  cmp     [r15+4], eax
0x180003b3c  jnz     loc_180003F1C
0x180003b42  lea     r15, [rsp+1D0h+var_16C+4]
0x180003b47  mov     r9d, [rsp+1D0h+TokenInformationLength]; TokenInformationLength
0x180003b4c  lea     rax, [rsp+1D0h+TokenInformationLength]
0x180003b51  mov     rcx, [rsp+1D0h+TokenHandle]; TokenHandle
0x180003b56  lea     r8, [rbp+0D0h+TokenInformation]; TokenInformation
0x180003b5a  mov     edx, 0Ah; TokenInformationClass
0x180003b5f  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x180003b64  call    cs:__imp_NtQueryInformationToken
0x180003b6a  mov     ebx, eax
0x180003b6c  test    eax, eax
0x180003b6e  js      loc_1800040E3
0x180003b74  mov     rax, 7FFFFF36D5969FFFh
0x180003b7e  lea     rcx, [rbp+0D0h+var_130]
0x180003b82  mov     [rsi], rax
0x180003b85  xorps   xmm0, xmm0
0x180003b88  xor     eax, eax
0x180003b8a  mov     [rbp+0D0h+var_120], rax
0x180003b8e  mov     [rsp+1D0h+var_188], rax
0x180003b93  mov     rax, [r14+0F0h]
0x180003b9a  movups  [rbp+0D0h+var_130], xmm0
0x180003b9e  mov     rax, [rax+0C0h]
0x180003ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003baa  test    al, al
0x180003bac  jz      loc_180003FF8
0x180003bb2  test    rdi, rdi
0x180003bb5  jz      loc_18000417F
0x180003bbb  movzx   esi, word ptr [rdi]
0x180003bbe  add     rsi, 8Ch
0x180003bc5  jmp     loc_180004184
0x180003bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bd1  lea     rax, WPP_GLOBAL_Control
0x180003bd8  cmp     rcx, rax
0x180003bdb  jz      loc_180003DDD
0x180003be1  test    byte ptr [rcx+1Ch], 1
0x180003be5  jz      loc_180003DDD
0x180003beb  mov     rcx, [rcx+10h]
0x180003bef  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\protocols\\bases"...
0x180003bf6  mov     edx, 34h ; '4'
0x180003bfb  mov     [rsp+1D0h+HandleAttributes], 0EF3h
0x180003c03  mov     r9d, ebx
0x180003c06  mov     [rsp+1D0h+ReturnLength], rax
0x180003c0b  lea     r8, WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids
0x180003c12  call    WPP_SF_Dsd
0x180003c17  jmp     loc_180003DDD
0x180003c1c  test    rbx, rbx
0x180003c1f  jz      loc_180003E4E
0x180003c25  mov     dword ptr [rbx+8], 1
0x180003c2c  mov     rcx, rbx
0x180003c2f  mov     eax, dword ptr [rbp+0D0h+var_130]
0x180003c32  mov     [rbx+20h], eax
0x180003c35  mov     rax, 444552434F545357h
0x180003c3f  mov     [rbx], rax
0x180003c42  mov     eax, 58h ; 'X'
0x180003c47  mov     [rbx+18h], ax
0x180003c4b  mov     qword ptr [rbx+10h], 0C9h
0x180003c53  test    rdi, rdi
0x180003c56  jz      loc_18000401F
0x180003c5c  movzx   eax, word ptr [rdi]
0x180003c5f  add     eax, 58h ; 'X'
0x180003c62  mov     [rbx+1Ch], eax
0x180003c65  movzx   eax, word ptr [rdi]
0x180003c68  test    ax, ax
0x180003c6b  jnz     loc_1800041DA
0x180003c71  mov     [rsp+1D0h+var_188], rbx
0x180003c76  test    r12, r12
0x180003c79  jnz     loc_180003FC1
0x180003c7f  mov     rax, [r15]
0x180003c82  mov     [rbx+28h], rax
0x180003c86  mov     rcx, [rsp+1D0h+var_188]
0x180003c8b  mov     eax, [rsp+1D0h+var_16C+0Ch]
0x180003c8f  mov     [rcx+20h], eax
0x180003c92  mov     rax, qword ptr [rbp+0D0h+var_4C+0Ch]
0x180003c99  mov     rcx, [rsp+1D0h+var_188]
0x180003c9e  mov     [rcx+3Ch], rax
0x180003ca2  mov     rcx, [rsp+1D0h+var_188]
0x180003ca7  mov     eax, [rsp+74h]
0x180003cab  mov     [rcx+24h], eax
0x180003cae  mov     rax, [rsp+1D0h+var_188]
0x180003cb3  mov     ecx, [rsp+1D0h+var_170]
0x180003cb7  mov     [rax+44h], ecx
0x180003cba  cmp     byte ptr [rsp+78h], 0
0x180003cbf  jz      short loc_180003CCA
0x180003cc1  mov     rax, [rsp+1D0h+var_188]
0x180003cc6  or      dword ptr [rax+48h], 1
0x180003cca  mov     rdx, [rsp+1D0h+TokenHandle]; SourceHandle
0x180003ccf  xor     r15d, r15d
0x180003cd2  cmp     rdx, [rbp+0D0h+var_150]
0x180003cd6  jnz     loc_180003E55
0x180003cdc  mov     r9, [rsp+1D0h+var_188]
0x180003ce1  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180003ce8  mov     [rsp+1D0h+Options], 2; Options
0x180003cf0  add     r9, 30h ; '0'; TargetHandle
0x180003cf4  mov     r8, rcx; TargetProcessHandle
0x180003cf7  mov     [rsp+1D0h+HandleAttributes], r15d; HandleAttributes
0x180003cfc  mov     dword ptr [rsp+1D0h+ReturnLength], r15d; DesiredAccess
0x180003d01  call    cs:__imp_NtDuplicateObject
0x180003d07  mov     ebx, eax
0x180003d09  test    eax, eax
0x180003d0b  js      loc_18000410E
0x180003d11  mov     rcx, [rbp+0D0h+var_150]; TokenHandle
0x180003d15  lea     rax, [rsp+1D0h+var_16C]
0x180003d1a  mov     r9d, 4; TokenInformationLength
0x180003d20  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x180003d25  lea     r8, [rsp+1D0h+var_174]; TokenInformation
0x180003d2a  mov     edx, 0Ch; TokenInformationClass
0x180003d2f  call    cs:__imp_NtQueryInformationToken
0x180003d35  mov     ebx, eax
0x180003d37  test    eax, eax
0x180003d39  js      loc_180004139
0x180003d3f  mov     rcx, [rsp+1D0h+var_188]
0x180003d44  xorps   xmm0, xmm0
0x180003d47  mov     eax, [rsp+1D0h+var_174]
0x180003d4b  mov     dl, 1; Wait
0x180003d4d  movups  [rbp+0D0h+var_108], xmm0
0x180003d51  mov     [rsp+1D0h+NewElement], 0
0x180003d56  mov     [rcx+38h], eax
0x180003d59  lea     rcx, [r14+70h]; Resource
0x180003d5d  mov     rax, [rsp+1D0h+var_188]
0x180003d62  mov     [rbp+0D0h+Buffer], rax
0x180003d66  movups  [rbp+0D0h+var_F8], xmm0
0x180003d6a  movups  [rbp+0D0h+var_E8], xmm0
0x180003d6e  movups  [rbp+0D0h+var_D8], xmm0
0x180003d72  movups  [rbp+0D0h+var_C8], xmm0
0x180003d76  movups  [rbp+0D0h+var_B8], xmm0
0x180003d7a  movups  [rbp+0D0h+var_A8], xmm0
0x180003d7e  movups  [rbp+0D0h+var_98], xmm0
0x180003d82  movups  [rbp+0D0h+var_88], xmm0
0x180003d86  call    cs:__imp_RtlAcquireResourceShared
0x180003d8c  lea     rdx, [rbp+0D0h+Buffer]; Buffer
0x180003d90  lea     rcx, [r14+8]; Table
0x180003d94  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180003d9a  mov     rbx, rax
0x180003d9d  test    rax, rax
0x180003da0  jz      loc_180003E68
0x180003da6  lock inc dword ptr [rax+8]
0x180003daa  mov     rdx, [rax]; struct basessp::_WST_CREDENTIAL *
0x180003dad  call    ?WSTReferenceCredential@BaseSSP@basessp@@QEAAXPEAU_WST_CREDENTIAL@2@@Z; basessp::BaseSSP::WSTReferenceCredential(basessp::_WST_CREDENTIAL *)
0x180003db2  lea     rcx, [r14+70h]; Resource
0x180003db6  call    cs:__imp_RtlReleaseResource
0x180003dbc  mov     rdx, [rsp+1D0h+var_188]; struct basessp::_WST_CREDENTIAL *
0x180003dc1  mov     rcx, r14; this
0x180003dc4  call    ?WSTDereferenceCredential@BaseSSP@basessp@@QEAAXPEAU_WST_CREDENTIAL@2@@Z; basessp::BaseSSP::WSTDereferenceCredential(basessp::_WST_CREDENTIAL *)
0x180003dc9  mov     rax, [rbx]
0x180003dcc  mov     [rsp+1D0h+var_188], rax
0x180003dd1  mov     rax, [rsp+1D0h+var_188]
0x180003dd6  mov     ebx, r15d
0x180003dd9  mov     [r13+0], rax
0x180003ddd  mov     rdx, [rsp+1D0h+var_188]; struct basessp::_WST_CREDENTIAL *
0x180003de2  mov     r15, [rsp+1D0h+var_30]
0x180003dea  mov     r13, [rsp+1D0h+var_20]
0x180003df2  mov     r12, [rsp+1D0h+var_18]
0x180003dfa  mov     rdi, [rsp+1C0h]
0x180003e02  mov     rsi, [rsp+1D0h+arg_0]
0x180003e0a  test    rdx, rdx
0x180003e0d  jz      short loc_180003E17
0x180003e0f  mov     rcx, r14; this
0x180003e12  call    ?WSTDereferenceCredential@BaseSSP@basessp@@QEAAXPEAU_WST_CREDENTIAL@2@@Z; basessp::BaseSSP::WSTDereferenceCredential(basessp::_WST_CREDENTIAL *)
0x180003e17  mov     rcx, [rsp+1D0h+TokenHandle]; Handle
0x180003e1c  mov     r14, [rsp+1D0h+var_28]
0x180003e24  test    rcx, rcx
0x180003e27  jz      short loc_180003E33
0x180003e29  cmp     rcx, [rbp+0D0h+var_150]
0x180003e2d  jnz     loc_180004210
0x180003e33  mov     eax, ebx
0x180003e35  mov     rcx, [rbp+0D0h+var_38]
0x180003e3c  xor     rcx, rsp; StackCookie
0x180003e3f  call    __security_check_cookie
0x180003e44  add     rsp, 1C8h
0x180003e4b  pop     rbx
0x180003e4c  pop     rbp
0x180003e4d  retn
0x180003e4e  mov     ebx, 0C0000017h
0x180003e53  jmp     short loc_180003DDD
0x180003e55  mov     rax, [rsp+1D0h+var_188]
0x180003e5a  mov     [rax+30h], rdx
0x180003e5e  mov     [rsp+1D0h+TokenHandle], r15
0x180003e63  jmp     loc_180003D11
0x180003e68  lea     rcx, [r14+70h]; Resource
0x180003e6c  call    cs:__imp_RtlConvertSharedToExclusive
0x180003e72  lea     r9, [rsp+1D0h+NewElement]; NewElement
0x180003e77  mov     r8d, 98h; BufferSize
0x180003e7d  lea     rdx, [rbp+0D0h+Buffer]; Buffer
0x180003e81  lea     rcx, [r14+8]; Table
0x180003e85  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180003e8b  mov     rbx, rax
0x180003e8e  test    rax, rax
0x180003e91  jz      loc_180004201
0x180003e97  lock inc dword ptr [rax+8]
0x180003e9b  mov     rdx, [rax]; struct basessp::_WST_CREDENTIAL *
0x180003e9e  call    ?WSTReferenceCredential@BaseSSP@basessp@@QEAAXPEAU_WST_CREDENTIAL@2@@Z; basessp::BaseSSP::WSTReferenceCredential(basessp::_WST_CREDENTIAL *)
0x180003ea3  cmp     [rsp+1D0h+NewElement], 0
0x180003ea8  jz      loc_180003DB2
0x180003eae  mov     rcx, [rbx]
0x180003eb1  mov     dword ptr [rcx+0Ch], 1
0x180003eb8  mov     rcx, [rbx]
0x180003ebb  movups  xmm0, xmmword ptr [rcx]
0x180003ebe  movups  xmmword ptr [rbx+10h], xmm0
0x180003ec2  movups  xmm1, xmmword ptr [rcx+10h]
0x180003ec6  movups  xmmword ptr [rbx+20h], xmm1
0x180003eca  movups  xmm0, xmmword ptr [rcx+20h]
0x180003ece  movups  xmmword ptr [rbx+30h], xmm0
0x180003ed2  movups  xmm1, xmmword ptr [rcx+30h]
0x180003ed6  movups  xmmword ptr [rbx+40h], xmm1
0x180003eda  movups  xmm0, xmmword ptr [rcx+40h]
0x180003ede  movups  xmmword ptr [rbx+50h], xmm0
0x180003ee2  movups  xmm1, xmmword ptr [rcx+50h]
0x180003ee6  movups  xmmword ptr [rbx+60h], xmm1
0x180003eea  movups  xmm0, xmmword ptr [rcx+60h]
0x180003eee  movups  xmmword ptr [rbx+70h], xmm0
0x180003ef2  movups  xmm1, xmmword ptr [rcx+70h]
0x180003ef6  movups  xmmword ptr [rbx+80h], xmm1
0x180003efd  movsd   xmm0, qword ptr [rcx+80h]
0x180003f05  lea     rcx, [r14+70h]; Resource
0x180003f09  movsd   qword ptr [rbx+90h], xmm0
0x180003f11  call    cs:__imp_RtlReleaseResource
0x180003f17  jmp     loc_180003DD1
0x180003f1c  cmp     eax, [rsp+1D0h+var_16C+4]
0x180003f20  jnz     short loc_180003F30
0x180003f22  mov     eax, [rsp+1D0h+var_16C+8]
0x180003f26  cmp     [r15+4], eax
0x180003f2a  jz      loc_180003B47
0x180003f30  cmp     byte ptr [rsp+78h], 0
0x180003f35  jz      loc_1800040D9
0x180003f3b  mov     rax, [r14+0F0h]
0x180003f42  lea     rdx, [rsp+1D0h+TokenHandle]
0x180003f47  mov     rcx, r15
0x180003f4a  mov     rax, [rax+170h]
0x180003f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f56  mov     ebx, eax
0x180003f58  test    eax, eax
0x180003f5a  jns     loc_180003B47
0x180003f60  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f67  lea     rax, WPP_GLOBAL_Control
0x180003f6e  cmp     rcx, rax
0x180003f71  jz      loc_180003DDD
  ... truncated ...
```
