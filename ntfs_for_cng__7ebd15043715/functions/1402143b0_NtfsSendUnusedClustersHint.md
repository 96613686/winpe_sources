# NtfsSendUnusedClustersHint

- ea: `0x1402143b0`
- end: `0x140214979`
- name: `NtfsSendUnusedClustersHint`
- size: `1481`
- prototype: `void __fastcall(_QWORD *, LONGLONG, unsigned int, PVOID *, _BYTE *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400cb8c4`
- `0x14020f350`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14003c184`
- `0x14003c210`
- `0x140040030`
- `0x1400400d8`
- `0x14004062c`
- `0x140040d48`
- `0x1400410a8`
- `0x1400596c0`
- `0x14014dde0`
- `0x1402143b0`
- `0x1402434fc`

## import_xrefs

- `ntoskrnl!FsRtlLookupLastBaseMcbEntryAndIndex` at `0x1402147a3`
- `ntoskrnl!FsRtlLookupLastBaseMcbEntryAndIndex` at `0x1402147a3`
- `ntoskrnl!IoGetActivityIdThread` at `0x140214566`
- `ntoskrnl!IoGetActivityIdThread` at `0x140214566`
- `ntoskrnl!FsRtlAddBaseMcbEntryEx` at `0x140214641`
- `ntoskrnl!FsRtlAddBaseMcbEntryEx` at `0x140214641`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140214896`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402148ba`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402148d5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4e4e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4e7c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4e99`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140214896`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402148ba`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402148d5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4e4e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4e7c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4e99`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140214880`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402b4e37`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140214880`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402b4e37`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x1402144c4`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x1402144c4`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140214485`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402144dc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14021450d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140214485`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402144dc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14021450d`

## pseudocode

