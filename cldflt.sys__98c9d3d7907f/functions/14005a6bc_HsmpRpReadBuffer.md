# HsmpRpReadBuffer

- ea: `0x14005a6bc`
- end: `0x14005aadb`
- name: `HsmpRpReadBuffer`
- size: `1055`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14005aaf0`
- `0x140067d04`
- `0x14006ac24`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000cf58`
- `0x14000db8c`
- `0x14005a6bc`

## import_xrefs

- `ntoskrnl!RtlDecompressBuffer` at `0x14005a81a`
- `ntoskrnl!RtlDecompressBuffer` at `0x14005a81a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a8b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a8fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a867`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a8b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a8fd`
- `ntoskrnl!ExAllocatePool2` at `0x14005a6f6`
- `ntoskrnl!ExAllocatePool2` at `0x14005a7cf`
- `ntoskrnl!ExAllocatePool2` at `0x14005a919`
- `ntoskrnl!ExAllocatePool2` at `0x14005a6f6`
- `ntoskrnl!ExAllocatePool2` at `0x14005a7cf`
- `ntoskrnl!ExAllocatePool2` at `0x14005a919`
- `FLTMGR!FltFsControlFile` at `0x14005a737`
- `FLTMGR!FltFsControlFile` at `0x14005aab0`
- `FLTMGR!FltFsControlFile` at `0x14005a737`
- `FLTMGR!FltFsControlFile` at `0x14005aab0`

## pseudocode

```c
__int64 __fastcall HsmpRpReadBuffer(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, UCHAR **a3)
{
  unsigned int v6; // esi
  UCHAR *OutputBuffer; // rax
  UCHAR *v8; // rdi
  __int64 v9; // rbx
  unsigned int v10; // ecx
  int v11; // ecx
  int v12; // ebx
  __int64 v13; // rax
  _WORD *v14; // rbp
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  UCHAR *Pool2; // rax
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  ULONG FinalUncompressedSize; // [rsp+90h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = 1024;
  OutputBuffer = (UCHAR *)ExAllocatePool2(256, 1024, 1884451656);
  v8 = OutputBuffer;
  if ( !OutputBuffer )
  {
    LODWORD(v9) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)v9;
    }
    v17 = 16;
    goto LABEL_31;
  }
  v9 = (unsigned int)FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, OutputBuffer, 0x400u, 0);
  HsmDbgBreakOnStatus(v9);
  if ( (_DWORD)v9 == -1073741789 || (_DWORD)v9 == -2147483643 )
  {
    ExFreePoolWithTag(v8, 0x70527348u);
    Pool2 = (UCHAR *)ExAllocatePool2(256, 0x4000, 1884451656);
    v8 = Pool2;
    if ( Pool2 )
    {
      v6 = 0x4000;
      v9 = (unsigned int)FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, Pool2, 0x4000u, 0);
      HsmDbgBreakOnStatus(v9);
      goto LABEL_4;
    }
    LODWORD(v9) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)v9;
    }
    v17 = 17;
LABEL_31:
    WPP_SF_qqd(v16->AttachedDevice, v17, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, Instance, FileObject);
    return (unsigned int)v9;
  }
