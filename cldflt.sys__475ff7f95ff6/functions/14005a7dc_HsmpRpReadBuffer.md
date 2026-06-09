# HsmpRpReadBuffer

- ea: `0x14005a7dc`
- end: `0x14005abfb`
- name: `HsmpRpReadBuffer`
- size: `1055`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14005ac10`
- `0x140067e24`
- `0x14006ad44`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000cf58`
- `0x14000db8c`
- `0x14005a7dc`

## import_xrefs

- `ntoskrnl!RtlDecompressBuffer` at `0x14005a93a`
- `ntoskrnl!RtlDecompressBuffer` at `0x14005a93a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a987`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a9d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005aa1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a987`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a9d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005aa1d`
- `ntoskrnl!ExAllocatePool2` at `0x14005a816`
- `ntoskrnl!ExAllocatePool2` at `0x14005a8ef`
- `ntoskrnl!ExAllocatePool2` at `0x14005aa39`
- `ntoskrnl!ExAllocatePool2` at `0x14005a816`
- `ntoskrnl!ExAllocatePool2` at `0x14005a8ef`
- `ntoskrnl!ExAllocatePool2` at `0x14005aa39`
- `FLTMGR!FltFsControlFile` at `0x14005a857`
- `FLTMGR!FltFsControlFile` at `0x14005abd0`
- `FLTMGR!FltFsControlFile` at `0x14005a857`
- `FLTMGR!FltFsControlFile` at `0x14005abd0`

## pseudocode

