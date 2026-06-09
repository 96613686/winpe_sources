# SubmitTransferPacket

- ea: `0x140004950`
- end: `0x140004ebe`
- name: `SubmitTransferPacket`
- size: `1390`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140001130`
- `0x140002fb0`
- `0x140004300`
- `0x1400206f8`
- `0x140020ef4`
- `0x140024070`
- `0x140025134`
- `0x140059cb4`
- `0x14005d970`

## callees

- `0x140004950`
- `0x140005d30`
- `0x140015c50`
- `0x140019bc4`
- `0x14003e470`

## import_xrefs

- `ntoskrnl!IoSetActivityIdIrp` at `0x140004e63`
- `ntoskrnl!IoSetActivityIdIrp` at `0x140004e63`
- `ntoskrnl!IoReuseIrp` at `0x140004995`
- `ntoskrnl!IoReuseIrp` at `0x140004995`
- `ntoskrnl!IofCallDriver` at `0x140004bb6`
- `ntoskrnl!IofCallDriver` at `0x140004bb6`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140004aee`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140004e1b`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140004aee`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140004e1b`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400049ac`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400049ac`
- `ntoskrnl!IoBuildPartialMdl` at `0x140004d81`
- `ntoskrnl!IoBuildPartialMdl` at `0x140004d81`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x140004ac7`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x140004ac7`
- `ntoskrnl!IoIsActivityTracingEnabled` at `0x1400049c0`
- `ntoskrnl!IoIsActivityTracingEnabled` at `0x1400049c0`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140004b08`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x140004b08`

## pseudocode

```c
NTSTATUS __fastcall SubmitTransferPacket(__int64 a1)
{
  __int64 v1; // rax
  IRP *v3; // rcx
  __int64 (__fastcall *v4)(__int64, _QWORD); // r12
  __int64 v5; // r13
  __int64 v6; // rsi
  struct _DEVICE_OBJECT *v7; // r15
  __int64 v8; // r14
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // edi
  __int64 j; // r9
  __int64 v14; // rcx
  unsigned __int64 v15; // r11
  int v16; // ebp
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // r9
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  char v24; // r8
  __int64 v25; // rdx
  unsigned int v27; // edi
  unsigned int i; // r9d
  __int64 v29; // rcx
  unsigned __int64 v30; // r11
  int v31; // ebp
  _BYTE *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // r8
  unsigned __int64 v38; // rax
  int v39; // ebp
  int v40; // ebp
  __int64 v41; // r8
  unsigned __int64 QpcTimeStamp; // [rsp+60h] [rbp+8h] BYREF
  __int64 v43; // [rsp+68h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 40);
  v3 = *(IRP **)(a1 + 32);
  v4 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(v1 + 64);
  v7 = *(struct _DEVICE_OBJECT **)(v6 + 16);
  v8 = *(_QWORD *)(v6 + 1144);
  v43 = 0;
  QpcTimeStamp = 0;
  IoReuseIrp(v3, -1073741637);
  if ( (int)IoGetActivityIdIrp(*(_QWORD *)(a1 + 48), a1 + 328) < 0 )
    *(_OWORD *)(a1 + 328) = *(_OWORD *)*(_QWORD *)(a1 + 48);
  if ( (unsigned __int8)IoIsActivityTracingEnabled() )
    IoSetActivityIdIrp(*(_QWORD *)(a1 + 32), a1 + 328);
  v9 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 184LL);
  *(_BYTE *)(v9 - 72) = 15;
  *(_QWORD *)(v9 - 64) = *(_QWORD *)(a1 + 288);
  v10 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v10 + 2) != 40 )
  {
    *(_BYTE *)(v10 + 4) = 0;
    goto LABEL_7;
  }
  if ( !*(_DWORD *)(v10 + 20) )
  {
    v27 = *(_DWORD *)(v10 + 56);
    for ( i = 0; i < v27; ++i )
    {
      v29 = *(unsigned int *)(v10 + 4LL * i + 120);
      if ( (unsigned int)v29 >= 0x80 )
      {
        v30 = *(unsigned int *)(v10 + 16);
        if ( (unsigned int)v29 < (unsigned int)v30 )
        {
          v31 = *(_DWORD *)(v29 + v10);
          if ( v31 == 64 )
          {
            if ( v29 + 40 <= v30 )
              goto LABEL_41;
          }
          else
          {
            v40 = v31 - 65;
            if ( v40 )
            {
              if ( v40 == 1 && v29 + 40 <= v30 )
              {
LABEL_41:
                *(_BYTE *)(v29 + v10 + 8) = 0;
                break;
              }
            }
            else if ( v29 + 56 <= v30 )
            {
              goto LABEL_41;
            }
          }
        }
      }
    }
  }
