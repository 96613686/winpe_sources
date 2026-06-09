# HsmiRecallWriteFileNoLock

- ea: `0x14006fbd4`
- end: `0x1400701d7`
- name: `HsmiRecallWriteFileNoLock`
- size: `1539`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x14005fcc4`

## callees

- `0x140003c50`
- `0x140017a44`
- `0x140017ad8`
- `0x14001e280`
- `0x140058cbc`
- `0x1400697c0`
- `0x14006fbd4`
- `0x14007038c`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14006fdf1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14006fdf1`
- `ntoskrnl!IoFreeMdl` at `0x14007019b`
- `ntoskrnl!IoFreeMdl` at `0x14007019b`
- `ntoskrnl!IoAllocateMdl` at `0x14006fdd6`
- `ntoskrnl!IoAllocateMdl` at `0x14006fdd6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006ff3f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006ff3f`
- `ntoskrnl!KeInitializeEvent` at `0x14006ff16`
- `ntoskrnl!KeInitializeEvent` at `0x14006ff16`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400701b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400701b4`
- `ntoskrnl!ExAllocatePool2` at `0x14006fda6`
- `ntoskrnl!ExAllocatePool2` at `0x14006fda6`
- `FLTMGR!FltWriteFileEx` at `0x14006fedb`
- `FLTMGR!FltWriteFileEx` at `0x14006fedb`
- `FLTMGR!FltReadFileEx` at `0x14006fe39`
- `FLTMGR!FltReadFileEx` at `0x14006fe39`

## pseudocode

```c
__int64 HsmiRecallWriteFileNoLock(__int64 a1, __int64 a2, __int64 a3, __int64 a4, ...)
{
  __int64 v4; // rax
  __int64 Range; // rbx
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
  LODWORD(Range) = 0;
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
    LODWORD(Range) = 0;
    LOBYTE(v42) = 0;
    v31 = 0;
    v35 = 0;
    LOBYTE(Timeout.LowPart) = 0;
    Bitmap = HsmiGetBitmap(a1, 16973, &Timeout);
    if ( Bitmap )
    {
      Range = (unsigned int)HsmpBitmapQueryRange(
                              Bitmap,
                              (unsigned int)&v32,
                              (unsigned int)&i,
                              (unsigned int)va,
                              (__int64)&v33);
      HsmDbgBreakOnStatus(Range);
    }
    else
    {
      LOBYTE(v42) = Timeout.LowPart;
      v33 = v13;
    }
    HsmDbgBreakOnStatus((unsigned int)Range);
    if ( (int)Range < 0 )
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
              LODWORD(Range) = -1073741670;
              HsmDbgBreakOnStatus(3221225626LL);
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
              LODWORD(Range) = -1073741670;
              HsmDbgBreakOnStatus(3221225626LL);
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
          Range = (unsigned int)FltReadFileEx(v36, v39, &v35, 4096, 0, 10, &v31, 0, 0, 0, v7);
          HsmDbgBreakOnStatus(Range);
          if ( (_DWORD)Range == -1073741807 )
          {
            LODWORD(Range) = 0;
            goto LABEL_62;
          }
          if ( (int)Range < 0 )
            goto LABEL_47;
          if ( v31 < v18 )
          {
            LODWORD(Range) = -1073741595;
            HsmDbgBreakOnStatus(3221225701LL);
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
        Range = (unsigned int)FltWriteFileEx(v36, v39, &v35, v19, v21, 10, &v31, 0, 0, 0, v22);
        HsmDbgBreakOnStatus(Range);
        if ( (_DWORD)Range != -1073741740 )
          break;
        Timeout.QuadPart = 0;
        memset(&Event, 0, sizeof(Event));
        KeInitializeEvent(&Event, NotificationEvent, 0);
        Timeout.QuadPart = -10000;
        Range = (unsigned int)KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
        HsmDbgBreakOnStatus(Range);
        if ( (_DWORD)Range != 258 && (_DWORD)Range )
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
      if ( (int)Range >= 0 )
      {
        if ( v31 >= v18 )
        {
          v33 = v32 + v19;
          goto LABEL_37;
        }
        LODWORD(Range) = -1073741595;
        HsmDbgBreakOnStatus(3221225701LL);
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
0x14006fbd4  mov     rax, rsp
0x14006fbd7  mov     [rax+20h], r9
0x14006fbdb  mov     [rax+18h], r8
0x14006fbdf  mov     [rax+10h], rdx
0x14006fbe3  push    rbp
0x14006fbe4  push    rbx
0x14006fbe5  push    rsi
0x14006fbe6  push    rdi
0x14006fbe7  push    r12
0x14006fbe9  push    r13
0x14006fbeb  push    r14
0x14006fbed  push    r15
0x14006fbef  lea     rbp, [rax-57h]
0x14006fbf3  sub     rsp, 0B8h
0x14006fbfa  mov     rax, [rcx+10h]
0x14006fbfe  lea     rsi, WPP_GLOBAL_Control
0x14006fc05  mov     r10, r9
0x14006fc08  xor     ebx, ebx
0x14006fc0a  xor     r13d, r13d
0x14006fc0d  mov     [rbp+4Fh+var_80], rbx
0x14006fc11  xor     r15d, r15d
0x14006fc14  mov     rdi, rcx
0x14006fc17  mov     r12, [rax+20h]
0x14006fc1b  mov     rax, [rax+10h]
0x14006fc1f  mov     rax, [rax+20h]
0x14006fc23  mov     [rbp+4Fh+var_68], rax
0x14006fc27  mov     rax, r9
0x14006fc2a  mov     r9d, dword ptr [rbp+4Fh+arg_20]
0x14006fc2e  add     r9, rax
0x14006fc31  mov     [rbp+4Fh+var_78], r9
0x14006fc35  mov     [rbp+4Fh+var_88], rax
0x14006fc39  cmp     rax, r9
0x14006fc3c  jge     loc_140070193
0x14006fc42  xor     ebx, ebx
0x14006fc44  lea     r8, [rbp+4Fh+Timeout]
0x14006fc48  mov     edx, 424Dh
0x14006fc4d  mov     byte ptr [rbp+4Fh+arg_20], bl
0x14006fc50  mov     rcx, rdi
0x14006fc53  mov     [rbp+4Fh+var_90], ebx
0x14006fc56  mov     [rbp+4Fh+var_70], rbx
0x14006fc5a  mov     byte ptr [rbp+4Fh+Timeout], bl
0x14006fc5d  call    HsmiGetBitmap
0x14006fc62  test    rax, rax
0x14006fc65  jz      short loc_14006FC8F
0x14006fc67  lea     rcx, [rbp+4Fh+var_80]
0x14006fc6b  mov     [rsp+0F0h+Irp], rcx
0x14006fc70  lea     r9, [rbp+4Fh+arg_20]
0x14006fc74  mov     rcx, rax
0x14006fc77  lea     r8, [rbp+4Fh+var_78]
0x14006fc7b  lea     rdx, [rbp+4Fh+var_88]
0x14006fc7f  call    HsmpBitmapQueryRange
0x14006fc84  mov     ecx, eax
0x14006fc86  mov     ebx, eax
0x14006fc88  call    HsmDbgBreakOnStatus
0x14006fc8d  jmp     short loc_14006FC99
0x14006fc8f  mov     al, byte ptr [rbp+4Fh+Timeout]
0x14006fc92  mov     byte ptr [rbp+4Fh+arg_20], al
0x14006fc95  mov     [rbp+4Fh+var_80], r9
0x14006fc99  mov     ecx, ebx
0x14006fc9b  call    HsmDbgBreakOnStatus
0x14006fca0  test    ebx, ebx
0x14006fca2  js      loc_140070138
0x14006fca8  cmp     byte ptr [rbp+4Fh+arg_20], 0
0x14006fcac  jz      short loc_14006FD19
0x14006fcae  mov     r10, cs:WPP_GLOBAL_Control
0x14006fcb5  cmp     r10, rsi
0x14006fcb8  jz      loc_14006FFCB
0x14006fcbe  mov     eax, [r10+2Ch]
0x14006fcc2  test    al, 1
0x14006fcc4  jz      loc_14006FFCB
0x14006fcca  cmp     byte ptr [r10+29h], 4
0x14006fccf  jb      loc_14006FFCB
0x14006fcd5  mov     rcx, rdi
0x14006fcd8  call    HsmpGetStreamSize
0x14006fcdd  mov     rcx, [r10+18h]
0x14006fce1  mov     r8, rax
0x14006fce4  mov     rax, [rbp+4Fh+var_80]
0x14006fce8  mov     edx, 0Bh
0x14006fced  mov     [rsp+0F0h+var_B0], rax
0x14006fcf2  mov     r9, r12
0x14006fcf5  mov     rax, [rbp+4Fh+var_88]
0x14006fcf9  mov     [rsp+0F0h+var_B8], rax
0x14006fcfe  mov     eax, [rdi+1Ch]
0x14006fd01  mov     [rsp+0F0h+var_C0], r8
0x14006fd06  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14006fd0a  mov     [rsp+0F0h+Irp], rdi
0x14006fd0f  call    WPP_SF_iqLiii
0x14006fd14  jmp     loc_14006FFCB
0x14006fd19  mov     r10, cs:WPP_GLOBAL_Control
0x14006fd20  cmp     r10, rsi
0x14006fd23  jz      short loc_14006FD73
0x14006fd25  mov     eax, [r10+2Ch]
0x14006fd29  test    al, 1
0x14006fd2b  jz      short loc_14006FD73
0x14006fd2d  cmp     byte ptr [r10+29h], 4
0x14006fd32  jb      short loc_14006FD73
0x14006fd34  mov     rcx, rdi
0x14006fd37  call    HsmpGetStreamSize
0x14006fd3c  mov     rcx, [r10+18h]
0x14006fd40  mov     r8, rax
0x14006fd43  mov     rax, [rbp+4Fh+var_80]
0x14006fd47  mov     edx, 0Ch
0x14006fd4c  mov     [rsp+0F0h+var_B0], rax
0x14006fd51  mov     r9, r12
0x14006fd54  mov     rax, [rbp+4Fh+var_88]
0x14006fd58  mov     [rsp+0F0h+var_B8], rax
0x14006fd5d  mov     eax, [rdi+1Ch]
0x14006fd60  mov     [rsp+0F0h+var_C0], r8
0x14006fd65  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14006fd69  mov     [rsp+0F0h+Irp], rdi
0x14006fd6e  call    WPP_SF_iqLiii
0x14006fd73  mov     rax, [rbp+4Fh+var_88]
0x14006fd77  mov     r14d, dword ptr [rbp+4Fh+var_80]
0x14006fd7b  sub     r14d, eax
0x14006fd7e  mov     [rbp+4Fh+var_70], rax
0x14006fd82  mov     esi, r14d
0x14006fd85  and     esi, 0FFFFF000h
0x14006fd8b  jnz     loc_14006FE94
0x14006fd91  xor     ebx, ebx
0x14006fd93  test    r13, r13
0x14006fd96  jnz     short loc_14006FDBE
0x14006fd98  mov     edx, 1000h
0x14006fd9d  lea     ecx, [rsi+40h]
0x14006fda0  mov     r8d, 77527348h
0x14006fda6  call    cs:__imp_ExAllocatePool2
0x14006fdad  nop     dword ptr [rax+rax+00h]
0x14006fdb2  mov     r13, rax
0x14006fdb5  test    rax, rax
0x14006fdb8  jz      loc_14006FFD8
0x14006fdbe  test    r15, r15
0x14006fdc1  jnz     short loc_14006FDFD
0x14006fdc3  xor     r9d, r9d; ChargeQuota
0x14006fdc6  mov     [rsp+0F0h+Irp], rbx; Irp
0x14006fdcb  xor     r8d, r8d; SecondaryBuffer
0x14006fdce  mov     edx, 1000h; Length
0x14006fdd3  mov     rcx, r13; VirtualAddress
0x14006fdd6  call    cs:__imp_IoAllocateMdl
0x14006fddd  nop     dword ptr [rax+rax+00h]
0x14006fde2  mov     r15, rax
0x14006fde5  test    rax, rax
0x14006fde8  jz      loc_14007002A
0x14006fdee  mov     rcx, rax; MemoryDescriptorList
0x14006fdf1  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14006fdf8  nop     dword ptr [rax+rax+00h]
0x14006fdfd  mov     rdx, [rbp+4Fh+arg_8]
0x14006fe01  lea     rax, [rbp+4Fh+var_90]
0x14006fe05  mov     rcx, [rbp+4Fh+var_68]
0x14006fe09  lea     r8, [rbp+4Fh+var_70]
0x14006fe0d  mov     [rsp+50h], r15
0x14006fe12  mov     r9d, 1000h
0x14006fe18  mov     [rsp+0F0h+var_A8], rbx
0x14006fe1d  mov     [rsp+0F0h+var_B0], rbx
0x14006fe22  mov     [rsp+0F0h+var_B8], rbx
0x14006fe27  mov     [rsp+0F0h+var_C0], rax
0x14006fe2c  mov     dword ptr [rsp+0F0h+var_C8], 0Ah
0x14006fe34  mov     [rsp+0F0h+Irp], rbx
0x14006fe39  call    cs:__imp_FltReadFileEx
0x14006fe40  nop     dword ptr [rax+rax+00h]
0x14006fe45  mov     ecx, eax
0x14006fe47  mov     ebx, eax
0x14006fe49  call    HsmDbgBreakOnStatus
0x14006fe4e  cmp     ebx, 0C0000011h
0x14006fe54  jz      loc_1400700F4
0x14006fe5a  test    ebx, ebx
0x14006fe5c  js      loc_1400700B7
0x14006fe62  cmp     [rbp+4Fh+var_90], r14d
0x14006fe66  jb      loc_1400700AB
0x14006fe6c  mov     rcx, [rbp+4Fh+var_88]
0x14006fe70  mov     esi, 1000h
0x14006fe75  mov     r8d, dword ptr [rbp+4Fh+var_80]
0x14006fe79  sub     r8d, ecx; Size
0x14006fe7c  sub     ecx, dword ptr [rbp+4Fh+arg_18]
0x14006fe7f  mov     edx, ecx
0x14006fe81  mov     rcx, r13; void *
0x14006fe84  add     rdx, [rbp+4Fh+arg_10]; Src
0x14006fe88  call    memmove
0x14006fe8d  xor     eax, eax
0x14006fe8f  mov     rcx, r15
0x14006fe92  jmp     short loc_14006FEA0
0x14006fe94  sub     eax, dword ptr [rbp+4Fh+arg_18]
0x14006fe97  mov     r14d, esi
0x14006fe9a  add     rax, [rbp+4Fh+arg_10]
0x14006fe9e  xor     ecx, ecx
0x14006fea0  mov     rdx, [rbp+4Fh+arg_8]
0x14006fea4  lea     r8, [rbp+4Fh+var_70]
0x14006fea8  mov     [rsp+50h], rcx
0x14006fead  mov     r9d, esi
0x14006feb0  xor     ecx, ecx
0x14006feb2  mov     [rsp+0F0h+var_A8], rcx
0x14006feb7  mov     [rsp+0F0h+var_B0], rcx
0x14006febc  mov     [rsp+0F0h+var_B8], rcx
0x14006fec1  lea     rcx, [rbp+4Fh+var_90]
0x14006fec5  mov     [rsp+0F0h+var_C0], rcx
0x14006feca  mov     rcx, [rbp+4Fh+var_68]
0x14006fece  mov     dword ptr [rsp+0F0h+var_C8], 0Ah
0x14006fed6  mov     [rsp+0F0h+Irp], rax
0x14006fedb  call    cs:__imp_FltWriteFileEx
0x14006fee2  nop     dword ptr [rax+rax+00h]
0x14006fee7  mov     ecx, eax
0x14006fee9  mov     ebx, eax
0x14006feeb  call    HsmDbgBreakOnStatus
0x14006fef0  cmp     ebx, 0C0000054h
0x14006fef6  jnz     loc_14006FFA8
0x14006fefc  xor     eax, eax
0x14006fefe  lea     rcx, [rbp+4Fh+Event]; Event
0x14006ff02  xorps   xmm0, xmm0
0x14006ff05  mov     [rbp+4Fh+Event.Header.WaitListHead.Blink], rax
0x14006ff09  xor     r8d, r8d; State
0x14006ff0c  mov     qword ptr [rbp+4Fh+Timeout], rax
0x14006ff10  xor     edx, edx; Type
0x14006ff12  movups  xmmword ptr [rbp+4Fh+Event.Header], xmm0
0x14006ff16  call    cs:__imp_KeInitializeEvent
0x14006ff1d  nop     dword ptr [rax+rax+00h]
0x14006ff22  lea     rax, [rbp+4Fh+Timeout]
0x14006ff26  mov     qword ptr [rbp+4Fh+Timeout], 0FFFFFFFFFFFFD8F0h
0x14006ff2e  xor     r9d, r9d; Alertable
0x14006ff31  mov     [rsp+0F0h+Irp], rax; Timeout
0x14006ff36  xor     r8d, r8d; WaitMode
0x14006ff39  lea     rcx, [rbp+4Fh+Event]; Object
0x14006ff3d  xor     edx, edx; WaitReason
0x14006ff3f  call    cs:__imp_KeWaitForSingleObject
0x14006ff46  nop     dword ptr [rax+rax+00h]
0x14006ff4b  mov     ecx, eax
0x14006ff4d  mov     ebx, eax
0x14006ff4f  call    HsmDbgBreakOnStatus
0x14006ff54  cmp     ebx, 102h
0x14006ff5a  jz      loc_14006FD73
0x14006ff60  test    ebx, ebx
0x14006ff62  jz      loc_14006FD73
0x14006ff68  mov     r10, cs:WPP_GLOBAL_Control
0x14006ff6f  lea     rax, WPP_GLOBAL_Control
0x14006ff76  cmp     r10, rax
0x14006ff79  jz      loc_140070193
0x14006ff7f  mov     eax, [r10+2Ch]
0x14006ff83  test    al, 1
0x14006ff85  jz      loc_140070193
0x14006ff8b  cmp     byte ptr [r10+29h], 2
0x14006ff90  jb      loc_140070193
0x14006ff96  mov     rcx, rdi
0x14006ff99  call    HsmpGetStreamSize
0x14006ff9e  mov     edx, 10h
0x14006ffa3  jmp     loc_140070160
0x14006ffa8  test    ebx, ebx
0x14006ffaa  js      loc_140070107
0x14006ffb0  cmp     [rbp+4Fh+var_90], r14d
0x14006ffb4  jb      loc_1400700FB
0x14006ffba  mov     eax, esi
0x14006ffbc  lea     rsi, WPP_GLOBAL_Control
0x14006ffc3  add     rax, [rbp+4Fh+var_88]
0x14006ffc7  mov     [rbp+4Fh+var_80], rax
0x14006ffcb  mov     rax, [rbp+4Fh+var_80]
0x14006ffcf  mov     r9, [rbp+4Fh+var_78]
0x14006ffd3  jmp     loc_14006FC35
0x14006ffd8  mov     esi, 0C000009Ah
0x14006ffdd  mov     ecx, esi
0x14006ffdf  mov     ebx, esi
0x14006ffe1  call    HsmDbgBreakOnStatus
0x14006ffe6  mov     r10, cs:WPP_GLOBAL_Control
0x14006ffed  lea     rax, WPP_GLOBAL_Control
0x14006fff4  cmp     r10, rax
0x14006fff7  jz      loc_140070193
0x14006fffd  mov     eax, [r10+2Ch]
0x140070001  test    al, 1
0x140070003  jz      loc_140070193
0x140070009  cmp     byte ptr [r10+29h], 2
0x14007000e  jb      loc_140070193
0x140070014  mov     rcx, rdi
0x140070017  call    HsmpGetStreamSize
0x14007001c  mov     edx, 0Dh
0x140070021  mov     dword ptr [rsp+0F0h+var_A8], esi
0x140070025  jmp     loc_140070164
0x14007002a  mov     esi, 0C000009Ah
0x14007002f  mov     ecx, esi
0x140070031  mov     ebx, esi
0x140070033  call    HsmDbgBreakOnStatus
0x140070038  mov     r10, cs:WPP_GLOBAL_Control
0x14007003f  lea     rax, WPP_GLOBAL_Control
0x140070046  cmp     r10, rax
0x140070049  jz      loc_1400701A7
0x14007004f  mov     eax, [r10+2Ch]
0x140070053  test    al, 1
0x140070055  jz      loc_1400701A7
0x14007005b  cmp     byte ptr [r10+29h], 2
0x140070060  jb      loc_1400701A7
0x140070066  mov     rcx, rdi
0x140070069  call    HsmpGetStreamSize
0x14007006e  mov     r8, [rbp+4Fh+var_78]
0x140070072  mov     edx, 0Eh
0x140070077  mov     rcx, [r10+18h]
0x14007007b  mov     r9, r12
0x14007007e  mov     dword ptr [rsp+0F0h+var_A8], esi
0x140070082  mov     [rsp+0F0h+var_B0], r8
0x140070087  mov     r8, [rbp+4Fh+var_88]
0x14007008b  mov     [rsp+0F0h+var_B8], r8
0x140070090  mov     [rsp+0F0h+var_C0], rax
0x140070095  mov     eax, [rdi+1Ch]
0x140070098  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14007009c  mov     [rsp+0F0h+Irp], rdi
0x1400700a1  call    WPP_SF_iqLiiid
0x1400700a6  jmp     loc_1400701A7
  ... truncated ...
```
