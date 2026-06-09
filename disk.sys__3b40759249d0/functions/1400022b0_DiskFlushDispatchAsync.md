# DiskFlushDispatchAsync

- ea: `0x1400022b0`
- end: `0x140002718`
- name: `DiskFlushDispatchAsync`
- size: `1128`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400019d0`
- `0x140002ac0`
- `0x140003710`

## callees

- `0x1400022b0`
- `0x1400034a0`
- `0x140004078`
- `0x1400041c0`
- `0x140006000`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000242c`
- `ntoskrnl!IofCallDriver` at `0x14000242c`
- `ntoskrnl!IoReuseIrp` at `0x1400024a6`
- `ntoskrnl!IoReuseIrp` at `0x1400024a6`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000232d`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000232d`
- `CLASSPNP!ClassSendSrbAsynchronous` at `0x1400025b6`
- `CLASSPNP!ClassSendSrbAsynchronous` at `0x1400025b6`
- `CLASSPNP!ClassAcquireRemoveLockEx` at `0x1400024c9`
- `CLASSPNP!ClassAcquireRemoveLockEx` at `0x1400024c9`

## pseudocode

```c
int __fastcall DiskFlushDispatchAsync(PDEVICE_OBJECT DeviceObject, __int64 a2)
{
  PVOID DeviceExtension; // rbp
  struct _SCSI_REQUEST_BLOCK *v3; // rbx
  int v6; // edi
  char v7; // si
  __int16 IoPriorityHint; // ax
  int v9; // eax
  int v10; // ecx
  bool v11; // si
  char v12; // cl
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned __int64 DataTransferLength; // rax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  _BYTE *v23; // rcx
  __int64 v24; // r8
  ULONG v25; // ecx
  __int64 SenseInfoBuffer_high; // rdx

  DeviceExtension = DeviceObject->DeviceExtension;
  v3 = (struct _SCSI_REQUEST_BLOCK *)(a2 + 48);
  if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 30LL) == 1 )
  {
    v6 = 308;
    memset(v3, 0, 0x134u);
    v3->Length = 8;
    v3->Function = 40;
    *(_DWORD *)&v3->QueueTag = 1397899864;
    v3->SrbFlags = 1;
    v7 = *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 31LL);
    if ( v7 != 1 )
      v6 = 184;
    *(_DWORD *)(a2 + 64) = v6;
    IoPriorityHint = IoGetIoPriorityHint(*(PIRP *)(a2 + 16));
    HIDWORD(v3->OriginalRequest) = 128;
    WORD2(v3->SenseInfoBuffer) = IoPriorityHint;
    v9 = *((_DWORD *)DeviceExtension + 146);
    LODWORD(v3->SenseInfoBuffer) = 255;
    HIWORD(v3->SenseInfoBuffer) = 32;
    LODWORD(v3->NextSrb) = 4 * v9;
    v10 = *((_DWORD *)DeviceExtension + 148);
    LODWORD(v3->DataBuffer) = v10;
    *(_QWORD *)&v3->Cdb[8] = *(_QWORD *)(a2 + 16);
    LODWORD(v3->DataBuffer) = v10 | 0x20000000;
    v11 = v7 == 1;
    LOWORD(v3[1].NextSrb) = 1;
    HIDWORD(v3[1].NextSrb) = 4;
  }
  else
  {
    v11 = 0;
    memset((void *)(a2 + 50), 0, 0x56u);
    v3->Length = 88;
    v3->TimeOutValue = 4 * *((_DWORD *)DeviceExtension + 146);
    *(_WORD *)&v3->QueueTag = 8447;
    v25 = *((_DWORD *)DeviceExtension + 148);
    v3->SrbFlags = v25;
    v3->OriginalRequest = *(PVOID *)(a2 + 16);
    v3->SrbFlags = v25 | 0x20000000;
  }
  v12 = *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 30LL);
  if ( (*((_WORD *)DeviceExtension + 320) & 1) == 0 )
  {
    if ( v12 == 1 )
    {
      v3->TimeOutValue = 8;
      LODWORD(v3->SrbExtension) = 0;
      LODWORD(v3[1].SenseInfoBuffer) = 0;
    }
    else
    {
      v3->Function = 8;
      v3->CdbLength = 0;
      v3->ScsiStatus = 0;
    }
    v3->SrbStatus = 0;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 16) + 184LL) + 32LL) = 0;
    v13 = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 184LL);
    *(_QWORD *)(v13 - 16) = DiskFlushComplete;
    *(_QWORD *)(v13 - 8) = 0;
    *(_BYTE *)(v13 - 69) = -32;
    v14 = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 184LL);
    *(_BYTE *)(v14 - 72) = 15;
    *(_QWORD *)(v14 - 64) = v3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        29,
        WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
        *(_QWORD *)(a2 + 16));
    }
    LODWORD(DataTransferLength) = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), *(PIRP *)(a2 + 16));
    return DataTransferLength;
  }
  if ( v12 == 1 )
  {
    v3->TimeOutValue = 0;
    if ( v11 )
    {
      *(_DWORD *)(a2 + 104) = 2;
      v16 = 148;
      HIDWORD(v3[1].SenseInfoBuffer) = 188;
    }
    else
    {
      *(_DWORD *)(a2 + 104) = 1;
      v16 = 144;
    }
    v17 = v16;
    LODWORD(v3[1].SenseInfoBuffer) = v16;
    DataTransferLength = v3->DataTransferLength;
    if ( v17 + 40 > DataTransferLength )
      return DataTransferLength;
    *(_DWORD *)((char *)&v3->Length + v17) = 64;
    *(_DWORD *)(&v3->ScsiStatus + v17) = 32;
    *(&v3->CdbLength + v17) = 10;
    *((_BYTE *)&v3->DataBuffer + v17) = 53;
    if ( v11 )
    {
      SenseInfoBuffer_high = HIDWORD(v3[1].SenseInfoBuffer);
      DataTransferLength = v3->DataTransferLength;
      if ( SenseInfoBuffer_high + 112 > DataTransferLength )
        return DataTransferLength;
      *(_DWORD *)((char *)&v3->Length + SenseInfoBuffer_high) = 67;
      *(_DWORD *)(&v3->ScsiStatus + SenseInfoBuffer_high) = 100;
    }
  }
  else
  {
    v3->Function = 0;
    v3->CdbLength = 10;
    v3->Cdb[0] = 53;
  }
  IoReuseIrp(*(PIRP *)(a2 + 392), -1073741637);
  ClassAcquireRemoveLockEx(DeviceObject, *(PVOID *)(a2 + 392), "minkernel\\storage\\disk\\disk.c", 0x7EDu);
  *(_QWORD *)(*(_QWORD *)(a2 + 392) + 152LL) = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 152LL);
  v18 = *(_QWORD *)(a2 + 392);
  --*(_BYTE *)(v18 + 67);
  *(_QWORD *)(v18 + 184) -= 72LL;
  v19 = *(_QWORD *)(*(_QWORD *)(a2 + 392) + 184LL);
  *(_QWORD *)(v19 + 8) = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(v19 + 40) = DeviceObject;
  v20 = *(_QWORD *)(*(_QWORD *)(a2 + 392) + 184LL);
  *(_QWORD *)(v20 - 16) = DiskFlushAsyncComplete;
  *(_QWORD *)(v20 - 8) = 0;
  *(_BYTE *)(v20 - 69) = -32;
  v21 = *(_QWORD *)(a2 + 392);
  --*(_BYTE *)(v21 + 67);
  *(_QWORD *)(v21 + 184) -= 72LL;
  v22 = *(_QWORD *)(*(_QWORD *)(a2 + 392) + 184LL);
  *(_QWORD *)(v22 + 40) = DeviceObject;
  v23 = *(_BYTE **)(*(_QWORD *)(a2 + 16) + 184LL);
  *(_BYTE *)v22 = *v23;
  *(_BYTE *)(v22 + 1) = v23[1];
  *(_BYTE *)(v22 + 2) = v23[2];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
  }
  LODWORD(DataTransferLength) = ClassSendSrbAsynchronous(DeviceObject, v3, *(PIRP *)(a2 + 392), 0, 0, 1u);
  if ( (_DWORD)DataTransferLength != 259
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    LODWORD(DataTransferLength) = WPP_SF_L(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    28,
                                    v24,
                                    (unsigned int)DataTransferLength);
  }
  return DataTransferLength;
}

```

