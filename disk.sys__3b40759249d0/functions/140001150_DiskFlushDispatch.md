# DiskFlushDispatch

- ea: `0x140001150`
- end: `0x140001492`
- name: `DiskFlushDispatch`
- size: `834`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140002ac0`

## callees

- `0x140001150`
- `0x1400034a0`
- `0x140004078`
- `0x140006000`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400012d8`
- `ntoskrnl!IofCallDriver` at `0x1400012d8`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000135e`
- `ntoskrnl!IoGetIoPriorityHint` at `0x14000135e`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000122e`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x14000122e`

## pseudocode

```c
int __fastcall DiskFlushDispatch(PDEVICE_OBJECT DeviceObject, __int64 a2)
{
  PVOID DeviceExtension; // rbp
  struct _SCSI_REQUEST_BLOCK *v3; // rbx
  UCHAR *p_Function; // rsi
  NTSTATUS v7; // r12d
  bool v8; // r8
  void *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 DataTransferLength; // rax
  __int64 v13; // rcx
  int v14; // edi
  char v15; // si
  __int16 IoPriorityHint; // ax
  bool v17; // zf
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 SenseInfoBuffer_high; // rdx

  DeviceExtension = DeviceObject->DeviceExtension;
  v3 = (struct _SCSI_REQUEST_BLOCK *)(a2 + 48);
  p_Function = (UCHAR *)(a2 + 50);
  v7 = 0;
  if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 30LL) == 1 )
  {
    v14 = 308;
    memset(v3, 0, 0x134u);
    v3->Length = 8;
    *p_Function = 40;
    *(_DWORD *)&v3->QueueTag = 1397899864;
    v3->SrbFlags = 1;
    v15 = *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 31LL);
    if ( v15 != 1 )
      v14 = 184;
    *(_DWORD *)(a2 + 64) = v14;
    IoPriorityHint = IoGetIoPriorityHint(*(PIRP *)(a2 + 16));
    HIDWORD(v3->OriginalRequest) = 128;
    WORD2(v3->SenseInfoBuffer) = IoPriorityHint;
    v17 = v15 == 1;
    LODWORD(v3->NextSrb) = 4 * *((_DWORD *)DeviceExtension + 146);
    LODWORD(v3->SenseInfoBuffer) = 255;
    p_Function = &v3->Function;
    HIWORD(v3->SenseInfoBuffer) = 32;
    v8 = v17;
    LODWORD(v3->DataBuffer) = *((_DWORD *)DeviceExtension + 148);
    LOWORD(v3[1].NextSrb) = 1;
    HIDWORD(v3[1].NextSrb) = 4;
  }
  else
  {
    *(_OWORD *)(a2 + 50) = 0;
    v8 = 0;
    *(_OWORD *)(a2 + 66) = 0;
    *(_OWORD *)(a2 + 82) = 0;
    *(_OWORD *)(a2 + 98) = 0;
    *(_OWORD *)(a2 + 114) = 0;
    *(_QWORD *)(a2 + 128) = 0;
    v3->Length = 88;
    *(_DWORD *)(a2 + 68) = 4 * *((_DWORD *)DeviceExtension + 146);
    *(_WORD *)(a2 + 56) = 8447;
    *(_DWORD *)(a2 + 60) = *((_DWORD *)DeviceExtension + 148);
  }
  if ( (*((_WORD *)DeviceExtension + 320) & 1) == 0 )
    goto LABEL_9;
  if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 30LL) != 1 )
  {
    *p_Function = 0;
    v3->CdbLength = 10;
    v3->Cdb[0] = 53;
LABEL_6:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x19u,
        (__int64)WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    v7 = ClassSendSrbSynchronous(DeviceObject, v3, 0, 0, 1u);
LABEL_9:
    if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 30LL) == 1 )
    {
      v3->TimeOutValue = 8;
      LODWORD(v3->SrbExtension) = 0;
      LODWORD(v3[1].SenseInfoBuffer) = 0;
      v13 = *(_QWORD *)(a2 + 16);
      LODWORD(v3->DataBuffer) |= 0x20000000u;
      *(_QWORD *)&v3->Cdb[8] = v13;
    }
    else
    {
      v3->Function = 8;
      v3->CdbLength = 0;
      v9 = *(void **)(a2 + 16);
      v3->SrbFlags |= 0x20000000u;
      v3->OriginalRequest = v9;
      v3->ScsiStatus = 0;
    }
    v3->SrbStatus = 0;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 16) + 184LL) + 32LL) = 0;
    v10 = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 184LL);
    *(_BYTE *)(v10 - 72) = 15;
    *(_QWORD *)(v10 - 64) = v3;
    v11 = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 184LL);
    *(_QWORD *)(v11 - 16) = DiskFlushComplete;
    *(_QWORD *)(v11 - 8) = v7;
    *(_BYTE *)(v11 - 69) = -32;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_0d021951613e35be7880fae860fb7f50_Traceguids,
        *(_QWORD *)(a2 + 16));
    }
    LODWORD(DataTransferLength) = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), *(PIRP *)(a2 + 16));
    return DataTransferLength;
  }
  v3->TimeOutValue = 0;
  if ( v8 )
  {
    *(_DWORD *)(a2 + 104) = 2;
    v18 = 148;
    HIDWORD(v3[1].SenseInfoBuffer) = 188;
  }
  else
  {
    *(_DWORD *)(a2 + 104) = 1;
    v18 = 144;
  }
  v19 = v18;
  LODWORD(v3[1].SenseInfoBuffer) = v18;
  DataTransferLength = v3->DataTransferLength;
  if ( v19 + 40 <= DataTransferLength )
  {
    *(_DWORD *)((char *)&v3->Length + v19) = 64;
    *(_DWORD *)(&v3->ScsiStatus + v19) = 32;
    *(&v3->CdbLength + v19) = 10;
    *((_BYTE *)&v3->DataBuffer + v19) = 53;
    if ( v8 )
    {
      SenseInfoBuffer_high = HIDWORD(v3[1].SenseInfoBuffer);
      DataTransferLength = v3->DataTransferLength;
      if ( SenseInfoBuffer_high + 112 > DataTransferLength )
        return DataTransferLength;
      *(_DWORD *)((char *)&v3->Length + SenseInfoBuffer_high) = 67;
      *(_DWORD *)(&v3->ScsiStatus + SenseInfoBuffer_high) = 100;
    }
    goto LABEL_6;
  }
  return DataTransferLength;
}

