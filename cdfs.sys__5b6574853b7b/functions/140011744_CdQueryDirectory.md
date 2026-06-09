# CdQueryDirectory

- ea: `0x140011744`
- end: `0x140011fcb`
- name: `CdQueryDirectory`
- size: `2183`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140010ee0`

## callees

- `0x140001114`
- `0x140001160`
- `0x140002df0`
- `0x140003000`
- `0x140003300`
- `0x140010f68`
- `0x140011138`
- `0x140011744`
- `0x14001203c`
- `0x14001617c`
- `0x1400163f0`
- `0x1400181a4`
- `0x14001a2a0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140011f18`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b89d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140011f18`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001b89d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140011f6c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b907`
- `ntoskrnl!ExReleaseFastMutex` at `0x140011f6c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001b907`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011f7c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b920`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011f7c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b920`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x140011bdc`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x140011bdc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400118a2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400118a2`

## pseudocode

```c
__int64 __fastcall CdQueryDirectory(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v10; // rsi
  __int64 v11; // rcx
  char *v12; // rsi
  unsigned int v13; // edi
  unsigned int v14; // r13d
  unsigned int v15; // r12d
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned int *v18; // r15
  __int64 v19; // r12
  char v20; // al
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // r13d
  unsigned int v24; // edx
  unsigned int v25; // edx
  __int64 v26; // r8
  __int64 v27; // rcx
  int v28; // edx
  union _LARGE_INTEGER *v29; // rax
  union _LARGE_INTEGER v30; // rax
  union _LARGE_INTEGER *v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  struct _KTHREAD *CurrentThread; // rsi
  __int64 v36; // rcx
  __int64 v38; // rax
  __int16 v39; // [rsp+40h] [rbp-3F8h] BYREF
  __int16 v40; // [rsp+42h] [rbp-3F6h] BYREF
  unsigned int v41; // [rsp+44h] [rbp-3F4h]
  int v42; // [rsp+48h] [rbp-3F0h]
  size_t Size; // [rsp+4Ch] [rbp-3ECh]
  union _LARGE_INTEGER *v44; // [rsp+58h] [rbp-3E0h]
  unsigned int v45; // [rsp+60h] [rbp-3D8h]
  int v46[2]; // [rsp+68h] [rbp-3D0h]
  __int64 v47; // [rsp+70h] [rbp-3C8h]
  int v48[2]; // [rsp+78h] [rbp-3C0h]
  union _LARGE_INTEGER *v49; // [rsp+80h] [rbp-3B8h]
  unsigned int v50; // [rsp+88h] [rbp-3B0h]
  __int64 v51; // [rsp+90h] [rbp-3A8h]
  unsigned int v52; // [rsp+98h] [rbp-3A0h]
  __int64 v53; // [rsp+A0h] [rbp-398h]
  __int64 v54; // [rsp+A8h] [rbp-390h]
  unsigned int v55; // [rsp+B0h] [rbp-388h]
  __int64 v56; // [rsp+B8h] [rbp-380h]
  __int64 v57; // [rsp+C0h] [rbp-378h]
  union _LARGE_INTEGER *v58; // [rsp+C8h] [rbp-370h]
  __int128 v59; // [rsp+D0h] [rbp-368h] BYREF
  _QWORD v60[96]; // [rsp+E0h] [rbp-358h] BYREF
  struct _TIME_FIELDS TimeFields; // [rsp+3E0h] [rbp-58h] BYREF

  *(_QWORD *)v46 = a3;
  v54 = a2;
  v47 = a1;
  v56 = a1;
  v57 = a2;
  v53 = a4;
  *(_QWORD *)v48 = a5;
  memset(v60, 0, sizeof(v60));
  LOBYTE(v39) = 0;
  v40 = 0;
  switch ( *(_DWORD *)(a3 + 24) )
  {
    case 1:
      v41 = 64;
      break;
    case 2:
      v41 = 68;
      break;
    case 3:
      v41 = 94;
      break;
    case 0xC:
      v41 = 12;
      break;
    case 0x25:
      v41 = 104;
      break;
    case 0x26:
      v41 = 80;
      break;
    default:
      CdCompleteRequest(a1, a2, 3221225475LL);
      return 3221225475LL;
  }
  v10 = *(_QWORD *)(a1 + 8);
  v11 = *(_QWORD *)(v10 + 8);
  if ( v11 )
  {
    if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
      v12 = *(char **)(v11 + 24);
    else
      v12 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000010u);
  }
  else
  {
    v12 = *(char **)(v10 + 112);
  }
  if ( !v12 )
    CdRaiseStatusEx(a1, 3221225626LL, 0, 720896, 286);
  v13 = 0;
  v42 = 0;
  v14 = 0;
  LODWORD(v44) = 0;
  v45 = 0;
  v15 = 0;
  v51 = 0;
  HIBYTE(v39) = 0;
  v49 = 0;
  memset(v60, 0, sizeof(v60));
  v60[0] = &v60[12];
  v60[1] = &v60[40];
  v60[2] = &v60[68];
  WORD1(v60[5]) = 24;
  v60[6] = &v60[9];
  CdAcquireResource(a1, *(_QWORD *)(a4 + 8), 0, 1);
  CdVerifyFcbOperation(a1, a4);
  CdInitializeEnumeration(a1, v46[0], a4, v48[0], v60, (__int64)&v39, (__int64)&v40, (__int64)&v40 + 1);
  v18 = (unsigned int *)(v60[1] + 32LL);
  v51 = v60[1] + 32LL;
  while ( 1 )
  {
    if ( v15 && (_BYTE)v40 )
      goto LABEL_23;
    LOBYTE(v17) = v39;
    v20 = CdEnumerateIndex(v47, *(_QWORD *)v48, v60, v17);
    LOBYTE(v39) = 1;
    if ( !v20 )
    {
      if ( !v15 )
      {
        v13 = -2147483642;
        v42 = -2147483642;
        if ( HIBYTE(v40) )
          v13 = -1073741809;
        v42 = v13;
      }
LABEL_23:
      HIBYTE(v39) = 1;
      goto LABEL_24;
    }
    v18 = (unsigned int *)(v60[1] + 32LL);
    v51 = v60[1] + 32LL;
    v21 = 0;
    Size = 0;
    v22 = 0;
    v23 = *(unsigned __int16 *)(v60[1] + 88LL);
    v50 = v23;
    if ( (*(_WORD *)(*(_QWORD *)v48 + 40LL) || (*(_BYTE *)(v60[1] + 56LL) & 2) != 0) && *(_WORD *)(v60[1] + 104LL) )
    {
      v22 = 2;
      v21 = *(unsigned __int16 *)(v60[1] + 104LL);
      Size = *(unsigned __int16 *)(v60[1] + 104LL) | 0x200000000LL;
    }
    v24 = *(_DWORD *)(*(_QWORD *)v46 + 8LL);
    if ( v15 > v24 )
      break;
    v25 = (v24 - v15) & 0xFFFFFFFE;
    v16 = v41;
    if ( v22 + v21 + v41 + v23 > v25 )
    {
      if ( v15 )
        break;
      if ( v41 + v23 > v25 )
      {
        v23 = v25 - v41;
        v50 = v25 - v41;
      }
      Size = 0;
      v13 = -2147483643;
      v42 = -2147483643;
      LOBYTE(v40) = 1;
    }
    memset(&v12[(unsigned int)v44], 0, v15 + v41 - (_DWORD)v44);
    v26 = *(_QWORD *)v46;
    if ( *(_DWORD *)(*(_QWORD *)v46 + 24LL) != 1
      && *(_DWORD *)(*(_QWORD *)v46 + 24LL) != 2
      && *(_DWORD *)(*(_QWORD *)v46 + 24LL) != 3 )
    {
      if ( *(_DWORD *)(*(_QWORD *)v46 + 24LL) == 12 )
      {
        *(_DWORD *)&v12[v15 + 4] = *v18;
        *(_DWORD *)&v12[v15 + 8] = v23 + HIDWORD(Size) + Size;
        goto LABEL_58;
      }
      if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v46 + 24LL) - 37) > 1 )
        goto LABEL_58;
    }
    v49 = (union _LARGE_INTEGER *)&v12[v15];
    v58 = v49;
    TimeFields = 0;
    TimeFields.Year = **(char **)(v60[1] + 48LL) + 1900;
    TimeFields.Month = *(char *)(*(_QWORD *)(v60[1] + 48LL) + 1LL);
    TimeFields.Day = *(char *)(*(_QWORD *)(v60[1] + 48LL) + 2LL);
    TimeFields.Hour = *(char *)(*(_QWORD *)(v60[1] + 48LL) + 3LL);
    TimeFields.Minute = *(char *)(*(_QWORD *)(v60[1] + 48LL) + 4LL);
    TimeFields.Second = *(char *)(*(_QWORD *)(v60[1] + 48LL) + 5LL);
    TimeFields.Milliseconds = 0;
    v44 = v49 + 1;
    RtlTimeFieldsToTime(&TimeFields, v49 + 1);
    if ( (*(_DWORD *)(*(_QWORD *)(v47 + 16) + 48LL) & 1) != 0
      || (v27 = *(_QWORD *)(v60[1] + 48LL), v28 = *(char *)(v27 + 6), !*(_BYTE *)(v27 + 6))
      || (unsigned __int8)(v28 + 48) > 0x64u )
    {
      v29 = v44;
    }
    else
    {
      v29 = v44;
      v44->QuadPart += 9000000000LL * -v28;
    }
    v30 = *v29;
    v31 = v49;
    v49[4] = v30;
    v31[3] = v30;
    if ( (v18[6] & 2) != 0 )
    {
      v31[6].QuadPart = 0;
      v31[5].QuadPart = 0;
      v32 = v31[7].LowPart | 0x10;
    }
    else
    {
      v31[5] = (union _LARGE_INTEGER)v60[4];
      v31[6].QuadPart = (v60[4] + 2047LL) & 0xFFFFFFFFFFFFF800uLL;
      v32 = v31[7].LowPart | 1;
    }
    v31[7].LowPart = v32;
    if ( (v18[6] & 1) != 0 )
      v31[7].LowPart |= 2u;
    v31->HighPart = *v18;
    v31[7].HighPart = v23 + HIDWORD(Size) + Size;
    v26 = *(_QWORD *)v46;