## disassembly

```asm
0x1400022b0  push    rbx
0x1400022b2  push    rbp
0x1400022b3  push    rsi
0x1400022b4  push    rdi
0x1400022b5  push    r12
0x1400022b7  push    r13
0x1400022b9  push    r14
0x1400022bb  push    r15
0x1400022bd  sub     rsp, 38h
0x1400022c1  mov     rbp, [rcx+40h]
0x1400022c5  lea     rbx, [rdx+30h]
0x1400022c9  mov     r14, rdx
0x1400022cc  mov     r15, rcx
0x1400022cf  mov     r13d, 8
0x1400022d5  mov     rax, [rbp+210h]
0x1400022dc  cmp     byte ptr [rax+1Eh], 1
0x1400022e0  jnz     loc_14000260A
0x1400022e6  mov     edi, 134h
0x1400022eb  xor     edx, edx; Val
0x1400022ed  mov     r8d, edi; Size
0x1400022f0  mov     rcx, rbx; void *
0x1400022f3  call    memset
0x1400022f8  mov     [rbx], r13w
0x1400022fc  mov     byte ptr [rbx+2], 28h ; '('
0x140002300  mov     dword ptr [rbx+8], 53524258h
0x140002307  mov     dword ptr [rbx+0Ch], 1
0x14000230e  mov     rax, [rbp+210h]
0x140002315  movzx   esi, byte ptr [rax+1Fh]
0x140002319  mov     eax, 0B8h
0x14000231e  cmp     sil, 1
0x140002322  cmovnz  edi, eax
0x140002325  mov     [r14+40h], edi
0x140002329  mov     rcx, [r14+10h]; Irp
0x14000232d  call    cs:__imp_IoGetIoPriorityHint
0x140002334  nop     dword ptr [rax+rax+00h]
0x140002339  mov     dword ptr [rbx+34h], 80h
0x140002340  mov     edx, 1
0x140002345  mov     [rbx+24h], ax
0x140002349  mov     r8d, 20h ; ' '
0x14000234f  mov     eax, [rbp+248h]
0x140002355  mov     dword ptr [rbx+20h], 0FFh
0x14000235c  mov     [rbx+26h], r8w
0x140002361  shl     eax, 2
0x140002364  mov     [rbx+28h], eax
0x140002367  mov     ecx, [rbp+250h]
0x14000236d  mov     [rbx+18h], ecx
0x140002370  bts     ecx, 1Dh
0x140002374  mov     rax, [r14+10h]
0x140002378  cmp     sil, dl
0x14000237b  mov     [rbx+50h], rax
0x14000237f  mov     [rbx+18h], ecx
0x140002382  setz    sil
0x140002386  mov     [rbx+80h], dx
0x14000238d  mov     dword ptr [rbx+84h], 4
0x140002397  movzx   eax, word ptr [rbp+280h]
0x14000239e  bt      ax, 0
0x1400023a3  mov     rax, [rbp+210h]
0x1400023aa  movzx   ecx, byte ptr [rax+1Eh]
0x1400023ae  jb      loc_14000244A
0x1400023b4  xor     edi, edi
0x1400023b6  cmp     cl, 1
0x1400023b9  jnz     loc_14000265D
0x1400023bf  mov     [rbx+14h], r13d
0x1400023c3  mov     [rbx+38h], edi
0x1400023c6  mov     [rbx+78h], edi
0x1400023c9  mov     [rbx+3], dil
0x1400023cd  mov     rax, [r14+10h]
0x1400023d1  mov     rcx, [rax+0B8h]
0x1400023d8  mov     [rcx+20h], rdi
0x1400023dc  mov     rax, [r14+10h]
0x1400023e0  mov     rcx, [rax+0B8h]
0x1400023e7  lea     rax, DiskFlushComplete
0x1400023ee  mov     [rcx-10h], rax
0x1400023f2  mov     [rcx-8], rdi
0x1400023f6  mov     byte ptr [rcx-45h], 0E0h
0x1400023fa  mov     rax, [r14+10h]
0x1400023fe  mov     rcx, [rax+0B8h]
0x140002405  mov     byte ptr [rcx-48h], 0Fh
0x140002409  mov     [rcx-40h], rbx
0x14000240d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002414  lea     rsi, WPP_GLOBAL_Control
0x14000241b  cmp     rcx, rsi
0x14000241e  jnz     loc_1400026E3
0x140002424  mov     rdx, [r14+10h]; Irp
0x140002428  mov     rcx, [rbp+10h]; DeviceObject
0x14000242c  call    cs:__imp_IofCallDriver
0x140002433  nop     dword ptr [rax+rax+00h]
0x140002438  add     rsp, 38h
0x14000243c  pop     r15
0x14000243e  pop     r14
0x140002440  pop     r13
0x140002442  pop     r12
0x140002444  pop     rdi
0x140002445  pop     rsi
0x140002446  pop     rbp
0x140002447  pop     rbx
0x140002448  retn
0x14000244a  xor     edi, edi
0x14000244c  cmp     cl, 1
0x14000244f  jnz     loc_14000266E
0x140002455  mov     [rbx+14h], edi
0x140002458  test    sil, sil
0x14000245b  jnz     loc_14000267F
0x140002461  mov     [r14+68h], edx
0x140002465  mov     eax, 90h
0x14000246a  mov     edx, eax
0x14000246c  mov     [rbx+78h], eax
0x14000246f  mov     eax, [rbx+10h]
0x140002472  lea     rcx, [rdx+28h]
0x140002476  cmp     rcx, rax
0x140002479  ja      short loc_140002438
0x14000247b  mov     dword ptr [rdx+rbx], 40h ; '@'
0x140002482  mov     [rdx+rbx+4], r8d
0x140002487  mov     byte ptr [rdx+rbx+0Ah], 0Ah
0x14000248c  mov     byte ptr [rdx+rbx+18h], 35h ; '5'
0x140002491  test    sil, sil
0x140002494  jnz     loc_140002698
0x14000249a  mov     rcx, [r14+188h]; Irp
0x1400024a1  mov     edx, 0C00000BBh; Iostatus
0x1400024a6  call    cs:__imp_IoReuseIrp
0x1400024ad  nop     dword ptr [rax+rax+00h]
0x1400024b2  mov     rdx, [r14+188h]; Tag
0x1400024b9  lea     r8, File; "minkernel\\storage\\disk\\disk.c"
0x1400024c0  mov     r9d, 7EDh; Line
0x1400024c6  mov     rcx, r15; DeviceObject
0x1400024c9  call    cs:__imp_ClassAcquireRemoveLockEx
0x1400024d0  nop     dword ptr [rax+rax+00h]
0x1400024d5  mov     rax, [r14+10h]
0x1400024d9  mov     rcx, [r14+188h]
0x1400024e0  mov     rax, [rax+98h]
0x1400024e7  mov     [rcx+98h], rax
0x1400024ee  mov     rax, [r14+188h]
0x1400024f5  dec     byte ptr [rax+43h]
0x1400024f8  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140002500  mov     rax, [r14+188h]
0x140002507  mov     rcx, [rax+0B8h]
0x14000250e  mov     rax, [r14+10h]
0x140002512  mov     [rcx+8], rax
0x140002516  mov     [rcx+28h], r15
0x14000251a  mov     rax, [r14+188h]
0x140002521  mov     rcx, [rax+0B8h]
0x140002528  lea     rax, DiskFlushAsyncComplete
0x14000252f  mov     [rcx-10h], rax
0x140002533  mov     [rcx-8], rdi
0x140002537  mov     byte ptr [rcx-45h], 0E0h
0x14000253b  mov     rax, [r14+188h]
0x140002542  dec     byte ptr [rax+43h]
0x140002545  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x14000254d  mov     rax, [r14+188h]
0x140002554  mov     rdx, [rax+0B8h]
0x14000255b  mov     [rdx+28h], r15
0x14000255f  mov     rax, [r14+10h]
0x140002563  mov     rcx, [rax+0B8h]
0x14000256a  movzx   eax, byte ptr [rcx]
0x14000256d  mov     [rdx], al
0x14000256f  movzx   eax, byte ptr [rcx+1]
0x140002573  mov     [rdx+1], al
0x140002576  movzx   eax, byte ptr [rcx+2]
0x14000257a  mov     [rdx+2], al
0x14000257d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002584  lea     rsi, WPP_GLOBAL_Control
0x14000258b  cmp     rcx, rsi
0x14000258e  jz      short loc_14000259D
0x140002590  test    dword ptr [rcx+2Ch], 20000h
0x140002597  jnz     loc_1400026BF
0x14000259d  mov     r8, [r14+188h]; Irp
0x1400025a4  xor     r9d, r9d; BufferAddress
0x1400025a7  mov     [rsp+78h+WriteToDevice], 1; WriteToDevice
0x1400025ac  mov     rdx, rbx; Srb
0x1400025af  mov     rcx, r15; DeviceObject
0x1400025b2  mov     [rsp+78h+BufferLength], edi; BufferLength
0x1400025b6  call    cs:__imp_ClassSendSrbAsynchronous
0x1400025bd  nop     dword ptr [rax+rax+00h]
0x1400025c2  cmp     eax, 103h
0x1400025c7  jz      loc_140002438
0x1400025cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025d4  cmp     rcx, rsi
0x1400025d7  jz      loc_140002438
0x1400025dd  test    dword ptr [rcx+2Ch], 20000h
0x1400025e4  jz      loc_140002438
0x1400025ea  cmp     byte ptr [rcx+29h], 2
0x1400025ee  jb      loc_140002438
0x1400025f4  mov     rcx, [rcx+18h]
0x1400025f8  mov     edx, 1Ch
0x1400025fd  mov     r9d, eax
0x140002600  call    WPP_SF_L
0x140002605  jmp     loc_140002438
0x14000260a  lea     rcx, [rdx+32h]; void *
0x14000260e  mov     r8d, 56h ; 'V'; Size
0x140002614  xor     edx, edx; Val
0x140002616  xor     sil, sil
0x140002619  call    memset
0x14000261e  mov     word ptr [rbx], 58h ; 'X'
0x140002623  mov     edx, 1
0x140002628  mov     eax, [rbp+248h]
0x14000262e  mov     r8d, 20h ; ' '
0x140002634  shl     eax, 2
0x140002637  mov     [rbx+14h], eax
0x14000263a  mov     word ptr [rbx+8], 20FFh
0x140002640  mov     ecx, [rbp+250h]
0x140002646  mov     [rbx+0Ch], ecx
0x140002649  bts     ecx, 1Dh
0x14000264d  mov     rax, [r14+10h]
0x140002651  mov     [rbx+30h], rax
0x140002655  mov     [rbx+0Ch], ecx
0x140002658  jmp     loc_140002397
0x14000265d  mov     [rbx+2], r13b
0x140002661  mov     [rbx+0Ah], dil
0x140002665  mov     [rbx+4], dil
0x140002669  jmp     loc_1400023C9
0x14000266e  mov     [rbx+2], dil
0x140002672  mov     byte ptr [rbx+0Ah], 0Ah
0x140002676  mov     byte ptr [rbx+48h], 35h ; '5'
0x14000267a  jmp     loc_14000249A
0x14000267f  mov     dword ptr [r14+68h], 2
0x140002687  mov     eax, 94h
0x14000268c  mov     dword ptr [rbx+7Ch], 0BCh
0x140002693  jmp     loc_14000246A
0x140002698  mov     edx, [rbx+7Ch]
0x14000269b  mov     eax, [rbx+10h]
0x14000269e  lea     rcx, [rdx+70h]
0x1400026a2  cmp     rcx, rax
0x1400026a5  ja      loc_140002438
0x1400026ab  mov     dword ptr [rdx+rbx], 43h ; 'C'
0x1400026b2  mov     dword ptr [rdx+rbx+4], 64h ; 'd'
0x1400026ba  jmp     loc_14000249A
0x1400026bf  cmp     byte ptr [rcx+29h], 5
0x1400026c3  jb      loc_14000259D
0x1400026c9  mov     rcx, [rcx+18h]
0x1400026cd  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400026d4  mov     edx, 1Bh
0x1400026d9  call    WPP_SF_
0x1400026de  jmp     loc_14000259D
0x1400026e3  test    dword ptr [rcx+2Ch], 20000h
0x1400026ea  jz      loc_140002424
0x1400026f0  cmp     byte ptr [rcx+29h], 5
0x1400026f4  jb      loc_140002424
0x1400026fa  mov     r9, [r14+10h]
0x1400026fe  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140002705  mov     rcx, [rcx+18h]
0x140002709  mov     edx, 1Dh
0x14000270e  call    WPP_SF_q
0x140002713  jmp     loc_140002424
```
