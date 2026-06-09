# RefsFsdFileSystemControl

- ea: `0x1c015be10`
- end: `0x1c015c00a`
- name: `RefsFsdFileSystemControl`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c00588cc`
- `0x1c00592b0`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c00996ec`
- `0x1c015be10`
- `0x1c015c010`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015bf1b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015bf1b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c015be8e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c015be8e`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c015beaa`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c015beaa`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0182eaf`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0182eaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015bfc1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015bfc1`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c015be7a`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c015be7a`

## pseudocode

```c
__int64 __fastcall RefsFsdFileSystemControl(__int64 a1, IRP *a2)
{
  __int64 v3; // r8
  __int64 v4; // rdx
  PIRP v5; // rcx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v7; // rbx
  UCHAR MinorFunction; // cl
  unsigned int v9; // eax
  unsigned int v10; // edi
  BOOLEAN IsOperationSynchronous; // [rsp+20h] [rbp-88h]
  struct _LIST_ENTRY *v13; // [rsp+28h] [rbp-80h] BYREF
  BOOL v14; // [rsp+30h] [rbp-78h]
  __int64 v15; // [rsp+38h] [rbp-70h] BYREF
  PIRP Irp; // [rsp+40h] [rbp-68h]
  IRP *v17; // [rsp+48h] [rbp-60h]
  IRP *v18; // [rsp+50h] [rbp-58h]
  _OWORD v19[2]; // [rsp+58h] [rbp-50h] BYREF
  __int64 v20; // [rsp+78h] [rbp-30h]
  __int128 v21; // [rsp+80h] [rbp-28h] BYREF

  v18 = a2;
  memset(v19, 0, sizeof(v19));
  v20 = 0;
  v13 = 0;
  v21 = 0;
  v15 = 0;
  if ( a2->Tail.Overlay.CurrentStackLocation->FileObject )
    IsOperationSynchronous = IoIsOperationSynchronous(a2);
  else
    IsOperationSynchronous = 1;
  KeEnterCriticalRegion();
  v14 = (int)IoPropagateActivityIdToThread(a2, &v21, &v15) >= 0;
  v17 = (IRP *)RefsInitializeTopLevelIrp(v19, 0, 0);
  Irp = v17;
  LOBYTE(v3) = 1;
  LOBYTE(v4) = IsOperationSynchronous;
  RefsInitializeIrpContext(a2, v4, v3, &v13);
  v5 = Irp;
  Flink = Irp->ThreadListEntry.Flink;
  if ( Flink )
  {
    v7 = v13;
  }
  else
  {
    *(_DWORD *)(&Irp->Size + 1) = 1397140410;
    v7 = v13;
    v5->ThreadListEntry.Flink = v13;
    LODWORD(v7->Blink) |= 0x100000u;
    IoSetTopLevelIrp(v5);
    Flink = v17->ThreadListEntry.Flink;
  }
  v7[6].Blink = Flink;
  RefsPreRequestProcessingExtend(v7);
  MinorFunction = a2->Tail.Overlay.CurrentStackLocation->MinorFunction;
  if ( MinorFunction == 1 )
  {
    v9 = RefsPostRequest(v7);
  }
  else if ( MinorFunction == 2 )
  {
    v9 = RefsVerifyVolumeRequest(v7, a2);
  }
  else
  {
    v9 = RefsCommonFileSystemControl(v7, a2);
  }
  v10 = v9;
  if ( v14 )
    IoClearActivityIdThread(v15);
  KeLeaveCriticalRegion();
  return v10;
}