LABEL_58:
    v33 = (unsigned int)(*(_DWORD *)(v26 + 24) - 37);
    if ( *(_DWORD *)(v26 + 24) == 37 )
    {
      *(_DWORD *)&v12[v15 + 100] = *(_DWORD *)(a4 + 156);
      v33 = *v18;
      *(_DWORD *)&v12[v15 + 96] = v33;
      if ( (v18[6] & 2) != 0 )
      {
        LODWORD(v33) = v33 | 0x80000000;
        *(_DWORD *)&v12[v15 + 96] = v33;
      }
    }
    else if ( *(_DWORD *)(v26 + 24) == 38 )
    {
      *(_DWORD *)&v12[v15 + 76] = *(_DWORD *)(a4 + 156);
      v33 = *v18;
      *(_DWORD *)&v12[v15 + 72] = v33;
      if ( (v18[6] & 2) != 0 )
      {
        LODWORD(v33) = v33 | 0x80000000;
        *(_DWORD *)&v12[v15 + 72] = v33;
      }
    }
    if ( v23 )
    {
      memmove(&v12[v15 + v41], *((const void **)v18 + 8), v23);
      if ( HIDWORD(Size) )
      {
        v33 = v15 + v23 + v41;
        *(_WORD *)&v12[v33] = 59;
        if ( (_DWORD)Size )
          memmove(&v12[v33 + 2], *((const void **)v18 + 10), (unsigned int)Size);
      }
      v26 = *(_QWORD *)v46;
    }
    if ( !v13 )
    {
      v34 = *(_DWORD *)(v26 + 24);
      if ( (v34 == 3 || v34 == 37) && !*(_WORD *)(*(_QWORD *)v48 + 40LL) && (*((_BYTE *)v18 + 25) & 2) == 0 )
      {
        if ( LOWORD(v60[5]) )
        {
          memmove((char *)&v49[8].QuadPart + 6, (const void *)v60[6], LOWORD(v60[5]));
        }
        else
        {
          v59 = *(_OWORD *)(v18 + 14);
          if ( (unsigned __int8)CdIs8dot3Name(v33, &v59) )
            goto LABEL_79;
          CdGenerate8dot3Name(v47, v18 + 22, *v18, (char *)&v49[8].QuadPart + 6, &v60[5]);
        }
        BYTE4(v49[8].QuadPart) = v60[5];
      }
    }
