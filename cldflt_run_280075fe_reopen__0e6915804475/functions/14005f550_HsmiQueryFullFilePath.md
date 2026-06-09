# HsmiQueryFullFilePath

- ea: `0x14005f550`
- end: `0x14005f743`
- name: `HsmiQueryFullFilePath`
- size: `499`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x14003baf0`
- `0x1400450e0`
- `0x14004f5f0`
- `0x140050d70`
- `0x140051b5c`
- `0x140051c80`
- `0x1400520d0`
- `0x140052454`
- `0x1400536e0`
- `0x140054a9c`
- `0x14005c8c0`
- `0x14005f204`
- `0x140075fc0`
- `0x14007edd4`
- `0x140083c64`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14001e280`
- `0x14005f550`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005f732`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f732`
- `ntoskrnl!ExAllocatePool2` at `0x14005f5d5`
- `ntoskrnl!ExAllocatePool2` at `0x14005f5d5`
- `FLTMGR!FltGetFileNameInformation` at `0x14005f68b`
- `FLTMGR!FltGetFileNameInformation` at `0x14005f68b`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14005f58d`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14005f58d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f661`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f661`

## pseudocode

```c
__int64 __fastcall HsmiQueryFullFilePath(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        FLT_FILE_NAME_OPTIONS a4,
        _OWORD *a5)
{
  unsigned int FileNameInformationUnsafe; // eax
  int v8; // ebx
  void *v9; // rdi
  __int64 Length; // rdx
  size_t v11; // rbx
  __int128 v13; // [rsp+30h] [rbp-38h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+78h] [rbp+10h] BYREF

  FileNameInformation = 0;
  DWORD1(v13) = 0;
  if ( a3 )
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(a3, 0, a4, &FileNameInformation);
  else
    FileNameInformationUnsafe = FltGetFileNameInformation(0, a4, &FileNameInformation);
  v8 = FileNameInformationUnsafe;
  HsmDbgBreakOnStatus(FileNameInformationUnsafe);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a3);
    }
    v9 = 0;
  }
  else
  {
    WORD1(v13) = FileNameInformation->Name.Length - FileNameInformation->Volume.Length + 2;
    *((_QWORD *)&v13 + 1) = ExAllocatePool2(256, WORD1(v13), 1934979912);
    v9 = (void *)*((_QWORD *)&v13 + 1);
    if ( *((_QWORD *)&v13 + 1) )
    {
      HsmDbgBreakOnStatus(0);
      Length = FileNameInformation->Volume.Length;
      v11 = (unsigned __int16)(FileNameInformation->Name.Length - Length);
      LOWORD(v13) = FileNameInformation->Name.Length - Length;
      memmove(*((void **)&v13 + 1), (char *)FileNameInformation->Name.Buffer + Length, v11);
      *(_WORD *)(*((_QWORD *)&v13 + 1) + 2 * (v11 >> 1)) = 0;
      v9 = 0;
      v8 = 0;
      *a5 = v13;
    }
    else
    {
      v8 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a3);
      }
    }
  }
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x73557348u);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14005f550  mov     [rsp+FileNameInformation], rdx
0x14005f555  push    rbx
0x14005f556  push    rbp
0x14005f557  push    rsi
0x14005f558  push    rdi
0x14005f559  sub     rsp, 48h
0x14005f55d  mov     [rsp+68h+FileNameInformation], 0
0x14005f566  xorps   xmm0, xmm0
0x14005f569  mov     eax, r9d
0x14005f56c  mov     rsi, r8
0x14005f56f  mov     rbp, rcx
0x14005f572  movups  [rsp+68h+var_38], xmm0
0x14005f577  test    r8, r8
0x14005f57a  jz      loc_14005F682
0x14005f580  lea     r9, [rsp+68h+FileNameInformation]; FileNameInformation
0x14005f585  mov     r8d, eax; NameOptions
0x14005f588  xor     edx, edx; Instance
0x14005f58a  mov     rcx, rsi; FileObject
0x14005f58d  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14005f594  nop     dword ptr [rax+rax+00h]
0x14005f599  mov     ecx, eax
0x14005f59b  mov     ebx, eax
0x14005f59d  call    HsmDbgBreakOnStatus
0x14005f5a2  test    ebx, ebx
0x14005f5a4  js      loc_14005F63F
0x14005f5aa  mov     rax, [rsp+68h+FileNameInformation]
0x14005f5af  mov     ecx, 100h
0x14005f5b4  mov     r8d, 73557348h
0x14005f5ba  movzx   edx, word ptr [rax+8]
0x14005f5be  sub     dx, [rax+18h]
0x14005f5c2  xor     eax, eax
0x14005f5c4  add     dx, 2
0x14005f5c8  mov     word ptr [rsp+68h+var_38], ax
0x14005f5cd  movzx   edx, dx
0x14005f5d0  mov     word ptr [rsp+68h+var_38+2], dx
0x14005f5d5  call    cs:__imp_ExAllocatePool2
0x14005f5dc  nop     dword ptr [rax+rax+00h]
0x14005f5e1  mov     qword ptr [rsp+68h+var_38+8], rax
0x14005f5e6  mov     rdi, rax
0x14005f5e9  test    rax, rax
0x14005f5ec  jz      loc_14005F6CC
0x14005f5f2  xor     ecx, ecx
0x14005f5f4  call    HsmDbgBreakOnStatus
0x14005f5f9  mov     rcx, [rsp+68h+FileNameInformation]
0x14005f5fe  movzx   edx, word ptr [rcx+18h]
0x14005f602  movzx   eax, word ptr [rcx+8]
0x14005f606  sub     ax, dx
0x14005f609  add     rdx, [rcx+10h]; Src
0x14005f60d  movzx   ebx, ax
0x14005f610  mov     rcx, rdi; void *
0x14005f613  mov     r8d, ebx; Size
0x14005f616  mov     word ptr [rsp+68h+var_38], bx
0x14005f61b  call    memmove
0x14005f620  movups  xmm0, [rsp+68h+var_38]
0x14005f625  xor     eax, eax
0x14005f627  shr     rbx, 1
0x14005f62a  mov     [rdi+rbx*2], ax
0x14005f62e  xor     edi, edi
0x14005f630  mov     rax, [rsp+68h+arg_20]
0x14005f638  xor     ebx, ebx
0x14005f63a  movups  xmmword ptr [rax], xmm0
0x14005f63d  jmp     short loc_14005F657
0x14005f63f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f646  lea     rax, WPP_GLOBAL_Control
0x14005f64d  cmp     rcx, rax
0x14005f650  jnz     short loc_14005F69C
0x14005f652  mov     rdi, qword ptr [rsp+68h+var_38+8]
0x14005f657  mov     rcx, [rsp+68h+FileNameInformation]; FileNameInformation
0x14005f65c  test    rcx, rcx
0x14005f65f  jz      short loc_14005F66D
0x14005f661  call    cs:__imp_FltReleaseFileNameInformation
0x14005f668  nop     dword ptr [rax+rax+00h]
0x14005f66d  test    rdi, rdi
0x14005f670  jnz     loc_14005F72A
0x14005f676  mov     eax, ebx
0x14005f678  add     rsp, 48h
0x14005f67c  pop     rdi
0x14005f67d  pop     rsi
0x14005f67e  pop     rbp
0x14005f67f  pop     rbx
0x14005f680  retn
0x14005f682  lea     r8, [rsp+68h+FileNameInformation]; FileNameInformation
0x14005f687  mov     edx, eax; NameOptions
0x14005f689  xor     ecx, ecx; CallbackData
0x14005f68b  call    cs:__imp_FltGetFileNameInformation
0x14005f692  nop     dword ptr [rax+rax+00h]
0x14005f697  jmp     loc_14005F599
0x14005f69c  mov     eax, [rcx+2Ch]
0x14005f69f  test    al, 8
0x14005f6a1  jz      short loc_14005F652
0x14005f6a3  cmp     byte ptr [rcx+29h], 2
0x14005f6a7  jb      short loc_14005F652
0x14005f6a9  mov     rcx, [rcx+18h]
0x14005f6ad  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005f6b4  mov     edx, 0Dh
0x14005f6b9  mov     [rsp+68h+var_40], ebx
0x14005f6bd  mov     r9, rbp
0x14005f6c0  mov     [rsp+68h+var_48], rsi
0x14005f6c5  call    WPP_SF_qqd
0x14005f6ca  jmp     short loc_14005F652
0x14005f6cc  mov     ebx, 0C000009Ah
0x14005f6d1  mov     ecx, ebx
0x14005f6d3  call    HsmDbgBreakOnStatus
0x14005f6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f6df  lea     rax, WPP_GLOBAL_Control
0x14005f6e6  cmp     rcx, rax
0x14005f6e9  jz      loc_14005F657
0x14005f6ef  mov     eax, [rcx+2Ch]
0x14005f6f2  test    al, 8
0x14005f6f4  jz      loc_14005F657
0x14005f6fa  cmp     byte ptr [rcx+29h], 2
0x14005f6fe  jb      loc_14005F657
0x14005f704  mov     rcx, [rcx+18h]
0x14005f708  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005f70f  mov     edx, 0Eh
0x14005f714  mov     [rsp+68h+var_40], ebx
0x14005f718  mov     r9, rbp
0x14005f71b  mov     [rsp+68h+var_48], rsi
0x14005f720  call    WPP_SF_qqd
0x14005f725  jmp     loc_14005F657
0x14005f72a  mov     edx, 73557348h; Tag
0x14005f72f  mov     rcx, rdi; P
0x14005f732  call    cs:__imp_ExFreePoolWithTag
0x14005f739  nop     dword ptr [rax+rax+00h]
0x14005f73e  jmp     loc_14005F676
```
