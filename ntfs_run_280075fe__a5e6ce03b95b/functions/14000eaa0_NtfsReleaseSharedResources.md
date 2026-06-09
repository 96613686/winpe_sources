# NtfsReleaseSharedResources

- ea: `0x14000eaa0`
- end: `0x14000f025`
- name: `NtfsReleaseSharedResources`
- size: `1413`
- prototype: ``
- caller_count: `16`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400177d0`
- `0x1401301b0`
- `0x1401493f4`
- `0x140193354`
- `0x1401a2cb0`
- `0x1401c3700`
- `0x1401c9a40`
- `0x1401dc5e8`
- `0x140205560`
- `0x14020d830`
- `0x140210dd0`
- `0x140227518`
- `0x140232674`
- `0x14024c894`
- `0x14024fba4`
- `0x140280ccc`

## callees

- `0x14000ea70`
- `0x14000eaa0`
- `0x1400596c0`
- `0x14025120c`

## import_xrefs

- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000ed08`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000ee5e`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000ed08`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000ee5e`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000ecde`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000ee38`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000ecde`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000ee38`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14000ec1a`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14000ed7c`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14000ec1a`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14000ed7c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ed4b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000eea1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ed4b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000eea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ef13`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ef13`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eb90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ebf5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000eb90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ebf5`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000eb63`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000ebcb`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000eb63`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000ebcb`

## pseudocode

```c
void __fastcall NtfsReleaseSharedResources(__int64 a1)
{
  int v1; // eax
  _QWORD *v3; // rsi
  int v4; // edi
  __int64 v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  struct _ERESOURCE *v8; // rcx
  __int64 v9; // rdi
  struct _ERESOURCE *v10; // rcx
  _QWORD *v11; // r15
  _QWORD *v12; // rax
  __int64 v13; // r13
  _QWORD *v14; // rbp
  _QWORD *v15; // r12
  _QWORD *v16; // r14
  _QWORD *i; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rax
  _QWORD *v21; // rsi
  _QWORD *v22; // rax
  _QWORD *v23; // rbp
  _QWORD *v24; // r14
  _QWORD *v25; // r15
  _QWORD *j; // rax
  __int64 v27; // rcx
  _QWORD *v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rdx

  v1 = *(unsigned __int16 *)(a1 + 34);
  if ( (_WORD)v1 )
  {
    if ( v1 != 1 )
    {
      v3 = *(_QWORD **)(a1 + 40);
      v4 = *(unsigned __int16 *)(a1 + 34);
      while ( 1 )
      {
        v5 = *v3;
        if ( !*v3 )
          goto LABEL_5;
        if ( *(_WORD *)v5 == 1805 )
        {
          NtfsReleaseQuotaControl(a1, *v3);
          *v3 = 0;
        }
        else
        {
          if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v5 + 104) + 64LL)) )
          {
            if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(*v3 + 104LL) + 64LL)) == 1 )
            {
              v11 = (_QWORD *)(a1 + 280);
              v12 = *(_QWORD **)(a1 + 280);
              if ( v12 != (_QWORD *)(a1 + 280) )
              {
                v13 = *v3;
                v14 = 0;
                while ( v12 != v11 )
                {
                  if ( *((_WORD *)v12 - 4) == 1831 )
                  {
                    v14 = v12 - 1;
                    break;
                  }
                  v12 = (_QWORD *)*v12;
                }
                if ( v14 )
                {
                  do
                  {
                    v15 = 0;
                    v16 = v14 + 1;
                    if ( (_QWORD *)*v11 != v11 )
                    {
                      for ( i = (_QWORD *)*v16; ; i = (_QWORD *)*i )
                      {
                        v16 = v14 + 1;
                        if ( i == v11 )
                          break;
                        if ( *((_WORD *)i - 4) == 1831 )
                        {
                          v15 = i - 1;
                          break;
                        }
                      }
                    }
                    v18 = v14[10];
                    if ( v18 )
                    {
                      if ( v13 && *(_QWORD *)(v18 + 184) != v13 )
                        goto LABEL_43;
                      if ( (*(_DWORD *)(v18 + 200) & 0x2000) != 0 || (*(_DWORD *)(v18 + 512) & 0x4040) != 0 )
                      {
                        if ( *(_DWORD *)(v18 + 256) == 256 && (*(_DWORD *)(v18 + 512) & 0x40) != 0 )
                          *(_DWORD *)(v18 + 256) = 0;
                        v30 = v14[10];
                        if ( (*(_DWORD *)(v30 + 200) & 0x2000) != 0 || (*(_DWORD *)(v30 + 512) & 0x4000) != 0 )
                        {
                          ClearFlagInterlocked(v30 + 200, 0x2000);
                          *(_DWORD *)(v14[10] + 512LL) &= ~0x4000u;
                        }
                      }
                      FsRtlAcquireHeaderMutex(v14[10] + 120LL, v14[10] + 160LL);
                      *(_QWORD *)(v14[10] + 496LL) = 0;
                      FsRtlReleaseHeaderMutex(v14[10] + 120LL, v14[10] + 160LL);
                    }
                    v19 = (_QWORD *)*v16;
                    if ( *(_QWORD **)(*v16 + 8LL) != v16 )
                      goto LABEL_75;
                    v20 = (_QWORD *)v16[1];
                    if ( (_QWORD *)*v20 != v16 )
                      goto LABEL_75;
                    *v20 = v19;
                    v19[1] = v20;
                    if ( v14 != (_QWORD *)(a1 + 552) )
                      ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v14);
LABEL_43:
                    v14 = v15;
                  }
                  while ( v15 );
                }
              }
            }
          }
          v7 = *v3;
          if ( *(_WORD *)*v3 == 1794 )
            v8 = (struct _ERESOURCE *)(*(_QWORD *)(v7 + 104) + 64LL);
          else
            v8 = *(struct _ERESOURCE **)(v7 + 8);
          ExReleaseResourceLite(v8);
          *v3 = 0;
        }
