# NegpAddServicesSid(_LSA_TOKEN_INFORMATION_TYPE,void *,_LSA_TOKEN_INFORMATION_TYPE *,void * *)

- ea: `0x1800d35d4`
- end: `0x1800d3a44`
- name: `?NegpAddServicesSid@@YAJW4_LSA_TOKEN_INFORMATION_TYPE@@PEAXPEAW41@PEAPEAX@Z`
- size: `1136`
- prototype: `__int64 __fastcall(enum _LSA_TOKEN_INFORMATION_TYPE, void *, enum _LSA_TOKEN_INFORMATION_TYPE *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18009a340`

## callees

- `0x180011278`
- `0x180016f70`
- `0x180056f84`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x1800d35d4`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800d38ce`
- `ntdll!RtlCopySid` at `0x1800d3930`
- `ntdll!RtlCopySid` at `0x1800d3977`
- `ntdll!RtlCopySid` at `0x1800d39a6`
- `ntdll!RtlCopySid` at `0x1800d39db`
- `ntdll!RtlCopySid` at `0x1800d38ce`
- `ntdll!RtlCopySid` at `0x1800d3930`
- `ntdll!RtlCopySid` at `0x1800d3977`
- `ntdll!RtlCopySid` at `0x1800d39a6`
- `ntdll!RtlCopySid` at `0x1800d39db`
- `ntdll!RtlFreeSid` at `0x1800d3a15`
- `ntdll!RtlFreeSid` at `0x1800d3a15`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d36bf`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d36bf`
- `ntdll!RtlLengthSid` at `0x1800d3664`
- `ntdll!RtlLengthSid` at `0x1800d36da`
- `ntdll!RtlLengthSid` at `0x1800d3707`
- `ntdll!RtlLengthSid` at `0x1800d3723`
- `ntdll!RtlLengthSid` at `0x1800d374f`
- `ntdll!RtlLengthSid` at `0x1800d38b7`
- `ntdll!RtlLengthSid` at `0x1800d3914`
- `ntdll!RtlLengthSid` at `0x1800d3960`
- `ntdll!RtlLengthSid` at `0x1800d398e`
- `ntdll!RtlLengthSid` at `0x1800d39c6`
- `ntdll!RtlLengthSid` at `0x1800d3664`
- `ntdll!RtlLengthSid` at `0x1800d36da`
- `ntdll!RtlLengthSid` at `0x1800d3707`
- `ntdll!RtlLengthSid` at `0x1800d3723`
- `ntdll!RtlLengthSid` at `0x1800d374f`
- `ntdll!RtlLengthSid` at `0x1800d38b7`
- `ntdll!RtlLengthSid` at `0x1800d3914`
- `ntdll!RtlLengthSid` at `0x1800d3960`
- `ntdll!RtlLengthSid` at `0x1800d398e`
- `ntdll!RtlLengthSid` at `0x1800d39c6`

## pseudocode

