# UlpCreateHttpRequest

- ea: `0x14002b040`
- end: `0x14002b8c7`
- name: `UlpCreateHttpRequest`
- size: `2183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f480`
- `0x14002c4d0`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x14002b040`
- `0x14002b8d0`
- `0x14002bd60`
- `0x14002c230`
- `0x140035a50`
- `0x140049d08`
- `0x1400513f0`
- `0x14005dfd0`
- `0x140062bd0`
- `0x140064ff0`
- `0x14006e4ec`
- `0x1400b1acc`
- `0x1400b2244`
- `0x1400e2ca0`
- `0x1400e79a0`
- `0x1400e7a14`
- `0x140167810`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c3f58`
- `0x1401cc484`
- `0x1401cc54c`
- `0x1401d9c5c`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!EtwProviderEnabled` at `0x14002b398`
- `ntoskrnl!EtwProviderEnabled` at `0x14002b398`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b62c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b62c`
- `ntoskrnl!ExUuidCreate` at `0x14002b40d`
- `ntoskrnl!ExUuidCreate` at `0x14002b40d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002b0c1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14002b0c1`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002b27b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002b66d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002b27b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14002b66d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002b551`
- `ntoskrnl!IoGetCurrentProcess` at `0x14002b551`

## pseudocode

```c
__int64 __fastcall UlpCreateHttpRequest(__int64 a1, _QWORD *a2)
{
  __int64 v2; // r14
  unsigned int LockArray_high; // ebp
  unsigned __int64 v6; // rbx
  unsigned int *v7; // rax
  unsigned int *v8; // rbx
  _QWORD *v9; // rax
  USHORT v10; // di
  int v11; // eax
  __int64 v12; // rbp
  NTSTATUS ConnectionRequestId; // edi
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int *v16; // rbp
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  int v20; // edx
  int v21; // ecx
  int v22; // r8d
  int v24; // eax
  bool v25; // zf
  int v26; // ebp
  __int64 *v27; // rbx
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v29; // r9
  __int64 v30; // rsi
  __int64 v31; // rcx
  __int64 v32; // rbx
  USHORT CurrentNodeNumber; // ax
  int v34; // eax
  __int128 v35; // xmm1
  __int128 v36; // xmm1
  __int128 v37; // xmm1
  UCHAR v38; // al
  __int64 v39; // r9
  __int64 v40; // [rsp+28h] [rbp-E0h]
  __int128 v41; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v42[6]; // [rsp+60h] [rbp-A8h] BYREF

  v2 = *(_QWORD *)(a1 + 1096);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qqP(1032, 34, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a1, *(_QWORD *)(a1 + 48), a2);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  if ( UxDebugDisableLookaside )
  {
    v7 = (unsigned int *)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))off_1401A0180)(
                           (unsigned int)dword_1401A0168,
                           qword_1401A0170,
                           (unsigned int)dword_1401A0178,
                           0);
  }
  else if ( UxCompactMode )
  {
    v32 = qword_1401A0160;
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    v7 = (unsigned int *)PplAllocateFromLookasideListProcessor(v32, CurrentNodeNumber);
  }
  else
  {
    v6 = qword_1401A0160 + ((unsigned __int64)(LockArray_high + 1) << 7);
    if ( !*(_BYTE *)(v6 + 176) )
      PplpLazyInitializeLookasideList(qword_1401A0160, v6 + 64);
    v7 = (unsigned int *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v6 + 64));
  }
  v8 = v7;
  if ( !v7 )
  {
    ConnectionRequestId = -1073741670;
    goto LABEL_44;
  }
  v7[4] = 1380478037;
  v9 = v7 + 130;
  *(v9 - 62) = 0;
  *((_DWORD *)v9 - 118) = 1;
  *(v9 - 61) = 0;
  *(v9 - 60) = 0;
  *((_DWORD *)v9 - 6) = 1;
  *((_DWORD *)v9 - 5) = 1;
  v9[1] = v9;
  *v9 = v9;
  *((_QWORD *)v8 + 64) = v8 + 126;
  *((_QWORD *)v8 + 63) = v8 + 126;
  *((_QWORD *)v8 + 156) = 0;
  *((_QWORD *)v8 + 158) = 0;
  *((_QWORD *)v8 + 160) = 0;
  *((_BYTE *)v8 + 104) = 0;
  *((_WORD *)v8 + 990) = 0;
  *((_QWORD *)v8 + 8) = 0;
  *((_QWORD *)v8 + 7) = 0;
  *(_OWORD *)(v8 + 18) = 0;
  *(_OWORD *)(v8 + 22) = 0;
  *((_QWORD *)v8 + 201) = v8 + 404;
  v8[411] = g_UlInternalRequestSize;
  *((_BYTE *)v8 + 544) = 41;
  v8[400] = 1;
  v8[406] = 0;
  *((_QWORD *)v8 + 204) = 0;
  v8[410] = 0;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_qD(1028, 10, WPP_f288c895c7c1312411851f8225fde794_Traceguids, v8 + 324, 1);
  memset(v8 + 324, 0, 0x130u);
  v8[324] = 1229155413;
  v8[329] = 1;
  *((_BYTE *)v8 + 1593) = 1;
  if ( (xmmword_1401A2CA0 & 0x10) != 0 )
    WPP_SF_(1028, 11, WPP_f288c895c7c1312411851f8225fde794_Traceguids);
  memset(v8 + 412, 0, 0x640u);
  *((_QWORD *)v8 + 309) = v8 + 616;
  *((_QWORD *)v8 + 308) = v8 + 616;
  *((_QWORD *)v8 + 350) = v8 + 698;
  *((_QWORD *)v8 + 349) = v8 + 698;
  *((_QWORD *)v8 + 67) = v8 + 812;
  *((_QWORD *)v8 + 351) = 0;
  *((_QWORD *)v8 + 317) = 0;
  v8[492] = 0;
  v8[688] = 3;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 16, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  if ( (unsigned __int16)UlNumberOfLanes <= 1u )
    v10 = 0;
  else
    v10 = KeGetCurrentNodeNumber();
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 17, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, v10);
  *((_WORD *)v8 + 924) = v10;
  *((_QWORD *)v8 + 213) = 0;
  *((_QWORD *)v8 + 391) = 0;
  v8[784] = 0;
  *((_QWORD *)v8 + 393) = 0;
  *((_QWORD *)v8 + 395) = 1448704085;
  *((_QWORD *)v8 + 394) = 258;
  v8[785] = 19;
  *((_QWORD *)v8 + 396) = 0;
  *((_QWORD *)v8 + 397) = 0;
  *((_QWORD *)v8 + 398) = 0;
  *((_QWORD *)v8 + 399) = 0;
  *((_WORD *)v8 + 1606) = 0;
  *((_BYTE *)v8 + 3214) = 0;
  v8[802] = 0;
  *((_QWORD *)v8 + 389) = 0;
  *((_BYTE *)v8 + 3120) = 0;
  *((_QWORD *)v8 + 400) = 0;
  *v8 = LockArray_high;
  v11 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
  if ( UxDebugCheckRefcount && v11 <= -1 )
    UlBugCheckEx(3u, a1 + 40, 0x11u, v11);
  *((_QWORD *)v8 + 3) = a1;
  *((_QWORD *)v8 + 4) = *(_QWORD *)(a1 + 48);
  v8[550] ^= ((unsigned __int8)v8[550] ^ *(_BYTE *)(a1 + 465)) & 1;
  *((_BYTE *)v8 + 3121) = (*(_BYTE *)(*(_QWORD *)(a1 + 1096) + 1765LL) & 0x40) != 0;
  if ( *(_BYTE *)(v2 + 79) && Microsoft_Windows_Networking_CorrelationEnabled
    || EtwProviderEnabled(*(_QWORD *)(v2 + 1688), 0, 0) )
  {
    v12 = *(_QWORD *)(a1 + 48);
    ConnectionRequestId = UlAllocateConnectionRequestId(v8);
    if ( ConnectionRequestId < 0 )
      goto LABEL_47;
    if ( !v12 )
    {
      v14 = *((_QWORD *)v8 + 3);
      if ( v14 )
      {
        v15 = *(_QWORD *)(v14 + 1096);
        if ( (*(_BYTE *)(v15 + 1761) & 2) != 0
          && (!*(_QWORD *)(v15 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v8, v14, 0)) )
        {
          McTemplateK0xxp_EtwWriteTransfer(
            *(_QWORD *)(*((_QWORD *)v8 + 3) + 1096LL) + 1688,
            v14,
            a1 + 440,
            *((_QWORD *)v8 + 8),
            *(_QWORD *)(a1 + 48),
            a1);
        }
      }
    }
    if ( (*(_BYTE *)(v2 + 1760) & 1) != 0 )
    {
      v16 = v8 + 18;
      if ( (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(v8, a1, 0) )
      {
        v34 = *(_DWORD *)(v2 + 1760);
        v35 = *(_OWORD *)(v2 + 1688);
        *(_QWORD *)&v42[0] = *(_QWORD *)(v2 + 1672);
        v42[1] = v35;
        *((_QWORD *)&v42[0] + 1) = v8 + 18;
        v36 = *(_OWORD *)(v2 + 1720);
        v42[2] = *(_OWORD *)(v2 + 1704);
        v42[3] = v36;
        v37 = *(_OWORD *)(v2 + 1752);
        v42[4] = *(_OWORD *)(v2 + 1736);
        v42[5] = v37;
        if ( (v34 & 1) != 0 )
        {
          v38 = SOCKADDR_SIZE(*(_WORD *)(a1 + 412));
          McTemplateK0xxqbr2_EtwWriteTransfer(
            (unsigned int)&v42[1],
            v38,
            a1 + 440,
            *((_QWORD *)v8 + 8),
            *(_QWORD *)(a1 + 48),
            v38,
            v39);
        }
      }
    }
    else
    {
      v16 = v8 + 18;
    }
    if ( *(_BYTE *)(v2 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
      UlEtwStartActivity(v16, 5);
  }
  else
  {
    LODWORD(v16) = (_DWORD)v8 + 72;
  }
  ConnectionRequestId = ExUuidCreate((UUID *)(v8 + 22));
  if ( ConnectionRequestId >= 0 )
  {
    if ( (BYTE9(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF__guid_qi(v18, v17, v19, v8 + 22, v8, *((_QWORD *)v8 + 8));
    if ( (*(_BYTE *)(v2 + 1760) & 2) != 0 )
      McTemplateK0xj_EtwWriteTransfer(v2 + 1688, v17, (_DWORD)v16, *((_QWORD *)v8 + 8), (__int64)(v8 + 22));
    v8[529] = *(_DWORD *)(a1 + 468);
    *((_QWORD *)v8 + 5) = *((_QWORD *)v8 + 4);
    if ( *(_BYTE *)(a1 + 466) )
    {
      *((_QWORD *)v8 + 5) = *(_QWORD *)(a1 + 472);
      *((_BYTE *)v8 + 3214) = 1;
    }
    ConnectionRequestId = UlpInitializeRequestSizingInfo(v8);
    if ( ConnectionRequestId >= 0 )
    {
      ConnectionRequestId = UlpInitializeRequestTimings(v8);
      if ( ConnectionRequestId >= 0 )
      {
        if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
          WPP_SF_qidiq_SOCKADDR_(
            v21,
            v20,
            v22,
            (_DWORD)v8,
            *((_QWORD *)v8 + 8),
            v8[12],
            *(_QWORD *)(a1 + 48),
            a1,
            a1 + 412);
        *a2 = v8;
        ConnectionRequestId = 0;
        goto LABEL_44;
      }
    }
  }
LABEL_47:
  v24 = _InterlockedDecrement((volatile signed __int32 *)v8 + 12);
  if ( UxDebugCheckRefcount && v24 <= -1 )
    UlBugCheckEx(3u, (ULONG_PTR)(v8 + 12), 1u, v24);
  v25 = UxDebugDisableLookaside == 0;
  v8[4] = 1380469877;
  if ( v25 )
  {
    if ( UxCompactMode )
      PnlFreeToLookasideList(qword_1401A0160, v8);
    else
      PplFreeToLookasideListProcessor(qword_1401A0160, v8, *v8);
  }
  else
  {
    memset(v42, 0, sizeof(v42));
    DWORD2(v42[2]) = dword_1401A0178;
    ((void (__fastcall *)(unsigned int *, _OWORD *))off_1401A0188)(v8, v42);
  }
  v26 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 40));
  if ( UxDebugCheckRefcount && v26 <= -1 )
    UlBugCheckEx(3u, a1 + 40, 0x11u, v26);
  if ( !v26 )
  {
    v27 = (__int64 *)(a1 + 64);
    CurrentProcess = IoGetCurrentProcess();
    v30 = *(_QWORD *)(a1 + 1088);
    v31 = *v27;
    if ( UxSystemProcess == CurrentProcess )
    {
      v41 = 0;
      if ( v31 || v27[2] || v27[4] )
        UlBugCheckEx(1u, (ULONG_PTR)v27, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
      if ( !KeGetCurrentIrql() )
      {
        UxPodAttachThread(v30, &v41);
        UlFreeHttpConnection(v27);
        UxPodDetachThread(&v41);
        goto LABEL_44;
      }
    }
    else if ( v31 || v27[2] || v27[4] )
    {
      UlBugCheckEx(1u, (ULONG_PTR)v27, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
    }
    LODWORD(v40) = -1;
    LOBYTE(v29) = 1;
    UlThreadPoolEnqueueWorkItem(0, v27, UlFreeHttpConnection, v29, v30, v40);
  }
LABEL_44:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qD(1032, 37, WPP_682cf469470432b235cb9a4961616e40_Traceguids, *a2, ConnectionRequestId);
  return (unsigned int)ConnectionRequestId;
}

```

## disassembly

```asm
0x14002b040  push    rbx
0x14002b042  push    rbp
0x14002b043  push    rsi
0x14002b044  push    r12
0x14002b046  push    r14
0x14002b048  sub     rsp, 0E0h
0x14002b04f  mov     rax, cs:__security_cookie
0x14002b056  xor     rax, rsp
0x14002b059  mov     [rsp+108h+var_48], rax
0x14002b061  mov     r14, [rcx+448h]
0x14002b068  mov     r12, rdx
0x14002b06b  mov     rsi, rcx
0x14002b06e  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14002b075  jnz     loc_14002B72F
0x14002b07b  mov     ebp, gs:1A4h
0x14002b083  cmp     cs:UxDebugDisableLookaside, 0
0x14002b08a  jnz     loc_14002B5C8
0x14002b090  cmp     cs:UxCompactMode, 0
0x14002b097  jnz     loc_14002B666
0x14002b09d  mov     rcx, cs:qword_1401A0160
0x14002b0a4  lea     ebx, [rbp+1]
0x14002b0a7  shl     rbx, 7
0x14002b0ab  add     rbx, rcx
0x14002b0ae  movzx   eax, byte ptr [rbx+0B0h]
0x14002b0b5  test    al, al
0x14002b0b7  jz      loc_14002B689
0x14002b0bd  lea     rcx, [rbx+40h]; Lookaside
0x14002b0c1  call    cs:__imp_ExAllocateFromLookasideListEx
0x14002b0c8  nop     dword ptr [rax+rax+00h]
0x14002b0cd  mov     [rsp+108h+arg_10], rdi
0x14002b0d5  mov     rbx, rax
0x14002b0d8  mov     [rsp+108h+var_30], r13
0x14002b0e0  mov     [rsp+108h+var_38], r15
0x14002b0e8  test    rax, rax
0x14002b0eb  jz      loc_14002B75B
0x14002b0f1  mov     dword ptr [rax+10h], 52486C55h
0x14002b0f8  lea     rax, [rax+208h]
0x14002b0ff  xor     r15d, r15d
0x14002b102  lea     r13, [rbx+58h]
0x14002b106  mov     [rax-1F0h], r15
0x14002b10d  mov     r8d, 1
0x14002b113  mov     [rax-1D8h], r8d
0x14002b11a  xorps   xmm0, xmm0
0x14002b11d  mov     [rax-1E8h], r15
0x14002b124  xorps   xmm1, xmm1
0x14002b127  mov     [rax-1E0h], r15
0x14002b12e  mov     [rax-18h], r8d
0x14002b132  mov     [rax-14h], r8d
0x14002b136  mov     [rax+8], rax
0x14002b13a  mov     [rax], rax
0x14002b13d  lea     rax, [rbx+1F8h]
0x14002b144  mov     [rax+8], rax
0x14002b148  mov     [rax], rax
0x14002b14b  lea     rax, [rbx+650h]
0x14002b152  mov     [rbx+4E0h], r15
0x14002b159  mov     [rbx+4F0h], r15
0x14002b160  mov     [rbx+500h], r15
0x14002b167  mov     [rbx+68h], r15b
0x14002b16b  mov     [rbx+7BCh], r15w
0x14002b173  mov     [rbx+40h], r15
0x14002b177  mov     [rbx+38h], r15
0x14002b17b  movups  xmmword ptr [rbx+48h], xmm0
0x14002b17f  movups  xmmword ptr [r13+0], xmm1
0x14002b184  mov     [rbx+648h], rax
0x14002b18b  mov     eax, cs:g_UlInternalRequestSize
0x14002b191  mov     [rbx+66Ch], eax
0x14002b197  mov     byte ptr [rbx+220h], 29h ; ')'
0x14002b19e  mov     [rbx+640h], r8d
0x14002b1a5  mov     [rbx+658h], r15d
0x14002b1ac  mov     [rbx+660h], r15
0x14002b1b3  mov     [rbx+668h], r15d
0x14002b1ba  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x14002b1c1  jnz     loc_14002B765
0x14002b1c7  xor     edx, edx; Val
0x14002b1c9  lea     rcx, [rbx+510h]; void *
0x14002b1d0  mov     r8d, 130h; Size
0x14002b1d6  call    memset
0x14002b1db  mov     dword ptr [rbx+510h], 49436C55h
0x14002b1e5  mov     dword ptr [rbx+524h], 1
0x14002b1ef  mov     byte ptr [rbx+639h], 1
0x14002b1f6  test    byte ptr cs:xmmword_1401A2CA0, 10h
0x14002b1fd  jnz     loc_14002B697
0x14002b203  lea     rcx, [rbx+670h]; void *
0x14002b20a  xor     edx, edx; Val
0x14002b20c  mov     r8d, 640h; Size
0x14002b212  call    memset
0x14002b217  lea     rax, [rbx+9A0h]
0x14002b21e  mov     [rax+8], rax
0x14002b222  mov     [rax], rax
0x14002b225  lea     rax, [rbx+0AE8h]
0x14002b22c  mov     [rax+8], rax
0x14002b230  mov     [rax], rax
0x14002b233  lea     rax, [rbx+0CB0h]
0x14002b23a  mov     [rbx+218h], rax
0x14002b241  mov     [rbx+0AF8h], r15
0x14002b248  mov     [rbx+9E8h], r15
0x14002b24f  mov     [rbx+7B0h], r15d
0x14002b256  mov     dword ptr [rbx+0AC0h], 3
0x14002b260  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14002b267  jnz     loc_14002B78C
0x14002b26d  cmp     cs:UlNumberOfLanes, 1
0x14002b275  jbe     loc_14002B5F0
0x14002b27b  call    cs:__imp_KeGetCurrentNodeNumber
0x14002b282  nop     dword ptr [rax+rax+00h]
0x14002b287  movzx   edi, ax
0x14002b28a  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14002b291  jnz     loc_14002B7A7
0x14002b297  mov     [rbx+738h], di
0x14002b29e  mov     eax, 1
0x14002b2a3  mov     [rbx+6A8h], r15
0x14002b2aa  mov     [rbx+0C38h], r15
0x14002b2b1  mov     [rbx+0C40h], r15d
0x14002b2b8  mov     [rbx+0C48h], r15
0x14002b2bf  mov     qword ptr [rbx+0C58h], 56597855h
0x14002b2ca  mov     qword ptr [rbx+0C50h], 102h
0x14002b2d5  mov     dword ptr [rbx+0C44h], 13h
0x14002b2df  mov     [rbx+0C60h], r15
0x14002b2e6  mov     [rbx+0C68h], r15
0x14002b2ed  mov     [rbx+0C70h], r15
0x14002b2f4  mov     [rbx+0C78h], r15
0x14002b2fb  mov     [rbx+0C8Ch], r15w
0x14002b303  mov     [rbx+0C8Eh], r15b
0x14002b30a  mov     [rbx+0C88h], r15d
0x14002b311  mov     [rbx+0C28h], r15
0x14002b318  mov     [rbx+0C30h], r15b
0x14002b31f  mov     [rbx+0C80h], r15
0x14002b326  mov     [rbx], ebp
0x14002b328  lock xadd [rsi+28h], eax
0x14002b32d  inc     eax
0x14002b32f  cmp     cs:UxDebugCheckRefcount, r15b
0x14002b336  jnz     loc_14002B59E
0x14002b33c  mov     [rbx+18h], rsi
0x14002b340  mov     rax, [rsi+30h]
0x14002b344  mov     [rbx+20h], rax
0x14002b348  mov     eax, [rbx+898h]
0x14002b34e  movzx   ecx, byte ptr [rsi+1D1h]
0x14002b355  xor     ecx, eax
0x14002b357  and     ecx, 1
0x14002b35a  xor     ecx, eax
0x14002b35c  mov     [rbx+898h], ecx
0x14002b362  mov     rax, [rsi+448h]
0x14002b369  movzx   ecx, byte ptr [rax+6E5h]
0x14002b370  shr     cl, 6
0x14002b373  and     cl, 1
0x14002b376  mov     [rbx+0C31h], cl
0x14002b37c  cmp     [r14+4Fh], r15b
0x14002b380  jz      short loc_14002B38C
0x14002b382  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14002b388  test    eax, eax
0x14002b38a  jnz     short loc_14002B3AC
0x14002b38c  mov     rcx, [r14+698h]; RegHandle
0x14002b393  xor     r8d, r8d; Keyword
0x14002b396  xor     edx, edx; Level
0x14002b398  call    cs:__imp_EtwProviderEnabled
0x14002b39f  nop     dword ptr [rax+rax+00h]
0x14002b3a4  test    al, al
0x14002b3a6  jz      loc_14002B5BF
0x14002b3ac  mov     rbp, [rsi+30h]
0x14002b3b0  mov     rcx, rbx
0x14002b3b3  call    UlAllocateConnectionRequestId
0x14002b3b8  mov     edi, eax
0x14002b3ba  test    eax, eax
0x14002b3bc  js      loc_14002B4E3
0x14002b3c2  test    rbp, rbp
0x14002b3c5  jnz     short loc_14002B3E4
0x14002b3c7  mov     rdx, [rbx+18h]
0x14002b3cb  test    rdx, rdx
0x14002b3ce  jz      short loc_14002B3E4
0x14002b3d0  mov     rcx, [rdx+448h]
0x14002b3d7  test    byte ptr [rcx+6E1h], 2
0x14002b3de  jnz     loc_14002B7C6
0x14002b3e4  test    byte ptr [r14+6E0h], 1
0x14002b3ec  jnz     loc_140173C02
0x14002b3f2  lea     rbp, [rbx+48h]
0x14002b3f6  cmp     [r14+4Fh], r15b
0x14002b3fa  jz      short loc_14002B40A
0x14002b3fc  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14002b402  test    eax, eax
0x14002b404  jnz     loc_14002B7EB
0x14002b40a  mov     rcx, r13; Uuid
0x14002b40d  call    cs:__imp_ExUuidCreate
0x14002b414  nop     dword ptr [rax+rax+00h]
0x14002b419  mov     edi, eax
0x14002b41b  test    eax, eax
0x14002b41d  js      loc_14002B4E3
0x14002b423  test    byte ptr cs:xmmword_1401A2CA0+9, 1
0x14002b42a  jnz     loc_14002B7FD
0x14002b430  test    byte ptr [r14+6E0h], 2
0x14002b438  jnz     loc_14002B818
0x14002b43e  mov     eax, [rsi+1D4h]
0x14002b444  mov     [rbx+844h], eax
0x14002b44a  mov     rax, [rbx+20h]
0x14002b44e  mov     [rbx+28h], rax
0x14002b452  cmp     [rsi+1D2h], r15b
0x14002b459  jz      short loc_14002B46D
0x14002b45b  mov     rax, [rsi+1D8h]
0x14002b462  mov     [rbx+28h], rax
0x14002b466  mov     byte ptr [rbx+0C8Eh], 1
0x14002b46d  mov     rcx, rbx
0x14002b470  call    UlpInitializeRequestSizingInfo
0x14002b475  mov     edi, eax
0x14002b477  test    eax, eax
0x14002b479  js      short loc_14002B4E3
0x14002b47b  mov     rcx, rbx
0x14002b47e  call    UlpInitializeRequestTimings
0x14002b483  mov     edi, eax
0x14002b485  test    eax, eax
0x14002b487  js      short loc_14002B4E3
0x14002b489  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14002b490  jnz     loc_14002B835
0x14002b496  mov     [r12], rbx
0x14002b49a  xor     edi, edi
0x14002b49c  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14002b4a3  jnz     loc_14002B8A4
0x14002b4a9  mov     r15, [rsp+108h+var_38]
0x14002b4b1  mov     eax, edi
0x14002b4b3  mov     rdi, [rsp+108h+arg_10]
0x14002b4bb  mov     r13, [rsp+108h+var_30]
0x14002b4c3  mov     rcx, [rsp+108h+var_48]
0x14002b4cb  xor     rcx, rsp; StackCookie
0x14002b4ce  call    __security_check_cookie
0x14002b4d3  add     rsp, 0E0h
0x14002b4da  pop     r14
0x14002b4dc  pop     r12
0x14002b4de  pop     rsi
0x14002b4df  pop     rbp
0x14002b4e0  pop     rbx
0x14002b4e1  retn
0x14002b4e3  mov     ebp, 0FFFFFFFFh
0x14002b4e8  lea     rdx, [rbx+30h]; BugCheckParameter2
0x14002b4ec  mov     eax, ebp
0x14002b4ee  lock xadd [rdx], eax
0x14002b4f2  dec     eax
0x14002b4f4  cmp     cs:UxDebugCheckRefcount, r15b
0x14002b4fb  jnz     loc_14002B6B2
0x14002b501  cmp     cs:UxDebugDisableLookaside, r15b
0x14002b508  mov     dword ptr [rbx+10h], 52484C75h
0x14002b50f  jnz     loc_14002B86C
0x14002b515  cmp     cs:UxCompactMode, r15b
0x14002b51c  mov     rdx, rbx
0x14002b51f  mov     rcx, cs:qword_1401A0160
0x14002b526  jz      loc_14002B6CE
0x14002b52c  call    PnlFreeToLookasideList
0x14002b531  lock xadd [rsi+28h], ebp
0x14002b536  dec     ebp
0x14002b538  cmp     cs:UxDebugCheckRefcount, r15b
0x14002b53f  jnz     loc_14002B6DB
0x14002b545  test    ebp, ebp
0x14002b547  jnz     loc_14002B49C
0x14002b54d  lea     rbx, [rsi+40h]
0x14002b551  call    cs:__imp_IoGetCurrentProcess
0x14002b558  nop     dword ptr [rax+rax+00h]
0x14002b55d  cmp     cs:UxSystemProcess, rax
0x14002b564  mov     rsi, [rsi+440h]
0x14002b56b  mov     rcx, [rbx]
0x14002b56e  jz      loc_14002B5F8
0x14002b574  test    rcx, rcx
0x14002b577  jnz     short loc_14002B583
0x14002b579  cmp     [rbx+10h], r15
0x14002b57d  jz      loc_14002B6FC
0x14002b583  mov     r9d, 0DBh; BugCheckParameter4
0x14002b589  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14002b590  mov     rdx, rbx; BugCheckParameter2
0x14002b593  mov     ecx, 1; BugCheckParameter1
0x14002b598  call    UlBugCheckEx
0x14002b59e  cmp     eax, 0FFFFFFFFh
0x14002b5a1  jg      loc_14002B33C
0x14002b5a7  movsxd  r9, eax; BugCheckParameter4
0x14002b5aa  lea     rdx, [rsi+28h]; BugCheckParameter2
0x14002b5ae  mov     r8d, 11h; BugCheckParameter3
0x14002b5b4  mov     ecx, 3; BugCheckParameter1
0x14002b5b9  call    UlBugCheckEx
0x14002b5bf  lea     rbp, [rbx+48h]
0x14002b5c3  jmp     loc_14002B40A
0x14002b5c8  mov     rax, cs:off_1401A0180
0x14002b5cf  xor     r9d, r9d
0x14002b5d2  mov     r8d, cs:dword_1401A0178
0x14002b5d9  mov     rdx, cs:qword_1401A0170
0x14002b5e0  mov     ecx, cs:dword_1401A0168
0x14002b5e6  call    _guard_dispatch_icall
0x14002b5eb  jmp     loc_14002B0CD
0x14002b5f0  mov     edi, r15d
0x14002b5f3  jmp     loc_14002B28A
0x14002b5f8  xorps   xmm0, xmm0
0x14002b5fb  movups  [rsp+108h+var_B8], xmm0
0x14002b600  test    rcx, rcx
0x14002b603  jnz     short loc_14002B60B
0x14002b605  cmp     [rbx+10h], r15
0x14002b609  jz      short loc_14002B626
0x14002b60b  mov     r9d, 0E1h; BugCheckParameter4
0x14002b611  lea     r8, aMinioHttpSysHt_1; "minio\\http\\sys\\httpconn.h"
0x14002b618  mov     rdx, rbx; BugCheckParameter2
0x14002b61b  mov     ecx, 1; BugCheckParameter1
0x14002b620  call    UlBugCheckEx
0x14002b626  cmp     [rbx+20h], r15
0x14002b62a  jnz     short loc_14002B60B
0x14002b62c  call    cs:__imp_KeGetCurrentIrql
0x14002b633  nop     dword ptr [rax+rax+00h]
0x14002b638  test    al, al
0x14002b63a  jz      loc_14002B70B
  ... truncated ...
```
