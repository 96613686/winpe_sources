# MouHid_IOCTL

- ea: `0x140001100`
- end: `0x14000135b`
- name: `MouHid_IOCTL`
- size: `603`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001100`
- `0x140001464`
- `0x140001524`
- `0x14000163c`
- `0x14000171c`
- `0x140001808`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001161`
- `ntoskrnl!IofCompleteRequest` at `0x1400012ed`
- `ntoskrnl!IofCompleteRequest` at `0x140001161`
- `ntoskrnl!IofCompleteRequest` at `0x1400012ed`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001305`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001305`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001145`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140001145`

## pseudocode

```c
__int64 __fastcall MouHid_IOCTL(__int64 a1, IRP *a2)
{
  __int64 v2; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  char v4; // r15
  NTSTATUS v6; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ebx
  DWORD LowPart; // edi
  int v12; // r9d
  struct _IRP *MasterIrp; // rdx
  int v14; // edx
  int RemlockSize; // [rsp+20h] [rbp-68h]

  v2 = *(_QWORD *)(a1 + 64);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v4 = a1;
  a2->IoStatus.Information = 0;
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 240), a2, File, 1u, 0x20u);
  v10 = v6;
  if ( v6 < 0 )
  {
    a2->IoStatus.Status = v6;
    IofCompleteRequest(a2, 0);
    return v10;
  }
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqL(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      v9,
      RemlockSize,
      v4,
      (char)a2,
      CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
  if ( LowPart == 983040 )
  {
    if ( CurrentStackLocation->Parameters.Read.Length < 0xC )
    {
      v10 = -1073741789;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Ld(WPP_GLOBAL_Control->DeviceExtension);
      goto LABEL_27;
    }
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    *(_QWORD *)&MasterIrp->Type = *(_QWORD *)(v2 + 376);
    LODWORD(MasterIrp->MdlAddress) = *(_DWORD *)(v2 + 384);
    a2->IoStatus.Information = 12;
    goto LABEL_26;
  }
  if ( LowPart != 983555 )
  {
    if ( LowPart == 984067 )
    {
      v10 = -1073741822;
    }
    else if ( LowPart == 985091 || LowPart == 987139 )
    {
      v10 = -1073741637;
    }
    else
    {
      v10 = -1073741808;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_Dd(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          3,
          v9,
          (__int64)WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids,
          LowPart,
          16);
      }
    }
    goto LABEL_27;
  }
  if ( !*(_QWORD *)(v2 + 232) )
  {
    if ( CurrentStackLocation->Parameters.Create.Options < 0x10 )
    {
      v10 = -1073741811;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_27;
      v12 = 12;
      goto LABEL_17;
    }
    *(_OWORD *)(v2 + 224) = *(_OWORD *)&CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
LABEL_26:
    v10 = 0;
    goto LABEL_27;
  }
  v10 = -1073741757;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = 11;
LABEL_17:
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      3,
      v12,
      (__int64)WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids,
      v10);
  }
LABEL_27:
  a2->IoStatus.Status = v10;
  IofCompleteRequest(a2, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 240), a2, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      3,
      15,
      (__int64)WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids);
  }
  return v10;
}

```

## disassembly

