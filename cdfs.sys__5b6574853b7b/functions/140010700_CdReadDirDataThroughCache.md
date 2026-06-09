# CdReadDirDataThroughCache

- ea: `0x140010700`
- end: `0x140010c31`
- name: `CdReadDirDataThroughCache`
- size: `1329`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000edcc`
- `0x140010d70`

## callees

- `0x140001114`
- `0x140003000`
- `0x140010700`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140010842`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010b8e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b7f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010842`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010b8e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b7f6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010856`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010856`
- `ntoskrnl!IofCallDriver` at `0x140010abc`
- `ntoskrnl!IofCallDriver` at `0x140010abc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010ae9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010ae9`
- `ntoskrnl!IoAllocateMdl` at `0x1400109a0`
- `ntoskrnl!IoAllocateMdl` at `0x1400109a0`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400109c2`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400109c2`
- `ntoskrnl!IoFreeMdl` at `0x1400109e9`
- `ntoskrnl!IoFreeMdl` at `0x140010b24`
- `ntoskrnl!IoFreeMdl` at `0x1400109e9`
- `ntoskrnl!IoFreeMdl` at `0x140010b24`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140010776`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140010776`
- `ntoskrnl!IoReuseIrp` at `0x140010925`
- `ntoskrnl!IoReuseIrp` at `0x140010925`
- `ntoskrnl!KeClearEvent` at `0x140010940`
- `ntoskrnl!KeClearEvent` at `0x140010940`
- `ntoskrnl!MmUnlockPages` at `0x140010b11`
- `ntoskrnl!MmUnlockPages` at `0x140010b11`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140010b68`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140010b68`

## pseudocode

```c
char __fastcall CdReadDirDataThroughCache(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // r13
  __int64 v5; // r14
  unsigned int v6; // r12d
  __int64 v7; // r8
  unsigned int i; // ecx
  unsigned int v9; // eax
  int v10; // ecx
  unsigned int v11; // edi
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  int v14; // eax
  PIRP *v15; // rbx
  struct _MDL *v16; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  char v18; // bl
  int v20; // [rsp+30h] [rbp-B8h]
  ULONG v21; // [rsp+30h] [rbp-B8h]
  NTSTATUS Status; // [rsp+30h] [rbp-B8h]
  unsigned int v23; // [rsp+34h] [rbp-B4h]
  char *v24; // [rsp+40h] [rbp-A8h]
  __int64 v25; // [rsp+58h] [rbp-90h]
  __int64 v26; // [rsp+68h] [rbp-80h]
  PVOID Object; // [rsp+70h] [rbp-78h]
  __int64 v28; // [rsp+88h] [rbp-60h]
  __int128 v29; // [rsp+98h] [rbp-50h] BYREF
  int v30; // [rsp+108h] [rbp+20h]

  v3 = a1 + 16;
  v26 = a1 + 16;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = *(_QWORD *)a2 >> 11;
  v6 = *(_DWORD *)(a2 + 8) >> 11;
  v24 = *(char **)(a2 + 24);
  v29 = 0;
  ExAcquireResourceSharedLite((PERESOURCE)(v4 + 680), 1u);
  if ( !*(_QWORD *)(v4 + 568) )
    CdRaiseStatusEx(a1, 2147483670LL, 0, 655360, 2536);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v6 )
      {
        v18 = 1;
        goto LABEL_26;
      }
      v7 = 0;
      for ( i = 0; i < 4; ++i )
      {
        v9 = *(_DWORD *)(v4 + 16 * (i + 36LL));
        if ( v9 != -1 && v9 <= (unsigned int)v5 && v9 + 24 > (unsigned int)v5 )
        {
          v7 = v4 + 16 * (i + 36LL);
          break;
        }
      }
      if ( !v7 )
        break;
      v10 = v5 - *(_DWORD *)v7;
      v11 = v6;
      if ( 24 - v10 < v6 )
        v11 = 24 - v10;
      memmove(v24, (const void *)(*(_QWORD *)(v7 + 8) + (unsigned int)(v10 << 11)), v11 << 11);
      v6 -= v11;
      v24 += 2048 * v11;
      LODWORD(v5) = v11 + v5;
      v3 = v26;
    }
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)v3 + 680LL));
    ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)v3 + 680LL), 1u);
    v25 = v4 + 16 * (*(unsigned int *)(v4 + 640) + 36LL);
    v23 = v5 - ((int)v5 - 16) % 0x18u;
    v12 = *(_QWORD *)(v4 + 520);
    v13 = *(unsigned __int8 *)(v12 + 3) - (unsigned __int64)*(unsigned __int8 *)(v12 + 2);
    LOBYTE(v30) = *(_BYTE *)(v12 + 8 * v13 + 19);
    BYTE1(v30) = *(_BYTE *)(v12 + 8 * v13 + 18);
    BYTE2(v30) = *(_BYTE *)(v12 + 8 * v13 + 17);
    HIBYTE(v30) = *(_BYTE *)(v12 + 8 * v13 + 16);
    v14 = v30 - v23;
    if ( v30 - v23 > 0x18 )
      v14 = 24;
    v20 = v14;
    if ( !v14 || (unsigned int)v5 < 0x10 )
      CdRaiseStatusEx(a1, 3221225485LL, 0, 655360, 2627);
    v15 = (PIRP *)(v4 + 648);
    IoReuseIrp(*(PIRP *)(v4 + 648), 0);
    Object = (PVOID)(v4 + 656);
    KeClearEvent((PRKEVENT)(v4 + 656));
    *(_QWORD *)(*(_QWORD *)(v4 + 648) + 152LL) = KeGetCurrentThread();
    v28 = *(_QWORD *)(*(_QWORD *)(v4 + 648) + 184LL) - 72LL;
    *(_BYTE *)v28 = 3;
    v21 = v20 << 11;
    IoAllocateMdl(*(PVOID *)(v25 + 8), v21, 0, 0, *(PIRP *)(v4 + 648));
    v16 = *(struct _MDL **)(*(_QWORD *)(v4 + 648) + 8LL);
    if ( !v16 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 56LL) = 0;
      CdRaiseStatusEx(a1, 3221225626LL, 0, 655360, 2660);
    }
    MmProbeAndLockPages(v16, 0, IoWriteAccess);
    if ( !(*v15)->MdlAddress )
      CdRaiseStatusEx(a1, 3221225626LL, 0, 655360, 2683);
    *(_DWORD *)v25 = -1;
    *(_DWORD *)(v28 + 8) = v21;
    *(_QWORD *)(v28 + 24) = (unsigned __int64)v23 << 11;
    CurrentStackLocation = (*v15)->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CdSyncCompletionRoutine;
    CurrentStackLocation[-1].Context = Object;
    CurrentStackLocation[-1].Control = 0;
    CurrentStackLocation[-1].Control = 64;
    CurrentStackLocation[-1].Control = -64;
    CurrentStackLocation[-1].Control = -32;
    (*v15)->UserIosb = (PIO_STATUS_BLOCK)&v29;
    Status = IofCallDriver(*(PDEVICE_OBJECT *)(v4 + 16), *v15);
    if ( Status == 259 )
    {
      KeWaitForSingleObject(Object, Executive, 0, 0, 0);
      Status = (*v15)->IoStatus.Status;
    }
    (*v15)->UserIosb = 0;
    MmUnlockPages((*v15)->MdlAddress);
    IoFreeMdl((*v15)->MdlAddress);
    (*v15)->MdlAddress = 0;
    if ( Status < 0 )
      break;
    *(_DWORD *)v25 = v23;
    *(_DWORD *)(v4 + 640) = ((unsigned __int8)*(_DWORD *)(v4 + 640) + 1) & 3;
    ExConvertExclusiveToSharedLite((PERESOURCE)(*(_QWORD *)v3 + 680LL));
  }
  v18 = 0;