```c
__int64 __fastcall HsmpRpReadBuffer(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, UCHAR **a3)
{
  unsigned int v6; // esi
  UCHAR *OutputBuffer; // rax
  UCHAR *v8; // rdi
  NTSTATUS v9; // ebx
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
    v9 = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
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
  v9 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, OutputBuffer, 0x400u, 0);
  HsmDbgBreakOnStatus(v9);
  if ( v9 == -1073741789 || v9 == -2147483643 )
  {
    ExFreePoolWithTag(v8, 0x70527348u);
    Pool2 = (UCHAR *)ExAllocatePool2(256, 0x4000, 1884451656);
    v8 = Pool2;
    if ( Pool2 )
    {
      v6 = 0x4000;
      v9 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, Pool2, 0x4000u, 0);
      HsmDbgBreakOnStatus(v9);
      goto LABEL_4;
    }
    v9 = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)v9;
    }
    v17 = 17;
LABEL_31:
    WPP_SF_qqd(
      v16->AttachedDevice,
      v17,
      WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
      Instance,
      FileObject,
      -1073741670);
    return (unsigned int)v9;
  }
LABEL_4:
  if ( v9 < 0 )
  {
    if ( v9 == -1073741195 )
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
    v9 = -1073741195;
    HsmDbgBreakOnStatus(-1073741195);
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
        v9 = 0;
        *a3 = v8;
        goto LABEL_14;
      }
      v12 = v11 + 8;
      v13 = ExAllocatePool2(256, (unsigned int)(v11 + 8), 1884451656);
      v14 = (_WORD *)v13;
      if ( !v13 )
      {
        v9 = -1073741670;
LABEL_20:
        HsmDbgBreakOnStatus(v9);
        if ( v14 )
          ExFreePoolWithTag(v14, 0x70527348u);
        goto LABEL_14;
      }
      *(_QWORD *)v13 = *(_QWORD *)v8;
      *(_DWORD *)(v13 + 8) = *((_DWORD *)v8 + 2);
      v9 = RtlDecompressBuffer(2u, (PUCHAR)(v13 + 12), v12 - 12, v8 + 12, v6 - 12, &FinalUncompressedSize);
      HsmDbgBreakOnStatus(v9);
      if ( v9 >= 0 && FinalUncompressedSize <= 0xFFFF )
      {
        v14[2] = *((_WORD *)v8 + 5);
        *a3 = (UCHAR *)v14;
LABEL_14:
        HsmDbgBreakOnStatus(v9);
        if ( v9 >= 0 )
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
        WPP_SF_qqd(v19->AttachedDevice, v20, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, Instance, FileObject, v9);
        goto LABEL_16;
      }
    }
    HsmDbgBreakOnCorruption();
    v9 = -1073688830;
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
0x14005a7dc  mov     [rsp+arg_0], rbx
0x14005a7e1  mov     [rsp+arg_8], rbp
0x14005a7e6  push    rsi
0x14005a7e7  push    rdi
0x14005a7e8  push    r12
0x14005a7ea  push    r14
0x14005a7ec  push    r15
0x14005a7ee  sub     rsp, 50h
0x14005a7f2  mov     r14, r8
0x14005a7f5  mov     qword ptr [r8], 0
0x14005a7fc  mov     r15, rdx
0x14005a7ff  mov     r12, rcx
0x14005a802  mov     esi, 400h
0x14005a807  mov     ebp, 100h
0x14005a80c  mov     edx, esi
0x14005a80e  mov     ecx, ebp
0x14005a810  mov     r8d, 70527348h
0x14005a816  call    cs:__imp_ExAllocatePool2
0x14005a81d  nop     dword ptr [rax+rax+00h]
0x14005a822  mov     rdi, rax
0x14005a825  test    rax, rax
0x14005a828  jz      loc_14005A9E0
0x14005a82e  mov     [rsp+78h+LengthReturned], 0; LengthReturned
0x14005a837  xor     r9d, r9d; InputBuffer
0x14005a83a  mov     [rsp+78h+OutputBufferLength], esi; OutputBufferLength
0x14005a83e  mov     r8d, 900A8h; FsControlCode
0x14005a844  mov     [rsp+78h+OutputBuffer], rax; OutputBuffer
0x14005a849  mov     rdx, r15; FileObject
0x14005a84c  mov     rcx, r12; Instance
0x14005a84f  mov     [rsp+78h+InputBufferLength], 0; InputBufferLength
0x14005a857  call    cs:__imp_FltFsControlFile
0x14005a85e  nop     dword ptr [rax+rax+00h]
0x14005a863  mov     ecx, eax
0x14005a865  mov     ebx, eax
0x14005a867  call    HsmDbgBreakOnStatus
0x14005a86c  cmp     ebx, 0C0000023h
0x14005a872  jz      loc_14005AA15
0x14005a878  cmp     ebx, 80000005h
0x14005a87e  jz      loc_14005AA15
0x14005a884  test    ebx, ebx
0x14005a886  js      loc_14005AB0B
0x14005a88c  movzx   ecx, word ptr [rdi+4]
0x14005a890  cmp     esi, ecx
0x14005a892  jb      loc_14005AB4B
0x14005a898  mov     eax, [rdi]
0x14005a89a  and     eax, 0FFFF0FFFh
0x14005a89f  cmp     eax, cs:dword_140029670
0x14005a8a5  jnz     loc_14005A9AF
0x14005a8ab  mov     [rsp+78h+FinalUncompressedSize], 0
0x14005a8b6  cmp     ecx, 4
0x14005a8b9  jb      loc_14005ABF4
0x14005a8bf  movzx   ecx, word ptr [rdi+0Ah]
0x14005a8c3  mov     edx, 3FFCh
0x14005a8c8  lea     eax, [rcx-4]
0x14005a8cb  cmp     ax, dx
0x14005a8ce  ja      loc_14005ABF4
0x14005a8d4  test    dword ptr [rdi+8], 8000h
0x14005a8db  jz      loc_14005AAAF
0x14005a8e1  lea     ebx, [rcx+8]
0x14005a8e4  mov     r8d, 70527348h
0x14005a8ea  mov     edx, ebx
0x14005a8ec  mov     rcx, rbp
0x14005a8ef  call    cs:__imp_ExAllocatePool2
0x14005a8f6  nop     dword ptr [rax+rax+00h]
0x14005a8fb  mov     rbp, rax
0x14005a8fe  test    rax, rax
0x14005a901  jz      loc_14005ABEA
0x14005a907  movsd   xmm0, qword ptr [rdi]
0x14005a90b  lea     r10, [rsp+78h+FinalUncompressedSize]
0x14005a913  movsd   qword ptr [rax], xmm0
0x14005a917  lea     r9, [rdi+0Ch]; CompressedBuffer
0x14005a91b  mov     eax, [rdi+8]
0x14005a91e  lea     r8d, [rbx-0Ch]; UncompressedBufferSize
0x14005a922  mov     [rbp+8], eax
0x14005a925  lea     rdx, [rbp+0Ch]; UncompressedBuffer
0x14005a929  lea     eax, [rsi-0Ch]
0x14005a92c  mov     [rsp+78h+OutputBuffer], r10; FinalUncompressedSize
0x14005a931  mov     ecx, 2; CompressionFormat
0x14005a936  mov     [rsp+78h+InputBufferLength], eax; CompressedBufferSize
0x14005a93a  call    cs:__imp_RtlDecompressBuffer
0x14005a941  nop     dword ptr [rax+rax+00h]
0x14005a946  mov     ecx, eax
0x14005a948  mov     ebx, eax
0x14005a94a  call    HsmDbgBreakOnStatus
0x14005a94f  test    ebx, ebx
0x14005a951  js      short loc_14005A9B4
0x14005a953  cmp     [rsp+78h+FinalUncompressedSize], 0FFFFh
0x14005a95e  ja      short loc_14005A9B4
0x14005a960  movzx   eax, word ptr [rdi+0Ah]
0x14005a964  mov     [rbp+4], ax
0x14005a968  mov     [r14], rbp
0x14005a96b  mov     ecx, ebx
0x14005a96d  call    HsmDbgBreakOnStatus
0x14005a972  test    ebx, ebx
0x14005a974  js      loc_14005AAB9
0x14005a97a  cmp     [r14], rdi
0x14005a97d  jz      short loc_14005A993
0x14005a97f  mov     edx, 70527348h; Tag
0x14005a984  mov     rcx, rdi; P
0x14005a987  call    cs:__imp_ExFreePoolWithTag
0x14005a98e  nop     dword ptr [rax+rax+00h]
0x14005a993  lea     r11, [rsp+78h+var_28]
0x14005a998  mov     eax, ebx
0x14005a99a  mov     rbx, [r11+30h]
0x14005a99e  mov     rbp, [r11+38h]
0x14005a9a2  mov     rsp, r11
0x14005a9a5  pop     r15
0x14005a9a7  pop     r14
0x14005a9a9  pop     r12
0x14005a9ab  pop     rdi
0x14005a9ac  pop     rsi
0x14005a9ad  retn
0x14005a9af  mov     [r14], rdi
0x14005a9b2  jmp     short loc_14005A97A
0x14005a9b4  call    HsmDbgBreakOnCorruption
0x14005a9b9  mov     ebx, 0C000CF02h
0x14005a9be  mov     ecx, ebx
0x14005a9c0  call    HsmDbgBreakOnStatus
0x14005a9c5  test    rbp, rbp
0x14005a9c8  jz      short loc_14005A96B
0x14005a9ca  mov     edx, 70527348h; Tag
0x14005a9cf  mov     rcx, rbp; P
0x14005a9d2  call    cs:__imp_ExFreePoolWithTag
0x14005a9d9  nop     dword ptr [rax+rax+00h]
0x14005a9de  jmp     short loc_14005A96B
0x14005a9e0  mov     esi, 0C000009Ah
0x14005a9e5  mov     ecx, esi
0x14005a9e7  mov     ebx, esi
0x14005a9e9  call    HsmDbgBreakOnStatus
0x14005a9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a9f5  lea     rax, WPP_GLOBAL_Control
0x14005a9fc  cmp     rcx, rax
0x14005a9ff  jz      short loc_14005A993
0x14005aa01  mov     eax, [rcx+2Ch]
0x14005aa04  test    al, 1
0x14005aa06  jz      short loc_14005A993
0x14005aa08  cmp     byte ptr [rcx+29h], 2
0x14005aa0c  jb      short loc_14005A993
0x14005aa0e  mov     edx, 10h
0x14005aa13  jmp     short loc_14005AA8E
0x14005aa15  mov     edx, 70527348h; Tag
0x14005aa1a  mov     rcx, rdi; P
0x14005aa1d  call    cs:__imp_ExFreePoolWithTag
0x14005aa24  nop     dword ptr [rax+rax+00h]
0x14005aa29  mov     ebx, 4000h
0x14005aa2e  mov     r8d, 70527348h
0x14005aa34  mov     edx, ebx
0x14005aa36  mov     rcx, rbp
0x14005aa39  call    cs:__imp_ExAllocatePool2
0x14005aa40  nop     dword ptr [rax+rax+00h]
0x14005aa45  mov     rdi, rax
0x14005aa48  test    rax, rax
0x14005aa4b  jnz     loc_14005ABA5
0x14005aa51  mov     esi, 0C000009Ah
0x14005aa56  mov     ecx, esi
0x14005aa58  mov     ebx, esi
0x14005aa5a  call    HsmDbgBreakOnStatus
0x14005aa5f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aa66  lea     rax, WPP_GLOBAL_Control
0x14005aa6d  cmp     rcx, rax
0x14005aa70  jz      loc_14005A993
0x14005aa76  mov     eax, [rcx+2Ch]
0x14005aa79  test    al, 1
0x14005aa7b  jz      loc_14005A993
0x14005aa81  cmp     byte ptr [rcx+29h], 2
0x14005aa85  jb      loc_14005A993
0x14005aa8b  lea     edx, [rdi+11h]
0x14005aa8e  mov     rcx, [rcx+18h]
0x14005aa92  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14005aa99  mov     dword ptr [rsp+78h+OutputBuffer], esi
0x14005aa9d  mov     r9, r12
0x14005aaa0  mov     qword ptr [rsp+78h+InputBufferLength], r15
0x14005aaa5  call    WPP_SF_qqd
0x14005aaaa  jmp     loc_14005A993
0x14005aaaf  xor     ebx, ebx
0x14005aab1  mov     [r14], rdi
0x14005aab4  jmp     loc_14005A96B
0x14005aab9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aac0  lea     rax, WPP_GLOBAL_Control
0x14005aac7  cmp     rcx, rax
0x14005aaca  jz      loc_14005A97F
0x14005aad0  mov     eax, [rcx+2Ch]
0x14005aad3  test    al, 1
0x14005aad5  jz      loc_14005A97F
0x14005aadb  cmp     byte ptr [rcx+29h], 2
0x14005aadf  jb      loc_14005A97F
0x14005aae5  mov     edx, 14h
0x14005aaea  mov     rcx, [rcx+18h]
0x14005aaee  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14005aaf5  mov     dword ptr [rsp+78h+OutputBuffer], ebx
0x14005aaf9  mov     r9, r12
0x14005aafc  mov     qword ptr [rsp+78h+InputBufferLength], r15
0x14005ab01  call    WPP_SF_qqd
0x14005ab06  jmp     loc_14005A97F
0x14005ab0b  mov     ecx, 0C0000275h
0x14005ab10  cmp     ebx, ecx
0x14005ab12  jz      loc_14005A97F
0x14005ab18  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab1f  lea     rax, WPP_GLOBAL_Control
0x14005ab26  cmp     rcx, rax
0x14005ab29  jz      loc_14005A97F
0x14005ab2f  mov     eax, [rcx+2Ch]
0x14005ab32  test    al, 1
0x14005ab34  jz      loc_14005A97F
0x14005ab3a  cmp     byte ptr [rcx+29h], 2
0x14005ab3e  jb      loc_14005A97F
0x14005ab44  mov     edx, 12h
0x14005ab49  jmp     short loc_14005AAEA
0x14005ab4b  mov     ecx, 0C0000275h
0x14005ab50  mov     ebx, ecx
0x14005ab52  call    HsmDbgBreakOnStatus
0x14005ab57  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab5e  lea     rax, WPP_GLOBAL_Control
0x14005ab65  cmp     rcx, rax
0x14005ab68  jz      loc_14005A97F
0x14005ab6e  mov     eax, [rcx+2Ch]
0x14005ab71  test    al, 1
0x14005ab73  jz      loc_14005A97F
0x14005ab79  cmp     byte ptr [rcx+29h], 2
0x14005ab7d  jb      loc_14005A97F
0x14005ab83  movzx   eax, word ptr [rdi+4]
0x14005ab87  mov     r9, r12
0x14005ab8a  mov     rcx, [rcx+18h]
0x14005ab8e  mov     [rsp+78h+OutputBufferLength], eax
0x14005ab92  mov     dword ptr [rsp+78h+OutputBuffer], esi
0x14005ab96  mov     qword ptr [rsp+78h+InputBufferLength], r15
0x14005ab9b  call    WPP_SF_qqDDDd
0x14005aba0  jmp     loc_14005A97F
0x14005aba5  mov     [rsp+78h+LengthReturned], 0; LengthReturned
0x14005abae  xor     r9d, r9d; InputBuffer
0x14005abb1  mov     [rsp+78h+OutputBufferLength], ebx; OutputBufferLength
0x14005abb5  mov     r8d, 900A8h; FsControlCode
0x14005abbb  mov     [rsp+78h+OutputBuffer], rax; OutputBuffer
0x14005abc0  mov     rdx, r15; FileObject
0x14005abc3  mov     rcx, r12; Instance
0x14005abc6  mov     [rsp+78h+InputBufferLength], 0; InputBufferLength
0x14005abce  mov     esi, ebx
0x14005abd0  call    cs:__imp_FltFsControlFile
0x14005abd7  nop     dword ptr [rax+rax+00h]
0x14005abdc  mov     ecx, eax
0x14005abde  mov     ebx, eax
0x14005abe0  call    HsmDbgBreakOnStatus
0x14005abe5  jmp     loc_14005A884
0x14005abea  mov     ebx, 0C000009Ah
0x14005abef  jmp     loc_14005A9BE
0x14005abf4  xor     ebp, ebp
0x14005abf6  jmp     loc_14005A9B4
```
