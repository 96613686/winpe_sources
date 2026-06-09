# MRxSmb2WaitForMultichannelSetup

- ea: `0x140051788`
- end: `0x140051aee`
- name: `MRxSmb2WaitForMultichannelSetup`
- size: `870`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x14001cc00`

## callees

- `0x1400122d0`
- `0x140029764`
- `0x14002a9ac`
- `0x14002bb3c`
- `0x14002bc00`
- `0x14002bcdc`
- `0x140051788`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140051861`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400518da`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140051acd`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140051861`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400518da`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140051acd`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400519f0`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400519f0`
- `mrxsmb!SmbCeEstablishMultipleConnections` at `0x1400518e9`
- `mrxsmb!SmbCeEstablishMultipleConnections` at `0x1400518e9`
- `mrxsmb!SmbCeReferenceSessionEntry` at `0x1400518be`
- `mrxsmb!SmbCeReferenceSessionEntry` at `0x1400518be`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051954`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051968`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051986`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14005199a`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051954`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051968`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140051986`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14005199a`

## pseudocode

```c
__int64 __fastcall MRxSmb2WaitForMultichannelSetup(__int64 a1, __int64 a2)
{
  unsigned int v3; // r14d
  __int64 v4; // r9
  __int64 v5; // r8
  __int64 v6; // r10
  __int64 v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rdi
  KIRQL v10; // bp
  int v11; // edx
  unsigned int v12; // r15d
  __int64 v14; // rdx
  __int64 v15; // r8
  PDEVICE_OBJECT v16; // rcx
  unsigned int v17; // ebx
  __int64 v18; // rcx
  unsigned int v19; // ebx
  __int64 v20; // rcx
  int v21; // ebx
  int v22; // edi
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF

  v3 = *(_DWORD *)(a2 + 8);
  v4 = a1;
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL);
  v6 = *(_QWORD *)(v5 + 40);
  v7 = *(_QWORD *)(v6 + 416);
  v8 = *(_QWORD *)(v7 + 384);
  v9 = *(_QWORD *)(v8 + 24);
  Interval.QuadPart = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqq(WPP_GLOBAL_Control->AttachedDevice, a2, v5, a1, v6, v7, v8);
  }
  v10 = SmbCeAcquireSpinLock(v9, a2, v5, v4);
  if ( !*(_QWORD *)(v8 + 576) || (*(_BYTE *)(v7 + 4) & 3) != 0 )
  {
    v12 = -1073741637;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qll(WPP_GLOBAL_Control->AttachedDevice);
    }
    *(_DWORD *)(v9 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 1920), v10);
  }
  else
  {
    v11 = *(_DWORD *)(v7 + 4);
    v12 = 0;
    if ( (v11 & 8) != 0 || (*(_BYTE *)(*(_QWORD *)(v7 + 384) + 764LL) & 0x40) != 0 )
    {
      *(_DWORD *)(v9 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 1920), v10);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_ll(
          WPP_GLOBAL_Control->AttachedDevice,
          v14,
          v15,
          (*(_DWORD *)(v7 + 4) >> 3) & 1,
          (*(unsigned __int8 *)(v8 + 764) >> 6) & 1);
      }
    }
    else
    {
      *(_DWORD *)(v7 + 4) = v11 | 8;
      SmbCeReferenceSessionEntry(v7);
      *(_DWORD *)(v9 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 1920), v10);
      SmbCeEstablishMultipleConnections(v7);
    }
    if ( v3 <= 1 )
    {
      v17 = *(_DWORD *)(a2 + 4);
      Interval.QuadPart = -150000;
      if ( v17 >= *(_DWORD *)(MRxSmbGetConfigurationBlock(v16) + 512) )
        v17 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v18) + 512);
      if ( !v17 )
        goto LABEL_40;
      v19 = *(_DWORD *)(a2 + 4);
      if ( v19 >= *(_DWORD *)(MRxSmbGetConfigurationBlock(v18) + 512) )
        v19 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v20) + 512);
      v21 = (int)(1000 * v19) / 15;
      if ( v21 )
      {
        while ( 1 )
        {
          v22 = v3 == 1 ? *(_DWORD *)(v8 + 612) : *(_DWORD *)(v8 + 608);
          KeDelayExecutionThread(0, 0, &Interval);
          if ( !v22 )
            break;
          if ( --v21 <= 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids);
            }
            return (unsigned int)-1073740675;
          }
        }
      }
      else
      {
LABEL_40:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids, v3);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140051788  mov     r11, rsp
0x14005178b  push    rbx
0x14005178c  push    rbp
0x14005178d  push    rsi
0x14005178e  push    rdi
0x14005178f  push    r12
0x140051791  push    r13
0x140051793  push    r14
0x140051795  push    r15
0x140051797  sub     rsp, 48h
0x14005179b  mov     rax, [rcx+48h]
0x14005179f  mov     r13, rdx
0x1400517a2  mov     r14d, [rdx+8]
0x1400517a6  mov     r9, rcx
0x1400517a9  mov     r8, [rax+28h]
0x1400517ad  mov     r10, [r8+28h]
0x1400517b1  mov     rbx, [r10+1A0h]
0x1400517b8  mov     rsi, [rbx+180h]
0x1400517bf  mov     rdi, [rsi+18h]
0x1400517c3  mov     qword ptr [r11+8], 0
0x1400517cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400517d2  lea     r12, WPP_GLOBAL_Control
0x1400517d9  cmp     rcx, r12
0x1400517dc  jz      short loc_140051800
0x1400517de  mov     eax, [rcx+2Ch]
0x1400517e1  test    al, 2
0x1400517e3  jz      short loc_140051800
0x1400517e5  cmp     byte ptr [rcx+29h], 4
0x1400517e9  jb      short loc_140051800
0x1400517eb  mov     rcx, [rcx+18h]
0x1400517ef  mov     [r11-58h], rsi
0x1400517f3  mov     [r11-60h], rbx
0x1400517f7  mov     [r11-68h], r10
0x1400517fb  call    WPP_SF_qqqq
0x140051800  mov     rcx, rdi
0x140051803  call    SmbCeAcquireSpinLock
0x140051808  mov     r9, [rsi+240h]
0x14005180f  mov     bpl, al
0x140051812  test    r9, r9
0x140051815  jz      loc_140051A77
0x14005181b  test    byte ptr [rbx+4], 3
0x14005181f  jnz     loc_140051A77
0x140051825  mov     edx, [rbx+4]
0x140051828  xor     r15d, r15d
0x14005182b  test    dl, 8
0x14005182e  jnz     short loc_140051844
0x140051830  mov     rax, [rbx+180h]
0x140051837  test    byte ptr [rax+2FCh], 40h
0x14005183e  jnz     short loc_140051844
0x140051840  xor     al, al
0x140051842  jmp     short loc_140051846
0x140051844  mov     al, 1
0x140051846  lea     r12, [rdi+780h]
0x14005184d  test    al, al
0x14005184f  jz      short loc_1400518B5
0x140051851  mov     dl, bpl; OldIrql
0x140051854  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x14005185e  mov     rcx, r12; SpinLock
0x140051861  call    cs:__imp_ExReleaseSpinLockExclusive
0x140051868  nop     dword ptr [rax+rax+00h]
0x14005186d  mov     rcx, cs:WPP_GLOBAL_Control
0x140051874  lea     rbp, WPP_GLOBAL_Control
0x14005187b  cmp     rcx, rbp
0x14005187e  jz      short loc_1400518FC
0x140051880  mov     eax, [rcx+2Ch]
0x140051883  test    al, 2
0x140051885  jz      short loc_1400518FC
0x140051887  cmp     byte ptr [rcx+29h], 4
0x14005188b  jb      short loc_1400518FC
0x14005188d  movzx   eax, byte ptr [rsi+2FCh]
0x140051894  mov     r9d, [rbx+4]
0x140051898  mov     rcx, [rcx+18h]
0x14005189c  shr     eax, 6
0x14005189f  shr     r9d, 3
0x1400518a3  and     eax, 1
0x1400518a6  and     r9d, 1
0x1400518aa  mov     [rsp+88h+var_68], eax
0x1400518ae  call    WPP_SF_ll
0x1400518b3  jmp     short loc_1400518FC
0x1400518b5  or      edx, 8
0x1400518b8  mov     rcx, rbx
0x1400518bb  mov     [rbx+4], edx
0x1400518be  call    cs:__imp_SmbCeReferenceSessionEntry
0x1400518c5  nop     dword ptr [rax+rax+00h]
0x1400518ca  mov     dl, bpl; OldIrql
0x1400518cd  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x1400518d7  mov     rcx, r12; SpinLock
0x1400518da  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400518e1  nop     dword ptr [rax+rax+00h]
0x1400518e6  mov     rcx, rbx
0x1400518e9  call    cs:__imp_SmbCeEstablishMultipleConnections
0x1400518f0  nop     dword ptr [rax+rax+00h]
0x1400518f5  lea     rbp, WPP_GLOBAL_Control
0x1400518fc  cmp     r14d, 1
0x140051900  jbe     short loc_140051944
0x140051902  mov     rcx, cs:WPP_GLOBAL_Control
0x140051909  cmp     rcx, rbp
0x14005190c  jz      loc_140051AD9
0x140051912  mov     eax, [rcx+2Ch]
0x140051915  test    al, 2
0x140051917  jz      loc_140051AD9
0x14005191d  cmp     byte ptr [rcx+29h], 4
0x140051921  jb      loc_140051AD9
0x140051927  mov     rcx, [rcx+18h]
0x14005192b  lea     r8, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids
0x140051932  mov     edx, 19h
0x140051937  mov     r9d, r14d
0x14005193a  call    WPP_SF_d
0x14005193f  jmp     loc_140051AD9
0x140051944  mov     ebx, [r13+4]
0x140051948  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFFFFDB610h
0x140051954  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14005195b  nop     dword ptr [rax+rax+00h]
0x140051960  cmp     ebx, [rax+200h]
0x140051966  jb      short loc_14005197A
0x140051968  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14005196f  nop     dword ptr [rax+rax+00h]
0x140051974  mov     ebx, [rax+200h]
0x14005197a  test    ebx, ebx
0x14005197c  jz      loc_140051A43
0x140051982  mov     ebx, [r13+4]
0x140051986  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14005198d  nop     dword ptr [rax+rax+00h]
0x140051992  cmp     ebx, [rax+200h]
0x140051998  jb      short loc_1400519AC
0x14005199a  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400519a1  nop     dword ptr [rax+rax+00h]
0x1400519a6  mov     ebx, [rax+200h]
0x1400519ac  imul    ecx, ebx, 3E8h
0x1400519b2  mov     eax, 88888889h
0x1400519b7  imul    ecx
0x1400519b9  lea     ebx, [rcx+rdx]
0x1400519bc  sar     ebx, 3
0x1400519bf  mov     eax, ebx
0x1400519c1  shr     eax, 1Fh
0x1400519c4  add     ebx, eax
0x1400519c6  jz      short loc_140051A43
0x1400519c8  xor     edi, edi
0x1400519ca  cmp     r14d, 1
0x1400519ce  jnz     short loc_1400519D8
0x1400519d0  mov     edi, [rsi+264h]
0x1400519d6  jmp     short loc_1400519E3
0x1400519d8  test    r14d, r14d
0x1400519db  jnz     short loc_1400519E4
0x1400519dd  mov     edi, [rsi+260h]
0x1400519e3  nop
0x1400519e4  lea     r8, [rsp+88h+Interval]; Interval
0x1400519ec  xor     edx, edx; Alertable
0x1400519ee  xor     ecx, ecx; WaitMode
0x1400519f0  call    cs:__imp_KeDelayExecutionThread
0x1400519f7  nop     dword ptr [rax+rax+00h]
0x1400519fc  test    edi, edi
0x1400519fe  jz      loc_140051AD9
0x140051a04  dec     ebx
0x140051a06  test    ebx, ebx
0x140051a08  jg      short loc_1400519CA
0x140051a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a11  cmp     rcx, rbp
0x140051a14  jz      short loc_140051A38
0x140051a16  mov     eax, [rcx+2Ch]
0x140051a19  test    al, 2
0x140051a1b  jz      short loc_140051A38
0x140051a1d  cmp     byte ptr [rcx+29h], 4
0x140051a21  jb      short loc_140051A38
0x140051a23  mov     rcx, [rcx+18h]
0x140051a27  lea     r8, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids
0x140051a2e  mov     edx, 1Bh
0x140051a33  call    WPP_SF_
0x140051a38  mov     r15d, 0C000047Dh
0x140051a3e  jmp     loc_140051AD9
0x140051a43  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a4a  cmp     rcx, rbp
0x140051a4d  jz      loc_140051AD9
0x140051a53  mov     eax, [rcx+2Ch]
0x140051a56  test    al, 2
0x140051a58  jz      short loc_140051AD9
0x140051a5a  cmp     byte ptr [rcx+29h], 4
0x140051a5e  jb      short loc_140051AD9
0x140051a60  mov     rcx, [rcx+18h]
0x140051a64  lea     r8, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids
0x140051a6b  mov     edx, 1Ah
0x140051a70  call    WPP_SF_
0x140051a75  jmp     short loc_140051AD9
0x140051a77  mov     r15d, 0C00000BBh
0x140051a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a84  cmp     rcx, r12
0x140051a87  jz      short loc_140051AB9
0x140051a89  mov     eax, [rcx+2Ch]
0x140051a8c  test    al, 2
0x140051a8e  jz      short loc_140051AB9
0x140051a90  cmp     byte ptr [rcx+29h], 4
0x140051a94  jb      short loc_140051AB9
0x140051a96  mov     r8d, [rbx+4]
0x140051a9a  mov     edx, r8d
0x140051a9d  mov     rcx, [rcx+18h]
0x140051aa1  and     edx, 1
0x140051aa4  shr     r8d, 1
0x140051aa7  and     r8d, 1
0x140051aab  mov     [rsp+88h+var_60], edx
0x140051aaf  mov     [rsp+88h+var_68], r8d
0x140051ab4  call    WPP_SF_qll
0x140051ab9  lea     rcx, [rdi+780h]; SpinLock
0x140051ac0  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x140051aca  mov     dl, bpl; OldIrql
0x140051acd  call    cs:__imp_ExReleaseSpinLockExclusive
0x140051ad4  nop     dword ptr [rax+rax+00h]
0x140051ad9  mov     eax, r15d
0x140051adc  add     rsp, 48h
0x140051ae0  pop     r15
0x140051ae2  pop     r14
0x140051ae4  pop     r13
0x140051ae6  pop     r12
0x140051ae8  pop     rdi
0x140051ae9  pop     rsi
0x140051aea  pop     rbp
0x140051aeb  pop     rbx
0x140051aec  retn
```
