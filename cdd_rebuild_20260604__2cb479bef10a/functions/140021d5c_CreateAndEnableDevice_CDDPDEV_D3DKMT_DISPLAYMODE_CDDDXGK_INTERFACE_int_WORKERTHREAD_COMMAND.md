# CreateAndEnableDevice(CDDPDEV *,_D3DKMT_DISPLAYMODE *,_CDDDXGK_INTERFACE *,int,_WORKERTHREAD_COMMAND)

- ea: `0x140021d5c`
- end: `0x14002225b`
- name: `?CreateAndEnableDevice@@YAJPEAUCDDPDEV@@PEAU_D3DKMT_DISPLAYMODE@@PEAU_CDDDXGK_INTERFACE@@HW4_WORKERTHREAD_COMMAND@@@Z`
- size: `1279`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011510`
- `0x140022c28`

## callees

- `0x140021d5c`
- `0x140027b1c`
- `0x14002a344`
- `0x14002cd8c`
- `0x14002d088`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry5` at `0x140021e36`
- `watchdog!WdLogSingleEntry5` at `0x140021eac`
- `watchdog!WdLogSingleEntry5` at `0x140022057`
- `watchdog!WdLogSingleEntry5` at `0x1400220cd`
- `watchdog!WdLogSingleEntry5` at `0x140022140`
- `watchdog!WdLogSingleEntry5` at `0x140021e36`
- `watchdog!WdLogSingleEntry5` at `0x140021eac`
- `watchdog!WdLogSingleEntry5` at `0x140022057`
- `watchdog!WdLogSingleEntry5` at `0x1400220cd`
- `watchdog!WdLogSingleEntry5` at `0x140022140`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x1400220e3`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x1400220e3`
- `watchdog!WdLogSingleEntry1` at `0x140022203`
- `watchdog!WdLogSingleEntry1` at `0x140022203`
- `watchdog!WdLogNewEntry5_WdError` at `0x140021e4c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002221a`
- `watchdog!WdLogNewEntry5_WdError` at `0x140021e4c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14002221a`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140021ec2`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002206d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140022156`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140021ec2`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002206d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140022156`

## pseudocode

