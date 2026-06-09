# CdCommonCreate

- ea: `0x14000c8b4`
- end: `0x14000d3f8`
- name: `CdCommonCreate`
- size: `2884`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140001240`
- `0x140002250`

## callees

- `0x140001114`
- `0x140001160`
- `0x140002df0`
- `0x140003000`
- `0x140003300`
- `0x14000c8b4`
- `0x14000d898`
- `0x14000dc38`
- `0x14000e1d0`
- `0x14000e4a0`
- `0x14000e544`
- `0x14001203c`
- `0x140012198`
- `0x14001233c`
- `0x140016024`
- `0x140016094`
- `0x1400165a8`
- `0x140016618`
- `0x1400166ac`
- `0x1400176a8`
- `0x1400181a4`
- `0x14001943c`
- `0x14001a400`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000d244`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d258`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b589`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b5a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d244`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d258`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b589`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b5a1`
- `ntoskrnl!CcUnpinData` at `0x14000ce30`
- `ntoskrnl!CcUnpinData` at `0x14000d18f`
- `ntoskrnl!CcUnpinData` at `0x14000d2bb`
- `ntoskrnl!CcUnpinData` at `0x14001b488`
- `ntoskrnl!CcUnpinData` at `0x14000ce30`
- `ntoskrnl!CcUnpinData` at `0x14000d18f`
- `ntoskrnl!CcUnpinData` at `0x14000d2bb`
- `ntoskrnl!CcUnpinData` at `0x14001b488`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d1bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d1ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d2e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d318`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b4b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b4e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ce8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d1bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d1ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d2e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d318`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b4b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b4e4`

## pseudocode

```c
__int64 __fastcall CdCommonCreate(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // r14
  __int64 v5; // r10
  int v7; // eax
  int v8; // r13d
  char v9; // r15
  char v10; // bl
  unsigned int v11; // esi
  unsigned __int64 v12; // r9
  unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  char v17; // r15
  int v18; // eax
  unsigned int v19; // r12d
  __int64 v20; // r9
  int v21; // r12d
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // ebx
  unsigned int v25; // eax
  __int64 v26; // r9
  int v27; // r13d
  int v28; // r9d
  char PathEntry; // r12
  int v30; // r9d
  int v31; // r9d
  __int64 v32; // rcx
  int v33; // r9d
  _QWORD *v34; // rbx
  __int64 v35; // rsi
  __int64 v36; // rdx
  char v37; // [rsp+50h] [rbp-4A8h]
  char v38; // [rsp+58h] [rbp-4A0h]
  char v39; // [rsp+59h] [rbp-49Fh]
  char v40; // [rsp+5Bh] [rbp-49Dh]
  __int64 v41; // [rsp+60h] [rbp-498h] BYREF
  unsigned __int64 v42; // [rsp+68h] [rbp-490h]
  __int64 v43; // [rsp+70h] [rbp-488h]
  _QWORD v44[3]; // [rsp+78h] [rbp-480h] BYREF
  PERESOURCE Resource; // [rsp+90h] [rbp-468h]
  void *v46[2]; // [rsp+98h] [rbp-460h] BYREF
  __int128 v47; // [rsp+A8h] [rbp-450h]
  __int64 v48; // [rsp+B8h] [rbp-440h]
  __int64 v49; // [rsp+C0h] [rbp-438h]
  __int64 v50; // [rsp+C8h] [rbp-430h]
  struct _UNICODE_STRING Name; // [rsp+D0h] [rbp-428h] BYREF
  __int128 v52; // [rsp+E0h] [rbp-418h]
  PVOID P[26]; // [rsp+F0h] [rbp-408h] BYREF
  _QWORD v54[96]; // [rsp+1C0h] [rbp-338h] BYREF

  v49 = a2;
  v3 = a1;
  v44[1] = a1;
  v44[2] = a2;
  v4 = *(_QWORD *)(a2 + 184);
  memset(P, 0, 0xC8u);
  memset(v54, 0, sizeof(v54));
  v41 = 0;
  Name = 0;
  v52 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v44[0] = 0;
  v5 = *(_QWORD *)(v3 + 16);
  v48 = v5;
  if ( !v5 )
  {
    CdCompleteRequest(v3, a2, 0);
    return 0;
  }
  v7 = *(_DWORD *)(v4 + 16);
  v8 = v7 & 0x2000;
  v9 = *(_BYTE *)(v4 + 2);
  if ( (v9 & 6) != 0 || *(_DWORD *)(v4 + 32) || (v10 = *(_BYTE *)(v4 + 19), v10 == 2) )
  {
    v24 = -1073741790;
    goto LABEL_121;
  }
  if ( (v7 & 0x10000) != 0 )
    goto LABEL_119;
  v11 = 0;
  v12 = 0;
  v42 = 0;
  v13 = 0;
  v50 = v5;
  v43 = *(_QWORD *)(v5 + 80);
  v14 = *(_QWORD *)(v4 + 48);
  v15 = *(_QWORD *)(v14 + 64);
  if ( !v15 || (v7 & 0x2000) != 0 )
    goto LABEL_14;
  *(_QWORD *)(v14 + 16) = *(_QWORD *)(v15 + 16);
  v11 = *(_DWORD *)(v15 + 32) & 7;
  if ( v11 )
  {
    v16 = *(_QWORD *)(v15 + 24);
    v12 = *(_QWORD *)(v15 + 32) & 0xFFFFFFFFFFFFFFF8uLL;
  }
  else
  {
    v16 = 0;
  }
  v42 = v12;
  v43 = v16;
  if ( v11 < 2 )
  {
LABEL_119:
    v24 = -1073741811;
LABEL_121:
    v36 = a2;
    goto LABEL_122;
  }
  v13 = (unsigned __int16 *)(v15 + 88);
LABEL_14:
  v17 = (unsigned __int8)~v9 >> 7;
  Resource = (PERESOURCE)(v14 + 88);
  v18 = CdNormalizeFileNames(
          (unsigned __int16 *)v3,
          v5,
          v8 != 0,
          v17,
          v11,
          v12,
          v13,
          (unsigned __int16 *)(v14 + 88),
          &Name);
  v19 = v18;
  if ( v18 < 0 )
  {
    CdCompleteRequest(v3, v49, (unsigned int)v18);
    return v19;
  }
  v39 = 0;
  v37 = 0;
  if ( LOWORD(Resource->SystemResourcesList.Flink) || v11 > 2 || v8 )
  {
    v38 = 0;
    v20 = 1;
  }
  else
  {
    v38 = 1;
    v20 = 0;
  }
  v21 = v48;
  Resource = (PERESOURCE)(v48 + 128);
  CdAcquireResource(v3, v48 + 128, 0, v20);
  CdVerifyVcb(v3, v48);
  v23 = *(_DWORD *)(v48 + 48);
  if ( (v23 & 0x10) != 0 )
  {
LABEL_22:
    v24 = -1073741790;
    goto LABEL_93;
  }
  if ( v8 )
  {
    if ( (v23 & 0x80u) != 0 )
    {
      v24 = -1073741808;
      goto LABEL_93;
    }
    if ( ((v10 - 1) & 0xFD) == 0 )
    {
      if ( (*(_DWORD *)(v3 + 32) & 4) == 0 )
        CdRaiseStatusEx(v3, 3221225688LL, 0, 0x80000, 440);
      v25 = CdOpenByFileId((PVOID)v3);
      goto LABEL_92;
    }
    goto LABEL_22;
  }
  if ( v38 )
  {
    if ( ((v10 - 1) & 0xFD) != 0 )
      goto LABEL_22;
    if ( (*(_DWORD *)(v4 + 16) & 1) == 0 )
    {
      v41 = *(_QWORD *)(v48 + 72);
      CdAcquireResource(v3, *(_QWORD *)(v41 + 200) + 32LL, 0, 0);
      v25 = CdOpenExistingFcb((PVOID)v3, 0, 0);
      goto LABEL_92;
    }
LABEL_32:
    v24 = -1073741565;
    goto LABEL_93;
  }
  CdAcquireResource(v3, *(_QWORD *)(v43 + 200) + 32LL, 0, 0);
  v41 = v43;
  if ( !Name.Length || (LOBYTE(v26) = v17, CdFindPrefix(v3, &v41, &Name, v26), !Name.Length) )
  {
    v22 = 773;
    if ( *(_WORD *)v41 == 773 )
    {
      if ( (*(_DWORD *)(v3 + 32) & 0x20000000) != 0 || (*(_DWORD *)(v4 + 16) & 1) != 0 )
        goto LABEL_32;
      if ( ((v10 - 1) & 0xFD) != 0 )
        goto LABEL_22;
    }
    else
    {
      if ( (*(_DWORD *)(v4 + 16) & 0x40) != 0 )
      {
LABEL_42:
        v24 = -1073741638;
        goto LABEL_93;
      }
      if ( ((v10 - 1) & 0xFD) != 0 )
        goto LABEL_22;
    }
    v25 = CdOpenExistingFcb((PVOID)v3, v17, v42);
    goto LABEL_92;
  }
  v22 = *(unsigned int *)(v41 + 176);
  if ( (v22 & 0x10) == 0 )
  {
LABEL_46:
    v24 = -1073741766;
    goto LABEL_93;
  }
  if ( (*(_DWORD *)(v3 + 32) & 4) == 0 )
    CdRaiseStatusEx(v3, 3221225688LL, 0, 0x80000, 607);
  LOWORD(v47) = 0;
  v27 = v21;
  while ( 1 )
  {
    v40 = 0;
    CdDissectName(v22, &Name, v46);
    memset(P, 0, 0xC8u);
    v39 = 1;
    LOBYTE(v28) = v17;
    PathEntry = CdFindPathEntry(v3, v41, (unsigned int)v46, v28, (__int64)P);
    if ( PathEntry )
      goto LABEL_84;
    LODWORD(v43) = CdShortNameDirentOffset(v22, v46);
    if ( (_DWORD)v43 != -1 )
    {
      if ( v37 )
        CdCleanupFileContext(v22, v54);
      memset(v54, 0, sizeof(v54));
      v54[0] = &v54[12];
      v54[1] = &v54[40];
      v54[2] = &v54[68];
      WORD1(v54[5]) = 24;
      v54[6] = &v54[9];
      v37 = 1;
      LOBYTE(v30) = v17;
      PathEntry = CdFindFileByShortName(v3, v41, (unsigned int)v46, v30, v43, (__int64)v54);
      if ( PathEntry )
        break;
    }
LABEL_66:
    if ( !PathEntry )
    {
      if ( Name.Length )
        goto LABEL_46;
      goto LABEL_68;
    }
LABEL_84:
    if ( v17 && !v40 )
      memmove(v46[1], P[10], LOWORD(P[9]));
    if ( !Name.Length )
    {
      if ( (*(_DWORD *)(v4 + 16) & 0x40) != 0 )
        goto LABEL_42;
      if ( v10 == 1 || v10 == 3 )
      {
        v25 = CdOpenDirectoryFromPathEntry(
                v3,
                v4,
                v27,
                (unsigned int)&v41,
                (__int64)v46,
                v17,
                v40,
                (__int64)&P[4],
                1,
                v42);
        goto LABEL_92;
      }
      goto LABEL_22;
    }
    CdOpenDirectoryFromPathEntry(v3, v4, v27, (unsigned int)&v41, (__int64)v46, v17, v40, (__int64)&P[4], 0, 0);
    v22 = (__int64)P[2];
    if ( P[2] )
    {
      CcUnpinData(P[2]);
      P[2] = 0;
    }
    if ( BYTE4(P[3]) )
    {
      v22 = (__int64)P[0];
      if ( P[0] )
      {
        ExFreePoolWithTag(P[0], 0);
        P[0] = 0;
      }
    }
    if ( ((__int64)P[8] & 1) != 0 )
    {
      v22 = (__int64)P[10];
      if ( P[10] )
      {
        ExFreePoolWithTag(P[10], 0);
        P[10] = 0;
      }
    }
  }
  v40 = 1;
  if ( (*(_BYTE *)(v54[1] + 56LL) & 2) != 0 )
  {
    if ( P[2] )
    {
      CcUnpinData(P[2]);
      P[2] = 0;
    }
    if ( BYTE4(P[3]) && P[0] )
    {
      ExFreePoolWithTag(P[0], 0);
      P[0] = 0;
    }
    if ( ((__int64)P[8] & 1) != 0 && P[10] )
    {
      ExFreePoolWithTag(P[10], 0);
      P[10] = 0;
    }
    memset(P, 0, 0xC8u);
    LOBYTE(v31) = v17;
    PathEntry = CdFindPathEntry(v3, v41, LODWORD(v54[1]) + 120, v31, (__int64)P);
    if ( !PathEntry )
      CdRaiseStatusEx(v3, 3221225730LL, 0, 0x80000, 699);
    if ( v17 )
      CdUpcaseName(v22, v46, v46);
    goto LABEL_66;
  }
  if ( Name.Length )
    goto LABEL_46;
  v44[0] = &v54[5];
LABEL_68:
  if ( !PathEntry )
  {
    if ( v37 )
      CdCleanupFileContext(v22, v54);
    memset(v54, 0, sizeof(v54));
    v54[0] = &v54[12];
    v54[1] = &v54[40];
    v54[2] = &v54[68];
    WORD1(v54[5]) = 24;
    v54[6] = &v54[9];
    v37 = 1;
    CdConvertNameToCdName(v32, (unsigned __int16 *)v46);
    LOBYTE(v33) = v17;
    if ( !(unsigned __int8)CdFindFile(v3, v41, (unsigned int)v46, v33, (__int64)v54, (__int64)v44) )
    {
      if ( v10 == 1 || v10 == 4 )
      {
        v24 = -1073741772;
        goto LABEL_93;
      }
      goto LABEL_22;
    }
  }
  if ( (*(_BYTE *)(v54[1] + 57LL) & 2) != 0 )
    CdRaiseStatusEx(v3, 3221225522LL, 0, 0x80000, 881);
  if ( (*(_DWORD *)(v3 + 32) & 0x20000000) != 0 || (*(_DWORD *)(v4 + 16) & 1) != 0 )
    goto LABEL_32;
  if ( ((v10 - 1) & 0xFD) != 0 )
    goto LABEL_22;
  v34 = (_QWORD *)v44[0];
  if ( v17 )
    memmove(v46[1], *(const void **)(v44[0] + 8LL), *(unsigned __int16 *)v44[0]);
  v25 = CdOpenFileFromFileContext(v3, v4, v27, (unsigned int)&v41, (__int64)v46, v17, v34 == &v54[5], (__int64)v54, v42);
LABEL_92:
  v24 = v25;
LABEL_93:
  if ( v39 )
  {
    v22 = (__int64)P[2];
    if ( P[2] )
    {
      CcUnpinData(P[2]);
      P[2] = 0;
    }
    if ( BYTE4(P[3]) )
    {
      v22 = (__int64)P[0];
      if ( P[0] )
      {
        ExFreePoolWithTag(P[0], 0);
        P[0] = 0;
      }
    }
    if ( ((__int64)P[8] & 1) != 0 )
    {
      v22 = (__int64)P[10];
      if ( P[10] )
      {
        ExFreePoolWithTag(P[10], 0);
        P[10] = 0;
      }
    }
  }
  if ( v37 )
    CdCleanupFileContext(v22, v54);
  if ( v24 == 259 )
  {
    v3 = 0;
    v35 = 0;
  }
  else
  {
    v35 = v49;
  }
  if ( v41 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v41 + 200) + 32LL));
  ExReleaseResourceLite(Resource);
  v36 = v35;
