# HidpEtwRundownOld

- ea: `0x180020c54`
- end: `0x1800211a9`
- name: `HidpEtwRundownOld`
- size: `1365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b704`

## callees

- `0x180014a44`
- `0x180014e80`
- `0x180020c54`
- `0x180027ba0`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x180020cac`
- `ntoskrnl!EtwActivityIdControl` at `0x180020cac`
- `ntoskrnl!EtwWrite` at `0x18002108f`
- `ntoskrnl!EtwWrite` at `0x18002108f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180020d22`
- `ntoskrnl!ExFreePoolWithTag` at `0x180021179`
- `ntoskrnl!ExFreePoolWithTag` at `0x180020d22`
- `ntoskrnl!ExFreePoolWithTag` at `0x180021179`
- `ntoskrnl!ExAllocatePool2` at `0x180020d3c`
- `ntoskrnl!ExAllocatePool2` at `0x180020d3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x180021142`
- `ntoskrnl!KeReleaseSpinLock` at `0x180021142`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180020ce0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180020ce0`

## pseudocode

```c
void __fastcall HidpEtwRundownOld(char a1)
{
  char *Pool2; // rdi
  unsigned int v3; // r15d
  KIRQL v4; // al
  unsigned __int64 v5; // rbx
  KIRQL v6; // r13
  unsigned int v7; // edx
  unsigned int v8; // r14d
  int v9; // edx
  int v10; // r8d
  int v11; // r8d
  int *v12; // rax
  int *v13; // rcx
  int *v14; // rax
  int v15; // ecx
  int *v16; // rax
  int v17; // ecx
  int *v18; // rax
  int v19; // ecx
  int *v20; // rax
  int v21; // ecx
  unsigned int v22; // r9d
  int v23; // ecx
  int v24; // ecx
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+64h] [rbp-9Ch] BYREF
  int v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v38; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  int *v42; // [rsp+E0h] [rbp-20h]
  int v43; // [rsp+E8h] [rbp-18h]
  int v44; // [rsp+ECh] [rbp-14h]
  int *v45; // [rsp+F0h] [rbp-10h]
  int v46; // [rsp+F8h] [rbp-8h]
  int v47; // [rsp+FCh] [rbp-4h]
  int *v48; // [rsp+100h] [rbp+0h]
  int v49; // [rsp+108h] [rbp+8h]
  int v50; // [rsp+10Ch] [rbp+Ch]
  int *v51; // [rsp+110h] [rbp+10h]
  int v52; // [rsp+118h] [rbp+18h]
  int v53; // [rsp+11Ch] [rbp+1Ch]
  int *v54; // [rsp+120h] [rbp+20h]
  int v55; // [rsp+128h] [rbp+28h]
  int v56; // [rsp+12Ch] [rbp+2Ch]
  unsigned int *v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+138h] [rbp+38h]
  unsigned __int64 v59; // [rsp+140h] [rbp+40h]
  __int64 v60; // [rsp+148h] [rbp+48h]
  __int64 v61; // [rsp+150h] [rbp+50h]
  int v62; // [rsp+158h] [rbp+58h]
  int v63; // [rsp+15Ch] [rbp+5Ch]
  unsigned __int64 v64; // [rsp+160h] [rbp+60h]
  __int64 v65; // [rsp+168h] [rbp+68h]
  int *v66; // [rsp+170h] [rbp+70h]
  __int64 v67; // [rsp+178h] [rbp+78h]
  int *v68; // [rsp+180h] [rbp+80h]
  __int64 v69; // [rsp+188h] [rbp+88h]
  unsigned __int64 v70; // [rsp+190h] [rbp+90h]
  __int64 v71; // [rsp+198h] [rbp+98h]
  unsigned __int64 v72; // [rsp+1A0h] [rbp+A0h]
  __int64 v73; // [rsp+1A8h] [rbp+A8h]
  unsigned __int64 v74; // [rsp+1B0h] [rbp+B0h]
  __int64 v75; // [rsp+1B8h] [rbp+B8h]
  unsigned __int64 v76; // [rsp+1C0h] [rbp+C0h]
  __int64 v77; // [rsp+1C8h] [rbp+C8h]
  unsigned __int64 v78; // [rsp+1D0h] [rbp+D0h]
  __int64 v79; // [rsp+1D8h] [rbp+D8h]
  unsigned __int64 v80; // [rsp+1E0h] [rbp+E0h]
  __int64 v81; // [rsp+1E8h] [rbp+E8h]
  char *v82; // [rsp+1F0h] [rbp+F0h]
  unsigned int v83; // [rsp+1F8h] [rbp+F8h]
  int v84; // [rsp+1FCh] [rbp+FCh]

  v31 = 0;
  v30 = 0;
  Pool2 = 0;
  v29 = 0;
  v28 = 0;
  v3 = 0;
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  if ( (WPP_MAIN_CB.AlignmentRequirement & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(&MS_HIDCLASS_ETW_PROVIDER_Context, HIDCLASS_ETW_EVENT_RUNDOWN_START, &ActivityId);
  v4 = KeAcquireSpinLockRaiseToDpc(&allFdoExtensionsSpinLock);
  v5 = allFdoExtensions;
  v6 = v4;
  while ( v5 )
  {
    v7 = *(_DWORD *)(v5 + 168);
    v8 = 68 * v7;
    v28 = v7;
    if ( v7 > v3 )
    {
      if ( Pool2 )
        ExFreePoolWithTag(Pool2, 0);
      Pool2 = (char *)ExAllocatePool2(64, v8, 1130654024);
      if ( !Pool2 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        {
          LOBYTE(v9) = 0;
        }
        if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qLL(
            WPP_GLOBAL_Control->AttachedDevice,
            v9,
            v10,
            *(_QWORD *)(v5 + 680),
            2,
            3,
            75,
            (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
            *(_QWORD *)v5,
            v28,
            v8);
        }
        break;
      }
      v7 = v28;
    }
    UserData.Ptr = v5;
    v3 = v7;
    *(_QWORD *)&UserData.Size = 8;
    v31 = **(_QWORD **)(*(_QWORD *)v5 + 64LL);
    v34 = &v31;
    v36 = v5 + 108;
    v38 = v5 + 110;
    v40 = v5 + 112;
    v35 = 8;
    v37 = 2;
    v39 = 2;
    v41 = 2;
    if ( *(_QWORD *)(v5 + 48) )
      v11 = *(_DWORD *)(v5 + 24);
    else
      v11 = 2;
    v12 = *(int **)(v5 + 16);
    v13 = &dword_18002B11C;
    v43 = v11;
    v44 = 0;
    if ( v12 )
      v13 = v12;
    v42 = v13;
    v14 = *(int **)(v5 + 32);
    if ( v14 )
    {
      v15 = *(_DWORD *)(v5 + 40);
    }
    else
    {
      v14 = &dword_18002B11C;
      v15 = 2;
    }
    v45 = v14;
    v46 = v15;
    v47 = 0;
    v16 = *(int **)(v5 + 48);
    if ( v16 )
    {
      v17 = *(_DWORD *)(v5 + 56);
    }
    else
    {
      v16 = &dword_18002B11C;
      v17 = 2;
    }
    v48 = v16;
    v49 = v17;
    v50 = 0;
    v18 = *(int **)(v5 + 64);
    if ( v18 )
    {
      v19 = *(_DWORD *)(v5 + 72);
    }
    else
    {
      v18 = &dword_18002B11C;
      v19 = 2;
    }
    v51 = v18;
    v52 = v19;
    v53 = 0;
    v20 = *(int **)(v5 + 80);
    if ( v20 )
    {
      v21 = *(_DWORD *)(v5 + 88);
    }
    else
    {
      v20 = &dword_18002B11C;
      v21 = 2;
    }
    v54 = v20;
    v22 = 0;
    v55 = v21;
    v57 = &v28;
    v56 = 0;
    v59 = v5 + 144;
    v58 = 4;
    v60 = 4;
    v23 = *(_DWORD *)(v5 + 144);
    v61 = *(_QWORD *)(v5 + 136);
    v64 = v5 + 364;
    v63 = 0;
    v62 = v23;
    v65 = 4;
    v24 = *(_DWORD *)(v5 + 4LL * *(unsigned int *)(v5 + 1584) + 1556);
    v66 = &v29;
    v29 = v24;
    v67 = 4;
    v30 = *(_DWORD *)(v5 + 248);
    v68 = &v30;
    v70 = v5 + 2104;
    v72 = v5 + 2064;
    v74 = v5 + 2072;
    v76 = v5 + 2080;
    v78 = v5 + 2088;
    v69 = 4;
    v71 = 8;
    v73 = 8;
    v75 = 8;
    v77 = 8;
    v79 = 8;
    v80 = v5 + 2096;
    v81 = 8;
    if ( v7 )
    {
      do
      {
        v25 = *(_QWORD *)(v5 + 152);
        v26 = 68LL * v22;
        v27 = 424LL * v22;
        *(_DWORD *)&Pool2[v26] = *(_DWORD *)(v27 + v25);
        *(_WORD *)&Pool2[v26 + 4] = *(_WORD *)(v27 + v25 + 8);
        *(_WORD *)&Pool2[v26 + 6] = *(_WORD *)(v27 + v25 + 10);
        *(_DWORD *)&Pool2[v26 + 8] = *(_DWORD *)(v27 + v25 + 352);
        *(_QWORD *)&Pool2[v26 + 12] = *(_QWORD *)(v27 + v25 + 360);
        *(_QWORD *)&Pool2[v26 + 20] = *(_QWORD *)(v27 + v25 + 376);
        *(_QWORD *)&Pool2[v26 + 28] = *(_QWORD *)(v27 + v25 + 384);
        *(_QWORD *)&Pool2[v26 + 36] = *(_QWORD *)(v27 + v25 + 392);
        *(_QWORD *)&Pool2[v26 + 44] = *(_QWORD *)(v27 + v25 + 400);
        *(_QWORD *)&Pool2[v26 + 52] = *(_QWORD *)(v27 + v25 + 408);
        *(_QWORD *)&Pool2[v26 + 60] = *(_QWORD *)(v27 + v25 + 416);
        if ( a1 )
          _InterlockedExchange64((volatile __int64 *)(v27 + v25 + 416), 0);
        ++v22;
      }
      while ( v22 < v28 );
    }
    v82 = Pool2;
    v83 = v8;
    v84 = 0;
    EtwWrite(MS_HIDCLASS_ETW_PROVIDER_Context, &HIDCLASS_ETW_EVENT_DEVICE_INFORMATION_V1, &ActivityId, 0x17u, &UserData);
    if ( a1 )
      _InterlockedExchange64((volatile __int64 *)(v5 + 2096), 0);
    v5 = *(_QWORD *)(v5 + 496);
  }
  KeReleaseSpinLock(&allFdoExtensionsSpinLock, v6);
  if ( (WPP_MAIN_CB.AlignmentRequirement & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(&MS_HIDCLASS_ETW_PROVIDER_Context, HIDCLASS_ETW_EVENT_RUNDOWN_COMPLETE, &ActivityId);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
}

```