```

## disassembly

```asm
0x1c015be10  mov     r11, rsp
0x1c015be13  mov     [r11+8], rbx
0x1c015be17  mov     [r11+18h], rsi
0x1c015be1b  mov     [r11+20h], rdi
0x1c015be1f  push    r14
0x1c015be21  sub     rsp, 0A0h
0x1c015be28  mov     rax, cs:__security_cookie
0x1c015be2f  xor     rax, rsp
0x1c015be32  mov     [rsp+0A8h+var_18], rax
0x1c015be3a  mov     rsi, rdx
0x1c015be3d  mov     [rsp+0A8h+var_58], rdx
0x1c015be42  xorps   xmm0, xmm0
0x1c015be45  xor     eax, eax
0x1c015be47  movups  [rsp+0A8h+var_50], xmm0
0x1c015be4c  movups  [rsp+0A8h+var_40], xmm0
0x1c015be51  mov     [r11-30h], rax
0x1c015be55  xor     ebx, ebx
0x1c015be57  mov     [r11-80h], rbx
0x1c015be5b  xor     edi, edi
0x1c015be5d  movups  xmmword ptr [r11-28h], xmm0
0x1c015be62  and     [r11-70h], rax
0x1c015be66  mov     rax, [rdx+0B8h]
0x1c015be6d  cmp     [rax+30h], rbx
0x1c015be71  jz      loc_1C015BFFA
0x1c015be77  mov     rcx, rdx; Irp
0x1c015be7a  call    cs:__imp_IoIsOperationSynchronous
0x1c015be81  nop     dword ptr [rax+rax+00h]
0x1c015be86  mov     [rsp+0A8h+var_88], al
0x1c015be8a  lea     r14d, [rbx+1]
0x1c015be8e  call    cs:__imp_KeEnterCriticalRegion
0x1c015be95  nop     dword ptr [rax+rax+00h]
0x1c015be9a  lea     r8, [rsp+0A8h+var_70]
0x1c015be9f  lea     rdx, [rsp+0A8h+var_28]
0x1c015bea7  mov     rcx, rsi
0x1c015beaa  call    cs:__imp_IoPropagateActivityIdToThread
0x1c015beb1  nop     dword ptr [rax+rax+00h]
0x1c015beb6  xor     ecx, ecx
0x1c015beb8  test    eax, eax
0x1c015beba  cmovns  ecx, r14d
0x1c015bebe  mov     [rsp+0A8h+var_78], ecx
0x1c015bec2  xor     r8d, r8d
0x1c015bec5  xor     edx, edx
0x1c015bec7  lea     rcx, [rsp+0A8h+var_50]
0x1c015becc  call    RefsInitializeTopLevelIrp
0x1c015bed1  mov     [rsp+0A8h+var_60], rax
0x1c015bed6  mov     [rsp+0A8h+Irp], rax
0x1c015bedb  test    rbx, rbx
0x1c015bede  jnz     loc_1C015BF74
0x1c015bee4  lea     r9, [rsp+0A8h+var_80]
0x1c015bee9  mov     r8b, r14b
0x1c015beec  mov     dl, [rsp+0A8h+var_88]
0x1c015bef0  mov     rcx, rsi
0x1c015bef3  call    RefsInitializeIrpContext
0x1c015bef8  mov     rcx, [rsp+0A8h+Irp]; Irp
0x1c015befd  mov     rax, [rcx+20h]
0x1c015bf01  test    rax, rax
0x1c015bf04  jnz     short loc_1C015BF6D
0x1c015bf06  mov     dword ptr [rcx+4], 5346ABBAh
0x1c015bf0d  mov     rbx, [rsp+0A8h+var_80]
0x1c015bf12  mov     [rcx+20h], rbx
0x1c015bf16  bts     dword ptr [rbx+8], 14h
0x1c015bf1b  call    cs:__imp_IoSetTopLevelIrp
0x1c015bf22  nop     dword ptr [rax+rax+00h]
0x1c015bf27  mov     rax, [rsp+0A8h+var_60]
0x1c015bf2c  mov     rax, [rax+20h]
0x1c015bf30  mov     [rbx+68h], rax
0x1c015bf34  mov     rcx, rbx
0x1c015bf37  call    RefsPreRequestProcessingExtend
0x1c015bf3c  mov     rax, [rsi+0B8h]
0x1c015bf43  mov     cl, [rax+1]
0x1c015bf46  mov     rdx, rsi
0x1c015bf49  cmp     cl, r14b
0x1c015bf4c  jz      short loc_1C015BF5D
0x1c015bf4e  cmp     cl, 2
0x1c015bf51  mov     rcx, rbx
0x1c015bf54  jz      short loc_1C015BF86
0x1c015bf56  call    RefsCommonFileSystemControl
0x1c015bf5b  jmp     short loc_1C015BF8B
0x1c015bf5d  xor     r9d, r9d
0x1c015bf60  mov     r8b, r14b
0x1c015bf63  mov     rcx, rbx
0x1c015bf66  call    RefsPostRequest
0x1c015bf6b  jmp     short loc_1C015BF8B
0x1c015bf6d  mov     rbx, [rsp+0A8h+var_80]
0x1c015bf72  jmp     short loc_1C015BF30
0x1c015bf74  cmp     edi, 0C0000188h
0x1c015bf7a  jnz     short loc_1C015BF34
0x1c015bf7c  mov     rcx, rbx
0x1c015bf7f  call    RefsCheckpointForLogFileFull
0x1c015bf84  jmp     short loc_1C015BF34
0x1c015bf86  call    RefsVerifyVolumeRequest
0x1c015bf8b  mov     edi, eax
0x1c015bf8d  mov     [rsp+0A8h+var_84], eax
0x1c015bf91  jmp     short loc_1C015BFB6
0x1c015bf93  mov     r8d, eax
0x1c015bf96  mov     rsi, [rsp+0A8h+var_58]
0x1c015bf9b  mov     rdx, rsi
0x1c015bf9e  mov     rbx, [rsp+0A8h+var_80]
0x1c015bfa3  mov     rcx, rbx
0x1c015bfa6  call    RefsProcessException
0x1c015bfab  mov     edi, eax
0x1c015bfad  mov     [rsp+0A8h+var_84], eax
0x1c015bfb1  jmp     loc_1C0182E86
0x1c015bfb6  cmp     [rsp+0A8h+var_78], 0
0x1c015bfbb  jnz     loc_1C0182EAA
0x1c015bfc1  call    cs:__imp_KeLeaveCriticalRegion
0x1c015bfc8  nop     dword ptr [rax+rax+00h]
0x1c015bfcd  mov     eax, edi
0x1c015bfcf  mov     rcx, [rsp+0A8h+var_18]
0x1c015bfd7  xor     rcx, rsp; StackCookie
0x1c015bfda  call    __security_check_cookie
0x1c015bfdf  lea     r11, [rsp+0A8h+var_8]
0x1c015bfe7  mov     rbx, [r11+10h]
0x1c015bfeb  mov     rsi, [r11+20h]
0x1c015bfef  mov     rdi, [r11+28h]
0x1c015bff3  mov     rsp, r11
0x1c015bff6  pop     r14
0x1c015bff8  retn
0x1c015bffa  mov     r14d, 1
0x1c015c000  mov     [rsp+0A8h+var_88], r14b
0x1c015c005  jmp     loc_1C015BE8E
0x1c017e903  push    rbp
0x1c017e905  sub     rsp, 20h
0x1c017e909  mov     rbp, rdx
0x1c017e90c  mov     rdx, rcx
0x1c017e90f  mov     rcx, [rbp+28h]
0x1c017e913  call    RefsExceptionFilter
0x1c017e918  nop
0x1c017e919  add     rsp, 20h
0x1c017e91d  pop     rbp
0x1c017e91e  retn
0x1c0182e86  cmp     eax, 0C00000D8h
0x1c0182e8b  jz      short loc_1C0182E9F
0x1c0182e8d  cmp     eax, 0C00001A8h
0x1c0182e92  jz      short loc_1C0182E9F
0x1c0182e94  cmp     eax, 0C0000188h
0x1c0182e99  jnz     loc_1C015BFB6
0x1c0182e9f  mov     r14d, 1
0x1c0182ea5  jmp     loc_1C015BEDB
0x1c0182eaa  mov     rcx, [rsp+0A8h+var_70]
0x1c0182eaf  call    cs:__imp_IoClearActivityIdThread
0x1c0182eb6  nop     dword ptr [rax+rax+00h]
0x1c0182ebb  nop
0x1c0182ebc  jmp     loc_1C015BFC1
```