LABEL_26:
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)v3 + 680LL));
  return v18;
}

```

## disassembly

```asm
0x140010700  mov     r11, rsp
0x140010703  mov     [r11+8], rcx
0x140010707  push    rbx
0x140010708  push    rdi
0x140010709  push    r12
0x14001070b  push    r13
0x14001070d  push    r14
0x14001070f  push    r15
0x140010711  sub     rsp, 0B8h
0x140010718  mov     r15, rcx
0x14001071b  lea     rdi, [rcx+10h]
0x14001071f  mov     [rsp+0E8h+var_80], rdi
0x140010724  mov     r13, [rdi]
0x140010727  mov     [rsp+0E8h+var_70], r13
0x14001072c  mov     r14, [rdx]
0x14001072f  shr     r14, 0Bh
0x140010733  mov     [rsp+0E8h+var_B0], r14d
0x140010738  mov     r12d, [rdx+8]
0x14001073c  shr     r12d, 0Bh
0x140010740  mov     [rsp+0E8h+var_AC], r12d
0x140010745  mov     rax, [rdx+18h]
0x140010749  mov     [rsp+0E8h+var_A8], rax
0x14001074e  mov     [rsp+0E8h+var_88], rax
0x140010753  mov     dword ptr [r11+20h], 0
0x14001075b  xorps   xmm0, xmm0
0x14001075e  movups  xmmword ptr [r11-50h], xmm0
0x140010763  xor     al, al
0x140010765  mov     [r11+10h], al
0x140010769  mov     [r11+18h], al
0x14001076d  lea     rcx, [r13+2A8h]; Resource
0x140010774  mov     dl, 1; Wait
0x140010776  call    cs:__imp_ExAcquireResourceSharedLite
0x14001077d  nop     dword ptr [rax+rax+00h]
0x140010782  nop
0x140010783  cmp     qword ptr [r13+238h], 0
0x14001078b  jz      loc_140010BAF
0x140010791  test    r12d, r12d
0x140010794  jz      loc_140010B79
0x14001079a  xor     r8d, r8d
0x14001079d  xor     ecx, ecx
0x14001079f  mov     [rsp+0E8h+var_A0], ecx
0x1400107a3  cmp     ecx, 4
0x1400107a6  jnb     short loc_1400107CC
0x1400107a8  mov     edx, ecx
0x1400107aa  add     rdx, 24h ; '$'
0x1400107ae  shl     rdx, 4
0x1400107b2  add     rdx, r13
0x1400107b5  mov     eax, [rdx]
0x1400107b7  cmp     eax, 0FFFFFFFFh
0x1400107ba  jz      short loc_140010830
0x1400107bc  cmp     eax, r14d
0x1400107bf  ja      short loc_140010830
0x1400107c1  add     eax, 18h
0x1400107c4  cmp     eax, r14d
0x1400107c7  jbe     short loc_140010830
0x1400107c9  mov     r8, rdx
0x1400107cc  test    r8, r8
0x1400107cf  jz      short loc_140010837
0x1400107d1  mov     ecx, r14d
0x1400107d4  sub     ecx, [r8]
0x1400107d7  mov     eax, 18h
0x1400107dc  sub     eax, ecx
0x1400107de  mov     edi, r12d
0x1400107e1  cmp     eax, r12d
0x1400107e4  cmovb   edi, eax
0x1400107e7  mov     eax, edi
0x1400107e9  shl     eax, 0Bh
0x1400107ec  mov     ebx, eax
0x1400107ee  shl     ecx, 0Bh
0x1400107f1  mov     edx, ecx
0x1400107f3  add     rdx, [r8+8]; Src
0x1400107f7  mov     r8d, eax; Size
0x1400107fa  mov     rcx, [rsp+0E8h+var_A8]; void *
0x1400107ff  call    memmove
0x140010804  sub     r12d, edi
0x140010807  mov     [rsp+0E8h+var_AC], r12d
0x14001080c  mov     rax, [rsp+0E8h+var_A8]
0x140010811  add     rax, rbx
0x140010814  mov     [rsp+0E8h+var_A8], rax
0x140010819  mov     [rsp+0E8h+var_88], rax
0x14001081e  add     r14d, edi
0x140010821  mov     [rsp+0E8h+var_B0], r14d
0x140010826  mov     rdi, [rsp+0E8h+var_80]
0x14001082b  jmp     loc_140010791
0x140010830  inc     ecx
0x140010832  jmp     loc_14001079F
0x140010837  mov     rcx, [rdi]
0x14001083a  mov     ebx, 2A8h
0x14001083f  add     rcx, rbx; Resource
0x140010842  call    cs:__imp_ExReleaseResourceLite
0x140010849  nop     dword ptr [rax+rax+00h]
0x14001084e  mov     rcx, [rdi]
0x140010851  add     rcx, rbx; Resource
0x140010854  mov     dl, 1; Wait
0x140010856  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001085d  nop     dword ptr [rax+rax+00h]
0x140010862  lea     rax, [r13+280h]
0x140010869  mov     [rsp+0E8h+var_58], rax
0x140010871  mov     eax, [rax]
0x140010873  add     rax, 24h ; '$'
0x140010877  shl     rax, 4
0x14001087b  add     rax, r13
0x14001087e  mov     [rsp+0E8h+var_90], rax
0x140010883  lea     ecx, [r14-10h]
0x140010887  mov     eax, 0AAAAAAABh
0x14001088c  mul     ecx
0x14001088e  shr     edx, 4
0x140010891  lea     eax, [rdx+rdx*2]
0x140010894  shl     eax, 3
0x140010897  sub     ecx, eax
0x140010899  mov     r8d, r14d
0x14001089c  sub     r8d, ecx
0x14001089f  mov     [rsp+0E8h+var_B4], r8d
0x1400108a4  mov     [rsp+0E8h+var_9C], r8d
0x1400108a9  mov     rdx, [r13+208h]
0x1400108b0  movzx   ecx, byte ptr [rdx+3]
0x1400108b4  movzx   eax, byte ptr [rdx+2]
0x1400108b8  sub     rcx, rax
0x1400108bb  mov     al, [rdx+rcx*8+13h]
0x1400108bf  mov     byte ptr [rsp+0E8h+arg_18], al
0x1400108c6  mov     al, [rdx+rcx*8+12h]
0x1400108ca  mov     byte ptr [rsp+0E8h+arg_18+1], al
0x1400108d1  mov     al, [rdx+rcx*8+11h]
0x1400108d5  mov     byte ptr [rsp+0E8h+arg_18+2], al
0x1400108dc  mov     al, [rdx+rcx*8+10h]
0x1400108e0  mov     byte ptr [rsp+0E8h+arg_18+3], al
0x1400108e7  mov     eax, [rsp+0E8h+arg_18]
0x1400108ee  sub     eax, r8d
0x1400108f1  mov     ecx, 18h
0x1400108f6  cmp     eax, ecx
0x1400108f8  cmova   eax, ecx
0x1400108fb  mov     [rsp+0E8h+var_B8], eax
0x1400108ff  test    eax, eax
0x140010901  jz      loc_140010C11
0x140010907  cmp     r14d, 10h
0x14001090b  jb      loc_140010C11
0x140010911  lea     rbx, [r13+288h]
0x140010918  mov     [rsp+0E8h+var_68], rbx
0x140010920  xor     edx, edx; Iostatus
0x140010922  mov     rcx, [rbx]; Irp
0x140010925  call    cs:__imp_IoReuseIrp
0x14001092c  nop     dword ptr [rax+rax+00h]
0x140010931  lea     rax, [r13+290h]
0x140010938  mov     [rsp+0E8h+Object], rax
0x14001093d  mov     rcx, rax; Event
0x140010940  call    cs:__imp_KeClearEvent
0x140010947  nop     dword ptr [rax+rax+00h]
0x14001094c  mov     rcx, gs:188h
0x140010955  mov     rax, [rbx]
0x140010958  mov     [rax+98h], rcx
0x14001095f  mov     rax, [rbx]
0x140010962  mov     rax, [rax+0B8h]
0x140010969  add     rax, 0FFFFFFFFFFFFFFB8h
0x14001096d  mov     [rsp+0E8h+var_60], rax
0x140010975  mov     byte ptr [rax], 3
0x140010978  mov     ecx, [rsp+0E8h+var_B8]
0x14001097c  shl     ecx, 0Bh
0x14001097f  mov     [rsp+0E8h+var_B8], ecx
0x140010983  mov     [rsp+0E8h+var_98], ecx
0x140010987  mov     rax, [rbx]
0x14001098a  mov     [rsp+0E8h+Irp], rax; Irp
0x14001098f  xor     r9d, r9d; ChargeQuota
0x140010992  xor     r8d, r8d; SecondaryBuffer
0x140010995  mov     edx, ecx; Length
0x140010997  mov     rcx, [rsp+0E8h+var_90]
0x14001099c  mov     rcx, [rcx+8]; VirtualAddress
0x1400109a0  call    cs:__imp_IoAllocateMdl
0x1400109a7  nop     dword ptr [rax+rax+00h]
0x1400109ac  mov     rax, [rbx]
0x1400109af  mov     rcx, [rax+8]; MemoryDescriptorList
0x1400109b3  test    rcx, rcx
0x1400109b6  jz      loc_140010BCD
0x1400109bc  xor     edx, edx; AccessMode
0x1400109be  lea     r8d, [rdx+1]; Operation
0x1400109c2  call    cs:__imp_MmProbeAndLockPages
0x1400109c9  nop     dword ptr [rax+rax+00h]
0x1400109ce  mov     ecx, [rsp+0E8h+var_B8]
0x1400109d2  mov     r8d, [rsp+0E8h+var_B4]
0x1400109d7  jmp     short loc_140010A49
0x1400109d9  mov     r13, [rsp+0E8h+var_70]
0x1400109de  mov     rcx, [r13+288h]
0x1400109e5  mov     rcx, [rcx+8]; Mdl
0x1400109e9  call    cs:__imp_IoFreeMdl
0x1400109f0  nop     dword ptr [rax+rax+00h]
0x1400109f5  mov     rax, [r13+288h]
0x1400109fc  mov     qword ptr [rax+8], 0
0x140010a04  mov     r15, [rsp+0E8h+arg_0]
0x140010a0c  mov     r14d, [rsp+0E8h+var_B0]
0x140010a11  mov     r12d, [rsp+0E8h+var_AC]
0x140010a16  mov     rax, [rsp+0E8h+var_88]
0x140010a1b  mov     [rsp+0E8h+var_A8], rax
0x140010a20  mov     al, [rsp+0E8h+arg_10]
0x140010a27  mov     [rsp+0E8h+arg_8], al
0x140010a2e  mov     rbx, [rsp+0E8h+var_68]
0x140010a36  mov     r8d, [rsp+0E8h+var_9C]
0x140010a3b  mov     [rsp+0E8h+var_B4], r8d
0x140010a40  mov     ecx, [rsp+0E8h+var_98]
0x140010a44  mov     rdi, [rsp+0E8h+var_80]
0x140010a49  mov     rax, [rbx]
0x140010a4c  cmp     qword ptr [rax+8], 0
0x140010a51  jz      loc_140010BF3
0x140010a57  mov     rax, [rsp+0E8h+var_90]
0x140010a5c  mov     dword ptr [rax], 0FFFFFFFFh
0x140010a62  mov     rdx, [rsp+0E8h+var_60]
0x140010a6a  mov     [rdx+8], ecx
0x140010a6d  mov     eax, r8d
0x140010a70  shl     rax, 0Bh
0x140010a74  mov     [rdx+18h], rax
0x140010a78  mov     rax, [rbx]
0x140010a7b  mov     rcx, [rax+0B8h]
0x140010a82  lea     rax, CdSyncCompletionRoutine
0x140010a89  mov     [rcx-10h], rax
0x140010a8d  mov     rax, [rsp+0E8h+Object]
0x140010a92  mov     [rcx-8], rax
0x140010a96  mov     byte ptr [rcx-45h], 0
0x140010a9a  mov     byte ptr [rcx-45h], 40h ; '@'
0x140010a9e  mov     byte ptr [rcx-45h], 0C0h
0x140010aa2  mov     byte ptr [rcx-45h], 0E0h
0x140010aa6  mov     rax, [rbx]
0x140010aa9  lea     rcx, [rsp+0E8h+var_50]
0x140010ab1  mov     [rax+48h], rcx
0x140010ab5  mov     rdx, [rbx]; Irp
0x140010ab8  mov     rcx, [r13+10h]; DeviceObject
0x140010abc  call    cs:__imp_IofCallDriver
0x140010ac3  nop     dword ptr [rax+rax+00h]
0x140010ac8  mov     [rsp+0E8h+var_B8], eax
0x140010acc  cmp     eax, 103h
0x140010ad1  jnz     short loc_140010AFF
0x140010ad3  mov     [rsp+0E8h+Irp], 0; Timeout
0x140010adc  xor     r9d, r9d; Alertable
0x140010adf  xor     r8d, r8d; WaitMode
0x140010ae2  xor     edx, edx; WaitReason
0x140010ae4  mov     rcx, [rsp+0E8h+Object]; Object
0x140010ae9  call    cs:__imp_KeWaitForSingleObject
0x140010af0  nop     dword ptr [rax+rax+00h]
0x140010af5  mov     rax, [rbx]
0x140010af8  mov     eax, [rax+30h]
0x140010afb  mov     [rsp+0E8h+var_B8], eax
0x140010aff  mov     rax, [rbx]
0x140010b02  mov     qword ptr [rax+48h], 0
0x140010b0a  mov     rcx, [rbx]
0x140010b0d  mov     rcx, [rcx+8]; MemoryDescriptorList
0x140010b11  call    cs:__imp_MmUnlockPages
0x140010b18  nop     dword ptr [rax+rax+00h]
0x140010b1d  mov     rcx, [rbx]
0x140010b20  mov     rcx, [rcx+8]; Mdl
0x140010b24  call    cs:__imp_IoFreeMdl
0x140010b2b  nop     dword ptr [rax+rax+00h]
0x140010b30  mov     rax, [rbx]
0x140010b33  mov     qword ptr [rax+8], 0
0x140010b3b  cmp     [rsp+0E8h+var_B8], 0
0x140010b40  jl      short loc_140010B7D
0x140010b42  mov     rax, [rsp+0E8h+var_90]
0x140010b47  mov     ecx, [rsp+0E8h+var_B4]
0x140010b4b  mov     [rax], ecx
0x140010b4d  mov     rcx, [rsp+0E8h+var_58]
0x140010b55  mov     eax, [rcx]
0x140010b57  inc     eax
0x140010b59  and     eax, 3
0x140010b5c  mov     [rcx], eax
0x140010b5e  mov     rcx, [rdi]
0x140010b61  add     rcx, 2A8h; Resource
0x140010b68  call    cs:__imp_ExConvertExclusiveToSharedLite
0x140010b6f  nop     dword ptr [rax+rax+00h]
0x140010b74  jmp     loc_140010791
0x140010b79  mov     bl, 1
0x140010b7b  jmp     short loc_140010B84
0x140010b7d  mov     bl, [rsp+0E8h+arg_8]
0x140010b84  mov     rcx, [rdi]
0x140010b87  add     rcx, 2A8h; Resource
0x140010b8e  call    cs:__imp_ExReleaseResourceLite
0x140010b95  nop     dword ptr [rax+rax+00h]
0x140010b9a  mov     al, bl
0x140010b9c  add     rsp, 0B8h
0x140010ba3  pop     r15
0x140010ba5  pop     r14
0x140010ba7  pop     r13
0x140010ba9  pop     r12
0x140010bab  pop     rdi
0x140010bac  pop     rbx
0x140010bad  retn
0x140010baf  mov     dword ptr [rsp+0E8h+Irp], 9E8h
0x140010bb7  mov     r9d, 0A0000h
0x140010bbd  xor     r8d, r8d
0x140010bc0  mov     edx, 80000016h
0x140010bc5  mov     rcx, r15
0x140010bc8  call    CdRaiseStatusEx
0x140010bcd  mov     rax, [r15+8]
0x140010bd1  mov     [rax+38h], rcx
0x140010bd5  mov     dword ptr [rsp+0E8h+Irp], 0A64h
0x140010bdd  mov     r9d, 0A0000h
0x140010be3  xor     r8d, r8d
0x140010be6  mov     edx, 0C000009Ah
0x140010beb  mov     rcx, r15
0x140010bee  call    CdRaiseStatusEx
0x140010bf3  mov     dword ptr [rsp+0E8h+Irp], 0A7Bh
0x140010bfb  mov     r9d, 0A0000h
0x140010c01  xor     r8d, r8d
0x140010c04  mov     edx, 0C000009Ah
0x140010c09  mov     rcx, r15
  ... truncated ...
```
