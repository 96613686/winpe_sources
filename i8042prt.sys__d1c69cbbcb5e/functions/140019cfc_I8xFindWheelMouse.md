# I8xFindWheelMouse

- ea: `0x140019cfc`
- end: `0x14001a13c`
- name: `I8xFindWheelMouse`
- size: `1088`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x14001a19c`

## callees

- `0x140004530`
- `0x1400066d0`
- `0x140006950`
- `0x140007b10`
- `0x14000a48c`
- `0x14000a67c`
- `0x14000c8b4`
- `0x14000da60`
- `0x140019cfc`
- `0x14001a144`
- `0x14001b750`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14001a085`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14001a085`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14001a0d3`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14001a0d3`
- `HAL!KeStallExecutionProcessor` at `0x140019de3`
- `HAL!KeStallExecutionProcessor` at `0x140019e6d`
- `HAL!KeStallExecutionProcessor` at `0x140019de3`
- `HAL!KeStallExecutionProcessor` at `0x140019e6d`

## pseudocode

```c
__int64 __fastcall I8xFindWheelMouse(__int64 a1, int a2)
{
  int v3; // r9d
  bool v4; // zf
  char v5; // al
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ebx
  __int128 *v9; // rdi
  unsigned int i; // ebx
  int BytePolledIterated; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // esi
  __int64 v15; // rcx
  unsigned int v17; // edi
  int v18; // r14d
  _DWORD *ErrorLogEntry; // rax
  unsigned int v20; // r8d
  __int64 v21; // rdx
  __int64 v22; // [rsp+28h] [rbp-51h]
  char v23[4]; // [rsp+40h] [rbp-39h] BYREF
  int v24; // [rsp+44h] [rbp-35h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-31h] BYREF
  int v26; // [rsp+4Ch] [rbp-2Dh] BYREF
  int v27; // [rsp+50h] [rbp-29h] BYREF
  __int16 v28; // [rsp+54h] [rbp-25h]
  char v29; // [rsp+56h] [rbp-23h]
  _DWORD v30[2]; // [rsp+58h] [rbp-21h] BYREF
  _DWORD v31[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v32; // [rsp+68h] [rbp-11h] BYREF
  __int128 v33; // [rsp+78h] [rbp-1h] BYREF

  v30[0] = 1693698291;
  v24 = 0;
  v23[0] = 0;
  v29 = 0;
  v25 = 0;
  v30[1] = 15880435;
  v31[0] = -923547405;
  v31[1] = 15880435;
  v27 = 687019251;
  v28 = 15603;
  v26 = 1480;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      81,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
  if ( !*(_BYTE *)(a1 + 1106) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v3 = 82;
LABEL_35:
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        16,
        v3,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
      return 3221225486LL;
    }
    return 3221225486LL;
  }
  v32 = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v4 = (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 8) == 0;
  }
  else
  {
    KeStallExecutionProcessor(0x32u);
    v5 = *(_BYTE *)(a1 + 1106);
    if ( v5 != 1 )
    {
      if ( v5 != 2 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v3 = 84;
          goto LABEL_35;
        }
        return 3221225486LL;
      }
      goto LABEL_23;
    }
    v8 = I8xTransmitByteSequence(
           (unsigned int)&v27,
           (unsigned int)&v26,
           (unsigned int)&v24,
           (unsigned int)&v32,
           (__int64)&v25);
    if ( v8 < 0 )
      goto LABEL_43;
    v9 = &v33;
    v33 = 0;
    for ( i = 0; i < 7; ++i )
    {
      BytePolledIterated = I8xGetBytePolledIterated(v7, v23);
      if ( v23[0] < 0x36u )
      {
        v7 = (unsigned __int8)v23[0];
        v6 = *((unsigned __int8 *)qword_140010988 + (unsigned __int8)v23[0]);
        *(_WORD *)v9 = v6;
        if ( (_WORD)v6 )
          v9 = (__int128 *)((char *)v9 + 2);
      }
      if ( BytePolledIterated < 0 )
      {
        do
          KeStallExecutionProcessor(0x32u);
        while ( (unsigned int)I8xGetBytePolled(0, v23) != -1073741643 );
        return 3221225486LL;
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_S(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        16,
        83,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        (__int64)&v33);
    v4 = (unsigned __int8)I8xVerifyMousePnPID(a1, &v33) == 0;
  }
  if ( v4 )
    return 3221225486LL;
LABEL_23:
  v8 = I8xTransmitByteSequence(
         (unsigned int)v30,
         (unsigned int)&v26,
         (unsigned int)&v24,
         (unsigned int)&v32,
         (__int64)&v25);
  if ( v8 < 0 )
    goto LABEL_43;
  v13 = I8xGetBytePolledIterated(v12, v23);
  v14 = (unsigned __int8)v23[0];
  v8 = v13;
  if ( v13 < 0 || v23[0] && v23[0] != 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dD(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        17,
        85,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v13,
        v23[0]);
    v17 = 4;
    DWORD2(v32) = 0;
    *(_QWORD *)&v32 = 4;
    v18 = -2147155950;
    HIDWORD(v32) = v14;
    TraceLoggingResetResponseFailed((unsigned int)v8);
    if ( v8 >= 0 )
      goto LABEL_49;
    goto LABEL_44;
  }
  if ( v23[0] != 3 )
  {
    **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 2u;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        16,
        86,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    goto LABEL_49;
  }
  **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 8u;
  *(_WORD *)(a1 + 584) = 32;
  v8 = I8xTransmitByteSequence(
         (unsigned int)v31,
         (unsigned int)&v26,
         (unsigned int)&v24,
         (unsigned int)&v32,
         (__int64)&v25);
  if ( v8 < 0 || (v8 = I8xGetBytePolledIterated(v15, v23), v8 < 0) )
  {
LABEL_43:
    v18 = v24;
    v17 = v25;
LABEL_44:
    if ( v18 )
    {
      ErrorLogEntry = IoAllocateErrorLogEntry(*(PVOID *)a1, 4 * ((unsigned __int8)v17 + 12));
      if ( ErrorLogEntry )
      {
        ErrorLogEntry[3] = v18;
        v20 = 0;
        *((_QWORD *)ErrorLogEntry + 3) = 0;
        *((_WORD *)ErrorLogEntry + 1) = 4 * v17;
        ErrorLogEntry[4] = v26;
        *(_WORD *)ErrorLogEntry = 0;
        for ( ErrorLogEntry[5] = v8; v20 < v17; ErrorLogEntry[v21 + 10] = *((_DWORD *)&v32 + v21) )
          v21 = v20++;
        IoWriteErrorLogEntry(ErrorLogEntry);
      }
    }
    goto LABEL_49;
  }
  if ( v23[0] == 4 )
  {
    **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 0x1008u;
    *(_WORD *)(a1 + 584) = 32;
  }
LABEL_49:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v22) = v8;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      15,
      87,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v22);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140019cfc  push    rbp
