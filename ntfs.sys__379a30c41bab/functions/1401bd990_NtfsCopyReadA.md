# NtfsCopyReadA

- ea: `0x1401bd990`
- end: `0x1401bdff0`
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
- `0x1400592c0`
- `0x140059740`
- `0x1401bd990`
- `0x1401be3e8`
- `0x1401be96c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bda88`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401bda88`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bddb5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401bddb5`
- `ntoskrnl!CcCopyReadEx` at `0x1401bdca3`
- `ntoskrnl!CcCopyReadEx` at `0x1401bdca3`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bdc64`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bdd6c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bdc64`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1401bdd6c`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x1401bdb0c`
- `ntoskrnl!FsRtlIncrementCcFastReadWait` at `0x1401bdb0c`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x1401bdf8c`
- `ntoskrnl!FsRtlIncrementCcFastReadNoWait` at `0x1401bdf8c`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x1401bdecb`
- `ntoskrnl!FsRtlIncrementCcFastReadResourceMiss` at `0x1401bdecb`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x1401bde56`
- `ntoskrnl!FsRtlIncrementCcFastReadNotPossible` at `0x1401bde56`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x1401bde1b`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x1401bde1b`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bdbfc`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bddf7`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bdbfc`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401bddf7`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdb93`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdfb9`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdfdc`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdb93`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdfb9`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401bdfdc`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aec2c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402aec2c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401bdd9f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401bdd9f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401bd9f3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1401bd9f3`

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
  __int64 v17; // r8
  __int64 v18; // rax
  char v19; // r12
  __int64 v20; // rbx
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
        v18 = *(_QWORD *)(v11 + 528);
        if ( v18 && (*(_DWORD *)(*(_QWORD *)(v18 + 64) + 4LL) & 1) != 0 || a1[5] != *(_QWORD *)(v11 + 288) + 16LL )
        {
          v10 = 0;
LABEL_40:
          if ( *v42 != 1794 )
            v11 = *v13;
          ExReleaseResourceLite(*(PERESOURCE *)(v11 + 112));
          goto LABEL_43;
        }
        v19 = 0;
        v20 = v43 + v39;
        if ( v43 + v39 > *(_QWORD *)(v11 + 40) )
        {
          FsRtlAcquireHeaderMutex(v11 + 120, v11 + 160, v17);
          v19 = 1;
        }
        v39 = v11 + 120;
        while ( 1 )
        {
          if ( v19 )
          {
            v24 = *(_QWORD *)(v11 + 40);
          }
          else
          {
            LOBYTE(v17) = 0;
            v21 = v11 + 160;
            for ( i = *(_DWORD *)(v11 + 160); ; i = 1 )
            {
              LODWORD(v36) = i;
              if ( (i & 1) != 0 )
              {
                FsRtlAcquireHeaderMutex(v11 + 120, v21, v17);
                LOBYTE(v17) = 1;
                i = v36;
              }
              v36 = *(_QWORD *)(v11 + 40);
              v23 = (_DWORD *)(v11 + 160);
              if ( (_BYTE)v17 )
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
          if ( v20 <= v24 )
            break;
          if ( v19 )
          {
            NtfsGetIoAtEof(v15, v11, *v38, v43, 1, (__int64)v35);
            break;
          }
          FsRtlAcquireHeaderMutex(v11 + 120, v11 + 160, v17);
          v19 = 1;
        }
        v25 = v19 == 0;
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
        if ( v20 > v27 )
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
0x1401bd990  push    rbx
0x1401bd992  push    rsi
0x1401bd993  push    rdi
0x1401bd994  push    r12
0x1401bd996  push    r13
0x1401bd998  push    r14
0x1401bd99a  push    r15
0x1401bd99c  sub     rsp, 2F0h
0x1401bd9a3  mov     rax, cs:__security_cookie
0x1401bd9aa  xor     rax, rsp
0x1401bd9ad  mov     [rsp+328h+var_48], rax
0x1401bd9b5  mov     [rsp+328h+var_2E8], r9b
0x1401bd9ba  mov     esi, r8d
0x1401bd9bd  mov     [rsp+328h+var_2D8], esi
0x1401bd9c1  mov     r12, rdx
0x1401bd9c4  mov     [rsp+328h+var_2D0], rdx
0x1401bd9c9  mov     rbx, rcx
0x1401bd9cc  mov     [rsp+328h+var_2A0], rcx
0x1401bd9d4  mov     r15, [rsp+328h+arg_30]
0x1401bd9dc  mov     rax, [rsp+328h+arg_28]
0x1401bd9e4  mov     [rsp+328h+var_298], rax
0x1401bd9ec  xor     edi, edi
0x1401bd9ee  mov     [rsp+328h+var_2E7], dil
0x1401bd9f3  call    cs:__imp_IoGetTopLevelIrp
0x1401bd9fa  nop     dword ptr [rax+rax+00h]
0x1401bd9ff  test    rax, rax
0x1401bda02  jnz     loc_1401BDEE9
0x1401bda08  lea     r14d, [rdi+1]
0x1401bda0c  test    esi, esi
0x1401bda0e  jz      loc_1401BDEF0
0x1401bda14  mov     r13d, 228h
0x1401bda1a  mov     r8d, r13d; Size
0x1401bda1d  xor     edx, edx; Val
0x1401bda1f  lea     rcx, [rsp+328h+var_278]; void *
0x1401bda27  call    memset
0x1401bda2c  lea     rax, [rsp+328h+var_278]
0x1401bda34  mov     [rsp+328h+var_2C0], rax
0x1401bda39  mov     [rsp+328h+var_2A8], rsi
0x1401bda41  mov     rcx, [r12]
0x1401bda45  mov     [rsp+328h+var_2C8], rcx
0x1401bda4a  mov     rax, 7FFFFFFFFFFFFFFFh
0x1401bda54  sub     rax, rcx
0x1401bda57  cmp     rax, rsi
0x1401bda5a  jl      loc_1401BDEE9
0x1401bda60  mov     rsi, [rbx+18h]
0x1401bda64  mov     [rsp+328h+var_288], rsi
0x1401bda6c  test    dword ptr [rsi+200h], 10000000h
0x1401bda76  jnz     loc_1401BDEE9
0x1401bda7c  mov     rax, [rbx+20h]
0x1401bda80  mov     [rsp+328h+var_290], rax
0x1401bda88  call    cs:__imp_KeEnterCriticalRegion
0x1401bda8f  nop     dword ptr [rax+rax+00h]
0x1401bda94  mov     r8d, r13d; Size
0x1401bda97  xor     edx, edx; Val
0x1401bda99  lea     rcx, [rsp+328h+var_278]; void *
0x1401bdaa1  call    memset
0x1401bdaa6  lea     r9, [rsp+328h+var_2C0]
0x1401bdaab  mov     r8b, r14b
0x1401bdaae  mov     dl, r14b
0x1401bdab1  xor     ecx, ecx; Irp
0x1401bdab3  call    NtfsInitializeIrpContextInternal
0x1401bdab8  lea     r12, [rsi+0B8h]
0x1401bdabf  mov     [rsp+328h+var_2B8], r12
0x1401bdac4  mov     rax, [r12]
0x1401bdac8  mov     rax, [rax+60h]
0x1401bdacc  mov     r13, [rsp+328h+var_2C0]
0x1401bdad1  mov     [r13+68h], rax
0x1401bdad5  test    rax, rax
0x1401bdad8  jz      short loc_1401BDAE7
0x1401bdada  test    dword ptr [rax+18h], 20000h
0x1401bdae1  jnz     loc_1401BDEFC
0x1401bdae7  btr     qword ptr [r13+10h], 14h
0x1401bdaed  mov     rax, [rsi+0C0h]
0x1401bdaf4  test    dword ptr [rax+18h], 40000h
0x1401bdafb  jnz     loc_1401BDF40
0x1401bdb01  cmp     [rsp+328h+var_2E8], dil
0x1401bdb06  jz      loc_1401BDF8C
0x1401bdb0c  call    cs:__imp_FsRtlIncrementCcFastReadWait
0x1401bdb13  nop     dword ptr [rax+rax+00h]
0x1401bdb18  cmp     [rsi+10h], rdi
0x1401bdb1c  jz      loc_1401BDECB
0x1401bdb22  xor     r9d, r9d
0x1401bdb25  mov     r8b, [rsp+328h+var_2E8]
0x1401bdb2a  mov     rdx, rsi
0x1401bdb2d  mov     rcx, r13
0x1401bdb30  call    NtfsAcquirePagingShared
0x1401bdb35  test    al, al
0x1401bdb37  jz      loc_1401BDECB
0x1401bdb3d  mov     [rsp+328h+var_280], r12
0x1401bdb45  mov     [rsp+328h+var_2B0], rsi
0x1401bdb4a  mov     rax, [rsi+210h]
0x1401bdb51  test    rax, rax
0x1401bdb54  jnz     loc_1401BDF9D
0x1401bdb5a  mov     rax, [rsi+120h]
0x1401bdb61  add     rax, 10h
0x1401bdb65  cmp     [rbx+28h], rax
0x1401bdb69  jnz     loc_1401BDDE8
0x1401bdb6f  mov     r12b, dil
0x1401bdb72  mov     rbx, [rsp+328h+var_2C8]
0x1401bdb77  add     rbx, [rsp+328h+var_2A8]
0x1401bdb7f  mov     rax, [rsi+28h]
0x1401bdb83  cmp     rbx, rax
0x1401bdb86  jle     short loc_1401BDBA2
0x1401bdb88  lea     rdx, [rsi+0A0h]
0x1401bdb8f  lea     rcx, [rsi+78h]
0x1401bdb93  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401bdb9a  nop     dword ptr [rax+rax+00h]
0x1401bdb9f  mov     r12b, r14b
0x1401bdba2  lea     rax, [rsi+78h]
0x1401bdba6  mov     [rsp+328h+var_2C8], rax
0x1401bdbab  test    r12b, r12b
0x1401bdbae  jnz     loc_1401BDE6A
0x1401bdbb4  mov     r8b, r12b
0x1401bdbb7  lea     rax, [rsi+0A0h]
0x1401bdbbe  mov     ecx, [rax]
0x1401bdbc0  mov     dword ptr [rsp+328h+var_2E0], ecx
0x1401bdbc4  test    r14b, cl
0x1401bdbc7  jnz     loc_1401BDFB2
0x1401bdbcd  mov     rax, [rsi+28h]
0x1401bdbd1  mov     [rsp+328h+var_2E0], rax
0x1401bdbd6  lea     rdx, [rsi+0A0h]
0x1401bdbdd  test    r8b, r8b
0x1401bdbe0  jnz     short loc_1401BDBF8
0x1401bdbe2  lock or [rsp+328h+var_328], edi
0x1401bdbe6  mov     eax, [rdx]
0x1401bdbe8  cmp     ecx, eax
0x1401bdbea  jz      short loc_1401BDC08
0x1401bdbec  mov     ecx, r14d
0x1401bdbef  lea     rax, [rsi+0A0h]
0x1401bdbf6  jmp     short loc_1401BDBC0
0x1401bdbf8  lea     rcx, [rsi+78h]
0x1401bdbfc  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401bdc03  nop     dword ptr [rax+rax+00h]
0x1401bdc08  mov     rax, [rsp+328h+var_2E0]
0x1401bdc0d  mov     rdx, rsi
0x1401bdc10  cmp     rbx, rax
0x1401bdc13  jg      loc_1401BDE93
0x1401bdc19  test    r12b, r12b
0x1401bdc1c  mov     r12, [rsp+328h+var_2C8]
0x1401bdc21  jnz     loc_1401BDDED
0x1401bdc27  mov     rdx, [rsp+328h+var_2A0]
0x1401bdc2f  cmp     [rdx+30h], rdi
0x1401bdc33  jz      loc_1401BDE56
0x1401bdc39  cmp     [rsi+5], dil
0x1401bdc3d  jz      loc_1401BDE56
0x1401bdc43  mov     al, [rsi+5]
0x1401bdc46  cmp     al, 2
0x1401bdc48  jz      loc_1401BDE2C
0x1401bdc4e  mov     rax, [rsi+20h]
0x1401bdc52  cmp     rbx, rax
0x1401bdc55  jg      loc_1401BDE73
0x1401bdc5b  mov     ebx, [rsp+328h+var_2D8]
0x1401bdc5f  mov     ecx, 4; Irp
0x1401bdc64  call    cs:__imp_IoSetTopLevelIrp
0x1401bdc6b  nop     dword ptr [rax+rax+00h]
0x1401bdc70  nop
0x1401bdc71  mov     [r15], edi
0x1401bdc74  mov     [rsp+328h+var_2F8], rdi
0x1401bdc79  mov     [rsp+328h+var_300], r15
0x1401bdc7e  mov     rax, [rsp+328h+var_298]
0x1401bdc86  mov     [rsp+328h+var_308], rax
0x1401bdc8b  mov     r9b, [rsp+328h+var_2E8]
0x1401bdc90  mov     r8d, ebx
0x1401bdc93  mov     rdx, [rsp+328h+var_2D0]
0x1401bdc98  mov     rbx, [rsp+328h+var_2A0]
0x1401bdca0  mov     rcx, rbx
0x1401bdca3  call    cs:__imp_CcCopyReadEx
0x1401bdcaa  nop     dword ptr [rax+rax+00h]
0x1401bdcaf  mov     r14b, al
0x1401bdcb2  mov     [rsp+328h+var_2E6], al
0x1401bdcb6  test    al, al
0x1401bdcb8  jz      short loc_1401BDCE1
0x1401bdcba  mov     r8, [rsp+328h+var_290]
0x1401bdcc2  mov     rdx, [rsi+0B8h]
0x1401bdcc9  mov     rcx, rbx
0x1401bdccc  call    NtfsUpdateFileTimestampsForAccess
0x1401bdcd1  mov     rdx, [r15+8]
0x1401bdcd5  mov     rax, [rsp+328h+var_2D0]
0x1401bdcda  add     rdx, [rax]
0x1401bdcdd  mov     [rbx+68h], rdx
0x1401bdce1  jmp     loc_1401BDD6A
0x1401bdce6  mov     edx, eax
0x1401bdce8  mov     cl, cs:NtfsStatusDebugFlags
0x1401bdcee  test    cl, cl
0x1401bdcf0  jz      short loc_1401BDD41
0x1401bdcf2  test    eax, eax
0x1401bdcf4  jz      short loc_1401BDD41
0x1401bdcf6  cmp     eax, 126h
0x1401bdcfb  jz      short loc_1401BDD41
0x1401bdcfd  lea     ecx, [rax-12Ah]
0x1401bdd03  cmp     ecx, 1
0x1401bdd06  jbe     short loc_1401BDD41
0x1401bdd08  cmp     eax, 0FFFFFFEDh
0x1401bdd0b  jnb     short loc_1401BDD41
0x1401bdd0d  cmp     eax, 0C00000D8h
0x1401bdd12  jz      short loc_1401BDD41
0x1401bdd14  cmp     eax, 0C0000016h
0x1401bdd19  jz      short loc_1401BDD41
0x1401bdd1b  cmp     eax, 0C0000011h
0x1401bdd20  jz      short loc_1401BDD41
0x1401bdd22  add     eax, 7FFFFFFBh
0x1401bdd27  cmp     eax, 1
0x1401bdd2a  jbe     short loc_1401BDD41
0x1401bdd2c  cmp     edx, 103h
0x1401bdd32  jz      short loc_1401BDD41
0x1401bdd34  xor     ecx, ecx
0x1401bdd36  mov     r8d, 3B01A3h
0x1401bdd3c  call    NtfsStatusTraceAndDebugInternal
0x1401bdd41  xor     r14b, r14b
0x1401bdd44  mov     [rsp+328h+var_2E6], r14b
0x1401bdd49  xor     edi, edi
0x1401bdd4b  mov     rsi, [rsp+328h+var_288]
0x1401bdd53  mov     r13, [rsp+328h+var_2C0]
0x1401bdd58  mov     rax, [rsp+328h+var_280]
0x1401bdd60  mov     [rsp+328h+var_2B8], rax
0x1401bdd65  mov     r12, [rsp+328h+var_2C8]
0x1401bdd6a  xor     ecx, ecx; Irp
0x1401bdd6c  call    cs:__imp_IoSetTopLevelIrp
0x1401bdd73  nop     dword ptr [rax+rax+00h]
0x1401bdd78  cmp     [rsp+328h+var_2E7], dil
0x1401bdd7d  jnz     loc_1401BDE08
0x1401bdd83  mov     r12, [rsp+328h+var_2B8]
0x1401bdd88  mov     ecx, 702h
0x1401bdd8d  mov     rax, [rsp+328h+var_2B0]
0x1401bdd92  cmp     cx, [rax]
0x1401bdd95  jz      short loc_1401BDD9B
0x1401bdd97  mov     rsi, [r12]
0x1401bdd9b  mov     rcx, [rsi+70h]; Resource
0x1401bdd9f  call    cs:__imp_ExReleaseResourceLite
0x1401bdda6  nop     dword ptr [rax+rax+00h]
0x1401bddab  xor     edx, edx
0x1401bddad  mov     rcx, r13
0x1401bddb0  call    NtfsCleanupIrpContext
0x1401bddb5  call    cs:__imp_KeLeaveCriticalRegion
0x1401bddbc  nop     dword ptr [rax+rax+00h]
0x1401bddc1  mov     al, r14b
0x1401bddc4  mov     rcx, [rsp+328h+var_48]
0x1401bddcc  xor     rcx, rsp; StackCookie
0x1401bddcf  call    __security_check_cookie
0x1401bddd4  add     rsp, 2F0h
0x1401bdddb  pop     r15
0x1401bdddd  pop     r14
0x1401bdddf  pop     r13
0x1401bdde1  pop     r12
0x1401bdde3  pop     rdi
0x1401bdde4  pop     rsi
0x1401bdde5  pop     rbx
0x1401bdde6  retn
0x1401bdde8  mov     r14b, dil
0x1401bddeb  jmp     short loc_1401BDD88
0x1401bdded  lea     rdx, [rsi+0A0h]
0x1401bddf4  mov     rcx, r12
0x1401bddf7  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401bddfe  nop     dword ptr [rax+rax+00h]
0x1401bde03  jmp     loc_1401BDC27
0x1401bde08  test    r13, r13
0x1401bde0b  jz      short loc_1401BDE11
0x1401bde0d  mov     [r13+40h], rdi
0x1401bde11  lea     rdx, [rsi+0A0h]
0x1401bde18  mov     rcx, r12
0x1401bde1b  call    cs:__imp_FsRtlReleaseEofLock
0x1401bde22  nop     dword ptr [rax+rax+00h]
0x1401bde27  jmp     loc_1401BDD83
0x1401bde2c  mov     byte ptr [rsp+328h+var_300], r14b
0x1401bde31  mov     eax, [rsp+328h+arg_20]
0x1401bde38  mov     dword ptr [rsp+328h+var_308], eax
0x1401bde3c  mov     r9d, [rsp+328h+var_2D8]
0x1401bde41  mov     r8, [rsp+328h+var_2D0]
0x1401bde46  mov     rcx, r13
0x1401bde49  call    NtfsFastIoCheckIfPossibleInternal
0x1401bde4e  test    al, al
0x1401bde50  jnz     loc_1401BDC4E
0x1401bde56  call    cs:__imp_FsRtlIncrementCcFastReadNotPossible
0x1401bde5d  nop     dword ptr [rax+rax+00h]
0x1401bde62  mov     r14b, dil
0x1401bde65  jmp     loc_1401BDD78
0x1401bde6a  mov     rax, [rsi+28h]
0x1401bde6e  jmp     loc_1401BDC0D
0x1401bde73  mov     rcx, [rsp+328h+var_2D0]
0x1401bde78  cmp     [rcx], rax
0x1401bde7b  jl      short loc_1401BDEDF
0x1401bde7d  mov     al, cs:NtfsStatusDebugFlags
0x1401bde83  mov     dword ptr [r15], 0C0000011h
0x1401bde8a  mov     [r15+8], rdi
0x1401bde8e  jmp     loc_1401BDD78
0x1401bde93  test    r12b, r12b
0x1401bde96  jz      loc_1401BDFD1
0x1401bde9c  lea     rax, [rsp+328h+var_2E7]
0x1401bdea1  mov     [rsp+328h+var_300], rax
0x1401bdea6  mov     byte ptr [rsp+328h+var_308], r14b
0x1401bdeab  mov     r9, [rsp+328h+var_2A8]
0x1401bdeb3  mov     r8, [rsp+328h+var_2D0]
0x1401bdeb8  mov     r8, [r8]
0x1401bdebb  mov     rdx, rsi
0x1401bdebe  mov     rcx, r13
0x1401bdec1  call    NtfsGetIoAtEof
0x1401bdec6  jmp     loc_1401BDC19
0x1401bdecb  call    cs:__imp_FsRtlIncrementCcFastReadResourceMiss
0x1401bded2  nop     dword ptr [rax+rax+00h]
0x1401bded7  mov     r14b, dil
  ... truncated ...
```
