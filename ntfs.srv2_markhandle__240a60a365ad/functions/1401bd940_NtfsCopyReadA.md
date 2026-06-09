# NtfsCopyReadA

- ea: `0x1401bd940`
- end: `0x1401bdfa0`
- name: `NtfsCopyReadA`
- size: `1632`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x140007ea0`
- `0x140008740`
- `0x140009af0`
- `0x140017030`
- `0x14001cd10`
- `0x140059250`
- `0x1400596c0`
- `0x1401bd940`
- `0x1401be398`
- `0x1401be91c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bda38`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bda38`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bdd65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bdd65`
- `ntoskrnl!CcCopyReadEx` at `0x1401bdc53`
- `ntoskrnl!CcCopyReadEx` at `0x1401bdc53`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bdc14`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bdd1c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bdc14`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bdd1c`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x1401bdabc`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x1401bdabc`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x1401bdf3c`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x1401bdf3c`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x1401bde7b`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x1401bde7b`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x1401bde06`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x1401bde06`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x1401bddcb`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x1401bddcb`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bdbac`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bdda7`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bdbac`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bdda7`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdb43`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdf69`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdf8c`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdb43`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdf69`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdf8c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aebdc`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aebdc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401bdd4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401bdd4f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401bd9a3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401bd9a3`

## pseudocode

```c
char __fastcall NtfsCopyReadA(_QWORD *a1, _QWORD *a2, unsigned int a3, char a4, ULONG a5, __int64 a6, __int64 a7)
{
  __int64 v7; // rsi
  char v10; // r14
  __int64 v11; // rsi
  __int64 v12; // r8
  __int64 *v13; // r12
  __int64 v14; // rax
  __int64 v15; // r13
  __int64 v16; // r8
  __int64 v17; // rax
  char v18; // r12
  __int64 v19; // rbx
  char v20; // r8
  __int64 v21; // rax
  int i; // ecx
  _DWORD *v23; // rdx
  __int64 v24; // rax
  bool v25; // zf
  __int64 v26; // r12
  __int64 v27; // rax
  unsigned int v28; // ebx
  __int64 v29; // r9
  __int64 v30; // r8
  _QWORD *v31; // rbx
  signed __int32 v33[8]; // [rsp+0h] [rbp-328h] BYREF
  char v34; // [rsp+40h] [rbp-2E8h]
  _BYTE v35[7]; // [rsp+41h] [rbp-2E7h] BYREF
  __int64 v36; // [rsp+48h] [rbp-2E0h]
  unsigned int v37; // [rsp+50h] [rbp-2D8h]
  _QWORD *v38; // [rsp+58h] [rbp-2D0h]
  __int64 v39; // [rsp+60h] [rbp-2C8h]
  _BYTE *v40; // [rsp+68h] [rbp-2C0h]
  __int64 *v41; // [rsp+70h] [rbp-2B8h]
  _WORD *v42; // [rsp+78h] [rbp-2B0h]
  __int64 v43; // [rsp+80h] [rbp-2A8h]
  _QWORD *v44; // [rsp+88h] [rbp-2A0h]
  __int64 v45; // [rsp+90h] [rbp-298h]
  __int64 v46; // [rsp+98h] [rbp-290h]
  __int64 v47; // [rsp+A0h] [rbp-288h]
  __int64 v48; // [rsp+A8h] [rbp-280h]
  _BYTE v49[560]; // [rsp+B0h] [rbp-278h] BYREF

  v34 = a4;
  v7 = a3;
  v37 = a3;
  v38 = a2;
  v44 = a1;
  v45 = a6;
  v35[0] = 0;
  if ( !IoGetTopLevelIrp() )
  {
    v10 = 1;
    if ( !(_DWORD)v7 )
    {
      *(_DWORD *)a7 = 0;
      *(_QWORD *)(a7 + 8) = 0;
      return v10;
    }
    memset(v49, 0, 0x228u);
    v40 = v49;
    v43 = v7;
    v39 = *a2;
    if ( 0x7FFFFFFFFFFFFFFFLL - v39 >= v7 )
    {
      v11 = a1[3];
      v47 = v11;
      if ( (*(_DWORD *)(v11 + 512) & 0x10000000) == 0 )
      {
        v46 = a1[4];
        KeEnterCriticalRegion();
        memset(v49, 0, 0x228u);
        NtfsInitializeIrpContextInternal(0);
        v13 = (__int64 *)(v11 + 184);
        v41 = (__int64 *)(v11 + 184);
        v14 = *(_QWORD *)(*(_QWORD *)(v11 + 184) + 96LL);
        v15 = (__int64)v40;
        *((_QWORD *)v40 + 13) = v14;
        if ( v14 && (*(_DWORD *)(v14 + 24) & 0x20000) != 0 )
          *(_QWORD *)(v15 + 16) |= 0x100000uLL;
        else
          *(_QWORD *)(v15 + 16) &= ~0x100000uLL;
        if ( (*(_DWORD *)(*(_QWORD *)(v11 + 192) + 24LL) & 0x40000) != 0
          && (*(_DWORD *)(*v13 + 4) & 0x100) == 0
          && (*(_BYTE *)(v11 + 512) & 0x20) == 0
          && ((*(_WORD *)(v11 + 460) & 0xC0FF) != 0 || (*(_DWORD *)(v11 + 200) & 8) != 0)
          && *(_DWORD *)(v11 + 256) == 128
          && !*(_DWORD *)(v11 + 448) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221226650LL, 3866808);
          *(_DWORD *)a7 = -1073740646;
          *(_QWORD *)(a7 + 8) = 0;
          goto LABEL_57;
        }
        if ( v34 )
          FsRtlIncrementCcFastReadWait();
        else
          FsRtlIncrementCcFastReadNoWait();
        if ( !*(_QWORD *)(v11 + 16) || (LOBYTE(v16) = v34, !(unsigned __int8)NtfsAcquirePagingShared(v15, v11, v16, 0)) )
        {
          FsRtlIncrementCcFastReadResourceMiss();
LABEL_57:
          v10 = 0;
LABEL_43:
          NtfsCleanupIrpContext(v15, 0, v12);
          KeLeaveCriticalRegion();
          return v10;
        }
        v48 = v11 + 184;
        v42 = (_WORD *)v11;
        v17 = *(_QWORD *)(v11 + 528);
        if ( v17 && (*(_DWORD *)(*(_QWORD *)(v17 + 64) + 4LL) & 1) != 0 || a1[5] != *(_QWORD *)(v11 + 288) + 16LL )
        {
          v10 = 0;
LABEL_40:
          if ( *v42 != 1794 )
            v11 = *v13;
          ExReleaseResourceLite(*(PERESOURCE *)(v11 + 112));
          goto LABEL_43;
        }
        v18 = 0;
        v19 = v43 + v39;
        if ( v43 + v39 > *(_QWORD *)(v11 + 40) )
        {
          FsRtlAcquireHeaderMutex(v11 + 120, v11 + 160);
          v18 = 1;
        }
        v39 = v11 + 120;
        while ( 1 )
        {
          if ( v18 )
          {
            v24 = *(_QWORD *)(v11 + 40);
          }
          else
          {
            v20 = 0;
            v21 = v11 + 160;
            for ( i = *(_DWORD *)(v11 + 160); ; i = 1 )
            {
              LODWORD(v36) = i;
              if ( (i & 1) != 0 )
              {
                FsRtlAcquireHeaderMutex(v11 + 120, v21);
                v20 = 1;
                i = v36;
              }
              v36 = *(_QWORD *)(v11 + 40);
              v23 = (_DWORD *)(v11 + 160);
              if ( v20 )
                break;
              _InterlockedOr(v33, 0);
              if ( i == *v23 )
                goto LABEL_26;
              v21 = v11 + 160;
            }
            FsRtlReleaseHeaderMutex(v11 + 120, v23);
LABEL_26:
            v24 = v36;
          }
          if ( v19 <= v24 )
            break;
          if ( v18 )
          {
            NtfsGetIoAtEof(v15, v11, *v38, v43, 1, (__int64)v35);
            break;
          }
          FsRtlAcquireHeaderMutex(v11 + 120, v11 + 160);
          v18 = 1;
        }
        v25 = v18 == 0;
        v26 = v39;
        if ( !v25 )
          FsRtlReleaseHeaderMutex(v39, v11 + 160);
        if ( !v44[6]
          || !*(_BYTE *)(v11 + 5)
          || *(_BYTE *)(v11 + 5) == 2 && !(unsigned __int8)NtfsFastIoCheckIfPossibleInternal(v15, v44, a5, 1) )
        {
          FsRtlIncrementCcFastReadNotPossible();
          v10 = 0;
LABEL_38:
          if ( v35[0] )
          {
            if ( v15 )
              *(_QWORD *)(v15 + 64) = 0;
            FsRtlReleaseEofLock(v26, v11 + 160);
          }
          v13 = v41;
          goto LABEL_40;
        }
        v27 = *(_QWORD *)(v11 + 32);
        if ( v19 > v27 )
        {
          if ( *v38 >= v27 )
          {
            *(_DWORD *)a7 = -1073741807;
            *(_QWORD *)(a7 + 8) = 0;
            goto LABEL_38;
          }
          v28 = *(_DWORD *)(v11 + 32) - *(_DWORD *)v38;
        }
        else
        {
          v28 = v37;
        }
        IoSetTopLevelIrp((PIRP)4);
        *(_DWORD *)a7 = 0;
        LOBYTE(v29) = v34;
        v30 = v28;
        v31 = v44;
        v10 = CcCopyReadEx(v44, v38, v30, v29, v45, a7, 0);
        v35[1] = v10;
        if ( v10 )
        {
          NtfsUpdateFileTimestampsForAccess(v31, *(_QWORD *)(v11 + 184), v46);
          v31[13] = *v38 + *(_QWORD *)(a7 + 8);
        }
        IoSetTopLevelIrp(0);
        goto LABEL_38;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1401bd940  push    rbx
0x1401bd942  push    rsi
0x1401bd943  push    rdi
0x1401bd944  push    r12
0x1401bd946  push    r13
0x1401bd948  push    r14
0x1401bd94a  push    r15
0x1401bd94c  sub     rsp, 2F0h
0x1401bd953  mov     rax, cs:__security_cookie
0x1401bd95a  xor     rax, rsp
0x1401bd95d  mov     [rsp+328h+var_48], rax
0x1401bd965  mov     [rsp+328h+var_2E8], r9b
0x1401bd96a  mov     esi, r8d
0x1401bd96d  mov     [rsp+328h+var_2D8], esi
0x1401bd971  mov     r12, rdx
0x1401bd974  mov     [rsp+328h+var_2D0], rdx
0x1401bd979  mov     rbx, rcx
0x1401bd97c  mov     [rsp+328h+var_2A0], rcx
0x1401bd984  mov     r15, [rsp+328h+arg_30]
0x1401bd98c  mov     rax, [rsp+328h+arg_28]
0x1401bd994  mov     [rsp+328h+var_298], rax
0x1401bd99c  xor     edi, edi
0x1401bd99e  mov     [rsp+328h+var_2E7], dil
0x1401bd9a3  call    cs:__imp_IoGetTopLevelIrp
0x1401bd9aa  nop     dword ptr [rax+rax+00h]
0x1401bd9af  test    rax, rax
0x1401bd9b2  jnz     loc_1401BDE99
0x1401bd9b8  lea     r14d, [rdi+1]
0x1401bd9bc  test    esi, esi
0x1401bd9be  jz      loc_1401BDEA0
0x1401bd9c4  mov     r13d, 228h
0x1401bd9ca  mov     r8d, r13d; Size
0x1401bd9cd  xor     edx, edx; Val
0x1401bd9cf  lea     rcx, [rsp+328h+var_278]; void *
0x1401bd9d7  call    memset
0x1401bd9dc  lea     rax, [rsp+328h+var_278]
0x1401bd9e4  mov     [rsp+328h+var_2C0], rax
0x1401bd9e9  mov     [rsp+328h+var_2A8], rsi
0x1401bd9f1  mov     rcx, [r12]
0x1401bd9f5  mov     [rsp+328h+var_2C8], rcx
0x1401bd9fa  mov     rax, 7FFFFFFFFFFFFFFFh
0x1401bda04  sub     rax, rcx
0x1401bda07  cmp     rax, rsi
0x1401bda0a  jl      loc_1401BDE99
0x1401bda10  mov     rsi, [rbx+18h]
0x1401bda14  mov     [rsp+328h+var_288], rsi
0x1401bda1c  test    dword ptr [rsi+200h], 10000000h
0x1401bda26  jnz     loc_1401BDE99
0x1401bda2c  mov     rax, [rbx+20h]
0x1401bda30  mov     [rsp+328h+var_290], rax
0x1401bda38  call    cs:__imp_KeEnterCriticalRegion
0x1401bda3f  nop     dword ptr [rax+rax+00h]
0x1401bda44  mov     r8d, r13d; Size
0x1401bda47  xor     edx, edx; Val
0x1401bda49  lea     rcx, [rsp+328h+var_278]; void *
0x1401bda51  call    memset
0x1401bda56  lea     r9, [rsp+328h+var_2C0]
0x1401bda5b  mov     r8b, r14b
0x1401bda5e  mov     dl, r14b
0x1401bda61  xor     ecx, ecx; Irp
0x1401bda63  call    NtfsInitializeIrpContextInternal
0x1401bda68  lea     r12, [rsi+0B8h]
0x1401bda6f  mov     [rsp+328h+var_2B8], r12
0x1401bda74  mov     rax, [r12]
0x1401bda78  mov     rax, [rax+60h]
0x1401bda7c  mov     r13, [rsp+328h+var_2C0]
0x1401bda81  mov     [r13+68h], rax
0x1401bda85  test    rax, rax
0x1401bda88  jz      short loc_1401BDA97
0x1401bda8a  test    dword ptr [rax+18h], 20000h
0x1401bda91  jnz     loc_1401BDEAC
0x1401bda97  btr     qword ptr [r13+10h], 14h
0x1401bda9d  mov     rax, [rsi+0C0h]
0x1401bdaa4  test    dword ptr [rax+18h], 40000h
0x1401bdaab  jnz     loc_1401BDEF0
0x1401bdab1  cmp     [rsp+328h+var_2E8], dil
0x1401bdab6  jz      loc_1401BDF3C
0x1401bdabc  call    cs:__imp_FsRtlIncrementCcFastReadWait
0x1401bdac3  nop     dword ptr [rax+rax+00h]
0x1401bdac8  cmp     [rsi+10h], rdi
0x1401bdacc  jz      loc_1401BDE7B
0x1401bdad2  xor     r9d, r9d
0x1401bdad5  mov     r8b, [rsp+328h+var_2E8]
0x1401bdada  mov     rdx, rsi
0x1401bdadd  mov     rcx, r13
0x1401bdae0  call    NtfsAcquirePagingShared
0x1401bdae5  test    al, al
0x1401bdae7  jz      loc_1401BDE7B
0x1401bdaed  mov     [rsp+328h+var_280], r12
0x1401bdaf5  mov     [rsp+328h+var_2B0], rsi
0x1401bdafa  mov     rax, [rsi+210h]
0x1401bdb01  test    rax, rax
0x1401bdb04  jnz     loc_1401BDF4D
0x1401bdb0a  mov     rax, [rsi+120h]
0x1401bdb11  add     rax, 10h
0x1401bdb15  cmp     [rbx+28h], rax
0x1401bdb19  jnz     loc_1401BDD98
0x1401bdb1f  mov     r12b, dil
0x1401bdb22  mov     rbx, [rsp+328h+var_2C8]
0x1401bdb27  add     rbx, [rsp+328h+var_2A8]
0x1401bdb2f  mov     rax, [rsi+28h]
0x1401bdb33  cmp     rbx, rax
0x1401bdb36  jle     short loc_1401BDB52
0x1401bdb38  lea     rdx, [rsi+0A0h]
0x1401bdb3f  lea     rcx, [rsi+78h]
0x1401bdb43  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401bdb4a  nop     dword ptr [rax+rax+00h]
0x1401bdb4f  mov     r12b, r14b
0x1401bdb52  lea     rax, [rsi+78h]
0x1401bdb56  mov     [rsp+328h+var_2C8], rax
0x1401bdb5b  test    r12b, r12b
0x1401bdb5e  jnz     loc_1401BDE1A
0x1401bdb64  mov     r8b, r12b
0x1401bdb67  lea     rax, [rsi+0A0h]
0x1401bdb6e  mov     ecx, [rax]
0x1401bdb70  mov     dword ptr [rsp+328h+var_2E0], ecx
0x1401bdb74  test    r14b, cl
0x1401bdb77  jnz     loc_1401BDF62
0x1401bdb7d  mov     rax, [rsi+28h]
0x1401bdb81  mov     [rsp+328h+var_2E0], rax
0x1401bdb86  lea     rdx, [rsi+0A0h]
0x1401bdb8d  test    r8b, r8b
0x1401bdb90  jnz     short loc_1401BDBA8
0x1401bdb92  lock or [rsp+328h+var_328], edi
0x1401bdb96  mov     eax, [rdx]
0x1401bdb98  cmp     ecx, eax
0x1401bdb9a  jz      short loc_1401BDBB8
0x1401bdb9c  mov     ecx, r14d
0x1401bdb9f  lea     rax, [rsi+0A0h]
0x1401bdba6  jmp     short loc_1401BDB70
0x1401bdba8  lea     rcx, [rsi+78h]
0x1401bdbac  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401bdbb3  nop     dword ptr [rax+rax+00h]
0x1401bdbb8  mov     rax, [rsp+328h+var_2E0]
0x1401bdbbd  mov     rdx, rsi
0x1401bdbc0  cmp     rbx, rax
0x1401bdbc3  jg      loc_1401BDE43
0x1401bdbc9  test    r12b, r12b
0x1401bdbcc  mov     r12, [rsp+328h+var_2C8]
0x1401bdbd1  jnz     loc_1401BDD9D
0x1401bdbd7  mov     rdx, [rsp+328h+var_2A0]
0x1401bdbdf  cmp     [rdx+30h], rdi
0x1401bdbe3  jz      loc_1401BDE06
0x1401bdbe9  cmp     [rsi+5], dil
0x1401bdbed  jz      loc_1401BDE06
0x1401bdbf3  mov     al, [rsi+5]
0x1401bdbf6  cmp     al, 2
0x1401bdbf8  jz      loc_1401BDDDC
0x1401bdbfe  mov     rax, [rsi+20h]
0x1401bdc02  cmp     rbx, rax
0x1401bdc05  jg      loc_1401BDE23
0x1401bdc0b  mov     ebx, [rsp+328h+var_2D8]
0x1401bdc0f  mov     ecx, 4; Irp
0x1401bdc14  call    cs:__imp_IoSetTopLevelIrp
0x1401bdc1b  nop     dword ptr [rax+rax+00h]
0x1401bdc20  nop
0x1401bdc21  mov     [r15], edi
0x1401bdc24  mov     [rsp+328h+var_2F8], rdi
0x1401bdc29  mov     [rsp+328h+var_300], r15
0x1401bdc2e  mov     rax, [rsp+328h+var_298]
0x1401bdc36  mov     [rsp+328h+var_308], rax
0x1401bdc3b  mov     r9b, [rsp+328h+var_2E8]
0x1401bdc40  mov     r8d, ebx
0x1401bdc43  mov     rdx, [rsp+328h+var_2D0]
0x1401bdc48  mov     rbx, [rsp+328h+var_2A0]
0x1401bdc50  mov     rcx, rbx
0x1401bdc53  call    cs:__imp_CcCopyReadEx
0x1401bdc5a  nop     dword ptr [rax+rax+00h]
0x1401bdc5f  mov     r14b, al
0x1401bdc62  mov     [rsp+328h+var_2E6], al
0x1401bdc66  test    al, al
0x1401bdc68  jz      short loc_1401BDC91
0x1401bdc6a  mov     r8, [rsp+328h+var_290]
0x1401bdc72  mov     rdx, [rsi+0B8h]
0x1401bdc79  mov     rcx, rbx
0x1401bdc7c  call    NtfsUpdateFileTimestampsForAccess
0x1401bdc81  mov     rdx, [r15+8]
0x1401bdc85  mov     rax, [rsp+328h+var_2D0]
0x1401bdc8a  add     rdx, [rax]
0x1401bdc8d  mov     [rbx+68h], rdx
0x1401bdc91  jmp     loc_1401BDD1A
0x1401bdc96  mov     edx, eax
0x1401bdc98  mov     cl, cs:NtfsStatusDebugFlags
0x1401bdc9e  test    cl, cl
0x1401bdca0  jz      short loc_1401BDCF1
0x1401bdca2  test    eax, eax
0x1401bdca4  jz      short loc_1401BDCF1
0x1401bdca6  cmp     eax, 126h
0x1401bdcab  jz      short loc_1401BDCF1
0x1401bdcad  lea     ecx, [rax-12Ah]
0x1401bdcb3  cmp     ecx, 1
0x1401bdcb6  jbe     short loc_1401BDCF1
0x1401bdcb8  cmp     eax, 0FFFFFFEDh
0x1401bdcbb  jnb     short loc_1401BDCF1
0x1401bdcbd  cmp     eax, 0C00000D8h
0x1401bdcc2  jz      short loc_1401BDCF1
0x1401bdcc4  cmp     eax, 0C0000016h
0x1401bdcc9  jz      short loc_1401BDCF1
0x1401bdccb  cmp     eax, 0C0000011h
0x1401bdcd0  jz      short loc_1401BDCF1
0x1401bdcd2  add     eax, 7FFFFFFBh
0x1401bdcd7  cmp     eax, 1
0x1401bdcda  jbe     short loc_1401BDCF1
0x1401bdcdc  cmp     edx, 103h
0x1401bdce2  jz      short loc_1401BDCF1
0x1401bdce4  xor     ecx, ecx
0x1401bdce6  mov     r8d, 3B01A3h
0x1401bdcec  call    NtfsStatusTraceAndDebugInternal
0x1401bdcf1  xor     r14b, r14b
0x1401bdcf4  mov     [rsp+328h+var_2E6], r14b
0x1401bdcf9  xor     edi, edi
0x1401bdcfb  mov     rsi, [rsp+328h+var_288]
0x1401bdd03  mov     r13, [rsp+328h+var_2C0]
0x1401bdd08  mov     rax, [rsp+328h+var_280]
0x1401bdd10  mov     [rsp+328h+var_2B8], rax
0x1401bdd15  mov     r12, [rsp+328h+var_2C8]
0x1401bdd1a  xor     ecx, ecx; Irp
0x1401bdd1c  call    cs:__imp_IoSetTopLevelIrp
0x1401bdd23  nop     dword ptr [rax+rax+00h]
0x1401bdd28  cmp     [rsp+328h+var_2E7], dil
0x1401bdd2d  jnz     loc_1401BDDB8
0x1401bdd33  mov     r12, [rsp+328h+var_2B8]
0x1401bdd38  mov     ecx, 702h
0x1401bdd3d  mov     rax, [rsp+328h+var_2B0]
0x1401bdd42  cmp     cx, [rax]
0x1401bdd45  jz      short loc_1401BDD4B
0x1401bdd47  mov     rsi, [r12]
0x1401bdd4b  mov     rcx, [rsi+70h]; Resource
0x1401bdd4f  call    cs:__imp_ExReleaseResourceLite
0x1401bdd56  nop     dword ptr [rax+rax+00h]
0x1401bdd5b  xor     edx, edx
0x1401bdd5d  mov     rcx, r13
0x1401bdd60  call    NtfsCleanupIrpContext
0x1401bdd65  call    cs:__imp_KeLeaveCriticalRegion
0x1401bdd6c  nop     dword ptr [rax+rax+00h]
0x1401bdd71  mov     al, r14b
0x1401bdd74  mov     rcx, [rsp+328h+var_48]
0x1401bdd7c  xor     rcx, rsp; StackCookie
0x1401bdd7f  call    __security_check_cookie
0x1401bdd84  add     rsp, 2F0h
0x1401bdd8b  pop     r15
0x1401bdd8d  pop     r14
0x1401bdd8f  pop     r13
0x1401bdd91  pop     r12
0x1401bdd93  pop     rdi
0x1401bdd94  pop     rsi
0x1401bdd95  pop     rbx
0x1401bdd96  retn
0x1401bdd98  mov     r14b, dil
0x1401bdd9b  jmp     short loc_1401BDD38
0x1401bdd9d  lea     rdx, [rsi+0A0h]
0x1401bdda4  mov     rcx, r12
0x1401bdda7  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401bddae  nop     dword ptr [rax+rax+00h]
0x1401bddb3  jmp     loc_1401BDBD7
0x1401bddb8  test    r13, r13
0x1401bddbb  jz      short loc_1401BDDC1
0x1401bddbd  mov     [r13+40h], rdi
0x1401bddc1  lea     rdx, [rsi+0A0h]
0x1401bddc8  mov     rcx, r12
0x1401bddcb  call    cs:__imp_FsRtlReleaseEofLock
0x1401bddd2  nop     dword ptr [rax+rax+00h]
0x1401bddd7  jmp     loc_1401BDD33
0x1401bdddc  mov     byte ptr [rsp+328h+var_300], r14b
0x1401bdde1  mov     eax, [rsp+328h+arg_20]
0x1401bdde8  mov     dword ptr [rsp+328h+var_308], eax
0x1401bddec  mov     r9d, [rsp+328h+var_2D8]
0x1401bddf1  mov     r8, [rsp+328h+var_2D0]
0x1401bddf6  mov     rcx, r13
0x1401bddf9  call    NtfsFastIoCheckIfPossibleInternal
0x1401bddfe  test    al, al
0x1401bde00  jnz     loc_1401BDBFE
0x1401bde06  call    cs:__imp_FsRtlIncrementCcFastReadNotPossible
0x1401bde0d  nop     dword ptr [rax+rax+00h]
0x1401bde12  mov     r14b, dil
0x1401bde15  jmp     loc_1401BDD28
0x1401bde1a  mov     rax, [rsi+28h]
0x1401bde1e  jmp     loc_1401BDBBD
0x1401bde23  mov     rcx, [rsp+328h+var_2D0]
0x1401bde28  cmp     [rcx], rax
0x1401bde2b  jl      short loc_1401BDE8F
0x1401bde2d  mov     al, cs:NtfsStatusDebugFlags
0x1401bde33  mov     dword ptr [r15], 0C0000011h
0x1401bde3a  mov     [r15+8], rdi
0x1401bde3e  jmp     loc_1401BDD28
0x1401bde43  test    r12b, r12b
0x1401bde46  jz      loc_1401BDF81
0x1401bde4c  lea     rax, [rsp+328h+var_2E7]
0x1401bde51  mov     [rsp+328h+var_300], rax
0x1401bde56  mov     byte ptr [rsp+328h+var_308], r14b
0x1401bde5b  mov     r9, [rsp+328h+var_2A8]
0x1401bde63  mov     r8, [rsp+328h+var_2D0]
0x1401bde68  mov     r8, [r8]
0x1401bde6b  mov     rdx, rsi
0x1401bde6e  mov     rcx, r13
0x1401bde71  call    NtfsGetIoAtEof
0x1401bde76  jmp     loc_1401BDBC9
0x1401bde7b  call    cs:__imp_FsRtlIncrementCcFastReadResourceMiss
0x1401bde82  nop     dword ptr [rax+rax+00h]
0x1401bde87  mov     r14b, dil
  ... truncated ...
```