0x140019cfe  push    rbx
0x140019cff  push    rsi
0x140019d00  push    rdi
0x140019d01  push    r12
0x140019d03  push    r13
0x140019d05  push    r14
0x140019d07  push    r15
0x140019d09  lea     rbp, [rsp-1Fh]
0x140019d0e  sub     rsp, 98h
0x140019d15  mov     rax, cs:__security_cookie
0x140019d1c  xor     rax, rsp
0x140019d1f  mov     [rbp+57h+var_48], rax
0x140019d23  xor     r13d, r13d
0x140019d26  mov     [rbp+57h+var_78], 64F3C8F3h
0x140019d2d  mov     [rbp+57h+var_8C], r13d
0x140019d31  mov     r15, rcx
0x140019d34  mov     [rbp+57h+var_90], r13b
0x140019d38  mov     [rbp+57h+var_7A], r13b
0x140019d3c  mov     [rbp+57h+var_88], r13d
0x140019d40  mov     [rbp+57h+var_74], 0F250F3h
0x140019d47  mov     [rbp+57h+var_70], 0C8F3C8F3h
0x140019d4e  mov     [rbp+57h+var_6C], 0F250F3h
0x140019d55  mov     [rbp+57h+var_80], 28F314F3h
0x140019d5c  mov     [rbp+57h+var_7C], 3CF3h
0x140019d62  mov     [rbp+57h+var_84], 5C8h
0x140019d69  lea     r12, WPP_RECORDER_INITIALIZED
0x140019d70  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019d77  lea     r14, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x140019d7e  jz      short loc_140019D9D
0x140019d80  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d87  lea     r9d, [r13+51h]
0x140019d8b  lea     r8d, [r13+0Fh]
0x140019d8f  mov     [rsp+0D0h+var_B0], r14
0x140019d94  mov     rcx, [rcx+40h]
0x140019d98  call    WPP_RECORDER_SF_
0x140019d9d  cmp     [r15+452h], r13b
0x140019da4  jnz     short loc_140019DBE
0x140019da6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019dad  jz      loc_140019FD8
0x140019db3  mov     r9d, 52h ; 'R'
0x140019db9  jmp     loc_140019FBD
0x140019dbe  xorps   xmm0, xmm0
0x140019dc1  movups  [rbp+57h+var_68], xmm0
0x140019dc5  cmp     [r15+8], r13
0x140019dc9  jz      short loc_140019DDC
0x140019dcb  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140019dd2  mov     ecx, [rax]
0x140019dd4  test    cl, 8
0x140019dd7  jmp     loc_140019ECF
0x140019ddc  mov     esi, 32h ; '2'
0x140019de1  mov     ecx, esi; MicroSeconds
0x140019de3  call    cs:__imp_KeStallExecutionProcessor
0x140019dea  nop     dword ptr [rax+rax+00h]
0x140019def  mov     al, [r15+452h]
0x140019df6  cmp     al, 1
0x140019df8  jnz     loc_140019FA6
0x140019dfe  lea     rax, [rbp+57h+var_88]
0x140019e02  lea     r9, [rbp+57h+var_68]
0x140019e06  mov     [rsp+0D0h+var_B0], rax
0x140019e0b  lea     r8, [rbp+57h+var_8C]
0x140019e0f  lea     rdx, [rbp+57h+var_84]
0x140019e13  lea     rcx, [rbp+57h+var_80]
0x140019e17  call    I8xTransmitByteSequence
0x140019e1c  mov     ebx, eax
0x140019e1e  test    eax, eax
0x140019e20  js      loc_14001A070
0x140019e26  xorps   xmm0, xmm0
0x140019e29  lea     rdi, [rbp+57h+var_58]
0x140019e2d  movups  [rbp+57h+var_58], xmm0
0x140019e31  mov     ebx, r13d
0x140019e34  cmp     ebx, 7
0x140019e37  jnb     short loc_140019E90
0x140019e39  lea     rdx, [rbp+57h+var_90]
0x140019e3d  call    I8xGetBytePolledIterated
0x140019e42  cmp     [rbp+57h+var_90], 36h ; '6'
0x140019e46  jnb     short loc_140019E63
0x140019e48  movzx   ecx, [rbp+57h+var_90]
0x140019e4c  lea     rdx, qword_140010988
0x140019e53  movzx   edx, byte ptr [rcx+rdx]
0x140019e57  mov     [rdi], dx
0x140019e5a  test    dx, dx
0x140019e5d  jz      short loc_140019E63
0x140019e5f  add     rdi, 2
0x140019e63  test    eax, eax
0x140019e65  js      short loc_140019E6B
0x140019e67  inc     ebx
0x140019e69  jmp     short loc_140019E34
0x140019e6b  mov     ecx, esi; MicroSeconds
0x140019e6d  call    cs:__imp_KeStallExecutionProcessor
0x140019e74  nop     dword ptr [rax+rax+00h]
0x140019e79  lea     rdx, [rbp+57h+var_90]
0x140019e7d  xor     ecx, ecx
0x140019e7f  call    I8xGetBytePolled
0x140019e84  cmp     eax, 0C00000B5h
0x140019e89  jnz     short loc_140019E6B
0x140019e8b  jmp     loc_140019FD8
0x140019e90  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019e97  jz      short loc_140019EC1
0x140019e99  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ea0  lea     rax, [rbp+57h+var_58]
0x140019ea4  mov     r9d, 53h ; 'S'
0x140019eaa  mov     [rsp+0D0h+var_A8], rax
0x140019eaf  mov     [rsp+0D0h+var_B0], r14
0x140019eb4  mov     rcx, [rcx+40h]
0x140019eb8  lea     r8d, [r9-43h]
0x140019ebc  call    WPP_RECORDER_SF_S
0x140019ec1  lea     rdx, [rbp+57h+var_58]
0x140019ec5  mov     rcx, r15
0x140019ec8  call    I8xVerifyMousePnPID
0x140019ecd  test    al, al
0x140019ecf  jz      loc_140019FD8
0x140019ed5  lea     rax, [rbp+57h+var_88]
0x140019ed9  lea     r9, [rbp+57h+var_68]
0x140019edd  mov     [rsp+0D0h+var_B0], rax
0x140019ee2  lea     r8, [rbp+57h+var_8C]
0x140019ee6  lea     rdx, [rbp+57h+var_84]
0x140019eea  lea     rcx, [rbp+57h+var_78]
0x140019eee  call    I8xTransmitByteSequence
0x140019ef3  mov     ebx, eax
0x140019ef5  test    eax, eax
0x140019ef7  js      loc_14001A070
0x140019efd  lea     rdx, [rbp+57h+var_90]
0x140019f01  call    I8xGetBytePolledIterated
0x140019f06  movzx   esi, [rbp+57h+var_90]
0x140019f0a  mov     ebx, eax
0x140019f0c  test    eax, eax
0x140019f0e  js      loc_14001A016
0x140019f14  test    sil, sil
0x140019f17  jz      short loc_140019F23
0x140019f19  cmp     sil, 3
0x140019f1d  jnz     loc_14001A016
0x140019f23  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140019f2a  cmp     sil, 3
0x140019f2e  jnz     loc_140019FE2
0x140019f34  or      dword ptr [rax], 8
0x140019f37  lea     r9, [rbp+57h+var_68]
0x140019f3b  lea     rax, [rbp+57h+var_88]
0x140019f3f  mov     esi, 20h ; ' '
0x140019f44  lea     r8, [rbp+57h+var_8C]
0x140019f48  mov     [rsp+0D0h+var_B0], rax
0x140019f4d  lea     rdx, [rbp+57h+var_84]
0x140019f51  mov     [r15+248h], si
0x140019f59  lea     rcx, [rbp+57h+var_70]
0x140019f5d  call    I8xTransmitByteSequence
0x140019f62  mov     ebx, eax
0x140019f64  test    eax, eax
0x140019f66  js      loc_14001A070
0x140019f6c  lea     rdx, [rbp+57h+var_90]
0x140019f70  call    I8xGetBytePolledIterated
0x140019f75  mov     ebx, eax
0x140019f77  test    eax, eax
0x140019f79  js      loc_14001A070
0x140019f7f  lea     edi, [rsi-1Ch]
0x140019f82  cmp     [rbp+57h+var_90], dil
0x140019f86  jnz     loc_14001A0E6
0x140019f8c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140019f93  or      dword ptr [rax], 1008h
0x140019f99  mov     [r15+248h], si
0x140019fa1  jmp     loc_14001A0E6
0x140019fa6  cmp     al, 2
0x140019fa8  jz      loc_140019ED5
0x140019fae  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019fb5  jz      short loc_140019FD8
0x140019fb7  mov     r9d, 54h ; 'T'
0x140019fbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140019fc4  mov     r8d, 10h
0x140019fca  mov     [rsp+0D0h+var_B0], r14
0x140019fcf  mov     rcx, [rcx+40h]
0x140019fd3  call    WPP_RECORDER_SF_
0x140019fd8  mov     eax, 0C000000Eh
0x140019fdd  jmp     loc_14001A11B
0x140019fe2  or      dword ptr [rax], 2
0x140019fe5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140019fec  jz      loc_14001A0E6
0x140019ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ff9  mov     r9d, 56h ; 'V'
0x140019fff  mov     [rsp+0D0h+var_B0], r14
0x14001a004  mov     rcx, [rcx+40h]
0x14001a008  lea     r8d, [r9-46h]
0x14001a00c  call    WPP_RECORDER_SF_
0x14001a011  jmp     loc_14001A0E6
0x14001a016  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a01d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a024  jz      short loc_14001A04D
0x14001a026  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a02d  mov     r9d, 55h ; 'U'
0x14001a033  mov     [rsp+0D0h+var_A0], esi
0x14001a037  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x14001a03b  mov     [rsp+0D0h+var_B0], r14
0x14001a040  mov     rcx, [rcx+40h]
0x14001a044  lea     r8d, [r9-44h]
0x14001a048  call    WPP_RECORDER_SF_dD
0x14001a04d  mov     edi, 4
0x14001a052  mov     dword ptr [rbp+57h+var_68+8], r13d
0x14001a056  mov     ecx, ebx
0x14001a058  mov     qword ptr [rbp+57h+var_68], rdi
0x14001a05c  mov     r14d, 80050012h
0x14001a062  mov     dword ptr [rbp+57h+var_68+0Ch], esi
0x14001a065  call    TraceLoggingResetResponseFailed
0x14001a06a  test    ebx, ebx
0x14001a06c  jns     short loc_14001A0DF
0x14001a06e  jmp     short loc_14001A077
0x14001a070  mov     r14d, [rbp+57h+var_8C]
0x14001a074  mov     edi, [rbp+57h+var_88]
0x14001a077  test    r14d, r14d
0x14001a07a  jz      short loc_14001A0DF
0x14001a07c  mov     rcx, [r15]; IoObject
0x14001a07f  lea     edx, [rdi+0Ch]
0x14001a082  shl     dl, 2; EntrySize
0x14001a085  call    cs:__imp_IoAllocateErrorLogEntry
0x14001a08c  nop     dword ptr [rax+rax+00h]
0x14001a091  mov     rcx, rax; ElEntry
0x14001a094  test    rax, rax
0x14001a097  jz      short loc_14001A0DF
0x14001a099  mov     [rax+0Ch], r14d
0x14001a09d  mov     r8d, r13d
0x14001a0a0  movzx   eax, di
0x14001a0a3  mov     [rcx+18h], r13
0x14001a0a7  shl     ax, 2
0x14001a0ab  mov     [rcx+2], ax
0x14001a0af  mov     eax, [rbp+57h+var_84]
0x14001a0b2  mov     [rcx+10h], eax
0x14001a0b5  mov     [rcx], r13w
0x14001a0b9  mov     [rcx+14h], ebx
0x14001a0bc  test    edi, edi
0x14001a0be  jz      short loc_14001A0D3
0x14001a0c0  mov     edx, r8d
0x14001a0c3  inc     r8d
0x14001a0c6  mov     eax, dword ptr [rbp+rdx*4+57h+var_68]
0x14001a0ca  mov     [rcx+rdx*4+28h], eax
0x14001a0ce  cmp     r8d, edi
0x14001a0d1  jb      short loc_14001A0C0
0x14001a0d3  call    cs:__imp_IoWriteErrorLogEntry
0x14001a0da  nop     dword ptr [rax+rax+00h]
0x14001a0df  lea     r14, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001a0e6  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a0ed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a0f4  jz      short loc_14001A119
0x14001a0f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a0fd  mov     r9d, 57h ; 'W'
0x14001a103  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x14001a107  mov     [rsp+0D0h+var_B0], r14
0x14001a10c  mov     rcx, [rcx+40h]
0x14001a110  lea     r8d, [r9-48h]
0x14001a114  call    WPP_RECORDER_SF_D
0x14001a119  mov     eax, ebx
0x14001a11b  mov     rcx, [rbp+57h+var_48]
0x14001a11f  xor     rcx, rsp; StackCookie
0x14001a122  call    __security_check_cookie
0x14001a127  add     rsp, 98h
0x14001a12e  pop     r15
0x14001a130  pop     r14
0x14001a132  pop     r13
0x14001a134  pop     r12
0x14001a136  pop     rdi
0x14001a137  pop     rsi
0x14001a138  pop     rbx
0x14001a139  pop     rbp
0x14001a13a  retn
```