LABEL_4:
  if ( (int)v9 < 0 )
  {
    if ( (_DWORD)v9 == -1073741195 )
      goto LABEL_16;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_16;
    }
    v20 = 18;
    goto LABEL_37;
  }
  v10 = *((unsigned __int16 *)v8 + 2);
  if ( v6 < v10 )
  {
    LODWORD(v9) = -1073741195;
    HsmDbgBreakOnStatus(3221226101LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqDDDd(
        WPP_GLOBAL_Control->AttachedDevice,
        v21,
        v22,
        Instance,
        FileObject,
        v6,
        *((unsigned __int16 *)v8 + 2));
    }
    goto LABEL_16;
  }
  if ( (*(_DWORD *)v8 & 0xFFFF0FFF) == dword_140029670 )
  {
    FinalUncompressedSize = 0;
    if ( v10 < 4 || (v11 = *((unsigned __int16 *)v8 + 5), (unsigned __int16)(v11 - 4) > 0x3FFCu) )
    {
      v14 = 0;
    }
    else
    {
      if ( (*((_DWORD *)v8 + 2) & 0x8000) == 0 )
      {
        LODWORD(v9) = 0;
        *a3 = v8;
        goto LABEL_14;
      }
      v12 = v11 + 8;
      v13 = ExAllocatePool2(256, (unsigned int)(v11 + 8), 1884451656);
      v14 = (_WORD *)v13;
      if ( !v13 )
      {
        LODWORD(v9) = -1073741670;
LABEL_20:
        HsmDbgBreakOnStatus((unsigned int)v9);
        if ( v14 )
          ExFreePoolWithTag(v14, 0x70527348u);
        goto LABEL_14;
      }
      *(_QWORD *)v13 = *(_QWORD *)v8;
      *(_DWORD *)(v13 + 8) = *((_DWORD *)v8 + 2);
      v9 = (unsigned int)RtlDecompressBuffer(2u, (PUCHAR)(v13 + 12), v12 - 12, v8 + 12, v6 - 12, &FinalUncompressedSize);
      HsmDbgBreakOnStatus(v9);
      if ( (int)v9 >= 0 && FinalUncompressedSize <= 0xFFFF )
      {
        v14[2] = *((_WORD *)v8 + 5);
        *a3 = (UCHAR *)v14;
LABEL_14:
        HsmDbgBreakOnStatus((unsigned int)v9);
        if ( (int)v9 >= 0 )
          goto LABEL_15;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_16;
        }
        v20 = 20;
LABEL_37:
        WPP_SF_qqd(v19->AttachedDevice, v20, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, Instance, FileObject);
        goto LABEL_16;
      }
    }
    HsmDbgBreakOnCorruption();
    LODWORD(v9) = -1073688830;
    goto LABEL_20;
  }
  *a3 = v8;
LABEL_15:
  if ( *a3 != v8 )
LABEL_16:
    ExFreePoolWithTag(v8, 0x70527348u);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14005a6bc  mov     [rsp+arg_0], rbx
