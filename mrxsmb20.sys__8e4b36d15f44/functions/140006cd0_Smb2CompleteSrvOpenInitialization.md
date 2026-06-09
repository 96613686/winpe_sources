# Smb2CompleteSrvOpenInitialization

- ea: `0x140006cd0`
- end: `0x140007013`
- name: `Smb2CompleteSrvOpenInitialization`
- size: `835`
- prototype: `__int64 __fastcall(__int64, char, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005820`
- `0x140007020`

## callees

- `0x140006cd0`
- `0x14000bd50`
- `0x140033e00`
- `0x1400345cc`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140006dd8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140006dd8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140006d34`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140006fc3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140006d34`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140006fc3`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140006e4c`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140006f13`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140006e4c`
- `mrxsmb!SmbCeSetConnectionKeepalive` at `0x140006f13`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140006e35`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140006e35`

## pseudocode

```c
__int64 __fastcall Smb2CompleteSrvOpenInitialization(__int64 a1, char a2, __int64 a3)
{
  __int64 v3; // rdi
  int v4; // ebx
  int *v6; // r12
  int v8; // r14d
  __int64 v9; // rsi
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // ecx
  __int64 v13; // r8
  __int64 v15; // rcx
  __int64 v16; // r15
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // eax
  __int64 v21; // rdx
  int *v22; // rdx
  char v23; // [rsp+F4h] [rbp+1Ch]

  v23 = BYTE4(a3);
  v3 = *(_QWORD *)(a1 + 48);
  v4 = a3;
  v6 = (int *)"Deferred";
  v8 = *(_DWORD *)(v3 + 4);
  if ( (int)a3 >= 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v22 = (int *)"Deferred";
    if ( !a2 )
      v22 = &dword_14003ECEC;
    WPP_SF_qsZ(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v22, a3, a1, (__int64)v22, *(_QWORD *)(a1 + 80));
    v9 = v3 + 16;
    ExAcquirePushLockExclusiveEx(v3 + 16, 0);
    goto LABEL_5;
  }
  v9 = v3 + 16;
  ExAcquirePushLockExclusiveEx(v3 + 16, 0);
  if ( v4 >= 0 )
  {
LABEL_5:
    v12 = *(_DWORD *)(a1 + 72) | 0x100000;
    if ( !a2 )
      v12 = *(_DWORD *)(a1 + 72) & 0xFFEFFFFF;
    *(_DWORD *)(a1 + 72) = v12;
    *(_DWORD *)(v3 + 4) = a2 != 0;
LABEL_8:
    if ( v4 != -1069481983
      && v4 != -1073740672
      && (unsigned int)(v4 + 1073740698) > 1
      && v4 != -1073740964
      && v4 != -1073741073
      && v4 != -1073741202
      && v4 != -1073741267
      && v4 != -1073741507
      && v4 != -1073741623
      && v4 != -1073741667
      && v4 != -1073741810
      && v4 != -2146893022
      && v4 != -2147483631 )
    {
      goto LABEL_15;
    }
    goto LABEL_11;
  }
  *(_DWORD *)(v3 + 4) = 9;
  if ( v4 != -1073741643 )
  {
    if ( v4 == -1073741620
      || v4 == -1073741634
      || v4 == -1073741252
      || v4 == -1073741636
      || v4 == -1073741300
      || v4 == -1073741299
      || v4 == -1073741258 )
    {
      v6 = (int *)"Deferred";
    }
    else if ( v4 != -1073741247 && v4 != -1073741309 )
    {
      goto LABEL_8;
    }
  }
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    if ( !a2 )
      v6 = &dword_14003ECEC;
    WPP_SF_qDsZ(WPP_GLOBAL_Control->AttachedDevice, v10, v11, a1, v4, (__int64)v6, *(_QWORD *)(a1 + 80));
  }
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 120LL);
  if ( (*(_DWORD *)(*(_QWORD *)(v13 + 40) + 176LL) & 0x80u) != 0
    && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
  {
    McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
      **(_WORD **)(a1 + 80) >> 1,
      (unsigned int)HandleOpenFailure,
      *(_QWORD *)(v13 + 88),
      v3,
      *(_QWORD *)(v3 + 28),
      *(_QWORD *)(v3 + 36),
      v3 + 264,
      v8,
      *(_WORD *)(v3 + 4),
      v4,
      v23,
      **(_WORD **)(v13 + 88) >> 1,
      *(_QWORD *)(*(_QWORD *)(v13 + 88) + 8LL),
      **(_WORD **)(a1 + 80) >> 1,
      *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL),
      0,
      0);
  }
LABEL_15:
  if ( v8 == 3 && !*(_DWORD *)(v3 + 4) )
  {
    v15 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 40LL);
    v16 = *(_QWORD *)(v15 + 416);
    v17 = *(_QWORD *)(v16 + 384);
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 432));
    if ( *(_DWORD *)(v16 + 704) )
    {
      v20 = *(_DWORD *)(v17 + 772);
      v21 = 10;
      if ( v20 )
        v21 = v20;
      SmbCeSetConnectionKeepalive(v16, v21, 2);
    }
    else
    {
      v18 = *(unsigned int *)(v17 + 776);
      if ( !(_DWORD)v18 )
        v18 = *(_DWORD *)(MRxSmbGetConfigurationBlock(v15) + 12) >> 1;
      SmbCeSetConnectionKeepalive(v16, v18, 0);
    }
  }
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x400) != 0 )
  {
    v19 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 120LL) + 88LL);
    McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer(
      **(_WORD **)(a1 + 80) >> 1,
      (unsigned int)OpenHandleStateTransition,
      *(_QWORD *)(a1 + 80),
      v3,
      0,
      0,
      v3 + 264,
      v8,
      *(_WORD *)(v3 + 4),
      v4,
      v23,
      *(_WORD *)v19 >> 1,
      *(_QWORD *)(v19 + 8),
      **(_WORD **)(a1 + 80) >> 1,
      *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL),
      0,
      0);
  }
  return ExReleasePushLockExclusiveEx(v9, 0);
}

```