```

## disassembly

```asm
0x140001150  push    rbx
0x140001152  push    rbp
0x140001153  push    rsi
0x140001154  push    rdi
0x140001155  push    r12
0x140001157  push    r13
0x140001159  push    r14
0x14000115b  push    r15
0x14000115d  sub     rsp, 38h
0x140001161  mov     rbp, [rcx+40h]
0x140001165  lea     rbx, [rdx+30h]
0x140001169  xor     edi, edi
0x14000116b  lea     rsi, [rbx+2]
0x14000116f  mov     r13, rcx
0x140001172  mov     r15, rdx
0x140001175  mov     ecx, 1
0x14000117a  mov     r12d, edi
0x14000117d  mov     rax, [rbp+210h]
0x140001184  mov     r10d, 20h ; ' '
0x14000118a  cmp     [rax+1Eh], cl
0x14000118d  jz      loc_140001317
0x140001193  xorps   xmm0, xmm0
0x140001196  xor     eax, eax
0x140001198  movups  xmmword ptr [rdx+32h], xmm0
0x14000119c  xor     r8b, r8b
0x14000119f  movups  xmmword ptr [rdx+42h], xmm0
0x1400011a3  movups  xmmword ptr [rdx+52h], xmm0
0x1400011a7  movups  xmmword ptr [rdx+62h], xmm0
0x1400011ab  movups  xmmword ptr [rdx+72h], xmm0
0x1400011af  mov     [rdx+80h], rax
0x1400011b6  mov     word ptr [rbx], 58h ; 'X'
0x1400011bb  mov     eax, [rbp+248h]
0x1400011c1  shl     eax, 2
0x1400011c4  mov     [rbx+14h], eax
0x1400011c7  mov     word ptr [rbx+8], 20FFh
0x1400011cd  mov     eax, [rbp+250h]
0x1400011d3  mov     [rbx+0Ch], eax
0x1400011d6  movzx   eax, word ptr [rbp+280h]
0x1400011dd  lea     r9, WPP_GLOBAL_Control
0x1400011e4  test    al, 1
0x1400011e6  jz      short loc_140001244
0x1400011e8  mov     rax, [rbp+210h]
0x1400011ef  cmp     byte ptr [rax+1Eh], 1
0x1400011f3  jz      loc_1400013C4
0x1400011f9  mov     [rsi], r12b
0x1400011fc  mov     byte ptr [rbx+0Ah], 0Ah
0x140001200  mov     byte ptr [rbx+48h], 35h ; '5'
0x140001204  mov     rcx, cs:WPP_GLOBAL_Control
0x14000120b  cmp     rcx, r9
0x14000120e  jz      short loc_14000121D
0x140001210  test    dword ptr [rcx+2Ch], 20000h
0x140001217  jnz     loc_140001446
0x14000121d  xor     r9d, r9d; BufferLength
0x140001220  mov     [rsp+78h+WriteToDevice], 1; WriteToDevice
0x140001225  xor     r8d, r8d; BufferAddress
0x140001228  mov     rdx, rbx; Srb
0x14000122b  mov     rcx, r13; DeviceObject
0x14000122e  call    cs:__imp_ClassSendSrbSynchronous
0x140001235  nop     dword ptr [rax+rax+00h]
0x14000123a  mov     r12d, eax
0x14000123d  lea     r9, WPP_GLOBAL_Control
0x140001244  mov     rcx, [rbp+210h]
0x14000124b  cmp     byte ptr [rcx+1Eh], 1
0x14000124f  jz      loc_1400012F6
0x140001255  mov     byte ptr [rbx+2], 8
0x140001259  mov     byte ptr [rbx+0Ah], 0
0x14000125d  mov     rax, [r15+10h]
0x140001261  or      dword ptr [rbx+0Ch], 20000000h
0x140001268  mov     [rbx+30h], rax
0x14000126c  mov     byte ptr [rbx+4], 0
0x140001270  mov     byte ptr [rbx+3], 0
0x140001274  mov     rax, [r15+10h]
0x140001278  mov     rcx, [rax+0B8h]
0x14000127f  mov     [rcx+20h], rdi
0x140001283  mov     rax, [r15+10h]
0x140001287  mov     rcx, [rax+0B8h]
0x14000128e  mov     byte ptr [rcx-48h], 0Fh
0x140001292  mov     [rcx-40h], rbx
0x140001296  mov     rax, [r15+10h]
0x14000129a  mov     rcx, [rax+0B8h]
0x1400012a1  lea     rax, DiskFlushComplete
0x1400012a8  mov     [rcx-10h], rax
0x1400012ac  movsxd  rax, r12d
0x1400012af  mov     [rcx-8], rax
0x1400012b3  mov     byte ptr [rcx-45h], 0E0h
0x1400012b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012be  cmp     rcx, r9
0x1400012c1  jz      short loc_1400012D0
0x1400012c3  test    dword ptr [rcx+2Ch], 20000h
0x1400012ca  jnz     loc_14000146A
0x1400012d0  mov     rdx, [r15+10h]; Irp
0x1400012d4  mov     rcx, [rbp+10h]; DeviceObject
0x1400012d8  call    cs:__imp_IofCallDriver
0x1400012df  nop     dword ptr [rax+rax+00h]
0x1400012e4  add     rsp, 38h
0x1400012e8  pop     r15
0x1400012ea  pop     r14
0x1400012ec  pop     r13
0x1400012ee  pop     r12
0x1400012f0  pop     rdi
0x1400012f1  pop     rsi
0x1400012f2  pop     rbp
0x1400012f3  pop     rbx
0x1400012f4  retn
0x1400012f6  mov     dword ptr [rbx+14h], 8
0x1400012fd  mov     [rbx+38h], edi
0x140001300  mov     [rbx+78h], edi
0x140001303  mov     rcx, [r15+10h]
0x140001307  or      dword ptr [rbx+18h], 20000000h
0x14000130e  mov     [rbx+50h], rcx
0x140001312  jmp     loc_140001270
0x140001317  mov     edi, 134h
0x14000131c  xor     edx, edx; Val
0x14000131e  mov     r8d, edi; Size
0x140001321  mov     rcx, rbx; void *
0x140001324  call    memset
0x140001329  mov     word ptr [rbx], 8
0x14000132e  mov     byte ptr [rsi], 28h ; '('
0x140001331  mov     dword ptr [rbx+8], 53524258h
0x140001338  mov     dword ptr [rbx+0Ch], 1
0x14000133f  mov     rax, [rbp+210h]
0x140001346  movzx   esi, byte ptr [rax+1Fh]
0x14000134a  mov     eax, 0B8h
0x14000134f  cmp     sil, 1
0x140001353  cmovnz  edi, eax
0x140001356  mov     [r15+40h], edi
0x14000135a  mov     rcx, [r15+10h]; Irp
0x14000135e  call    cs:__imp_IoGetIoPriorityHint
0x140001365  nop     dword ptr [rax+rax+00h]
0x14000136a  mov     dword ptr [rbx+34h], 80h
0x140001371  mov     ecx, 1
0x140001376  mov     [rbx+24h], ax
0x14000137a  mov     r10d, 20h ; ' '
0x140001380  mov     eax, [rbp+248h]
0x140001386  shl     eax, 2
0x140001389  cmp     sil, cl
0x14000138c  mov     [rbx+28h], eax
0x14000138f  mov     dword ptr [rbx+20h], 0FFh
0x140001396  lea     rsi, [rbx+2]
0x14000139a  mov     [rbx+26h], r10w
0x14000139f  setz    r8b
0x1400013a3  mov     eax, [rbp+250h]
0x1400013a9  xor     edi, edi
0x1400013ab  mov     [rbx+18h], eax
0x1400013ae  mov     [rbx+80h], cx
0x1400013b5  mov     dword ptr [rbx+84h], 4
0x1400013bf  jmp     loc_1400011D6
0x1400013c4  mov     [rbx+14h], edi
0x1400013c7  test    r8b, r8b
0x1400013ca  jnz     short loc_140001430
0x1400013cc  mov     [r15+68h], ecx
0x1400013d0  mov     eax, 90h
0x1400013d5  mov     edx, eax
0x1400013d7  mov     [rbx+78h], eax
0x1400013da  mov     eax, [rbx+10h]
0x1400013dd  lea     rcx, [rdx+28h]
0x1400013e1  cmp     rcx, rax
0x1400013e4  ja      loc_1400012E4
0x1400013ea  mov     dword ptr [rdx+rbx], 40h ; '@'
0x1400013f1  mov     [rdx+rbx+4], r10d
0x1400013f6  mov     byte ptr [rdx+rbx+0Ah], 0Ah
0x1400013fb  mov     byte ptr [rdx+rbx+18h], 35h ; '5'
0x140001400  test    r8b, r8b
0x140001403  jz      loc_140001204
0x140001409  mov     edx, [rbx+7Ch]
0x14000140c  mov     eax, [rbx+10h]
0x14000140f  lea     rcx, [rdx+70h]
0x140001413  cmp     rcx, rax
0x140001416  ja      loc_1400012E4
0x14000141c  mov     dword ptr [rdx+rbx], 43h ; 'C'
0x140001423  mov     dword ptr [rdx+rbx+4], 64h ; 'd'
0x14000142b  jmp     loc_140001204
0x140001430  mov     dword ptr [r15+68h], 2
0x140001438  mov     eax, 94h
0x14000143d  mov     dword ptr [rbx+7Ch], 0BCh
0x140001444  jmp     short loc_1400013D5
0x140001446  cmp     byte ptr [rcx+29h], 5
0x14000144a  jb      loc_14000121D
0x140001450  mov     rcx, [rcx+18h]
0x140001454  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000145b  mov     edx, 19h
0x140001460  call    WPP_SF_
0x140001465  jmp     loc_14000121D
0x14000146a  cmp     byte ptr [rcx+29h], 5
0x14000146e  jb      loc_1400012D0
0x140001474  mov     r9, [r15+10h]
0x140001478  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000147f  mov     rcx, [rcx+18h]
0x140001483  mov     edx, 1Ah
0x140001488  call    WPP_SF_q
0x14000148d  jmp     loc_1400012D0
```