```c
void __fastcall NtfsSendUnusedClustersHint(_QWORD *a1, LONGLONG a2, unsigned int a3, PVOID *a4, _BYTE *a5)
{
  LONGLONG v6; // r13
  __int64 v8; // rsi
  __int64 v9; // r14
  char *v10; // r15
  char v11; // bl
  char *v12; // rax
  _OWORD *v13; // rax
  _QWORD *v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  _OWORD *v18; // rax
  _OWORD *ActivityIdThread; // rax
  _DWORD *v20; // rbx
  __int64 v21; // rdx
  _QWORD *v22; // r8
  unsigned int v23; // eax
  _QWORD *v24; // r8
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  unsigned int v27; // eax
  _QWORD *v28; // rdx
  _QWORD *v29; // rax
  void *v30; // rdx
  __int64 v31; // [rsp+20h] [rbp-78h]
  char v32; // [rsp+40h] [rbp-58h]
  ULONG Index; // [rsp+44h] [rbp-54h] BYREF
  __int64 v34; // [rsp+48h] [rbp-50h]
  __int64 LargeVbn; // [rsp+50h] [rbp-48h] BYREF
  char *v36; // [rsp+58h] [rbp-40h]
  __int64 v37; // [rsp+60h] [rbp-38h]

  v6 = a3;
  v8 = (__int64)a1;
  v37 = a1[13];
  v9 = v37;
  v10 = 0;
  v36 = 0;
  v11 = 0;
  v32 = 0;
  if ( !*(_BYTE *)(v37 + 5521) )
  {
    if ( a2 || a3 )
    {
      if ( (a1[2] & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0ppd_EtwWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)delnotify_c196, v37, a2, a3);
      }
    }
    else if ( (a1[2] & 0x100000LL) == 0
           && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0p_EtwWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)delnotify_c206, v37);
    }
    if ( *a4 )
    {
      v20 = (_DWORD *)*((_QWORD *)*a4 + 4);
    }
    else
    {
      if ( !(_DWORD)v6
        || *a5
        || (v12 = (char *)ExAllocateFromLookasideListEx(&NtfsDeallocatedClustersLookasideList),
            v10 = v12,
            (v36 = v12) == 0) )
      {
        v11 = 0;
        goto LABEL_54;
      }
      *(_OWORD *)v12 = 0;
      *((_OWORD *)v12 + 1) = 0;
      *((_OWORD *)v12 + 2) = 0;
      *((_OWORD *)v12 + 3) = 0;
      FsRtlInitializeBaseMcbEx((PBASE_MCB)(v12 + 16), PoolType, 1u);
      v32 = 1;
      v13 = ExAllocateFromLookasideListEx(&NtfsMarkUnusedContextLookasideList);
      *a4 = v13;
      *v13 = 0;
      v13[1] = 0;
      v13[2] = 0;
      v13[3] = 0;
      *((_QWORD *)v13 + 8) = 0;
      v14 = *a4;
      v14[4] = ExAllocateFromLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList);
      memset(*((void **)*a4 + 4), 0, 0x400u);
      *((_DWORD *)v10 + 14) |= 1u;
      *((_QWORD *)*a4 + 3) = v10;
      v10 = 0;
      v36 = 0;
      v17 = (char *)*a4;
      v18 = *(_OWORD **)(v8 + 120);
      if ( v18 )
      {
        *(_OWORD *)(v17 + 56) = *v18;
        *((_QWORD *)v17 + 6) = v17 + 56;
      }
      else
      {
        ActivityIdThread = (_OWORD *)IoGetActivityIdThread(v16);
        if ( ActivityIdThread )
        {
          *(_OWORD *)(v17 + 56) = *ActivityIdThread;
          *((_QWORD *)v17 + 6) = v17 + 56;
        }
        else
        {
          *((_QWORD *)v17 + 6) = 0;
        }
      }
      *((_QWORD *)*a4 + 2) = v9;
      v20 = (_DWORD *)*((_QWORD *)*a4 + 4);
      *v20 = 1024;
      v20[1] = 1;
      v20[2] = 0x80000000;
      v20[5] = 32;
      if ( (*(_DWORD *)(v8 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        v31 = *((_QWORD *)*a4 + 3);
        McTemplateU0pppp_EtwWriteTransfer(v31, v15, v9);
      }
    }
    Index = v20[5];
    LODWORD(LargeVbn) = (*v20 - Index) & 0xFFFFFFF0;
    if ( !(_DWORD)v6 )
      goto LABEL_36;
    if ( !a2 )
    {
      v34 = 0xD30039016CLL;
      NtfsAttachCorruptionSimple(v8, 1u, 2050, 3735916, 0);
      NtfsAttachRepairInfoPriv(v8, 0, 0, (struct _LIST_ENTRY *)0xD30039016CLL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v8, 0xC0000032, 0x39016Cu);
      NtfsRaiseStatusInternal(v8, -1073741774, 0, 0, 3735916);
    }
    a1 = a5;
    if ( !*a5 )
    {
      LODWORD(v34) = v20[6];
      if ( FsRtlAddBaseMcbEntryEx((PBASE_MCB)(*((_QWORD *)*a4 + 3) + 16LL), a2, a2, v6) >= 0 )
      {
        v22 = (_QWORD *)((char *)v20 + (unsigned int)v34 + Index);
        v34 = (__int64)v22;
        if ( (*(_DWORD *)(v8 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          LODWORD(v31) = v6;
          McTemplateU0pidp_EtwWriteTransfer(*((_QWORD *)*a4 + 3) + 16LL, v21, v9, a2, v31, *((_QWORD *)*a4 + 3) + 16LL);
          v22 = (_QWORD *)v34;
        }
        *v22 = a2 << *(_BYTE *)(v9 + 488);
        v22[1] = v6 << *(_BYTE *)(v9 + 488);
        v20[6] += 16;
        *(_QWORD *)(*((_QWORD *)*a4 + 3) + 48LL) += v6;
        goto LABEL_36;
      }
      a1 = a5;
    }
    *(_BYTE *)a1 = 1;
    if ( (*(_DWORD *)(v8 + 16) & 0x100000) != 0
      || (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) == 0 )
    {
LABEL_37:
      v23 = v20[6];
      if ( v23 >= (unsigned int)LargeVbn || (*(_BYTE *)a1 || !(_DWORD)v6) && v23 )
      {
        v24 = *(_QWORD **)(v9 + 1616);
        if ( *v24 != v9 + 1608 )
          __fastfail(3u);
        v25 = (_QWORD *)*((_QWORD *)*a4 + 3);
        *v25 = v9 + 1608;
        v25[1] = v24;
        *v24 = v25;
        *(_QWORD *)(v9 + 1616) = v25;
        *(_QWORD *)(v9 + 312) += *(_QWORD *)(*((_QWORD *)*a4 + 3) + 48LL);
        *((_QWORD *)*a4 + 5) = *(_QWORD *)(*((_QWORD *)*a4 + 3) + 48LL);
        Index = 0;
        LargeVbn = 0;
        FsRtlLookupLastBaseMcbEntryAndIndex((PBASE_MCB)(*((_QWORD *)*a4 + 3) + 16LL), &LargeVbn, &LargeVbn, &Index);
        *(_DWORD *)(v9 + 1512) += Index;
        v27 = *(_DWORD *)(v9 + 1512);
        if ( *(_DWORD *)(v9 + 8964) < v27 )
          *(_DWORD *)(v9 + 8964) = v27;
        if ( (*(_DWORD *)(v8 + 16) & 0x100000LL) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0ppp_EtwWriteTransfer(v26, (const EVENT_DESCRIPTOR *)delnotify_c508, v9, *a4, v8);
        }
        *v20 = 28;
        a1 = (_QWORD *)(v8 + 464);
        v28 = *(_QWORD **)(v8 + 472);
        if ( *v28 != v8 + 464 )
          __fastfail(3u);
        v29 = *a4;
        *v29 = a1;
        v29[1] = v28;
        *v28 = v29;
        *(_QWORD *)(v8 + 472) = v29;
        *a4 = 0;
      }
      v11 = v32;
      goto LABEL_54;
    }
    McTemplateU0pp_EtwWriteTransfer(
      (__int64)a1,
      (const EVENT_DESCRIPTOR *)delnotify_c427,
      v9,
      *((_QWORD *)*a4 + 3) + 16LL);
LABEL_36:
    a1 = a5;
    goto LABEL_37;
  }
  a1 = *a4;
  if ( *a4 )
  {
    NtfsFreeMarkUnusedContext(a1);
    *a4 = 0;
  }
LABEL_54:
  if ( v10 )
  {
    if ( (*(_DWORD *)(v8 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000) != 0 )
    {
      McTemplateU0p_EtwWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)delnotify_c557, v9);
    }
    if ( v11 )
      FsRtlUninitializeBaseMcb((PBASE_MCB)(v10 + 16));
    ExFreeToLookasideListEx(&NtfsDeallocatedClustersLookasideList, v10);
    if ( *a4 )
    {
      v30 = (void *)*((_QWORD *)*a4 + 4);
      if ( v30 )
        ExFreeToLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList, v30);
    }
    if ( *a4 )
    {
      ExFreeToLookasideListEx(&NtfsMarkUnusedContextLookasideList, *a4);
      *a4 = 0;
    }
  }
}

```

