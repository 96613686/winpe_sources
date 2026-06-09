# CldSyncSendCancelHydrationRequest

- ea: `0x14003e5e4`
- end: `0x14003eba5`
- name: `CldSyncSendCancelHydrationRequest`
- size: `1473`
- prototype: `void __fastcall(struct _EX_RUNDOWN_REF *, __int64, __int64, __int64, __int64, int, int, __int64, unsigned int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x140041754`

## callees

- `0x140003c50`
- `0x14000ac28`
- `0x14000d868`
- `0x14000f7b0`
- `0x14000f83c`
- `0x14000fbec`
- `0x14000fcec`
- `0x140036120`
- `0x140037e4c`
- `0x14003e5e4`
- `0x14003f624`
- `0x14003f660`
- `0x140056c50`
- `0x140056ccc`
- `0x1400577f8`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14003eb84`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003eb84`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14003e9f2`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14003e9f2`
- `FLTMGR!FltReleasePushLockEx` at `0x14003eb6c`
- `FLTMGR!FltReleasePushLockEx` at `0x14003eb6c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003e783`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003e783`

## pseudocode

```c
void __fastcall CldSyncSendCancelHydrationRequest(
        struct _EX_RUNDOWN_REF *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        unsigned int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  struct _EX_RUNDOWN_REF *v13; // r15
  __int64 v14; // rbx
  _QWORD *v15; // r13
  unsigned int v16; // r10d
  char v17; // bp
  int v18; // r9d
  __int64 v19; // r8
  __int64 v20; // r11
  __int64 v21; // rdx
  __int64 v22; // r15
  __int64 v23; // rsi
  __int64 v24; // r12
  __int64 v25; // rdi
  int v26; // r9d
  int v27; // r10d
  __int64 v28; // r11
  int v29; // eax
  int v30; // ebp
  int v31; // eax
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // ebx
  int v35; // esi
  __int64 v36; // rcx
  int v37; // ebp
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r14
  unsigned int v42; // ebp
  int v43; // ebx
  int v44; // eax
  int i; // ebx
  __int64 v46; // rcx
  __int64 v47; // [rsp+30h] [rbp-98h]
  __int64 v48; // [rsp+40h] [rbp-88h]
  char v49; // [rsp+60h] [rbp-68h]
  int v50; // [rsp+64h] [rbp-64h]
  __int64 v51; // [rsp+68h] [rbp-60h]

  v13 = a1;
  v14 = (unsigned int)CldiSyncReferenceRoot();
  HsmDbgBreakOnStatus(v14);
  if ( (int)v14 >= 0 )
  {
    v15 = CldSyncReferenceStream((__int64)v13, a4, 1);
    if ( v15 )
    {
      v16 = a9;
      v17 = 0;
      v18 = 0;
      v49 = 0;
      v50 = 0;
      v19 = ~(a9 - 1LL);
      v20 = (a10 & v19) / a9;
      v21 = (v19 & (a9 + a10 + a11 - 1)) % a9;
      v22 = (v19 & (a9 + a10 + a11 - 1)) / a9;
      v51 = v22;
      while ( 2 )
      {
        v23 = v20;
        v24 = v18 != 0 ? 72LL : 56LL;
        v25 = (__int64)v15 + v24;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qDii(WPP_GLOBAL_Control->AttachedDevice, v21, v19, (char *)v15 + v24, v16, v20, v22);
        }
        if ( !v17 )
        {
          FltAcquirePushLockExclusiveEx(v15 + 3, 0);
          v49 = 1;
        }
        v26 = 0;
        v27 = *(_DWORD *)((char *)v15 + v24 + 4) - 1;
        if ( v27 >= 0 )
        {
          v28 = *(_QWORD *)(v25 + 8);
          do
          {
            v19 = (unsigned int)((v27 + v26) >> 1);
            if ( *(_QWORD *)(v28 + 24LL * (int)v19) >= v23 )
              v27 = v19 - 1;
            v29 = v19 + 1;
            if ( *(_QWORD *)(v28 + 24LL * (int)v19) >= v23 )
              v29 = v26;
            v26 = v29;
          }
          while ( v29 <= v27 );
        }
        v30 = 0;
        if ( v26 - 1 >= 0 )
          v30 = v26 - 1;
        while ( 1 )
        {
          v31 = *(_DWORD *)((char *)v15 + v24 + 4);
          if ( v30 >= v31 || v23 >= v22 )
            break;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qDiidii(
              WPP_GLOBAL_Control->AttachedDevice,
              *(_QWORD *)(v25 + 8),
              3LL * v30,
              (char *)v15 + v24,
              v30,
              *(_QWORD *)(*(_QWORD *)(v25 + 8) + 24LL * v30),
              *(_QWORD *)(*(_QWORD *)(v25 + 8) + 24LL * v30 + 8),
              *(_DWORD *)(*(_QWORD *)(v25 + 8) + 24LL * v30 + 16),
              v23,
              v22);
          }
          v32 = *(_QWORD *)(v25 + 8);
          v33 = *(_QWORD *)(v32 + 24LL * v30);
          if ( v33 < v22 )
          {
            v21 = v33 + *(_QWORD *)(v32 + 24LL * v30 + 8);
            if ( v23 < v21 )
            {
              if ( v23 > v33 )
                v22 = v23;
              if ( v22 > v33 && v22 < v21 )
              {
                v34 = CldiSyncSplitPendingRange((char *)v15 + v24, (unsigned int)v30, v22);
                HsmDbgBreakOnStatus((unsigned int)v34);
                if ( v34 < 0 )
                {
                  v13 = a1;
                  goto LABEL_74;
                }
              }
              if ( v23 == v22 )
              {
                v22 = v51;
              }
              else
              {
                --*(_DWORD *)(*(_QWORD *)(v25 + 8) + 24LL * v30 + 16);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_qqq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    82,
                    WPP_84af94341c2b38590a04322a1aa95385_Traceguids,
                    (char *)v15 + v24,
                    *(_QWORD *)(*(_QWORD *)(v25 + 8) + 24LL * v30),
                    *(_QWORD *)(*(_QWORD *)(v25 + 8) + 24LL * v30 + 8));
                }
                v22 = v51;
                v23 = *(_QWORD *)(*(_QWORD *)(v25 + 8) + 24LL * v30)
                    + *(_QWORD *)(*(_QWORD *)(v25 + 8) + 24LL * v30 + 8);
                if ( v51 < v23 )
                  v23 = v51;
              }
            }
          }
          ++v30;
        }
        v13 = a1;
        v35 = 0;
        if ( v31 > 0 )
        {
          do
          {
            v21 = *(_QWORD *)(v25 + 8);
            if ( !*(_DWORD *)(v21 + 24LL * v35 + 16) )
            {
              v36 = *(_QWORD *)(v21 + 24LL * v35);
              v37 = v51;
              v38 = (a10 & ~(a9 - 1LL)) / a9;
              v39 = *(_QWORD *)(v21 + 24LL * v35 + 8);
              if ( v38 <= v36 )
                v38 = v36;
              v40 = v36 + v39;
              v41 = v38 * a9;
              if ( v51 >= v40 )
                v37 = v40;
              v42 = a9 * (v37 - v38);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_iqiD(WPP_GLOBAL_Control->AttachedDevice, v40, v38, a4, v25, v41, v42);
              }
              CldiSyncRemovePendingRange(v25, v35--);
              FsRtlRemoveBaseMcbEntry((PBASE_MCB)(v15 + 4), v41 / a9, v42 / a9);
              LODWORD(v48) = a7;
              LODWORD(v47) = a6;
              v43 = CldPortSendCancelHydrationMessage(
                      a1[12].Count,
                      a1->Count,
                      a2,
                      a3,
                      a4,
                      a5,
                      v47,
                      a8,
                      v48,
                      v41,
                      v42,
                      a12);
              HsmDbgBreakOnStatus((unsigned int)v43);
              if ( v43 < 0
                && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              {
                WPP_SF_iqDiD(WPP_GLOBAL_Control->AttachedDevice, v21, v19, a4, v25, a9, v41, v42);
              }
            }
            v44 = *(_DWORD *)(v25 + 4);
            ++v35;
          }
          while ( v35 < v44 );
          if ( v44 > 0 )
          {
            for ( i = 0; i < v44; ++i )
            {
              if ( i < v44 - 1 )
              {
                v46 = *(_QWORD *)(v25 + 8);
                v21 = 3LL * i;
                v19 = v21;
                if ( *(_DWORD *)(v46 + 24LL * i + 16) == *(_DWORD *)(v46 + 24LL * i + 40)
                  && *(_QWORD *)(v46 + 24LL * i) + *(_QWORD *)(v46 + 24LL * i + 8) == *(_QWORD *)(v46 + 24LL * i + 24) )
                {
                  CldiSyncSplicePendingRanges(v25, (unsigned int)i--);
                }
              }
              v44 = *(_DWORD *)(v25 + 4);
            }
          }
        }
        v16 = a9;
        v18 = v50 + 1;
        v20 = (a10 & ~(a9 - 1LL)) / a9;
        v50 = v18;
        if ( v18 < 2 )
        {
          v22 = v51;
          v17 = v49;
          continue;
        }
        break;
      }
