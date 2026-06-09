# sub_18008EAAC

- ea: `0x18008eaac`
- end: `0x18008effd`
- name: `sub_18008EAAC`
- size: `1361`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18008ea90`

## callees

- `0x180059ab4`
- `0x180059eac`
- `0x18005ae04`
- `0x18005e330`
- `0x18005ef34`
- `0x180070420`
- `0x180070474`
- `0x180079880`
- `0x18007e95c`
- `0x180088b78`
- `0x18008b914`
- `0x18008dc00`
- `0x18008eaac`
- `0x180207168`
- `0x1802b9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008efd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008efd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008eae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008eae5`

## string_xrefs

- `0x18008eaf8`: `CHEIFIdentityTransformationImage::OnDecodeCompleted`
- `0x18008eb19`: `CHEIFIdentityTransformationImage::OnDecodeCompleted`
- `0x18008ec2b`: `CHEIFIdentityTransformationImage::OnDecodeCompleted`
- `0x18008eceb`: `CHEIFIdentityTransformationImage::OnDecodeCompleted`
- `0x18008ef49`: `CHEIFIdentityTransformationImage::OnDecodeCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall sub_18008EAAC(unsigned __int64 a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  unsigned int *v5; // r14
  __int64 v6; // rdi
  signed int v7; // edi
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, __int64, IMFSample **, IMFMediaType **, __int64 *); // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  __int64 v36; // [rsp+40h] [rbp-59h] BYREF
  __int64 v37; // [rsp+48h] [rbp-51h] BYREF
  IMFSample *v38; // [rsp+50h] [rbp-49h] BYREF
  IMFMediaType *v39; // [rsp+58h] [rbp-41h] BYREF
  IUnknown *v40; // [rsp+60h] [rbp-39h] BYREF
  IMFSample *v41; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v42[3]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v43[104]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v44; // [rsp+100h] [rbp+67h] BYREF
  __int64 v45; // [rsp+108h] [rbp+6Fh] BYREF
  IMFSample *v46; // [rsp+110h] [rbp+77h] BYREF
  IMFMediaType *v47; // [rsp+118h] [rbp+7Fh] BYREF

  v42[1] = -2;
  v40 = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  v42[2] = a1 + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  sub_180059AB4(&v44, "CHEIFIdentityTransformationImage::OnDecodeCompleted", 178);
  v5 = (unsigned int *)(a1 + 16);
  sub_18005E330(
    v43,
    (a1 + 16) & ((unsigned __int128)-(__int128)a1 >> 64),
    "CHEIFIdentityTransformationImage::OnDecodeCompleted");
  v6 = **(_QWORD **)(a1 + 176);
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 56LL))(a2) == v6 )
  {
    v47 = 0;
    v46 = 0;
    v36 = 0;
    v8 = *(_QWORD *)(a1 + 200);
    v9 = *(__int64 (__fastcall **)(__int64, __int64, IMFSample **, IMFMediaType **, __int64 *))(*(_QWORD *)v8 + 264LL);
    sub_180070474(&v36);
    sub_180070474(&v47);
    sub_180070474(&v46);
    v7 = v9(v8, a2, &v46, &v47, &v36);
    if ( v7 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 29, &unk_1805D3748, *v5, v7);
      }
      v13 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v13 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v14 = sub_18005AE04(v13, v10, v11, v12);
        if ( *(_DWORD *)(v14 + 1996) != v7 )
          sub_180207168(v14, "CHEIFIdentityTransformationImage::OnDecodeCompleted", 190, (unsigned int)v7);
      }
      goto LABEL_59;
    }
    v37 = 0;
    v45 = 0;
    sub_180070474(&v37);
    v7 = sub_180088B78(*(_QWORD *)(a1 + 112), *(_QWORD *)(*(_QWORD *)(a1 + 176) + 16LL), &v37);
    if ( v7 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 30, &unk_1805D3748, *v5, v7);
      }
      v18 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v18 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v18 + 8) )
        goto LABEL_58;
      v19 = sub_18005AE04(v18, v15, v16, v17);
      if ( *(_DWORD *)(v19 + 1996) == v7 )
        goto LABEL_58;
      v20 = 203;
      goto LABEL_23;
    }
    sub_180070474(&v45);
    v7 = sub_180088B78(v36, v37, &v45);
    if ( v7 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 31, &unk_1805D3748, *v5, v7);
      }
      v24 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v24 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v24 + 8) )
        goto LABEL_58;
      v19 = sub_18005AE04(v24, v21, v22, v23);
      if ( *(_DWORD *)(v19 + 1996) == v7 )
        goto LABEL_58;
      v20 = 207;