LABEL_7:
  *(_BYTE *)(*(_QWORD *)(a1 + 288) + 3LL) = 0;
  v11 = *(_QWORD *)(a1 + 288);
  if ( *(_BYTE *)(v11 + 2) != 40 )
  {
    *(_BYTE *)(v11 + 11) = 18;
    goto LABEL_16;
  }
  if ( !*(_DWORD *)(v11 + 20) )
  {
    v12 = *(_DWORD *)(v11 + 56);
    for ( j = 0; (unsigned int)j < v12; j = (unsigned int)(j + 1) )
    {
      v14 = *(unsigned int *)(v11 + 4 * j + 120);
      if ( (unsigned int)v14 >= 0x80 )
      {
        v15 = *(unsigned int *)(v11 + 16);
        if ( (unsigned int)v14 < (unsigned int)v15 )
        {
          v16 = *(_DWORD *)(v14 + v11);
          if ( v16 == 64 )
          {
            if ( v14 + 40 <= v15 )
              goto LABEL_14;
          }
          else
          {
            v39 = v16 - 65;
            if ( v39 )
            {
              if ( v39 == 1 && v14 + 40 <= v15 )
              {
LABEL_14:
                *(_BYTE *)(v14 + v11 + 9) = 18;
                break;
              }
            }
            else if ( v14 + 56 <= v15 )
            {
              goto LABEL_14;
            }
          }
        }
      }
    }
  }