LABEL_74:
      if ( v49 )
        FltReleasePushLockEx(v15 + 3, 0);
      CldiSyncReleaseRundown((__int64)v15);
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
0x14003e5e4  mov     rax, rsp
0x14003e5e7  mov     [rax+20h], r9
0x14003e5eb  mov     [rax+18h], r8
0x14003e5ef  mov     [rax+10h], rdx
0x14003e5f3  mov     [rax+8], rcx
0x14003e5f7  push    rbx
0x14003e5f8  push    rbp
0x14003e5f9  push    rsi
0x14003e5fa  push    rdi
0x14003e5fb  push    r12
0x14003e5fd  push    r13
0x14003e5ff  push    r14
0x14003e601  push    r15
0x14003e603  sub     rsp, 88h
0x14003e60a  mov     rdi, r9
0x14003e60d  mov     r15, rcx
0x14003e610  call    CldiSyncReferenceRoot
0x14003e615  mov     ecx, eax
0x14003e617  mov     ebx, eax
0x14003e619  call    HsmDbgBreakOnStatus
0x14003e61e  test    ebx, ebx
0x14003e620  jns     short loc_14003E692
0x14003e622  mov     r10, cs:WPP_GLOBAL_Control
0x14003e629  lea     rax, WPP_GLOBAL_Control
0x14003e630  cmp     r10, rax
0x14003e633  jz      loc_14003EB90
0x14003e639  test    dword ptr [r10+2Ch], 100h
0x14003e641  jz      loc_14003EB90
0x14003e647  cmp     byte ptr [r10+29h], 2
0x14003e64c  jb      loc_14003EB90
0x14003e652  mov     rax, [rsp+0C8h+arg_50]
0x14003e65a  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14003e661  mov     rcx, [r10+18h]
0x14003e665  mov     edx, 4Fh ; 'O'
0x14003e66a  mov     dword ptr [rsp+0C8h+var_90], ebx
0x14003e66e  mov     r9, r15
0x14003e671  mov     [rsp+0C8h+var_98], rax
0x14003e676  mov     rax, [rsp+0C8h+arg_48]
0x14003e67e  mov     [rsp+0C8h+var_A0], rax
0x14003e683  mov     [rsp+0C8h+var_A8], rdi
0x14003e688  call    WPP_SF_qqiqd
0x14003e68d  jmp     loc_14003EB90
0x14003e692  mov     r8b, 1
0x14003e695  mov     rdx, rdi
0x14003e698  mov     rcx, r15
0x14003e69b  call    CldSyncReferenceStream
0x14003e6a0  mov     r13, rax
0x14003e6a3  test    rax, rax
0x14003e6a6  jnz     short loc_14003E6B7
0x14003e6a8  mov     ecx, 0C0000189h
0x14003e6ad  call    HsmDbgBreakOnStatus
0x14003e6b2  jmp     loc_14003EB80
0x14003e6b7  mov     r10d, [rsp+0C8h+arg_40]
0x14003e6bf  lea     rbx, WPP_GLOBAL_Control
0x14003e6c6  mov     rcx, [rsp+0C8h+arg_48]
0x14003e6ce  xor     bpl, bpl
0x14003e6d1  xor     r9d, r9d
0x14003e6d4  mov     [rsp+0C8h+var_68], bpl
0x14003e6d9  mov     [rsp+0C8h+var_64], r9d
0x14003e6de  lea     r8, [r10-1]
0x14003e6e2  mov     [rsp+0C8h+var_58], r10
0x14003e6e7  not     r8
0x14003e6ea  mov     rax, r8
0x14003e6ed  and     rax, rcx
0x14003e6f0  cqo
0x14003e6f2  idiv    r10
0x14003e6f5  lea     rdx, [r10+rcx]
0x14003e6f9  mov     r11, rax
0x14003e6fc  mov     [rsp+0C8h+var_50], rax
0x14003e701  mov     rax, [rsp+0C8h+arg_50]
0x14003e709  dec     rax
0x14003e70c  add     rax, rdx
0x14003e70f  and     rax, r8
0x14003e712  cqo
0x14003e714  idiv    r10
0x14003e717  mov     r15, rax
0x14003e71a  mov     [rsp+0C8h+var_60], rax
0x14003e71f  jmp     short loc_14003E72B
0x14003e721  mov     r15, [rsp+0C8h+var_60]
0x14003e726  mov     bpl, [rsp+0C8h+var_68]
0x14003e72b  mov     rsi, r11
0x14003e72e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e735  mov     eax, r9d
0x14003e738  neg     eax
0x14003e73a  sbb     r12, r12
0x14003e73d  and     r12d, 10h
0x14003e741  add     r12, 38h ; '8'
0x14003e745  lea     rdi, [r12+r13]
0x14003e749  cmp     rcx, rbx
0x14003e74c  jz      short loc_14003E778
0x14003e74e  test    dword ptr [rcx+2Ch], 100h
0x14003e755  jz      short loc_14003E778
0x14003e757  cmp     byte ptr [rcx+29h], 4
0x14003e75b  jb      short loc_14003E778
0x14003e75d  mov     rcx, [rcx+18h]
0x14003e761  mov     r9, rdi
0x14003e764  mov     [rsp+0C8h+var_98], r15
0x14003e769  mov     [rsp+0C8h+var_A0], r11
0x14003e76e  mov     dword ptr [rsp+0C8h+var_A8], r10d
0x14003e773  call    WPP_SF_qDii
0x14003e778  test    bpl, bpl
0x14003e77b  jnz     short loc_14003E794
0x14003e77d  lea     rcx, [r13+18h]
0x14003e781  xor     edx, edx
0x14003e783  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14003e78a  nop     dword ptr [rax+rax+00h]
0x14003e78f  mov     [rsp+0C8h+var_68], 1
0x14003e794  mov     r10d, [r12+r13+4]
0x14003e799  xor     r9d, r9d
0x14003e79c  sub     r10d, 1
0x14003e7a0  js      short loc_14003E7D0
0x14003e7a2  mov     r11, [rdi+8]
0x14003e7a6  lea     r8d, [r10+r9]
0x14003e7aa  sar     r8d, 1
0x14003e7ad  movsxd  rax, r8d
0x14003e7b0  lea     rcx, [rax+rax*2]
0x14003e7b4  cmp     [r11+rcx*8], rsi
0x14003e7b8  lea     eax, [r8-1]
0x14003e7bc  cmovge  r10d, eax
0x14003e7c0  lea     eax, [r8+1]
0x14003e7c4  cmovge  eax, r9d
0x14003e7c8  mov     r9d, eax
0x14003e7cb  cmp     eax, r10d
0x14003e7ce  jle     short loc_14003E7A6
0x14003e7d0  lea     eax, [r9-1]
0x14003e7d4  xor     ebp, ebp
0x14003e7d6  test    eax, eax
0x14003e7d8  cmovns  ebp, eax
0x14003e7db  mov     eax, [r12+r13+4]
0x14003e7e0  cmp     ebp, eax
0x14003e7e2  jge     loc_14003E92B
0x14003e7e8  cmp     rsi, r15
0x14003e7eb  jge     loc_14003E92B
0x14003e7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e7f8  cmp     rcx, rbx
0x14003e7fb  jz      short loc_14003E84D
0x14003e7fd  test    dword ptr [rcx+2Ch], 100h
0x14003e804  jz      short loc_14003E84D
0x14003e806  cmp     byte ptr [rcx+29h], 4
0x14003e80a  jb      short loc_14003E84D
0x14003e80c  mov     rdx, [rdi+8]
0x14003e810  mov     r9, rdi
0x14003e813  mov     rcx, [rcx+18h]
0x14003e817  mov     [rsp+0C8h+var_80], r15
0x14003e81c  mov     [rsp+0C8h+var_88], rsi
0x14003e821  movsxd  rax, ebp
0x14003e824  lea     r8, [rax+rax*2]
0x14003e828  mov     eax, [rdx+r8*8+10h]
0x14003e82d  mov     dword ptr [rsp+0C8h+var_90], eax
0x14003e831  mov     rax, [rdx+r8*8+8]
0x14003e836  mov     [rsp+0C8h+var_98], rax
0x14003e83b  mov     rax, [rdx+r8*8]
0x14003e83f  mov     [rsp+0C8h+var_A0], rax
0x14003e844  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x14003e848  call    WPP_SF_qDiidii
0x14003e84d  movsxd  rax, ebp
0x14003e850  lea     r14, [rax+rax*2]
0x14003e854  mov     rax, [rdi+8]
0x14003e858  mov     rcx, [rax+r14*8]
0x14003e85c  cmp     rcx, r15
0x14003e85f  jge     loc_14003E924
0x14003e865  mov     rdx, [rax+r14*8+8]
0x14003e86a  add     rdx, rcx
0x14003e86d  cmp     rsi, rdx
0x14003e870  jge     loc_14003E924
0x14003e876  cmp     rsi, rcx
0x14003e879  cmovg   r15, rsi
0x14003e87d  cmp     r15, rcx
0x14003e880  jle     short loc_14003E8AC
0x14003e882  cmp     r15, rdx
0x14003e885  jge     short loc_14003E8AC
0x14003e887  mov     r8, r15
0x14003e88a  mov     edx, ebp
0x14003e88c  mov     rcx, rdi
0x14003e88f  call    CldiSyncSplitPendingRange
0x14003e894  mov     ecx, eax
0x14003e896  mov     ebx, eax
0x14003e898  call    HsmDbgBreakOnStatus
0x14003e89d  test    ebx, ebx
0x14003e89f  js      loc_14003EB57
0x14003e8a5  lea     rbx, WPP_GLOBAL_Control
0x14003e8ac  cmp     rsi, r15
0x14003e8af  jz      short loc_14003E91F
0x14003e8b1  mov     rax, [rdi+8]
0x14003e8b5  dec     dword ptr [rax+r14*8+10h]
0x14003e8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e8c1  cmp     rcx, rbx
0x14003e8c4  jz      short loc_14003E904
0x14003e8c6  test    dword ptr [rcx+2Ch], 100h
0x14003e8cd  jz      short loc_14003E904
0x14003e8cf  cmp     byte ptr [rcx+29h], 4
0x14003e8d3  jb      short loc_14003E904
0x14003e8d5  mov     r8, [rdi+8]
0x14003e8d9  mov     edx, 52h ; 'R'
0x14003e8de  mov     rcx, [rcx+18h]
0x14003e8e2  mov     r9, rdi
0x14003e8e5  mov     rax, [r8+r14*8+8]
0x14003e8ea  mov     [rsp+0C8h+var_A0], rax
0x14003e8ef  mov     rax, [r8+r14*8]
0x14003e8f3  lea     r8, WPP_84af94341c2b38590a04322a1aa95385_Traceguids
0x14003e8fa  mov     [rsp+0C8h+var_A8], rax
0x14003e8ff  call    WPP_SF_qqq
0x14003e904  mov     rax, [rdi+8]
0x14003e908  mov     r15, [rsp+0C8h+var_60]
0x14003e90d  mov     rsi, [rax+r14*8+8]
0x14003e912  add     rsi, [rax+r14*8]
0x14003e916  cmp     r15, rsi
0x14003e919  cmovl   rsi, r15
0x14003e91d  jmp     short loc_14003E924
0x14003e91f  mov     r15, [rsp+0C8h+var_60]
0x14003e924  inc     ebp
0x14003e926  jmp     loc_14003E7DB
0x14003e92b  mov     r15, [rsp+0C8h+arg_0]
0x14003e933  xor     esi, esi
0x14003e935  test    eax, eax
0x14003e937  jle     loc_14003EB2A
0x14003e93d  mov     r12, [rsp+0C8h+var_60]
0x14003e942  mov     rdx, [rdi+8]
0x14003e946  movsxd  rax, esi
0x14003e949  lea     rax, [rax+rax*2]
0x14003e94d  cmp     dword ptr [rdx+rax*8+10h], 0
0x14003e952  jnz     loc_14003EAD2
0x14003e958  mov     rcx, [rdx+rax*8]
0x14003e95c  mov     ebp, r12d
0x14003e95f  mov     r8, [rsp+0C8h+var_50]
0x14003e964  mov     rdx, [rdx+rax*8+8]
0x14003e969  cmp     r8, rcx
0x14003e96c  mov     r14, [rsp+0C8h+var_58]
0x14003e971  cmovle  r8, rcx
0x14003e975  add     rdx, rcx
0x14003e978  imul    r14, r8
0x14003e97c  cmp     r12, rdx
0x14003e97f  cmovge  ebp, edx
0x14003e982  sub     ebp, r8d
0x14003e985  imul    ebp, [rsp+0C8h+arg_40]
0x14003e98d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e994  cmp     rcx, rbx
0x14003e997  jz      short loc_14003E9C7
0x14003e999  test    dword ptr [rcx+2Ch], 100h
0x14003e9a0  jz      short loc_14003E9C7
0x14003e9a2  cmp     byte ptr [rcx+29h], 4
0x14003e9a6  jb      short loc_14003E9C7
0x14003e9a8  mov     r9, [rsp+0C8h+arg_18]
0x14003e9b0  mov     rcx, [rcx+18h]
0x14003e9b4  mov     dword ptr [rsp+0C8h+var_98], ebp
0x14003e9b8  mov     [rsp+0C8h+var_A0], r14
0x14003e9bd  mov     [rsp+0C8h+var_A8], rdi
0x14003e9c2  call    WPP_SF_iqiD
0x14003e9c7  mov     edx, esi
0x14003e9c9  mov     rcx, rdi
0x14003e9cc  call    CldiSyncRemovePendingRange
0x14003e9d1  xor     edx, edx
0x14003e9d3  lea     rcx, [r13+20h]; Mcb
0x14003e9d7  mov     eax, ebp
0x14003e9d9  dec     esi
0x14003e9db  div     [rsp+0C8h+arg_40]
0x14003e9e2  mov     r8d, eax; SectorCount
0x14003e9e5  mov     rax, r14
0x14003e9e8  cqo
0x14003e9ea  idiv    [rsp+0C8h+var_58]
0x14003e9ef  mov     rdx, rax; Vbn
0x14003e9f2  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x14003e9f9  nop     dword ptr [rax+rax+00h]
0x14003e9fe  mov     rcx, [rsp+0C8h+arg_58]
0x14003ea06  mov     rdx, [r15]
0x14003ea09  mov     r9, [rsp+0C8h+arg_10]
0x14003ea11  mov     r8, [rsp+0C8h+arg_8]
0x14003ea19  mov     [rsp+0C8h+var_70], rcx
0x14003ea1e  mov     rcx, [r15+60h]
0x14003ea22  mov     eax, ebp
0x14003ea24  mov     [rsp+0C8h+var_78], rax
0x14003ea29  mov     eax, [rsp+0C8h+arg_30]
0x14003ea30  mov     [rsp+0C8h+var_80], r14
0x14003ea35  mov     dword ptr [rsp+0C8h+var_88], eax
0x14003ea39  mov     rax, [rsp+0C8h+arg_38]
0x14003ea41  mov     [rsp+0C8h+var_90], rax
0x14003ea46  mov     eax, [rsp+0C8h+arg_28]
0x14003ea4d  mov     dword ptr [rsp+0C8h+var_98], eax
0x14003ea51  mov     rax, [rsp+0C8h+arg_20]
0x14003ea59  mov     [rsp+0C8h+var_A0], rax
0x14003ea5e  mov     rax, [rsp+0C8h+arg_18]
0x14003ea66  mov     [rsp+0C8h+var_A8], rax
0x14003ea6b  call    CldPortSendCancelHydrationMessage
0x14003ea70  mov     ecx, eax
0x14003ea72  mov     ebx, eax
0x14003ea74  call    HsmDbgBreakOnStatus
0x14003ea79  test    ebx, ebx
0x14003ea7b  jns     short loc_14003EACB
0x14003ea7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ea84  lea     rbx, WPP_GLOBAL_Control
0x14003ea8b  cmp     rcx, rbx
0x14003ea8e  jz      short loc_14003EAD2
0x14003ea90  test    dword ptr [rcx+2Ch], 100h
0x14003ea97  jz      short loc_14003EAD2
0x14003ea99  cmp     byte ptr [rcx+29h], 3
0x14003ea9d  jb      short loc_14003EAD2
0x14003ea9f  mov     eax, [rsp+0C8h+arg_40]
0x14003eaa6  mov     r9, [rsp+0C8h+arg_18]
0x14003eaae  mov     rcx, [rcx+18h]
0x14003eab2  mov     dword ptr [rsp+0C8h+var_90], ebp
  ... truncated ...
```