## disassembly

```asm
0x140006cd0  mov     [rsp+arg_10], r8
0x140006cd5  push    rbx
0x140006cd6  push    rbp
0x140006cd7  push    rsi
0x140006cd8  push    rdi
0x140006cd9  push    r12
0x140006cdb  push    r13
0x140006cdd  push    r14
0x140006cdf  push    r15
0x140006ce1  sub     rsp, 98h
0x140006ce8  mov     rdi, [rcx+30h]
0x140006cec  mov     rbx, r8
0x140006cef  lea     r13, dword_14003ECEC
0x140006cf6  movzx   r15d, dl
0x140006cfa  lea     r12, aDeferred; "Deferred"
0x140006d01  mov     rbp, rcx
0x140006d04  lea     rax, WPP_GLOBAL_Control
0x140006d0b  mov     r14d, [rdi+4]
0x140006d0f  test    r8d, r8d
0x140006d12  js      short loc_140006D2B
0x140006d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d1b  cmp     rcx, rax
0x140006d1e  jz      short loc_140006D2B
0x140006d20  mov     eax, [rcx+2Ch]
0x140006d23  test    al, 40h
0x140006d25  jnz     loc_140006F8C
0x140006d2b  lea     rsi, [rdi+10h]
0x140006d2f  xor     edx, edx
0x140006d31  mov     rcx, rsi
0x140006d34  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140006d3b  nop     dword ptr [rax+rax+00h]
0x140006d40  test    ebx, ebx
0x140006d42  js      short loc_140006D73
0x140006d44  mov     ecx, [rbp+48h]
0x140006d47  mov     eax, ecx
0x140006d49  btr     eax, 14h
0x140006d4d  bts     ecx, 14h
0x140006d51  test    r15b, r15b
0x140006d54  cmovz   ecx, eax
0x140006d57  xor     eax, eax
0x140006d59  test    r15b, r15b
0x140006d5c  mov     [rbp+48h], ecx
0x140006d5f  setnz   al
0x140006d62  mov     [rdi+4], eax
0x140006d65  cmp     ebx, 0C0410001h
0x140006d6b  jnz     loc_14003887A
0x140006d71  jmp     short loc_140006D86
0x140006d73  mov     dword ptr [rdi+4], 9
0x140006d7a  cmp     ebx, 0C00000B5h
0x140006d80  jnz     loc_140006F71
0x140006d86  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d8d  lea     rax, WPP_GLOBAL_Control
0x140006d94  cmp     rcx, rax
0x140006d97  jnz     loc_140006FD4
0x140006d9d  mov     rax, [rbp+20h]
0x140006da1  mov     r8, [rax+78h]
0x140006da5  mov     rax, [r8+28h]
0x140006da9  mov     ecx, [rax+0B0h]
0x140006daf  test    cl, cl
0x140006db1  jns     short loc_140006DC0
0x140006db3  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 10h
0x140006dba  jnz     loc_140038912
0x140006dc0  cmp     r14d, 3
0x140006dc4  jz      short loc_140006DF9
0x140006dc6  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 4
0x140006dcd  jnz     loc_140006E5D
0x140006dd3  xor     edx, edx
0x140006dd5  mov     rcx, rsi
0x140006dd8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140006ddf  nop     dword ptr [rax+rax+00h]
0x140006de4  add     rsp, 98h
0x140006deb  pop     r15
0x140006ded  pop     r14
0x140006def  pop     r13
0x140006df1  pop     r12
0x140006df3  pop     rdi
0x140006df4  pop     rsi
0x140006df5  pop     rbp
0x140006df6  pop     rbx
0x140006df7  retn
0x140006df9  cmp     dword ptr [rdi+4], 0
0x140006dfd  jnz     short loc_140006DC6
0x140006dff  mov     rax, [rbp+28h]
0x140006e03  mov     rcx, [rax+28h]
0x140006e07  mov     r15, [rcx+1A0h]
0x140006e0e  mov     rdx, [r15+180h]
0x140006e15  lock inc dword ptr [r15+1B0h]
0x140006e1d  cmp     dword ptr [r15+2C0h], 0
0x140006e25  jnz     loc_140006EFA
0x140006e2b  mov     edx, [rdx+308h]
0x140006e31  test    edx, edx
0x140006e33  jnz     short loc_140006E46
0x140006e35  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140006e3c  nop     dword ptr [rax+rax+00h]
0x140006e41  mov     edx, [rax+0Ch]
0x140006e44  shr     edx, 1
0x140006e46  xor     r8d, r8d
0x140006e49  mov     rcx, r15
0x140006e4c  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140006e53  nop     dword ptr [rax+rax+00h]
0x140006e58  jmp     loc_140006DC6
0x140006e5d  mov     rax, [rbp+20h]
0x140006e61  lea     r10, [rdi+108h]
0x140006e68  mov     r8, [rbp+50h]
0x140006e6c  mov     [rsp+0D8h+var_58], 0
0x140006e77  mov     [rsp+0D8h+var_60], 0
0x140006e7f  mov     rcx, [rax+78h]
0x140006e83  mov     rax, [r8+8]
0x140006e87  mov     [rsp+0D8h+var_68], rax
0x140006e8c  mov     r9, [rcx+58h]
0x140006e90  movzx   ecx, word ptr [r8]
0x140006e94  shr     cx, 1
0x140006e97  mov     [rsp+0D8h+var_70], cx
0x140006e9c  movzx   edx, word ptr [r9]
0x140006ea0  mov     rax, [r9+8]
0x140006ea4  mov     r9, rdi
0x140006ea7  mov     [rsp+0D8h+var_78], rax
0x140006eac  mov     eax, dword ptr [rsp+0D8h+arg_10+4]
0x140006eb3  shr     dx, 1
0x140006eb6  mov     [rsp+0D8h+var_80], dx
0x140006ebb  lea     rdx, OpenHandleStateTransition
0x140006ec2  mov     [rsp+0D8h+var_88], eax
0x140006ec6  movzx   eax, word ptr [rdi+4]
0x140006eca  mov     [rsp+0D8h+var_90], ebx
0x140006ece  mov     [rsp+0D8h+var_98], ax
0x140006ed3  mov     [rsp+0D8h+var_A0], r14w
0x140006ed9  mov     [rsp+0D8h+var_A8], r10
0x140006ede  mov     [rsp+0D8h+var_B0], 0
0x140006ee7  mov     [rsp+0D8h+var_B8], 0
0x140006ef0  call    McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer
0x140006ef5  jmp     loc_140006DD3
0x140006efa  mov     eax, [rdx+304h]
0x140006f00  mov     r8d, 2
0x140006f06  test    eax, eax
0x140006f08  mov     edx, 0Ah
0x140006f0d  mov     rcx, r15
0x140006f10  cmovnz  edx, eax
0x140006f13  call    cs:__imp_SmbCeSetConnectionKeepalive
0x140006f1a  nop     dword ptr [rax+rax+00h]
0x140006f1f  jmp     loc_140006DC6
0x140006f24  cmp     ebx, 0C00000BEh
0x140006f2a  jz      short loc_140006F79
0x140006f2c  cmp     ebx, 0C000023Ch
0x140006f32  jz      short loc_140006F79
0x140006f34  cmp     ebx, 0C00000BCh
0x140006f3a  jz      short loc_140006F79
0x140006f3c  cmp     ebx, 0C000020Ch
0x140006f42  jz      short loc_140006F79
0x140006f44  cmp     ebx, 0C000020Dh
0x140006f4a  jz      short loc_140006F79
0x140006f4c  cmp     ebx, 0C0000236h
0x140006f52  jz      short loc_140006F79
0x140006f54  cmp     ebx, 0C0000241h
0x140006f5a  jz      loc_140006D86
0x140006f60  cmp     ebx, 0C0000203h
0x140006f66  jz      loc_140006D86
0x140006f6c  jmp     loc_140006D65
0x140006f71  cmp     ebx, 0C00000CCh
0x140006f77  jnz     short loc_140006F24
0x140006f79  lea     r13, dword_14003ECEC
0x140006f80  lea     r12, aDeferred; "Deferred"
0x140006f87  jmp     loc_140006D86
0x140006f8c  cmp     byte ptr [rcx+29h], 2
0x140006f90  jb      loc_140006D2B
0x140006f96  mov     rax, [rbp+50h]
0x140006f9a  test    r15b, r15b
0x140006f9d  mov     rcx, [rcx+18h]
0x140006fa1  mov     rdx, r12
0x140006fa4  cmovz   rdx, r13
0x140006fa8  mov     [rsp+0D8h+var_B0], rax
0x140006fad  mov     r9, rbp
0x140006fb0  mov     [rsp+0D8h+var_B8], rdx
0x140006fb5  call    WPP_SF_qsZ
0x140006fba  lea     rsi, [rdi+10h]
0x140006fbe  xor     edx, edx
0x140006fc0  mov     rcx, rsi
0x140006fc3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140006fca  nop     dword ptr [rax+rax+00h]
0x140006fcf  jmp     loc_140006D44
0x140006fd4  mov     eax, [rcx+2Ch]
0x140006fd7  test    al, 1
0x140006fd9  jz      loc_140006D9D
0x140006fdf  cmp     byte ptr [rcx+29h], 1
0x140006fe3  jb      loc_140006D9D
0x140006fe9  mov     rax, [rbp+50h]
0x140006fed  test    r15b, r15b
0x140006ff0  mov     rcx, [rcx+18h]
0x140006ff4  mov     r9, rbp
0x140006ff7  mov     [rsp+0D8h+var_A8], rax
0x140006ffc  cmovz   r12, r13
0x140007000  mov     [rsp+0D8h+var_B0], r12
0x140007005  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x140007009  call    WPP_SF_qDsZ
0x14000700e  jmp     loc_140006D9D
0x14003887a  cmp     ebx, 0C0000480h
0x140038880  jz      loc_140006D86
0x140038886  lea     eax, [rbx+3FFFFB9Ah]
0x14003888c  cmp     eax, 1
0x14003888f  jbe     loc_140006D86
0x140038895  cmp     ebx, 0C000035Ch
0x14003889b  jz      loc_140006D86
0x1400388a1  cmp     ebx, 0C00002EFh
0x1400388a7  jz      loc_140006D86
0x1400388ad  cmp     ebx, 0C000026Eh
0x1400388b3  jz      loc_140006D86
0x1400388b9  cmp     ebx, 0C000022Dh
0x1400388bf  jz      loc_140006D86
0x1400388c5  cmp     ebx, 0C000013Dh
0x1400388cb  jz      loc_140006D86
0x1400388d1  cmp     ebx, 0C00000C9h
0x1400388d7  jz      loc_140006D86
0x1400388dd  cmp     ebx, 0C000009Dh
0x1400388e3  jz      loc_140006D86
0x1400388e9  cmp     ebx, 0C000000Eh
0x1400388ef  jz      loc_140006D86
0x1400388f5  cmp     ebx, 80090322h
0x1400388fb  jz      loc_140006D86
0x140038901  cmp     ebx, 80000011h
0x140038907  jnz     loc_140006DC0
0x14003890d  jmp     loc_140006D86
0x140038912  mov     rax, [rbp+50h]
0x140038916  lea     r9, [rdi+108h]
0x14003891d  mov     r8, [r8+58h]
0x140038921  mov     [rsp+0D8h+var_58], 0
0x14003892c  mov     [rsp+0D8h+var_60], 0
0x140038934  movzx   ecx, word ptr [rax]
0x140038937  mov     rax, [rax+8]
0x14003893b  movzx   edx, word ptr [r8]
0x14003893f  mov     [rsp+0D8h+var_68], rax
0x140038944  mov     rax, [r8+8]
0x140038948  shr     dx, 1
0x14003894b  shr     cx, 1
0x14003894e  mov     [rsp+0D8h+var_70], cx
0x140038953  mov     [rsp+0D8h+var_78], rax
0x140038958  mov     eax, dword ptr [rsp+0D8h+arg_10+4]
0x14003895f  mov     [rsp+0D8h+var_80], dx
0x140038964  lea     rdx, HandleOpenFailure
0x14003896b  mov     [rsp+0D8h+var_88], eax
0x14003896f  movzx   eax, word ptr [rdi+4]
0x140038973  mov     [rsp+0D8h+var_90], ebx
0x140038977  mov     [rsp+0D8h+var_98], ax
0x14003897c  mov     rax, [rdi+24h]
0x140038980  mov     [rsp+0D8h+var_A0], r14w
0x140038986  mov     [rsp+0D8h+var_A8], r9
0x14003898b  mov     r9, rdi
0x14003898e  mov     [rsp+0D8h+var_B0], rax
0x140038993  mov     rax, [rdi+1Ch]
0x140038997  mov     [rsp+0D8h+var_B8], rax
0x14003899c  call    McTemplateK0pxxjhhqqhzr8hzr10qq_EtwWriteTransfer
0x1400389a1  nop
0x1400389a2  jmp     loc_140006DC0
```
