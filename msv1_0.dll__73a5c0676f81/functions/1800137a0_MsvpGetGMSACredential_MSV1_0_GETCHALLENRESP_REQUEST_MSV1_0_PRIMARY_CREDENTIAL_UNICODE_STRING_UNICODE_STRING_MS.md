# MsvpGetGMSACredential(_MSV1_0_GETCHALLENRESP_REQUEST *,_MSV1_0_PRIMARY_CREDENTIAL *,_UNICODE_STRING,_UNICODE_STRING,_MSV1_0_PRIMARY_CREDENTIAL *,_MSV1_0_PRIMARY_CREDENTIAL *)

- ea: `0x1800137a0`
- end: `0x180013b22`
- name: `?MsvpGetGMSACredential@@YAJPEAU_MSV1_0_GETCHALLENRESP_REQUEST@@PEAU_MSV1_0_PRIMARY_CREDENTIAL@@U_UNICODE_STRING@@211@Z`
- size: `898`
- prototype: `int(struct _MSV1_0_GETCHALLENRESP_REQUEST *, struct _MSV1_0_PRIMARY_CREDENTIAL *, struct _UNICODE_STRING *__struct_ptr, struct _UNICODE_STRING *__struct_ptr, struct _MSV1_0_PRIMARY_CREDENTIAL *, struct _MSV1_0_PRIMARY_CREDENTIAL *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180024c00`

## callees

- `0x180006c50`
- `0x1800137a0`
- `0x1800186d4`
- `0x180019030`
- `0x18002ee7c`
- `0x180040124`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180013ad6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180013ad6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013ac0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013ac0`

## pseudocode

```c
__int64 __fastcall MsvpGetGMSACredential(
        struct _MSV1_0_GETCHALLENRESP_REQUEST *a1,
        __m128i *a2,
        __m128i *a3,
        struct _UNICODE_STRING *a4,
        struct _MSV1_0_PRIMARY_CREDENTIAL *a5,
        struct _MSV1_0_PRIMARY_CREDENTIAL *a6)
{
  struct _MSV1_0_PRIMARY_CREDENTIAL *v6; // rbx
  int v11; // esi
  struct _MSV1_0_PRIMARY_CREDENTIAL *v12; // rax
  __int64 v13; // rcx
  __int128 v14; // xmm0
  int v15; // edi
  _BYTE *v16; // rcx
  _BYTE *v17; // rcx
  int v19; // ecx
  struct _UNICODE_STRING v20; // xmm1
  _WORD *v21; // xmm0_8
  __m128i v22; // xmm0
  __int64 v23; // rax
  __int64 v24; // rax
  _WORD *v25; // xmm1_8
  __int64 v26; // r8
  __int64 v27; // r9
  int CredEncryptionTypeForUser; // edi
  LONG v29; // eax
  __int128 *v30; // rcx
  int v31; // [rsp+48h] [rbp-59h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-51h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-49h] BYREF
  struct _UNICODE_STRING v34; // [rsp+60h] [rbp-41h] BYREF
  __int128 v35; // [rsp+70h] [rbp-31h] BYREF
  __int128 v36; // [rsp+80h] [rbp-21h] BYREF
  __m128i v37; // [rsp+90h] [rbp-11h] BYREF
  __int128 v38; // [rsp+A0h] [rbp-1h] BYREF
  __int128 v39; // [rsp+B0h] [rbp+Fh]

