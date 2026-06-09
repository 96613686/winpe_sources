# DuplicateTokenInformationV3(_LSA_TOKEN_INFORMATION_V3 * *,void *,_LSA_TOKEN_INFORMATION_TYPE)

- ea: `0x1800f0c74`
- end: `0x1800f0fd6`
- name: `?DuplicateTokenInformationV3@@YAJPEAPEAU_LSA_TOKEN_INFORMATION_V3@@PEAXW4_LSA_TOKEN_INFORMATION_TYPE@@@Z`
- size: `866`
- prototype: `__int64 __fastcall(struct _LSA_TOKEN_INFORMATION_V3 **, void *, enum _LSA_TOKEN_INFORMATION_TYPE)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800f1224`

## callees

- `0x180016f70`
- `0x1800f0c74`
- `0x18012cf40`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800f0eaf`
- `ntdll!RtlCopySid` at `0x1800f0f16`
- `ntdll!RtlCopySid` at `0x1800f0f53`
- `ntdll!RtlCopySid` at `0x1800f0f81`
- `ntdll!RtlCopySid` at `0x1800f0fb2`
- `ntdll!RtlCopySid` at `0x1800f0eaf`
- `ntdll!RtlCopySid` at `0x1800f0f16`
- `ntdll!RtlCopySid` at `0x1800f0f53`
- `ntdll!RtlCopySid` at `0x1800f0f81`
- `ntdll!RtlCopySid` at `0x1800f0fb2`
- `ntdll!RtlLengthSid` at `0x1800f0cd0`
- `ntdll!RtlLengthSid` at `0x1800f0d03`
- `ntdll!RtlLengthSid` at `0x1800f0d45`
- `ntdll!RtlLengthSid` at `0x1800f0d66`
- `ntdll!RtlLengthSid` at `0x1800f0d7d`
- `ntdll!RtlLengthSid` at `0x1800f0e93`
- `ntdll!RtlLengthSid` at `0x1800f0efa`
- `ntdll!RtlLengthSid` at `0x1800f0f38`
- `ntdll!RtlLengthSid` at `0x1800f0f66`
- `ntdll!RtlLengthSid` at `0x1800f0f99`
- `ntdll!RtlLengthSid` at `0x1800f0cd0`
- `ntdll!RtlLengthSid` at `0x1800f0d03`
- `ntdll!RtlLengthSid` at `0x1800f0d45`
- `ntdll!RtlLengthSid` at `0x1800f0d66`
- `ntdll!RtlLengthSid` at `0x1800f0d7d`
- `ntdll!RtlLengthSid` at `0x1800f0e93`
- `ntdll!RtlLengthSid` at `0x1800f0efa`
- `ntdll!RtlLengthSid` at `0x1800f0f38`
- `ntdll!RtlLengthSid` at `0x1800f0f66`
- `ntdll!RtlLengthSid` at `0x1800f0f99`

## pseudocode

```c
__int64 __fastcall DuplicateTokenInformationV3(
        struct _LSA_TOKEN_INFORMATION_V3 **a1,
        unsigned int **a2,
        enum _LSA_TOKEN_INFORMATION_TYPE a3)
{
  unsigned int v3; // r12d
  unsigned int v7; // ebx
  unsigned int *v8; // rax
  unsigned int *v9; // rax
  ULONG v10; // eax
  unsigned int *v11; // rdx
  ULONG v12; // ebx
  unsigned int v13; // edi
  ULONG v14; // eax
  unsigned int *v15; // rdx
  unsigned int v16; // edi
  ULONG v17; // eax
  unsigned int *v18; // rcx
  unsigned int *v19; // rcx
  __int64 v20; // rax
  struct _LSA_TOKEN_INFORMATION_V3 *v21; // r15
  struct _TOKEN_GROUPS *v23; // r14
  unsigned int *v24; // rax
  ULONG v25; // eax
  __int64 v26; // rbx
  unsigned int *v27; // rax
  unsigned int v28; // ebp
  ULONG v29; // eax
  __int64 v30; // rbx
  unsigned int *v31; // rcx
  ULONG v32; // eax
  __int64 v33; // rbx
  ULONG v34; // eax
  __int64 v35; // rbx
  unsigned int *v36; // rcx
  char *v37; // rbx
  ULONG v38; // eax