## disassembly

```asm
0x1402143b0  mov     [rsp+arg_8], rbx
0x1402143b5  mov     [rsp+arg_10], rsi
0x1402143ba  mov     [rsp+arg_18], r9
0x1402143bf  mov     [rsp+arg_0], rcx
0x1402143c4  push    rdi
0x1402143c5  push    r12
0x1402143c7  push    r13
0x1402143c9  push    r14
0x1402143cb  push    r15
0x1402143cd  sub     rsp, 70h
0x1402143d1  mov     rdi, r9
0x1402143d4  mov     r13d, r8d
0x1402143d7  mov     r12, rdx
0x1402143da  mov     rsi, rcx
0x1402143dd  mov     r14, [rcx+68h]
0x1402143e1  mov     [rsp+98h+var_38], r14
0x1402143e6  xor     r15d, r15d
0x1402143e9  mov     [rsp+98h+var_40], r15
0x1402143ee  xor     bl, bl
0x1402143f0  mov     [rsp+98h+var_58], bl
0x1402143f4  cmp     [r14+1591h], bl
0x1402143fb  jnz     loc_140214832
0x140214401  test    rdx, rdx
0x140214404  jnz     short loc_14021442F
0x140214406  test    r8d, r8d
0x140214409  jnz     short loc_14021442F
0x14021440b  mov     eax, [rcx+10h]
0x14021440e  bt      rax, 14h
0x140214413  jb      short loc_140214459
0x140214415  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14021441c  jz      short loc_140214459
0x14021441e  mov     r8, r14
0x140214421  lea     rdx, delnotify_c206
0x140214428  call    McTemplateU0p_EtwWriteTransfer
0x14021442d  jmp     short loc_140214459
0x14021442f  mov     eax, [rcx+10h]
0x140214432  bt      rax, 14h
0x140214437  jb      short loc_140214459
0x140214439  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x140214440  jz      short loc_140214459
0x140214442  mov     dword ptr [rsp+98h+var_78], r13d
0x140214447  mov     r9, r12
0x14021444a  mov     r8, r14
0x14021444d  lea     rdx, delnotify_c196
0x140214454  call    McTemplateU0ppd_EtwWriteTransfer
0x140214459  mov     rbx, [rdi]
0x14021445c  test    rbx, rbx
0x14021445f  jnz     loc_1402145ED
0x140214465  test    r13d, r13d
0x140214468  jz      loc_1402145E6
0x14021446e  mov     rax, [rsp+98h+arg_20]
0x140214476  cmp     [rax], bl
0x140214478  jnz     loc_1402145E6
0x14021447e  lea     rcx, NtfsDeallocatedClustersLookasideList; Lookaside
0x140214485  call    cs:__imp_ExAllocateFromLookasideListEx
0x14021448c  nop     dword ptr [rax+rax+00h]
0x140214491  mov     r15, rax
0x140214494  mov     [rsp+98h+var_40], rax
0x140214499  test    rax, rax
0x14021449c  jz      loc_1402145E6
0x1402144a2  xorps   xmm0, xmm0
0x1402144a5  movups  xmmword ptr [rax], xmm0
0x1402144a8  movups  xmmword ptr [rax+10h], xmm0
0x1402144ac  movups  xmmword ptr [rax+20h], xmm0
0x1402144b0  movups  xmmword ptr [rax+30h], xmm0
0x1402144b4  mov     r8d, 1; Flags
0x1402144ba  lea     rcx, [rax+10h]; Mcb
0x1402144be  mov     edx, cs:PoolType; PoolType
0x1402144c4  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x1402144cb  nop     dword ptr [rax+rax+00h]
0x1402144d0  mov     [rsp+98h+var_58], 1
0x1402144d5  lea     rcx, NtfsMarkUnusedContextLookasideList; Lookaside
0x1402144dc  call    cs:__imp_ExAllocateFromLookasideListEx
0x1402144e3  nop     dword ptr [rax+rax+00h]
0x1402144e8  mov     [rdi], rax
0x1402144eb  xorps   xmm0, xmm0
0x1402144ee  xor     ecx, ecx
0x1402144f0  movups  xmmword ptr [rax], xmm0
0x1402144f3  movups  xmmword ptr [rax+10h], xmm0
0x1402144f7  movups  xmmword ptr [rax+20h], xmm0
0x1402144fb  movups  xmmword ptr [rax+30h], xmm0
0x1402144ff  mov     [rax+40h], rcx
0x140214503  mov     rbx, [rdi]
0x140214506  lea     rcx, NtfsDeviceManageDataSetAttributesLookasideList; Lookaside
0x14021450d  call    cs:__imp_ExAllocateFromLookasideListEx
0x140214514  nop     dword ptr [rax+rax+00h]
0x140214519  mov     [rbx+20h], rax
0x14021451d  mov     rcx, [rdi]
0x140214520  xor     edx, edx; Val
0x140214522  mov     r8d, 400h; Size
0x140214528  mov     rcx, [rcx+20h]; void *
0x14021452c  call    memset
0x140214531  or      dword ptr [r15+38h], 1
0x140214536  mov     rax, [rdi]
0x140214539  mov     [rax+18h], r15
0x14021453d  xor     r15d, r15d
0x140214540  mov     [rsp+98h+var_40], r15
0x140214545  mov     rbx, [rdi]
0x140214548  mov     rax, [rsi+78h]
0x14021454c  test    rax, rax
0x14021454f  jz      short loc_140214566
0x140214551  movups  xmm0, xmmword ptr [rax]
0x140214554  movups  xmmword ptr [rbx+38h], xmm0
0x140214558  lea     rax, [rbx+38h]
0x14021455c  mov     [rbx+30h], rax
0x140214560  mov     rax, [rbx+30h]
0x140214564  jmp     short loc_14021458B
0x140214566  call    cs:__imp_IoGetActivityIdThread
0x14021456d  nop     dword ptr [rax+rax+00h]
0x140214572  test    rax, rax
0x140214575  jz      short loc_140214587
0x140214577  lea     rcx, [rbx+38h]
0x14021457b  movups  xmm0, xmmword ptr [rax]
0x14021457e  movups  xmmword ptr [rcx], xmm0
0x140214581  mov     [rbx+30h], rcx
0x140214585  jmp     short loc_14021458B
0x140214587  mov     [rbx+30h], r15
0x14021458b  mov     rax, [rdi]
0x14021458e  mov     [rax+10h], r14
0x140214592  mov     rax, [rdi]
0x140214595  mov     rbx, [rax+20h]
0x140214599  mov     dword ptr [rbx], 400h
0x14021459f  mov     dword ptr [rbx+4], 1
0x1402145a6  mov     dword ptr [rbx+8], 80000000h
0x1402145ad  mov     dword ptr [rbx+14h], 20h ; ' '
0x1402145b4  mov     eax, [rsi+10h]
0x1402145b7  bt      rax, 14h
0x1402145bc  jb      short loc_1402145F1
0x1402145be  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x1402145c5  jz      short loc_1402145F1
0x1402145c7  mov     r9, [rdi]
0x1402145ca  mov     rcx, [r9+18h]
0x1402145ce  lea     rax, [rcx+10h]
0x1402145d2  mov     [rsp+98h+var_70], rax
0x1402145d7  mov     [rsp+98h+var_78], rcx
0x1402145dc  mov     r8, r14
0x1402145df  call    McTemplateU0pppp_EtwWriteTransfer
0x1402145e4  jmp     short loc_1402145F1
0x1402145e6  xor     bl, bl
0x1402145e8  jmp     loc_14021484D
0x1402145ed  mov     rbx, [rbx+20h]
0x1402145f1  mov     eax, [rbx+14h]
0x1402145f4  mov     [rsp+98h+Index], eax
0x1402145f8  mov     ecx, [rbx]
0x1402145fa  sub     ecx, eax
0x1402145fc  and     ecx, 0FFFFFFF0h
0x1402145ff  mov     dword ptr [rsp+98h+LargeVbn], ecx
0x140214603  test    r13d, r13d
0x140214606  jz      loc_140214704
0x14021460c  test    r12, r12
0x14021460f  jz      loc_140214903
0x140214615  mov     rcx, [rsp+98h+arg_20]
0x14021461d  cmp     byte ptr [rcx], 0
0x140214620  jnz     loc_1402146D4
0x140214626  mov     eax, [rbx+18h]
0x140214629  mov     dword ptr [rsp+98h+var_50], eax
0x14021462d  mov     r9, r13; SectorCount
0x140214630  mov     rax, [rdi]
0x140214633  mov     rcx, [rax+18h]
0x140214637  add     rcx, 10h; Mcb
0x14021463b  mov     r8, r12; Lbn
0x14021463e  mov     rdx, r12; Vbn
0x140214641  call    cs:__imp_FsRtlAddBaseMcbEntryEx
0x140214648  nop     dword ptr [rax+rax+00h]
0x14021464d  test    eax, eax
0x14021464f  js      short loc_1402146CC
0x140214651  mov     r8d, [rsp+98h+Index]
0x140214656  add     r8d, dword ptr [rsp+98h+var_50]
0x14021465b  add     r8, rbx
0x14021465e  mov     [rsp+98h+var_50], r8
0x140214663  mov     eax, [rsi+10h]
0x140214666  bt      rax, 14h
0x14021466b  jb      short loc_14021469B
0x14021466d  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x140214674  jz      short loc_14021469B
0x140214676  mov     rax, [rdi]
0x140214679  mov     rcx, [rax+18h]
0x14021467d  add     rcx, 10h
0x140214681  mov     [rsp+98h+var_70], rcx
0x140214686  mov     dword ptr [rsp+98h+var_78], r13d
0x14021468b  mov     r9, r12
0x14021468e  mov     r8, r14
0x140214691  call    McTemplateU0pidp_EtwWriteTransfer
0x140214696  mov     r8, [rsp+98h+var_50]
0x14021469b  movzx   ecx, byte ptr [r14+1E8h]
0x1402146a3  shl     r12, cl
0x1402146a6  mov     [r8], r12
0x1402146a9  movzx   ecx, byte ptr [r14+1E8h]
0x1402146b1  mov     rax, r13
0x1402146b4  shl     rax, cl
0x1402146b7  mov     [r8+8], rax
0x1402146bb  add     dword ptr [rbx+18h], 10h
0x1402146bf  mov     rax, [rdi]
0x1402146c2  mov     rcx, [rax+18h]
0x1402146c6  add     [rcx+30h], r13
0x1402146ca  jmp     short loc_140214704
0x1402146cc  mov     rcx, [rsp+98h+arg_20]
0x1402146d4  mov     byte ptr [rcx], 1
0x1402146d7  mov     eax, [rsi+10h]
0x1402146da  bt      rax, 14h
0x1402146df  jb      short loc_14021470C
0x1402146e1  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x1402146e8  jz      short loc_14021470C
0x1402146ea  mov     rax, [rdi]
0x1402146ed  mov     r9, [rax+18h]
0x1402146f1  add     r9, 10h
0x1402146f5  mov     r8, r14
0x1402146f8  lea     rdx, delnotify_c427
0x1402146ff  call    McTemplateU0pp_EtwWriteTransfer
0x140214704  mov     rcx, [rsp+98h+arg_20]
0x14021470c  mov     eax, [rbx+18h]
0x14021470f  cmp     eax, dword ptr [rsp+98h+LargeVbn]
0x140214713  jnb     short loc_14021472B
0x140214715  cmp     byte ptr [rcx], 0
0x140214718  jnz     short loc_140214723
0x14021471a  test    r13d, r13d
0x14021471d  jnz     loc_140214848
0x140214723  test    eax, eax
0x140214725  jz      loc_140214848
0x14021472b  lea     rdx, [r14+648h]
0x140214732  mov     r8, [rdx+8]
0x140214736  cmp     [r8], rdx
0x140214739  jz      short loc_140214742
0x14021473b  mov     ecx, 3
0x140214740  int     29h; Win8: RtlFailFast(ecx)
0x140214742  mov     rax, [rdi]
0x140214745  mov     rcx, [rax+18h]
0x140214749  mov     [rcx], rdx
0x14021474c  mov     [rcx+8], r8
0x140214750  mov     [r8], rcx
0x140214753  mov     [rdx+8], rcx
0x140214757  mov     rax, [rdi]
0x14021475a  mov     rcx, [rax+18h]
0x14021475e  mov     rax, [rcx+30h]
0x140214762  add     [r14+138h], rax
0x140214769  mov     rdx, [rdi]
0x14021476c  mov     rax, [rdx+18h]
0x140214770  mov     rcx, [rax+30h]
0x140214774  mov     [rdx+28h], rcx
0x140214778  mov     [rsp+98h+Index], 0
0x140214780  mov     [rsp+98h+LargeVbn], 0
0x140214789  mov     rax, [rdi]
0x14021478c  mov     rcx, [rax+18h]
0x140214790  add     rcx, 10h; OpaqueMcb
0x140214794  lea     r9, [rsp+98h+Index]; Index
0x140214799  lea     r8, [rsp+98h+LargeVbn]; LargeLbn
0x14021479e  lea     rdx, [rsp+98h+LargeVbn]; LargeVbn
0x1402147a3  call    cs:__imp_FsRtlLookupLastBaseMcbEntryAndIndex
0x1402147aa  nop     dword ptr [rax+rax+00h]
0x1402147af  mov     eax, [rsp+98h+Index]
0x1402147b3  add     [r14+5E8h], eax
0x1402147ba  mov     eax, [r14+5E8h]
0x1402147c1  cmp     [r14+2304h], eax
0x1402147c8  jnb     short loc_1402147D1
0x1402147ca  mov     [r14+2304h], eax
0x1402147d1  mov     eax, [rsi+10h]
0x1402147d4  bt      rax, 14h
0x1402147d9  jb      short loc_1402147FB
0x1402147db  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x1402147e2  jz      short loc_1402147FB
0x1402147e4  mov     [rsp+98h+var_78], rsi
0x1402147e9  mov     r9, [rdi]
0x1402147ec  mov     r8, r14
0x1402147ef  lea     rdx, delnotify_c508
0x1402147f6  call    McTemplateU0ppp_EtwWriteTransfer
0x1402147fb  mov     dword ptr [rbx], 1Ch
0x140214801  lea     rcx, [rsi+1D0h]
0x140214808  mov     rdx, [rcx+8]
0x14021480c  cmp     [rdx], rcx
0x14021480f  jz      short loc_140214818
0x140214811  mov     ecx, 3
0x140214816  int     29h; Win8: RtlFailFast(ecx)
0x140214818  mov     rax, [rdi]
0x14021481b  mov     [rax], rcx
0x14021481e  mov     [rax+8], rdx
0x140214822  mov     [rdx], rax
0x140214825  mov     [rcx+8], rax
0x140214829  mov     qword ptr [rdi], 0
0x140214830  jmp     short loc_140214848
0x140214832  mov     rcx, [r9]; Entry
0x140214835  test    rcx, rcx
0x140214838  jz      short loc_14021484D
0x14021483a  call    NtfsFreeMarkUnusedContext
0x14021483f  mov     qword ptr [rdi], 0
0x140214846  jmp     short loc_14021484D
0x140214848  movzx   ebx, [rsp+98h+var_58]
0x14021484d  test    r15, r15
0x140214850  jz      loc_1402148E8
0x140214856  mov     eax, [rsi+10h]
0x140214859  bt      rax, 14h
0x14021485e  jb      short loc_140214878
0x140214860  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 10h
0x140214867  jz      short loc_140214878
0x140214869  mov     r8, r14
0x14021486c  lea     rdx, delnotify_c557
0x140214873  call    McTemplateU0p_EtwWriteTransfer
0x140214878  test    bl, bl
0x14021487a  jz      short loc_14021488C
0x14021487c  lea     rcx, [r15+10h]; Mcb
0x140214880  call    cs:__imp_FsRtlUninitializeBaseMcb
  ... truncated ...
```