LABEL_16:
  if ( *(_BYTE *)(a1 + 56) )
  {
    v32 = *(_BYTE **)(*(_QWORD *)(a1 + 48) + 184LL);
    *(_BYTE *)(v9 - 70) = v32[2];
    if ( (unsigned __int8)(*v32 - 3) <= 1u && (*(_WORD *)(v6 + 640) & 0x100) != 0 )
    {
      v33 = *(_QWORD *)(v6 + 1144);
      v7 = *(struct _DEVICE_OBJECT **)(v6 + 512);
      v4 = *(__int64 (__fastcall **)(__int64, _QWORD))(v33 + 472);
      v5 = *(_QWORD *)(v33 + 456);
      if ( (*(_DWORD *)(v33 + 664) & 0x80u) != 0 )
      {
        v34 = *(_QWORD *)(a1 + 288);
        if ( *(_BYTE *)(v34 + 2) == 40 )
          *(_DWORD *)(v34 + 24) |= 0x4000u;
        else
          *(_DWORD *)(v34 + 12) |= 0x4000u;
      }
    }
  }
  v17 = 24;
  if ( *(_BYTE *)(a1 + 296) )
  {
    v35 = *(_QWORD *)(a1 + 288);
    v36 = 60;
    v37 = 64;
    if ( *(_BYTE *)(v35 + 2) != 40 )
    {
      v36 = 16;
      v37 = 24;
    }
    IoBuildPartialMdl(
      *(PMDL *)(*(_QWORD *)(a1 + 48) + 8LL),
      *(PMDL *)(a1 + 304),
      *(PVOID *)(v37 + v35),
      *(_DWORD *)(v36 + v35));
    v18 = *(_QWORD *)(a1 + 304);
  }
  else
  {
    v18 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 32) + 8LL) = v18;
  IoPropagateIrpExtensionEx(
    *(_QWORD *)(a1 + 48),
    *(_QWORD *)(a1 + 32),
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8LL) + 32LL)
  + *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 8LL) + 44LL)
  - (unsigned __int64)*(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL) + 44LL)
  - *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL) + 32LL),
    0xFFFFFFFFLL);
  QpcTimeStamp = 0;
  if ( ClassPnPPerfSensitiveEtwEventsEnabled || *(_QWORD *)(v8 + 696) )
    QpcTimeStamp = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
  if ( (int)IoGetIoAttributionHandle(*(_QWORD *)(a1 + 48), &v43) >= 0 )
  {
    v38 = QpcTimeStamp;
    if ( !QpcTimeStamp )
    {
      v38 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
      QpcTimeStamp = v38;
    }
    LOBYTE(v19) = 1;
    TransferPktRecordIoAttribution(a1, v38, 0, v19);
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 656));
  }
  v20 = *(_QWORD *)(a1 + 312) == 0;
  *(_QWORD *)(a1 + 320) = QpcTimeStamp;
  if ( !v20 )
    HistoryLogSendPacket(a1);
  v21 = *(_QWORD *)(a1 + 288);
  v22 = *(_QWORD *)(a1 + 48);
  if ( *(_BYTE *)(v21 + 2) == 40 )
    *(_QWORD *)(v21 + 104) = v22;
  else
    *(_QWORD *)(v21 + 56) = v22;
  if ( (*(_DWORD *)(v8 + 664) & 1) != 0 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 48) + 128LL) )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 3880));
    else
      _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6)
                                                      + *(_QWORD *)(v8 + 680)
                                                      + 20));
  }
  if ( ClassPnPPerfSensitiveEtwEventsEnabled == 1 )
    ClasspWriteIODispatchEvent(a1);
  v23 = *(_QWORD *)(a1 + 288);
  v24 = *(_BYTE *)(v23 + 2);
  if ( v24 != 40 )
    v17 = 12;
  if ( (*(_DWORD *)(v17 + v23) & 0x4000) == 0 )
    goto LABEL_32;
  if ( !v4 || !v5 )
  {
    if ( v24 == 40 )
      *(_DWORD *)(v23 + 24) &= ~0x4000u;
    else
      *(_DWORD *)(v23 + 12) &= ~0x4000u;
LABEL_32:
    v25 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 184LL);
    *(_QWORD *)(v25 - 16) = TransferPktComplete;
    *(_QWORD *)(v25 - 8) = a1;
    *(_BYTE *)(v25 - 69) = -32;
    return IofCallDriver(v7, *(PIRP *)(a1 + 32));
  }
  v41 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 184LL);
  *(_QWORD *)(v41 - 16) = TransferPktComplete;
  *(_QWORD *)(v41 - 8) = a1;
  *(_BYTE *)(v41 - 69) = -32;
  return v4(v5, *(_QWORD *)(a1 + 32));
}