LABEL_5:
        if ( !--v4 )
        {
          v6 = *(void **)(a1 + 40);
          if ( *(_BYTE *)(a1 + 32) == 18 )
          {
            memset(v6, 0, 8LL * *(unsigned __int16 *)(a1 + 34));
          }
          else
          {
            ExFreePoolWithTag(v6, 0);
            *(_QWORD *)(a1 + 40) = 0;
            *(_WORD *)(a1 + 34) = 0;
          }
          return;
        }
        ++v3;
      }
    }
    v9 = *(_QWORD *)(a1 + 40);
    if ( v9 )
    {
      if ( *(_WORD *)v9 == 1805 )
      {
        NtfsReleaseQuotaControl(a1, *(_QWORD *)(a1 + 40));
        *(_QWORD *)(a1 + 40) = 0;
        *(_WORD *)(a1 + 34) = 0;
        return;
      }
      if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(v9 + 104) + 64LL)) )
      {
        if ( ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v9 + 104) + 64LL)) == 1 )
        {
          v21 = (_QWORD *)(a1 + 280);
          v22 = *(_QWORD **)(a1 + 280);
          if ( v22 != (_QWORD *)(a1 + 280) )
          {
            v23 = 0;
            while ( v22 != v21 )
            {
              if ( *((_WORD *)v22 - 4) == 1831 )
              {
                v23 = v22 - 1;
                break;
              }
              v22 = (_QWORD *)*v22;
            }
            if ( v23 )
            {
              while ( 1 )
              {
                v24 = v23 + 1;
                v25 = 0;
                if ( (_QWORD *)*v21 != v21 )
                {
                  for ( j = (_QWORD *)*v24; ; j = (_QWORD *)*j )
                  {
                    v24 = v23 + 1;
                    if ( j == v21 )
                      break;
                    if ( *((_WORD *)j - 4) == 1831 )
                    {
                      v25 = j - 1;
                      break;
                    }
                  }
                }
                v27 = v23[10];
                if ( v27 )
                {
                  if ( *(_QWORD *)(v27 + 184) != v9 )
                    goto LABEL_66;
                  if ( (*(_DWORD *)(v27 + 200) & 0x2000) != 0 || (*(_DWORD *)(v27 + 512) & 0x4040) != 0 )
                  {
                    if ( *(_DWORD *)(v27 + 256) == 256 && (*(_DWORD *)(v27 + 512) & 0x40) != 0 )
                      *(_DWORD *)(v27 + 256) = 0;
                    v31 = v23[10];
                    if ( (*(_DWORD *)(v31 + 200) & 0x2000) != 0 || (*(_DWORD *)(v31 + 512) & 0x4000) != 0 )
                    {
                      ClearFlagInterlocked(v31 + 200, 0x2000);
                      *(_DWORD *)(v23[10] + 512LL) &= ~0x4000u;
                    }
                  }
                  FsRtlAcquireHeaderMutex(v23[10] + 120LL, v23[10] + 160LL);
                  *(_QWORD *)(v23[10] + 496LL) = 0;
                  FsRtlReleaseHeaderMutex(v23[10] + 120LL, v23[10] + 160LL);
                }
                v28 = (_QWORD *)*v24;
                if ( *(_QWORD **)(*v24 + 8LL) != v24 || (v29 = (_QWORD *)v24[1], (_QWORD *)*v29 != v24) )
LABEL_75:
                  __fastfail(3u);
                *v29 = v28;
                v28[1] = v29;
                if ( v23 != (_QWORD *)(a1 + 552) )
                  ExFreeToLookasideListEx(&NtfsScbSnapshotLookasideList, v23);
LABEL_66:
                if ( !v25 )
                  break;
                v23 = v25;
              }
            }
          }
        }
      }
      if ( *(_WORD *)v9 == 1794 )
        v10 = (struct _ERESOURCE *)(*(_QWORD *)(v9 + 104) + 64LL);
      else
        v10 = *(struct _ERESOURCE **)(v9 + 8);
      ExReleaseResourceLite(v10);
    }
    *(_QWORD *)(a1 + 40) = 0;
    *(_WORD *)(a1 + 34) = 0;
  }
}

