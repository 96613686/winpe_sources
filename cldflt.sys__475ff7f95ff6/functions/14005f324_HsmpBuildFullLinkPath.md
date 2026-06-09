# HsmpBuildFullLinkPath

- ea: `0x14005f324`
- end: `0x14005f662`
- name: `HsmpBuildFullLinkPath`
- size: `830`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140059090`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e76c`
- `0x14005f324`
- `0x14005f670`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005f5b1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14005f5b1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005f462`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005f48c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005f462`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14005f48c`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f4d0`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f4d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f4ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f651`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f4ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f651`
- `ntoskrnl!ExAllocatePool2` at `0x14005f427`
- `ntoskrnl!ExAllocatePool2` at `0x14005f427`
- `FLTMGR!FltClose` at `0x14005f4e5`
- `FLTMGR!FltClose` at `0x14005f4e5`

## pseudocode

```c
__int64 __fastcall HsmpBuildFullLinkPath(__int64 a1, __int64 a2, const UNICODE_STRING *a3, UNICODE_STRING *a4)
{
  struct _FLT_INSTANCE *v8; // rdx
  int v10; // edi
  __int64 v11; // rdx
  unsigned __int16 v12; // ax
  unsigned __int16 v13; // cx
  PWSTR Buffer; // rbx
  UNICODE_STRING v15; // xmm0
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // [rsp+20h] [rbp-60h]
  HANDLE FileHandle; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-18h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+30h] BYREF

  FileHandle = 0;
  Object = 0;
  v8 = *(struct _FLT_INSTANCE **)(a1 + 32);
  Source = 0;
  Destination = 0;
  v10 = HsmpOpenFileByIdEx(
          (const UNICODE_STRING *)a1,
          v8,
          a2,
          0x100080u,
          v19,
          2097153,
          0,
          &FileHandle,
          (PFILE_OBJECT *)&Object);
  HsmDbgBreakOnStatus(v10);
  if ( v10 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_13;
    }
    v18 = 19;
LABEL_30:
    WPP_SF_qqd(v17->AttachedDevice, v18, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a2, v10);
    goto LABEL_13;
  }
  v10 = HsmiQueryFullFilePath(*(_QWORD *)(a1 + 32), v11, (struct _FILE_OBJECT *)Object, 0x101u, &Source);
  HsmDbgBreakOnStatus(v10);
  if ( v10 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_13;
    }
    v18 = 20;
    goto LABEL_30;
  }
  if ( !a3 )
  {
    v15 = Source;
    Source.Buffer = 0;
LABEL_12:
    *a4 = v15;
    goto LABEL_13;
  }
  v12 = Source.Length + 2;
  if ( (unsigned __int16)(Source.Length + 2) < Source.Length
    || (v13 = a3->Length + v12, v13 < v12)
    || (unsigned __int16)(v13 + 2) < v13 )
  {
    Destination.MaximumLength = -1;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_13;
    }
    v18 = 21;
    goto LABEL_30;
  }
  Destination.MaximumLength = v13 + 2;
  Destination.Length = 0;
  Destination.Buffer = (PWSTR)ExAllocatePool2(256, (unsigned __int16)(v13 + 2), 1934979912);
  Buffer = Destination.Buffer;
  v10 = Destination.Buffer == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(v10);
  if ( Buffer )
  {
    RtlAppendUnicodeStringToString(&Destination, &Source);
    if ( Destination.Buffer[((unsigned __int64)Destination.Length >> 1) - 1] != 92 )
      RtlAppendUnicodeToString(&Destination, L"\\");
    RtlAppendUnicodeStringToString(&Destination, a3);
    Destination.Buffer[(unsigned __int64)Destination.Length >> 1] = 0;
    v15 = Destination;
    Destination.Buffer = 0;
    goto LABEL_12;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v18 = 22;
    goto LABEL_30;
  }
LABEL_13:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Source.Buffer )
    ExFreePoolWithTag(Source.Buffer, 0x73557348u);
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0x73557348u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14005f324  mov     r11, rsp
0x14005f327  mov     [r11+10h], rbx
0x14005f32b  mov     [r11+18h], rsi
0x14005f32f  push    rbp
0x14005f330  push    rdi
0x14005f331  push    r13
0x14005f333  push    r14
0x14005f335  push    r15
0x14005f337  mov     rbp, rsp
0x14005f33a  sub     rsp, 80h
0x14005f341  lea     rax, [rbp+Object]
0x14005f345  mov     [rbp+FileHandle], 0
0x14005f34d  mov     [r11-68h], rax
0x14005f351  mov     r15, r8
0x14005f354  lea     rax, [rbp+FileHandle]
0x14005f358  mov     [rbp+Object], 0
0x14005f360  mov     [r11-70h], rax
0x14005f364  mov     r13, r9
0x14005f367  mov     r14, rdx
0x14005f36a  mov     [rsp+80h+var_50], 0
0x14005f36f  xorps   xmm0, xmm0
0x14005f372  mov     [rsp+80h+var_58], 200001h
0x14005f37a  xorps   xmm1, xmm1
0x14005f37d  mov     r8, rdx
0x14005f380  mov     rdx, [rcx+20h]
0x14005f384  mov     r9d, 100080h
0x14005f38a  mov     rsi, rcx
0x14005f38d  movups  xmmword ptr [rbp+Source.Length], xmm0
0x14005f391  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x14005f395  call    HsmpOpenFileByIdEx
0x14005f39a  mov     ecx, eax
0x14005f39c  mov     edi, eax
0x14005f39e  call    HsmDbgBreakOnStatus
0x14005f3a3  test    edi, edi
0x14005f3a5  js      loc_14005F573
0x14005f3ab  mov     r8, [rbp+Object]
0x14005f3af  lea     rax, [rbp+Source]
0x14005f3b3  mov     rcx, [rsi+20h]
0x14005f3b7  mov     r9d, 101h
0x14005f3bd  mov     [rsp+80h+var_60], rax
0x14005f3c2  call    HsmiQueryFullFilePath
0x14005f3c7  mov     ecx, eax
0x14005f3c9  mov     edi, eax
0x14005f3cb  call    HsmDbgBreakOnStatus
0x14005f3d0  test    edi, edi
0x14005f3d2  js      loc_14005F5E8
0x14005f3d8  test    r15, r15
0x14005f3db  jz      loc_14005F4B3
0x14005f3e1  movzx   eax, [rbp+Source.Length]
0x14005f3e5  add     ax, 2
0x14005f3e9  cmp     ax, [rbp+Source.Length]
0x14005f3ed  jb      loc_14005F537
0x14005f3f3  movzx   ecx, ax
0x14005f3f6  add     cx, [r15]
0x14005f3fa  cmp     cx, ax
0x14005f3fd  jb      loc_14005F537
0x14005f403  lea     edx, [rcx+2]
0x14005f406  cmp     dx, cx
0x14005f409  jb      loc_14005F537
0x14005f40f  mov     [rbp+Destination.MaximumLength], dx
0x14005f413  xor     eax, eax
0x14005f415  movzx   edx, dx
0x14005f418  mov     ecx, 100h
0x14005f41d  mov     r8d, 73557348h
0x14005f423  mov     [rbp+Destination.Length], ax
0x14005f427  call    cs:__imp_ExAllocatePool2
0x14005f42e  nop     dword ptr [rax+rax+00h]
0x14005f433  mov     rcx, rax
0x14005f436  mov     [rbp+Destination.Buffer], rax
0x14005f43a  neg     rcx
0x14005f43d  mov     rbx, rax
0x14005f440  sbb     edi, edi
0x14005f442  not     edi
0x14005f444  and     edi, 0C000009Ah
0x14005f44a  mov     ecx, edi
0x14005f44c  call    HsmDbgBreakOnStatus
0x14005f451  test    rbx, rbx
0x14005f454  jz      loc_14005F61B
0x14005f45a  lea     rdx, [rbp+Source]; Source
0x14005f45e  lea     rcx, [rbp+Destination]; Destination
0x14005f462  call    cs:__imp_RtlAppendUnicodeStringToString
0x14005f469  nop     dword ptr [rax+rax+00h]
0x14005f46e  movzx   ecx, [rbp+Destination.Length]
0x14005f472  mov     rax, [rbp+Destination.Buffer]
0x14005f476  shr     rcx, 1
0x14005f479  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14005f47f  jnz     loc_14005F5A6
0x14005f485  mov     rdx, r15; Source
0x14005f488  lea     rcx, [rbp+Destination]; Destination
0x14005f48c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14005f493  nop     dword ptr [rax+rax+00h]
0x14005f498  movzx   edx, [rbp+Destination.Length]
0x14005f49c  mov     rax, [rbp+Destination.Buffer]
0x14005f4a0  shr     rdx, 1
0x14005f4a3  xor     ecx, ecx
0x14005f4a5  mov     [rax+rdx*2], cx
0x14005f4a9  movups  xmm0, xmmword ptr [rbp+Destination.Length]
0x14005f4ad  mov     [rbp+Destination.Buffer], rcx
0x14005f4b1  jmp     short loc_14005F4BF
0x14005f4b3  movups  xmm0, xmmword ptr [rbp+Source.Length]
0x14005f4b7  mov     [rbp+Source.Buffer], 0
0x14005f4bf  movdqu  xmmword ptr [r13+0], xmm0
0x14005f4c5  cmp     [rbp+Object], 0
0x14005f4ca  jz      short loc_14005F4DC
0x14005f4cc  mov     rcx, [rbp+Object]; Object
0x14005f4d0  call    cs:__imp_ObfDereferenceObject
0x14005f4d7  nop     dword ptr [rax+rax+00h]
0x14005f4dc  mov     rcx, [rbp+FileHandle]; FileHandle
0x14005f4e0  test    rcx, rcx
0x14005f4e3  jz      short loc_14005F4F1
0x14005f4e5  call    cs:__imp_FltClose
0x14005f4ec  nop     dword ptr [rax+rax+00h]
0x14005f4f1  mov     rcx, [rbp+Source.Buffer]; P
0x14005f4f5  test    rcx, rcx
0x14005f4f8  jz      short loc_14005F50B
0x14005f4fa  mov     edx, 73557348h; Tag
0x14005f4ff  call    cs:__imp_ExFreePoolWithTag
0x14005f506  nop     dword ptr [rax+rax+00h]
0x14005f50b  mov     rcx, [rbp+Destination.Buffer]; P
0x14005f50f  test    rcx, rcx
0x14005f512  jnz     loc_14005F64C
0x14005f518  lea     r11, [rsp+80h+var_s0]
0x14005f520  mov     eax, edi
0x14005f522  mov     rbx, [r11+38h]
0x14005f526  mov     rsi, [r11+40h]
0x14005f52a  mov     rsp, r11
0x14005f52d  pop     r15
0x14005f52f  pop     r14
0x14005f531  pop     r13
0x14005f533  pop     rdi
0x14005f534  pop     rbp
0x14005f535  retn
0x14005f537  mov     eax, 0FFFFh
0x14005f53c  mov     [rbp+Destination.MaximumLength], ax
0x14005f540  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f547  lea     rax, WPP_GLOBAL_Control
0x14005f54e  cmp     rcx, rax
0x14005f551  jz      loc_14005F4C5
0x14005f557  mov     eax, [rcx+2Ch]
0x14005f55a  test    al, 8
0x14005f55c  jz      loc_14005F4C5
0x14005f562  cmp     byte ptr [rcx+29h], 2
0x14005f566  jb      loc_14005F4C5
0x14005f56c  mov     edx, 15h
0x14005f571  jmp     short loc_14005F5C7
0x14005f573  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f57a  lea     rax, WPP_GLOBAL_Control
0x14005f581  cmp     rcx, rax
0x14005f584  jz      loc_14005F4C5
0x14005f58a  mov     eax, [rcx+2Ch]
0x14005f58d  test    al, 8
0x14005f58f  jz      loc_14005F4C5
0x14005f595  cmp     byte ptr [rcx+29h], 2
0x14005f599  jb      loc_14005F4C5
0x14005f59f  mov     edx, 13h
0x14005f5a4  jmp     short loc_14005F5C7
0x14005f5a6  lea     rdx, asc_1400206E8; "\\"
0x14005f5ad  lea     rcx, [rbp+Destination]; Destination
0x14005f5b1  call    cs:__imp_RtlAppendUnicodeToString
0x14005f5b8  nop     dword ptr [rax+rax+00h]
0x14005f5bd  jmp     loc_14005F485
0x14005f5c2  mov     edx, 16h
0x14005f5c7  mov     rcx, [rcx+18h]
0x14005f5cb  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005f5d2  mov     [rsp+80h+var_58], edi
0x14005f5d6  mov     r9, rsi
0x14005f5d9  mov     [rsp+80h+var_60], r14
0x14005f5de  call    WPP_SF_qqd
0x14005f5e3  jmp     loc_14005F4C5
0x14005f5e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f5ef  lea     rax, WPP_GLOBAL_Control
0x14005f5f6  cmp     rcx, rax
0x14005f5f9  jz      loc_14005F4C5
0x14005f5ff  mov     eax, [rcx+2Ch]
0x14005f602  test    al, 8
0x14005f604  jz      loc_14005F4C5
0x14005f60a  cmp     byte ptr [rcx+29h], 2
0x14005f60e  jb      loc_14005F4C5
0x14005f614  mov     edx, 14h
0x14005f619  jmp     short loc_14005F5C7
0x14005f61b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f622  lea     rax, WPP_GLOBAL_Control
0x14005f629  cmp     rcx, rax
0x14005f62c  jz      loc_14005F4C5
0x14005f632  mov     eax, [rcx+2Ch]
0x14005f635  test    al, 8
0x14005f637  jz      loc_14005F4C5
0x14005f63d  cmp     byte ptr [rcx+29h], 2
0x14005f641  jb      loc_14005F4C5
0x14005f647  jmp     loc_14005F5C2
0x14005f64c  mov     edx, 73557348h; Tag
0x14005f651  call    cs:__imp_ExFreePoolWithTag
0x14005f658  nop     dword ptr [rax+rax+00h]
0x14005f65d  jmp     loc_14005F518
```