0x14005a6c1  mov     [rsp+arg_8], rbp
0x14005a6c6  push    rsi
0x14005a6c7  push    rdi
0x14005a6c8  push    r12
0x14005a6ca  push    r14
0x14005a6cc  push    r15
0x14005a6ce  sub     rsp, 50h
0x14005a6d2  mov     r14, r8
0x14005a6d5  mov     qword ptr [r8], 0
0x14005a6dc  mov     r15, rdx
0x14005a6df  mov     r12, rcx
0x14005a6e2  mov     esi, 400h
0x14005a6e7  mov     ebp, 100h
0x14005a6ec  mov     edx, esi
0x14005a6ee  mov     ecx, ebp
0x14005a6f0  mov     r8d, 70527348h
0x14005a6f6  call    cs:__imp_ExAllocatePool2
0x14005a6fd  nop     dword ptr [rax+rax+00h]
0x14005a702  mov     rdi, rax
0x14005a705  test    rax, rax
0x14005a708  jz      loc_14005A8C0
0x14005a70e  mov     [rsp+78h+LengthReturned], 0; LengthReturned
0x14005a717  xor     r9d, r9d; InputBuffer
0x14005a71a  mov     [rsp+78h+OutputBufferLength], esi; OutputBufferLength
0x14005a71e  mov     r8d, 900A8h; FsControlCode
0x14005a724  mov     [rsp+78h+OutputBuffer], rax; OutputBuffer
0x14005a729  mov     rdx, r15; FileObject
0x14005a72c  mov     rcx, r12; Instance
0x14005a72f  mov     [rsp+78h+InputBufferLength], 0; InputBufferLength
0x14005a737  call    cs:__imp_FltFsControlFile
0x14005a73e  nop     dword ptr [rax+rax+00h]
0x14005a743  mov     ecx, eax
0x14005a745  mov     ebx, eax
0x14005a747  call    HsmDbgBreakOnStatus
0x14005a74c  cmp     ebx, 0C0000023h
0x14005a752  jz      loc_14005A8F5
0x14005a758  cmp     ebx, 80000005h
0x14005a75e  jz      loc_14005A8F5
0x14005a764  test    ebx, ebx
0x14005a766  js      loc_14005A9EB
0x14005a76c  movzx   ecx, word ptr [rdi+4]
0x14005a770  cmp     esi, ecx
0x14005a772  jb      loc_14005AA2B
0x14005a778  mov     eax, [rdi]
0x14005a77a  and     eax, 0FFFF0FFFh
0x14005a77f  cmp     eax, cs:dword_140029670
0x14005a785  jnz     loc_14005A88F
0x14005a78b  mov     [rsp+78h+FinalUncompressedSize], 0
0x14005a796  cmp     ecx, 4
0x14005a799  jb      loc_14005AAD4
0x14005a79f  movzx   ecx, word ptr [rdi+0Ah]
0x14005a7a3  mov     edx, 3FFCh
0x14005a7a8  lea     eax, [rcx-4]
0x14005a7ab  cmp     ax, dx
0x14005a7ae  ja      loc_14005AAD4
0x14005a7b4  test    dword ptr [rdi+8], 8000h
0x14005a7bb  jz      loc_14005A98F
0x14005a7c1  lea     ebx, [rcx+8]
0x14005a7c4  mov     r8d, 70527348h
0x14005a7ca  mov     edx, ebx
0x14005a7cc  mov     rcx, rbp
0x14005a7cf  call    cs:__imp_ExAllocatePool2
0x14005a7d6  nop     dword ptr [rax+rax+00h]
0x14005a7db  mov     rbp, rax
0x14005a7de  test    rax, rax
0x14005a7e1  jz      loc_14005AACA
0x14005a7e7  movsd   xmm0, qword ptr [rdi]
0x14005a7eb  lea     r10, [rsp+78h+FinalUncompressedSize]
0x14005a7f3  movsd   qword ptr [rax], xmm0
0x14005a7f7  lea     r9, [rdi+0Ch]; CompressedBuffer
0x14005a7fb  mov     eax, [rdi+8]
0x14005a7fe  lea     r8d, [rbx-0Ch]; UncompressedBufferSize
0x14005a802  mov     [rbp+8], eax
0x14005a805  lea     rdx, [rbp+0Ch]; UncompressedBuffer
0x14005a809  lea     eax, [rsi-0Ch]
0x14005a80c  mov     [rsp+78h+OutputBuffer], r10; FinalUncompressedSize
0x14005a811  mov     ecx, 2; CompressionFormat
0x14005a816  mov     [rsp+78h+InputBufferLength], eax; CompressedBufferSize
0x14005a81a  call    cs:__imp_RtlDecompressBuffer
0x14005a821  nop     dword ptr [rax+rax+00h]
0x14005a826  mov     ecx, eax
0x14005a828  mov     ebx, eax
0x14005a82a  call    HsmDbgBreakOnStatus
0x14005a82f  test    ebx, ebx
0x14005a831  js      short loc_14005A894
0x14005a833  cmp     [rsp+78h+FinalUncompressedSize], 0FFFFh
0x14005a83e  ja      short loc_14005A894
0x14005a840  movzx   eax, word ptr [rdi+0Ah]
0x14005a844  mov     [rbp+4], ax
0x14005a848  mov     [r14], rbp
0x14005a84b  mov     ecx, ebx
0x14005a84d  call    HsmDbgBreakOnStatus
0x14005a852  test    ebx, ebx
0x14005a854  js      loc_14005A999
0x14005a85a  cmp     [r14], rdi
0x14005a85d  jz      short loc_14005A873
0x14005a85f  mov     edx, 70527348h; Tag
0x14005a864  mov     rcx, rdi; P
0x14005a867  call    cs:__imp_ExFreePoolWithTag
0x14005a86e  nop     dword ptr [rax+rax+00h]
0x14005a873  lea     r11, [rsp+78h+var_28]
0x14005a878  mov     eax, ebx
0x14005a87a  mov     rbx, [r11+30h]
0x14005a87e  mov     rbp, [r11+38h]
0x14005a882  mov     rsp, r11
0x14005a885  pop     r15
0x14005a887  pop     r14
0x14005a889  pop     r12
0x14005a88b  pop     rdi
0x14005a88c  pop     rsi
0x14005a88d  retn
0x14005a88f  mov     [r14], rdi
0x14005a892  jmp     short loc_14005A85A
0x14005a894  call    HsmDbgBreakOnCorruption
0x14005a899  mov     ebx, 0C000CF02h
0x14005a89e  mov     ecx, ebx
0x14005a8a0  call    HsmDbgBreakOnStatus
0x14005a8a5  test    rbp, rbp
0x14005a8a8  jz      short loc_14005A84B
0x14005a8aa  mov     edx, 70527348h; Tag
0x14005a8af  mov     rcx, rbp; P
0x14005a8b2  call    cs:__imp_ExFreePoolWithTag
0x14005a8b9  nop     dword ptr [rax+rax+00h]
0x14005a8be  jmp     short loc_14005A84B
0x14005a8c0  mov     esi, 0C000009Ah
0x14005a8c5  mov     ecx, esi
0x14005a8c7  mov     ebx, esi
0x14005a8c9  call    HsmDbgBreakOnStatus
0x14005a8ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a8d5  lea     rax, WPP_GLOBAL_Control
0x14005a8dc  cmp     rcx, rax
0x14005a8df  jz      short loc_14005A873
0x14005a8e1  mov     eax, [rcx+2Ch]
0x14005a8e4  test    al, 1
0x14005a8e6  jz      short loc_14005A873
0x14005a8e8  cmp     byte ptr [rcx+29h], 2
0x14005a8ec  jb      short loc_14005A873
0x14005a8ee  mov     edx, 10h
0x14005a8f3  jmp     short loc_14005A96E
0x14005a8f5  mov     edx, 70527348h; Tag
0x14005a8fa  mov     rcx, rdi; P
0x14005a8fd  call    cs:__imp_ExFreePoolWithTag
0x14005a904  nop     dword ptr [rax+rax+00h]
0x14005a909  mov     ebx, 4000h
0x14005a90e  mov     r8d, 70527348h
0x14005a914  mov     edx, ebx
0x14005a916  mov     rcx, rbp
0x14005a919  call    cs:__imp_ExAllocatePool2
0x14005a920  nop     dword ptr [rax+rax+00h]
0x14005a925  mov     rdi, rax
0x14005a928  test    rax, rax
0x14005a92b  jnz     loc_14005AA85
0x14005a931  mov     esi, 0C000009Ah
0x14005a936  mov     ecx, esi
0x14005a938  mov     ebx, esi
0x14005a93a  call    HsmDbgBreakOnStatus
0x14005a93f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a946  lea     rax, WPP_GLOBAL_Control
0x14005a94d  cmp     rcx, rax
0x14005a950  jz      loc_14005A873
0x14005a956  mov     eax, [rcx+2Ch]
0x14005a959  test    al, 1
0x14005a95b  jz      loc_14005A873
0x14005a961  cmp     byte ptr [rcx+29h], 2
0x14005a965  jb      loc_14005A873
0x14005a96b  lea     edx, [rdi+11h]
0x14005a96e  mov     rcx, [rcx+18h]
0x14005a972  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14005a979  mov     dword ptr [rsp+78h+OutputBuffer], esi
0x14005a97d  mov     r9, r12
0x14005a980  mov     qword ptr [rsp+78h+InputBufferLength], r15
0x14005a985  call    WPP_SF_qqd
0x14005a98a  jmp     loc_14005A873
0x14005a98f  xor     ebx, ebx
0x14005a991  mov     [r14], rdi
0x14005a994  jmp     loc_14005A84B
0x14005a999  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a9a0  lea     rax, WPP_GLOBAL_Control
0x14005a9a7  cmp     rcx, rax
0x14005a9aa  jz      loc_14005A85F
0x14005a9b0  mov     eax, [rcx+2Ch]
0x14005a9b3  test    al, 1
0x14005a9b5  jz      loc_14005A85F
0x14005a9bb  cmp     byte ptr [rcx+29h], 2
0x14005a9bf  jb      loc_14005A85F
0x14005a9c5  mov     edx, 14h
0x14005a9ca  mov     rcx, [rcx+18h]
0x14005a9ce  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14005a9d5  mov     dword ptr [rsp+78h+OutputBuffer], ebx
0x14005a9d9  mov     r9, r12
0x14005a9dc  mov     qword ptr [rsp+78h+InputBufferLength], r15
0x14005a9e1  call    WPP_SF_qqd
0x14005a9e6  jmp     loc_14005A85F
0x14005a9eb  mov     ecx, 0C0000275h
0x14005a9f0  cmp     ebx, ecx
0x14005a9f2  jz      loc_14005A85F
0x14005a9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a9ff  lea     rax, WPP_GLOBAL_Control
0x14005aa06  cmp     rcx, rax
0x14005aa09  jz      loc_14005A85F
0x14005aa0f  mov     eax, [rcx+2Ch]
0x14005aa12  test    al, 1
0x14005aa14  jz      loc_14005A85F
0x14005aa1a  cmp     byte ptr [rcx+29h], 2
0x14005aa1e  jb      loc_14005A85F
0x14005aa24  mov     edx, 12h
0x14005aa29  jmp     short loc_14005A9CA
0x14005aa2b  mov     ecx, 0C0000275h
0x14005aa30  mov     ebx, ecx
0x14005aa32  call    HsmDbgBreakOnStatus
0x14005aa37  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aa3e  lea     rax, WPP_GLOBAL_Control
0x14005aa45  cmp     rcx, rax
0x14005aa48  jz      loc_14005A85F
0x14005aa4e  mov     eax, [rcx+2Ch]
0x14005aa51  test    al, 1
0x14005aa53  jz      loc_14005A85F
0x14005aa59  cmp     byte ptr [rcx+29h], 2
0x14005aa5d  jb      loc_14005A85F
0x14005aa63  movzx   eax, word ptr [rdi+4]
0x14005aa67  mov     r9, r12
0x14005aa6a  mov     rcx, [rcx+18h]
0x14005aa6e  mov     [rsp+78h+OutputBufferLength], eax
0x14005aa72  mov     dword ptr [rsp+78h+OutputBuffer], esi
0x14005aa76  mov     qword ptr [rsp+78h+InputBufferLength], r15
0x14005aa7b  call    WPP_SF_qqDDDd
0x14005aa80  jmp     loc_14005A85F
0x14005aa85  mov     [rsp+78h+LengthReturned], 0; LengthReturned
0x14005aa8e  xor     r9d, r9d; InputBuffer
0x14005aa91  mov     [rsp+78h+OutputBufferLength], ebx; OutputBufferLength
0x14005aa95  mov     r8d, 900A8h; FsControlCode
0x14005aa9b  mov     [rsp+78h+OutputBuffer], rax; OutputBuffer
0x14005aaa0  mov     rdx, r15; FileObject
0x14005aaa3  mov     rcx, r12; Instance
0x14005aaa6  mov     [rsp+78h+InputBufferLength], 0; InputBufferLength
0x14005aaae  mov     esi, ebx
0x14005aab0  call    cs:__imp_FltFsControlFile
0x14005aab7  nop     dword ptr [rax+rax+00h]
0x14005aabc  mov     ecx, eax
0x14005aabe  mov     ebx, eax
0x14005aac0  call    HsmDbgBreakOnStatus
0x14005aac5  jmp     loc_14005A764
0x14005aaca  mov     ebx, 0C000009Ah
0x14005aacf  jmp     loc_14005A89E
0x14005aad4  xor     ebp, ebp
0x14005aad6  jmp     loc_14005A894
```