```

## disassembly

```asm
0x14000eaa0  push    rbx
0x14000eaa2  sub     rsp, 40h
0x14000eaa6  movzx   eax, word ptr [rcx+22h]
0x14000eaaa  mov     rbx, rcx
0x14000eaad  test    ax, ax
0x14000eab0  jnz     short loc_14000EAB9
0x14000eab2  add     rsp, 40h
0x14000eab6  pop     rbx
0x14000eab7  retn
0x14000eab9  mov     [rsp+48h+arg_0], rbp
0x14000eabe  mov     [rsp+48h+arg_8], rsi
0x14000eac3  mov     [rsp+48h+arg_10], rdi
0x14000eac8  mov     [rsp+48h+var_10], r12
0x14000eacd  mov     [rsp+48h+var_18], r13
0x14000ead2  mov     [rsp+48h+var_20], r14
0x14000ead7  mov     [rsp+48h+var_28], r15
0x14000eadc  cmp     eax, 1
0x14000eadf  jz      loc_14000EBA9
0x14000eae5  mov     rsi, [rcx+28h]
0x14000eae9  mov     edi, eax
0x14000eaeb  mov     eax, 70Dh
0x14000eaf0  xor     r14d, r14d
0x14000eaf3  mov     r12d, 727h
0x14000eaf9  mov     rcx, [rsi]
0x14000eafc  test    rcx, rcx
0x14000eaff  jnz     short loc_14000EB52
0x14000eb01  add     edi, 0FFFFFFFFh
0x14000eb04  jz      short loc_14000EB0C
0x14000eb06  add     rsi, 8
0x14000eb0a  jmp     short loc_14000EAF9
0x14000eb0c  mov     rcx, [rbx+28h]; void *
0x14000eb10  xor     edx, edx; Val
0x14000eb12  cmp     byte ptr [rbx+20h], 12h
0x14000eb16  jnz     loc_14000EF13
0x14000eb1c  movzx   r8d, word ptr [rbx+22h]
0x14000eb21  shl     r8, 3; Size
0x14000eb25  call    memset
0x14000eb2a  mov     r14, [rsp+48h+var_20]
0x14000eb2f  mov     r13, [rsp+48h+var_18]
0x14000eb34  mov     r12, [rsp+48h+var_10]
0x14000eb39  mov     rdi, [rsp+48h+arg_10]
0x14000eb3e  mov     rsi, [rsp+48h+arg_8]
0x14000eb43  mov     rbp, [rsp+48h+arg_0]
0x14000eb48  mov     r15, [rsp+48h+var_28]
0x14000eb4d  jmp     loc_14000EAB2
0x14000eb52  cmp     [rcx], ax
0x14000eb55  jz      loc_14000EEC4
0x14000eb5b  mov     rcx, [rcx+68h]
0x14000eb5f  add     rcx, 40h ; '@'; Resource
0x14000eb63  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14000eb6a  nop     dword ptr [rax+rax+00h]
0x14000eb6f  test    al, al
0x14000eb71  jnz     loc_14000EC0F
0x14000eb77  mov     rcx, [rsi]
0x14000eb7a  mov     eax, 702h
0x14000eb7f  cmp     ax, [rcx]
0x14000eb82  jnz     loc_14000EEDC
0x14000eb88  mov     rcx, [rcx+68h]
0x14000eb8c  add     rcx, 40h ; '@'; Resource
0x14000eb90  call    cs:__imp_ExReleaseResourceLite
0x14000eb97  nop     dword ptr [rax+rax+00h]
0x14000eb9c  mov     eax, 70Dh
0x14000eba1  mov     [rsi], r14
0x14000eba4  jmp     loc_14000EB01
0x14000eba9  mov     rdi, [rcx+28h]
0x14000ebad  xor     r12d, r12d
0x14000ebb0  test    rdi, rdi
0x14000ebb3  jz      short loc_14000EC01
0x14000ebb5  mov     eax, 70Dh
0x14000ebba  cmp     [rdi], ax
0x14000ebbd  jz      loc_14000EEF5
0x14000ebc3  mov     rcx, [rdi+68h]
0x14000ebc7  add     rcx, 40h ; '@'; Resource
0x14000ebcb  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14000ebd2  nop     dword ptr [rax+rax+00h]
0x14000ebd7  test    al, al
0x14000ebd9  jnz     loc_14000ED74
0x14000ebdf  mov     eax, 702h
0x14000ebe4  cmp     ax, [rdi]
0x14000ebe7  jnz     loc_14000EFFF
0x14000ebed  mov     rcx, [rdi+68h]
0x14000ebf1  add     rcx, 40h ; '@'; Resource
0x14000ebf5  call    cs:__imp_ExReleaseResourceLite
0x14000ebfc  nop     dword ptr [rax+rax+00h]
0x14000ec01  mov     [rbx+28h], r12
0x14000ec05  mov     [rbx+22h], r12w
0x14000ec0a  jmp     loc_14000EB2A
0x14000ec0f  mov     rax, [rsi]
0x14000ec12  mov     rcx, [rax+68h]
0x14000ec16  add     rcx, 40h ; '@'; Resource
0x14000ec1a  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14000ec21  nop     dword ptr [rax+rax+00h]
0x14000ec26  cmp     eax, 1
0x14000ec29  jnz     loc_14000EB77
0x14000ec2f  lea     r15, [rbx+118h]
0x14000ec36  mov     rax, [r15]
0x14000ec39  cmp     rax, r15
0x14000ec3c  jz      loc_14000EB77
0x14000ec42  mov     r13, [rsi]
0x14000ec45  mov     rbp, r14
0x14000ec48  cmp     rax, r15
0x14000ec4b  jz      short loc_14000EC5C
0x14000ec4d  cmp     [rax-8], r12w
0x14000ec52  jnz     loc_14000EEE5
0x14000ec58  lea     rbp, [rax-8]
0x14000ec5c  test    rbp, rbp
0x14000ec5f  jz      loc_14000EB77
0x14000ec65  mov     r12, r14
0x14000ec68  lea     r14, [rbp+8]
0x14000ec6c  cmp     [r15], r15
0x14000ec6f  jz      short loc_14000EC94
0x14000ec71  mov     rax, [r14]
0x14000ec74  mov     rcx, r14
0x14000ec77  mov     r8d, 727h
0x14000ec7d  mov     r14, rcx
0x14000ec80  cmp     rax, r15
0x14000ec83  jz      short loc_14000EC94
0x14000ec85  cmp     [rax-8], r8w
0x14000ec8a  jnz     loc_14000EF0B
0x14000ec90  lea     r12, [rax-8]
0x14000ec94  mov     rcx, [rbp+50h]
0x14000ec98  test    rcx, rcx
0x14000ec9b  jz      short loc_14000ED14
0x14000ec9d  test    r13, r13
0x14000eca0  jz      short loc_14000ECAF
0x14000eca2  cmp     [rcx+0B8h], r13
0x14000eca9  jnz     loc_14000ED57
0x14000ecaf  test    dword ptr [rcx+0C8h], 2000h
0x14000ecb9  jnz     loc_14000EF3C
0x14000ecbf  test    dword ptr [rcx+200h], 4040h
0x14000ecc9  jnz     loc_14000EF3C
0x14000eccf  mov     rcx, [rbp+50h]
0x14000ecd3  lea     rdx, [rcx+0A0h]
0x14000ecda  add     rcx, 78h ; 'x'
0x14000ecde  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14000ece5  nop     dword ptr [rax+rax+00h]
0x14000ecea  mov     rax, [rbp+50h]
0x14000ecee  mov     qword ptr [rax+1F0h], 0
0x14000ecf9  mov     rcx, [rbp+50h]
0x14000ecfd  lea     rdx, [rcx+0A0h]
0x14000ed04  add     rcx, 78h ; 'x'
0x14000ed08  call    cs:__imp_FsRtlReleaseHeaderMutex
0x14000ed0f  nop     dword ptr [rax+rax+00h]
0x14000ed14  mov     rcx, [r14]
0x14000ed17  cmp     [rcx+8], r14
0x14000ed1b  jnz     loc_14000EF2D
0x14000ed21  mov     rax, [r14+8]
0x14000ed25  cmp     [rax], r14
0x14000ed28  jnz     loc_14000EF2D
0x14000ed2e  mov     [rax], rcx
0x14000ed31  mov     [rcx+8], rax
0x14000ed35  lea     rax, [rbx+228h]
0x14000ed3c  cmp     rbp, rax
0x14000ed3f  jz      short loc_14000ED57
0x14000ed41  mov     rdx, rbp; Entry
0x14000ed44  lea     rcx, NtfsScbSnapshotLookasideList; Lookaside
0x14000ed4b  call    cs:__imp_ExFreeToLookasideListEx
0x14000ed52  nop     dword ptr [rax+rax+00h]
0x14000ed57  mov     rbp, r12
0x14000ed5a  mov     r14d, 0
0x14000ed60  test    r12, r12
0x14000ed63  jnz     loc_14000EC65
0x14000ed69  mov     r12d, 727h
0x14000ed6f  jmp     loc_14000EB77
0x14000ed74  mov     rcx, [rdi+68h]
0x14000ed78  add     rcx, 40h ; '@'; Resource
0x14000ed7c  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14000ed83  nop     dword ptr [rax+rax+00h]
0x14000ed88  cmp     eax, 1
0x14000ed8b  jnz     loc_14000EBDF
0x14000ed91  lea     rsi, [rbx+118h]
0x14000ed98  mov     rax, [rsi]
0x14000ed9b  cmp     rax, rsi
0x14000ed9e  jz      loc_14000EBDF
0x14000eda4  mov     rbp, r12
0x14000eda7  mov     r8d, 727h
0x14000edad  cmp     rax, rsi
0x14000edb0  jz      short loc_14000EDC1
0x14000edb2  cmp     [rax-8], r8w
0x14000edb7  jnz     loc_14000EEED
0x14000edbd  lea     rbp, [rax-8]
0x14000edc1  test    rbp, rbp
0x14000edc4  jz      loc_14000EBDF
0x14000edca  lea     r14, [rbp+8]
0x14000edce  mov     r15, r12
0x14000edd1  cmp     [rsi], rsi
0x14000edd4  jz      short loc_14000EDF3
0x14000edd6  mov     rax, [r14]
0x14000edd9  mov     rdx, r14
0x14000eddc  mov     r14, rdx
0x14000eddf  cmp     rax, rsi
0x14000ede2  jz      short loc_14000EDF3
0x14000ede4  cmp     [rax-8], r8w
0x14000ede9  jnz     loc_14000EF34
0x14000edef  lea     r15, [rax-8]
0x14000edf3  mov     rcx, [rbp+50h]
0x14000edf7  test    rcx, rcx
0x14000edfa  jz      short loc_14000EE6A
0x14000edfc  cmp     [rcx+0B8h], rdi
0x14000ee03  jnz     loc_14000EEAD
0x14000ee09  test    dword ptr [rcx+0C8h], 2000h
0x14000ee13  jnz     loc_14000EF96
0x14000ee19  test    dword ptr [rcx+200h], 4040h
0x14000ee23  jnz     loc_14000EF96
0x14000ee29  mov     rcx, [rbp+50h]
0x14000ee2d  lea     rdx, [rcx+0A0h]
0x14000ee34  add     rcx, 78h ; 'x'
0x14000ee38  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14000ee3f  nop     dword ptr [rax+rax+00h]
0x14000ee44  mov     rax, [rbp+50h]
0x14000ee48  mov     [rax+1F0h], r12
0x14000ee4f  mov     rcx, [rbp+50h]
0x14000ee53  lea     rdx, [rcx+0A0h]
0x14000ee5a  add     rcx, 78h ; 'x'
0x14000ee5e  call    cs:__imp_FsRtlReleaseHeaderMutex
0x14000ee65  nop     dword ptr [rax+rax+00h]
0x14000ee6a  mov     rcx, [r14]
0x14000ee6d  cmp     [rcx+8], r14
0x14000ee71  jnz     loc_14000EF2D
0x14000ee77  mov     rax, [r14+8]
0x14000ee7b  cmp     [rax], r14
0x14000ee7e  jnz     loc_14000EF2D
0x14000ee84  mov     [rax], rcx
0x14000ee87  mov     [rcx+8], rax
0x14000ee8b  lea     rax, [rbx+228h]
0x14000ee92  cmp     rbp, rax
0x14000ee95  jz      short loc_14000EEAD
0x14000ee97  mov     rdx, rbp; Entry
0x14000ee9a  lea     rcx, NtfsScbSnapshotLookasideList; Lookaside
0x14000eea1  call    cs:__imp_ExFreeToLookasideListEx
0x14000eea8  nop     dword ptr [rax+rax+00h]
0x14000eead  test    r15, r15
0x14000eeb0  jz      loc_14000EBDF
0x14000eeb6  mov     rbp, r15
0x14000eeb9  mov     r8d, 727h
0x14000eebf  jmp     loc_14000EDCA
0x14000eec4  mov     rdx, rcx
0x14000eec7  mov     rcx, rbx
0x14000eeca  call    NtfsReleaseQuotaControl
0x14000eecf  mov     eax, 70Dh
0x14000eed4  mov     [rsi], r14
0x14000eed7  jmp     loc_14000EB01
0x14000eedc  mov     rcx, [rcx+8]
0x14000eee0  jmp     loc_14000EB90
0x14000eee5  mov     rax, [rax]
0x14000eee8  jmp     loc_14000EC48
0x14000eeed  mov     rax, [rax]
0x14000eef0  jmp     loc_14000EDAD
0x14000eef5  mov     rdx, rdi
0x14000eef8  call    NtfsReleaseQuotaControl
0x14000eefd  mov     [rbx+28h], r12
0x14000ef01  mov     [rbx+22h], r12w
0x14000ef06  jmp     loc_14000EB2A
0x14000ef0b  mov     rax, [rax]
0x14000ef0e  jmp     loc_14000EC7D
0x14000ef13  call    cs:__imp_ExFreePoolWithTag
0x14000ef1a  nop     dword ptr [rax+rax+00h]
0x14000ef1f  mov     [rbx+28h], r14
0x14000ef23  mov     [rbx+22h], r14w
0x14000ef28  jmp     loc_14000EB2A
0x14000ef2d  mov     ecx, 3
0x14000ef32  int     29h; Win8: RtlFailFast(ecx)
0x14000ef34  mov     rax, [rax]
0x14000ef37  jmp     loc_14000EDDC
0x14000ef3c  cmp     dword ptr [rcx+100h], 100h
0x14000ef46  jz      loc_14000F008
0x14000ef4c  mov     rdx, [rbp+50h]
0x14000ef50  lea     rcx, [rdx+0C8h]
0x14000ef57  test    dword ptr [rcx], 2000h
0x14000ef5d  jnz     short loc_14000EF6F
0x14000ef5f  test    dword ptr [rdx+200h], 4000h
0x14000ef69  jz      loc_14000ECCF
0x14000ef6f  mov     edx, 2000h
0x14000ef74  call    ClearFlagInterlocked
0x14000ef79  mov     rcx, [rbp+50h]
0x14000ef7d  mov     edx, [rcx+200h]
0x14000ef83  mov     rax, [rbp+50h]
0x14000ef87  btr     edx, 0Eh
0x14000ef8b  mov     [rax+200h], edx
0x14000ef91  jmp     loc_14000ECCF
0x14000ef96  cmp     dword ptr [rcx+100h], 100h
0x14000efa0  jz      short loc_14000EFEC
0x14000efa2  mov     rdx, [rbp+50h]
0x14000efa6  lea     rcx, [rdx+0C8h]
0x14000efad  test    dword ptr [rcx], 2000h
0x14000efb3  jnz     short loc_14000EFC5
0x14000efb5  test    dword ptr [rdx+200h], 4000h
0x14000efbf  jz      loc_14000EE29
0x14000efc5  mov     edx, 2000h
0x14000efca  call    ClearFlagInterlocked
0x14000efcf  mov     rcx, [rbp+50h]
0x14000efd3  mov     edx, [rcx+200h]
0x14000efd9  mov     rax, [rbp+50h]
0x14000efdd  btr     edx, 0Eh
0x14000efe1  mov     [rax+200h], edx
0x14000efe7  jmp     loc_14000EE29
0x14000efec  mov     eax, [rcx+200h]
0x14000eff2  test    al, 40h
0x14000eff4  jz      short loc_14000EFA2
0x14000eff6  mov     [rcx+100h], r12d
  ... truncated ...
```
