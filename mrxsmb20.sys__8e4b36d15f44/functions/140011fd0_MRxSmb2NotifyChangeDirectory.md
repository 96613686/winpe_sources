# MRxSmb2NotifyChangeDirectory

- ea: `0x140011fd0`
- end: `0x1400121fb`
- name: `MRxSmb2NotifyChangeDirectory`
- size: `555`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x140011fd0`
- `0x140012210`
- `0x140022700`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400120fb`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400120fb`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012081`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012081`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012091`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012091`
- `mrxsmb!MRxSmbDeviceObject` at `0x140012129`
- `mrxsmb!SmbCeInitiateExchange` at `0x14001216e`
- `mrxsmb!SmbCeInitiateExchange` at `0x14001216e`
- `mrxsmb!SmbCeInitializeExchange` at `0x140012032`
- `mrxsmb!SmbCeInitializeExchange` at `0x140012032`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140012139`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140012139`

## pseudocode

```c
__int64 __fastcall MRxSmb2NotifyChangeDirectory(__int64 a1)
{
  __int64 v1; // rdx
  int v2; // edi
  __int64 v4; // r13
  __int64 v5; // rax
  __int64 result; // rax
  __int64 v7; // rsi
  __int64 v8; // rbp
  KIRQL v9; // r15
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 FirstBindingObject; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 72);
  v2 = 0;
  v20 = 0;
  v4 = *(_QWORD *)(*(_QWORD *)(v1 + 40) + 40LL);
  v5 = *(_QWORD *)(v1 + 48);
  *(_DWORD *)(v1 + 72) |= 0x1000u;
  *(_DWORD *)(v5 + 8) |= 0x80u;
  v20 = 0;
  result = SmbCeInitializeExchange(&v20, a1, 0, 0, 0, v4, 2544, &ChangeNotifyDispatch);
  if ( !(_DWORD)result )
  {
    _InterlockedOr((volatile signed __int32 *)(v20 + 68), 0x2040u);
    v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
    v8 = *(_QWORD *)(v7 + 24);
    v9 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920));
    *(_DWORD *)(v8 + 2352) = (unsigned int)PsGetCurrentThreadId();
    if ( !*(_DWORD *)(v7 + 12)
      && ((FirstBindingObject = SmbCeGetFirstBindingObjectEx(*(_QWORD *)(v7 + 416), v10, v11, v12)) != 0
       && (v17 = *(_QWORD *)(FirstBindingObject + 392)) != 0
       || (v19 = SmbCeGetFirstBindingObjectEx(*(_QWORD *)(*(_QWORD *)(v7 + 416) + 384LL), v14, v15, v16)) != 0
       && (v17 = *(_QWORD *)(v19 + 392)) != 0) )
    {
      v18 = *(_QWORD *)(v17 + 280);
      if ( v18 >= 0xC738 )
      {
        v2 = 60;
        if ( v18 < 0x31128 )
          v2 = 30;
      }
      else
      {
        v2 = 10;
      }
    }
    *(_DWORD *)(v8 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920), v9);
    *(_DWORD *)(v20 + 2536) = v2;
    if ( *(_QWORD *)(a1 + 80) == MRxSmbDeviceObject
      && *(_BYTE *)(MRxSmbGetConfigurationBlock(MRxSmbDeviceObject) + 231)
      && (*(_DWORD *)(*(_QWORD *)(a1 + 56) + 164LL) & 1) == 0
      && (~*(_BYTE *)(a1 + 540) & 0x17) == 0 )
    {
      Smb2UpdateDirInfoCacheLifeTime(a1, *(_QWORD *)(v4 + 424) + 1112LL, (unsigned int)(60 * v2));
      *(_BYTE *)(v20 + 2540) = 1;
    }
    return SmbCeInitiateExchange(v20);
  }
  return result;
}