```

## disassembly

```asm
0x140004950  mov     [rsp+arg_10], rbx
0x140004955  push    rbp
0x140004956  push    rsi
0x140004957  push    rdi
0x140004958  push    r12
0x14000495a  push    r13
0x14000495c  push    r14
0x14000495e  push    r15
0x140004960  sub     rsp, 20h
0x140004964  mov     rax, [rcx+28h]
0x140004968  xor     ebp, ebp
0x14000496a  mov     rbx, rcx
0x14000496d  mov     edx, 0C00000BBh; Iostatus
0x140004972  mov     rcx, [rcx+20h]; Irp
0x140004976  mov     r12d, ebp
0x140004979  mov     r13d, ebp
0x14000497c  mov     rsi, [rax+40h]
0x140004980  mov     r15, [rsi+10h]
0x140004984  mov     r14, [rsi+478h]
0x14000498b  mov     [rsp+58h+arg_8], rbp
0x140004990  mov     [rsp+58h+QpcTimeStamp], rbp
0x140004995  call    cs:__imp_IoReuseIrp
0x14000499c  nop     dword ptr [rax+rax+00h]
0x1400049a1  mov     rcx, [rbx+30h]
0x1400049a5  lea     rdx, [rbx+148h]
0x1400049ac  call    cs:__imp_IoGetActivityIdIrp
0x1400049b3  nop     dword ptr [rax+rax+00h]
0x1400049b8  test    eax, eax
0x1400049ba  js      loc_140004C3C
0x1400049c0  call    cs:__imp_IoIsActivityTracingEnabled
0x1400049c7  nop     dword ptr [rax+rax+00h]
0x1400049cc  test    al, al
0x1400049ce  jnz     loc_140004E58
0x1400049d4  mov     rax, [rbx+20h]
0x1400049d8  mov     r8, [rax+0B8h]
0x1400049df  mov     byte ptr [r8-48h], 0Fh
0x1400049e4  mov     rax, [rbx+120h]
0x1400049eb  mov     [r8-40h], rax
0x1400049ef  mov     rdx, [rbx+120h]
0x1400049f6  cmp     byte ptr [rdx+2], 28h ; '('
0x1400049fa  jz      loc_140004BEB
0x140004a00  mov     [rdx+4], bpl
0x140004a04  mov     rax, [rbx+120h]
0x140004a0b  mov     [rax+3], r12b
0x140004a0f  mov     rdx, [rbx+120h]
0x140004a16  cmp     byte ptr [rdx+2], 28h ; '('
0x140004a1a  jnz     short loc_140004A6E
0x140004a1c  cmp     [rdx+14h], r12d
0x140004a20  jnz     short loc_140004A72
0x140004a22  mov     edi, [rdx+38h]
0x140004a25  xor     r9d, r9d
0x140004a28  test    edi, edi
0x140004a2a  jz      short loc_140004A72
0x140004a2c  mov     ecx, [rdx+r9*4+78h]
0x140004a31  cmp     ecx, 80h
0x140004a37  jb      loc_140004C5C
0x140004a3d  mov     r11d, [rdx+10h]
0x140004a41  cmp     ecx, r11d
0x140004a44  jnb     loc_140004C5C
0x140004a4a  mov     ebp, [rcx+rdx]
0x140004a4d  lea     r10, [rcx+rdx]
0x140004a51  cmp     ebp, 40h ; '@'
0x140004a54  jnz     loc_140004DCE
0x140004a5a  add     rcx, 28h ; '('
0x140004a5e  cmp     rcx, r11
0x140004a61  ja      loc_140004C5C
0x140004a67  mov     byte ptr [r10+9], 12h
0x140004a6c  jmp     short loc_140004A72
0x140004a6e  mov     byte ptr [rdx+0Bh], 12h
0x140004a72  cmp     [rbx+38h], r12b
0x140004a76  jnz     loc_140004CC0
0x140004a7c  cmp     byte ptr [rbx+128h], 0
0x140004a83  mov     edi, 18h
0x140004a88  jnz     loc_140004D46
0x140004a8e  mov     rax, [rbx+30h]
0x140004a92  mov     rax, [rax+8]
0x140004a96  mov     rcx, [rbx+20h]
0x140004a9a  mov     [rcx+8], rax
0x140004a9e  mov     rdx, [rbx+20h]
0x140004aa2  mov     rcx, [rbx+30h]
0x140004aa6  mov     r10, [rdx+8]
0x140004aaa  mov     r9, [rcx+8]
0x140004aae  mov     r8d, [r10+2Ch]
0x140004ab2  mov     eax, [r9+2Ch]
0x140004ab6  sub     r8, rax
0x140004ab9  sub     r8, [r9+20h]
0x140004abd  mov     r9d, 0FFFFFFFFh
0x140004ac3  add     r8, [r10+20h]
0x140004ac7  call    cs:__imp_IoPropagateIrpExtensionEx
0x140004ace  nop     dword ptr [rax+rax+00h]
0x140004ad3  cmp     cs:ClassPnPPerfSensitiveEtwEventsEnabled, 0
0x140004ada  mov     [rsp+58h+QpcTimeStamp], 0
0x140004ae3  jz      loc_140004BD8
0x140004ae9  lea     rcx, [rsp+58h+QpcTimeStamp]; QpcTimeStamp
0x140004aee  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140004af5  nop     dword ptr [rax+rax+00h]
0x140004afa  mov     [rsp+58h+QpcTimeStamp], rax
0x140004aff  mov     rcx, [rbx+30h]
0x140004b03  lea     rdx, [rsp+58h+arg_8]
0x140004b08  call    cs:__imp_IoGetIoAttributionHandle
0x140004b0f  nop     dword ptr [rax+rax+00h]
0x140004b14  test    eax, eax
0x140004b16  jns     loc_140004DA6
0x140004b1c  cmp     qword ptr [rbx+138h], 0
0x140004b24  mov     rax, [rsp+58h+QpcTimeStamp]
0x140004b29  mov     [rbx+140h], rax
0x140004b30  jnz     loc_140004E74
0x140004b36  mov     rax, [rbx+120h]
0x140004b3d  mov     rcx, [rbx+30h]
0x140004b41  cmp     byte ptr [rax+2], 28h ; '('
0x140004b45  jnz     loc_140004CB7
0x140004b4b  mov     [rax+68h], rcx
0x140004b4f  mov     eax, [r14+298h]
0x140004b56  test    al, 1
0x140004b58  jnz     loc_140004C87
0x140004b5e  cmp     cs:ClassPnPPerfSensitiveEtwEventsEnabled, 1
0x140004b65  jz      loc_140004D99
0x140004b6b  mov     rdx, [rbx+120h]
0x140004b72  mov     eax, 0Ch
0x140004b77  movzx   r8d, byte ptr [rdx+2]
0x140004b7c  cmp     r8b, 28h ; '('
0x140004b80  cmovnz  rdi, rax
0x140004b84  test    dword ptr [rdi+rdx], 4000h
0x140004b8b  jnz     loc_140004E81
0x140004b91  mov     rax, [rbx+20h]
0x140004b95  lea     r9, TransferPktComplete
0x140004b9c  mov     rcx, r15; DeviceObject
0x140004b9f  mov     rdx, [rax+0B8h]
0x140004ba6  mov     [rdx-10h], r9
0x140004baa  mov     [rdx-8], rbx
0x140004bae  mov     byte ptr [rdx-45h], 0E0h
0x140004bb2  mov     rdx, [rbx+20h]; Irp
0x140004bb6  call    cs:__imp_IofCallDriver
0x140004bbd  nop     dword ptr [rax+rax+00h]
0x140004bc2  mov     rbx, [rsp+58h+arg_10]
0x140004bc7  add     rsp, 20h
0x140004bcb  pop     r15
0x140004bcd  pop     r14
0x140004bcf  pop     r13
0x140004bd1  pop     r12
0x140004bd3  pop     rdi
0x140004bd4  pop     rsi
0x140004bd5  pop     rbp
0x140004bd6  retn
0x140004bd8  cmp     qword ptr [r14+2B8h], 0
0x140004be0  jz      loc_140004AFF
0x140004be6  jmp     loc_140004AE9
0x140004beb  cmp     [rdx+14h], ebp
0x140004bee  jnz     loc_140004A04
0x140004bf4  mov     edi, [rdx+38h]
0x140004bf7  mov     r9d, ebp
0x140004bfa  test    edi, edi
0x140004bfc  jz      loc_140004A04
0x140004c02  mov     eax, r9d
0x140004c05  mov     ecx, [rdx+rax*4+78h]
0x140004c09  cmp     ecx, 80h
0x140004c0f  jb      short loc_140004C76
0x140004c11  mov     r11d, [rdx+10h]
0x140004c15  cmp     ecx, r11d
0x140004c18  jnb     short loc_140004C76
0x140004c1a  mov     ebp, [rcx+rdx]
0x140004c1d  lea     r10, [rcx+rdx]
0x140004c21  cmp     ebp, 40h ; '@'
0x140004c24  jnz     loc_140004DF2
0x140004c2a  add     rcx, 28h ; '('
0x140004c2e  cmp     rcx, r11
0x140004c31  ja      short loc_140004C76
0x140004c33  mov     [r10+8], r12b
0x140004c37  jmp     loc_140004A04
0x140004c3c  mov     rax, [rbx+30h]
0x140004c40  movups  xmm0, xmmword ptr [rax]
0x140004c43  movups  xmmword ptr [rbx+148h], xmm0
0x140004c4a  jmp     loc_1400049C0
0x140004c4f  add     rcx, 38h ; '8'
0x140004c53  cmp     rcx, r11
0x140004c56  jbe     loc_140004A67
0x140004c5c  inc     r9d
0x140004c5f  cmp     r9d, edi
0x140004c62  jnb     loc_140004A72
0x140004c68  jmp     loc_140004A2C
0x140004c6d  add     rcx, 38h ; '8'
0x140004c71  cmp     rcx, r11
0x140004c74  jbe     short loc_140004C33
0x140004c76  inc     r9d
0x140004c79  cmp     r9d, edi
0x140004c7c  jnb     loc_140004A04
0x140004c82  jmp     loc_140004C02
0x140004c87  mov     rax, [rbx+30h]
0x140004c8b  cmp     byte ptr [rax+80h], 0
0x140004c92  jnz     loc_140004D39
0x140004c98  mov     eax, gs:1A4h
0x140004ca0  mov     ecx, eax
0x140004ca2  mov     rax, [r14+2A8h]
0x140004ca9  shl     rcx, 6
0x140004cad  lock inc dword ptr [rcx+rax+14h]
0x140004cb2  jmp     loc_140004B5E
0x140004cb7  mov     [rax+38h], rcx
0x140004cbb  jmp     loc_140004B4F
0x140004cc0  mov     rax, [rbx+30h]
0x140004cc4  mov     rcx, [rax+0B8h]
0x140004ccb  movzx   eax, byte ptr [rcx+2]
0x140004ccf  mov     [r8-46h], al
0x140004cd3  movzx   eax, byte ptr [rcx]
0x140004cd6  sub     al, 3
0x140004cd8  cmp     al, 1
0x140004cda  ja      loc_140004A7C
0x140004ce0  movzx   eax, word ptr [rsi+280h]
0x140004ce7  bt      ax, 8
0x140004cec  jnb     loc_140004A7C
0x140004cf2  mov     rax, [rsi+478h]
0x140004cf9  mov     r15, [rsi+200h]
0x140004d00  mov     r12, [rax+1D8h]
0x140004d07  mov     r13, [rax+1C8h]
0x140004d0e  mov     eax, [rax+298h]
0x140004d14  test    al, al
0x140004d16  jns     loc_140004A7C
0x140004d1c  mov     rax, [rbx+120h]
0x140004d23  cmp     byte ptr [rax+2], 28h ; '('
0x140004d27  jnz     loc_140004E2E
0x140004d2d  or      dword ptr [rax+18h], 4000h
0x140004d34  jmp     loc_140004A7C
0x140004d39  lock inc dword ptr [r14+0F28h]
0x140004d41  jmp     loc_140004B5E
0x140004d46  mov     rdx, [rbx+120h]
0x140004d4d  mov     ecx, 10h
0x140004d52  mov     r9d, 3Ch ; '<'
0x140004d58  mov     r8d, 40h ; '@'
0x140004d5e  cmp     byte ptr [rdx+2], 28h ; '('
0x140004d62  cmovnz  r9d, ecx
0x140004d66  cmovnz  r8, rdi
0x140004d6a  mov     rcx, [rbx+30h]
0x140004d6e  mov     r9d, [r9+rdx]; Length
0x140004d72  mov     r8, [r8+rdx]; VirtualAddress
0x140004d76  mov     rdx, [rbx+130h]; TargetMdl
0x140004d7d  mov     rcx, [rcx+8]; SourceMdl
0x140004d81  call    cs:__imp_IoBuildPartialMdl
0x140004d88  nop     dword ptr [rax+rax+00h]
0x140004d8d  mov     rax, [rbx+130h]
0x140004d94  jmp     loc_140004A96
0x140004d99  mov     rcx, rbx
0x140004d9c  call    ClasspWriteIODispatchEvent
0x140004da1  jmp     loc_140004B6B
0x140004da6  mov     rax, [rsp+58h+QpcTimeStamp]
0x140004dab  test    rax, rax
0x140004dae  jz      short loc_140004E16
0x140004db0  mov     r9b, 1
0x140004db3  xor     r8d, r8d
0x140004db6  mov     rdx, rax
0x140004db9  mov     rcx, rbx
0x140004dbc  call    TransferPktRecordIoAttribution
0x140004dc1  lock inc dword ptr [r14+290h]
0x140004dc9  jmp     loc_140004B1C
0x140004dce  sub     ebp, 41h ; 'A'
0x140004dd1  jz      loc_140004C4F
0x140004dd7  cmp     ebp, 1
0x140004dda  jnz     loc_140004C5C
0x140004de0  add     rcx, 28h ; '('
0x140004de4  cmp     rcx, r11
0x140004de7  jbe     loc_140004A67
0x140004ded  jmp     loc_140004C5C
0x140004df2  sub     ebp, 41h ; 'A'
0x140004df5  jz      loc_140004C6D
0x140004dfb  cmp     ebp, 1
0x140004dfe  jnz     loc_140004C76
0x140004e04  add     rcx, 28h ; '('
0x140004e08  cmp     rcx, r11
0x140004e0b  jbe     loc_140004C33
0x140004e11  jmp     loc_140004C76
0x140004e16  lea     rcx, [rsp+58h+QpcTimeStamp]; QpcTimeStamp
0x140004e1b  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140004e22  nop     dword ptr [rax+rax+00h]
0x140004e27  mov     [rsp+58h+QpcTimeStamp], rax
0x140004e2c  jmp     short loc_140004DB0
0x140004e2e  or      dword ptr [rax+0Ch], 4000h
0x140004e35  jmp     loc_140004A7C
0x140004e3a  cmp     r8b, 28h ; '('
0x140004e3e  jnz     short loc_140004E4C
0x140004e40  and     dword ptr [rdx+18h], 0FFFFBFFFh
0x140004e47  jmp     loc_140004B91
0x140004e4c  and     dword ptr [rdx+0Ch], 0FFFFBFFFh
0x140004e53  jmp     loc_140004B91
0x140004e58  mov     rcx, [rbx+20h]
0x140004e5c  lea     rdx, [rbx+148h]
0x140004e63  call    cs:__imp_IoSetActivityIdIrp
0x140004e6a  nop     dword ptr [rax+rax+00h]
0x140004e6f  jmp     loc_1400049D4
0x140004e74  mov     rcx, rbx
0x140004e77  call    HistoryLogSendPacket
0x140004e7c  jmp     loc_140004B36
0x140004e81  test    r12, r12
0x140004e84  jz      short loc_140004E3A
0x140004e86  test    r13, r13
0x140004e89  jz      short loc_140004E3A
0x140004e8b  mov     rdx, [rbx+20h]
0x140004e8f  lea     r9, TransferPktComplete
0x140004e96  mov     rcx, r13
0x140004e99  mov     rax, r12
0x140004e9c  mov     r8, [rdx+0B8h]
0x140004ea3  mov     [r8-10h], r9
0x140004ea7  mov     [r8-8], rbx
  ... truncated ...
```