```asm
0x140001100  push    rbx
0x140001102  push    rbp
0x140001103  push    rsi
0x140001104  push    rdi
0x140001105  push    r12
0x140001107  push    r13
0x140001109  push    r14
0x14000110b  push    r15
0x14000110d  sub     rsp, 48h
0x140001111  mov     r14, [rcx+40h]
0x140001115  lea     r8, File; File
0x14000111c  mov     rbp, [rdx+0B8h]
0x140001123  xor     eax, eax
0x140001125  mov     r15, rcx
0x140001128  mov     [rdx+38h], rax
0x14000112c  mov     rsi, rdx
0x14000112f  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x140001137  lea     r12, [r14+0F0h]
0x14000113e  mov     rcx, r12; RemoveLock
0x140001141  lea     r9d, [rax+1]; Line
0x140001145  call    cs:__imp_IoAcquireRemoveLockEx
0x14000114c  nop     dword ptr [rax+rax+00h]
0x140001151  xor     ecx, ecx
0x140001153  mov     ebx, eax
0x140001155  test    eax, eax
0x140001157  jns     short loc_140001172
0x140001159  xor     edx, edx; PriorityBoost
0x14000115b  mov     [rsi+30h], eax
0x14000115e  mov     rcx, rsi; Irp
0x140001161  call    cs:__imp_IofCompleteRequest
0x140001168  nop     dword ptr [rax+rax+00h]
0x14000116d  jmp     loc_140001347
0x140001172  mov     edi, [rbp+18h]
0x140001175  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000117c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140001183  jz      short loc_1400011A5
0x140001185  mov     rcx, cs:WPP_GLOBAL_Control
0x14000118c  mov     [rsp+88h+var_50], edi
0x140001190  mov     [rsp+88h+var_58], rsi
0x140001195  mov     [rsp+88h+var_60], r15
0x14000119a  mov     rcx, [rcx+40h]
0x14000119e  call    WPP_RECORDER_SF_qqL
0x1400011a3  xor     ecx, ecx
0x1400011a5  lea     rax, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids
0x1400011ac  mov     r15d, 3
0x1400011b2  cmp     edi, 0F0000h
0x1400011b8  jz      loc_14000129A
0x1400011be  cmp     edi, 0F0203h
0x1400011c4  jz      short loc_14000122B
0x1400011c6  cmp     edi, 0F0403h
0x1400011cc  jz      short loc_140001221
0x1400011ce  cmp     edi, 0F0803h
0x1400011d4  jz      short loc_140001217
0x1400011d6  cmp     edi, 0F1003h
0x1400011dc  jz      short loc_140001217
0x1400011de  mov     ebx, 0C0000010h
0x1400011e3  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400011ea  jz      loc_1400012E5
0x1400011f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400011f7  mov     r8d, r15d
0x1400011fa  mov     dword ptr [rsp+88h+var_58], ebx
0x1400011fe  mov     dl, 2
0x140001200  mov     dword ptr [rsp+88h+var_60], edi
0x140001204  mov     qword ptr [rsp+88h+RemlockSize], rax
0x140001209  mov     rcx, [rcx+40h]
0x14000120d  call    WPP_RECORDER_SF_Dd
0x140001212  jmp     loc_1400012E5
0x140001217  mov     ebx, 0C00000BBh
0x14000121c  jmp     loc_1400012E5
0x140001221  mov     ebx, 0C0000002h
0x140001226  jmp     loc_1400012E5
0x14000122b  cmp     [r14+0E8h], rcx
0x140001232  jz      short loc_14000126C
0x140001234  mov     ebx, 0C0000043h
0x140001239  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140001240  jz      loc_1400012E5
0x140001246  mov     r9d, 0Bh
0x14000124c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001253  mov     r8d, r15d
0x140001256  mov     dword ptr [rsp+88h+var_60], ebx
0x14000125a  mov     dl, 2
0x14000125c  mov     qword ptr [rsp+88h+RemlockSize], rax
0x140001261  mov     rcx, [rcx+40h]
0x140001265  call    WPP_RECORDER_SF_d
0x14000126a  jmp     short loc_1400012E5
0x14000126c  cmp     dword ptr [rbp+10h], 10h
0x140001270  jnb     short loc_140001288
0x140001272  mov     ebx, 0C000000Dh
0x140001277  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14000127e  jz      short loc_1400012E5
0x140001280  mov     r9d, 0Ch
0x140001286  jmp     short loc_14000124C
0x140001288  mov     rax, [rbp+20h]
0x14000128c  movups  xmm0, xmmword ptr [rax]
0x14000128f  movdqu  xmmword ptr [r14+0E0h], xmm0
0x140001298  jmp     short loc_1400012E3
0x14000129a  cmp     dword ptr [rbp+8], 0Ch
0x14000129e  jnb     short loc_1400012C0
0x1400012a0  mov     ebx, 0C0000023h
0x1400012a5  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400012ac  jz      short loc_1400012E5
0x1400012ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400012b5  mov     rcx, [rcx+40h]
0x1400012b9  call    WPP_RECORDER_SF_Ld
0x1400012be  jmp     short loc_1400012E5
0x1400012c0  movsd   xmm0, qword ptr [r14+178h]
0x1400012c9  mov     rdx, [rsi+18h]
0x1400012cd  movsd   qword ptr [rdx], xmm0
0x1400012d1  mov     eax, [r14+180h]
0x1400012d8  mov     [rdx+8], eax
0x1400012db  mov     qword ptr [rsi+38h], 0Ch
0x1400012e3  mov     ebx, ecx
0x1400012e5  xor     edx, edx; PriorityBoost
0x1400012e7  mov     [rsi+30h], ebx
0x1400012ea  mov     rcx, rsi; Irp
0x1400012ed  call    cs:__imp_IofCompleteRequest
0x1400012f4  nop     dword ptr [rax+rax+00h]
0x1400012f9  mov     r8d, 20h ; ' '; RemlockSize
0x1400012ff  mov     rdx, rsi; Tag
0x140001302  mov     rcx, r12; RemoveLock
0x140001305  call    cs:__imp_IoReleaseRemoveLockEx
0x14000130c  nop     dword ptr [rax+rax+00h]
0x140001311  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140001318  jz      short loc_140001347
0x14000131a  mov     rcx, cs:WPP_GLOBAL_Control
0x140001321  xor     eax, eax
0x140001323  cmp     [rcx+48h], ax
0x140001327  jz      short loc_140001347
0x140001329  mov     rcx, [rcx+40h]
0x14000132d  lea     r9d, [rax+0Fh]
0x140001331  lea     rax, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids
0x140001338  mov     r8d, r15d
0x14000133b  mov     dl, 5
0x14000133d  mov     qword ptr [rsp+88h+RemlockSize], rax
0x140001342  call    WPP_RECORDER_SF_
0x140001347  mov     eax, ebx
0x140001349  add     rsp, 48h
0x14000134d  pop     r15
0x14000134f  pop     r14
0x140001351  pop     r13
0x140001353  pop     r12
0x140001355  pop     rdi
0x140001356  pop     rsi
0x140001357  pop     rbp
0x140001358  pop     rbx
0x140001359  retn
```