```

## disassembly

```asm
0x140011fd0  push    rbx
0x140011fd2  push    rdi
0x140011fd3  push    r13
0x140011fd5  sub     rsp, 50h
0x140011fd9  mov     rdx, [rcx+48h]
0x140011fdd  xor     edi, edi
0x140011fdf  mov     [rsp+68h+arg_0], rdi
0x140011fe4  mov     rbx, rcx
0x140011fe7  xor     r9d, r9d
0x140011fea  xor     r8d, r8d
0x140011fed  mov     rax, [rdx+28h]
0x140011ff1  mov     r13, [rax+28h]
0x140011ff5  mov     rax, [rdx+30h]
0x140011ff9  or      dword ptr [rdx+48h], 1000h
0x140012000  mov     rdx, rcx
0x140012003  lea     rcx, [rsp+68h+arg_0]
0x140012008  or      dword ptr [rax+8], 80h
0x14001200f  lea     rax, ChangeNotifyDispatch
0x140012016  mov     [rsp+68h+var_30], rax
0x14001201b  mov     [rsp+68h+var_38], 9F0h
0x140012023  mov     [rsp+68h+var_40], r13
0x140012028  mov     [rsp+68h+var_48], rdi
0x14001202d  mov     [rsp+68h+arg_0], rdi
0x140012032  call    cs:__imp_SmbCeInitializeExchange
0x140012039  nop     dword ptr [rax+rax+00h]
0x14001203e  test    eax, eax
0x140012040  jnz     loc_14001217A
0x140012046  mov     rax, [rsp+68h+arg_0]
0x14001204b  mov     [rsp+68h+arg_8], rbp
0x140012050  mov     [rsp+68h+arg_10], rsi
0x140012058  mov     [rsp+68h+var_20], r14
0x14001205d  mov     [rsp+68h+var_28], r15
0x140012062  lock or dword ptr [rax+44h], 2040h
0x14001206a  mov     rax, [rbx+48h]
0x14001206e  mov     rcx, [rax+28h]
0x140012072  mov     rsi, [rcx+28h]
0x140012076  mov     rbp, [rsi+18h]
0x14001207a  lea     rcx, [rbp+780h]; SpinLock
0x140012081  call    cs:__imp_ExAcquireSpinLockExclusive
0x140012088  nop     dword ptr [rax+rax+00h]
0x14001208d  movzx   r15d, al
0x140012091  call    cs:__imp_PsGetCurrentThreadId
0x140012098  nop     dword ptr [rax+rax+00h]
0x14001209d  mov     [rbp+930h], eax
0x1400120a3  cmp     [rsi+0Ch], edi
0x1400120a6  jnz     short loc_1400120E6
0x1400120a8  mov     rcx, [rsi+1A0h]
0x1400120af  call    SmbCeGetFirstBindingObjectEx
0x1400120b4  test    rax, rax
0x1400120b7  jz      loc_1400121B2
0x1400120bd  mov     rax, [rax+188h]
0x1400120c4  test    rax, rax
0x1400120c7  jz      loc_1400121B2
0x1400120cd  mov     rcx, [rax+118h]
0x1400120d4  cmp     rcx, 0C738h
0x1400120db  jnb     loc_140012184
0x1400120e1  mov     edi, 0Ah
0x1400120e6  movzx   edx, r15b; OldIrql
0x1400120ea  mov     dword ptr [rbp+930h], 0FFFFFFFFh
0x1400120f4  lea     rcx, [rbp+780h]; SpinLock
0x1400120fb  call    cs:__imp_ExReleaseSpinLockExclusive
0x140012102  nop     dword ptr [rax+rax+00h]
0x140012107  mov     rax, [rsp+68h+arg_0]
0x14001210c  mov     r15, [rsp+68h+var_28]
0x140012111  mov     r14, [rsp+68h+var_20]
0x140012116  mov     rsi, [rsp+68h+arg_10]
0x14001211e  mov     rbp, [rsp+68h+arg_8]
0x140012123  mov     [rax+9E8h], edi
0x140012129  mov     rax, cs:__imp_MRxSmbDeviceObject
0x140012130  mov     rcx, [rax]
0x140012133  cmp     [rbx+50h], rcx
0x140012137  jnz     short loc_140012169
0x140012139  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140012140  nop     dword ptr [rax+rax+00h]
0x140012145  cmp     byte ptr [rax+0E7h], 0
0x14001214c  jz      short loc_140012169
0x14001214e  mov     rax, [rbx+38h]
0x140012152  mov     ecx, [rax+0A4h]
0x140012158  test    cl, 1
0x14001215b  jnz     short loc_140012169
0x14001215d  mov     eax, [rbx+21Ch]
0x140012163  not     eax
0x140012165  test    al, 17h
0x140012167  jz      short loc_1400121D0
0x140012169  mov     rcx, [rsp+68h+arg_0]
0x14001216e  call    cs:__imp_SmbCeInitiateExchange
0x140012175  nop     dword ptr [rax+rax+00h]
0x14001217a  add     rsp, 50h
0x14001217e  pop     r13
0x140012180  pop     rdi
0x140012181  pop     rbx
0x140012182  retn
0x140012184  cmp     rcx, 31128h
0x14001218b  mov     edi, 3Ch ; '<'
0x140012190  mov     eax, 1Eh
0x140012195  cmovb   edi, eax
0x140012198  jmp     loc_1400120E6
0x14001219d  mov     rax, [rax+188h]
0x1400121a4  test    rax, rax
0x1400121a7  jz      loc_1400120E6
0x1400121ad  jmp     loc_1400120CD
0x1400121b2  mov     rcx, [rsi+1A0h]
0x1400121b9  mov     rcx, [rcx+180h]
0x1400121c0  call    SmbCeGetFirstBindingObjectEx
0x1400121c5  test    rax, rax
0x1400121c8  jz      loc_1400120E6
0x1400121ce  jmp     short loc_14001219D
0x1400121d0  mov     rdx, [r13+1A8h]
0x1400121d7  mov     rcx, rbx
0x1400121da  imul    r8d, edi, 3Ch ; '<'
0x1400121de  add     rdx, 458h
0x1400121e5  call    Smb2UpdateDirInfoCacheLifeTime
0x1400121ea  mov     rax, [rsp+68h+arg_0]
0x1400121ef  mov     byte ptr [rax+9ECh], 1
0x1400121f6  jmp     loc_140012169
```