## disassembly

```asm
0x180020c54  push    rbp
0x180020c56  push    rbx
0x180020c57  push    rsi
0x180020c58  push    rdi
0x180020c59  push    r12
0x180020c5b  push    r13
0x180020c5d  push    r14
0x180020c5f  push    r15
0x180020c61  lea     rbp, [rsp-118h]
0x180020c69  sub     rsp, 218h
0x180020c70  mov     rax, cs:__security_cookie
0x180020c77  xor     rax, rsp
0x180020c7a  mov     [rbp+150h+var_50], rax
0x180020c81  xor     esi, esi
0x180020c83  lea     rdx, [rsp+250h+ActivityId]; ActivityId
0x180020c88  mov     r12b, cl
0x180020c8b  mov     [rsp+250h+var_1E0], rsi
0x180020c90  xorps   xmm0, xmm0
0x180020c93  mov     [rsp+250h+var_1E8], esi
0x180020c97  mov     edi, esi
0x180020c99  mov     [rsp+250h+var_1EC], esi
0x180020c9d  lea     ecx, [rsi+3]; ControlCode
0x180020ca0  mov     [rsp+250h+var_1F0], esi
0x180020ca4  mov     r15d, esi
0x180020ca7  movups  xmmword ptr [rsp+250h+ActivityId.Data1], xmm0
0x180020cac  call    cs:__imp_EtwActivityIdControl
0x180020cb3  nop     dword ptr [rax+rax+00h]
0x180020cb8  test    byte ptr cs:WPP_MAIN_CB.AlignmentRequirement, 1
0x180020cbf  jz      short loc_180020CD9
0x180020cc1  lea     r8, [rsp+250h+ActivityId]
0x180020cc6  lea     rdx, HIDCLASS_ETW_EVENT_RUNDOWN_START
0x180020ccd  lea     rcx, MS_HIDCLASS_ETW_PROVIDER_Context
0x180020cd4  call    McTemplateK0_EtwWriteTransfer
0x180020cd9  lea     rcx, allFdoExtensionsSpinLock; SpinLock
0x180020ce0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180020ce7  nop     dword ptr [rax+rax+00h]
0x180020cec  mov     rbx, cs:allFdoExtensions
0x180020cf3  mov     r13b, al
0x180020cf6  mov     r9d, 2
0x180020cfc  test    rbx, rbx
0x180020cff  jz      loc_180021138
0x180020d05  mov     edx, [rbx+0A8h]
0x180020d0b  imul    r14d, edx, 44h ; 'D'
0x180020d0f  mov     [rsp+250h+var_1F0], edx
0x180020d13  cmp     edx, r15d
0x180020d16  jbe     short loc_180020D5E
0x180020d18  test    rdi, rdi
0x180020d1b  jz      short loc_180020D2E
0x180020d1d  xor     edx, edx; Tag
0x180020d1f  mov     rcx, rdi; P
0x180020d22  call    cs:__imp_ExFreePoolWithTag
0x180020d29  nop     dword ptr [rax+rax+00h]
0x180020d2e  mov     edx, r14d
0x180020d31  mov     ecx, 40h ; '@'
0x180020d36  mov     r8d, 43646948h
0x180020d3c  call    cs:__imp_ExAllocatePool2
0x180020d43  nop     dword ptr [rax+rax+00h]
0x180020d48  mov     rdi, rax
0x180020d4b  test    rax, rax
0x180020d4e  jz      loc_1800210B3
0x180020d54  mov     edx, [rsp+250h+var_1F0]
0x180020d58  mov     r9d, 2
0x180020d5e  mov     [rbp+150h+var_1C0.Ptr], rbx
0x180020d62  mov     r15d, edx
0x180020d65  mov     qword ptr [rbp+150h+var_1C0.Size], 8
0x180020d6d  mov     rax, [rbx]
0x180020d70  mov     rcx, [rax+40h]
0x180020d74  mov     rax, [rcx]
0x180020d77  mov     [rsp+250h+var_1E0], rax
0x180020d7c  lea     rax, [rsp+250h+var_1E0]
0x180020d81  mov     [rbp+150h+var_1B0], rax
0x180020d85  lea     rax, [rbx+6Ch]
0x180020d89  mov     [rbp+150h+var_1A0], rax
0x180020d8d  lea     rax, [rbx+6Eh]
0x180020d91  mov     [rbp+150h+var_190], rax
0x180020d95  lea     rax, [rbx+70h]
0x180020d99  mov     [rbp+150h+var_180], rax
0x180020d9d  mov     [rbp+150h+var_1A8], 8
0x180020da5  mov     [rbp+150h+var_198], 2
0x180020dad  mov     [rbp+150h+var_188], 2
0x180020db5  mov     [rbp+150h+var_178], 2
0x180020dbd  cmp     [rbx+30h], rsi
0x180020dc1  jz      short loc_180020DC9
0x180020dc3  mov     r8d, [rbx+18h]
0x180020dc7  jmp     short loc_180020DCC
0x180020dc9  mov     r8d, r9d
0x180020dcc  mov     rax, [rbx+10h]
0x180020dd0  lea     rcx, dword_18002B11C
0x180020dd7  test    rax, rax
0x180020dda  mov     [rbp+150h+var_168], r8d
0x180020dde  mov     [rbp+150h+var_164], esi
0x180020de1  cmovnz  rcx, rax
0x180020de5  mov     [rbp+150h+var_170], rcx
0x180020de9  mov     rax, [rbx+20h]
0x180020ded  test    rax, rax
0x180020df0  jz      short loc_180020DF7
0x180020df2  mov     ecx, [rbx+28h]
0x180020df5  jmp     short loc_180020E01
0x180020df7  lea     rax, dword_18002B11C
0x180020dfe  mov     ecx, r9d
0x180020e01  mov     [rbp+150h+var_160], rax
0x180020e05  mov     [rbp+150h+var_158], ecx
0x180020e08  mov     [rbp+150h+var_154], esi
0x180020e0b  mov     rax, [rbx+30h]
0x180020e0f  test    rax, rax
0x180020e12  jz      short loc_180020E19
0x180020e14  mov     ecx, [rbx+38h]
0x180020e17  jmp     short loc_180020E23
0x180020e19  lea     rax, dword_18002B11C
0x180020e20  mov     ecx, r9d
0x180020e23  mov     [rbp+150h+var_150], rax
0x180020e27  mov     [rbp+150h+var_148], ecx
0x180020e2a  mov     [rbp+150h+var_144], esi
0x180020e2d  mov     rax, [rbx+40h]
0x180020e31  test    rax, rax
0x180020e34  jz      short loc_180020E3B
0x180020e36  mov     ecx, [rbx+48h]
0x180020e39  jmp     short loc_180020E45
0x180020e3b  lea     rax, dword_18002B11C
0x180020e42  mov     ecx, r9d
0x180020e45  mov     [rbp+150h+var_140], rax
0x180020e49  mov     [rbp+150h+var_138], ecx
0x180020e4c  mov     [rbp+150h+var_134], esi
0x180020e4f  mov     rax, [rbx+50h]
0x180020e53  test    rax, rax
0x180020e56  jz      short loc_180020E5D
0x180020e58  mov     ecx, [rbx+58h]
0x180020e5b  jmp     short loc_180020E67
0x180020e5d  lea     rax, dword_18002B11C
0x180020e64  mov     ecx, r9d
0x180020e67  mov     [rbp+150h+var_130], rax
0x180020e6b  xor     r9d, r9d
0x180020e6e  mov     [rbp+150h+var_128], ecx
0x180020e71  lea     rax, [rsp+250h+var_1F0]
0x180020e76  mov     [rbp+150h+var_120], rax
0x180020e7a  lea     rcx, [rbx+90h]
0x180020e81  mov     [rbp+150h+var_124], esi
0x180020e84  mov     [rbp+150h+var_110], rcx
0x180020e88  mov     [rbp+150h+var_118], 4
0x180020e90  mov     [rbp+150h+var_108], 4
0x180020e98  mov     rax, [rbx+88h]
0x180020e9f  mov     ecx, [rcx]
0x180020ea1  mov     [rbp+150h+var_100], rax
0x180020ea5  lea     rax, [rbx+16Ch]
0x180020eac  mov     [rbp+150h+var_F0], rax
0x180020eb0  mov     [rbp+150h+var_F4], esi
0x180020eb3  lea     rsi, [rbx+830h]
0x180020eba  mov     [rbp+150h+var_F8], ecx
0x180020ebd  mov     [rbp+150h+var_E8], 4
0x180020ec5  mov     eax, [rbx+630h]
0x180020ecb  mov     ecx, [rbx+rax*4+614h]
0x180020ed2  lea     rax, [rsp+250h+var_1EC]
0x180020ed7  mov     [rbp+150h+var_E0], rax
0x180020edb  mov     [rsp+250h+var_1EC], ecx
0x180020edf  mov     [rbp+150h+var_D8], 4
0x180020ee7  mov     eax, [rbx+0F8h]
0x180020eed  mov     [rsp+250h+var_1E8], eax
0x180020ef1  lea     rax, [rsp+250h+var_1E8]
0x180020ef6  mov     [rbp+150h+var_D0], rax
0x180020efd  lea     rax, [rbx+838h]
0x180020f04  mov     [rbp+150h+var_C0], rax
0x180020f0b  lea     rax, [rbx+810h]
0x180020f12  mov     [rbp+150h+var_B0], rax
0x180020f19  lea     rax, [rbx+818h]
0x180020f20  mov     [rbp+150h+var_A0], rax
0x180020f27  lea     rax, [rbx+820h]
0x180020f2e  mov     [rbp+150h+var_90], rax
0x180020f35  lea     rax, [rbx+828h]
0x180020f3c  mov     [rbp+150h+var_80], rax
0x180020f43  mov     [rbp+150h+var_C8], 4
0x180020f4e  mov     [rbp+150h+var_B8], 8
0x180020f59  mov     [rbp+150h+var_A8], 8
0x180020f64  mov     [rbp+150h+var_98], 8
0x180020f6f  mov     [rbp+150h+var_88], 8
0x180020f7a  mov     [rbp+150h+var_78], 8
0x180020f85  mov     [rbp+150h+var_70], rsi
0x180020f8c  mov     [rbp+150h+var_68], 8
0x180020f97  test    edx, edx
0x180020f99  jz      loc_180021055
0x180020f9f  mov     r8, [rbx+98h]
0x180020fa6  mov     eax, r9d
0x180020fa9  imul    rcx, rax, 44h ; 'D'
0x180020fad  imul    rdx, rax, 1A8h
0x180020fb4  mov     eax, [rdx+r8]
0x180020fb8  mov     [rcx+rdi], eax
0x180020fbb  movzx   eax, word ptr [rdx+r8+8]
0x180020fc1  mov     [rcx+rdi+4], ax
0x180020fc6  movzx   eax, word ptr [rdx+r8+0Ah]
0x180020fcc  mov     [rcx+rdi+6], ax
0x180020fd1  mov     eax, [rdx+r8+160h]
0x180020fd9  mov     [rcx+rdi+8], eax
0x180020fdd  mov     rax, [rdx+r8+168h]
0x180020fe5  mov     [rcx+rdi+0Ch], rax
0x180020fea  mov     rax, [rdx+r8+178h]
0x180020ff2  mov     [rcx+rdi+14h], rax
0x180020ff7  mov     rax, [rdx+r8+180h]
0x180020fff  mov     [rcx+rdi+1Ch], rax
0x180021004  mov     rax, [rdx+r8+188h]
0x18002100c  mov     [rcx+rdi+24h], rax
0x180021011  mov     rax, [rdx+r8+190h]
0x180021019  mov     [rcx+rdi+2Ch], rax
0x18002101e  mov     rax, [rdx+r8+198h]
0x180021026  mov     [rcx+rdi+34h], rax
0x18002102b  mov     rax, [rdx+r8+1A0h]
0x180021033  mov     [rcx+rdi+3Ch], rax
0x180021038  test    r12b, r12b
0x18002103b  jz      short loc_180021047
0x18002103d  xor     eax, eax
0x18002103f  xchg    rax, [rdx+r8+1A0h]
0x180021047  inc     r9d
0x18002104a  cmp     r9d, [rsp+250h+var_1F0]
0x18002104f  jb      loc_180020F9F
0x180021055  mov     rcx, cs:MS_HIDCLASS_ETW_PROVIDER_Context; RegHandle
0x18002105c  lea     rax, [rbp+150h+var_1C0]
0x180021060  mov     r9d, 17h; UserDataCount
0x180021066  mov     [rsp+250h+UserData], rax; UserData
0x18002106b  lea     r8, [rsp+250h+ActivityId]; ActivityId
0x180021070  mov     [rbp+150h+var_60], rdi
0x180021077  lea     rdx, HIDCLASS_ETW_EVENT_DEVICE_INFORMATION_V1; EventDescriptor
0x18002107e  mov     [rbp+150h+var_58], r14d
0x180021085  mov     [rbp+150h+var_54], 0
0x18002108f  call    cs:__imp_EtwWrite
0x180021096  nop     dword ptr [rax+rax+00h]
0x18002109b  test    r12b, r12b
0x18002109e  jz      short loc_1800210A5
0x1800210a0  xor     eax, eax
0x1800210a2  xchg    rax, [rsi]
0x1800210a5  mov     rbx, [rbx+1F0h]
0x1800210ac  xor     esi, esi
0x1800210ae  jmp     loc_180020CF6
0x1800210b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210ba  lea     rax, WPP_GLOBAL_Control
0x1800210c1  cmp     rcx, rax
0x1800210c4  jz      short loc_1800210D5
0x1800210c6  mov     eax, [rcx+2Ch]
0x1800210c9  test    al, 4
0x1800210cb  jz      short loc_1800210D5
0x1800210cd  cmp     byte ptr [rcx+29h], 2
0x1800210d1  mov     dl, 1
0x1800210d3  jnb     short loc_1800210D8
0x1800210d5  mov     dl, sil
0x1800210d8  lea     rax, WPP_RECORDER_INITIALIZED
0x1800210df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800210e6  setnz   r8b
0x1800210ea  test    dl, dl
0x1800210ec  jnz     short loc_1800210F3
0x1800210ee  test    r8b, r8b
0x1800210f1  jz      short loc_180021138
0x1800210f3  mov     eax, [rsp+250h+var_1F0]
0x1800210f7  mov     r9, [rbx+2A8h]
0x1800210fe  mov     rcx, [rcx+18h]
0x180021102  mov     [rsp+250h+var_200], r14d
0x180021107  mov     [rsp+250h+var_208], eax
0x18002110b  mov     rax, [rbx]
0x18002110e  mov     [rsp+250h+var_210], rax
0x180021113  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18002111a  mov     [rsp+250h+var_218], rax
0x18002111f  mov     [rsp+250h+var_220], 4Bh ; 'K'
0x180021126  mov     [rsp+250h+var_228], 3
0x18002112e  mov     byte ptr [rsp+250h+UserData], 2
0x180021133  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x180021138  mov     dl, r13b; NewIrql
0x18002113b  lea     rcx, allFdoExtensionsSpinLock; SpinLock
0x180021142  call    cs:__imp_KeReleaseSpinLock
0x180021149  nop     dword ptr [rax+rax+00h]
0x18002114e  test    byte ptr cs:WPP_MAIN_CB.AlignmentRequirement, 1
0x180021155  jz      short loc_18002116F
0x180021157  lea     r8, [rsp+250h+ActivityId]
0x18002115c  lea     rdx, HIDCLASS_ETW_EVENT_RUNDOWN_COMPLETE
0x180021163  lea     rcx, MS_HIDCLASS_ETW_PROVIDER_Context
0x18002116a  call    McTemplateK0_EtwWriteTransfer
0x18002116f  test    rdi, rdi
0x180021172  jz      short loc_180021185
0x180021174  xor     edx, edx; Tag
0x180021176  mov     rcx, rdi; P
0x180021179  call    cs:__imp_ExFreePoolWithTag
0x180021180  nop     dword ptr [rax+rax+00h]
0x180021185  mov     rcx, [rbp+150h+var_50]
0x18002118c  xor     rcx, rsp; StackCookie
0x18002118f  call    __security_check_cookie
0x180021194  add     rsp, 218h
0x18002119b  pop     r15
0x18002119d  pop     r14
0x18002119f  pop     r13
0x1800211a1  pop     r12
0x1800211a3  pop     rdi
0x1800211a4  pop     rsi
0x1800211a5  pop     rbx
0x1800211a6  pop     rbp
0x1800211a7  retn
```