  v6 = a5;
  v11 = 0;
  v38 = 0;
  SystemTimeAsFileTime = 0;
  v39 = 0;
  FileTime1 = 0;
  v31 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  if ( !NtLmGlobalDomainJoined )
    goto LABEL_2;
  v15 = (*(__int64 (__fastcall **)(_QWORD, char *, int *))(**((_QWORD **)a5 + 4) + 72LL))(
          *((_QWORD *)a5 + 4),
          (char *)a5 + 32,
          &v31);
  if ( v15 < 0 )
    goto LABEL_6;
  if ( !NtLmGlobalDomainJoined || !v31 )
  {
LABEL_2:
    v12 = a6;
    v13 = 3;
    do
    {
      v12 = (struct _MSV1_0_PRIMARY_CREDENTIAL *)((char *)v12 + 128);
      v14 = *(_OWORD *)v6;
      v6 = (struct _MSV1_0_PRIMARY_CREDENTIAL *)((char *)v6 + 128);
      *((_OWORD *)v12 - 8) = v14;
      *((_OWORD *)v12 - 7) = *((_OWORD *)v6 - 7);
      *((_OWORD *)v12 - 6) = *((_OWORD *)v6 - 6);
      *((_OWORD *)v12 - 5) = *((_OWORD *)v6 - 5);
      *((_OWORD *)v12 - 4) = *((_OWORD *)v6 - 4);
      *((_OWORD *)v12 - 3) = *((_OWORD *)v6 - 3);
      *((_OWORD *)v12 - 2) = *((_OWORD *)v6 - 2);
      *((_OWORD *)v12 - 1) = *((_OWORD *)v6 - 1);
      --v13;
    }
    while ( v13 );
LABEL_4:
    v15 = 0;
LABEL_5:
    if ( v11 && v34.Buffer )
      NtLmFree(v34.Buffer);
    goto LABEL_6;
  }
  if ( (*((_BYTE *)a1 + 4) & 1) != 0 )
  {
    v19 = 1;
    goto LABEL_14;
  }
  v15 = ((__int64 (__fastcall *)(__int128 *))LsaFunctions->GetClientInfo)(&v38);
  if ( v15 >= 0 )
  {
    v19 = 0;
    if ( !(_BYTE)v39 && (_QWORD)v38 != 996 )
    {
      v15 = -1073741790;
      goto LABEL_6;
    }
LABEL_14:
    v20 = *a4;
    v37 = *a3;
    v21 = (_WORD *)_mm_srli_si128(v37, 8).m128i_u64[0];
    v34 = v20;
    if ( !v21 || !*v21 )
    {
      if ( v19 )
        v22 = a2[1];
      else
        v22 = *(__m128i *)((char *)a1 + 40);
      v37 = v22;
    }
    v25 = (_WORD *)_mm_srli_si128((__m128i)v20, 8).m128i_u64[0];
    if ( !v25 || !*v25 )
    {
      if ( v19 )
      {
        v15 = NlpMapLogonDomain(&v34, (struct _UNICODE_STRING *)a2);
        if ( v15 < 0 )
          goto LABEL_6;
        v11 = 1;
      }
      else
      {
        v34 = *(struct _UNICODE_STRING *)((char *)a1 + 56);
      }
    }
    v15 = ((__int64 (__fastcall *)(__m128i *, struct _UNICODE_STRING *, _QWORD, _QWORD, __int128 *, __int128 *, FILETIME *))qword_1800883D0)(
            &v37,
            &v34,
            0,
            0,
            &v35,
            &v36,
            &FileTime1);
    if ( v15 < 0 )
      goto LABEL_5;
    CredEncryptionTypeForUser = NlpGetCredEncryptionTypeForUser(0, (char *)a1 + 8, v26, v27);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v29 = CompareFileTime(&FileTime1, &SystemTimeAsFileTime);
    v30 = &v36;
    if ( v29 <= 0 )
      v30 = &v35;
    v15 = NlpPutOwfsInPrimaryCredential((_DWORD)v30, 0, 0, CredEncryptionTypeForUser, (__int64)a6 + 32);
    if ( v15 < 0 )
      goto LABEL_5;
    goto LABEL_4;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids,
      (unsigned int)v15);
LABEL_6:
  v16 = (_BYTE *)*((_QWORD *)&v35 + 1);
  if ( *((_QWORD *)&v35 + 1) )
  {
    v23 = (unsigned __int16)v35;
    if ( (_WORD)v35 )
    {
      do
      {
        *v16++ = 0;
        --v23;
      }
      while ( v23 );
    }
    ((void (*)(void))qword_180088240)();
  }
  v17 = (_BYTE *)*((_QWORD *)&v36 + 1);
  if ( *((_QWORD *)&v36 + 1) )
  {
    v24 = (unsigned __int16)v36;
    if ( (_WORD)v36 )
    {
      do
      {
        *v17++ = 0;
        --v24;
      }
      while ( v24 );
    }
    ((void (*)(void))qword_180088240)();
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800137a0  mov     rax, rsp
0x1800137a3  push    rbp
0x1800137a4  push    rdi
0x1800137a5  lea     rbp, [rax-4Fh]
0x1800137a9  sub     rsp, 0D8h
0x1800137b0  mov     [rax+8], rbx
0x1800137b4  xorps   xmm0, xmm0
0x1800137b7  mov     rbx, [rbp+47h+arg_20]
0x1800137bb  xorps   xmm1, xmm1
0x1800137be  mov     [rax+10h], rsi
0x1800137c2  mov     [rax+18h], r12
0x1800137c6  mov     r12, r9
0x1800137c9  mov     [rax-18h], r13
0x1800137cd  mov     r13, r8
0x1800137d0  mov     [rax-20h], r14
0x1800137d4  mov     r14, rcx
0x1800137d7  mov     [rax-28h], r15
0x1800137db  mov     r15, rdx
0x1800137de  xor     eax, eax
0x1800137e0  cmp     cs:NtLmGlobalDomainJoined, al
0x1800137e6  mov     esi, eax
0x1800137e8  movups  [rbp+47h+var_48], xmm0
0x1800137ec  mov     qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800137f0  movups  [rbp+47h+var_38], xmm0
0x1800137f4  mov     qword ptr [rbp+47h+FileTime1.dwLowDateTime], rax
0x1800137f8  mov     [rbp+47h+var_A0], eax
0x1800137fb  movups  [rbp+47h+var_58], xmm0
0x1800137ff  movups  xmmword ptr [rbp+47h+var_88.Length], xmm1
0x180013803  movups  [rbp+47h+var_78], xmm0
0x180013807  movups  [rbp+47h+var_68], xmm1
0x18001380b  jnz     loc_1800138CD
0x180013811  mov     rax, [rbp+47h+arg_28]
0x180013815  mov     ecx, 3
0x18001381a  lea     rax, [rax+80h]
0x180013821  movups  xmm0, xmmword ptr [rbx]
0x180013824  lea     rbx, [rbx+80h]
0x18001382b  movups  xmmword ptr [rax-80h], xmm0
0x18001382f  movups  xmm1, xmmword ptr [rbx-70h]
0x180013833  movups  xmmword ptr [rax-70h], xmm1
0x180013837  movups  xmm0, xmmword ptr [rbx-60h]
0x18001383b  movups  xmmword ptr [rax-60h], xmm0
0x18001383f  movups  xmm1, xmmword ptr [rbx-50h]
0x180013843  movups  xmmword ptr [rax-50h], xmm1
0x180013847  movups  xmm0, xmmword ptr [rbx-40h]
0x18001384b  movups  xmmword ptr [rax-40h], xmm0
0x18001384f  movups  xmm1, xmmword ptr [rbx-30h]
0x180013853  movups  xmmword ptr [rax-30h], xmm1
0x180013857  movups  xmm0, xmmword ptr [rbx-20h]
0x18001385b  movups  xmmword ptr [rax-20h], xmm0
0x18001385f  movups  xmm1, xmmword ptr [rbx-10h]
0x180013863  movups  xmmword ptr [rax-10h], xmm1
0x180013867  sub     rcx, 1
0x18001386b  jnz     short loc_18001381A
0x18001386d  xor     edi, edi
0x18001386f  test    esi, esi
0x180013871  jnz     loc_180013B0B
0x180013877  mov     rcx, qword ptr [rbp+47h+var_78+8]
0x18001387b  mov     r15, [rsp+0E0h+var_20]
0x180013883  mov     r14, [rsp+0E0h+var_18]
0x18001388b  mov     r13, [rsp+0D0h]
0x180013893  mov     r12, [rsp+0E0h+arg_10]
0x18001389b  mov     rsi, [rsp+0E0h+arg_8]
0x1800138a3  mov     rbx, [rsp+0E0h+arg_0]
0x1800138ab  test    rcx, rcx
0x1800138ae  jnz     loc_18001394F
0x1800138b4  mov     rcx, qword ptr [rbp+47h+var_68+8]
0x1800138b8  test    rcx, rcx
0x1800138bb  jnz     loc_18001397A
0x1800138c1  mov     eax, edi
0x1800138c3  add     rsp, 0D8h
0x1800138ca  pop     rdi
0x1800138cb  pop     rbp
0x1800138cc  retn
0x1800138cd  mov     rcx, [rbx+20h]
0x1800138d1  lea     rdx, [rbx+20h]
0x1800138d5  lea     r8, [rbp+47h+var_A0]
0x1800138d9  mov     rax, [rcx]
0x1800138dc  mov     rax, [rax+48h]
0x1800138e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138e5  mov     edi, eax
0x1800138e7  test    eax, eax
0x1800138e9  js      short loc_180013877
0x1800138eb  cmp     cs:NtLmGlobalDomainJoined, sil
0x1800138f2  jz      loc_180013811
0x1800138f8  cmp     [rbp+47h+var_A0], esi
0x1800138fb  jz      loc_180013811
0x180013901  test    byte ptr [r14+4], 1
0x180013906  jz      loc_1800139A5
0x18001390c  mov     ecx, 1
0x180013911  movaps  xmm0, xmmword ptr [r13+0]
0x180013916  movaps  xmm1, xmmword ptr [r12]
0x18001391b  movups  [rbp+47h+var_58], xmm0
0x18001391f  psrldq  xmm0, 8
0x180013924  movq    rdx, xmm0
0x180013929  movups  xmmword ptr [rbp+47h+var_88.Length], xmm1
0x18001392d  test    rdx, rdx
0x180013930  jz      short loc_18001393D
0x180013932  xor     eax, eax
0x180013934  cmp     ax, [rdx]
0x180013937  jnz     loc_180013A30
0x18001393d  test    ecx, ecx
0x18001393f  jz      loc_180013A27
0x180013945  movups  xmm0, xmmword ptr [r15+10h]
0x18001394a  jmp     loc_180013A2C
0x18001394f  movzx   eax, word ptr [rbp+47h+var_78]
0x180013953  test    rax, rax
0x180013956  jz      short loc_180013969
0x180013958  mov     byte ptr [rcx], 0
0x18001395b  lea     rcx, [rcx+1]
0x18001395f  sub     rax, 1
0x180013963  jnz     short loc_180013958
0x180013965  mov     rcx, qword ptr [rbp+47h+var_78+8]
0x180013969  mov     rax, cs:qword_180088240
0x180013970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013975  jmp     loc_1800138B4
0x18001397a  movzx   eax, word ptr [rbp+47h+var_68]
0x18001397e  test    rax, rax
0x180013981  jz      short loc_180013994
0x180013983  mov     byte ptr [rcx], 0
0x180013986  lea     rcx, [rcx+1]
0x18001398a  sub     rax, 1
0x18001398e  jnz     short loc_180013983
0x180013990  mov     rcx, qword ptr [rbp+47h+var_68+8]
0x180013994  mov     rax, cs:qword_180088240
0x18001399b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a0  jmp     loc_1800138C1
0x1800139a5  mov     rax, cs:LsaFunctions
0x1800139ac  lea     rcx, [rbp+47h+var_48]
0x1800139b0  mov     rax, [rax+80h]
0x1800139b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139bc  mov     edi, eax
0x1800139be  test    eax, eax
0x1800139c0  jns     short loc_180013A00
0x1800139c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139c9  lea     rax, WPP_GLOBAL_Control
0x1800139d0  cmp     rcx, rax
0x1800139d3  jz      loc_180013877
0x1800139d9  test    byte ptr [rcx+1Ch], 1
0x1800139dd  jz      loc_180013877
0x1800139e3  mov     rcx, [rcx+10h]
0x1800139e7  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x1800139ee  mov     edx, 23h ; '#'
0x1800139f3  mov     r9d, edi
0x1800139f6  call    WPP_SF_d
0x1800139fb  jmp     loc_180013877
0x180013a00  xor     ecx, ecx
0x180013a02  cmp     byte ptr [rbp+47h+var_38], cl
0x180013a05  jnz     loc_180013911
0x180013a0b  cmp     dword ptr [rbp+47h+var_48], 3E4h
0x180013a12  jnz     short loc_180013A1D
0x180013a14  cmp     dword ptr [rbp+47h+var_48+4], ecx
0x180013a17  jz      loc_180013911
0x180013a1d  mov     edi, 0C0000022h
0x180013a22  jmp     loc_180013877
0x180013a27  movups  xmm0, xmmword ptr [r14+28h]
0x180013a2c  movups  [rbp+47h+var_58], xmm0
0x180013a30  psrldq  xmm1, 8
0x180013a35  movq    rdx, xmm1
0x180013a3a  test    rdx, rdx
0x180013a3d  jz      short loc_180013A46
0x180013a3f  xor     eax, eax
0x180013a41  cmp     ax, [rdx]
0x180013a44  jnz     short loc_180013A70
0x180013a46  test    ecx, ecx
0x180013a48  jz      short loc_180013A67
0x180013a4a  mov     rdx, r15; struct _UNICODE_STRING *
0x180013a4d  lea     rcx, [rbp+47h+var_88]; struct _UNICODE_STRING *
0x180013a51  call    ?NlpMapLogonDomain@@YAJPEAU_UNICODE_STRING@@0@Z; NlpMapLogonDomain(_UNICODE_STRING *,_UNICODE_STRING *)
0x180013a56  mov     edi, eax
0x180013a58  test    eax, eax
0x180013a5a  js      loc_180013877
0x180013a60  mov     esi, 1
0x180013a65  jmp     short loc_180013A70
0x180013a67  movups  xmm0, xmmword ptr [r14+38h]
0x180013a6c  movups  xmmword ptr [rbp+47h+var_88.Length], xmm0
0x180013a70  lea     rax, [rbp+47h+FileTime1]
0x180013a74  xor     r9d, r9d
0x180013a77  mov     [rsp+30h], rax
0x180013a7c  lea     rdx, [rbp+47h+var_88]
0x180013a80  lea     rax, [rbp+47h+var_68]
0x180013a84  xor     r8d, r8d
0x180013a87  mov     [rsp+0E0h+var_B8], rax
0x180013a8c  lea     rcx, [rbp+47h+var_58]
0x180013a90  lea     rax, [rbp+47h+var_78]
0x180013a94  mov     [rsp+0E0h+var_C0], rax
0x180013a99  mov     rax, cs:qword_1800883D0
0x180013aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013aa5  mov     edi, eax
0x180013aa7  test    eax, eax
0x180013aa9  js      loc_18001386F
0x180013aaf  lea     rdx, [r14+8]
0x180013ab3  xor     ecx, ecx
0x180013ab5  call    NlpGetCredEncryptionTypeForUser
0x180013aba  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013abe  mov     edi, eax
0x180013ac0  call    cs:__imp_GetSystemTimeAsFileTime
0x180013ac6  mov     rbx, [rbp+47h+arg_28]
0x180013aca  lea     rdx, [rbp+47h+SystemTimeAsFileTime]; lpFileTime2
0x180013ace  lea     rcx, [rbp+47h+FileTime1]; lpFileTime1
0x180013ad2  add     rbx, 20h ; ' '
0x180013ad6  call    cs:__imp_CompareFileTime
0x180013adc  lea     rdx, [rbp+47h+var_78]
0x180013ae0  mov     [rsp+0E0h+var_C0], rbx
0x180013ae5  test    eax, eax
0x180013ae7  lea     rcx, [rbp+47h+var_68]
0x180013aeb  mov     r9d, edi
0x180013aee  cmovle  rcx, rdx
0x180013af2  xor     r8d, r8d
0x180013af5  xor     edx, edx
0x180013af7  call    NlpPutOwfsInPrimaryCredential
0x180013afc  mov     edi, eax
0x180013afe  test    eax, eax
0x180013b00  jns     loc_18001386D
0x180013b06  jmp     loc_18001386F
0x180013b0b  mov     rcx, [rbp+47h+var_88.Buffer]
0x180013b0f  test    rcx, rcx
0x180013b12  jz      loc_180013877
0x180013b18  call    NtLmFree
0x180013b1d  jmp     loc_180013877
```
