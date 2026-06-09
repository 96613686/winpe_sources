# UxpTpDequeueTransmitPacket

- ea: `0x140055c08`
- end: `0x140056305`
- name: `UxpTpDequeueTransmitPacket`
- size: `1789`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `5`
- callee_count: `11`
- tags: ``

## callers

- `0x140054b00`
- `0x140054ba4`
- `0x140055440`
- `0x140055880`
- `0x140141400`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140035a50`
- `0x14004a950`
- `0x140052198`
- `0x140055c08`
- `0x140062bd0`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4444`
- `0x1401d6e48`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140056033`
- `ntoskrnl!KeGetCurrentIrql` at `0x140056033`
- `ntoskrnl!KeReadStateEvent` at `0x140055e18`
- `ntoskrnl!KeReadStateEvent` at `0x140055e55`
- `ntoskrnl!KeReadStateEvent` at `0x140055e75`
- `ntoskrnl!KeReadStateEvent` at `0x140055f1b`
- `ntoskrnl!KeReadStateEvent` at `0x140055e18`
- `ntoskrnl!KeReadStateEvent` at `0x140055e55`
- `ntoskrnl!KeReadStateEvent` at `0x140055e75`
- `ntoskrnl!KeReadStateEvent` at `0x140055f1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140055f81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140055f81`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140055c8a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140055c8a`

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
  __int64 v50; // [rsp+28h] [rbp-48h]
  __int64 v51; // [rsp+50h] [rbp-20h] BYREF
  __int64 *v52; // [rsp+58h] [rbp-18h]
  __int128 v53; // [rsp+60h] [rbp-10h] BYREF
  __int64 v54; // [rsp+B0h] [rbp+40h] BYREF
  int v55; // [rsp+B8h] [rbp+48h]

  v5 = a2;
  v51 = (__int64)&v51;
  v6 = a3;
  LOBYTE(v55) = 0;
  v52 = &v51;
  v8 = 0;
  v54 = 0;
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
    LOBYTE(v13) = v55;
    SpinLock[3] -= v5;
    v12 = (*((_DWORD *)SpinLock + 8))-- == 1;
    v13 = (unsigned __int8)v13;
    if ( v12 )
      v13 = 1;
    v55 = v13;
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
        v17 = v52;
        if ( (__int64 *)*v52 != &v51 )
          goto LABEL_110;
        *(_QWORD *)(v14 + 32) = v52;
        *v15 = &v51;
        *v17 = (__int64)v15;
        v52 = (__int64 *)(v14 + 24);
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
      v28 = v52;
      if ( (__int64 *)*v52 != &v51 )
        goto LABEL_110;
      v26[1] = (__int64)v52;
      *v26 = (__int64)&v51;
      *v28 = (__int64)v26;
      v52 = v26;
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
          v44 = UxpTpAllocateChunkTracker(v32 - 3, v20, &v54);
          if ( v44 >= 0 )
          {
            v8 = v54;
            if ( *(_DWORD *)(v54 + 268) )
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
              v55 = v46;
              goto LABEL_101;
            }
LABEL_100:
            LOBYTE(v46) = v55;