```c
__int64 __fastcall NegpAddServicesSid(
        unsigned int a1,
        unsigned int **a2,
        enum _LSA_TOKEN_INFORMATION_TYPE *a3,
        void **a4)
{
  enum _LSA_TOKEN_INFORMATION_TYPE v5; // r13d
  unsigned int v6; // ebx
  ULONG v7; // eax
  unsigned int *v8; // rbx
  ULONG v9; // r14d
  int v10; // ebx
  NTSTATUS v11; // eax
  ULONG v12; // eax
  unsigned int *v13; // rdx
  ULONG v14; // edi
  unsigned int v15; // ebx
  ULONG v16; // eax
  ULONG v17; // ebx
  unsigned int *v18; // rax
  unsigned int *v19; // rcx
  unsigned int *v20; // rax
  int v21; // edi
  unsigned int *v22; // rax
  _DWORD *v23; // r15
  size_t v24; // r8
  _DWORD *v25; // rdx
  char *v26; // r12
  char *v27; // rbx
  int v28; // ecx
  unsigned int *v29; // rax
  unsigned int v30; // eax
  char *v31; // r14
  int v32; // eax
  unsigned int *v33; // rdx
  size_t v34; // rbx
  ULONG v35; // eax
  __int64 v36; // rbx
  unsigned int *v37; // rax
  char *v38; // r14
  unsigned int v39; // r13d
  __int64 v40; // rdi
  __int64 v41; // rcx
  ULONG v42; // eax
  __int64 v43; // rbx
  ULONG v44; // eax
  __int64 v45; // rbx
  char *v46; // rbx
  ULONG v47; // eax
  __int64 v48; // r14
  char *v49; // rbx
  ULONG v50; // eax
  NTSTATUS v52; // [rsp+60h] [rbp-29h]
  PSID SourceSid; // [rsp+68h] [rbp-21h] BYREF
  unsigned int v54; // [rsp+70h] [rbp-19h]
  enum _LSA_TOKEN_INFORMATION_TYPE *v55; // [rsp+78h] [rbp-11h]
  void **v56; // [rsp+80h] [rbp-9h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp-1h] BYREF

  v56 = a4;
  v55 = a3;
  v54 = a1;
  SourceSid = 0;
  v5 = a1;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  if ( a1 - 1 > 2 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids, a1);
    v6 = -1073741637;
    goto LABEL_49;
  }
  v7 = RtlLengthSid(a2[1]);
  v8 = a2[3];
  v9 = v7;
  if ( v8 )
    v10 = 16 * (*v8 + 7);
  else
    v10 = 112;
  v11 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x50u, 0, 0, 0, 0, 0, 0, 0, &SourceSid);
  v52 = v11;
  if ( v11 < 0 )
  {
    v6 = v11;
    goto LABEL_49;
  }
  v12 = RtlLengthSid(SourceSid);
  v13 = a2[3];
  v14 = v9 + v10 + v12;
  if ( v13 && *v13 )
  {
    v15 = 0;
    do
    {
      v16 = RtlLengthSid(*(PSID *)&v13[4 * v15 + 2]);
      v13 = a2[3];
      ++v15;
      v14 += v16;
    }
    while ( v15 < *v13 );
  }
  v17 = RtlLengthSid(a2[4]) + v14;
  v18 = a2[5];
  if ( v18 )
    v17 += 12 * *v18 + 4;
  v19 = a2[6];
  if ( v19 )
    v17 += RtlLengthSid(v19);
  v20 = a2[7];
  if ( v20 )
    v17 += *((unsigned __int16 *)v20 + 1);
  v21 = 3;
  if ( v5 == LsaTokenInformationV3 )
  {
    v22 = a2[8];
    if ( v22 )
      v17 += ((*v22 + 7) & 0xFFFFFFF8) + 16;
  }
  v23 = (_DWORD *)LsapAllocate(v17);
  if ( !v23 )
  {
    v6 = -1073741801;
LABEL_49:
    v23 = a2;
    v21 = v5;
    goto LABEL_50;
  }
  v24 = 88;
  if ( v5 != LsaTokenInformationV3 )
    v24 = 64;
  memcpy_0(v23, a2, v24);
  v25 = v23 + 22;
  v26 = (char *)(v23 + 22);
  if ( v5 == LsaTokenInformationV3 )
  {
    if ( a2[8] )
    {
      *((_QWORD *)v23 + 8) = v25;
      v27 = (char *)(v23 + 26);
      v28 = *a2[8];
      *v25 = v28;
      if ( v28 )
      {
        memcpy_0(v27, *((const void **)a2[8] + 1), *a2[8]);
        *(_QWORD *)(*((_QWORD *)v23 + 8) + 8LL) = v27;
        v26 = &v27[(*a2[8] + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
      }
      else
      {
        v26 = (char *)(v23 + 26);
        *((_QWORD *)v23 + 12) = 0;
      }
    }
    else
    {
      *((_QWORD *)v23 + 8) = 0;
    }
  }
  *((_QWORD *)v23 + 3) = v26;
  v29 = a2[3];
  if ( v29 )
  {
    v30 = *v29;
    v31 = &v26[16 * v30 + 24];
    v32 = v30 + 1;
  }
  else
  {
    v31 = v26 + 24;
    v32 = 1;
  }
  *(_DWORD *)v26 = v32;
  v33 = a2[5];
  if ( v33 )
  {
    v34 = 12 * *v33 + 4;
    memcpy_0(v31, v33, v34);
    v31 += v34;
  }
  if ( a2[7] )
  {
    *((_QWORD *)v23 + 7) = v31;
    memcpy_0(v31, a2[7], *((unsigned __int16 *)a2[7] + 1));
    v31 += *((unsigned __int16 *)a2[7] + 1);
  }
  *((_DWORD *)v26 + 4) = 7;
  *((_QWORD *)v26 + 1) = v31;
  v35 = RtlLengthSid(SourceSid);
  v36 = v35;
  RtlCopySid(v35, v31, SourceSid);
  v37 = a2[3];
  v38 = &v31[v36];
  if ( v37 && *v37 )
  {
    v39 = 0;
    do
    {
      v40 = 2LL * v39++;
      v41 = 2LL * v39;
      *(_DWORD *)&v26[8 * v41 + 16] = v37[2 * v40 + 4];
      *(_QWORD *)&v26[8 * v41 + 8] = v38;
      v42 = RtlLengthSid(*(PSID *)&a2[3][2 * v40 + 2]);
      v43 = v42;
      RtlCopySid(v42, v38, *(PSID *)&a2[3][2 * v40 + 2]);
      v37 = a2[3];
      v38 += v43;
    }
    while ( v39 < *v37 );
    v5 = v54;
    v21 = 3;
  }
  v23[4] = *((_DWORD *)a2 + 4);
  *((_QWORD *)v23 + 1) = v38;
  v44 = RtlLengthSid(a2[1]);
  v45 = v44;
  RtlCopySid(v44, v38, a2[1]);
  v46 = &v38[v45];
  *((_QWORD *)v23 + 4) = v46;
  v47 = RtlLengthSid(a2[4]);
  v48 = v47;
  RtlCopySid(v47, v46, a2[4]);
  if ( a2[6] )
  {
    v49 = &v46[v48];
    *((_QWORD *)v23 + 6) = v49;
    v50 = RtlLengthSid(a2[6]);
    RtlCopySid(v50, v49, a2[6]);
  }
  LsapFreeTokenInformation(v5, a2);
  v6 = v52;
LABEL_50:
  *v55 = v21;
  *v56 = v23;
  if ( SourceSid )
    RtlFreeSid(SourceSid);
  return v6;
}

```

