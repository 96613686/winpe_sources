# CldSyncSendCancelHydrationRequest

- ea: `0x14003e5c4`
- end: `0x14003eb85`
- name: `CldSyncSendCancelHydrationRequest`
- size: `1473`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x140041700`

## callees

- `0x140003c50`
- `0x14000ac28`
- `0x14000d868`
- `0x14000f748`
- `0x14000f7d4`
- `0x14000fb84`
- `0x14000fc84`
- `0x140036120`
- `0x140037e2c`
- `0x14003e5c4`
- `0x14003f604`
- `0x14003f640`
- `0x140056b30`
- `0x140056bac`
- `0x1400576d8`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14003eb64`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003eb64`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14003e9d2`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14003e9d2`
- `FLTMGR!FltReleasePushLockEx` at `0x14003eb4c`
- `FLTMGR!FltReleasePushLockEx` at `0x14003eb4c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003e763`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003e763`

## pseudocode

```c
void __fastcall CldSyncSendCancelHydrationRequest(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        int a6,
        int a7,
        __int64 a8,
        unsigned int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  struct _EX_RUNDOWN_REF *v13; // r15
  int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // r13
  unsigned int v17; // r10d
  char v18; // bp
  int v19; // r9d
  __int64 v20; // r8
  __int64 v21; // r11
  __int64 v22; // rdx
  __int64 v23; // r15
  __int64 v24; // rsi
  __int64 v25; // r12
  __int64 v26; // rdi
  int v27; // r9d
  int v28; // r10d
  __int64 v29; // r11
  int v30; // eax
  int v31; // ebp
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  int v35; // ebx
  int v36; // esi
  __int64 v37; // rcx
  int v38; // ebp
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // r14
  unsigned int v43; // ebp
  int v44; // ebx
  int v45; // eax
  int i; // ebx
  __int64 v47; // rcx
  char v48; // [rsp+60h] [rbp-68h]
  int v49; // [rsp+64h] [rbp-64h]
  __int64 v50; // [rsp+68h] [rbp-60h]

  v13 = (struct _EX_RUNDOWN_REF *)a1;
  v14 = CldiSyncReferenceRoot();
  HsmDbgBreakOnStatus((unsigned int)v14);
  if ( v14 >= 0 )
  {
    LOBYTE(v15) = 1;
    v16 = CldSyncReferenceStream(v13, a4, v15);
    if ( v16 )
    {
      v17 = a9;
      v18 = 0;
      v19 = 0;
      v48 = 0;
      v49 = 0;
      v20 = ~(a9 - 1LL);
      v21 = (a10 & v20) / a9;
      v22 = (v20 & (a9 + a10 + a11 - 1)) % a9;
      v23 = (v20 & (a9 + a10 + a11 - 1)) / a9;
      v50 = v23;
      while ( 2 )
      {
        v24 = v21;
        v25 = v19 != 0 ? 72LL : 56LL;
        v26 = v25 + v16;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qDii(WPP_GLOBAL_Control->AttachedDevice, v22, v20, v25 + v16, v17, v21, v23);
        }
        if ( !v18 )
        {
          FltAcquirePushLockExclusiveEx(v16 + 24, 0);
          v48 = 1;
        }
        v27 = 0;
        v28 = *(_DWORD *)(v25 + v16 + 4) - 1;
        if ( v28 >= 0 )
        {
          v29 = *(_QWORD *)(v26 + 8);
          do
          {
            v20 = (unsigned int)((v28 + v27) >> 1);
            if ( *(_QWORD *)(v29 + 24LL * (int)v20) >= v24 )
              v28 = v20 - 1;
            v30 = v20 + 1;
            if ( *(_QWORD *)(v29 + 24LL * (int)v20) >= v24 )
              v30 = v27;
            v27 = v30;
          }
          while ( v30 <= v28 );
        }
        v31 = 0;
        if ( v27 - 1 >= 0 )
          v31 = v27 - 1;
        while ( 1 )
        {
          v32 = *(_DWORD *)(v25 + v16 + 4);
          if ( v31 >= v32 || v24 >= v23 )
            break;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qDiidii(
              WPP_GLOBAL_Control->AttachedDevice,
              *(_QWORD *)(v26 + 8),
              3LL * v31,
              v25 + v16,
              v31,
              *(_QWORD *)(*(_QWORD *)(v26 + 8) + 24LL * v31),
              *(_QWORD *)(*(_QWORD *)(v26 + 8) + 24LL * v31 + 8),
              *(_DWORD *)(*(_QWORD *)(v26 + 8) + 24LL * v31 + 16),
              v24,
              v23);
          }
          v33 = *(_QWORD *)(v26 + 8);
          v34 = *(_QWORD *)(v33 + 24LL * v31);
          if ( v34 < v23 )
          {
            v22 = v34 + *(_QWORD *)(v33 + 24LL * v31 + 8);
            if ( v24 < v22 )
            {
              if ( v24 > v34 )
                v23 = v24;
              if ( v23 > v34 && v23 < v22 )
              {
                v35 = CldiSyncSplitPendingRange(v25 + v16, (unsigned int)v31, v23);
                HsmDbgBreakOnStatus((unsigned int)v35);
                if ( v35 < 0 )
                {
                  v13 = (struct _EX_RUNDOWN_REF *)a1;
                  goto LABEL_74;
                }
              }
              if ( v24 == v23 )
              {
                v23 = v50;
              }
              else
              {
                --*(_DWORD *)(*(_QWORD *)(v26 + 8) + 24LL * v31 + 16);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_qqq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    82,
                    WPP_84af94341c2b38590a04322a1aa95385_Traceguids,
                    v25 + v16,
                    *(_QWORD *)(*(_QWORD *)(v26 + 8) + 24LL * v31),
                    *(_QWORD *)(*(_QWORD *)(v26 + 8) + 24LL * v31 + 8));
                }
                v23 = v50;
                v24 = *(_QWORD *)(*(_QWORD *)(v26 + 8) + 24LL * v31)
                    + *(_QWORD *)(*(_QWORD *)(v26 + 8) + 24LL * v31 + 8);
                if ( v50 < v24 )
                  v24 = v50;
              }
            }
          }
          ++v31;
        }
        v13 = (struct _EX_RUNDOWN_REF *)a1;
        v36 = 0;
        if ( v32 > 0 )
        {
          do
          {
            v22 = *(_QWORD *)(v26 + 8);
            if ( !*(_DWORD *)(v22 + 24LL * v36 + 16) )
            {
              v37 = *(_QWORD *)(v22 + 24LL * v36);
              v38 = v50;
              v39 = (a10 & ~(a9 - 1LL)) / a9;
              v40 = *(_QWORD *)(v22 + 24LL * v36 + 8);
              if ( v39 <= v37 )
                v39 = v37;
              v41 = v37 + v40;
              v42 = v39 * a9;
              if ( v50 >= v41 )
                v38 = v41;
              v43 = a9 * (v38 - v39);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_iqiD(WPP_GLOBAL_Control->AttachedDevice, v41, v39, a4, v26, v42, v43);
              }
              CldiSyncRemovePendingRange(v26, (unsigned int)v36--);
              FsRtlRemoveBaseMcbEntry((PBASE_MCB)(v16 + 32), v42 / a9, v43 / a9);
              v44 = CldPortSendCancelHydrationMessage(a1[12], *a1, a2, a3, a4, a5, a6, a8, a7, v42, v43, a12);
              HsmDbgBreakOnStatus((unsigned int)v44);
              if ( v44 < 0
                && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              {
                WPP_SF_iqDiD(WPP_GLOBAL_Control->AttachedDevice, v22, v20, a4, v26, a9, v42, v43);
              }
            }
            v45 = *(_DWORD *)(v26 + 4);
            ++v36;
          }
          while ( v36 < v45 );
          if ( v45 > 0 )
          {
            for ( i = 0; i < v45; ++i )
            {
              if ( i < v45 - 1 )
              {
                v47 = *(_QWORD *)(v26 + 8);
                v22 = 3LL * i;
                v20 = v22;
                if ( *(_DWORD *)(v47 + 24LL * i + 16) == *(_DWORD *)(v47 + 24LL * i + 40)
                  && *(_QWORD *)(v47 + 24LL * i) + *(_QWORD *)(v47 + 24LL * i + 8) == *(_QWORD *)(v47 + 24LL * i + 24) )
                {
                  CldiSyncSplicePendingRanges(v26, (unsigned int)i--);
                }
              }
              v45 = *(_DWORD *)(v26 + 4);
            }
          }
        }
        v17 = a9;
        v19 = v49 + 1;
        v21 = (a10 & ~(a9 - 1LL)) / a9;
        v49 = v19;
        if ( v19 < 2 )
        {
          v23 = v50;
          v18 = v48;
          continue;
        }
        break;
      }
LABEL_74:
      if ( v48 )
        FltReleasePushLockEx(v16 + 24, 0);
      CldiSyncReleaseRundown(v16);
    }
    else
    {
      HsmDbgBreakOnStatus(3221225865LL);
    }
    ExReleaseRundownProtection(v13 + 11);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqiqd(
      WPP_GLOBAL_Control->AttachedDevice,
      79,
      WPP_84af94341c2b38590a04322a1aa95385_Traceguids,
      v13,
      a4,
      a10,
      a11,
      v14);
  }
}

```

