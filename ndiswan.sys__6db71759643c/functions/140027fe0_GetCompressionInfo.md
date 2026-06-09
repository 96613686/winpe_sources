# GetCompressionInfo

- ea: `0x140027fe0`
- end: `0x140028414`
- name: `GetCompressionInfo`
- size: `1076`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140002cc0`
- `0x140005494`
- `0x14000550c`
- `0x1400084d8`
- `0x1400085b0`
- `0x14000a290`
- `0x14000a5f4`
- `0x140027fe0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400283b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400283f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400283b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400283f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400280e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400283cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400280e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400283cf`

## pseudocode

```c
__int64 __fastcall GetCompressionInfo(__int64 *a1, unsigned int a2, __int64 a3, unsigned int a4, _DWORD *a5)
{
  KSPIN_LOCK *v5; // rsi
  char *v7; // rbx
  PDEVICE_OBJECT v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // r15
  _OWORD *v16; // rcx
  __int64 v17; // rdx
  _OWORD *v18; // rax
  __int128 v19; // xmm1
  _OWORD *v20; // rcx
  __int64 v21; // rdx
  _OWORD *v22; // rax
  __int128 v23; // xmm1
  int v24; // eax
  __int64 i; // rcx
  __int64 j; // rcx
  int v27; // eax
  __int64 k; // rcx
  __int64 m; // rcx
  int v30; // ecx
  bool v31; // zf
  KIRQL v32; // al
  PVOID v34; // [rsp+70h] [rbp+40h] BYREF
  PVOID Entry; // [rsp+80h] [rbp+50h] BYREF

  v5 = 0;
  v7 = 0;
  v34 = 0;
  Entry = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  *a5 = 744;
  if ( a2 < 0x2E8 || a4 < 0x2E8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a4, 744);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a2, 744);
      }
    }
    v14 = -1073741820;
  }
  else
  {
    if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
      v12 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
    else
      v12 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline(
              v11,
              &WPP_GLOBAL_Control,
              744);
    v13 = *a1;
    if ( v12 )
    {
      v14 = ValidateLinkAndBundle(v13, 1, &v34, &Entry);
      if ( v14 < 0 )
        goto LABEL_13;
    }
    else
    {
      v14 = 0;
      if ( !(unsigned __int8)AreLinkAndBundleValid(v13, 1, &v34, &Entry) )
      {
        v14 = 601;
LABEL_13:
        v5 = (KSPIN_LOCK *)v34;
        v7 = (char *)Entry;
        goto LABEL_54;
      }
    }
    v5 = (KSPIN_LOCK *)v34;
    v7 = (char *)Entry;
    v15 = *((_QWORD *)v34 + 9);
    *(_WORD *)(a3 + 74) = 0;
    *(_WORD *)(a3 + 442) = 0;
    *(_BYTE *)(a3 + 72) = -1;
    *(_BYTE *)(a3 + 440) = -1;
    v7[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 221);
    v16 = v7 + 520;
    *(_QWORD *)(a3 + 8) = *((_QWORD *)v7 + 51);
    v17 = 2;
    *(_OWORD *)(a3 + 16) = *((_OWORD *)v7 + 26);
    *(_QWORD *)(a3 + 32) = *((_QWORD *)v7 + 54);
    v18 = (_OWORD *)(a3 + 120);
    *(_OWORD *)(a3 + 40) = *(_OWORD *)(v7 + 440);
    *(_QWORD *)(a3 + 56) = *((_QWORD *)v7 + 57);
    do
    {
      *v18 = *v16;
      v18[1] = v16[1];
      v18[2] = v16[2];
      v18[3] = v16[3];
      v18[4] = v16[4];
      v18[5] = v16[5];
      v18[6] = v16[6];
      v19 = v16[7];
      v16 += 8;
      v18[7] = v19;
      v18 += 8;
      --v17;
    }
    while ( v17 );
    v20 = v7 + 896;
    *(_DWORD *)(a3 + 116) = *((_DWORD *)v7 + 129);
    v21 = 2;
    *(_QWORD *)(a3 + 376) = *((_QWORD *)v7 + 98);
    *(_OWORD *)(a3 + 384) = *(_OWORD *)(v7 + 792);
    *(_QWORD *)(a3 + 400) = *((_QWORD *)v7 + 101);
    v22 = (_OWORD *)(a3 + 488);
    *(_OWORD *)(a3 + 408) = *((_OWORD *)v7 + 51);
    *(_QWORD *)(a3 + 424) = *((_QWORD *)v7 + 104);
    do
    {
      *v22 = *v20;
      v22[1] = v20[1];
      v22[2] = v20[2];
      v22[3] = v20[3];
      v22[4] = v20[4];
      v22[5] = v20[5];
      v22[6] = v20[6];
      v23 = v20[7];
      v20 += 8;
      v22[7] = v23;
      v22 += 8;
      --v21;
    }
    while ( v21 );
    *(_DWORD *)(a3 + 484) = *((_DWORD *)v7 + 223);
    *(_DWORD *)(a3 + 64) = 1;
    v24 = *((_DWORD *)v7 + 117);
    if ( v24 == 2 )
    {
      for ( i = 0; (unsigned int)i < 0x10; i = (unsigned int)(i + 1) )
      {
        if ( *(_BYTE *)(i + a3 + 16) )
          goto LABEL_29;
      }
    }
    else if ( v24 == 3 )
    {
      for ( j = 0; (unsigned int)j < 0x100; j = (unsigned int)(j + 1) )
      {
        if ( *(_BYTE *)(j + a3 + 120) )
        {
LABEL_29:
          *(_DWORD *)(a3 + 64) = 225;
          break;
        }
      }
    }
    *(_DWORD *)(a3 + 432) = 1;
    v27 = *((_DWORD *)v7 + 211);
    if ( v27 == 2 )
    {
      for ( k = 0; (unsigned int)k < 0x10; k = (unsigned int)(k + 1) )
      {
        if ( *(_BYTE *)(k + a3 + 384) )
          goto LABEL_40;
      }
    }
    else if ( v27 == 3 )
    {
      for ( m = 0; (unsigned int)m < 0x100; m = (unsigned int)(m + 1) )
      {
        if ( *(_BYTE *)(m + a3 + 488) )
        {
LABEL_40:
          *(_DWORD *)(a3 + 432) = 225;
          break;
        }
      }
    }
    if ( gbHistoryless )
    {
      v30 = *(_DWORD *)(v15 + 124);
      if ( (unsigned int)(v30 - 8) <= 1 || (unsigned int)(v30 - 13) <= 2 )
      {
        *(_DWORD *)(a3 + 64) |= 0x1000000u;
        *(_DWORD *)(a3 + 432) |= 0x1000000u;
      }
    }
  }