LABEL_79:
    v50 = HIDWORD(Size) + Size + v23;
    v14 = v15 + v41 + v50;
    LODWORD(v44) = v14;
    v52 = v14;
    v16 = v15 - v45;
    *(_DWORD *)&v12[v45] = v16;
    HIBYTE(v40) = 0;
    v45 = v15;
    v15 = (v14 + 7) & 0xFFFFFFF8;
    v55 = v15;
  }
  v39 = 256;
  v13 = 0;
  v42 = 0;
  v14 = (unsigned int)v44;
LABEL_24:
  v19 = v47;
  CdCleanupFileContext(v16, v60);
  if ( (v13 & 0xC0000000) != 0xC0000000 )
  {
    CurrentThread = KeGetCurrentThread();
    if ( CurrentThread != *(struct _KTHREAD **)(a4 + 184) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a4 + 200) + 136LL));
      *(_QWORD *)(a4 + 184) = CurrentThread;
    }
    ++*(_DWORD *)(a4 + 192);
    v36 = *(_QWORD *)v48;
    *(_DWORD *)(*(_QWORD *)v48 + 16LL) = *v18;
    *(_DWORD *)(v36 + 4) &= ~0x100000u;
    if ( (_BYTE)v39 )
      *(_DWORD *)(v36 + 4) |= 0x100000u;
    if ( (*(_DWORD *)(a4 + 192))-- == 1 )
    {
      *(_QWORD *)(a4 + 184) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a4 + 200) + 136LL));
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)(a4 + 8));
  v38 = v54;
  *(_QWORD *)(v54 + 56) = v14;
  CdCompleteRequest(v19, v38, v13);
  return v13;
}