## disassembly

```asm
0x14003e5c4  mov     rax, rsp
0x14003e5c7  mov     [rax+20h], r9
0x14003e5cb  mov     [rax+18h], r8
0x14003e5cf  mov     [rax+10h], rdx
0x14003e5d3  mov     [rax+8], rcx
0x14003e5d7  push    rbx
0x14003e5d8  push    rbp
0x14003e5d9  push    rsi
0x14003e5da  push    rdi
0x14003e5db  push    r12
0x14003e5dd  push    r13
0x14003e5df  push    r14
0x14003e5e1  push    r15
0x14003e5e3  sub     rsp, 88h
0x14003e5ea  mov     rdi, r9
0x14003e5ed  mov     r15, rcx
0x14003e5f0  call    CldiSyncReferenceRoot
0x14003e5f5  mov     ecx, eax
0x14003e5f7  mov     ebx, eax
0x14003e5f9  call    HsmDbgBreakOnStatus
0x14003e5fe  test    ebx, ebx
0x14003e600  jns     short loc_14003E672
0x14003e602  mov     r10, cs:WPP_GLOBAL_Control
0x14003e609  lea     rax, WPP_GLOBAL_Control
0x14003e610  cmp     r10, rax
0x14003e613  jz      loc_14003EB70
0x14003e619  test    dword ptr [r10+2Ch], 100h
0x14003e621  jz      loc_14003EB70
0x14003e627  cmp     byte ptr [r10+29h], 2
0x14003e62c  jb      loc_14003EB70
0x14003e632  mov     rax, [rsp+0C8h+arg_50]
0x14003e63a  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14003e641  mov     rcx, [r10+18h]
0x14003e645  mov     edx, 4Fh ; 'O'
0x14003e64a  mov     dword ptr [rsp+0C8h+var_90], ebx
0x14003e64e  mov     r9, r15
0x14003e651  mov     [rsp+0C8h+var_98], rax
0x14003e656  mov     rax, [rsp+0C8h+arg_48]
0x14003e65e  mov     [rsp+0C8h+var_A0], rax
0x14003e663  mov     [rsp+0C8h+var_A8], rdi
0x14003e668  call    WPP_SF_qqiqd
0x14003e66d  jmp     loc_14003EB70
0x14003e672  mov     r8b, 1
0x14003e675  mov     rdx, rdi
0x14003e678  mov     rcx, r15
0x14003e67b  call    CldSyncReferenceStream
0x14003e680  mov     r13, rax
0x14003e683  test    rax, rax
0x14003e686  jnz     short loc_14003E697
0x14003e688  mov     ecx, 0C0000189h
0x14003e68d  call    HsmDbgBreakOnStatus
0x14003e692  jmp     loc_14003EB60
0x14003e697  mov     r10d, [rsp+0C8h+arg_40]
0x14003e69f  lea     rbx, WPP_GLOBAL_Control
0x14003e6a6  mov     rcx, [rsp+0C8h+arg_48]
0x14003e6ae  xor     bpl, bpl
0x14003e6b1  xor     r9d, r9d
0x14003e6b4  mov     [rsp+0C8h+var_68], bpl
0x14003e6b9  mov     [rsp+0C8h+var_64], r9d
0x14003e6be  lea     r8, [r10-1]
0x14003e6c2  mov     [rsp+0C8h+var_58], r10
0x14003e6c7  not     r8
0x14003e6ca  mov     rax, r8
0x14003e6cd  and     rax, rcx
0x14003e6d0  cqo
0x14003e6d2  idiv    r10
0x14003e6d5  lea     rdx, [r10+rcx]
0x14003e6d9  mov     r11, rax
0x14003e6dc  mov     [rsp+0C8h+var_50], rax
0x14003e6e1  mov     rax, [rsp+0C8h+arg_50]
0x14003e6e9  dec     rax
0x14003e6ec  add     rax, rdx
0x14003e6ef  and     rax, r8
0x14003e6f2  cqo
0x14003e6f4  idiv    r10
0x14003e6f7  mov     r15, rax
0x14003e6fa  mov     [rsp+0C8h+var_60], rax
0x14003e6ff  jmp     short loc_14003E70B
0x14003e701  mov     r15, [rsp+0C8h+var_60]
0x14003e706  mov     bpl, [rsp+0C8h+var_68]
0x14003e70b  mov     rsi, r11
0x14003e70e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e715  mov     eax, r9d
0x14003e718  neg     eax
0x14003e71a  sbb     r12, r12
0x14003e71d  and     r12d, 10h
0x14003e721  add     r12, 38h ; '8'
0x14003e725  lea     rdi, [r12+r13]
0x14003e729  cmp     rcx, rbx
0x14003e72c  jz      short loc_14003E758
0x14003e72e  test    dword ptr [rcx+2Ch], 100h
0x14003e735  jz      short loc_14003E758
0x14003e737  cmp     byte ptr [rcx+29h], 4
0x14003e73b  jb      short loc_14003E758
0x14003e73d  mov     rcx, [rcx+18h]
0x14003e741  mov     r9, rdi
0x14003e744  mov     [rsp+0C8h+var_98], r15
0x14003e749  mov     [rsp+0C8h+var_A0], r11
0x14003e74e  mov     dword ptr [rsp+0C8h+var_A8], r10d
0x14003e753  call    WPP_SF_qDii
0x14003e758  test    bpl, bpl
0x14003e75b  jnz     short loc_14003E774
0x14003e75d  lea     rcx, [r13+18h]
0x14003e761  xor     edx, edx
0x14003e763  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14003e76a  nop     dword ptr [rax+rax+00h]
0x14003e76f  mov     [rsp+0C8h+var_68], 1
0x14003e774  mov     r10d, [r12+r13+4]
0x14003e779  xor     r9d, r9d
0x14003e77c  sub     r10d, 1
0x14003e780  js      short loc_14003E7B0
0x14003e782  mov     r11, [rdi+8]
0x14003e786  lea     r8d, [r10+r9]
0x14003e78a  sar     r8d, 1
0x14003e78d  movsxd  rax, r8d
0x14003e790  lea     rcx, [rax+rax*2]
0x14003e794  cmp     [r11+rcx*8], rsi
0x14003e798  lea     eax, [r8-1]
0x14003e79c  cmovge  r10d, eax
0x14003e7a0  lea     eax, [r8+1]
0x14003e7a4  cmovge  eax, r9d
0x14003e7a8  mov     r9d, eax
0x14003e7ab  cmp     eax, r10d
0x14003e7ae  jle     short loc_14003E786
0x14003e7b0  lea     eax, [r9-1]
0x14003e7b4  xor     ebp, ebp
0x14003e7b6  test    eax, eax
0x14003e7b8  cmovns  ebp, eax
0x14003e7bb  mov     eax, [r12+r13+4]
0x14003e7c0  cmp     ebp, eax
0x14003e7c2  jge     loc_14003E90B
0x14003e7c8  cmp     rsi, r15
0x14003e7cb  jge     loc_14003E90B
0x14003e7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e7d8  cmp     rcx, rbx
0x14003e7db  jz      short loc_14003E82D
0x14003e7dd  test    dword ptr [rcx+2Ch], 100h
0x14003e7e4  jz      short loc_14003E82D
0x14003e7e6  cmp     byte ptr [rcx+29h], 4
0x14003e7ea  jb      short loc_14003E82D
0x14003e7ec  mov     rdx, [rdi+8]
0x14003e7f0  mov     r9, rdi
0x14003e7f3  mov     rcx, [rcx+18h]
0x14003e7f7  mov     [rsp+0C8h+var_80], r15
0x14003e7fc  mov     [rsp+0C8h+var_88], rsi
0x14003e801  movsxd  rax, ebp
0x14003e804  lea     r8, [rax+rax*2]
0x14003e808  mov     eax, [rdx+r8*8+10h]
0x14003e80d  mov     dword ptr [rsp+0C8h+var_90], eax
0x14003e811  mov     rax, [rdx+r8*8+8]
0x14003e816  mov     [rsp+0C8h+var_98], rax
0x14003e81b  mov     rax, [rdx+r8*8]
0x14003e81f  mov     [rsp+0C8h+var_A0], rax
0x14003e824  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x14003e828  call    WPP_SF_qDiidii
0x14003e82d  movsxd  rax, ebp
0x14003e830  lea     r14, [rax+rax*2]
0x14003e834  mov     rax, [rdi+8]
0x14003e838  mov     rcx, [rax+r14*8]
0x14003e83c  cmp     rcx, r15
0x14003e83f  jge     loc_14003E904
0x14003e845  mov     rdx, [rax+r14*8+8]
0x14003e84a  add     rdx, rcx
0x14003e84d  cmp     rsi, rdx
0x14003e850  jge     loc_14003E904
0x14003e856  cmp     rsi, rcx
0x14003e859  cmovg   r15, rsi
0x14003e85d  cmp     r15, rcx
0x14003e860  jle     short loc_14003E88C
0x14003e862  cmp     r15, rdx
0x14003e865  jge     short loc_14003E88C
0x14003e867  mov     r8, r15
0x14003e86a  mov     edx, ebp
0x14003e86c  mov     rcx, rdi
0x14003e86f  call    CldiSyncSplitPendingRange
0x14003e874  mov     ecx, eax
0x14003e876  mov     ebx, eax
0x14003e878  call    HsmDbgBreakOnStatus
0x14003e87d  test    ebx, ebx
0x14003e87f  js      loc_14003EB37
0x14003e885  lea     rbx, WPP_GLOBAL_Control
0x14003e88c  cmp     rsi, r15
0x14003e88f  jz      short loc_14003E8FF
0x14003e891  mov     rax, [rdi+8]
0x14003e895  dec     dword ptr [rax+r14*8+10h]
0x14003e89a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e8a1  cmp     rcx, rbx
0x14003e8a4  jz      short loc_14003E8E4
0x14003e8a6  test    dword ptr [rcx+2Ch], 100h
0x14003e8ad  jz      short loc_14003E8E4
0x14003e8af  cmp     byte ptr [rcx+29h], 4
0x14003e8b3  jb      short loc_14003E8E4
0x14003e8b5  mov     r8, [rdi+8]
0x14003e8b9  mov     edx, 52h ; 'R'
0x14003e8be  mov     rcx, [rcx+18h]
0x14003e8c2  mov     r9, rdi
0x14003e8c5  mov     rax, [r8+r14*8+8]
0x14003e8ca  mov     [rsp+0C8h+var_A0], rax
0x14003e8cf  mov     rax, [r8+r14*8]
0x14003e8d3  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14003e8da  mov     [rsp+0C8h+var_A8], rax
0x14003e8df  call    WPP_SF_qqq
0x14003e8e4  mov     rax, [rdi+8]
0x14003e8e8  mov     r15, [rsp+0C8h+var_60]
0x14003e8ed  mov     rsi, [rax+r14*8+8]
0x14003e8f2  add     rsi, [rax+r14*8]
0x14003e8f6  cmp     r15, rsi
0x14003e8f9  cmovl   rsi, r15
0x14003e8fd  jmp     short loc_14003E904
0x14003e8ff  mov     r15, [rsp+0C8h+var_60]
0x14003e904  inc     ebp
0x14003e906  jmp     loc_14003E7BB
0x14003e90b  mov     r15, [rsp+0C8h+arg_0]
0x14003e913  xor     esi, esi
0x14003e915  test    eax, eax
0x14003e917  jle     loc_14003EB0A
0x14003e91d  mov     r12, [rsp+0C8h+var_60]
0x14003e922  mov     rdx, [rdi+8]
0x14003e926  movsxd  rax, esi
0x14003e929  lea     rax, [rax+rax*2]
0x14003e92d  cmp     dword ptr [rdx+rax*8+10h], 0
0x14003e932  jnz     loc_14003EAB2
0x14003e938  mov     rcx, [rdx+rax*8]
0x14003e93c  mov     ebp, r12d
0x14003e93f  mov     r8, [rsp+0C8h+var_50]
0x14003e944  mov     rdx, [rdx+rax*8+8]
0x14003e949  cmp     r8, rcx
0x14003e94c  mov     r14, [rsp+0C8h+var_58]
0x14003e951  cmovle  r8, rcx
0x14003e955  add     rdx, rcx
0x14003e958  imul    r14, r8
0x14003e95c  cmp     r12, rdx
0x14003e95f  cmovge  ebp, edx
0x14003e962  sub     ebp, r8d
0x14003e965  imul    ebp, [rsp+0C8h+arg_40]
0x14003e96d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e974  cmp     rcx, rbx
0x14003e977  jz      short loc_14003E9A7
0x14003e979  test    dword ptr [rcx+2Ch], 100h
0x14003e980  jz      short loc_14003E9A7
0x14003e982  cmp     byte ptr [rcx+29h], 4
0x14003e986  jb      short loc_14003E9A7
0x14003e988  mov     r9, [rsp+0C8h+arg_18]
0x14003e990  mov     rcx, [rcx+18h]
0x14003e994  mov     dword ptr [rsp+0C8h+var_98], ebp
0x14003e998  mov     [rsp+0C8h+var_A0], r14
0x14003e99d  mov     [rsp+0C8h+var_A8], rdi
0x14003e9a2  call    WPP_SF_iqiD
0x14003e9a7  mov     edx, esi
0x14003e9a9  mov     rcx, rdi
0x14003e9ac  call    CldiSyncRemovePendingRange
0x14003e9b1  xor     edx, edx
0x14003e9b3  lea     rcx, [r13+20h]; Mcb
0x14003e9b7  mov     eax, ebp
0x14003e9b9  dec     esi
0x14003e9bb  div     [rsp+0C8h+arg_40]
0x14003e9c2  mov     r8d, eax; SectorCount
0x14003e9c5  mov     rax, r14
0x14003e9c8  cqo
0x14003e9ca  idiv    [rsp+0C8h+var_58]
0x14003e9cf  mov     rdx, rax; Vbn
0x14003e9d2  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x14003e9d9  nop     dword ptr [rax+rax+00h]
0x14003e9de  mov     rcx, [rsp+0C8h+arg_58]
0x14003e9e6  mov     rdx, [r15]
0x14003e9e9  mov     r9, [rsp+0C8h+arg_10]
0x14003e9f1  mov     r8, [rsp+0C8h+arg_8]
0x14003e9f9  mov     [rsp+0C8h+var_70], rcx
0x14003e9fe  mov     rcx, [r15+60h]
0x14003ea02  mov     eax, ebp
0x14003ea04  mov     [rsp+0C8h+var_78], rax
0x14003ea09  mov     eax, [rsp+0C8h+arg_30]
0x14003ea10  mov     [rsp+0C8h+var_80], r14
0x14003ea15  mov     dword ptr [rsp+0C8h+var_88], eax
0x14003ea19  mov     rax, [rsp+0C8h+arg_38]
0x14003ea21  mov     [rsp+0C8h+var_90], rax
0x14003ea26  mov     eax, [rsp+0C8h+arg_28]
0x14003ea2d  mov     dword ptr [rsp+0C8h+var_98], eax
0x14003ea31  mov     rax, [rsp+0C8h+arg_20]
0x14003ea39  mov     [rsp+0C8h+var_A0], rax
0x14003ea3e  mov     rax, [rsp+0C8h+arg_18]
0x14003ea46  mov     [rsp+0C8h+var_A8], rax
0x14003ea4b  call    CldPortSendCancelHydrationMessage
0x14003ea50  mov     ecx, eax
0x14003ea52  mov     ebx, eax
0x14003ea54  call    HsmDbgBreakOnStatus
0x14003ea59  test    ebx, ebx
0x14003ea5b  jns     short loc_14003EAAB
0x14003ea5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ea64  lea     rbx, WPP_GLOBAL_Control
0x14003ea6b  cmp     rcx, rbx
0x14003ea6e  jz      short loc_14003EAB2
0x14003ea70  test    dword ptr [rcx+2Ch], 100h
0x14003ea77  jz      short loc_14003EAB2
0x14003ea79  cmp     byte ptr [rcx+29h], 3
0x14003ea7d  jb      short loc_14003EAB2
0x14003ea7f  mov     eax, [rsp+0C8h+arg_40]
0x14003ea86  mov     r9, [rsp+0C8h+arg_18]
0x14003ea8e  mov     rcx, [rcx+18h]
0x14003ea92  mov     dword ptr [rsp+0C8h+var_90], ebp
  ... truncated ...
```
