# PAC_MarshallValidationInfo(_SAMPR_USER_ALL_INFORMATION *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,void *,_UNICODE_STRING *,_UNICODE_STRING *,uchar,uchar,_LARGE_INTEGER *,_LARGE_INTEGER *,_LSA_LAST_INTER_LOGON_INFO *,uchar * *,ulong *)

- ea: `0x180044770`
- end: `0x18004498b`
- name: `?PAC_MarshallValidationInfo@@YAJPEAU_SAMPR_USER_ALL_INFORMATION@@PEAU_SAMPR_GET_GROUPS_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_UNICODE_STRING@@4EEPEAT_LARGE_INTEGER@@5PEAU_LSA_LAST_INTER_LOGON_INFO@@PEAPEAEPEAK@Z`
- size: `539`
- prototype: `__int64 __fastcall(struct _SAMPR_USER_ALL_INFORMATION *, struct _SAMPR_GET_GROUPS_BUFFER *, struct _SID_AND_ATTRIBUTES_LIST *, void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8, unsigned __int8, union _LARGE_INTEGER *, union _LARGE_INTEGER *, struct _LSA_LAST_INTER_LOGON_INFO *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180044434`

## callees

- `0x1800057f0`
- `0x180018870`
- `0x1800210f0`
- `0x180021a54`
- `0x180044260`
- `0x180044770`
- `0x180044f8c`

## pseudocode

```c
__int64 __fastcall PAC_MarshallValidationInfo(
        struct _SAMPR_USER_ALL_INFORMATION *a1,
        struct _SAMPR_GET_GROUPS_BUFFER *a2,
        const void **a3,
        void *a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        union _LARGE_INTEGER *a9,
        union _LARGE_INTEGER *a10,
        struct _LSA_LAST_INTER_LOGON_INFO *a11,
        unsigned __int8 **a12,
        unsigned int *a13)
{
  __int64 v17; // rdx
  void *v18; // rdi
  int v19; // r9d
  int v20; // r8d
  void *v21; // rax
  unsigned int v22; // ebx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+38h] [rbp-C8h]
  int v33; // [rsp+3Ch] [rbp-C4h]
  int v34; // [rsp+40h] [rbp-C0h]
  int v35; // [rsp+44h] [rbp-BCh]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  __int64 v37; // [rsp+50h] [rbp-B0h]
  __int64 v38; // [rsp+58h] [rbp-A8h]
  __int128 v39; // [rsp+60h] [rbp-A0h]
  __int128 v40; // [rsp+70h] [rbp-90h]
  __int128 v41; // [rsp+80h] [rbp-80h]
  __int128 v42; // [rsp+90h] [rbp-70h]
  __int128 v43; // [rsp+A0h] [rbp-60h]
  __int128 v44; // [rsp+B0h] [rbp-50h]
  __int16 v45; // [rsp+C0h] [rbp-40h]
  __int16 v46; // [rsp+C2h] [rbp-3Eh]
  int v47; // [rsp+C4h] [rbp-3Ch]
  int v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+CCh] [rbp-34h]
  __int64 v50; // [rsp+D0h] [rbp-30h]
  int v51; // [rsp+D8h] [rbp-28h]
  __int128 v52; // [rsp+F0h] [rbp-10h]
  __int128 v53; // [rsp+100h] [rbp+0h]
  void *v54; // [rsp+110h] [rbp+10h]
  int v55; // [rsp+120h] [rbp+20h]
  int v56; // [rsp+140h] [rbp+40h]
  void *v57; // [rsp+148h] [rbp+48h]

  memset_0((char *)&v31 + 4, 0, 0x134u);
  v17 = 0;
  v18 = 0;
  if ( a3 )
    v17 = *(unsigned int *)a3;
  v19 = *((_DWORD *)a1 + 70);
  v20 = v51;
  if ( (v19 & 0x1000) != 0 )
    v20 = 0x40000;
  v33 = 0x7FFFFFFF;
  v31 = *(_QWORD *)a1;
  v36 = *((_QWORD *)a1 + 2);
  v37 = *((_QWORD *)a1 + 4);
  v38 = *((_QWORD *)a1 + 5);
  v32 = -1;
  v34 = -1;
  v35 = 0x7FFFFFFF;
  if ( (v19 & 0x1000) != 0 )
  {
    v37 = 0x7FFFFFFFFFFFFFFFLL;
    v38 = 0x7FFFFFFFFFFFFFFFLL;
  }
  v45 = *((_WORD *)a1 + 153);
  v46 = *((_WORD *)a1 + 152);
  v47 = *((_DWORD *)a1 + 68);
  v48 = *((_DWORD *)a1 + 69);
  if ( a2 )
  {
    v49 = *(_DWORD *)a2;
    v50 = *((_QWORD *)a2 + 1);
  }
  else
  {
    v49 = 0;
    v50 = 0;
  }
  v55 = v19;
  v51 = v20 | 0x20;
  if ( (_DWORD)v17 )
  {
    v56 = v17;
    v21 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 16 * v17);
    v18 = v21;
    if ( !v21 )
      return (unsigned int)-1073741670;
    v57 = v21;
    if ( a3 )
      memcpy_0(v21, a3[1], 16LL * *(unsigned int *)a3);
  }
  v23 = *((_OWORD *)a1 + 4);
  v39 = *((_OWORD *)a1 + 3);
  v54 = a4;
  v24 = *((_OWORD *)a1 + 7);
  v40 = v23;
  v25 = *((_OWORD *)a1 + 8);
  v41 = v24;
  v26 = *((_OWORD *)a1 + 5);
  v42 = v25;
  v27 = *((_OWORD *)a1 + 6);
  v43 = v26;
  v28 = (__int128)*a6;
  v44 = v27;
  v29 = (__int128)*a5;
  v52 = v28;
  v53 = v29;
  v22 = PAC_EncodeValidationInformation((struct _NETLOGON_VALIDATION_SAM_INFO3 *)&v31, a12, a13);
  if ( v18 )
    Pku2uFree(v18);
  return v22;
}

```