LABEL_23:
      sub_180207168(v19, "CHEIFIdentityTransformationImage::OnDecodeCompleted", v20, (unsigned int)v7);
LABEL_58:
      sub_180070474(&v45);
      sub_180070474(&v37);
LABEL_59:
      sub_180070474(&v36);
      sub_180070474(&v46);
      sub_180070474(&v47);
      sub_18008B914(
        v7,
        v40,
        *(IMFAsyncCallback **)(*(_QWORD *)(a1 + 176) + 8LL),
        *(IUnknown **)(*(_QWORD *)(a1 + 176) + 24LL));
      goto LABEL_60;
    }
    v39 = v47;
    sub_180070420(&v39);
    v38 = v46;
    sub_180070420(&v38);
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 176) + 44LL) )
    {
      sub_180070474(&v38);
      sub_180070474(&v39);
      v7 = sub_18007E95C(a1, (__int64)v47, (__int64)v46, v45, *(_QWORD *)(*(_QWORD *)(a1 + 176) + 32LL), &v39, &v38);
      if ( v7 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 32, &unk_1805D3748, *v5, v7);
        }
        v28 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v28 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v28 + 8) )
          goto LABEL_57;
        v29 = sub_18005AE04(v28, v25, v26, v27);
        if ( *(_DWORD *)(v29 + 1996) == v7 )
          goto LABEL_57;
        v30 = 220;
LABEL_56:
        sub_180207168(v29, "CHEIFIdentityTransformationImage::OnDecodeCompleted", v30, (unsigned int)v7);
LABEL_57:
        sub_180070474(&v38);
        sub_180070474(&v39);
        goto LABEL_58;
      }
      sub_180070474(&v45);
    }
    v44 = v45;
    v41 = v38;
    v42[0] = v39;
    v7 = sub_18008DC00(&v40, v42, &v41, &v44);
    if ( v7 >= 0 )
      goto LABEL_57;
    if ( RequestContext != &RequestContext
      && (*((_BYTE *)RequestContext + 28) & 1) != 0
      && *((_BYTE *)RequestContext + 25) >= 4u )
    {
      sub_180079880(*((_QWORD *)RequestContext + 2), 33, &unk_1805D3748, *v5, v7);
    }
    v34 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v34 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( !*((_BYTE *)v34 + 8) )
      goto LABEL_57;
    v29 = sub_18005AE04(v34, v31, v32, v33);
    if ( *(_DWORD *)(v29 + 1996) == v7 )
      goto LABEL_57;
    v30 = 226;
    goto LABEL_56;
  }
  v7 = 0;
LABEL_60:
  sub_18005EF34(v43);
  sub_180059EAC(&v44);
  LeaveCriticalSection(v4);
  sub_180070474(&v40);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18008eaac  push    rbp