LABEL_122:
  CdCompleteRequest(v3, v36, v24);
  return v24;
}

```

## disassembly

```asm
0x14000c8b4  mov     r11, rsp
0x14000c8b7  mov     [r11+18h], rbx
0x14000c8bb  mov     [r11+20h], rsi
0x14000c8bf  push    rdi
0x14000c8c0  push    r12
0x14000c8c2  push    r13
0x14000c8c4  push    r14
0x14000c8c6  push    r15
0x14000c8c8  sub     rsp, 4D0h
0x14000c8cf  mov     rax, cs:__security_cookie
0x14000c8d6  xor     rax, rsp
0x14000c8d9  mov     [rsp+4F8h+var_38], rax
0x14000c8e1  mov     r12, rdx
0x14000c8e4  mov     [r11-438h], rdx
0x14000c8eb  mov     rdi, rcx
0x14000c8ee  mov     [r11-478h], rcx
0x14000c8f5  mov     [r11-470h], rdx
0x14000c8fc  mov     r14, [rdx+0B8h]
0x14000c903  xor     edx, edx; Val
0x14000c905  mov     r8d, 0C8h; Size
0x14000c90b  lea     rcx, [r11-408h]; void *
0x14000c912  call    memset
0x14000c917  xor     edx, edx; Val
0x14000c919  mov     r8d, 300h; Size
0x14000c91f  lea     rcx, [rsp+4F8h+var_338]; void *
0x14000c927  call    memset
0x14000c92c  xor     ecx, ecx
0x14000c92e  mov     [rsp+4F8h+var_498], rcx
0x14000c933  xorps   xmm0, xmm0
0x14000c936  movups  xmmword ptr [rsp+4F8h+var_428.Length], xmm0
0x14000c93e  movups  [rsp+4F8h+var_418], xmm0
0x14000c946  xorps   xmm1, xmm1
0x14000c949  movups  xmmword ptr [rsp+4F8h+var_460], xmm1
0x14000c951  movups  [rsp+4F8h+var_450], xmm1
0x14000c959  mov     [rsp+4F8h+var_480], rcx
0x14000c95e  mov     r10, [rdi+10h]
0x14000c962  mov     [rsp+4F8h+var_440], r10
0x14000c96a  test    r10, r10
0x14000c96d  jnz     short loc_14000C984
0x14000c96f  xor     r8d, r8d
0x14000c972  mov     rdx, r12
0x14000c975  mov     rcx, rdi
0x14000c978  call    CdCompleteRequest
0x14000c97d  xor     eax, eax
0x14000c97f  jmp     loc_14000D353
0x14000c984  mov     eax, [r14+10h]
0x14000c988  mov     r13d, eax
0x14000c98b  and     r13d, 2000h
0x14000c992  setnz   r11b
0x14000c996  mov     r15b, [r14+2]
0x14000c99a  test    r15b, 6
0x14000c99e  jnz     loc_14000D33E
0x14000c9a4  cmp     [r14+20h], ecx
0x14000c9a8  jnz     loc_14000D33E
0x14000c9ae  mov     bl, [r14+13h]
0x14000c9b2  cmp     bl, 2
0x14000c9b5  jz      loc_14000D33E
0x14000c9bb  bt      eax, 10h
0x14000c9bf  jb      loc_14000D337
0x14000c9c5  mov     esi, ecx
0x14000c9c7  mov     r9, rcx
0x14000c9ca  mov     [rsp+4F8h+var_490], rcx
0x14000c9cf  mov     r8, rcx
0x14000c9d2  mov     [rsp+4F8h+var_430], r10
0x14000c9da  mov     rax, [r10+50h]
0x14000c9de  mov     [rsp+4F8h+var_488], rax
0x14000c9e3  mov     rdx, [r14+30h]
0x14000c9e7  mov     rcx, [rdx+40h]
0x14000c9eb  test    rcx, rcx
0x14000c9ee  jz      short loc_14000CA2C
0x14000c9f0  test    r13d, r13d
0x14000c9f3  jnz     short loc_14000CA2C
0x14000c9f5  mov     rax, [rcx+10h]
0x14000c9f9  mov     [rdx+10h], rax
0x14000c9fd  mov     esi, [rcx+20h]
0x14000ca00  and     esi, 7
0x14000ca03  jnz     short loc_14000CA09
0x14000ca05  xor     eax, eax
0x14000ca07  jmp     short loc_14000CA15
0x14000ca09  mov     rax, [rcx+18h]
0x14000ca0d  mov     r9, [rcx+20h]
0x14000ca11  and     r9, 0FFFFFFFFFFFFFFF8h
0x14000ca15  mov     [rsp+4F8h+var_490], r9
0x14000ca1a  mov     [rsp+4F8h+var_488], rax
0x14000ca1f  cmp     esi, 2
0x14000ca22  jb      loc_14000D337
0x14000ca28  lea     r8, [rcx+58h]
0x14000ca2c  not     r15b
0x14000ca2f  shr     r15b, 7
0x14000ca33  lea     rax, [rdx+58h]
0x14000ca37  mov     [rsp+4F8h+Resource], rax
0x14000ca3f  lea     rcx, [rsp+4F8h+var_428]
0x14000ca47  mov     [rsp+4F8h+Name], rcx; Name
0x14000ca4c  mov     [rsp+4F8h+var_4C0], rax; __int64
0x14000ca51  mov     [rsp+4F8h+var_4C8], r8; __int64
0x14000ca56  mov     [rsp+4F8h+var_4D0], r9; __int64
0x14000ca5b  mov     dword ptr [rsp+4F8h+var_4D8], esi; int
0x14000ca5f  mov     r9b, r15b; int
0x14000ca62  mov     r8b, r11b; int
0x14000ca65  mov     rdx, r10; int
0x14000ca68  mov     rcx, rdi; int
0x14000ca6b  call    CdNormalizeFileNames
0x14000ca70  mov     r12d, eax
0x14000ca73  mov     [rsp+4F8h+var_4A4], eax
0x14000ca77  xor     ecx, ecx
0x14000ca79  test    eax, eax
0x14000ca7b  jns     short loc_14000CA98
0x14000ca7d  mov     r8d, eax
0x14000ca80  mov     rdx, [rsp+4F8h+var_438]
0x14000ca88  mov     rcx, rdi
0x14000ca8b  call    CdCompleteRequest
0x14000ca90  mov     eax, r12d
0x14000ca93  jmp     loc_14000D353
0x14000ca98  mov     [rsp+4F8h+var_49F], cl
0x14000ca9c  mov     [rsp+4F8h+var_4A8], cl
0x14000caa0  mov     rax, [rsp+4F8h+Resource]
0x14000caa8  cmp     [rax], cx
0x14000caab  jnz     short loc_14000CAC5
0x14000caad  cmp     esi, 2
0x14000cab0  ja      short loc_14000CAC5
0x14000cab2  test    r13d, r13d
0x14000cab5  jnz     short loc_14000CAC5
0x14000cab7  lea     esi, [r13+1]
0x14000cabb  mov     [rsp+4F8h+var_4A0], sil
0x14000cac0  mov     r9d, ecx
0x14000cac3  jmp     short loc_14000CAD1
0x14000cac5  mov     [rsp+4F8h+var_4A0], cl
0x14000cac9  mov     esi, 1
0x14000cace  mov     r9d, esi
0x14000cad1  mov     r12, [rsp+4F8h+var_440]
0x14000cad9  lea     rax, [r12+80h]
0x14000cae1  mov     [rsp+4F8h+Resource], rax
0x14000cae9  xor     r8d, r8d
0x14000caec  mov     rdx, rax
0x14000caef  mov     rcx, rdi
0x14000caf2  call    CdAcquireResource
0x14000caf7  mov     rdx, r12
0x14000cafa  mov     rcx, rdi
0x14000cafd  call    CdVerifyVcb
0x14000cb02  mov     eax, [r12+30h]
0x14000cb07  xor     edx, edx
0x14000cb09  test    al, 10h
0x14000cb0b  jz      short loc_14000CB1B
0x14000cb0d  mov     ebx, 0C0000022h
0x14000cb12  mov     [rsp+4F8h+var_4A4], ebx
0x14000cb16  jmp     loc_14000D178
0x14000cb1b  test    r13d, r13d
0x14000cb1e  jz      short loc_14000CB56
0x14000cb20  test    al, al
0x14000cb22  jns     short loc_14000CB2B
0x14000cb24  mov     ebx, 0C0000010h
0x14000cb29  jmp     short loc_14000CB12
0x14000cb2b  sub     bl, sil
0x14000cb2e  test    bl, 0FDh
0x14000cb31  jnz     short loc_14000CB0D
0x14000cb33  mov     eax, [rdi+20h]
0x14000cb36  mov     rcx, rdi; Context
0x14000cb39  test    al, 4
0x14000cb3b  jz      loc_14000D381
0x14000cb41  lea     r9, [rsp+4F8h+var_498]
0x14000cb46  mov     r8, r12
0x14000cb49  mov     rdx, r14
0x14000cb4c  call    CdOpenByFileId
0x14000cb51  jmp     loc_14000D170
0x14000cb56  cmp     [rsp+4F8h+var_4A0], dl
0x14000cb5a  jz      short loc_14000CBBB
0x14000cb5c  sub     bl, sil
0x14000cb5f  test    bl, 0FDh
0x14000cb62  jnz     short loc_14000CB0D
0x14000cb64  mov     eax, [r14+10h]
0x14000cb68  test    sil, al
0x14000cb6b  jz      short loc_14000CB74
0x14000cb6d  mov     ebx, 0C0000103h
0x14000cb72  jmp     short loc_14000CB12
0x14000cb74  mov     rax, [r12+48h]
0x14000cb79  mov     [rsp+4F8h+var_498], rax
0x14000cb7e  mov     rdx, [rax+0C8h]
0x14000cb85  add     rdx, 20h ; ' '
0x14000cb89  xor     r9d, r9d
0x14000cb8c  xor     r8d, r8d
0x14000cb8f  mov     rcx, rdi
0x14000cb92  call    CdAcquireResource
0x14000cb97  xor     eax, eax
0x14000cb99  mov     [rsp+4F8h+var_4D0], rax; __int64
0x14000cb9e  mov     [rsp+4F8h+var_4D8], al; char
0x14000cba2  lea     r9d, [rax+2]
0x14000cba6  lea     r8, [rsp+4F8h+var_498]
0x14000cbab  mov     rdx, r14
0x14000cbae  mov     rcx, rdi; Context
0x14000cbb1  call    CdOpenExistingFcb
0x14000cbb6  jmp     loc_14000D170
0x14000cbbb  mov     r13, [rsp+4F8h+var_488]
0x14000cbc0  mov     rdx, [r13+0C8h]
0x14000cbc7  add     rdx, 20h ; ' '
0x14000cbcb  xor     r9d, r9d
0x14000cbce  xor     r8d, r8d
0x14000cbd1  mov     rcx, rdi
0x14000cbd4  call    CdAcquireResource
0x14000cbd9  mov     [rsp+4F8h+var_498], r13
0x14000cbde  movzx   eax, [rsp+4F8h+var_428.Length]
0x14000cbe6  xor     edx, edx
0x14000cbe8  test    ax, ax
0x14000cbeb  jz      short loc_14000CC18
0x14000cbed  mov     r9b, r15b
0x14000cbf0  lea     r8, [rsp+4F8h+var_428]
0x14000cbf8  lea     rdx, [rsp+4F8h+var_498]
0x14000cbfd  mov     rcx, rdi
0x14000cc00  call    CdFindPrefix
0x14000cc05  movzx   eax, [rsp+4F8h+var_428.Length]
0x14000cc0d  xor     edx, edx
0x14000cc0f  test    ax, ax
0x14000cc12  jnz     loc_14000CC9F
0x14000cc18  mov     ecx, 305h
0x14000cc1d  mov     rax, [rsp+4F8h+var_498]
0x14000cc22  cmp     [rax], cx
0x14000cc25  jnz     short loc_14000CC67
0x14000cc27  test    dword ptr [rdi+20h], 20000000h
0x14000cc2e  jnz     loc_14000CB6D
0x14000cc34  mov     eax, [r14+10h]
0x14000cc38  test    sil, al
0x14000cc3b  jnz     loc_14000CB6D
0x14000cc41  sub     bl, sil
0x14000cc44  test    bl, 0FDh
0x14000cc47  jnz     loc_14000CB0D
0x14000cc4d  mov     rcx, [rsp+4F8h+var_490]
0x14000cc52  mov     [rsp+4F8h+var_4D0], rcx
0x14000cc57  mov     [rsp+4F8h+var_4D8], r15b
0x14000cc5c  mov     r9d, 4
0x14000cc62  jmp     loc_14000CBA6
0x14000cc67  mov     eax, [r14+10h]
0x14000cc6b  test    al, 40h
0x14000cc6d  jz      short loc_14000CC79
0x14000cc6f  mov     ebx, 0C00000BAh
0x14000cc74  jmp     loc_14000CB12
0x14000cc79  sub     bl, sil
0x14000cc7c  test    bl, 0FDh
0x14000cc7f  jnz     loc_14000CB0D
0x14000cc85  mov     rcx, [rsp+4F8h+var_490]
0x14000cc8a  mov     [rsp+4F8h+var_4D0], rcx
0x14000cc8f  mov     [rsp+4F8h+var_4D8], r15b
0x14000cc94  mov     r9d, 3
0x14000cc9a  jmp     loc_14000CBA6
0x14000cc9f  mov     rax, [rsp+4F8h+var_498]
0x14000cca4  mov     ecx, [rax+0B0h]
0x14000ccaa  test    cl, 10h
0x14000ccad  jnz     short loc_14000CCB9
0x14000ccaf  mov     ebx, 0C000003Ah
0x14000ccb4  jmp     loc_14000CB12
0x14000ccb9  mov     eax, [rdi+20h]
0x14000ccbc  test    al, 4
0x14000ccbe  jz      loc_14000D39C
0x14000ccc4  mov     word ptr [rsp+4F8h+var_450], dx
0x14000cccc  mov     r13, r12
0x14000cccf  mov     [rsp+4F8h+var_49D], dl
0x14000ccd3  lea     r8, [rsp+4F8h+var_460]
0x14000ccdb  lea     rdx, [rsp+4F8h+var_428]
0x14000cce3  call    CdDissectName
0x14000cce8  xor     edx, edx; Val
0x14000ccea  mov     r8d, 0C8h; Size
0x14000ccf0  lea     rcx, [rsp+4F8h+P]; void *
0x14000ccf8  call    memset
0x14000ccfd  mov     [rsp+4F8h+var_49F], sil
0x14000cd02  lea     rax, [rsp+4F8h+P]
0x14000cd0a  mov     qword ptr [rsp+4F8h+var_4D8], rax
0x14000cd0f  mov     r9b, r15b
0x14000cd12  lea     r8, [rsp+4F8h+var_460]
0x14000cd1a  mov     rdx, [rsp+4F8h+var_498]
0x14000cd1f  mov     rcx, rdi
0x14000cd22  call    CdFindPathEntry
0x14000cd27  mov     r12b, al
0x14000cd2a  mov     [rsp+4F8h+var_49E], al
0x14000cd2e  xor     edx, edx
0x14000cd30  test    al, al
0x14000cd32  jnz     loc_14000D0D3
0x14000cd38  lea     rdx, [rsp+4F8h+var_460]
0x14000cd40  call    CdShortNameDirentOffset
0x14000cd45  mov     dword ptr [rsp+4F8h+var_488], eax
0x14000cd49  cmp     eax, 0FFFFFFFFh
0x14000cd4c  jz      loc_14000CF0C
0x14000cd52  xor     eax, eax
0x14000cd54  cmp     [rsp+4F8h+var_4A8], al
0x14000cd58  jz      short loc_14000CD67
0x14000cd5a  lea     rdx, [rsp+4F8h+var_338]
0x14000cd62  call    CdCleanupFileContext
0x14000cd67  xor     edx, edx; Val
0x14000cd69  mov     r8d, 300h; Size
0x14000cd6f  lea     rcx, [rsp+4F8h+var_338]; void *
0x14000cd77  call    memset
0x14000cd7c  lea     rax, [rsp+4F8h+var_2D8]
0x14000cd84  mov     [rsp+4F8h+var_338], rax
0x14000cd8c  lea     rax, [rsp+4F8h+var_1F8]
0x14000cd94  mov     [rsp+4F8h+var_330], rax
0x14000cd9c  lea     rax, [rsp+4F8h+var_118]
0x14000cda4  mov     [rsp+4F8h+var_328], rax
0x14000cdac  mov     eax, 18h
0x14000cdb1  mov     [rsp+4F8h+var_30E], ax
0x14000cdb9  lea     rax, [rsp+4F8h+var_2F0]
0x14000cdc1  mov     [rsp+4F8h+var_308], rax
0x14000cdc9  mov     [rsp+4F8h+var_4A8], sil
0x14000cdce  lea     rax, [rsp+4F8h+var_338]
  ... truncated ...
```