LABEL_101:
            if ( v8 )
            {
              v48 = v29 || (_BYTE)v46;
              *(_BYTE *)(v8 + 257) = v48;
            }
            goto LABEL_63;
          }
          *((_DWORD *)v43 + 17) = v44;
          v45 = (__int64 **)v52;
          SpinLock[11] = 0;
          if ( *v45 == &v51 )
          {
            v8 = v54;
            *v32 = (KSPIN_LOCK)&v51;
            v32[1] = (KSPIN_LOCK)v45;
            *v45 = (__int64 *)v32;
            v52 = (__int64 *)v32;
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
  if ( (_BYTE)v55 )
    SpinLock[12] = 0;
  KeReleaseSpinLock(SpinLock, v11);
  while ( 1 )
  {
    result = (volatile signed __int32 *)v51;
    if ( (__int64 *)v51 == &v51 )
      break;
    if ( *(__int64 **)(v51 + 8) != &v51 )
      goto LABEL_110;
    v35 = *(_QWORD *)v51;
    if ( *(_QWORD *)(*(_QWORD *)v51 + 8LL) != v51 )
      goto LABEL_110;
    v51 = *(_QWORD *)v51;
    *(_QWORD *)(v35 + 8) = &v51;
    *((_QWORD *)result + 1) = result;
    *(_QWORD *)result = result;
    v36 = _InterlockedDecrement(result - 1);
    if ( UxDebugCheckRefcount && v36 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)(result - 1), 1u, v36);
    if ( !v36 )
    {
      v37 = result + 66;
      v53 = 0;
      if ( *((_QWORD *)result + 33) || *((_QWORD *)result + 35) || *((_QWORD *)result + 37) )
        UlBugCheckEx(1u, (ULONG_PTR)(result + 66), (ULONG_PTR)"minio\\http\\sys\\tpacket.c", 0x8A4u);
      v38 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)result + 2) + 8LL) + 1088LL);
      if ( KeGetCurrentIrql() )
      {
        LODWORD(v50) = -1;
        LOBYTE(v39) = 1;
        UlThreadPoolEnqueueWorkItem(0, v37, UxpTpFreeTransmitPacketWorker, v39, v38, v50);
      }
      else
      {
        UxPodAttachThread(v38, &v53);
        UxpTpFreeTransmitPacketWorker(v37);
        UxPodDetachThread(&v53);
      }
    }
  }
  if ( v8 )
  {
    v49 = v8 + 208;
    if ( *(_QWORD *)(v8 + 208) || *(_QWORD *)(v8 + 224) || *(_QWORD *)(v8 + 240) )
      UlBugCheckEx(1u, v49, (ULONG_PTR)"minio\\http\\sys\\tpacket.c", 0x8B2u);
    LODWORD(v50) = -1;
    LOBYTE(v33) = 1;
    result = (volatile signed __int32 *)UlThreadPoolEnqueueWorkItem(
                                          0,
                                          v49,
                                          UxpTpProcessMdlRuns,
                                          v33,
                                          *(_QWORD *)(SpinLock[1] + 1088),
                                          v50);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    return (volatile signed __int32 *)WPP_SF_(1032, 37, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140055c08  mov     [rsp-38h+arg_18], rbx
0x140055c0d  push    rbp
0x140055c0e  push    rsi
0x140055c0f  push    rdi
0x140055c10  push    r12
0x140055c12  push    r13
0x140055c14  push    r14
0x140055c16  push    r15
0x140055c18  mov     rbp, rsp
0x140055c1b  sub     rsp, 70h
0x140055c1f  xor     r12d, r12d
0x140055c22  movzx   r14d, r9b
0x140055c26  lea     rax, [rbp+var_20]
0x140055c2a  mov     esi, edx
0x140055c2c  mov     [rbp+var_20], rax
0x140055c30  mov     edi, r8d
0x140055c33  lea     rax, [rbp+var_20]
0x140055c37  mov     byte ptr [rbp+arg_8], r12b
0x140055c3b  mov     [rbp+var_18], rax
0x140055c3f  mov     rbx, rcx
0x140055c42  mov     r15d, r12d
0x140055c45  mov     [rbp+arg_0], r12
0x140055c49  lea     ecx, [r12+1]
0x140055c4e  test    byte ptr cs:xmmword_1401A2CA0+1, cl
0x140055c54  jz      short loc_140055C87
0x140055c56  mov     rcx, [rbx+8]
0x140055c5a  test    rcx, rcx
0x140055c5d  jz      short loc_140055C65
0x140055c5f  mov     rdx, [rcx+30h]
0x140055c63  jmp     short loc_140055C68
0x140055c65  mov     rdx, r12
0x140055c68  mov     [rsp+70h+var_30], r14d
0x140055c6d  mov     r9, rbx
0x140055c70  mov     [rsp+70h+var_38], edi
0x140055c74  mov     [rsp+70h+var_40], esi
0x140055c78  mov     [rsp+70h+var_48], rdx
0x140055c7d  mov     [rsp+70h+var_50], rcx
0x140055c82  call    WPP_SF_qqiDDl
0x140055c87  mov     rcx, rbx; SpinLock
0x140055c8a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140055c91  nop     dword ptr [rax+rax+00h]
0x140055c96  mov     r13b, al
0x140055c99  test    edi, edi
0x140055c9b  jz      short loc_140055CA0
0x140055c9d  mov     [rbx+10h], edi
0x140055ca0  mov     r8d, 1
0x140055ca6  test    esi, esi
0x140055ca8  jz      short loc_140055CBF
0x140055caa  mov     eax, [rbp+arg_8]
0x140055cad  sub     [rbx+18h], rsi
0x140055cb1  add     dword ptr [rbx+20h], 0FFFFFFFFh
0x140055cb5  movzx   eax, al
0x140055cb8  cmovz   eax, r8d
0x140055cbc  mov     [rbp+arg_8], eax
0x140055cbf  cmp     [rbx+68h], r12b
0x140055cc3  jz      short loc_140055CF4
0x140055cc5  mov     r14d, 1
0x140055ccb  mov     esi, 408h
0x140055cd0  test    byte ptr cs:xmmword_1401A2CA0+1, r14b
0x140055cd7  jz      loc_140055F71
0x140055cdd  lea     edx, [r14+1Eh]
0x140055ce1  mov     ecx, esi
0x140055ce3  lea     r8, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids
0x140055cea  call    WPP_SF_
0x140055cef  jmp     loc_140055F71
0x140055cf4  lea     r12, WPP_5029077b3d5d3a1af72887c1c6a12643_Traceguids
0x140055cfb  mov     esi, 408h
0x140055d00  test    r14b, r14b
0x140055d03  jnz     loc_140055DEA
0x140055d09  test    edi, edi
0x140055d0b  jnz     loc_140055DEA
0x140055d11  mov     rdi, [rbx+58h]
0x140055d15  mov     [rbx+58h], r15
0x140055d19  mov     eax, [rdi+80h]
0x140055d1f  cmp     [rdi+84h], eax
0x140055d25  jnz     short loc_140055DA6
0x140055d27  test    byte ptr cs:xmmword_1401A2CA0+1, r8b
0x140055d2e  jz      short loc_140055D48
0x140055d30  mov     edx, 20h ; ' '
0x140055d35  mov     ecx, esi
0x140055d37  mov     r9, rdi
0x140055d3a  mov     r8, r12
0x140055d3d  call    WPP_SF_q
0x140055d42  mov     r8d, 1
0x140055d48  dec     dword ptr [rbx+38h]
0x140055d4b  lea     rcx, [rdi+18h]
0x140055d4f  mov     rax, [rdi+0C8h]
0x140055d56  sub     [rbx+40h], rax
0x140055d5a  test    byte ptr [rdi+60h], 8
0x140055d5e  jz      short loc_140055D81
0x140055d60  lea     rax, [rbx+48h]
0x140055d64  mov     rdx, [rax+8]
0x140055d68  cmp     [rdx], rax
0x140055d6b  jnz     loc_14005626D
0x140055d71  mov     [rcx], rax
0x140055d74  mov     [rcx+8], rdx
0x140055d78  mov     [rdx], rcx
0x140055d7b  mov     [rax+8], rcx
0x140055d7f  jmp     short loc_140055DEA
0x140055d81  mov     rax, [rbp+var_18]
0x140055d85  lea     rdx, [rbp+var_20]
0x140055d89  cmp     [rax], rdx
0x140055d8c  jnz     loc_14005626D
0x140055d92  mov     [rcx+8], rax
0x140055d96  lea     rdx, [rbp+var_20]
0x140055d9a  mov     [rcx], rdx
0x140055d9d  mov     [rax], rcx
0x140055da0  mov     [rbp+var_18], rcx
0x140055da4  jmp     short loc_140055DEA
0x140055da6  test    byte ptr cs:xmmword_1401A2CA0+1, r8b
0x140055dad  jz      short loc_140055DC7
0x140055daf  mov     edx, 21h ; '!'
0x140055db4  mov     ecx, esi
0x140055db6  mov     r9, rdi
0x140055db9  mov     r8, r12
0x140055dbc  call    WPP_SF_q
0x140055dc1  mov     r8d, 1
0x140055dc7  lea     rcx, [rbx+28h]
0x140055dcb  mov     rdx, [rcx]
0x140055dce  cmp     [rdx+8], rcx
0x140055dd2  jnz     loc_14005626D
0x140055dd8  lea     rax, [rdi+18h]
0x140055ddc  mov     [rax], rdx
0x140055ddf  mov     [rax+8], rcx
0x140055de3  mov     [rdx+8], rax
0x140055de7  mov     [rcx], rax
0x140055dea  mov     r14d, 10000h
0x140055df0  cmp     [rbx+20h], r8d
0x140055df4  jbe     loc_140055EA7
0x140055dfa  mov     rax, [rbx+8]
0x140055dfe  mov     rcx, [rax+448h]
0x140055e05  cmp     dword ptr [rcx+1120h], 0FFFFFFFFh
0x140055e0c  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x140055e13  jnz     short loc_140055E75
0x140055e15  mov     edi, [rbx+10h]
0x140055e18  call    cs:__imp_KeReadStateEvent
0x140055e1f  nop     dword ptr [rax+rax+00h]
0x140055e24  test    eax, eax
0x140055e26  jnz     short loc_140055E33
0x140055e28  cmp     edi, r14d
0x140055e2b  mov     edx, r14d
0x140055e2e  cmovb   edx, edi
0x140055e31  jmp     short loc_140055E36
0x140055e33  lea     edx, [rdi+rdi]
0x140055e36  mov     rax, [rbx+8]
0x140055e3a  mov     rcx, [rax+448h]
0x140055e41  mov     eax, [rcx+1124h]
0x140055e47  cmp     eax, edx
0x140055e49  jbe     short loc_140055E9B
0x140055e4b  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x140055e52  mov     edi, [rbx+10h]
0x140055e55  call    cs:__imp_KeReadStateEvent
0x140055e5c  nop     dword ptr [rax+rax+00h]
0x140055e61  test    eax, eax
0x140055e63  jnz     short loc_140055E70
0x140055e65  cmp     edi, r14d
0x140055e68  mov     eax, r14d
0x140055e6b  cmovb   eax, edi
0x140055e6e  jmp     short loc_140055E9B
0x140055e70  lea     eax, [rdi+rdi]
0x140055e73  jmp     short loc_140055E9B
0x140055e75  call    cs:__imp_KeReadStateEvent
0x140055e7c  nop     dword ptr [rax+rax+00h]
0x140055e81  test    eax, eax
0x140055e83  jnz     short loc_140055E8A
0x140055e85  mov     eax, r14d
0x140055e88  jmp     short loc_140055E9B
0x140055e8a  mov     rax, [rbx+8]
0x140055e8e  mov     rcx, [rax+448h]
0x140055e95  mov     eax, [rcx+1120h]
0x140055e9b  cmp     [rbx+18h], rax
0x140055e9f  jnb     short loc_140055F0E
0x140055ea1  mov     r8d, 1
0x140055ea7  test    byte ptr cs:xmmword_1401A2CA0+1, r8b
0x140055eae  jz      short loc_140055EBF
0x140055eb0  mov     edx, 22h ; '"'
0x140055eb5  mov     ecx, esi
0x140055eb7  mov     r8, r12
0x140055eba  call    WPP_SF_
0x140055ebf  lea     rcx, [rbx+48h]
0x140055ec3  mov     rax, [rcx]
0x140055ec6  cmp     rax, rcx
0x140055ec9  jz      short loc_140055F0E
0x140055ecb  cmp     [rax+8], rcx
0x140055ecf  jnz     loc_14005626D
0x140055ed5  mov     rdx, [rax]
0x140055ed8  cmp     [rdx+8], rax
0x140055edc  jnz     loc_14005626D
0x140055ee2  mov     [rcx], rdx
0x140055ee5  lea     r8, [rbp+var_20]
0x140055ee9  mov     [rdx+8], rcx
0x140055eed  mov     rdx, [rbp+var_18]
0x140055ef1  cmp     [rdx], r8
0x140055ef4  jnz     loc_14005626D
0x140055efa  mov     [rax+8], rdx
0x140055efe  lea     r8, [rbp+var_20]
0x140055f02  mov     [rax], r8
0x140055f05  mov     [rdx], rax
0x140055f08  mov     [rbp+var_18], rax
0x140055f0c  jmp     short loc_140055EC3
0x140055f0e  mov     rcx, cs:UxHighNonPagedPoolEvent; Event
0x140055f15  xor     r12b, r12b
0x140055f18  mov     edi, [rbx+10h]
0x140055f1b  call    cs:__imp_KeReadStateEvent
0x140055f22  nop     dword ptr [rax+rax+00h]
0x140055f27  xor     r8d, r8d
0x140055f2a  test    eax, eax
0x140055f2c  jnz     short loc_140055F37
0x140055f2e  cmp     edi, r14d
0x140055f31  cmovb   r14d, edi
0x140055f35  jmp     short loc_140055F3B
0x140055f37  lea     r14d, [rdi+rdi]
0x140055f3b  mov     eax, r14d
0x140055f3e  cmp     [rbx+18h], rax
0x140055f42  jb      short loc_140055F4E
0x140055f44  cmp     dword ptr [rbx+20h], 2
0x140055f48  jnb     loc_1400561EB
0x140055f4e  cmp     [rbx+58h], r8
0x140055f52  jnz     loc_1400561EB
0x140055f58  lea     rcx, [rbx+28h]
0x140055f5c  mov     rdi, [rcx]
0x140055f5f  cmp     rdi, rcx
0x140055f62  jnz     loc_140056069
0x140055f68  mov     r14d, 1
0x140055f6e  xor     r12d, r12d
0x140055f71  cmp     byte ptr [rbp+arg_8], r12b
0x140055f75  jz      short loc_140055F7B
0x140055f77  mov     [rbx+60h], r12
0x140055f7b  mov     dl, r13b; NewIrql
0x140055f7e  mov     rcx, rbx; SpinLock
0x140055f81  call    cs:__imp_KeReleaseSpinLock
0x140055f88  nop     dword ptr [rax+rax+00h]
0x140055f8d  or      r13d, 0FFFFFFFFh
0x140055f91  mov     rax, [rbp+var_20]
0x140055f95  lea     rcx, [rbp+var_20]
0x140055f99  cmp     rax, rcx
0x140055f9c  jz      loc_140056274
0x140055fa2  lea     rcx, [rbp+var_20]
0x140055fa6  cmp     [rax+8], rcx
0x140055faa  jnz     loc_14005626D
0x140055fb0  mov     rcx, [rax]
0x140055fb3  cmp     [rcx+8], rax
0x140055fb7  jnz     loc_14005626D
0x140055fbd  mov     [rbp+var_20], rcx
0x140055fc1  lea     rdx, [rbp+var_20]
0x140055fc5  mov     [rcx+8], rdx
0x140055fc9  lea     rdx, [rax-4]; BugCheckParameter2
0x140055fcd  mov     [rax+8], rax
0x140055fd1  or      ecx, 0FFFFFFFFh
0x140055fd4  mov     [rax], rax
0x140055fd7  lock xadd [rdx], ecx
0x140055fdb  dec     ecx
0x140055fdd  cmp     cs:UxDebugCheckRefcount, r12b
0x140055fe4  jz      short loc_140055FEF
0x140055fe6  cmp     ecx, 0FFFFFFFFh
0x140055fe9  jle     loc_140056243
0x140055fef  test    ecx, ecx
0x140055ff1  jnz     short loc_140055F91
0x140055ff3  lea     rdi, [rax+108h]
0x140055ffa  xorps   xmm0, xmm0
0x140055ffd  movups  [rbp+var_10], xmm0
0x140056001  cmp     [rdi], r12
0x140056004  jnz     loc_140056254
0x14005600a  cmp     [rax+118h], r12
0x140056011  jnz     loc_140056254
0x140056017  cmp     [rax+128h], r12
0x14005601e  jnz     loc_140056254
0x140056024  mov     rax, [rax+10h]
0x140056028  mov     rdx, [rax+8]
0x14005602c  mov     rsi, [rdx+440h]
0x140056033  call    cs:__imp_KeGetCurrentIrql
0x14005603a  nop     dword ptr [rax+rax+00h]
0x14005603f  test    al, al
0x140056041  jnz     loc_140056220
0x140056047  lea     rdx, [rbp+var_10]
0x14005604b  mov     rcx, rsi
0x14005604e  call    UxPodAttachThread
0x140056053  mov     rcx, rdi
0x140056056  call    UxpTpFreeTransmitPacketWorker
0x14005605b  lea     rcx, [rbp+var_10]
0x14005605f  call    UxPodDetachThread
0x140056064  jmp     loc_140055F91
0x140056069  movzx   eax, word ptr [rdi+48h]
0x14005606d  test    ax, ax
0x140056070  jns     short loc_14005607F
0x140056072  mov     rax, [rdi+78h]
0x140056076  mov     rdx, [rax+98h]
0x14005607d  jmp     short loc_140056093
0x14005607f  bt      ax, 0Eh
0x140056084  jnb     short loc_140056090
0x140056086  mov     rax, [rdi+78h]
0x14005608a  mov     rdx, [rax+10h]
0x14005608e  jmp     short loc_140056093
0x140056090  mov     rdx, r8
0x140056093  cmp     [rbx+60h], rdx
0x140056097  jz      short loc_1400560A3
0x140056099  cmp     [rbx+20h], r8d
0x14005609d  jnz     loc_140055F68
0x1400560a3  cmp     [rdi+8], rcx
0x1400560a7  jnz     loc_14005626D
  ... truncated ...
```