  v3 = 0;
  *a1 = 0;
  v7 = 88;
  if ( a3 == LsaTokenInformationV3 )
  {
    v8 = a2[8];
    if ( v8 )
      v7 = ((*v8 + 7) & 0xFFFFFFF8) + 104;
    v9 = a2[9];
    if ( v9 )
      v7 += ((*v9 + 7) & 0xFFFFFFF8) + 16;
  }
  v10 = RtlLengthSid(a2[1]);
  v11 = a2[3];
  v12 = v10 + v7;
  if ( v11 )
  {
    v12 += 16 * *v11 + 24;
    if ( *v11 )
    {
      v13 = 0;
      do
      {
        v14 = RtlLengthSid(*(PSID *)&v11[4 * v13 + 2]);
        v11 = a2[3];
        ++v13;
        v12 += v14;
      }
      while ( v13 < *v11 );
    }
  }
  if ( a3 == LsaTokenInformationV3 )
  {
    v15 = a2[10];
    if ( v15 )
    {
      v12 += 16 * *v15 + 24;
      if ( *v15 )
      {
        v16 = 0;
        do
        {
          v17 = RtlLengthSid(*(PSID *)&v15[4 * v16 + 2]);
          v15 = a2[10];
          ++v16;
          v12 += v17;
        }
        while ( v16 < *v15 );
      }
    }
  }
  v18 = a2[4];
  if ( v18 )
    v12 += RtlLengthSid(v18);
  v19 = a2[6];
  if ( v19 )
    v12 += RtlLengthSid(v19);
  v20 = LsapAllocate(v12);
  v21 = (struct _LSA_TOKEN_INFORMATION_V3 *)v20;
  if ( !v20 )
    return 3221225495LL;
  v23 = (struct _TOKEN_GROUPS *)(v20 + 88);
  *(_QWORD *)v20 = *a2;
  *(_DWORD *)(v20 + 16) = *((_DWORD *)a2 + 4);
  a2[7] = 0;
  if ( a3 == LsaTokenInformationV3 )
  {
    if ( a2[8] )
    {
      *(_QWORD *)(v20 + 64) = v23;
      LsapDuplicateClaimsBlob((void *)(v20 + 88), a2[8]);
      v23 = (struct _TOKEN_GROUPS *)((char *)v23 + ((*a2[8] + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 16);
    }
    else
    {
      *(_QWORD *)(v20 + 64) = 0;
    }
    if ( a2[9] )
    {
      v21->DeviceClaims.DeviceClaims = v23;
      LsapDuplicateClaimsBlob(v23, a2[9]);
      v23 = (struct _TOKEN_GROUPS *)((char *)v23 + ((*a2[9] + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 16);
    }
    else
    {
      v21->DeviceClaims.DeviceClaims = 0;
    }
  }
  if ( a2[3] )
  {
    v21->Groups = v23;
    v23->GroupCount = *a2[3];
    v23 = (struct _TOKEN_GROUPS *)((char *)v23 + 16 * *a2[3] + 24);
  }
  if ( a3 == LsaTokenInformationV3 && a2[10] )
  {
    v21->DeviceGroups = v23;
    v23->GroupCount = *a2[10];
    v23 = (struct _TOKEN_GROUPS *)((char *)v23 + 16 * *a2[10] + 24);
  }
  v24 = a2[3];
  if ( v24 && *v24 )
  {
    do
    {
      v21->Groups->Groups[v3].Sid = v23;
      v25 = RtlLengthSid(*(PSID *)&a2[3][4 * v3 + 2]);
      v26 = v25;
      RtlCopySid(v25, v23, *(PSID *)&a2[3][4 * v3 + 2]);
      v23 = (struct _TOKEN_GROUPS *)((char *)v23 + v26);
      ++v3;
    }
    while ( v3 < *a2[3] );
  }
  if ( a3 == LsaTokenInformationV3 )
  {
    v27 = a2[10];
    if ( v27 )
    {
      v28 = 0;
      if ( *v27 )
      {
        do
        {
          v21->DeviceGroups->Groups[v28].Sid = v23;
          v29 = RtlLengthSid(*(PSID *)&a2[10][4 * v28 + 2]);
          v30 = v29;
          RtlCopySid(v29, v23, *(PSID *)&a2[10][4 * v28 + 2]);
          v23 = (struct _TOKEN_GROUPS *)((char *)v23 + v30);
          ++v28;
        }
        while ( v28 < *a2[10] );
      }
    }
  }
  v31 = a2[4];
  if ( v31 )
  {
    v32 = RtlLengthSid(v31);
    v21->PrimaryGroup.PrimaryGroup = v23;
    v33 = v32;
    RtlCopySid(v32, v23, a2[4]);
    v23 = (struct _TOKEN_GROUPS *)((char *)v23 + v33);
  }
  v34 = RtlLengthSid(a2[1]);
  v21->User.User.Sid = v23;
  v35 = v34;
  RtlCopySid(v34, v23, a2[1]);
  v36 = a2[6];
  if ( v36 )
  {
    v37 = (char *)v23 + v35;
    v38 = RtlLengthSid(v36);
    v21->Owner.Owner = v37;
    RtlCopySid(v38, v37, a2[6]);
  }
  *a1 = v21;
  return 0;
}

```

## disassembly

```asm
0x1800f0c74  push    rbx
0x1800f0c76  push    rbp
0x1800f0c77  push    rsi
0x1800f0c78  push    rdi
0x1800f0c79  push    r12
0x1800f0c7b  push    r13
0x1800f0c7d  push    r14
0x1800f0c7f  push    r15
0x1800f0c81  sub     rsp, 28h
0x1800f0c85  xor     r12d, r12d
0x1800f0c88  mov     ebp, r8d
0x1800f0c8b  mov     [rcx], r12
0x1800f0c8e  mov     rsi, rdx
0x1800f0c91  mov     r13, rcx
0x1800f0c94  mov     ebx, 58h ; 'X'
0x1800f0c99  cmp     r8d, 3
0x1800f0c9d  jnz     short loc_1800F0CCC
0x1800f0c9f  mov     rax, [rdx+40h]
0x1800f0ca3  mov     ecx, 0FFFFFFF8h
0x1800f0ca8  test    rax, rax
0x1800f0cab  jz      short loc_1800F0CB7
0x1800f0cad  mov     ebx, [rax]
0x1800f0caf  add     ebx, 7
0x1800f0cb2  and     ebx, ecx
0x1800f0cb4  add     ebx, 68h ; 'h'
0x1800f0cb7  mov     rax, [rdx+48h]
0x1800f0cbb  test    rax, rax
0x1800f0cbe  jz      short loc_1800F0CCC
0x1800f0cc0  mov     eax, [rax]
0x1800f0cc2  add     eax, 7
0x1800f0cc5  and     eax, ecx
0x1800f0cc7  add     eax, 10h
0x1800f0cca  add     ebx, eax
0x1800f0ccc  mov     rcx, [rdx+8]; Sid
0x1800f0cd0  call    cs:__imp_RtlLengthSid
0x1800f0cd7  nop     dword ptr [rax+rax+00h]
0x1800f0cdc  mov     rdx, [rsi+18h]
0x1800f0ce0  add     ebx, eax
0x1800f0ce2  test    rdx, rdx
0x1800f0ce5  jz      short loc_1800F0D1B
0x1800f0ce7  mov     eax, [rdx]
0x1800f0ce9  shl     eax, 4
0x1800f0cec  add     eax, 18h
0x1800f0cef  add     ebx, eax
0x1800f0cf1  cmp     [rdx], r12d
0x1800f0cf4  jbe     short loc_1800F0D1B
0x1800f0cf6  mov     edi, r12d
0x1800f0cf9  mov     ecx, edi
0x1800f0cfb  add     rcx, rcx
0x1800f0cfe  mov     rcx, [rdx+rcx*8+8]; Sid
0x1800f0d03  call    cs:__imp_RtlLengthSid
0x1800f0d0a  nop     dword ptr [rax+rax+00h]
0x1800f0d0f  mov     rdx, [rsi+18h]
0x1800f0d13  inc     edi
0x1800f0d15  add     ebx, eax
0x1800f0d17  cmp     edi, [rdx]
0x1800f0d19  jb      short loc_1800F0CF9
0x1800f0d1b  cmp     ebp, 3
0x1800f0d1e  jnz     short loc_1800F0D5D
0x1800f0d20  mov     rdx, [rsi+50h]
0x1800f0d24  test    rdx, rdx
0x1800f0d27  jz      short loc_1800F0D5D
0x1800f0d29  mov     eax, [rdx]
0x1800f0d2b  shl     eax, 4
0x1800f0d2e  add     eax, 18h
0x1800f0d31  add     ebx, eax
0x1800f0d33  cmp     [rdx], r12d
0x1800f0d36  jbe     short loc_1800F0D5D
0x1800f0d38  mov     edi, r12d
0x1800f0d3b  mov     ecx, edi
0x1800f0d3d  add     rcx, rcx
0x1800f0d40  mov     rcx, [rdx+rcx*8+8]; Sid
0x1800f0d45  call    cs:__imp_RtlLengthSid
0x1800f0d4c  nop     dword ptr [rax+rax+00h]
0x1800f0d51  mov     rdx, [rsi+50h]
0x1800f0d55  inc     edi
0x1800f0d57  add     ebx, eax
0x1800f0d59  cmp     edi, [rdx]
0x1800f0d5b  jb      short loc_1800F0D3B
0x1800f0d5d  mov     rcx, [rsi+20h]; Sid
0x1800f0d61  test    rcx, rcx
0x1800f0d64  jz      short loc_1800F0D74
0x1800f0d66  call    cs:__imp_RtlLengthSid
0x1800f0d6d  nop     dword ptr [rax+rax+00h]
0x1800f0d72  add     ebx, eax
0x1800f0d74  mov     rcx, [rsi+30h]; Sid
0x1800f0d78  test    rcx, rcx
0x1800f0d7b  jz      short loc_1800F0D8B
0x1800f0d7d  call    cs:__imp_RtlLengthSid
0x1800f0d84  nop     dword ptr [rax+rax+00h]
0x1800f0d89  add     ebx, eax
0x1800f0d8b  mov     ecx, ebx
0x1800f0d8d  call    LsapAllocate
0x1800f0d92  mov     r15, rax
0x1800f0d95  test    rax, rax
0x1800f0d98  jnz     short loc_1800F0DA4
0x1800f0d9a  mov     eax, 0C0000017h
0x1800f0d9f  jmp     loc_1800F0FC4
0x1800f0da4  mov     rax, [rsi]
0x1800f0da7  lea     r14, [r15+58h]
0x1800f0dab  mov     [r15], rax
0x1800f0dae  mov     eax, [rsi+10h]
0x1800f0db1  mov     [r15+10h], eax
0x1800f0db5  mov     [rsi+38h], r12
0x1800f0db9  cmp     ebp, 3
0x1800f0dbc  jnz     short loc_1800F0E20
0x1800f0dbe  cmp     [rsi+40h], r12
0x1800f0dc2  jz      short loc_1800F0DEB
0x1800f0dc4  mov     [r15+40h], r14
0x1800f0dc8  mov     rcx, r14; void *
0x1800f0dcb  mov     rdx, [rsi+40h]; void *
0x1800f0dcf  call    ?LsapDuplicateClaimsBlob@@YAXPEAX0@Z; LsapDuplicateClaimsBlob(void *,void *)
0x1800f0dd4  mov     rax, [rsi+40h]
0x1800f0dd8  mov     ecx, [rax]
0x1800f0dda  add     rcx, 7
0x1800f0dde  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800f0de2  add     rcx, 10h
0x1800f0de6  add     r14, rcx
0x1800f0de9  jmp     short loc_1800F0DEF
0x1800f0deb  mov     [r15+40h], r12
0x1800f0def  cmp     [rsi+48h], r12
0x1800f0df3  jz      short loc_1800F0E1C
0x1800f0df5  mov     [r15+48h], r14
0x1800f0df9  mov     rcx, r14; void *
0x1800f0dfc  mov     rdx, [rsi+48h]; void *
0x1800f0e00  call    ?LsapDuplicateClaimsBlob@@YAXPEAX0@Z; LsapDuplicateClaimsBlob(void *,void *)
0x1800f0e05  mov     rax, [rsi+48h]
0x1800f0e09  mov     ecx, [rax]
0x1800f0e0b  add     rcx, 7
0x1800f0e0f  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800f0e13  add     rcx, 10h
0x1800f0e17  add     r14, rcx
0x1800f0e1a  jmp     short loc_1800F0E20
0x1800f0e1c  mov     [r15+48h], r12
0x1800f0e20  cmp     [rsi+18h], r12
0x1800f0e24  jz      short loc_1800F0E44
0x1800f0e26  mov     [r15+18h], r14
0x1800f0e2a  mov     rax, [rsi+18h]
0x1800f0e2e  mov     ecx, [rax]
0x1800f0e30  mov     [r14], ecx
0x1800f0e33  mov     rax, [rsi+18h]
0x1800f0e37  mov     ecx, [rax]
0x1800f0e39  shl     rcx, 4
0x1800f0e3d  add     rcx, 18h
0x1800f0e41  add     r14, rcx
0x1800f0e44  cmp     ebp, 3
0x1800f0e47  jnz     short loc_1800F0E6D
0x1800f0e49  cmp     [rsi+50h], r12
0x1800f0e4d  jz      short loc_1800F0E6D
0x1800f0e4f  mov     [r15+50h], r14
0x1800f0e53  mov     rax, [rsi+50h]
0x1800f0e57  mov     ecx, [rax]
0x1800f0e59  mov     [r14], ecx
0x1800f0e5c  mov     rax, [rsi+50h]
0x1800f0e60  mov     ecx, [rax]
0x1800f0e62  shl     rcx, 4
0x1800f0e66  add     rcx, 18h
0x1800f0e6a  add     r14, rcx
0x1800f0e6d  mov     rax, [rsi+18h]
0x1800f0e71  test    rax, rax
0x1800f0e74  jz      short loc_1800F0ECD
0x1800f0e76  cmp     [rax], r12d
0x1800f0e79  jbe     short loc_1800F0ECD
0x1800f0e7b  mov     rax, [r15+18h]
0x1800f0e7f  mov     edi, r12d
0x1800f0e82  add     rdi, rdi
0x1800f0e85  mov     [rax+rdi*8+8], r14
0x1800f0e8a  mov     rcx, [rsi+18h]
0x1800f0e8e  mov     rcx, [rcx+rdi*8+8]; Sid
0x1800f0e93  call    cs:__imp_RtlLengthSid
0x1800f0e9a  nop     dword ptr [rax+rax+00h]
0x1800f0e9f  mov     r8, [rsi+18h]
0x1800f0ea3  mov     rdx, r14; DestinationSid
0x1800f0ea6  mov     ecx, eax; DestinationSidLength
0x1800f0ea8  mov     ebx, eax
0x1800f0eaa  mov     r8, [r8+rdi*8+8]; SourceSid
0x1800f0eaf  call    cs:__imp_RtlCopySid
0x1800f0eb6  nop     dword ptr [rax+rax+00h]
0x1800f0ebb  mov     rax, [rsi+18h]
0x1800f0ebf  add     r14, rbx
0x1800f0ec2  inc     r12d
0x1800f0ec5  cmp     r12d, [rax]
0x1800f0ec8  jb      short loc_1800F0E7B
0x1800f0eca  xor     r12d, r12d
0x1800f0ecd  cmp     ebp, 3
0x1800f0ed0  jnz     short loc_1800F0F2F
0x1800f0ed2  mov     rax, [rsi+50h]
0x1800f0ed6  test    rax, rax
0x1800f0ed9  jz      short loc_1800F0F2F
0x1800f0edb  mov     ebp, r12d
0x1800f0ede  cmp     [rax], r12d
0x1800f0ee1  jbe     short loc_1800F0F2F
0x1800f0ee3  mov     rax, [r15+50h]
0x1800f0ee7  mov     edi, ebp
0x1800f0ee9  add     rdi, rdi
0x1800f0eec  mov     [rax+rdi*8+8], r14
0x1800f0ef1  mov     rcx, [rsi+50h]
0x1800f0ef5  mov     rcx, [rcx+rdi*8+8]; Sid
0x1800f0efa  call    cs:__imp_RtlLengthSid
0x1800f0f01  nop     dword ptr [rax+rax+00h]
0x1800f0f06  mov     r8, [rsi+50h]
0x1800f0f0a  mov     rdx, r14; DestinationSid
0x1800f0f0d  mov     ecx, eax; DestinationSidLength
0x1800f0f0f  mov     ebx, eax
0x1800f0f11  mov     r8, [r8+rdi*8+8]; SourceSid
0x1800f0f16  call    cs:__imp_RtlCopySid
0x1800f0f1d  nop     dword ptr [rax+rax+00h]
0x1800f0f22  mov     rax, [rsi+50h]
0x1800f0f26  add     r14, rbx
0x1800f0f29  inc     ebp
0x1800f0f2b  cmp     ebp, [rax]
0x1800f0f2d  jb      short loc_1800F0EE3
0x1800f0f2f  mov     rcx, [rsi+20h]; Sid
0x1800f0f33  test    rcx, rcx
0x1800f0f36  jz      short loc_1800F0F62
0x1800f0f38  call    cs:__imp_RtlLengthSid
0x1800f0f3f  nop     dword ptr [rax+rax+00h]
0x1800f0f44  mov     [r15+20h], r14
0x1800f0f48  mov     rdx, r14; DestinationSid
0x1800f0f4b  mov     r8, [rsi+20h]; SourceSid
0x1800f0f4f  mov     ecx, eax; DestinationSidLength
0x1800f0f51  mov     ebx, eax
0x1800f0f53  call    cs:__imp_RtlCopySid
0x1800f0f5a  nop     dword ptr [rax+rax+00h]
0x1800f0f5f  add     r14, rbx
0x1800f0f62  mov     rcx, [rsi+8]; Sid
0x1800f0f66  call    cs:__imp_RtlLengthSid
0x1800f0f6d  nop     dword ptr [rax+rax+00h]
0x1800f0f72  mov     [r15+8], r14
0x1800f0f76  mov     rdx, r14; DestinationSid
0x1800f0f79  mov     r8, [rsi+8]; SourceSid
0x1800f0f7d  mov     ecx, eax; DestinationSidLength
0x1800f0f7f  mov     ebx, eax
0x1800f0f81  call    cs:__imp_RtlCopySid
0x1800f0f88  nop     dword ptr [rax+rax+00h]
0x1800f0f8d  mov     rcx, [rsi+30h]; Sid
0x1800f0f91  test    rcx, rcx
0x1800f0f94  jz      short loc_1800F0FBE
0x1800f0f96  add     rbx, r14
0x1800f0f99  call    cs:__imp_RtlLengthSid
0x1800f0fa0  nop     dword ptr [rax+rax+00h]
0x1800f0fa5  mov     [r15+30h], rbx
0x1800f0fa9  mov     rdx, rbx; DestinationSid
0x1800f0fac  mov     r8, [rsi+30h]; SourceSid
0x1800f0fb0  mov     ecx, eax; DestinationSidLength
0x1800f0fb2  call    cs:__imp_RtlCopySid
0x1800f0fb9  nop     dword ptr [rax+rax+00h]
0x1800f0fbe  mov     [r13+0], r15
0x1800f0fc2  xor     eax, eax
0x1800f0fc4  add     rsp, 28h
0x1800f0fc8  pop     r15
0x1800f0fca  pop     r14
0x1800f0fcc  pop     r13
0x1800f0fce  pop     r12
0x1800f0fd0  pop     rdi
0x1800f0fd1  pop     rsi
0x1800f0fd2  pop     rbp
0x1800f0fd3  pop     rbx
0x1800f0fd4  retn
```
