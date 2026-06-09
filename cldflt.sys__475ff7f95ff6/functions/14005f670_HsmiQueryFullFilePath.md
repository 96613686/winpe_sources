# HsmiQueryFullFilePath

- ea: `0x14005f670`
- end: `0x14005f863`
- name: `HsmiQueryFullFilePath`
- size: `499`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FILE_OBJECT *, FLT_FILE_NAME_OPTIONS, _OWORD *)`
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x14003bb10`
- `0x1400451d0`
- `0x14004f710`
- `0x140050e90`
- `0x140051c7c`
- `0x140051da0`
- `0x1400521f0`
- `0x140052574`
- `0x140053800`
- `0x140054bbc`
- `0x14005c9e0`
- `0x14005f324`
- `0x1400760e0`
- `0x14007ef6c`
- `0x140083e24`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14001e300`
- `0x14005f670`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005f852`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f852`
- `ntoskrnl!ExAllocatePool2` at `0x14005f6f5`
- `ntoskrnl!ExAllocatePool2` at `0x14005f6f5`
- `FLTMGR!FltGetFileNameInformation` at `0x14005f7ab`
- `FLTMGR!FltGetFileNameInformation` at `0x14005f7ab`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14005f6ad`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14005f6ad`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f781`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005f781`

## pseudocode

```c
__int64 __fastcall HsmiQueryFullFilePath(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        FLT_FILE_NAME_OPTIONS a4,
        _OWORD *a5)
{
  NTSTATUS FileNameInformationUnsafe; // eax
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
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a3, v8);
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
      HsmDbgBreakOnStatus(-1073741670);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
          a1,
          a3,
          -1073741670);
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
0x14005f670  mov     [rsp+FileNameInformation], rdx
0x14005f675  push    rbx
0x14005f676  push    rbp
0x14005f677  push    rsi
0x14005f678  push    rdi
0x14005f679  sub     rsp, 48h
0x14005f67d  mov     [rsp+68h+FileNameInformation], 0
0x14005f686  xorps   xmm0, xmm0
0x14005f689  mov     eax, r9d
0x14005f68c  mov     rsi, r8
0x14005f68f  mov     rbp, rcx
0x14005f692  movups  [rsp+68h+var_38], xmm0
0x14005f697  test    r8, r8
0x14005f69a  jz      loc_14005F7A2
0x14005f6a0  lea     r9, [rsp+68h+FileNameInformation]; FileNameInformation
0x14005f6a5  mov     r8d, eax; NameOptions
0x14005f6a8  xor     edx, edx; Instance
0x14005f6aa  mov     rcx, rsi; FileObject
0x14005f6ad  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14005f6b4  nop     dword ptr [rax+rax+00h]
0x14005f6b9  mov     ecx, eax
0x14005f6bb  mov     ebx, eax
0x14005f6bd  call    HsmDbgBreakOnStatus
0x14005f6c2  test    ebx, ebx
0x14005f6c4  js      loc_14005F75F
0x14005f6ca  mov     rax, [rsp+68h+FileNameInformation]
0x14005f6cf  mov     ecx, 100h
0x14005f6d4  mov     r8d, 73557348h
0x14005f6da  movzx   edx, word ptr [rax+8]
0x14005f6de  sub     dx, [rax+18h]
0x14005f6e2  xor     eax, eax
0x14005f6e4  add     dx, 2
0x14005f6e8  mov     word ptr [rsp+68h+var_38], ax
0x14005f6ed  movzx   edx, dx
0x14005f6f0  mov     word ptr [rsp+68h+var_38+2], dx
0x14005f6f5  call    cs:__imp_ExAllocatePool2
0x14005f6fc  nop     dword ptr [rax+rax+00h]
0x14005f701  mov     qword ptr [rsp+68h+var_38+8], rax
0x14005f706  mov     rdi, rax
0x14005f709  test    rax, rax
0x14005f70c  jz      loc_14005F7EC
0x14005f712  xor     ecx, ecx
0x14005f714  call    HsmDbgBreakOnStatus
0x14005f719  mov     rcx, [rsp+68h+FileNameInformation]
0x14005f71e  movzx   edx, word ptr [rcx+18h]
0x14005f722  movzx   eax, word ptr [rcx+8]
0x14005f726  sub     ax, dx
0x14005f729  add     rdx, [rcx+10h]; Src
0x14005f72d  movzx   ebx, ax
0x14005f730  mov     rcx, rdi; void *
0x14005f733  mov     r8d, ebx; Size
0x14005f736  mov     word ptr [rsp+68h+var_38], bx
0x14005f73b  call    memmove
0x14005f740  movups  xmm0, [rsp+68h+var_38]
0x14005f745  xor     eax, eax
0x14005f747  shr     rbx, 1
0x14005f74a  mov     [rdi+rbx*2], ax
0x14005f74e  xor     edi, edi
0x14005f750  mov     rax, [rsp+68h+arg_20]
0x14005f758  xor     ebx, ebx
0x14005f75a  movups  xmmword ptr [rax], xmm0
0x14005f75d  jmp     short loc_14005F777
0x14005f75f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f766  lea     rax, WPP_GLOBAL_Control
0x14005f76d  cmp     rcx, rax
0x14005f770  jnz     short loc_14005F7BC
0x14005f772  mov     rdi, qword ptr [rsp+68h+var_38+8]
0x14005f777  mov     rcx, [rsp+68h+FileNameInformation]; FileNameInformation
0x14005f77c  test    rcx, rcx
0x14005f77f  jz      short loc_14005F78D
0x14005f781  call    cs:__imp_FltReleaseFileNameInformation
0x14005f788  nop     dword ptr [rax+rax+00h]
0x14005f78d  test    rdi, rdi
0x14005f790  jnz     loc_14005F84A
0x14005f796  mov     eax, ebx
0x14005f798  add     rsp, 48h
0x14005f79c  pop     rdi
0x14005f79d  pop     rsi
0x14005f79e  pop     rbp
0x14005f79f  pop     rbx
0x14005f7a0  retn
0x14005f7a2  lea     r8, [rsp+68h+FileNameInformation]; FileNameInformation
0x14005f7a7  mov     edx, eax; NameOptions
0x14005f7a9  xor     ecx, ecx; CallbackData
0x14005f7ab  call    cs:__imp_FltGetFileNameInformation
0x14005f7b2  nop     dword ptr [rax+rax+00h]
0x14005f7b7  jmp     loc_14005F6B9
0x14005f7bc  mov     eax, [rcx+2Ch]
0x14005f7bf  test    al, 8
0x14005f7c1  jz      short loc_14005F772
0x14005f7c3  cmp     byte ptr [rcx+29h], 2
0x14005f7c7  jb      short loc_14005F772
0x14005f7c9  mov     rcx, [rcx+18h]
0x14005f7cd  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005f7d4  mov     edx, 0Dh
0x14005f7d9  mov     [rsp+68h+var_40], ebx
0x14005f7dd  mov     r9, rbp
0x14005f7e0  mov     [rsp+68h+var_48], rsi
0x14005f7e5  call    WPP_SF_qqd
0x14005f7ea  jmp     short loc_14005F772
0x14005f7ec  mov     ebx, 0C000009Ah
0x14005f7f1  mov     ecx, ebx
0x14005f7f3  call    HsmDbgBreakOnStatus
0x14005f7f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f7ff  lea     rax, WPP_GLOBAL_Control
0x14005f806  cmp     rcx, rax
0x14005f809  jz      loc_14005F777
0x14005f80f  mov     eax, [rcx+2Ch]
0x14005f812  test    al, 8
0x14005f814  jz      loc_14005F777
0x14005f81a  cmp     byte ptr [rcx+29h], 2
0x14005f81e  jb      loc_14005F777
0x14005f824  mov     rcx, [rcx+18h]
0x14005f828  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005f82f  mov     edx, 0Eh
0x14005f834  mov     [rsp+68h+var_40], ebx
0x14005f838  mov     r9, rbp
0x14005f83b  mov     [rsp+68h+var_48], rsi
0x14005f840  call    WPP_SF_qqd
0x14005f845  jmp     loc_14005F777
0x14005f84a  mov     edx, 73557348h; Tag
0x14005f84f  mov     rcx, rdi; P
0x14005f852  call    cs:__imp_ExFreePoolWithTag
0x14005f859  nop     dword ptr [rax+rax+00h]
0x14005f85e  jmp     loc_14005F796
```