0x18008eaae  push    rbx
0x18008eaaf  push    rsi
0x18008eab0  push    rdi
0x18008eab1  push    r12
0x18008eab3  push    r13
0x18008eab5  push    r14
0x18008eab7  push    r15
0x18008eab9  lea     rbp, [rsp-1Fh]
0x18008eabe  sub     rsp, 0B8h
0x18008eac5  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18008eacd  mov     r12, rdx
0x18008ead0  mov     r15, rcx
0x18008ead3  xor     r13d, r13d
0x18008ead6  mov     [rbp+57h+var_90], r13
0x18008eada  lea     rbx, [rcx+18h]
0x18008eade  mov     [rbp+57h+var_70], rbx
0x18008eae2  mov     rcx, rbx; lpCriticalSection
0x18008eae5  call    cs:EnterCriticalSection
0x18008eaec  nop     dword ptr [rax+rax+00h]
0x18008eaf1  nop
0x18008eaf2  mov     r8d, 0B2h
0x18008eaf8  lea     rdx, aCheifidentityt_3; "CHEIFIdentityTransformationImage::OnDec"...
0x18008eaff  lea     rcx, [rbp+57h+arg_0]
0x18008eb03  call    sub_180059AB4
0x18008eb08  nop
0x18008eb09  lea     r14, [r15+10h]
0x18008eb0d  mov     rax, r15
0x18008eb10  neg     rax
0x18008eb13  sbb     rdx, rdx
0x18008eb16  and     rdx, r14
0x18008eb19  lea     r8, aCheifidentityt_3; "CHEIFIdentityTransformationImage::OnDec"...
0x18008eb20  lea     rcx, [rbp+57h+var_68]
0x18008eb24  call    sub_18005E330
0x18008eb29  nop
0x18008eb2a  mov     rax, [r15+0B0h]
0x18008eb31  mov     rdi, [rax]
0x18008eb34  mov     rax, [r12]
0x18008eb38  mov     rcx, r12
0x18008eb3b  mov     rax, [rax+38h]
0x18008eb3f  call    j__guard_dispatch_icall
0x18008eb44  cmp     rax, rdi
0x18008eb47  jz      short loc_18008EB51
0x18008eb49  mov     edi, r13d
0x18008eb4c  jmp     loc_18008EFB9
0x18008eb51  mov     [rbp+57h+arg_18], r13
0x18008eb55  mov     [rbp+57h+arg_10], r13
0x18008eb59  mov     [rbp+57h+var_B0], r13
0x18008eb5d  mov     rsi, [r15+0C8h]
0x18008eb64  mov     rax, [rsi]
0x18008eb67  mov     rdi, [rax+108h]
0x18008eb6e  lea     rcx, [rbp+57h+var_B0]
0x18008eb72  call    sub_180070474
0x18008eb77  lea     rcx, [rbp+57h+arg_18]
0x18008eb7b  call    sub_180070474
0x18008eb80  lea     rcx, [rbp+57h+arg_10]
0x18008eb84  call    sub_180070474
0x18008eb89  lea     rax, [rbp+57h+var_B0]
0x18008eb8d  mov     [rsp+0F0h+var_D0], rax
0x18008eb92  lea     r9, [rbp+57h+arg_18]
0x18008eb96  lea     r8, [rbp+57h+arg_10]
0x18008eb9a  mov     rdx, r12
0x18008eb9d  mov     rcx, rsi
0x18008eba0  mov     rax, rdi
0x18008eba3  call    j__guard_dispatch_icall
0x18008eba8  mov     edi, eax
0x18008ebaa  test    eax, eax
0x18008ebac  jns     loc_18008EC3F
0x18008ebb2  lea     rax, RequestContext
0x18008ebb9  mov     rcx, cs:RequestContext
0x18008ebc0  cmp     rcx, rax
0x18008ebc3  jz      short loc_18008EBED
0x18008ebc5  test    byte ptr [rcx+1Ch], 1
0x18008ebc9  jz      short loc_18008EBED
0x18008ebcb  cmp     byte ptr [rcx+19h], 4
0x18008ebcf  jb      short loc_18008EBED
0x18008ebd1  mov     edx, 1Dh
0x18008ebd6  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18008ebda  mov     r9d, [r14]
0x18008ebdd  lea     r8, unk_1805D3748
0x18008ebe4  mov     rcx, [rcx+10h]
0x18008ebe8  call    sub_180079880
0x18008ebed  mov     rcx, cs:qword_180685260
0x18008ebf4  test    rcx, rcx
0x18008ebf7  jnz     short loc_18008EC07
0x18008ebf9  lea     rcx, qword_180684620
0x18008ec00  mov     cs:qword_180685260, rcx
0x18008ec07  cmp     [rcx+8], r13b
0x18008ec0b  jz      loc_18008EF81
0x18008ec11  call    sub_18005AE04
0x18008ec16  cmp     [rax+7CCh], edi
0x18008ec1c  jz      loc_18008EF81
0x18008ec22  mov     r9d, edi
0x18008ec25  mov     r8d, 0BEh
0x18008ec2b  lea     rdx, aCheifidentityt_3; "CHEIFIdentityTransformationImage::OnDec"...
0x18008ec32  mov     rcx, rax
0x18008ec35  call    sub_180207168
0x18008ec3a  jmp     loc_18008EF81
0x18008ec3f  mov     [rbp+57h+var_A8], r13
0x18008ec43  mov     [rbp+57h+arg_8], r13
0x18008ec47  lea     rcx, [rbp+57h+var_A8]
0x18008ec4b  call    sub_180070474
0x18008ec50  mov     rdx, [r15+0B0h]
0x18008ec57  lea     r8, [rbp+57h+var_A8]
0x18008ec5b  mov     rdx, [rdx+10h]
0x18008ec5f  mov     rcx, [r15+70h]
0x18008ec63  call    sub_180088B78
0x18008ec68  mov     edi, eax
0x18008ec6a  test    eax, eax
0x18008ec6c  jns     loc_18008ECFF
0x18008ec72  lea     rax, RequestContext
0x18008ec79  mov     rcx, cs:RequestContext
0x18008ec80  cmp     rcx, rax
0x18008ec83  jz      short loc_18008ECAD
0x18008ec85  test    byte ptr [rcx+1Ch], 1
0x18008ec89  jz      short loc_18008ECAD
0x18008ec8b  cmp     byte ptr [rcx+19h], 4
0x18008ec8f  jb      short loc_18008ECAD
0x18008ec91  mov     edx, 1Eh
0x18008ec96  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18008ec9a  mov     r9d, [r14]
0x18008ec9d  lea     r8, unk_1805D3748
0x18008eca4  mov     rcx, [rcx+10h]
0x18008eca8  call    sub_180079880
0x18008ecad  mov     rcx, cs:qword_180685260
0x18008ecb4  test    rcx, rcx
0x18008ecb7  jnz     short loc_18008ECC7
0x18008ecb9  lea     rcx, qword_180684620
0x18008ecc0  mov     cs:qword_180685260, rcx
0x18008ecc7  cmp     [rcx+8], r13b
0x18008eccb  jz      loc_18008EF6D
0x18008ecd1  call    sub_18005AE04
0x18008ecd6  cmp     [rax+7CCh], edi
0x18008ecdc  jz      loc_18008EF6D
0x18008ece2  mov     r8d, 0CBh
0x18008ece8  mov     r9d, edi
0x18008eceb  lea     rdx, aCheifidentityt_3; "CHEIFIdentityTransformationImage::OnDec"...
0x18008ecf2  mov     rcx, rax
0x18008ecf5  call    sub_180207168
0x18008ecfa  jmp     loc_18008EF6D
0x18008ecff  lea     rcx, [rbp+57h+arg_8]
0x18008ed03  call    sub_180070474
0x18008ed08  lea     r8, [rbp+57h+arg_8]
0x18008ed0c  mov     rdx, [rbp+57h+var_A8]
0x18008ed10  mov     rcx, [rbp+57h+var_B0]
0x18008ed14  call    sub_180088B78
0x18008ed19  mov     edi, eax
0x18008ed1b  test    eax, eax
0x18008ed1d  jns     short loc_18008ED9A
0x18008ed1f  lea     rax, RequestContext
0x18008ed26  mov     rcx, cs:RequestContext
0x18008ed2d  cmp     rcx, rax
0x18008ed30  jz      short loc_18008ED5A
0x18008ed32  test    byte ptr [rcx+1Ch], 1
0x18008ed36  jz      short loc_18008ED5A
0x18008ed38  cmp     byte ptr [rcx+19h], 4
0x18008ed3c  jb      short loc_18008ED5A
0x18008ed3e  mov     edx, 1Fh
0x18008ed43  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18008ed47  mov     r9d, [r14]
0x18008ed4a  lea     r8, unk_1805D3748
0x18008ed51  mov     rcx, [rcx+10h]
0x18008ed55  call    sub_180079880
0x18008ed5a  mov     rcx, cs:qword_180685260
0x18008ed61  test    rcx, rcx
0x18008ed64  jnz     short loc_18008ED74
0x18008ed66  lea     rcx, qword_180684620
0x18008ed6d  mov     cs:qword_180685260, rcx
0x18008ed74  cmp     [rcx+8], r13b
0x18008ed78  jz      loc_18008EF6D
0x18008ed7e  call    sub_18005AE04
0x18008ed83  cmp     [rax+7CCh], edi
0x18008ed89  jz      loc_18008EF6D
0x18008ed8f  mov     r8d, 0CFh
0x18008ed95  jmp     loc_18008ECE8
0x18008ed9a  mov     rax, [rbp+57h+arg_18]
0x18008ed9e  mov     [rbp+57h+var_98], rax
0x18008eda2  lea     rcx, [rbp+57h+var_98]
0x18008eda6  call    sub_180070420
0x18008edab  nop
0x18008edac  mov     rax, [rbp+57h+arg_10]
0x18008edb0  mov     [rbp+57h+var_A0], rax
0x18008edb4  lea     rcx, [rbp+57h+var_A0]
0x18008edb8  call    sub_180070420
0x18008edbd  nop
0x18008edbe  mov     rax, [r15+0B0h]
0x18008edc5  cmp     [rax+2Ch], r13b
0x18008edc9  jz      loc_18008EEA1
0x18008edcf  lea     rcx, [rbp+57h+var_A0]
0x18008edd3  call    sub_180070474
0x18008edd8  lea     rcx, [rbp+57h+var_98]
0x18008eddc  call    sub_180070474
0x18008ede1  mov     rax, [r15+0B0h]
0x18008ede8  lea     rcx, [rbp+57h+var_A0]
0x18008edec  mov     [rsp+0F0h+var_C0], rcx
0x18008edf1  lea     rcx, [rbp+57h+var_98]
0x18008edf5  mov     [rsp+0F0h+var_C8], rcx
0x18008edfa  mov     rax, [rax+20h]
0x18008edfe  mov     [rsp+0F0h+var_D0], rax
0x18008ee03  mov     r9, [rbp+57h+arg_8]
0x18008ee07  mov     r8, [rbp+57h+arg_10]
0x18008ee0b  mov     rdx, [rbp+57h+arg_18]
0x18008ee0f  mov     rcx, r15
0x18008ee12  call    sub_18007E95C
0x18008ee17  mov     edi, eax
0x18008ee19  test    eax, eax
0x18008ee1b  jns     short loc_18008EE98
0x18008ee1d  lea     rax, RequestContext
0x18008ee24  mov     rcx, cs:RequestContext
0x18008ee2b  cmp     rcx, rax
0x18008ee2e  jz      short loc_18008EE58
0x18008ee30  test    byte ptr [rcx+1Ch], 1
0x18008ee34  jz      short loc_18008EE58
0x18008ee36  cmp     byte ptr [rcx+19h], 4
0x18008ee3a  jb      short loc_18008EE58
0x18008ee3c  mov     edx, 20h ; ' '
0x18008ee41  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18008ee45  mov     r9d, [r14]
0x18008ee48  lea     r8, unk_1805D3748
0x18008ee4f  mov     rcx, [rcx+10h]
0x18008ee53  call    sub_180079880
0x18008ee58  mov     rcx, cs:qword_180685260
0x18008ee5f  test    rcx, rcx
0x18008ee62  jnz     short loc_18008EE72
0x18008ee64  lea     rcx, qword_180684620
0x18008ee6b  mov     cs:qword_180685260, rcx
0x18008ee72  cmp     [rcx+8], r13b
0x18008ee76  jz      loc_18008EF59
0x18008ee7c  call    sub_18005AE04
0x18008ee81  cmp     [rax+7CCh], edi
0x18008ee87  jz      loc_18008EF59
0x18008ee8d  mov     r8d, 0DCh
0x18008ee93  jmp     loc_18008EF46
0x18008ee98  lea     rcx, [rbp+57h+arg_8]
0x18008ee9c  call    sub_180070474
0x18008eea1  mov     rax, [rbp+57h+arg_8]
0x18008eea5  mov     [rbp+57h+arg_0], rax
0x18008eea9  mov     rax, [rbp+57h+var_A0]
0x18008eead  mov     [rbp+57h+var_88], rax
0x18008eeb1  mov     rax, [rbp+57h+var_98]
0x18008eeb5  mov     [rbp+57h+var_80], rax
0x18008eeb9  lea     r9, [rbp+57h+arg_0]
0x18008eebd  lea     r8, [rbp+57h+var_88]
0x18008eec1  lea     rdx, [rbp+57h+var_80]
0x18008eec5  lea     rcx, [rbp+57h+var_90]
0x18008eec9  call    sub_18008DC00
0x18008eece  mov     edi, eax
0x18008eed0  test    eax, eax
0x18008eed2  jns     loc_18008EF59
0x18008eed8  lea     rax, RequestContext
0x18008eedf  mov     rcx, cs:RequestContext
0x18008eee6  cmp     rcx, rax
0x18008eee9  jz      short loc_18008EF13
0x18008eeeb  test    byte ptr [rcx+1Ch], 1
0x18008eeef  jz      short loc_18008EF13
0x18008eef1  cmp     byte ptr [rcx+19h], 4
0x18008eef5  jb      short loc_18008EF13
0x18008eef7  mov     edx, 21h ; '!'
0x18008eefc  mov     dword ptr [rsp+0F0h+var_D0], edi
0x18008ef00  mov     r9d, [r14]
0x18008ef03  lea     r8, unk_1805D3748
0x18008ef0a  mov     rcx, [rcx+10h]
0x18008ef0e  call    sub_180079880
0x18008ef13  mov     rcx, cs:qword_180685260
0x18008ef1a  test    rcx, rcx
0x18008ef1d  jnz     short loc_18008EF2D
0x18008ef1f  lea     rcx, qword_180684620
0x18008ef26  mov     cs:qword_180685260, rcx
0x18008ef2d  cmp     [rcx+8], r13b
0x18008ef31  jz      short loc_18008EF59
0x18008ef33  call    sub_18005AE04
0x18008ef38  cmp     [rax+7CCh], edi
0x18008ef3e  jz      short loc_18008EF59
0x18008ef40  mov     r8d, 0E2h
0x18008ef46  mov     r9d, edi
0x18008ef49  lea     rdx, aCheifidentityt_3; "CHEIFIdentityTransformationImage::OnDec"...
0x18008ef50  mov     rcx, rax
0x18008ef53  call    sub_180207168
0x18008ef58  nop
0x18008ef59  lea     rcx, [rbp+57h+var_A0]
0x18008ef5d  call    sub_180070474
0x18008ef62  nop
0x18008ef63  lea     rcx, [rbp+57h+var_98]
0x18008ef67  call    sub_180070474
0x18008ef6c  nop
0x18008ef6d  lea     rcx, [rbp+57h+arg_8]
0x18008ef71  call    sub_180070474
0x18008ef76  nop
0x18008ef77  lea     rcx, [rbp+57h+var_A8]
0x18008ef7b  call    sub_180070474
0x18008ef80  nop
0x18008ef81  lea     rcx, [rbp+57h+var_B0]
0x18008ef85  call    sub_180070474
0x18008ef8a  nop
0x18008ef8b  lea     rcx, [rbp+57h+arg_10]
0x18008ef8f  call    sub_180070474
0x18008ef94  nop
0x18008ef95  lea     rcx, [rbp+57h+arg_18]
0x18008ef99  call    sub_180070474
0x18008ef9e  mov     r8, [r15+0B0h]
  ... truncated ...
```