```

## disassembly

```asm
0x140011744  push    rbx
0x140011746  push    rsi
0x140011747  push    rdi
0x140011748  push    r12
0x14001174a  push    r13
0x14001174c  push    r14
0x14001174e  push    r15
0x140011750  sub     rsp, 400h
0x140011757  mov     rax, cs:__security_cookie
0x14001175e  xor     rax, rsp
0x140011761  mov     [rsp+438h+var_48], rax
0x140011769  mov     r14, r9
0x14001176c  mov     rdi, r8
0x14001176f  mov     qword ptr [rsp+438h+var_3D0], r8
0x140011774  mov     rsi, rdx
0x140011777  mov     [rsp+438h+var_390], rdx
0x14001177f  mov     r15, rcx
0x140011782  mov     [rsp+438h+var_3C8], rcx
0x140011787  mov     [rsp+438h+var_380], rcx
0x14001178f  mov     [rsp+438h+var_378], rdx
0x140011797  mov     [rsp+438h+var_398], r9
0x14001179f  mov     rax, [rsp+438h+arg_20]
0x1400117a7  mov     qword ptr [rsp+438h+var_3C0], rax
0x1400117ac  xor     edx, edx; Val
0x1400117ae  mov     r8d, 300h; Size
0x1400117b4  lea     rcx, [rsp+438h+var_358]; void *
0x1400117bc  call    memset
0x1400117c1  xor     ebx, ebx
0x1400117c3  mov     byte ptr [rsp+438h+var_3F8+3], bl
0x1400117c7  mov     byte ptr [rsp+438h+var_3F8], bl
0x1400117cb  mov     byte ptr [rsp+438h+var_3F8+2], bl
0x1400117cf  mov     r8d, [rdi+18h]
0x1400117d3  sub     r8d, 1
0x1400117d7  jz      loc_140011866
0x1400117dd  sub     r8d, 1
0x1400117e1  jz      short loc_14001185C
0x1400117e3  sub     r8d, 1
0x1400117e7  jz      short loc_140011852
0x1400117e9  sub     r8d, 9
0x1400117ed  jz      short loc_140011848
0x1400117ef  sub     r8d, 19h
0x1400117f3  jz      short loc_14001183E
0x1400117f5  cmp     r8d, 1
0x1400117f9  jz      short loc_140011834
0x1400117fb  mov     ebx, 0C0000003h
0x140011800  mov     r8d, ebx
0x140011803  mov     rdx, rsi
0x140011806  mov     rcx, r15
0x140011809  call    CdCompleteRequest
0x14001180e  mov     eax, ebx
0x140011810  mov     rcx, [rsp+438h+var_48]
0x140011818  xor     rcx, rsp; StackCookie
0x14001181b  call    __security_check_cookie
0x140011820  add     rsp, 400h
0x140011827  pop     r15
0x140011829  pop     r14
0x14001182b  pop     r13
0x14001182d  pop     r12
0x14001182f  pop     rdi
0x140011830  pop     rsi
0x140011831  pop     rbx
0x140011832  retn
0x140011834  mov     dword ptr [rsp+438h+var_3F8+4], 50h ; 'P'
0x14001183c  jmp     short loc_14001186E
0x14001183e  mov     dword ptr [rsp+438h+var_3F8+4], 68h ; 'h'
0x140011846  jmp     short loc_14001186E
0x140011848  mov     dword ptr [rsp+438h+var_3F8+4], 0Ch
0x140011850  jmp     short loc_14001186E
0x140011852  mov     dword ptr [rsp+438h+var_3F8+4], 5Eh ; '^'
0x14001185a  jmp     short loc_14001186E
0x14001185c  mov     dword ptr [rsp+438h+var_3F8+4], 44h ; 'D'
0x140011864  jmp     short loc_14001186E
0x140011866  mov     dword ptr [rsp+438h+var_3F8+4], 40h ; '@'
0x14001186e  mov     rsi, [r15+8]
0x140011872  mov     rcx, [rsi+8]; MemoryDescriptorList
0x140011876  test    rcx, rcx
0x140011879  jnz     short loc_140011881
0x14001187b  mov     rsi, [rsi+70h]
0x14001187f  jmp     short loc_1400118B1
0x140011881  test    byte ptr [rcx+0Ah], 5
0x140011885  jz      short loc_14001188D
0x140011887  mov     rsi, [rcx+18h]
0x14001188b  jmp     short loc_1400118B1
0x14001188d  mov     [rsp+438h+Priority], 40000010h; Priority
0x140011895  mov     [rsp+438h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x140011899  xor     r9d, r9d; RequestedAddress
0x14001189c  xor     edx, edx; AccessMode
0x14001189e  lea     r8d, [r9+1]; CacheType
0x1400118a2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400118a9  nop     dword ptr [rax+rax+00h]
0x1400118ae  mov     rsi, rax
0x1400118b1  test    rsi, rsi
0x1400118b4  jz      loc_140011FAC
0x1400118ba  mov     edi, ebx
0x1400118bc  mov     [rsp+438h+var_3F0], ebx
0x1400118c0  mov     r13d, ebx
0x1400118c3  mov     dword ptr [rsp+438h+var_3E0], ebx
0x1400118c7  mov     [rsp+438h+var_3D8], ebx
0x1400118cb  mov     r12d, ebx
0x1400118ce  mov     [rsp+438h+var_3A8], rbx
0x1400118d6  mov     byte ptr [rsp+438h+var_3F8+1], bl
0x1400118da  mov     [rsp+438h+var_3B8], rbx
0x1400118e2  xor     edx, edx; Val
0x1400118e4  mov     r8d, 300h; Size
0x1400118ea  lea     rcx, [rsp+438h+var_358]; void *
0x1400118f2  call    memset
0x1400118f7  lea     rax, [rsp+438h+var_2F8]
0x1400118ff  mov     [rsp+438h+var_358], rax
0x140011907  lea     rax, [rsp+438h+var_218]
0x14001190f  mov     [rsp+438h+var_350], rax
0x140011917  lea     rax, [rsp+438h+var_138]
0x14001191f  mov     [rsp+438h+var_348], rax
0x140011927  mov     eax, 18h
0x14001192c  mov     [rsp+438h+var_32E], ax
0x140011934  lea     rax, [rsp+438h+var_310]
0x14001193c  mov     [rsp+438h+Src], rax
0x140011944  mov     r9d, 1
0x14001194a  xor     r8d, r8d
0x14001194d  mov     rdx, [r14+8]
0x140011951  mov     rcx, r15
0x140011954  call    CdAcquireResource
0x140011959  nop
0x14001195a  mov     rdx, r14
0x14001195d  mov     rcx, r15
0x140011960  call    CdVerifyFcbOperation
0x140011965  lea     rax, [rsp+438h+var_3F8+3]
0x14001196a  mov     [rsp+438h+var_400], rax; __int64
0x14001196f  lea     rax, [rsp+438h+var_3F8+2]
0x140011974  mov     [rsp+438h+var_408], rax; __int64
0x140011979  lea     rax, [rsp+438h+var_3F8]
0x14001197e  mov     qword ptr [rsp+438h+Priority], rax; __int64
0x140011983  lea     rax, [rsp+438h+var_358]
0x14001198b  mov     qword ptr [rsp+438h+BugCheckOnFailure], rax; void *
0x140011990  mov     r9, qword ptr [rsp+438h+var_3C0]; int
0x140011995  mov     r8, r14; int
0x140011998  mov     rdx, qword ptr [rsp+438h+var_3D0]; int
0x14001199d  mov     rcx, r15; int
0x1400119a0  call    CdInitializeEnumeration
0x1400119a5  mov     rax, [rsp+438h+var_350]
0x1400119ad  lea     r15, [rax+20h]
0x1400119b1  mov     [rsp+438h+var_3A8], r15
0x1400119b9  test    r12d, r12d
0x1400119bc  jz      short loc_1400119D6
0x1400119be  cmp     byte ptr [rsp+438h+var_3F8+2], bl
0x1400119c2  jz      short loc_1400119D6
0x1400119c4  mov     sil, 1
0x1400119c7  mov     byte ptr [rsp+438h+var_3F8+1], sil
0x1400119cc  mov     r12, [rsp+438h+var_3C8]
0x1400119d1  jmp     loc_140011ED1
0x1400119d6  mov     r9b, byte ptr [rsp+438h+var_3F8]
0x1400119db  lea     r8, [rsp+438h+var_358]
0x1400119e3  mov     rdx, qword ptr [rsp+438h+var_3C0]
0x1400119e8  mov     rcx, [rsp+438h+var_3C8]
0x1400119ed  call    CdEnumerateIndex
0x1400119f2  mov     byte ptr [rsp+438h+var_3F8], 1
0x1400119f7  test    al, al
0x1400119f9  jnz     short loc_140011A1B
0x1400119fb  test    r12d, r12d
0x1400119fe  jnz     short loc_1400119C4
0x140011a00  mov     edi, 80000006h
0x140011a05  mov     [rsp+438h+var_3F0], edi
0x140011a09  mov     eax, 0C000000Fh
0x140011a0e  cmp     byte ptr [rsp+438h+var_3F8+3], bl
0x140011a12  cmovnz  edi, eax
0x140011a15  mov     [rsp+438h+var_3F0], edi
0x140011a19  jmp     short loc_1400119C4
0x140011a1b  mov     r15, [rsp+438h+var_350]
0x140011a23  add     r15, 20h ; ' '
0x140011a27  mov     [rsp+438h+var_3A8], r15
0x140011a2f  mov     r8d, ebx
0x140011a32  mov     dword ptr [rsp+438h+Size], ebx
0x140011a36  mov     r9d, ebx
0x140011a39  mov     dword ptr [rsp+438h+Size+4], ebx
0x140011a3d  movzx   r13d, word ptr [r15+38h]
0x140011a42  mov     [rsp+438h+var_3B0], r13d
0x140011a4a  mov     rax, qword ptr [rsp+438h+var_3C0]
0x140011a4f  cmp     [rax+28h], bx
0x140011a53  jnz     short loc_140011A5C
0x140011a55  test    byte ptr [r15+18h], 2
0x140011a5a  jz      short loc_140011A78
0x140011a5c  movzx   eax, word ptr [r15+48h]
0x140011a61  test    ax, ax
0x140011a64  jz      short loc_140011A78
0x140011a66  mov     r9d, 2
0x140011a6c  mov     dword ptr [rsp+438h+Size+4], r9d
0x140011a71  mov     r8d, eax
0x140011a74  mov     dword ptr [rsp+438h+Size], eax
0x140011a78  mov     rax, qword ptr [rsp+438h+var_3D0]
0x140011a7d  mov     edx, [rax+8]
0x140011a80  cmp     r12d, edx
0x140011a83  jbe     short loc_140011AA1
0x140011a85  mov     byte ptr [rsp+438h+var_3F8], bl
0x140011a89  mov     sil, 1
0x140011a8c  mov     byte ptr [rsp+438h+var_3F8+1], sil
0x140011a91  mov     edi, ebx
0x140011a93  mov     [rsp+438h+var_3F0], ebx
0x140011a97  mov     r13d, dword ptr [rsp+438h+var_3E0]
0x140011a9c  jmp     loc_1400119CC
0x140011aa1  sub     edx, r12d
0x140011aa4  and     edx, 0FFFFFFFEh
0x140011aa7  mov     ecx, dword ptr [rsp+438h+var_3F8+4]
0x140011aab  lea     eax, [rcx+r13]
0x140011aaf  add     eax, r8d
0x140011ab2  add     eax, r9d
0x140011ab5  cmp     eax, edx
0x140011ab7  jbe     short loc_140011AEA
0x140011ab9  test    r12d, r12d
0x140011abc  jnz     short loc_140011A85
0x140011abe  lea     eax, [rcx+r13]
0x140011ac2  cmp     eax, edx
0x140011ac4  jbe     short loc_140011AD4
0x140011ac6  mov     r13d, edx
0x140011ac9  sub     r13d, ecx
0x140011acc  mov     [rsp+438h+var_3B0], r13d
0x140011ad4  mov     dword ptr [rsp+438h+Size+4], ebx
0x140011ad8  mov     dword ptr [rsp+438h+Size], ebx
0x140011adc  mov     edi, 80000005h
0x140011ae1  mov     [rsp+438h+var_3F0], edi
0x140011ae5  mov     byte ptr [rsp+438h+var_3F8+2], 1
0x140011aea  mov     r8d, ecx
0x140011aed  mov     ecx, dword ptr [rsp+438h+var_3E0]
0x140011af1  sub     r8d, ecx
0x140011af4  add     r8d, r12d; Size
0x140011af7  add     rcx, rsi; void *
0x140011afa  xor     edx, edx; Val
0x140011afc  call    memset
0x140011b01  mov     r8, qword ptr [rsp+438h+var_3D0]
0x140011b06  mov     ecx, [r8+18h]
0x140011b0a  sub     ecx, 1
0x140011b0d  jz      short loc_140011B30
0x140011b0f  sub     ecx, 1
0x140011b12  jz      short loc_140011B30
0x140011b14  sub     ecx, 1
0x140011b17  jz      short loc_140011B30
0x140011b19  sub     ecx, 9
0x140011b1c  jz      loc_140011C33
0x140011b22  sub     ecx, 19h
0x140011b25  jz      short loc_140011B30
0x140011b27  cmp     ecx, 1
0x140011b2a  jnz     loc_140011CD1
0x140011b30  mov     r8d, r12d
0x140011b33  add     r8, rsi
0x140011b36  mov     [rsp+438h+var_3B8], r8
0x140011b3e  mov     [rsp+438h+var_370], r8
0x140011b46  xorps   xmm0, xmm0
0x140011b49  movups  xmmword ptr [rsp+438h+TimeFields.Year], xmm0
0x140011b51  mov     rdx, [rsp+438h+var_350]
0x140011b59  mov     rax, [rdx+30h]
0x140011b5d  movsx   ecx, byte ptr [rax]
0x140011b60  mov     eax, 76Ch
0x140011b65  add     cx, ax
0x140011b68  mov     [rsp+438h+TimeFields.Year], cx
0x140011b70  mov     rax, [rdx+30h]
0x140011b74  movsx   ecx, byte ptr [rax+1]
0x140011b78  mov     [rsp+438h+TimeFields.Month], cx
0x140011b80  mov     rax, [rdx+30h]
0x140011b84  movsx   ecx, byte ptr [rax+2]
0x140011b88  mov     [rsp+438h+TimeFields.Day], cx
0x140011b90  mov     rax, [rdx+30h]
0x140011b94  movsx   ecx, byte ptr [rax+3]
0x140011b98  mov     [rsp+438h+TimeFields.Hour], cx
0x140011ba0  mov     rax, [rdx+30h]
0x140011ba4  movsx   ecx, byte ptr [rax+4]
0x140011ba8  mov     [rsp+438h+TimeFields.Minute], cx
0x140011bb0  mov     rax, [rdx+30h]
0x140011bb4  movsx   ecx, byte ptr [rax+5]
0x140011bb8  mov     [rsp+438h+TimeFields.Second], cx
0x140011bc0  mov     [rsp+438h+TimeFields.Milliseconds], bx
0x140011bc8  lea     rax, [r8+8]
0x140011bcc  mov     [rsp+438h+var_3E0], rax
0x140011bd1  mov     rdx, rax; Time
0x140011bd4  lea     rcx, [rsp+438h+TimeFields]; TimeFields
0x140011bdc  call    cs:__imp_RtlTimeFieldsToTime
0x140011be3  nop     dword ptr [rax+rax+00h]
0x140011be8  mov     rcx, [rsp+438h+var_3C8]
0x140011bed  mov     rax, [rcx+10h]
0x140011bf1  mov     ecx, [rax+30h]
0x140011bf4  test    cl, 1
0x140011bf7  jnz     short loc_140011C51
0x140011bf9  mov     rax, [rsp+438h+var_350]
0x140011c01  mov     rcx, [rax+30h]
0x140011c05  movsx   edx, byte ptr [rcx+6]
0x140011c09  test    dl, dl
0x140011c0b  jz      short loc_140011C51
0x140011c0d  lea     eax, [rdx+30h]
0x140011c10  cmp     al, 64h ; 'd'
0x140011c12  ja      short loc_140011C51
0x140011c14  mov     eax, edx
0x140011c16  neg     eax
0x140011c18  movsxd  rcx, eax
0x140011c1b  mov     rax, 218711A00h
0x140011c25  imul    rcx, rax
0x140011c29  mov     rax, [rsp+438h+var_3E0]
0x140011c2e  add     [rax], rcx
0x140011c31  jmp     short loc_140011C56
0x140011c33  mov     ecx, r12d
0x140011c36  mov     eax, [r15]
0x140011c39  mov     [rcx+rsi+4], eax
0x140011c3d  mov     eax, dword ptr [rsp+438h+Size]
0x140011c41  add     eax, dword ptr [rsp+438h+Size+4]
  ... truncated ...
```
