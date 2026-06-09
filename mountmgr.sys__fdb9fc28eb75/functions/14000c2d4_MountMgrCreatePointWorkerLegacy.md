# MountMgrCreatePointWorkerLegacy

- ea: `0x14000c2d4`
- end: `0x14000c51f`
- name: `MountMgrCreatePointWorkerLegacy`
- size: `587`
- prototype: `__int64 __fastcall(__int64, UNICODE_STRING *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config`

## callers

- `0x14000bcac`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140003280`
- `0x14000c2d4`
- `0x14000fdb8`
- `0x140018da0`
- `0x140019ca0`
- `0x14001a2b0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000c46d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000c46d`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000c49b`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000c49b`
- `ntoskrnl!ExAllocatePool2` at `0x14000c37b`
- `ntoskrnl!ExAllocatePool2` at `0x14000c37b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4f4`

## string_xrefs

- `0x14000c466`: `\Registry\Machine\System\MountedDevices`
- `0x14000c484`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrCreatePointWorkerLegacy(__int64 a1, UNICODE_STRING *a2, __int64 a3)
{
  int v5; // eax
  __int64 v6; // r8
  unsigned __int16 *v7; // rdi
  NTSTATUS v8; // ebx
  __int64 v9; // rdx
  WCHAR *Pool2; // rax
  WCHAR *v11; // rsi
  size_t Length; // rbx
  PDEVICE_OBJECT v13; // r8
  __int64 v14; // rdx
  UNICODE_STRING String2; // [rsp+38h] [rbp-49h] BYREF
  _QWORD v17[14]; // [rsp+48h] [rbp-39h] BYREF
  PVOID P; // [rsp+E8h] [rbp+67h] BYREF

  P = 0;
  String2 = 0;
  v5 = QueryUniqueId(a3, &P);
  v7 = (unsigned __int16 *)P;
  v8 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 115, v6, (unsigned int)v5);
    goto LABEL_22;
  }
  v9 = a2->Length + 2LL;
  String2 = *a2;
  Pool2 = (WCHAR *)ExAllocatePool2(258, v9, 1098149453);
  v11 = Pool2;
  if ( Pool2 )
  {
    Length = a2->Length;
    memmove(Pool2, a2->Buffer, Length);
    v11[Length >> 1] = 0;
    String2.MaximumLength += 2;
    String2.Buffer = v11;
    MountmgrSetDLStringCase(&String2);
    v8 = GlobalCreateSymbolicLink(&String2, a3);
    if ( v8 >= 0 )
    {
      if ( (unsigned __int8)IsDriveLetter(&String2) )
      {
        memset(&v17[1], 0, 0x68u);
        v17[0] = DeleteDriveLetterRoutine;
        RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices", v17, v7, 0);
      }
      v8 = RtlWriteRegistryValue(0, L"\\Registry\\Machine\\System\\MountedDevices", v11, 3u, v7 + 1, *v7);
      if ( v8 >= 0 )
        goto LABEL_21;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_21;
      v14 = 118;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_21;
      v14 = 117;
    }
    WPP_SF_L(v13->AttachedDevice, v14, v13, (unsigned int)v8);
LABEL_21:
    ExFreePoolWithTag(v11, 0);
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 116);
  v8 = -1073741670;
LABEL_22:
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000c2d4  mov     rax, rsp
0x14000c2d7  mov     [rax+10h], rbx
0x14000c2db  mov     [rax+18h], rsi
0x14000c2df  mov     [rax+8], rcx
0x14000c2e3  push    rbp
0x14000c2e4  push    rdi
0x14000c2e5  push    r12
0x14000c2e7  push    r14
0x14000c2e9  push    r15
0x14000c2eb  lea     rbp, [rax-5Fh]
0x14000c2ef  sub     rsp, 0B0h
0x14000c2f6  mov     r14, rdx
0x14000c2f9  mov     [rbp+57h+P], 0
0x14000c301  xorps   xmm0, xmm0
0x14000c304  lea     rdx, [rbp+57h+P]
0x14000c308  mov     rcx, r8
0x14000c30b  mov     r15, r8
0x14000c30e  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x14000c312  call    QueryUniqueId
0x14000c317  mov     rdi, [rbp+57h+P]
0x14000c31b  mov     ebx, eax
0x14000c31d  test    eax, eax
0x14000c31f  jns     short loc_14000C35A
0x14000c321  mov     rax, cs:WPP_GLOBAL_Control
0x14000c328  lea     rcx, WPP_GLOBAL_Control
0x14000c32f  cmp     rax, rcx
0x14000c332  jz      loc_14000C4EA
0x14000c338  mov     ecx, [rax+2Ch]
0x14000c33b  test    cl, 1
0x14000c33e  jz      loc_14000C4EA
0x14000c344  mov     rcx, [rax+18h]
0x14000c348  mov     edx, 73h ; 's'
0x14000c34d  mov     r9d, ebx
0x14000c350  call    WPP_SF_L
0x14000c355  jmp     loc_14000C4EA
0x14000c35a  movups  xmm0, xmmword ptr [r14]
0x14000c35e  movzx   edx, word ptr [r14]
0x14000c362  mov     r12d, 2
0x14000c368  add     rdx, r12
0x14000c36b  mov     ecx, 102h
0x14000c370  mov     r8d, 41746E4Dh
0x14000c376  movdqu  xmmword ptr [rbp+57h+String2.Length], xmm0
0x14000c37b  call    cs:__imp_ExAllocatePool2
0x14000c382  nop     dword ptr [rax+rax+00h]
0x14000c387  mov     rsi, rax
0x14000c38a  test    rax, rax
0x14000c38d  jnz     short loc_14000C3C0
0x14000c38f  mov     r8, cs:WPP_GLOBAL_Control
0x14000c396  lea     rcx, WPP_GLOBAL_Control
0x14000c39d  cmp     r8, rcx
0x14000c3a0  jz      short loc_14000C3B6
0x14000c3a2  mov     eax, [r8+2Ch]
0x14000c3a6  test    al, 4
0x14000c3a8  jz      short loc_14000C3B6
0x14000c3aa  mov     rcx, [r8+18h]
0x14000c3ae  lea     edx, [rsi+74h]
0x14000c3b1  call    WPP_SF_
0x14000c3b6  mov     ebx, 0C000009Ah
0x14000c3bb  jmp     loc_14000C4EA
0x14000c3c0  movzx   ebx, word ptr [r14]
0x14000c3c4  mov     rcx, rsi; void *
0x14000c3c7  mov     rdx, [r14+8]; Src
0x14000c3cb  mov     r8d, ebx; Size
0x14000c3ce  call    memmove
0x14000c3d3  xor     eax, eax
0x14000c3d5  shr     rbx, 1
0x14000c3d8  lea     rcx, [rbp+57h+String2]
0x14000c3dc  mov     [rsi+rbx*2], ax
0x14000c3e0  add     [rbp+57h+String2.MaximumLength], r12w
0x14000c3e5  mov     [rbp+57h+String2.Buffer], rsi
0x14000c3e9  call    MountmgrSetDLStringCase
0x14000c3ee  mov     rdx, r15
0x14000c3f1  lea     rcx, [rbp+57h+String2]
0x14000c3f5  call    GlobalCreateSymbolicLink
0x14000c3fa  mov     ebx, eax
0x14000c3fc  test    eax, eax
0x14000c3fe  jns     short loc_14000C42D
0x14000c400  mov     r8, cs:WPP_GLOBAL_Control
0x14000c407  lea     rcx, WPP_GLOBAL_Control
0x14000c40e  cmp     r8, rcx
0x14000c411  jz      loc_14000C4D9
0x14000c417  mov     eax, [r8+2Ch]
0x14000c41b  test    al, 1
0x14000c41d  jz      loc_14000C4D9
0x14000c423  mov     edx, 75h ; 'u'
0x14000c428  jmp     loc_14000C4CD
0x14000c42d  lea     rcx, [rbp+57h+String2]; String2
0x14000c431  call    IsDriveLetter
0x14000c436  test    al, al
0x14000c438  jz      short loc_14000C479
0x14000c43a  xor     edx, edx; Val
0x14000c43c  lea     rcx, [rbp+57h+var_88]; void *
0x14000c440  lea     r8d, [rdx+68h]; Size
0x14000c444  call    memset
0x14000c449  lea     rax, DeleteDriveLetterRoutine
0x14000c450  mov     [rsp+0D0h+ValueData], 0
0x14000c459  mov     r9, rdi
0x14000c45c  mov     [rbp+57h+var_90], rax
0x14000c460  lea     r8, [rbp+57h+var_90]
0x14000c464  xor     ecx, ecx
0x14000c466  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000c46d  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000c474  nop     dword ptr [rax+rax+00h]
0x14000c479  movzx   eax, word ptr [rdi]
0x14000c47c  lea     rcx, [rdi+2]
0x14000c480  mov     [rsp+0D0h+ValueLength], eax; ValueLength
0x14000c484  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x14000c48b  mov     [rsp+0D0h+ValueData], rcx; ValueData
0x14000c490  mov     r9d, 3; ValueType
0x14000c496  xor     ecx, ecx; RelativeTo
0x14000c498  mov     r8, rsi; ValueName
0x14000c49b  call    cs:__imp_RtlWriteRegistryValue
0x14000c4a2  nop     dword ptr [rax+rax+00h]
0x14000c4a7  mov     ebx, eax
0x14000c4a9  test    eax, eax
0x14000c4ab  jns     short loc_14000C4D9
0x14000c4ad  mov     r8, cs:WPP_GLOBAL_Control
0x14000c4b4  lea     rcx, WPP_GLOBAL_Control
0x14000c4bb  cmp     r8, rcx
0x14000c4be  jz      short loc_14000C4D9
0x14000c4c0  mov     eax, [r8+2Ch]
0x14000c4c4  test    al, 1
0x14000c4c6  jz      short loc_14000C4D9
0x14000c4c8  mov     edx, 76h ; 'v'
0x14000c4cd  mov     rcx, [r8+18h]
0x14000c4d1  mov     r9d, ebx
0x14000c4d4  call    WPP_SF_L
0x14000c4d9  xor     edx, edx; Tag
0x14000c4db  mov     rcx, rsi; P
0x14000c4de  call    cs:__imp_ExFreePoolWithTag
0x14000c4e5  nop     dword ptr [rax+rax+00h]
0x14000c4ea  test    rdi, rdi
0x14000c4ed  jz      short loc_14000C500
0x14000c4ef  xor     edx, edx; Tag
0x14000c4f1  mov     rcx, rdi; P
0x14000c4f4  call    cs:__imp_ExFreePoolWithTag
0x14000c4fb  nop     dword ptr [rax+rax+00h]
0x14000c500  lea     r11, [rsp+0D0h+var_20]
0x14000c508  mov     eax, ebx
0x14000c50a  mov     rbx, [r11+38h]
0x14000c50e  mov     rsi, [r11+40h]
0x14000c512  mov     rsp, r11
0x14000c515  pop     r15
0x14000c517  pop     r14
0x14000c519  pop     r12
0x14000c51b  pop     rdi
0x14000c51c  pop     rbp
0x14000c51d  retn
```
