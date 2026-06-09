# HsmiRecallWriteFileNoLock

- ea: `0x14006fcf4`
- end: `0x1400702f7`
- name: `HsmiRecallWriteFileNoLock`
- size: `1539`
- prototype: `__int64(__int64, __int64, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x14005fde4`

## callees

- `0x140003c50`
- `0x140017ac4`
- `0x140017b58`
- `0x14001e300`
- `0x140058ddc`
- `0x1400698e0`
- `0x14006fcf4`
- `0x1400704ac`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14006ff11`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14006ff11`
- `ntoskrnl!IoFreeMdl` at `0x1400702bb`
- `ntoskrnl!IoFreeMdl` at `0x1400702bb`
- `ntoskrnl!IoAllocateMdl` at `0x14006fef6`
- `ntoskrnl!IoAllocateMdl` at `0x14006fef6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007005f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007005f`
- `ntoskrnl!KeInitializeEvent` at `0x140070036`
- `ntoskrnl!KeInitializeEvent` at `0x140070036`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400702d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400702d4`
- `ntoskrnl!ExAllocatePool2` at `0x14006fec6`
- `ntoskrnl!ExAllocatePool2` at `0x14006fec6`
- `FLTMGR!FltWriteFileEx` at `0x14006fffb`
- `FLTMGR!FltWriteFileEx` at `0x14006fffb`
- `FLTMGR!FltReadFileEx` at `0x14006ff59`
- `FLTMGR!FltReadFileEx` at `0x14006ff59`

## pseudocode

```c
__int64 HsmiRecallWriteFileNoLock(__int64 a1, __int64 a2, __int64 a3, __int64 a4, ...)
{
  __int64 v4; // rax
  NTSTATUS Range; // ebx
  void *Pool2; // r13
  struct _MDL *v7; // r15
  __int64 v9; // r12
  __int64 v10; // rax
  __int64 v11; // r9
  __int64 Bitmap; // rax
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // rax
  __int64 v17; // r10
  unsigned int v18; // r14d
  unsigned int v19; // esi
  struct _MDL *Mdl; // rax
  __int64 v21; // rax
  struct _MDL *v22; // rcx
  __int64 StreamSize; // rax
  __int64 v24; // r10
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // r10
  __int64 v29; // r10
  unsigned int v31; // [rsp+68h] [rbp-41h] BYREF
  __int64 v32; // [rsp+70h] [rbp-39h] BYREF
  __int64 v33; // [rsp+78h] [rbp-31h] BYREF
  __int64 i; // [rsp+80h] [rbp-29h] BYREF
  __int64 v35; // [rsp+88h] [rbp-21h] BYREF
  __int64 v36; // [rsp+90h] [rbp-19h]
  struct _KEVENT Event; // [rsp+98h] [rbp-11h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+108h] [rbp+5Fh] BYREF
  __int64 v39; // [rsp+110h] [rbp+67h]
  __int64 v40; // [rsp+118h] [rbp+6Fh]
  __int64 v41; // [rsp+120h] [rbp+77h]
  __int64 v42; // [rsp+128h] [rbp+7Fh] BYREF
  va_list va; // [rsp+128h] [rbp+7Fh]
  va_list va1; // [rsp+130h] [rbp+87h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v42 = va_arg(va1, _QWORD);
  v41 = a4;
  v40 = a3;
  v39 = a2;
  v4 = *(_QWORD *)(a1 + 16);
  Range = 0;
  Pool2 = 0;
  v33 = 0;
  v7 = 0;
  v9 = *(_QWORD *)(v4 + 32);
  v36 = *(_QWORD *)(*(_QWORD *)(v4 + 16) + 32LL);
  v10 = a4;
  v11 = a4 + (unsigned int)v42;
  for ( i = v11; ; v11 = i )
  {
    v32 = v10;
    if ( v10 >= v11 )
      break;
    Range = 0;
    LOBYTE(v42) = 0;
    v31 = 0;
    v35 = 0;
    LOBYTE(Timeout.LowPart) = 0;
    Bitmap = HsmiGetBitmap(a1, 16973, &Timeout);
    if ( Bitmap )
    {
      Range = HsmpBitmapQueryRange(Bitmap, (unsigned int)&v32, (unsigned int)&i, (unsigned int)va, (__int64)&v33);
      HsmDbgBreakOnStatus(Range);
    }
    else
    {
      LOBYTE(v42) = Timeout.LowPart;
      v33 = v13;
    }
    HsmDbgBreakOnStatus(Range);
    if ( Range < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        StreamSize = HsmpGetStreamSize(a1);
        v25 = 10;
LABEL_61:
        WPP_SF_iqLiiid(*(_QWORD *)(v24 + 24), v25, v32, v9, a1, *(_DWORD *)(a1 + 28), StreamSize, v32, i, Range);
      }
      break;
    }
    if ( !(_BYTE)v42 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v16 = HsmpGetStreamSize(a1);
        WPP_SF_iqLiii(*(_QWORD *)(v17 + 24), 12, v16, v9, a1, *(_DWORD *)(a1 + 28), v16, v32, v33);
      }
      while ( 1 )
      {
        v18 = v33 - v32;
        v35 = v32;
        v19 = (v33 - v32) & 0xFFFFF000;
        if ( v19 )
        {
          v18 = (v33 - v32) & 0xFFFFF000;
          v21 = v40 + (unsigned int)(v32 - v41);
          v22 = 0;
        }
        else
        {
          if ( !Pool2 )
          {
            Pool2 = (void *)ExAllocatePool2(v19 + 64, 4096, 2001892168);
            if ( !Pool2 )
            {
              Range = -1073741670;
              HsmDbgBreakOnStatus(-1073741670);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v26 = HsmpGetStreamSize(a1);
                WPP_SF_iqLiiid(*(_QWORD *)(v29 + 24), 13, v32, v9, a1, *(_DWORD *)(a1 + 28), v26, v32, i, -1073741670);
              }
              goto LABEL_62;
            }
          }
          if ( !v7 )
          {
            Mdl = IoAllocateMdl(Pool2, 0x1000u, 0, 0, 0);
            v7 = Mdl;
            if ( !Mdl )
            {
              Range = -1073741670;
              HsmDbgBreakOnStatus(-1073741670);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v27 = HsmpGetStreamSize(a1);
                WPP_SF_iqLiiid(*(_QWORD *)(v28 + 24), 14, v32, v9, a1, *(_DWORD *)(a1 + 28), v27, v32, i, -1073741670);
              }
              goto LABEL_64;
            }
            MmBuildMdlForNonPagedPool(Mdl);
          }
          Range = FltReadFileEx(v36, v39, &v35, 4096, 0, 10, &v31, 0, 0, 0, v7);
          HsmDbgBreakOnStatus(Range);
          if ( Range == -1073741807 )
          {
            Range = 0;
            goto LABEL_62;
          }
          if ( Range < 0 )
            goto LABEL_47;
          if ( v31 < v18 )
          {
            Range = -1073741595;
            HsmDbgBreakOnStatus(-1073741595);
LABEL_47:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              StreamSize = HsmpGetStreamSize(a1);
              v25 = 15;
              goto LABEL_61;
            }
            goto LABEL_62;
          }
          v19 = 4096;
          memmove(Pool2, (const void *)(v40 + (unsigned int)(v32 - v41)), (unsigned int)(v33 - v32));
          v21 = 0;
          v22 = v7;
        }
        Range = FltWriteFileEx(v36, v39, &v35, v19, v21, 10, &v31, 0, 0, 0, v22);
        HsmDbgBreakOnStatus(Range);
        if ( Range != -1073741740 )
          break;
        Timeout.QuadPart = 0;
        memset(&Event, 0, sizeof(Event));
        KeInitializeEvent(&Event, NotificationEvent, 0);
        Timeout.QuadPart = -10000;
        Range = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
        HsmDbgBreakOnStatus(Range);
        if ( Range != 258 && Range )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            StreamSize = HsmpGetStreamSize(a1);
            v25 = 16;
            goto LABEL_61;
          }
          goto LABEL_62;
        }
      }
      if ( Range >= 0 )
      {
        if ( v31 >= v18 )
        {
          v33 = v32 + v19;
          goto LABEL_37;
        }
        Range = -1073741595;
        HsmDbgBreakOnStatus(-1073741595);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        StreamSize = HsmpGetStreamSize(a1);
        v25 = 17;
        goto LABEL_61;
      }
      break;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v14 = HsmpGetStreamSize(a1);
      WPP_SF_iqLiii(*(_QWORD *)(v15 + 24), 11, v14, v9, a1, *(_DWORD *)(a1 + 28), v14, v32, v33);
    }
