# UxpTpDequeueTransmitPacket

- ea: `0x140055c28`
- end: `0x140056325`
- name: `UxpTpDequeueTransmitPacket`
- size: `1789`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x140054b20`
- `0x140054bc4`
- `0x140055460`
- `0x1400558a0`
- `0x140141310`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140035a70`
- `0x14004a970`
- `0x1400521b8`
- `0x140055c28`
- `0x140062bf0`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4444`
- `0x1401d6e48`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140056053`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056053`
- `ntoskrnl!KeReadStateEvent` at `0x140055e38`
- `ntoskrnl!KeReadStateEvent` at `0x140055e75`
- `ntoskrnl!KeReadStateEvent` at `0x140055e95`
- `ntoskrnl!KeReadStateEvent` at `0x140055f3b`
- `ntoskrnl!KeReadStateEvent` at `0x140055e38`
- `ntoskrnl!KeReadStateEvent` at `0x140055e75`
- `ntoskrnl!KeReadStateEvent` at `0x140055e95`
- `ntoskrnl!KeReadStateEvent` at `0x140055f3b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140055fa1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140055fa1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140055caa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140055caa`

## pseudocode

```c
volatile signed __int32 *__fastcall UxpTpDequeueTransmitPacket(
        PKSPIN_LOCK SpinLock,
        unsigned int a2,
        __int64 a3,
        unsigned __int8 a4)
{
  __int64 v5; // rsi
  int v6; // edi
  __int64 v8; // r15
  KSPIN_LOCK v9; // rcx
  __int64 v10; // rdx
  KIRQL v11; // r13
  bool v12; // zf
  int v13; // eax
  KSPIN_LOCK v14; // rdi
  __int64 **v15; // rcx
  PKSPIN_LOCK *v16; // rdx
  __int64 *v17; // rax
  PKSPIN_LOCK v18; // rcx
  KSPIN_LOCK v19; // rdx
  unsigned int v20; // r14d
  unsigned int v21; // edi
  unsigned int v22; // edx
  unsigned __int64 v23; // rax
  unsigned int v24; // edi
  PKSPIN_LOCK v25; // rcx
  __int64 *v26; // rax
  KSPIN_LOCK v27; // rdx
  __int64 *v28; // rdx
  bool v29; // r12
  unsigned int v30; // edi
  PKSPIN_LOCK v31; // rcx
  KSPIN_LOCK *v32; // rdi
  __int64 v33; // r9
  volatile signed __int32 *result; // rax
  __int64 v35; // rcx
  int v36; // ecx
  _QWORD *v37; // rdi
  __int64 v38; // rsi
  __int64 v39; // r9
  __int16 v40; // ax
  __int64 v41; // rdx
  KSPIN_LOCK v42; // rax
  KSPIN_LOCK *v43; // rsi
  int v44; // eax
  __int64 **v45; // rax
  KSPIN_LOCK v46; // rax
  KSPIN_LOCK v47; // rcx
  bool v48; // al
  ULONG_PTR v49; // rdx
  __int64 v50; // [rsp+50h] [rbp-20h] BYREF
  __int64 *v51; // [rsp+58h] [rbp-18h]
  __int128 v52; // [rsp+60h] [rbp-10h] BYREF
  __int64 v53; // [rsp+B0h] [rbp+40h] BYREF
  int v54; // [rsp+B8h] [rbp+48h]

  v5 = a2;
  v50 = (__int64)&v50;
  v6 = a3;
  LOBYTE(v54) = 0;
  v51 = &v50;
  v8 = 0;
  v53 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    v9 = SpinLock[1];
    if ( v9 )
      v10 = *(_QWORD *)(v9 + 48);
    else
      v10 = 0;
    WPP_SF_qqiDDl(v9, v10, a3, SpinLock, v9, v10, v5, a3, a4);
  }
  v11 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  if ( v6 )
    *((_DWORD *)SpinLock + 4) = v6;
  if ( (_DWORD)v5 )
  {
    LOBYTE(v13) = v54;
    SpinLock[3] -= v5;
    v12 = (*((_DWORD *)SpinLock + 8))-- == 1;
    v13 = (unsigned __int8)v13;
    if ( v12 )
      v13 = 1;
    v54 = v13;
  }
  if ( *((_BYTE *)SpinLock + 104) )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 31, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids);
    goto LABEL_63;
  }
  if ( !a4 && !v6 )
  {
    v14 = SpinLock[11];
    SpinLock[11] = 0;
    if ( *(_DWORD *)(v14 + 132) == *(_DWORD *)(v14 + 128) )
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_q(1032, 32, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids, v14);
      --*((_DWORD *)SpinLock + 14);
      v15 = (__int64 **)(v14 + 24);
      SpinLock[8] -= *(_QWORD *)(v14 + 200);
      if ( (*(_BYTE *)(v14 + 96) & 8) != 0 )
      {
        v16 = (PKSPIN_LOCK *)SpinLock[10];
        if ( *v16 != SpinLock + 9 )
          goto LABEL_110;
        *v15 = (__int64 *)(SpinLock + 9);
        *(_QWORD *)(v14 + 32) = v16;
        *v16 = (PKSPIN_LOCK)v15;
        SpinLock[10] = (KSPIN_LOCK)v15;
      }
      else
      {
        v17 = v51;
        if ( (__int64 *)*v51 != &v50 )
          goto LABEL_110;
        *(_QWORD *)(v14 + 32) = v51;
        *v15 = &v50;
        *v17 = (__int64)v15;
        v51 = (__int64 *)(v14 + 24);
      }
    }
    else
    {
      if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
        WPP_SF_q(1032, 33, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids, v14);
      v18 = SpinLock + 5;
      v19 = SpinLock[5];
      if ( *(PKSPIN_LOCK *)(v19 + 8) != SpinLock + 5 )
        goto LABEL_110;
      *(_QWORD *)(v14 + 24) = v19;
      *(_QWORD *)(v14 + 32) = v18;
      *(_QWORD *)(v19 + 8) = v14 + 24;
      *v18 = v14 + 24;
    }
  }
  v20 = 0x10000;
  if ( *((_DWORD *)SpinLock + 8) <= 1u )
    goto LABEL_46;
  if ( *(_DWORD *)(*(_QWORD *)(SpinLock[1] + 1096) + 4384LL) == -1 )
  {
    v21 = *((_DWORD *)SpinLock + 4);
    if ( KeReadStateEvent(UxHighNonPagedPoolEvent) )
    {
      v22 = 2 * v21;
    }
    else
    {
      v22 = 0x10000;
      if ( v21 < 0x10000 )
        v22 = v21;
    }
    v23 = *(unsigned int *)(*(_QWORD *)(SpinLock[1] + 1096) + 4388LL);
    if ( (unsigned int)v23 > v22 )
    {
      v24 = *((_DWORD *)SpinLock + 4);
      if ( KeReadStateEvent(UxHighNonPagedPoolEvent) )
      {
        v23 = 2 * v24;
      }
      else
      {
        v23 = 0x10000;
        if ( v24 < 0x10000 )
          v23 = v24;
      }
    }
  }
  else
  {
    v23 = KeReadStateEvent(UxHighNonPagedPoolEvent)
        ? *(unsigned int *)(*(_QWORD *)(SpinLock[1] + 1096) + 4384LL)
        : 0x10000LL;
  }
  if ( SpinLock[3] < v23 )
  {
LABEL_46:
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_(1032, 34, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids);
    v25 = SpinLock + 9;
    while ( 1 )
    {
      v26 = (__int64 *)*v25;
      if ( (PKSPIN_LOCK)*v25 == v25 )
        break;
      if ( (PKSPIN_LOCK)v26[1] != v25 )
        goto LABEL_110;
      v27 = *v26;
      if ( *(__int64 **)(*v26 + 8) != v26 )
        goto LABEL_110;
      *v25 = v27;
      *(_QWORD *)(v27 + 8) = v25;
      v28 = v51;
      if ( (__int64 *)*v51 != &v50 )
        goto LABEL_110;
      v26[1] = (__int64)v51;
      *v26 = (__int64)&v50;
      *v28 = (__int64)v26;
      v51 = v26;
    }
  }
  v29 = 0;
  v30 = *((_DWORD *)SpinLock + 4);
  if ( KeReadStateEvent(UxHighNonPagedPoolEvent) )
  {
    v20 = 2 * v30;
  }
  else if ( v30 < 0x10000 )
  {
    v20 = v30;
  }
  if ( SpinLock[3] >= v20 && *((_DWORD *)SpinLock + 8) >= 2u || SpinLock[11] )
    goto LABEL_100;
  v31 = SpinLock + 5;
  v32 = (KSPIN_LOCK *)SpinLock[5];
  if ( v32 != SpinLock + 5 )
  {
    v40 = *((_WORD *)v32 + 36);
    if ( v40 >= 0 )
      v41 = (v40 & 0x4000) != 0 ? *(_QWORD *)(v32[15] + 16) : 0LL;
    else
      v41 = *(_QWORD *)(v32[15] + 152);
    if ( SpinLock[12] == v41 || !*((_DWORD *)SpinLock + 8) )
    {
      if ( (PKSPIN_LOCK)v32[1] == v31 )
      {
        v42 = *v32;
        if ( *(KSPIN_LOCK **)(*v32 + 8) == v32 )
        {
          *v31 = v42;
          v43 = v32 - 3;
          *(_QWORD *)(v42 + 8) = v31;
          v32[1] = (KSPIN_LOCK)v32;
          *v32 = (KSPIN_LOCK)v32;
          SpinLock[11] = (KSPIN_LOCK)(v32 - 3);
          if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
            WPP_SF_qqdd(
              1032,
              35,
              WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids,
              v32 - 3,
              SpinLock[3],
              v20,
              *((_DWORD *)SpinLock + 8));
          v44 = UxpTpAllocateChunkTracker(v32 - 3, v20, &v53);
          if ( v44 >= 0 )
          {
            v8 = v53;
            if ( *(_DWORD *)(v53 + 268) )
            {
              ++*((_DWORD *)SpinLock + 8);
              SpinLock[3] += *(unsigned int *)(v8 + 268);
              if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
                WPP_SF_q(1032, 36, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids, SpinLock[3]);
              LODWORD(v46) = *((unsigned __int16 *)v43 + 48);
              if ( (v46 & 0x8000u) == 0LL )
              {
                if ( (v46 & 0x4000) != 0 )
                {
                  v46 = v43[18];
                  v47 = *(_QWORD *)(v46 + 16);
                }
                else
                {
                  v47 = 0;
                }
              }
              else
              {
                v46 = v43[18];
                v47 = *(_QWORD *)(v46 + 152);
              }
              v12 = v47 == SpinLock[12];
              LOBYTE(v46) = 0;
              SpinLock[12] = v47;
              v29 = !v12;
              v54 = v46;
              goto LABEL_101;
            }
LABEL_100:
            LOBYTE(v46) = v54;
LABEL_101:
            if ( v8 )
            {
              v48 = v29 || (_BYTE)v46;
              *(_BYTE *)(v8 + 257) = v48;
            }
            goto LABEL_63;
          }
          *((_DWORD *)v43 + 17) = v44;
          v45 = (__int64 **)v51;
          SpinLock[11] = 0;
          if ( *v45 == &v50 )
          {
            v8 = v53;
            *v32 = (KSPIN_LOCK)&v50;
            v32[1] = (KSPIN_LOCK)v45;
            *v45 = (__int64 *)v32;
            v51 = (__int64 *)v32;
            *((_BYTE *)SpinLock + 104) = 1;
            goto LABEL_100;
          }
        }
      }
LABEL_110:
      __fastfail(3u);
    }
  }