LABEL_54:
  if ( v7 )
  {
    v31 = (*((_DWORD *)v7 + 6))-- == 1;
    if ( v31 )
      DoDerefBundleCBWork(v7);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v7 + 221, v7[1776]);
  }
  if ( v5 )
  {
    v32 = KeAcquireSpinLockRaiseToDpc(v5 + 92);
    *((_BYTE *)v5 + 744) = v32;
    v31 = (*((_DWORD *)v5 + 7))-- == 1;
    if ( v31 )
      DoDerefLinkCBWork(v5);
    else
      KeReleaseSpinLock(v5 + 92, v32);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140027fe0  push    rbp
0x140027fe2  push    rbx
0x140027fe3  push    rsi
0x140027fe4  push    rdi
0x140027fe5  push    r12
0x140027fe7  push    r14
0x140027fe9  push    r15
0x140027feb  mov     rbp, rsp
0x140027fee  sub     rsp, 30h
0x140027ff2  xor     esi, esi
0x140027ff4  mov     r14d, r9d
0x140027ff7  xor     ebx, ebx
0x140027ff9  mov     [rbp+arg_0], rsi
0x140027ffd  mov     [rbp+Entry], rbx
0x140028001  mov     rdi, r8
0x140028004  mov     r15d, edx
0x140028007  mov     r12, rcx
0x14002800a  mov     rcx, cs:WPP_GLOBAL_Control
0x140028011  lea     rdx, WPP_GLOBAL_Control
0x140028018  cmp     rcx, rdx
0x14002801b  jz      short loc_140028044
0x14002801d  mov     eax, [rcx+2Ch]
0x140028020  test    al, 20h
0x140028022  jz      short loc_140028044
0x140028024  cmp     byte ptr [rcx+29h], 5
0x140028028  jb      short loc_140028044
0x14002802a  mov     rcx, [rcx+18h]
0x14002802e  lea     edx, [rsi+51h]
0x140028031  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028038  call    WPP_SF_
0x14002803d  lea     rdx, WPP_GLOBAL_Control
0x140028044  mov     rax, [rbp+arg_20]
0x140028048  mov     r8d, 2E8h
0x14002804e  mov     [rax], r8d
0x140028051  cmp     r15d, r8d
0x140028054  jb      loc_140028311
0x14002805a  cmp     r14d, r8d
0x14002805d  jb      loc_140028311
0x140028063  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x140028069  test    al, 10h
0x14002806b  jz      short loc_140028072
0x14002806d  and     eax, 1
0x140028070  jmp     short loc_140028077
0x140028072  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x140028077  mov     rcx, [r12]
0x14002807b  mov     r12d, 1
0x140028081  lea     r9, [rbp+Entry]
0x140028085  mov     dl, r12b
0x140028088  lea     r8, [rbp+arg_0]
0x14002808c  test    eax, eax
0x14002808e  jnz     short loc_1400280AF
0x140028090  xor     r14d, r14d
0x140028093  call    AreLinkAndBundleValid
0x140028098  test    al, al
0x14002809a  jnz     short loc_1400280BB
0x14002809c  mov     r14d, 259h
0x1400280a2  mov     rsi, [rbp+arg_0]
0x1400280a6  mov     rbx, [rbp+Entry]
0x1400280aa  jmp     loc_140028390
0x1400280af  call    ValidateLinkAndBundle
0x1400280b4  mov     r14d, eax
0x1400280b7  test    eax, eax
0x1400280b9  js      short loc_1400280A2
0x1400280bb  mov     rsi, [rbp+arg_0]
0x1400280bf  xor     ecx, ecx
0x1400280c1  mov     rbx, [rbp+Entry]
0x1400280c5  mov     r15, [rsi+48h]
0x1400280c9  mov     [rdi+4Ah], cx
0x1400280cd  mov     [rdi+1BAh], cx
0x1400280d4  lea     rcx, [rbx+6E8h]; SpinLock
0x1400280db  mov     byte ptr [rdi+48h], 0FFh
0x1400280df  mov     byte ptr [rdi+1B8h], 0FFh
0x1400280e6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400280ed  nop     dword ptr [rax+rax+00h]
0x1400280f2  mov     [rbx+6F0h], al
0x1400280f8  mov     r9d, 2
0x1400280fe  mov     rax, [rbx+198h]
0x140028105  lea     rcx, [rbx+208h]
0x14002810c  mov     [rdi+8], rax
0x140028110  mov     edx, r9d
0x140028113  movups  xmm0, xmmword ptr [rbx+1A0h]
0x14002811a  lea     r8d, [r9+7Eh]
0x14002811e  movdqu  xmmword ptr [rdi+10h], xmm0
0x140028123  mov     rax, [rbx+1B0h]
0x14002812a  mov     [rdi+20h], rax
0x14002812e  lea     rax, [rdi+78h]
0x140028132  movups  xmm0, xmmword ptr [rbx+1B8h]
0x140028139  movups  xmmword ptr [rdi+28h], xmm0
0x14002813d  movsd   xmm1, qword ptr [rbx+1C8h]
0x140028145  movsd   qword ptr [rdi+38h], xmm1
0x14002814a  movups  xmm0, xmmword ptr [rcx]
0x14002814d  movups  xmmword ptr [rax], xmm0
0x140028150  movups  xmm1, xmmword ptr [rcx+10h]
0x140028154  movups  xmmword ptr [rax+10h], xmm1
0x140028158  movups  xmm0, xmmword ptr [rcx+20h]
0x14002815c  movups  xmmword ptr [rax+20h], xmm0
0x140028160  movups  xmm1, xmmword ptr [rcx+30h]
0x140028164  movups  xmmword ptr [rax+30h], xmm1
0x140028168  movups  xmm0, xmmword ptr [rcx+40h]
0x14002816c  movups  xmmword ptr [rax+40h], xmm0
0x140028170  movups  xmm1, xmmword ptr [rcx+50h]
0x140028174  movups  xmmword ptr [rax+50h], xmm1
0x140028178  movups  xmm0, xmmword ptr [rcx+60h]
0x14002817c  movups  xmmword ptr [rax+60h], xmm0
0x140028180  movups  xmm1, xmmword ptr [rcx+70h]
0x140028184  add     rcx, r8
0x140028187  movups  xmmword ptr [rax+70h], xmm1
0x14002818b  add     rax, r8
0x14002818e  sub     rdx, 1
0x140028192  jnz     short loc_14002814A
0x140028194  mov     eax, [rbx+204h]
0x14002819a  lea     rcx, [rbx+380h]
0x1400281a1  mov     [rdi+74h], eax
0x1400281a4  mov     rdx, r9
0x1400281a7  mov     rax, [rbx+310h]
0x1400281ae  mov     [rdi+178h], rax
0x1400281b5  movups  xmm0, xmmword ptr [rbx+318h]
0x1400281bc  movdqu  xmmword ptr [rdi+180h], xmm0
0x1400281c4  mov     rax, [rbx+328h]
0x1400281cb  mov     [rdi+190h], rax
0x1400281d2  lea     rax, [rdi+1E8h]
0x1400281d9  movups  xmm0, xmmword ptr [rbx+330h]
0x1400281e0  movups  xmmword ptr [rdi+198h], xmm0
0x1400281e7  movsd   xmm1, qword ptr [rbx+340h]
0x1400281ef  movsd   qword ptr [rdi+1A8h], xmm1
0x1400281f7  movups  xmm0, xmmword ptr [rcx]
0x1400281fa  movups  xmmword ptr [rax], xmm0
0x1400281fd  movups  xmm1, xmmword ptr [rcx+10h]
0x140028201  movups  xmmword ptr [rax+10h], xmm1
0x140028205  movups  xmm0, xmmword ptr [rcx+20h]
0x140028209  movups  xmmword ptr [rax+20h], xmm0
0x14002820d  movups  xmm1, xmmword ptr [rcx+30h]
0x140028211  movups  xmmword ptr [rax+30h], xmm1
0x140028215  movups  xmm0, xmmword ptr [rcx+40h]
0x140028219  movups  xmmword ptr [rax+40h], xmm0
0x14002821d  movups  xmm1, xmmword ptr [rcx+50h]
0x140028221  movups  xmmword ptr [rax+50h], xmm1
0x140028225  movups  xmm0, xmmword ptr [rcx+60h]
0x140028229  movups  xmmword ptr [rax+60h], xmm0
0x14002822d  movups  xmm1, xmmword ptr [rcx+70h]
0x140028231  add     rcx, r8
0x140028234  movups  xmmword ptr [rax+70h], xmm1
0x140028238  add     rax, r8
0x14002823b  sub     rdx, 1
0x14002823f  jnz     short loc_1400281F7
0x140028241  mov     eax, [rbx+37Ch]
0x140028247  mov     edx, 100h
0x14002824c  mov     [rdi+1E4h], eax
0x140028252  mov     [rdi+40h], r12d
0x140028256  mov     eax, [rbx+1D4h]
0x14002825c  lea     r8d, [rdx-1Fh]
0x140028260  cmp     eax, r9d
0x140028263  jnz     short loc_140028278
0x140028265  xor     ecx, ecx
0x140028267  cmp     ecx, 10h
0x14002826a  jnb     short loc_140028293
0x14002826c  cmp     byte ptr [rcx+rdi+10h], 0
0x140028271  jnz     short loc_14002828F
0x140028273  add     ecx, r12d
0x140028276  jmp     short loc_140028267
0x140028278  cmp     eax, 3
0x14002827b  jnz     short loc_140028293
0x14002827d  xor     ecx, ecx
0x14002827f  cmp     ecx, edx
0x140028281  jnb     short loc_140028293
0x140028283  cmp     byte ptr [rcx+rdi+78h], 0
0x140028288  jnz     short loc_14002828F
0x14002828a  add     ecx, r12d
0x14002828d  jmp     short loc_14002827F
0x14002828f  mov     [rdi+40h], r8d
0x140028293  mov     [rdi+1B0h], r12d
0x14002829a  mov     eax, [rbx+34Ch]
0x1400282a0  cmp     eax, r9d
0x1400282a3  jnz     short loc_1400282BB
0x1400282a5  xor     ecx, ecx
0x1400282a7  cmp     ecx, 10h
0x1400282aa  jnb     short loc_1400282DC
0x1400282ac  cmp     byte ptr [rcx+rdi+180h], 0
0x1400282b4  jnz     short loc_1400282D5
0x1400282b6  add     ecx, r12d
0x1400282b9  jmp     short loc_1400282A7
0x1400282bb  cmp     eax, 3
0x1400282be  jnz     short loc_1400282DC
0x1400282c0  xor     ecx, ecx
0x1400282c2  cmp     ecx, edx
0x1400282c4  jnb     short loc_1400282DC
0x1400282c6  cmp     byte ptr [rcx+rdi+1E8h], 0
0x1400282ce  jnz     short loc_1400282D5
0x1400282d0  add     ecx, r12d
0x1400282d3  jmp     short loc_1400282C2
0x1400282d5  mov     [rdi+1B0h], r8d
0x1400282dc  cmp     cs:gbHistoryless, 0
0x1400282e3  jz      loc_140028390
0x1400282e9  mov     ecx, [r15+7Ch]
0x1400282ed  lea     eax, [rcx-8]
0x1400282f0  cmp     eax, r12d
0x1400282f3  jbe     short loc_140028301
0x1400282f5  lea     eax, [rcx-0Dh]
0x1400282f8  cmp     eax, r9d
0x1400282fb  ja      loc_140028390
0x140028301  mov     eax, 1000000h
0x140028306  or      [rdi+40h], eax
0x140028309  or      [rdi+1B0h], eax
0x14002830f  jmp     short loc_140028390
0x140028311  mov     rcx, cs:WPP_GLOBAL_Control
0x140028318  cmp     rcx, rdx
0x14002831b  jz      short loc_14002838A
0x14002831d  mov     eax, [rcx+2Ch]
0x140028320  test    al, 20h
0x140028322  jz      short loc_140028354
0x140028324  cmp     byte ptr [rcx+29h], 3
0x140028328  jb      short loc_140028354
0x14002832a  mov     rcx, [rcx+18h]
0x14002832e  mov     edx, 52h ; 'R'
0x140028333  mov     [rsp+30h+var_10], r8d
0x140028338  mov     r9d, r14d
0x14002833b  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028342  call    WPP_SF_dd
0x140028347  mov     r8d, 2E8h
0x14002834d  lea     rdx, WPP_GLOBAL_Control
0x140028354  mov     rcx, cs:WPP_GLOBAL_Control
0x14002835b  cmp     rcx, rdx
0x14002835e  jz      short loc_14002838A
0x140028360  mov     eax, [rcx+2Ch]
0x140028363  test    al, 20h
0x140028365  jz      short loc_14002838A
0x140028367  cmp     byte ptr [rcx+29h], 3
0x14002836b  jb      short loc_14002838A
0x14002836d  mov     rcx, [rcx+18h]
0x140028371  mov     edx, 53h ; 'S'
0x140028376  mov     [rsp+30h+var_10], r8d
0x14002837b  mov     r9d, r15d
0x14002837e  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028385  call    WPP_SF_dd
0x14002838a  mov     r14d, 0C0000004h
0x140028390  or      edi, 0FFFFFFFFh
0x140028393  test    rbx, rbx
0x140028396  jz      short loc_1400283C0
0x140028398  add     [rbx+18h], edi
0x14002839b  jnz     short loc_1400283A7
0x14002839d  mov     rcx, rbx; Entry
0x1400283a0  call    DoDerefBundleCBWork
0x1400283a5  jmp     short loc_1400283C0
0x1400283a7  mov     dl, [rbx+6F0h]; NewIrql
0x1400283ad  lea     rcx, [rbx+6E8h]; SpinLock
0x1400283b4  call    cs:__imp_KeReleaseSpinLock
0x1400283bb  nop     dword ptr [rax+rax+00h]
0x1400283c0  test    rsi, rsi
0x1400283c3  jz      short loc_140028401
0x1400283c5  lea     rbx, [rsi+2E0h]
0x1400283cc  mov     rcx, rbx; SpinLock
0x1400283cf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400283d6  nop     dword ptr [rax+rax+00h]
0x1400283db  mov     [rsi+2E8h], al
0x1400283e1  add     [rsi+1Ch], edi
0x1400283e4  jnz     short loc_1400283F0
0x1400283e6  mov     rcx, rsi; Entry
0x1400283e9  call    DoDerefLinkCBWork
0x1400283ee  jmp     short loc_140028401
0x1400283f0  mov     dl, al; NewIrql
0x1400283f2  mov     rcx, rbx; SpinLock
0x1400283f5  call    cs:__imp_KeReleaseSpinLock
0x1400283fc  nop     dword ptr [rax+rax+00h]
0x140028401  mov     eax, r14d
0x140028404  add     rsp, 30h
0x140028408  pop     r15
0x14002840a  pop     r14
0x14002840c  pop     r12
0x14002840e  pop     rdi
0x14002840f  pop     rsi
0x140028410  pop     rbx
0x140028411  pop     rbp
0x140028412  retn
```