LABEL_37:
    v10 = v33;
  }
LABEL_62:
  if ( v7 )
    IoFreeMdl(v7);
LABEL_64:
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x77527348u);
  return (unsigned int)Range;
}

```

## disassembly

```asm
0x14006fcf4  mov     rax, rsp
0x14006fcf7  mov     [rax+20h], r9
0x14006fcfb  mov     [rax+18h], r8
0x14006fcff  mov     [rax+10h], rdx
0x14006fd03  push    rbp
0x14006fd04  push    rbx
0x14006fd05  push    rsi
0x14006fd06  push    rdi
0x14006fd07  push    r12
0x14006fd09  push    r13
0x14006fd0b  push    r14
0x14006fd0d  push    r15
0x14006fd0f  lea     rbp, [rax-57h]
0x14006fd13  sub     rsp, 0B8h
0x14006fd1a  mov     rax, [rcx+10h]
0x14006fd1e  lea     rsi, WPP_GLOBAL_Control
0x14006fd25  mov     r10, r9
0x14006fd28  xor     ebx, ebx
0x14006fd2a  xor     r13d, r13d
0x14006fd2d  mov     [rbp+4Fh+var_80], rbx
0x14006fd31  xor     r15d, r15d
0x14006fd34  mov     rdi, rcx
0x14006fd37  mov     r12, [rax+20h]
0x14006fd3b  mov     rax, [rax+10h]
0x14006fd3f  mov     rax, [rax+20h]
0x14006fd43  mov     [rbp+4Fh+var_68], rax
0x14006fd47  mov     rax, r9
0x14006fd4a  mov     r9d, dword ptr [rbp+4Fh+arg_20]
0x14006fd4e  add     r9, rax
0x14006fd51  mov     [rbp+4Fh+var_78], r9
0x14006fd55  mov     [rbp+4Fh+var_88], rax
0x14006fd59  cmp     rax, r9
0x14006fd5c  jge     loc_1400702B3
0x14006fd62  xor     ebx, ebx
0x14006fd64  lea     r8, [rbp+4Fh+Timeout]
0x14006fd68  mov     edx, 424Dh
0x14006fd6d  mov     byte ptr [rbp+4Fh+arg_20], bl
0x14006fd70  mov     rcx, rdi
0x14006fd73  mov     [rbp+4Fh+var_90], ebx
0x14006fd76  mov     [rbp+4Fh+var_70], rbx
0x14006fd7a  mov     byte ptr [rbp+4Fh+Timeout], bl
0x14006fd7d  call    HsmiGetBitmap
0x14006fd82  test    rax, rax
0x14006fd85  jz      short loc_14006FDAF
0x14006fd87  lea     rcx, [rbp+4Fh+var_80]
0x14006fd8b  mov     [rsp+0F0h+Irp], rcx
0x14006fd90  lea     r9, [rbp+4Fh+arg_20]
0x14006fd94  mov     rcx, rax
0x14006fd97  lea     r8, [rbp+4Fh+var_78]
0x14006fd9b  lea     rdx, [rbp+4Fh+var_88]
0x14006fd9f  call    HsmpBitmapQueryRange
0x14006fda4  mov     ecx, eax
0x14006fda6  mov     ebx, eax
0x14006fda8  call    HsmDbgBreakOnStatus
0x14006fdad  jmp     short loc_14006FDB9
0x14006fdaf  mov     al, byte ptr [rbp+4Fh+Timeout]
0x14006fdb2  mov     byte ptr [rbp+4Fh+arg_20], al
0x14006fdb5  mov     [rbp+4Fh+var_80], r9
0x14006fdb9  mov     ecx, ebx
0x14006fdbb  call    HsmDbgBreakOnStatus
0x14006fdc0  test    ebx, ebx
0x14006fdc2  js      loc_140070258
0x14006fdc8  cmp     byte ptr [rbp+4Fh+arg_20], 0
0x14006fdcc  jz      short loc_14006FE39
0x14006fdce  mov     r10, cs:WPP_GLOBAL_Control
0x14006fdd5  cmp     r10, rsi
0x14006fdd8  jz      loc_1400700EB
0x14006fdde  mov     eax, [r10+2Ch]
0x14006fde2  test    al, 1
0x14006fde4  jz      loc_1400700EB
0x14006fdea  cmp     byte ptr [r10+29h], 4
0x14006fdef  jb      loc_1400700EB
0x14006fdf5  mov     rcx, rdi
0x14006fdf8  call    HsmpGetStreamSize
0x14006fdfd  mov     rcx, [r10+18h]
0x14006fe01  mov     r8, rax
0x14006fe04  mov     rax, [rbp+4Fh+var_80]
0x14006fe08  mov     edx, 0Bh
0x14006fe0d  mov     [rsp+0F0h+var_B0], rax
0x14006fe12  mov     r9, r12
0x14006fe15  mov     rax, [rbp+4Fh+var_88]
0x14006fe19  mov     [rsp+0F0h+var_B8], rax
0x14006fe1e  mov     eax, [rdi+1Ch]
0x14006fe21  mov     [rsp+0F0h+var_C0], r8
0x14006fe26  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14006fe2a  mov     [rsp+0F0h+Irp], rdi
0x14006fe2f  call    WPP_SF_iqLiii
0x14006fe34  jmp     loc_1400700EB
0x14006fe39  mov     r10, cs:WPP_GLOBAL_Control
0x14006fe40  cmp     r10, rsi
0x14006fe43  jz      short loc_14006FE93
0x14006fe45  mov     eax, [r10+2Ch]
0x14006fe49  test    al, 1
0x14006fe4b  jz      short loc_14006FE93
0x14006fe4d  cmp     byte ptr [r10+29h], 4
0x14006fe52  jb      short loc_14006FE93
0x14006fe54  mov     rcx, rdi
0x14006fe57  call    HsmpGetStreamSize
0x14006fe5c  mov     rcx, [r10+18h]
0x14006fe60  mov     r8, rax
0x14006fe63  mov     rax, [rbp+4Fh+var_80]
0x14006fe67  mov     edx, 0Ch
0x14006fe6c  mov     [rsp+0F0h+var_B0], rax
0x14006fe71  mov     r9, r12
0x14006fe74  mov     rax, [rbp+4Fh+var_88]
0x14006fe78  mov     [rsp+0F0h+var_B8], rax
0x14006fe7d  mov     eax, [rdi+1Ch]
0x14006fe80  mov     [rsp+0F0h+var_C0], r8
0x14006fe85  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14006fe89  mov     [rsp+0F0h+Irp], rdi
0x14006fe8e  call    WPP_SF_iqLiii
0x14006fe93  mov     rax, [rbp+4Fh+var_88]
0x14006fe97  mov     r14d, dword ptr [rbp+4Fh+var_80]
0x14006fe9b  sub     r14d, eax
0x14006fe9e  mov     [rbp+4Fh+var_70], rax
0x14006fea2  mov     esi, r14d
0x14006fea5  and     esi, 0FFFFF000h
0x14006feab  jnz     loc_14006FFB4
0x14006feb1  xor     ebx, ebx
0x14006feb3  test    r13, r13
0x14006feb6  jnz     short loc_14006FEDE
0x14006feb8  mov     edx, 1000h
0x14006febd  lea     ecx, [rsi+40h]
0x14006fec0  mov     r8d, 77527348h
0x14006fec6  call    cs:__imp_ExAllocatePool2
0x14006fecd  nop     dword ptr [rax+rax+00h]
0x14006fed2  mov     r13, rax
0x14006fed5  test    rax, rax
0x14006fed8  jz      loc_1400700F8
0x14006fede  test    r15, r15
0x14006fee1  jnz     short loc_14006FF1D
0x14006fee3  xor     r9d, r9d; ChargeQuota
0x14006fee6  mov     [rsp+0F0h+Irp], rbx; Irp
0x14006feeb  xor     r8d, r8d; SecondaryBuffer
0x14006feee  mov     edx, 1000h; Length
0x14006fef3  mov     rcx, r13; VirtualAddress
0x14006fef6  call    cs:__imp_IoAllocateMdl
0x14006fefd  nop     dword ptr [rax+rax+00h]
0x14006ff02  mov     r15, rax
0x14006ff05  test    rax, rax
0x14006ff08  jz      loc_14007014A
0x14006ff0e  mov     rcx, rax; MemoryDescriptorList
0x14006ff11  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14006ff18  nop     dword ptr [rax+rax+00h]
0x14006ff1d  mov     rdx, [rbp+4Fh+arg_8]
0x14006ff21  lea     rax, [rbp+4Fh+var_90]
0x14006ff25  mov     rcx, [rbp+4Fh+var_68]
0x14006ff29  lea     r8, [rbp+4Fh+var_70]
0x14006ff2d  mov     [rsp+50h], r15
0x14006ff32  mov     r9d, 1000h
0x14006ff38  mov     [rsp+0F0h+var_A8], rbx
0x14006ff3d  mov     [rsp+0F0h+var_B0], rbx
0x14006ff42  mov     [rsp+0F0h+var_B8], rbx
0x14006ff47  mov     [rsp+0F0h+var_C0], rax
0x14006ff4c  mov     dword ptr [rsp+0F0h+var_C8], 0Ah
0x14006ff54  mov     [rsp+0F0h+Irp], rbx
0x14006ff59  call    cs:__imp_FltReadFileEx
0x14006ff60  nop     dword ptr [rax+rax+00h]
0x14006ff65  mov     ecx, eax
0x14006ff67  mov     ebx, eax
0x14006ff69  call    HsmDbgBreakOnStatus
0x14006ff6e  cmp     ebx, 0C0000011h
0x14006ff74  jz      loc_140070214
0x14006ff7a  test    ebx, ebx
0x14006ff7c  js      loc_1400701D7
0x14006ff82  cmp     [rbp+4Fh+var_90], r14d
0x14006ff86  jb      loc_1400701CB
0x14006ff8c  mov     rcx, [rbp+4Fh+var_88]
0x14006ff90  mov     esi, 1000h
0x14006ff95  mov     r8d, dword ptr [rbp+4Fh+var_80]
0x14006ff99  sub     r8d, ecx; Size
0x14006ff9c  sub     ecx, dword ptr [rbp+4Fh+arg_18]
0x14006ff9f  mov     edx, ecx
0x14006ffa1  mov     rcx, r13; void *
0x14006ffa4  add     rdx, [rbp+4Fh+arg_10]; Src
0x14006ffa8  call    memmove
0x14006ffad  xor     eax, eax
0x14006ffaf  mov     rcx, r15
0x14006ffb2  jmp     short loc_14006FFC0
0x14006ffb4  sub     eax, dword ptr [rbp+4Fh+arg_18]
0x14006ffb7  mov     r14d, esi
0x14006ffba  add     rax, [rbp+4Fh+arg_10]
0x14006ffbe  xor     ecx, ecx
0x14006ffc0  mov     rdx, [rbp+4Fh+arg_8]
0x14006ffc4  lea     r8, [rbp+4Fh+var_70]
0x14006ffc8  mov     [rsp+50h], rcx
0x14006ffcd  mov     r9d, esi
0x14006ffd0  xor     ecx, ecx
0x14006ffd2  mov     [rsp+0F0h+var_A8], rcx
0x14006ffd7  mov     [rsp+0F0h+var_B0], rcx
0x14006ffdc  mov     [rsp+0F0h+var_B8], rcx
0x14006ffe1  lea     rcx, [rbp+4Fh+var_90]
0x14006ffe5  mov     [rsp+0F0h+var_C0], rcx
0x14006ffea  mov     rcx, [rbp+4Fh+var_68]
0x14006ffee  mov     dword ptr [rsp+0F0h+var_C8], 0Ah
0x14006fff6  mov     [rsp+0F0h+Irp], rax
0x14006fffb  call    cs:__imp_FltWriteFileEx
0x140070002  nop     dword ptr [rax+rax+00h]
0x140070007  mov     ecx, eax
0x140070009  mov     ebx, eax
0x14007000b  call    HsmDbgBreakOnStatus
0x140070010  cmp     ebx, 0C0000054h
0x140070016  jnz     loc_1400700C8
0x14007001c  xor     eax, eax
0x14007001e  lea     rcx, [rbp+4Fh+Event]; Event
0x140070022  xorps   xmm0, xmm0
0x140070025  mov     [rbp+4Fh+Event.Header.WaitListHead.Blink], rax
0x140070029  xor     r8d, r8d; State
0x14007002c  mov     qword ptr [rbp+4Fh+Timeout], rax
0x140070030  xor     edx, edx; Type
0x140070032  movups  xmmword ptr [rbp+4Fh+Event.Header], xmm0
0x140070036  call    cs:__imp_KeInitializeEvent
0x14007003d  nop     dword ptr [rax+rax+00h]
0x140070042  lea     rax, [rbp+4Fh+Timeout]
0x140070046  mov     qword ptr [rbp+4Fh+Timeout], 0FFFFFFFFFFFFD8F0h
0x14007004e  xor     r9d, r9d; Alertable
0x140070051  mov     [rsp+0F0h+Irp], rax; Timeout
0x140070056  xor     r8d, r8d; WaitMode
0x140070059  lea     rcx, [rbp+4Fh+Event]; Object
0x14007005d  xor     edx, edx; WaitReason
0x14007005f  call    cs:__imp_KeWaitForSingleObject
0x140070066  nop     dword ptr [rax+rax+00h]
0x14007006b  mov     ecx, eax
0x14007006d  mov     ebx, eax
0x14007006f  call    HsmDbgBreakOnStatus
0x140070074  cmp     ebx, 102h
0x14007007a  jz      loc_14006FE93
0x140070080  test    ebx, ebx
0x140070082  jz      loc_14006FE93
0x140070088  mov     r10, cs:WPP_GLOBAL_Control
0x14007008f  lea     rax, WPP_GLOBAL_Control
0x140070096  cmp     r10, rax
0x140070099  jz      loc_1400702B3
0x14007009f  mov     eax, [r10+2Ch]
0x1400700a3  test    al, 1
0x1400700a5  jz      loc_1400702B3
0x1400700ab  cmp     byte ptr [r10+29h], 2
0x1400700b0  jb      loc_1400702B3
0x1400700b6  mov     rcx, rdi
0x1400700b9  call    HsmpGetStreamSize
0x1400700be  mov     edx, 10h
0x1400700c3  jmp     loc_140070280
0x1400700c8  test    ebx, ebx
0x1400700ca  js      loc_140070227
0x1400700d0  cmp     [rbp+4Fh+var_90], r14d
0x1400700d4  jb      loc_14007021B
0x1400700da  mov     eax, esi
0x1400700dc  lea     rsi, WPP_GLOBAL_Control
0x1400700e3  add     rax, [rbp+4Fh+var_88]
0x1400700e7  mov     [rbp+4Fh+var_80], rax
0x1400700eb  mov     rax, [rbp+4Fh+var_80]
0x1400700ef  mov     r9, [rbp+4Fh+var_78]
0x1400700f3  jmp     loc_14006FD55
0x1400700f8  mov     esi, 0C000009Ah
0x1400700fd  mov     ecx, esi
0x1400700ff  mov     ebx, esi
0x140070101  call    HsmDbgBreakOnStatus
0x140070106  mov     r10, cs:WPP_GLOBAL_Control
0x14007010d  lea     rax, WPP_GLOBAL_Control
0x140070114  cmp     r10, rax
0x140070117  jz      loc_1400702B3
0x14007011d  mov     eax, [r10+2Ch]
0x140070121  test    al, 1
0x140070123  jz      loc_1400702B3
0x140070129  cmp     byte ptr [r10+29h], 2
0x14007012e  jb      loc_1400702B3
0x140070134  mov     rcx, rdi
0x140070137  call    HsmpGetStreamSize
0x14007013c  mov     edx, 0Dh
0x140070141  mov     dword ptr [rsp+0F0h+var_A8], esi
0x140070145  jmp     loc_140070284
0x14007014a  mov     esi, 0C000009Ah
0x14007014f  mov     ecx, esi
0x140070151  mov     ebx, esi
0x140070153  call    HsmDbgBreakOnStatus
0x140070158  mov     r10, cs:WPP_GLOBAL_Control
0x14007015f  lea     rax, WPP_GLOBAL_Control
0x140070166  cmp     r10, rax
0x140070169  jz      loc_1400702C7
0x14007016f  mov     eax, [r10+2Ch]
0x140070173  test    al, 1
0x140070175  jz      loc_1400702C7
0x14007017b  cmp     byte ptr [r10+29h], 2
0x140070180  jb      loc_1400702C7
0x140070186  mov     rcx, rdi
0x140070189  call    HsmpGetStreamSize
0x14007018e  mov     r8, [rbp+4Fh+var_78]
0x140070192  mov     edx, 0Eh
0x140070197  mov     rcx, [r10+18h]
0x14007019b  mov     r9, r12
0x14007019e  mov     dword ptr [rsp+0F0h+var_A8], esi
0x1400701a2  mov     [rsp+0F0h+var_B0], r8
0x1400701a7  mov     r8, [rbp+4Fh+var_88]
0x1400701ab  mov     [rsp+0F0h+var_B8], r8
0x1400701b0  mov     [rsp+0F0h+var_C0], rax
0x1400701b5  mov     eax, [rdi+1Ch]
0x1400701b8  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1400701bc  mov     [rsp+0F0h+Irp], rdi
0x1400701c1  call    WPP_SF_iqLiiid
0x1400701c6  jmp     loc_1400702C7
  ... truncated ...
```