LABEL_63:
  if ( (_BYTE)v54 )
    SpinLock[12] = 0;
  KeReleaseSpinLock(SpinLock, v11);
  while ( 1 )
  {
    result = (volatile signed __int32 *)v50;
    if ( (__int64 *)v50 == &v50 )
      break;
    if ( *(__int64 **)(v50 + 8) != &v50 )
      goto LABEL_110;
    v35 = *(_QWORD *)v50;
    if ( *(_QWORD *)(*(_QWORD *)v50 + 8LL) != v50 )
      goto LABEL_110;
    v50 = *(_QWORD *)v50;
    *(_QWORD *)(v35 + 8) = &v50;
    *((_QWORD *)result + 1) = result;
    *(_QWORD *)result = result;
    v36 = _InterlockedDecrement(result - 1);
    if ( UxDebugCheckRefcount && v36 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(result - 1), 1u, v36);
    if ( !v36 )
    {
      v37 = result + 66;
      v52 = 0;
      if ( *((_QWORD *)result + 33) || *((_QWORD *)result + 35) || *((_QWORD *)result + 37) )
        UlBugCheckEx(1u, (ULONG_PTR)(result + 66), (ULONG_PTR)"minio\\http\\sys\\tpacket.c", 0x8A4u);
      v38 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)result + 2) + 8LL) + 1088LL);
      if ( KeGetCurrentIrql() )
      {
        LOBYTE(v39) = 1;
        UlThreadPoolEnqueueWorkItem(0, v37, UxpTpFreeTransmitPacketWorker, v39, v38, -1);
      }
      else
      {
        UxPodAttachThread(v38, &v52);
        UxpTpFreeTransmitPacketWorker(v37);
        UxPodDetachThread(&v52);
      }
    }
  }
  if ( v8 )
  {
    v49 = v8 + 208;
    if ( *(_QWORD *)(v8 + 208) || *(_QWORD *)(v8 + 224) || *(_QWORD *)(v8 + 240) )
      UlBugCheckEx(1u, v49, (ULONG_PTR)"minio\\http\\sys\\tpacket.c", 0x8B2u);
    LOBYTE(v33) = 1;
    result = (volatile signed __int32 *)UlThreadPoolEnqueueWorkItem(
                                          0,
                                          v49,
                                          UxpTpProcessMdlRuns,
                                          v33,
                                          *(_QWORD *)(SpinLock[1] + 1088),
                                          -1);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    return (volatile signed __int32 *)WPP_SF_(1032, 37, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140055c28  mov     [rsp-38h+arg_18], rbx
0x140055c2d  push    rbp
0x140055c2e  push    rsi
0x140055c2f  push    rdi
0x140055c30  push    r12
0x140055c32  push    r13
0x140055c34  push    r14
0x140055c36  push    r15
0x140055c38  mov     rbp, rsp
0x140055c3b  sub     rsp, 70h
0x140055c3f  xor     r12d, r12d
0x140055c42  movzx   r14d, r9b
0x140055c46  lea     rax, [rbp+var_20]
0x140055c4a  mov     esi, edx
0x140055c4c  mov     [rbp+var_20], rax
0x140055c50  mov     edi, r8d
0x140055c53  lea     rax, [rbp+var_20]
0x140055c57  mov     byte ptr [rbp+arg_8], r12b
0x140055c5b  mov     [rbp+var_18], rax
0x140055c5f  mov     rbx, rcx
0x140055c62  mov     r15d, r12d
0x140055c65  mov     [rbp+arg_0], r12
0x140055c69  lea     ecx, [r12+1]
0x140055c6e  test    byte ptr cs:xmmword_1401A2CA0+1, cl
0x140055c74  jz      short loc_140055CA7
0x140055c76  mov     rcx, [rbx+8]
0x140055c7a  test    rcx, rcx
0x140055c7d  jz      short loc_140055C85
0x140055c7f  mov     rdx, [rcx+30h]
0x140055c83  jmp     short loc_140055C88
0x140055c85  mov     rdx, r12
0x140055c88  mov     [rsp+70h+var_30], r14d
0x140055c8d  mov     r9, rbx
0x140055c90  mov     [rsp+70h+var_38], edi
0x140055c94  mov     [rsp+70h+var_40], esi
0x140055c98  mov     [rsp+70h+var_48], rdx
0x140055c9d  mov     [rsp+70h+var_50], rcx
0x140055ca2  call    WPP_SF_qqiDDl
0x140055ca7  mov     rcx, rbx; SpinLock
0x140055caa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140055cb1  nop     dword ptr [rax+rax+00h]
0x140055cb6  mov     r13b, al
0x140055cb9  test    edi, edi
0x140055cbb  jz      short loc_140055CC0
0x140055cbd  mov     [rbx+10h], edi
0x140055cc0  mov     r8d, 1
0x140055cc6  test    esi, esi
0x140055cc8  jz      short loc_140055CDF
0x140055cca  mov     eax, [rbp+arg_8]
0x140055ccd  sub     [rbx+18h], rsi
0x140055cd1  add     dword ptr [rbx+20h], 0FFFFFFFFh
0x140055cd5  movzx   eax, al
0x140055cd8  cmovz   eax, r8d
0x140055cdc  mov     [rbp+arg_8], eax
0x140055cdf  cmp     [rbx+68h], r12b
0x140055ce3  jz      short loc_140055D14
0x140055ce5  mov     r14d, 1
0x140055ceb  mov     esi, 408h
0x140055cf0  test    byte ptr cs:xmmword_1401A2CA0+1, r14b
0x140055cf7  jz      loc_140055F91
0x140055cfd  lea     edx, [r14+1Eh]
0x140055d01  mov     ecx, esi
0x140055d03  lea     r8, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids
0x140055d0a  call    WPP_SF_
0x140055d0f  jmp     loc_140055F91
0x140055d14  lea     r12, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids
0x140055d1b  mov     esi, 408h
0x140055d20  test    r14b, r14b
0x140055d23  jnz     loc_140055E0A
0x140055d29  test    edi, edi
0x140055d2b  jnz     loc_140055E0A
0x140055d31  mov     rdi, [rbx+58h]
0x140055d35  mov     [rbx+58h], r15
0x140055d39  mov     eax, [rdi+80h]
0x140055d3f  cmp     [rdi+84h], eax
0x140055d45  jnz     short loc_140055DC6
0x140055d47  test    byte ptr cs:xmmword_1401A2CA0+1, r8b
0x140055d4e  jz      short loc_140055D68
0x140055d50  mov     edx, 20h ; ' '
0x140055d55  mov     ecx, esi
0x140055d57  mov     r9, rdi
0x140055d5a  mov     r8, r12
0x140055d5d  call    WPP_SF_q
0x140055d62  mov     r8d, 1
0x140055d68  dec     dword ptr [rbx+38h]
0x140055d6b  lea     rcx, [rdi+18h]
0x140055d6f  mov     rax, [rdi+0C8h]
0x140055d76  sub     [rbx+40h], rax
0x140055d7a  test    byte ptr [rdi+60h], 8
0x140055d7e  jz      short loc_140055DA1
0x140055d80  lea     rax, [rbx+48h]
0x140055d84  mov     rdx, [rax+8]
0x140055d88  cmp     [rdx], rax
0x140055d8b  jnz     loc_14005628D
0x140055d91  mov     [rcx], rax
0x140055d94  mov     [rcx+8], rdx
0x140055d98  mov     [rdx], rcx
0x140055d9b  mov     [rax+8], rcx
0x140055d9f  jmp     short loc_140055E0A
0x140055da1  mov     rax, [rbp+var_18]
0x140055da5  lea     rdx, [rbp+var_20]
0x140055da9  cmp     [rax], rdx
0x140055dac  jnz     loc_14005628D
0x140055db2  mov     [rcx+8], rax
0x140055db6  lea     rdx, [rbp+var_20]
0x140055dba  mov     [rcx], rdx
0x140055dbd  mov     [rax], rcx
0x140055dc0  mov     [rbp+var_18], rcx
0x140055dc4  jmp     short loc_140055E0A
0x140055dc6  test    byte ptr cs:xmmword_1401A2CA0+1, r8b
0x140055dcd  jz      short loc_140055DE7
0x140055dcf  mov     edx, 21h ; '!'
0x140055dd4  mov     ecx, esi
0x140055dd6  mov     r9, rdi
0x140055dd9  mov     r8, r12
0x140055ddc  call    WPP_SF_q
0x140055de1  mov     r8d, 1
0x140055de7  lea     rcx, [rbx+28h]
0x140055deb  mov     rdx, [rcx]
0x140055dee  cmp     [rdx+8], rcx
0x140055df2  jnz     loc_14005628D
0x140055df8  lea     rax, [rdi+18h]
0x140055dfc  mov     [rax], rdx
0x140055dff  mov     [rax+8], rcx
0x140055e03  mov     [rdx+8], rax
0x140055e07  mov     [rcx], rax
0x140055e0a  mov     r14d, 10000h
0x140055e10  cmp     [rbx+20h], r8d
0x140055e14  jbe     loc_140055EC7
0x140055e1a  mov     rax, [rbx+8]
0x140055e1e  mov     rcx, [rax+448h]
0x140055e25  cmp     dword ptr [rcx+1120h], 0FFFFFFFFh
0x140055e2c  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x140055e33  jnz     short loc_140055E95
0x140055e35  mov     edi, [rbx+10h]
0x140055e38  call    cs:__imp_KeReadStateEvent
0x140055e3f  nop     dword ptr [rax+rax+00h]
0x140055e44  test    eax, eax
0x140055e46  jnz     short loc_140055E53
0x140055e48  cmp     edi, r14d
0x140055e4b  mov     edx, r14d
0x140055e4e  cmovb   edx, edi
0x140055e51  jmp     short loc_140055E56
0x140055e53  lea     edx, [rdi+rdi]
0x140055e56  mov     rax, [rbx+8]
0x140055e5a  mov     rcx, [rax+448h]
0x140055e61  mov     eax, [rcx+1124h]
0x140055e67  cmp     eax, edx
0x140055e69  jbe     short loc_140055EBB
0x140055e6b  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x140055e72  mov     edi, [rbx+10h]
0x140055e75  call    cs:__imp_KeReadStateEvent
0x140055e7c  nop     dword ptr [rax+rax+00h]
0x140055e81  test    eax, eax
0x140055e83  jnz     short loc_140055E90
0x140055e85  cmp     edi, r14d
0x140055e88  mov     eax, r14d
0x140055e8b  cmovb   eax, edi
0x140055e8e  jmp     short loc_140055EBB
0x140055e90  lea     eax, [rdi+rdi]
0x140055e93  jmp     short loc_140055EBB
0x140055e95  call    cs:__imp_KeReadStateEvent
0x140055e9c  nop     dword ptr [rax+rax+00h]
0x140055ea1  test    eax, eax
0x140055ea3  jnz     short loc_140055EAA
0x140055ea5  mov     eax, r14d
0x140055ea8  jmp     short loc_140055EBB
0x140055eaa  mov     rax, [rbx+8]
0x140055eae  mov     rcx, [rax+448h]
0x140055eb5  mov     eax, [rcx+1120h]
0x140055ebb  cmp     [rbx+18h], rax
0x140055ebf  jnb     short loc_140055F2E
0x140055ec1  mov     r8d, 1
0x140055ec7  test    byte ptr cs:xmmword_1401A2CA0+1, r8b
0x140055ece  jz      short loc_140055EDF
0x140055ed0  mov     edx, 22h ; '"'
0x140055ed5  mov     ecx, esi
0x140055ed7  mov     r8, r12
0x140055eda  call    WPP_SF_
0x140055edf  lea     rcx, [rbx+48h]
0x140055ee3  mov     rax, [rcx]
0x140055ee6  cmp     rax, rcx
0x140055ee9  jz      short loc_140055F2E
0x140055eeb  cmp     [rax+8], rcx
0x140055eef  jnz     loc_14005628D
0x140055ef5  mov     rdx, [rax]
0x140055ef8  cmp     [rdx+8], rax
0x140055efc  jnz     loc_14005628D
0x140055f02  mov     [rcx], rdx
0x140055f05  lea     r8, [rbp+var_20]
0x140055f09  mov     [rdx+8], rcx
0x140055f0d  mov     rdx, [rbp+var_18]
0x140055f11  cmp     [rdx], r8
0x140055f14  jnz     loc_14005628D
0x140055f1a  mov     [rax+8], rdx
0x140055f1e  lea     r8, [rbp+var_20]
0x140055f22  mov     [rax], r8
0x140055f25  mov     [rdx], rax
0x140055f28  mov     [rbp+var_18], rax
0x140055f2c  jmp     short loc_140055EE3
0x140055f2e  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x140055f35  xor     r12b, r12b
0x140055f38  mov     edi, [rbx+10h]
0x140055f3b  call    cs:__imp_KeReadStateEvent
0x140055f42  nop     dword ptr [rax+rax+00h]
0x140055f47  xor     r8d, r8d
0x140055f4a  test    eax, eax
0x140055f4c  jnz     short loc_140055F57
0x140055f4e  cmp     edi, r14d
0x140055f51  cmovb   r14d, edi
0x140055f55  jmp     short loc_140055F5B
0x140055f57  lea     r14d, [rdi+rdi]
0x140055f5b  mov     eax, r14d
0x140055f5e  cmp     [rbx+18h], rax
0x140055f62  jb      short loc_140055F6E
0x140055f64  cmp     dword ptr [rbx+20h], 2
0x140055f68  jnb     loc_14005620B
0x140055f6e  cmp     [rbx+58h], r8
0x140055f72  jnz     loc_14005620B
0x140055f78  lea     rcx, [rbx+28h]
0x140055f7c  mov     rdi, [rcx]
0x140055f7f  cmp     rdi, rcx
0x140055f82  jnz     loc_140056089
0x140055f88  mov     r14d, 1
0x140055f8e  xor     r12d, r12d
0x140055f91  cmp     byte ptr [rbp+arg_8], r12b
0x140055f95  jz      short loc_140055F9B
0x140055f97  mov     [rbx+60h], r12
0x140055f9b  mov     dl, r13b; NewIrql
0x140055f9e  mov     rcx, rbx; SpinLock
0x140055fa1  call    cs:__imp_KeReleaseSpinLock
0x140055fa8  nop     dword ptr [rax+rax+00h]
0x140055fad  or      r13d, 0FFFFFFFFh
0x140055fb1  mov     rax, [rbp+var_20]
0x140055fb5  lea     rcx, [rbp+var_20]
0x140055fb9  cmp     rax, rcx
0x140055fbc  jz      loc_140056294
0x140055fc2  lea     rcx, [rbp+var_20]
0x140055fc6  cmp     [rax+8], rcx
0x140055fca  jnz     loc_14005628D
0x140055fd0  mov     rcx, [rax]
0x140055fd3  cmp     [rcx+8], rax
0x140055fd7  jnz     loc_14005628D
0x140055fdd  mov     [rbp+var_20], rcx
0x140055fe1  lea     rdx, [rbp+var_20]
0x140055fe5  mov     [rcx+8], rdx
0x140055fe9  lea     rdx, [rax-4]; BugCheckParameter2
0x140055fed  mov     [rax+8], rax
0x140055ff1  or      ecx, 0FFFFFFFFh
0x140055ff4  mov     [rax], rax
0x140055ff7  lock xadd [rdx], ecx
0x140055ffb  dec     ecx
0x140055ffd  cmp     cs:UxDebugCheckRefcount, r12b
0x140056004  jz      short loc_14005600F
0x140056006  cmp     ecx, 0FFFFFFFFh
0x140056009  jle     loc_140056263
0x14005600f  test    ecx, ecx
0x140056011  jnz     short loc_140055FB1
0x140056013  lea     rdi, [rax+108h]
0x14005601a  xorps   xmm0, xmm0
0x14005601d  movups  [rbp+var_10], xmm0
0x140056021  cmp     [rdi], r12
0x140056024  jnz     loc_140056274
0x14005602a  cmp     [rax+118h], r12
0x140056031  jnz     loc_140056274
0x140056037  cmp     [rax+128h], r12
0x14005603e  jnz     loc_140056274
0x140056044  mov     rax, [rax+10h]
0x140056048  mov     rdx, [rax+8]
0x14005604c  mov     rsi, [rdx+440h]
0x140056053  call    cs:__imp_KeGetCurrentIrql
0x14005605a  nop     dword ptr [rax+rax+00h]
0x14005605f  test    al, al
0x140056061  jnz     loc_140056240
0x140056067  lea     rdx, [rbp+var_10]
0x14005606b  mov     rcx, rsi
0x14005606e  call    UxPodAttachThread
0x140056073  mov     rcx, rdi
0x140056076  call    UxpTpFreeTransmitPacketWorker
0x14005607b  lea     rcx, [rbp+var_10]
0x14005607f  call    UxPodDetachThread
0x140056084  jmp     loc_140055FB1
0x140056089  movzx   eax, word ptr [rdi+48h]
0x14005608d  test    ax, ax
0x140056090  jns     short loc_14005609F
0x140056092  mov     rax, [rdi+78h]
0x140056096  mov     rdx, [rax+98h]
0x14005609d  jmp     short loc_1400560B3
0x14005609f  bt      ax, 0Eh
0x1400560a4  jnb     short loc_1400560B0
0x1400560a6  mov     rax, [rdi+78h]
0x1400560aa  mov     rdx, [rax+10h]
0x1400560ae  jmp     short loc_1400560B3
0x1400560b0  mov     rdx, r8
0x1400560b3  cmp     [rbx+60h], rdx
0x1400560b7  jz      short loc_1400560C3
0x1400560b9  cmp     [rbx+20h], r8d
0x1400560bd  jnz     loc_140055F88
0x1400560c3  cmp     [rdi+8], rcx
0x1400560c7  jnz     loc_14005628D
  ... truncated ...
```