```c
__int64 __fastcall CreateAndEnableDevice(__int64 a1, __int64 a2, __int64 a3, int a4, unsigned int a5)
{
  __int64 v5; // rdi
  _DWORD *v6; // rsi
  int v11; // ebp
  int v12; // eax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  int ResidencyState; // eax
  __int64 v16; // rcx
  int v17; // eax
  void (__fastcall *v18)(__int64, __int64, __int64); // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rax

  LODWORD(v5) = 0;
  v6 = (_DWORD *)(a1 + 2520);
  v11 = 3;
  while ( *v6 )
  {
LABEL_11:
    *(_QWORD *)(a1 + 5472) = (*(__int64 (**)(void))(a1 + 272))();
LABEL_12:
    v16 = (unsigned int)*v6;
    if ( (_DWORD)v16 )
    {
      if ( *(_BYTE *)(a1 + 2716) )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, __int64, __int64, __int64))(a1 + 104))(
                v16,
                *(unsigned int *)(a1 + 2708),
                a3,
                *(unsigned int *)(a1 + 784),
                a2,
                a1 + 2544,
                a1 + 2560,
                a1 + 1096);
        v5 = v17;
        if ( v17 < 0 )
        {
          v21 = (unsigned int)(v17 + 1071774970);
          if ( (unsigned int)v21 <= 0x32 && (v22 = 0x4200000000001LL, _bittest64(&v22, v21))
            || (_DWORD)v5 == -1073741130
            || (_DWORD)v5 == -1071774886 )
          {
            WdLogSingleEntry5(
              4,
              v5,
              a1,
              *(unsigned int *)(a1 + 784),
              *(unsigned int *)(a1 + 796),
              *(unsigned int *)(a1 + 800));
            WdLogGlobalForLineNumber = 5008;
            v25 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v25[3] = gCddImageInfo;
            v25[4] = (unsigned int)dword_14003E570;
            v25[5] = 215857758;
            WdLogGlobalForLineNumber = 5008;
          }
          else if ( (_DWORD)v5 == -1073741801 || (_DWORD)v5 == -1071775488 )
          {
            WdLogSingleEntry5(
              6,
              v5,
              a1,
              *(unsigned int *)(a1 + 784),
              *(unsigned int *)(a1 + 796),
              *(unsigned int *)(a1 + 800));
            WdLogGlobalForLineNumber = 5014;
            v24 = (_QWORD *)WdLogNewEntry5_WdLowResource();
            v24[3] = gCddImageInfo;
            v24[4] = (unsigned int)dword_14003E570;
            v24[5] = 215857758;
            WdLogGlobalForLineNumber = 5014;
          }
          else
          {
            WdLogSingleEntry5(
              4,
              v5,
              a1,
              *(unsigned int *)(a1 + 784),
              *(unsigned int *)(a1 + 796),
              *(unsigned int *)(a1 + 800));
            WdLogGlobalForLineNumber = 5019;
            v23 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v23[3] = gCddImageInfo;
            v23[4] = (unsigned int)dword_14003E570;
            v23[5] = 215857758;
            WdLogGlobalForLineNumber = 5019;
          }
          CDDPDEV::CheckDeviceRemoved((CDDPDEV *)a1, v5);
          if ( (*(_DWORD *)(a1 + 2744) & 0x400) != 0 )
            CDDPDEV::DestroyDevice(a1, a5);
          ++*(_DWORD *)(a1 + 2656);
          ++*(_DWORD *)(a1 + 2664);
          *(_DWORD *)(a1 + 2668) = 100;
        }
        else
        {
          BootAnimationRelayThreadStartup((PVOID)a1);
          v18 = *(void (__fastcall **)(__int64, __int64, __int64))(a1 + 184);
          v19 = *(unsigned int *)(a1 + 784);
          v20 = *(_QWORD *)(a1 + 2488);
          *(_BYTE *)(a1 + 2714) = 0;
          *(_BYTE *)(a1 + 2717) = 0;
          v18(v20, v19, a1 + 788);
          ++*(_DWORD *)(a1 + 2660);
          *(_DWORD *)(a1 + 2668) = 1;
          *(_DWORD *)(a1 + 2664) = 0;
        }
      }
      else if ( a4 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 184))(
          *(_QWORD *)(a1 + 2488),
          *(unsigned int *)(a1 + 784),
          a1 + 788);
      }
    }
    if ( !v11 || *v6 )
      return (unsigned int)v5;
    --v11;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _DWORD *, __int64, __int64, __int64, __int64, __int64, __int64))(a1 + 88))(
          *(_QWORD *)(a1 + 2488),
          *(_QWORD *)(a1 + 2504),
          *(_QWORD *)(a1 + 728),
          v6,
          a1 + 2524,
          a1 + 2528,
          a1 + 1824,
          a1 + 2440,
          a1 + 2464,
          a1 + 32);
  LODWORD(v5) = v12;
  if ( v12 < 0 )
  {
    if ( v12 == -1073741130 || v12 == -1073741801 )
    {
      WdLogSingleEntry5(
        4,
        v12,
        a1,
        *(unsigned int *)(a1 + 784),
        *(unsigned int *)(a1 + 796),
        *(unsigned int *)(a1 + 800));
      WdLogGlobalForLineNumber = 4933;
      v14 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v14[3] = gCddImageInfo;
      v14[4] = (unsigned int)dword_14003E570;
      v14[5] = 215857758;
      WdLogGlobalForLineNumber = 4933;
    }
    else
    {
      WdLogSingleEntry5(
        2,
        v12,
        a1,
        *(unsigned int *)(a1 + 784),
        *(unsigned int *)(a1 + 796),
        *(unsigned int *)(a1 + 800));
      WdLogGlobalForLineNumber = 4928;
      v13 = (_QWORD *)WdLogNewEntry5_WdError();
      v13[3] = gCddImageInfo;
      v13[4] = (unsigned int)dword_14003E570;
      v13[5] = 215857758;
      WdLogGlobalForLineNumber = 4928;
    }
LABEL_10:
    if ( !*v6 )
      goto LABEL_12;
    goto LABEL_11;
  }
  *(_DWORD *)(a1 + 2744) &= ~0x400u;
  if ( !*(_BYTE *)(a1 + 12716) )
    goto LABEL_10;
  ResidencyState = CDDPDEV::CreateResidencyState((CDDPDEV *)a1);
  LODWORD(v5) = ResidencyState;
  if ( ResidencyState >= 0 )
    goto LABEL_10;
  WdLogSingleEntry1(2, ResidencyState);
  WdLogGlobalForLineNumber = 4950;
  v26 = (_QWORD *)WdLogNewEntry5_WdError();
  v26[3] = gCddImageInfo;
  v26[4] = (unsigned int)dword_14003E570;
  v26[5] = 215857758;
  WdLogGlobalForLineNumber = 4950;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140021d5c  push    rbx
0x140021d5e  push    rbp
0x140021d5f  push    rsi
0x140021d60  push    rdi
0x140021d61  push    r12
0x140021d63  push    r14
0x140021d65  push    r15
0x140021d67  sub     rsp, 60h
0x140021d6b  xor     edi, edi
0x140021d6d  lea     rsi, [rcx+9D8h]
0x140021d74  mov     r14d, r9d
0x140021d77  mov     r15, r8
0x140021d7a  mov     r12, rdx
0x140021d7d  mov     rbx, rcx
0x140021d80  lea     ebp, [rdi+3]
0x140021d83  cmp     dword ptr [rsi], 0
0x140021d86  jnz     loc_140021F20
0x140021d8c  lea     rax, [rbx+20h]
0x140021d90  mov     [rsp+98h+var_50], rax
0x140021d95  lea     rcx, [rbx+9A0h]
0x140021d9c  mov     rax, [rbx+58h]
0x140021da0  lea     rdx, [rbx+988h]
0x140021da7  mov     [rsp+98h+var_58], rcx
0x140021dac  lea     r8, [rbx+720h]
0x140021db3  mov     rcx, [rbx+9B8h]
0x140021dba  lea     r9, [rbx+9E0h]
0x140021dc1  mov     [rsp+98h+var_60], rdx
0x140021dc6  lea     r10, [rbx+9DCh]
0x140021dcd  mov     rdx, [rbx+9C8h]
0x140021dd4  mov     [rsp+98h+var_68], r8
0x140021dd9  mov     r8, [rbx+2D8h]
0x140021de0  mov     [rsp+98h+var_70], r9
0x140021de5  mov     r9, rsi
0x140021de8  mov     [rsp+98h+var_78], r10
0x140021ded  call    _guard_dispatch_icall
0x140021df2  movsxd  rdi, eax
0x140021df5  test    eax, eax
0x140021df7  jns     loc_140021EF7
0x140021dfd  cmp     edi, 0C00002B6h
0x140021e03  jz      short loc_140021E84
0x140021e05  cmp     edi, 0C0000017h
0x140021e0b  jz      short loc_140021E84
0x140021e0d  mov     ecx, [rbx+320h]
0x140021e13  mov     rdx, rdi
0x140021e16  mov     r8d, [rbx+31Ch]
0x140021e1d  mov     r9d, [rbx+310h]
0x140021e24  mov     [rsp+98h+var_70], rcx
0x140021e29  mov     ecx, 2
0x140021e2e  mov     [rsp+98h+var_78], r8
0x140021e33  mov     r8, rbx
0x140021e36  call    cs:__imp_WdLogSingleEntry5
0x140021e3d  nop     dword ptr [rax+rax+00h]
0x140021e42  mov     cs:WdLogGlobalForLineNumber, 1340h
0x140021e4c  call    cs:__imp_WdLogNewEntry5_WdError
0x140021e53  nop     dword ptr [rax+rax+00h]
0x140021e58  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140021e5f  mov     [rax+18h], rcx
0x140021e63  mov     ecx, cs:dword_14003E570
0x140021e69  mov     [rax+20h], rcx
0x140021e6d  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140021e75  mov     cs:WdLogGlobalForLineNumber, 1340h
0x140021e7f  jmp     loc_140021F1B
0x140021e84  mov     ecx, [rbx+31Ch]
0x140021e8a  mov     rdx, rdi
0x140021e8d  mov     eax, [rbx+320h]
0x140021e93  mov     r8, rbx
0x140021e96  mov     r9d, [rbx+310h]
0x140021e9d  mov     [rsp+98h+var_70], rax
0x140021ea2  mov     [rsp+98h+var_78], rcx
0x140021ea7  mov     ecx, 4
0x140021eac  call    cs:__imp_WdLogSingleEntry5
0x140021eb3  nop     dword ptr [rax+rax+00h]
0x140021eb8  mov     cs:WdLogGlobalForLineNumber, 1345h
0x140021ec2  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140021ec9  nop     dword ptr [rax+rax+00h]
0x140021ece  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140021ed5  mov     [rax+18h], rcx
0x140021ed9  mov     ecx, cs:dword_14003E570
0x140021edf  mov     [rax+20h], rcx
0x140021ee3  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140021eeb  mov     cs:WdLogGlobalForLineNumber, 1345h
0x140021ef5  jmp     short loc_140021F1B
0x140021ef7  btr     dword ptr [rbx+0AB8h], 0Ah
0x140021eff  cmp     byte ptr [rbx+31ACh], 0
0x140021f06  jz      short loc_140021F1B
0x140021f08  mov     rcx, rbx; this
0x140021f0b  call    ?CreateResidencyState@CDDPDEV@@QEAAJXZ; CDDPDEV::CreateResidencyState(void)
0x140021f10  movsxd  rdi, eax
0x140021f13  test    eax, eax
0x140021f15  js      loc_1400221FB
0x140021f1b  cmp     dword ptr [rsi], 0
0x140021f1e  jz      short loc_140021F33
0x140021f20  mov     rax, [rbx+110h]
0x140021f27  call    _guard_dispatch_icall
0x140021f2c  mov     [rbx+1560h], rax
0x140021f33  mov     ecx, [rsi]
0x140021f35  test    ecx, ecx
0x140021f37  jz      loc_1400221EB
0x140021f3d  cmp     byte ptr [rbx+0A9Ch], 0
0x140021f44  jz      loc_1400221C6
0x140021f4a  mov     rax, [rbx+68h]
0x140021f4e  lea     rdx, [rbx+448h]
0x140021f55  mov     [rsp+98h+var_60], rdx
0x140021f5a  lea     r9, [rbx+9F0h]
0x140021f61  mov     edx, [rbx+0A94h]
0x140021f67  lea     r8, [rbx+0A00h]
0x140021f6e  mov     [rsp+98h+var_68], r8
0x140021f73  mov     r8, r15
0x140021f76  mov     [rsp+98h+var_70], r9
0x140021f7b  mov     r9d, [rbx+310h]
0x140021f82  mov     [rsp+98h+var_78], r12
0x140021f87  call    _guard_dispatch_icall
0x140021f8c  movsxd  rdi, eax
0x140021f8f  test    eax, eax
0x140021f91  js      short loc_140021FE8
0x140021f93  mov     rcx, rbx; StartContext
0x140021f96  call    ?BootAnimationRelayThreadStartup@@YAJPEAUCDDPDEV@@@Z; BootAnimationRelayThreadStartup(CDDPDEV *)
0x140021f9b  mov     rax, [rbx+0B8h]
0x140021fa2  lea     r8, [rbx+314h]
0x140021fa9  mov     edx, [rbx+310h]
0x140021faf  mov     rcx, [rbx+9B8h]
0x140021fb6  mov     byte ptr [rbx+0A9Ah], 0
0x140021fbd  mov     byte ptr [rbx+0A9Dh], 0
0x140021fc4  call    _guard_dispatch_icall
0x140021fc9  inc     dword ptr [rbx+0A64h]
0x140021fcf  mov     dword ptr [rbx+0A6Ch], 1
0x140021fd9  mov     dword ptr [rbx+0A68h], 0
0x140021fe3  jmp     loc_1400221EB
0x140021fe8  lea     eax, [rdi+3FE1FCFAh]
0x140021fee  cmp     eax, 32h ; '2'
0x140021ff1  ja      short loc_140022007
0x140021ff3  mov     rcx, 4200000000001h
0x140021ffd  bt      rcx, rax
0x140022001  jb      loc_140022118
0x140022007  cmp     edi, 0C00002B6h
0x14002200d  jz      loc_140022118
0x140022013  cmp     edi, 0C01E035Ah
0x140022019  jz      loc_140022118
0x14002201f  cmp     edi, 0C0000017h
0x140022025  jz      short loc_1400220A5
0x140022027  cmp     edi, 0C01E0100h
0x14002202d  jz      short loc_1400220A5
0x14002202f  mov     ecx, [rbx+31Ch]
0x140022035  mov     rdx, rdi
0x140022038  mov     eax, [rbx+320h]
0x14002203e  mov     r8, rbx
0x140022041  mov     r9d, [rbx+310h]
0x140022048  mov     [rsp+98h+var_70], rax
0x14002204d  mov     [rsp+98h+var_78], rcx
0x140022052  mov     ecx, 4
0x140022057  call    cs:__imp_WdLogSingleEntry5
0x14002205e  nop     dword ptr [rax+rax+00h]
0x140022063  mov     cs:WdLogGlobalForLineNumber, 139Bh
0x14002206d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140022074  nop     dword ptr [rax+rax+00h]
0x140022079  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140022080  mov     [rax+18h], rcx
0x140022084  mov     ecx, cs:dword_14003E570
0x14002208a  mov     [rax+20h], rcx
0x14002208e  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140022096  mov     cs:WdLogGlobalForLineNumber, 139Bh
0x1400220a0  jmp     loc_140022189
0x1400220a5  mov     ecx, [rbx+31Ch]
0x1400220ab  mov     rdx, rdi
0x1400220ae  mov     eax, [rbx+320h]
0x1400220b4  mov     r8, rbx
0x1400220b7  mov     r9d, [rbx+310h]
0x1400220be  mov     [rsp+98h+var_70], rax
0x1400220c3  mov     [rsp+98h+var_78], rcx
0x1400220c8  mov     ecx, 6
0x1400220cd  call    cs:__imp_WdLogSingleEntry5
0x1400220d4  nop     dword ptr [rax+rax+00h]
0x1400220d9  mov     cs:WdLogGlobalForLineNumber, 1396h
0x1400220e3  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x1400220ea  nop     dword ptr [rax+rax+00h]
0x1400220ef  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400220f6  mov     [rax+18h], rcx
0x1400220fa  mov     ecx, cs:dword_14003E570
0x140022100  mov     [rax+20h], rcx
0x140022104  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002210c  mov     cs:WdLogGlobalForLineNumber, 1396h
0x140022116  jmp     short loc_140022189
0x140022118  mov     ecx, [rbx+31Ch]
0x14002211e  mov     rdx, rdi
0x140022121  mov     eax, [rbx+320h]
0x140022127  mov     r8, rbx
0x14002212a  mov     r9d, [rbx+310h]
0x140022131  mov     [rsp+98h+var_70], rax
0x140022136  mov     [rsp+98h+var_78], rcx
0x14002213b  mov     ecx, 4
0x140022140  call    cs:__imp_WdLogSingleEntry5
0x140022147  nop     dword ptr [rax+rax+00h]
0x14002214c  mov     cs:WdLogGlobalForLineNumber, 1390h
0x140022156  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14002215d  nop     dword ptr [rax+rax+00h]
0x140022162  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140022169  mov     [rax+18h], rcx
0x14002216d  mov     ecx, cs:dword_14003E570
0x140022173  mov     [rax+20h], rcx
0x140022177  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002217f  mov     cs:WdLogGlobalForLineNumber, 1390h
0x140022189  mov     edx, edi; int
0x14002218b  mov     rcx, rbx; this
0x14002218e  call    ?CheckDeviceRemoved@CDDPDEV@@QEAAXJ@Z; CDDPDEV::CheckDeviceRemoved(long)
0x140022193  test    dword ptr [rbx+0AB8h], 400h
0x14002219d  jz      short loc_1400221AE
0x14002219f  mov     edx, [rsp+98h+arg_20]
0x1400221a6  mov     rcx, rbx
0x1400221a9  call    ?DestroyDevice@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z; CDDPDEV::DestroyDevice(_WORKERTHREAD_COMMAND)
0x1400221ae  inc     dword ptr [rbx+0A60h]
0x1400221b4  inc     dword ptr [rbx+0A68h]
0x1400221ba  mov     dword ptr [rbx+0A6Ch], 64h ; 'd'
0x1400221c4  jmp     short loc_1400221EB
0x1400221c6  test    r14d, r14d
0x1400221c9  jz      short loc_1400221EB
0x1400221cb  mov     rax, [rbx+0B8h]
0x1400221d2  lea     r8, [rbx+314h]
0x1400221d9  mov     edx, [rbx+310h]
0x1400221df  mov     rcx, [rbx+9B8h]
0x1400221e6  call    _guard_dispatch_icall
0x1400221eb  test    ebp, ebp
0x1400221ed  jz      short loc_140022249
0x1400221ef  cmp     dword ptr [rsi], 0
0x1400221f2  jnz     short loc_140022249
0x1400221f4  dec     ebp
0x1400221f6  jmp     loc_140021D83
0x1400221fb  mov     rdx, rdi
0x1400221fe  mov     ecx, 2
0x140022203  call    cs:__imp_WdLogSingleEntry1
0x14002220a  nop     dword ptr [rax+rax+00h]
0x14002220f  mov     ebx, 1356h
0x140022214  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002221a  call    cs:__imp_WdLogNewEntry5_WdError
0x140022221  nop     dword ptr [rax+rax+00h]
0x140022226  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002222d  mov     [rax+18h], rcx
0x140022231  mov     ecx, cs:dword_14003E570
0x140022237  mov     [rax+20h], rcx
0x14002223b  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140022243  mov     cs:WdLogGlobalForLineNumber, ebx
0x140022249  mov     eax, edi
0x14002224b  add     rsp, 60h
0x14002224f  pop     r15
0x140022251  pop     r14
0x140022253  pop     r12
0x140022255  pop     rdi
0x140022256  pop     rsi
0x140022257  pop     rbp
0x140022258  pop     rbx
0x140022259  retn
```