## disassembly

```asm
0x1800d35d4  push    rbp
0x1800d35d6  push    rbx
0x1800d35d7  push    rsi
0x1800d35d8  push    rdi
0x1800d35d9  push    r12
0x1800d35db  push    r13
0x1800d35dd  push    r14
0x1800d35df  push    r15
0x1800d35e1  lea     rbp, [rsp-1Fh]
0x1800d35e6  sub     rsp, 0A8h
0x1800d35ed  mov     rax, cs:__security_cookie
0x1800d35f4  xor     rax, rsp
0x1800d35f7  mov     [rbp+57h+var_50], rax
0x1800d35fb  xor     r12d, r12d
0x1800d35fe  mov     [rbp+57h+var_60], r9
0x1800d3602  lea     eax, [rcx-1]
0x1800d3605  mov     [rbp+57h+var_68], r8
0x1800d3609  mov     [rbp+57h+var_70], ecx
0x1800d360c  mov     rsi, rdx
0x1800d360f  mov     [rbp+57h+SourceSid], r12
0x1800d3613  mov     r13d, ecx
0x1800d3616  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x1800d361a  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1800d3620  cmp     eax, 2
0x1800d3623  jbe     short loc_1800D3660
0x1800d3625  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d362c  lea     rax, WPP_GLOBAL_Control
0x1800d3633  cmp     rcx, rax
0x1800d3636  jz      short loc_1800D3656
0x1800d3638  test    byte ptr [rcx+1Ch], 1
0x1800d363c  jz      short loc_1800D3656
0x1800d363e  mov     rcx, [rcx+10h]
0x1800d3642  lea     edx, [r12+68h]
0x1800d3647  mov     r9d, r13d
0x1800d364a  lea     r8, WPP_ba8e463a02353fcee7069faa518abd92_Traceguids
0x1800d3651  call    WPP_SF_d
0x1800d3656  mov     ebx, 0C00000BBh
0x1800d365b  jmp     loc_1800D39F9
0x1800d3660  mov     rcx, [rdx+8]; Sid
0x1800d3664  call    cs:__imp_RtlLengthSid
0x1800d366b  nop     dword ptr [rax+rax+00h]
0x1800d3670  mov     rbx, [rsi+18h]
0x1800d3674  mov     r14d, eax
0x1800d3677  test    rbx, rbx
0x1800d367a  jz      short loc_1800D3686
0x1800d367c  mov     ebx, [rbx]
0x1800d367e  add     ebx, 7
0x1800d3681  shl     ebx, 4
0x1800d3684  jmp     short loc_1800D368B
0x1800d3686  mov     ebx, 70h ; 'p'
0x1800d368b  lea     rax, [rbp+57h+SourceSid]
0x1800d368f  xor     r9d, r9d; SubAuthority1
0x1800d3692  mov     [rsp+0E0h+Sid], rax; Sid
0x1800d3697  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800d369b  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x1800d36a0  mov     dl, 2; SubAuthorityCount
0x1800d36a2  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x1800d36a7  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x1800d36ac  lea     r8d, [r9+50h]; SubAuthority0
0x1800d36b0  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x1800d36b5  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x1800d36ba  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x1800d36bf  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800d36c6  nop     dword ptr [rax+rax+00h]
0x1800d36cb  mov     [rbp+57h+var_80], eax
0x1800d36ce  test    eax, eax
0x1800d36d0  js      loc_1800D39F7
0x1800d36d6  mov     rcx, [rbp+57h+SourceSid]; Sid
0x1800d36da  call    cs:__imp_RtlLengthSid
0x1800d36e1  nop     dword ptr [rax+rax+00h]
0x1800d36e6  mov     rdx, [rsi+18h]
0x1800d36ea  lea     edi, [rbx+rax]
0x1800d36ed  add     edi, r14d
0x1800d36f0  test    rdx, rdx
0x1800d36f3  jz      short loc_1800D371F
0x1800d36f5  cmp     [rdx], r12d
0x1800d36f8  jbe     short loc_1800D371F
0x1800d36fa  mov     ebx, r12d
0x1800d36fd  mov     ecx, ebx
0x1800d36ff  add     rcx, rcx
0x1800d3702  mov     rcx, [rdx+rcx*8+8]; Sid
0x1800d3707  call    cs:__imp_RtlLengthSid
0x1800d370e  nop     dword ptr [rax+rax+00h]
0x1800d3713  mov     rdx, [rsi+18h]
0x1800d3717  inc     ebx
0x1800d3719  add     edi, eax
0x1800d371b  cmp     ebx, [rdx]
0x1800d371d  jb      short loc_1800D36FD
0x1800d371f  mov     rcx, [rsi+20h]; Sid
0x1800d3723  call    cs:__imp_RtlLengthSid
0x1800d372a  nop     dword ptr [rax+rax+00h]
0x1800d372f  lea     ebx, [rax+rdi]
0x1800d3732  mov     rax, [rsi+28h]
0x1800d3736  test    rax, rax
0x1800d3739  jz      short loc_1800D3746
0x1800d373b  mov     eax, [rax]
0x1800d373d  lea     ecx, [rax+rax*2]
0x1800d3740  lea     ebx, [rbx+rcx*4]
0x1800d3743  add     ebx, 4
0x1800d3746  mov     rcx, [rsi+30h]; Sid
0x1800d374a  test    rcx, rcx
0x1800d374d  jz      short loc_1800D375D
0x1800d374f  call    cs:__imp_RtlLengthSid
0x1800d3756  nop     dword ptr [rax+rax+00h]
0x1800d375b  add     ebx, eax
0x1800d375d  mov     rax, [rsi+38h]
0x1800d3761  test    rax, rax
0x1800d3764  jz      short loc_1800D376C
0x1800d3766  movzx   eax, word ptr [rax+2]
0x1800d376a  add     ebx, eax
0x1800d376c  mov     edi, 3
0x1800d3771  cmp     r13d, edi
0x1800d3774  jnz     short loc_1800D378C
0x1800d3776  mov     rax, [rsi+40h]
0x1800d377a  test    rax, rax
0x1800d377d  jz      short loc_1800D378C
0x1800d377f  mov     eax, [rax]
0x1800d3781  add     eax, 7
0x1800d3784  and     eax, 0FFFFFFF8h
0x1800d3787  add     eax, 10h
0x1800d378a  add     ebx, eax
0x1800d378c  mov     ecx, ebx
0x1800d378e  call    LsapAllocate
0x1800d3793  mov     r15, rax
0x1800d3796  test    rax, rax
0x1800d3799  jnz     short loc_1800D37A5
0x1800d379b  mov     ebx, 0C0000017h
0x1800d37a0  jmp     loc_1800D39F9
0x1800d37a5  mov     eax, 40h ; '@'
0x1800d37aa  cmp     r13d, edi
0x1800d37ad  mov     rdx, rsi; Src
0x1800d37b0  mov     rcx, r15; void *
0x1800d37b3  lea     r8d, [rax+18h]
0x1800d37b7  cmovnz  r8d, eax; Size
0x1800d37bb  call    memcpy_0
0x1800d37c0  lea     rdx, [r15+58h]
0x1800d37c4  mov     r12, rdx
0x1800d37c7  cmp     r13d, edi
0x1800d37ca  jnz     short loc_1800D382B
0x1800d37cc  cmp     qword ptr [rsi+40h], 0
0x1800d37d1  jz      short loc_1800D3823
0x1800d37d3  mov     [r15+40h], rdx
0x1800d37d7  lea     rbx, [rdx+10h]
0x1800d37db  mov     rax, [rsi+40h]
0x1800d37df  mov     ecx, [rax]
0x1800d37e1  mov     [rdx], ecx
0x1800d37e3  test    ecx, ecx
0x1800d37e5  jz      short loc_1800D3816
0x1800d37e7  mov     rdx, [rsi+40h]
0x1800d37eb  mov     rcx, rbx; void *
0x1800d37ee  mov     r8d, [rdx]; Size
0x1800d37f1  mov     rdx, [rdx+8]; Src
0x1800d37f5  call    memcpy_0
0x1800d37fa  mov     rax, [r15+40h]
0x1800d37fe  mov     [rax+8], rbx
0x1800d3802  mov     rax, [rsi+40h]
0x1800d3806  mov     r12d, [rax]
0x1800d3809  add     r12, 7
0x1800d380d  and     r12, 0FFFFFFFFFFFFFFF8h
0x1800d3811  add     r12, rbx
0x1800d3814  jmp     short loc_1800D382B
0x1800d3816  mov     r12, rbx
0x1800d3819  mov     qword ptr [rdx+8], 0
0x1800d3821  jmp     short loc_1800D382B
0x1800d3823  mov     qword ptr [r15+40h], 0
0x1800d382b  mov     [r15+18h], r12
0x1800d382f  lea     rcx, [r12+18h]
0x1800d3834  mov     rax, [rsi+18h]
0x1800d3838  test    rax, rax
0x1800d383b  jz      short loc_1800D384D
0x1800d383d  mov     eax, [rax]
0x1800d383f  mov     r14d, eax
0x1800d3842  shl     r14, 4
0x1800d3846  add     r14, rcx
0x1800d3849  inc     eax
0x1800d384b  jmp     short loc_1800D3855
0x1800d384d  mov     r14, rcx
0x1800d3850  mov     eax, 1
0x1800d3855  mov     [r12], eax
0x1800d3859  mov     rdx, [rsi+28h]; Src
0x1800d385d  test    rdx, rdx
0x1800d3860  jz      short loc_1800D387E
0x1800d3862  mov     eax, [rdx]
0x1800d3864  lea     ecx, [rax+rax*2]
0x1800d3867  lea     ecx, ds:4[rcx*4]
0x1800d386e  mov     ebx, ecx
0x1800d3870  mov     r8d, ecx; Size
0x1800d3873  mov     rcx, r14; void *
0x1800d3876  call    memcpy_0
0x1800d387b  add     r14, rbx
0x1800d387e  cmp     qword ptr [rsi+38h], 0
0x1800d3883  jz      short loc_1800D38A5
0x1800d3885  mov     [r15+38h], r14
0x1800d3889  mov     rcx, r14; void *
0x1800d388c  mov     rdx, [rsi+38h]; Src
0x1800d3890  movzx   r8d, word ptr [rdx+2]; Size
0x1800d3895  call    memcpy_0
0x1800d389a  mov     rax, [rsi+38h]
0x1800d389e  movzx   ecx, word ptr [rax+2]
0x1800d38a2  add     r14, rcx
0x1800d38a5  mov     dword ptr [r12+10h], 7
0x1800d38ae  mov     [r12+8], r14
0x1800d38b3  mov     rcx, [rbp+57h+SourceSid]; Sid
0x1800d38b7  call    cs:__imp_RtlLengthSid
0x1800d38be  nop     dword ptr [rax+rax+00h]
0x1800d38c3  mov     r8, [rbp+57h+SourceSid]; SourceSid
0x1800d38c7  mov     rdx, r14; DestinationSid
0x1800d38ca  mov     ecx, eax; DestinationSidLength
0x1800d38cc  mov     ebx, eax
0x1800d38ce  call    cs:__imp_RtlCopySid
0x1800d38d5  nop     dword ptr [rax+rax+00h]
0x1800d38da  mov     rax, [rsi+18h]
0x1800d38de  add     r14, rbx
0x1800d38e1  test    rax, rax
0x1800d38e4  jz      short loc_1800D3951
0x1800d38e6  cmp     dword ptr [rax], 0
0x1800d38e9  jbe     short loc_1800D3951
0x1800d38eb  xor     r13d, r13d
0x1800d38ee  mov     edi, r13d
0x1800d38f1  add     rdi, rdi
0x1800d38f4  inc     r13d
0x1800d38f7  mov     ecx, r13d
0x1800d38fa  add     rcx, rcx
0x1800d38fd  mov     eax, [rax+rdi*8+10h]
0x1800d3901  mov     [r12+rcx*8+10h], eax
0x1800d3906  mov     [r12+rcx*8+8], r14
0x1800d390b  mov     rcx, [rsi+18h]
0x1800d390f  mov     rcx, [rcx+rdi*8+8]; Sid
0x1800d3914  call    cs:__imp_RtlLengthSid
0x1800d391b  nop     dword ptr [rax+rax+00h]
0x1800d3920  mov     r8, [rsi+18h]
0x1800d3924  mov     rdx, r14; DestinationSid
0x1800d3927  mov     ecx, eax; DestinationSidLength
0x1800d3929  mov     ebx, eax
0x1800d392b  mov     r8, [r8+rdi*8+8]; SourceSid
0x1800d3930  call    cs:__imp_RtlCopySid
0x1800d3937  nop     dword ptr [rax+rax+00h]
0x1800d393c  mov     rax, [rsi+18h]
0x1800d3940  add     r14, rbx
0x1800d3943  cmp     r13d, [rax]
0x1800d3946  jb      short loc_1800D38EE
0x1800d3948  mov     r13d, [rbp+57h+var_70]
0x1800d394c  mov     edi, 3
0x1800d3951  mov     eax, [rsi+10h]
0x1800d3954  mov     [r15+10h], eax
0x1800d3958  mov     [r15+8], r14
0x1800d395c  mov     rcx, [rsi+8]; Sid
0x1800d3960  call    cs:__imp_RtlLengthSid
0x1800d3967  nop     dword ptr [rax+rax+00h]
0x1800d396c  mov     r8, [rsi+8]; SourceSid
0x1800d3970  mov     rdx, r14; DestinationSid
0x1800d3973  mov     ecx, eax; DestinationSidLength
0x1800d3975  mov     ebx, eax
0x1800d3977  call    cs:__imp_RtlCopySid
0x1800d397e  nop     dword ptr [rax+rax+00h]
0x1800d3983  add     rbx, r14
0x1800d3986  mov     [r15+20h], rbx
0x1800d398a  mov     rcx, [rsi+20h]; Sid
0x1800d398e  call    cs:__imp_RtlLengthSid
0x1800d3995  nop     dword ptr [rax+rax+00h]
0x1800d399a  mov     r8, [rsi+20h]; SourceSid
0x1800d399e  mov     rdx, rbx; DestinationSid
0x1800d39a1  mov     ecx, eax; DestinationSidLength
0x1800d39a3  mov     r14d, eax
0x1800d39a6  call    cs:__imp_RtlCopySid
0x1800d39ad  nop     dword ptr [rax+rax+00h]
0x1800d39b2  xor     r12d, r12d
0x1800d39b5  cmp     [rsi+30h], r12
0x1800d39b9  jz      short loc_1800D39E7
0x1800d39bb  add     rbx, r14
0x1800d39be  mov     [r15+30h], rbx
0x1800d39c2  mov     rcx, [rsi+30h]; Sid
0x1800d39c6  call    cs:__imp_RtlLengthSid
0x1800d39cd  nop     dword ptr [rax+rax+00h]
0x1800d39d2  mov     r8, [rsi+30h]; SourceSid
0x1800d39d6  mov     rdx, rbx; DestinationSid
0x1800d39d9  mov     ecx, eax; DestinationSidLength
0x1800d39db  call    cs:__imp_RtlCopySid
0x1800d39e2  nop     dword ptr [rax+rax+00h]
0x1800d39e7  mov     rdx, rsi; void *
0x1800d39ea  mov     ecx, r13d; enum _LSA_TOKEN_INFORMATION_TYPE
0x1800d39ed  call    ?LsapFreeTokenInformation@@YAXW4_LSA_TOKEN_INFORMATION_TYPE@@PEAX@Z; LsapFreeTokenInformation(_LSA_TOKEN_INFORMATION_TYPE,void *)
0x1800d39f2  mov     ebx, [rbp+57h+var_80]
0x1800d39f5  jmp     short loc_1800D39FF
0x1800d39f7  mov     ebx, eax
0x1800d39f9  mov     r15, rsi
0x1800d39fc  mov     edi, r13d
0x1800d39ff  mov     rax, [rbp+57h+var_68]
0x1800d3a03  mov     [rax], edi
0x1800d3a05  mov     rax, [rbp+57h+var_60]
0x1800d3a09  mov     [rax], r15
0x1800d3a0c  mov     rcx, [rbp+57h+SourceSid]; Sid
0x1800d3a10  test    rcx, rcx
0x1800d3a13  jz      short loc_1800D3A21
0x1800d3a15  call    cs:__imp_RtlFreeSid
0x1800d3a1c  nop     dword ptr [rax+rax+00h]
0x1800d3a21  mov     eax, ebx
0x1800d3a23  mov     rcx, [rbp+57h+var_50]
0x1800d3a27  xor     rcx, rsp; StackCookie
0x1800d3a2a  call    __security_check_cookie
  ... truncated ...
```