## disassembly

```asm
0x180044770  push    rbp
0x180044772  push    rbx
0x180044773  push    rsi
0x180044774  push    rdi
0x180044775  push    r12
0x180044777  push    r13
0x180044779  push    r14
0x18004477b  push    r15
0x18004477d  lea     rbp, [rsp-88h]
0x180044785  sub     rsp, 188h
0x18004478c  mov     rax, cs:__security_cookie
0x180044793  xor     rax, rsp
0x180044796  mov     [rbp+0C0h+var_50], rax
0x18004479a  mov     rax, [rbp+0C0h+arg_58]
0x1800447a1  mov     rsi, r8
0x1800447a4  mov     r12, [rbp+0C0h+arg_20]
0x1800447ab  mov     r14, rdx
0x1800447ae  mov     r13, [rbp+0C0h+arg_28]
0x1800447b5  mov     rbx, rcx
0x1800447b8  mov     [rsp+1C0h+var_198], rax
0x1800447bd  lea     rcx, [rsp+1C0h+var_18C]; void *
0x1800447c2  mov     rax, [rbp+0C0h+arg_60]
0x1800447c9  xor     edx, edx; Val
0x1800447cb  mov     r8d, 134h; Size
0x1800447d1  mov     [rsp+1C0h+var_1A0], rax
0x1800447d6  mov     r15, r9
0x1800447d9  call    memset_0
0x1800447de  xor     edx, edx
0x1800447e0  xor     edi, edi
0x1800447e2  test    rsi, rsi
0x1800447e5  jz      short loc_1800447E9
0x1800447e7  mov     edx, [rsi]
0x1800447e9  mov     r9d, [rbx+118h]
0x1800447f0  mov     eax, 40000h
0x1800447f5  mov     r8d, [rbp+0C0h+var_E8]
0x1800447f9  bt      r9d, 0Ch
0x1800447fe  mov     r11d, 7FFFFFFFh
0x180044804  cmovb   r8d, eax
0x180044808  mov     [rsp+1C0h+var_184], r11d
0x18004480d  mov     rax, [rbx]
0x180044810  or      r10d, 0FFFFFFFFh
0x180044814  mov     [rsp+30h], rax
0x180044819  mov     rax, [rbx+10h]
0x18004481d  mov     [rsp+1C0h+var_178], rax
0x180044822  mov     rax, [rbx+20h]
0x180044826  mov     [rsp+1C0h+var_170], rax
0x18004482b  mov     rax, [rbx+28h]
0x18004482f  mov     [rsp+1C0h+var_168], rax
0x180044834  mov     [rsp+1C0h+var_188], r10d
0x180044839  mov     [rsp+1C0h+var_180], r10d
0x18004483e  mov     [rsp+1C0h+var_17C], r11d
0x180044843  bt      r9d, 0Ch
0x180044848  jnb     short loc_18004485E
0x18004484a  mov     dword ptr [rsp+1C0h+var_170], r10d
0x18004484f  mov     dword ptr [rsp+1C0h+var_170+4], r11d
0x180044854  mov     dword ptr [rsp+1C0h+var_168], r10d
0x180044859  mov     dword ptr [rsp+1C0h+var_168+4], r11d
0x18004485e  movzx   eax, word ptr [rbx+132h]
0x180044865  mov     [rbp+0C0h+var_100], ax
0x180044869  movzx   eax, word ptr [rbx+130h]
0x180044870  mov     [rbp+0C0h+var_FE], ax
0x180044874  mov     eax, [rbx+110h]
0x18004487a  mov     [rbp+0C0h+var_FC], eax
0x18004487d  mov     eax, [rbx+114h]
0x180044883  mov     [rbp+0C0h+var_F8], eax
0x180044886  test    r14, r14
0x180044889  jz      short loc_18004489B
0x18004488b  mov     eax, [r14]
0x18004488e  mov     [rbp+0C0h+var_F4], eax
0x180044891  mov     rax, [r14+8]
0x180044895  mov     [rbp+0C0h+var_F0], rax
0x180044899  jmp     short loc_1800448A2
0x18004489b  mov     [rbp+0C0h+var_F4], edi
0x18004489e  mov     [rbp+0C0h+var_F0], rdi
0x1800448a2  or      r8d, 20h
0x1800448a6  mov     [rbp+0C0h+var_A0], r9d
0x1800448aa  mov     [rbp+0C0h+var_E8], r8d
0x1800448ae  test    edx, edx
0x1800448b0  jz      short loc_1800448F3
0x1800448b2  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x1800448b9  mov     [rbp+0C0h+var_80], edx
0x1800448bc  shl     rdx, 4; unsigned __int64
0x1800448c0  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x1800448c5  mov     rdi, rax
0x1800448c8  test    rax, rax
0x1800448cb  jnz     short loc_1800448D7
0x1800448cd  mov     ebx, 0C000009Ah
0x1800448d2  jmp     loc_180044969
0x1800448d7  mov     [rbp+0C0h+var_78], rax
0x1800448db  test    rsi, rsi
0x1800448de  jz      short loc_1800448F3
0x1800448e0  mov     r8d, [rsi]
0x1800448e3  mov     rcx, rax; void *
0x1800448e6  mov     rdx, [rsi+8]; Src
0x1800448ea  shl     r8, 4; Size
0x1800448ee  call    memcpy_0
0x1800448f3  movups  xmm0, xmmword ptr [rbx+30h]
0x1800448f7  mov     r8, [rsp+1C0h+var_1A0]; unsigned int *
0x1800448fc  lea     rcx, [rsp+1C0h+var_190]; struct _NETLOGON_VALIDATION_SAM_INFO3 *
0x180044901  movups  xmm1, xmmword ptr [rbx+40h]
0x180044905  mov     rdx, [rsp+1C0h+var_198]; unsigned __int8 **
0x18004490a  movdqu  [rsp+1C0h+var_160], xmm0
0x180044910  mov     [rbp+0C0h+var_B0], r15
0x180044914  movups  xmm0, xmmword ptr [rbx+70h]
0x180044918  movdqu  [rsp+1C0h+var_150], xmm1
0x18004491e  movups  xmm1, xmmword ptr [rbx+80h]
0x180044925  movdqu  [rbp+0C0h+var_140], xmm0
0x18004492a  movups  xmm0, xmmword ptr [rbx+50h]
0x18004492e  movdqu  [rbp+0C0h+var_130], xmm1
0x180044933  movups  xmm1, xmmword ptr [rbx+60h]
0x180044937  movdqu  [rbp+0C0h+var_120], xmm0
0x18004493c  movups  xmm0, xmmword ptr [r13+0]
0x180044941  movdqu  [rbp+0C0h+var_110], xmm1
0x180044946  movups  xmm1, xmmword ptr [r12]
0x18004494b  movdqu  [rbp+0C0h+var_D0], xmm0
0x180044950  movdqu  [rbp+0C0h+var_C0], xmm1
0x180044955  call    ?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z; PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)
0x18004495a  mov     ebx, eax
0x18004495c  test    rdi, rdi
0x18004495f  jz      short loc_180044969
0x180044961  mov     rcx, rdi; void *
0x180044964  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180044969  mov     eax, ebx
0x18004496b  mov     rcx, [rbp+0C0h+var_50]
0x18004496f  xor     rcx, rsp; StackCookie
0x180044972  call    __security_check_cookie
0x180044977  add     rsp, 188h
0x18004497e  pop     r15
0x180044980  pop     r14
0x180044982  pop     r13
0x180044984  pop     r12
0x180044986  pop     rdi
0x180044987  pop     rsi
0x180044988  pop     rbx
0x180044989  pop     rbp
0x18004498a  retn
```
