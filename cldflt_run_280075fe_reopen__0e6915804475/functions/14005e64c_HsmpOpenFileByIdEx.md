# HsmpOpenFileByIdEx

- ea: `0x14005e64c`
- end: `0x14005e7dd`
- name: `HsmpOpenFileByIdEx`
- size: `401`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x140033f48`
- `0x1400430ec`
- `0x140043234`
- `0x14004348c`
- `0x140043bac`
- `0x140043f04`
- `0x14004b934`
- `0x140054a9c`
- `0x14005f204`
- `0x14005fcc4`
- `0x140065a48`
- `0x14006f438`
- `0x140077f3c`
- `0x14007ecd4`
- `0x14007f444`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e2d0`
- `0x14005e64c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005e6ce`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005e6ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e751`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e751`
- `ntoskrnl!ExAllocatePool2` at `0x14005e691`
- `ntoskrnl!ExAllocatePool2` at `0x14005e691`

## pseudocode

```c
__int64 __fastcall HsmpOpenFileByIdEx(
        const UNICODE_STRING *a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        ACCESS_MASK a4,
        __int64 a5,
        int a6,
        char a7,
        void **a8,
        PFILE_OBJECT *a9)
{
  __int64 v10; // rdx
  unsigned int v14; // edi
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // [rsp+20h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-48h] BYREF

  v10 = (unsigned __int16)(a1[4].Length + 8);
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  DestinationString.MaximumLength = v10;
  DestinationString.Length = 0;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v10, 1934979912);
  v14 = DestinationString.Buffer == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(v14);
  if ( DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&DestinationString, a1 + 4);
    *(_QWORD *)((char *)DestinationString.Buffer + DestinationString.Length) = a3;
    DestinationString.Length += 8;
    v14 = HsmiOpenFile((__int64)a1, a2, &DestinationString, a4, v18, a6 | 0x2000u, a7, a8, a9);
    HsmDbgBreakOnStatus(v14);
    if ( (v14 & 0x80000000) != 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v17 = 28;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v17 = 27;
LABEL_14:
      WPP_SF_qqd(v16->AttachedDevice, v17, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a3);
    }
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
  return v14;
}

```

## disassembly

```asm
0x14005e64c  push    rbx
0x14005e64e  push    rbp
0x14005e64f  push    rsi
0x14005e650  push    rdi
0x14005e651  push    r12
0x14005e653  push    r14
0x14005e655  push    r15
0x14005e657  sub     rsp, 60h
0x14005e65b  movzx   eax, word ptr [rcx+40h]
0x14005e65f  mov     r12, rdx
0x14005e662  add     ax, 8
0x14005e666  xorps   xmm0, xmm0
0x14005e669  movzx   edx, ax
0x14005e66c  mov     rbp, r8
0x14005e66f  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x14005e674  xor     eax, eax
0x14005e676  mov     [rsp+98h+DestinationString.MaximumLength], dx
0x14005e67b  mov     rsi, rcx
0x14005e67e  mov     [rsp+98h+DestinationString.Length], ax
0x14005e683  mov     ecx, 100h
0x14005e688  mov     r8d, 73557348h
0x14005e68e  mov     r15d, r9d
0x14005e691  call    cs:__imp_ExAllocatePool2
0x14005e698  nop     dword ptr [rax+rax+00h]
0x14005e69d  mov     rcx, rax
0x14005e6a0  mov     [rsp+98h+DestinationString.Buffer], rax
0x14005e6a5  neg     rcx
0x14005e6a8  mov     rbx, rax
0x14005e6ab  sbb     edi, edi
0x14005e6ad  not     edi
0x14005e6af  and     edi, 0C000009Ah
0x14005e6b5  mov     ecx, edi
0x14005e6b7  call    HsmDbgBreakOnStatus
0x14005e6bc  test    rbx, rbx
0x14005e6bf  jz      loc_14005E76F
0x14005e6c5  lea     rdx, [rsi+40h]; SourceString
0x14005e6c9  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14005e6ce  call    cs:__imp_RtlCopyUnicodeString
0x14005e6d5  nop     dword ptr [rax+rax+00h]
0x14005e6da  movzx   ecx, [rsp+98h+DestinationString.Length]
0x14005e6df  lea     r8, [rsp+98h+DestinationString]
0x14005e6e4  mov     rax, [rsp+98h+DestinationString.Buffer]
0x14005e6e9  mov     r9d, r15d
0x14005e6ec  mov     rdx, r12
0x14005e6ef  mov     [rcx+rax], rbp
0x14005e6f3  mov     rax, [rsp+98h+arg_40]
0x14005e6fb  mov     ecx, [rsp+98h+arg_28]
0x14005e702  add     [rsp+98h+DestinationString.Length], 8
0x14005e708  bts     ecx, 0Dh
0x14005e70c  mov     [rsp+98h+var_58], rax
0x14005e711  mov     rax, [rsp+98h+arg_38]
0x14005e719  mov     [rsp+98h+var_60], rax
0x14005e71e  mov     al, [rsp+98h+arg_30]
0x14005e725  mov     [rsp+98h+var_68], al
0x14005e729  mov     [rsp+98h+var_70], ecx
0x14005e72d  mov     rcx, rsi
0x14005e730  call    HsmiOpenFile
0x14005e735  mov     ecx, eax
0x14005e737  mov     edi, eax
0x14005e739  call    HsmDbgBreakOnStatus
0x14005e73e  test    edi, edi
0x14005e740  js      short loc_14005E796
0x14005e742  mov     rcx, [rsp+98h+DestinationString.Buffer]; P
0x14005e747  test    rcx, rcx
0x14005e74a  jz      short loc_14005E75D
0x14005e74c  mov     edx, 73557348h; Tag
0x14005e751  call    cs:__imp_ExFreePoolWithTag
0x14005e758  nop     dword ptr [rax+rax+00h]
0x14005e75d  mov     eax, edi
0x14005e75f  add     rsp, 60h
0x14005e763  pop     r15
0x14005e765  pop     r14
0x14005e767  pop     r12
0x14005e769  pop     rdi
0x14005e76a  pop     rsi
0x14005e76b  pop     rbp
0x14005e76c  pop     rbx
0x14005e76d  retn
0x14005e76f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e776  lea     rax, WPP_GLOBAL_Control
0x14005e77d  cmp     rcx, rax
0x14005e780  jz      short loc_14005E742
0x14005e782  mov     eax, [rcx+2Ch]
0x14005e785  test    al, 8
0x14005e787  jz      short loc_14005E742
0x14005e789  cmp     byte ptr [rcx+29h], 2
0x14005e78d  jb      short loc_14005E742
0x14005e78f  mov     edx, 1Bh
0x14005e794  jmp     short loc_14005E7BC
0x14005e796  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e79d  lea     rax, WPP_GLOBAL_Control
0x14005e7a4  cmp     rcx, rax
0x14005e7a7  jz      short loc_14005E742
0x14005e7a9  mov     edx, [rcx+2Ch]
0x14005e7ac  test    dl, 8
0x14005e7af  jz      short loc_14005E742
0x14005e7b1  cmp     byte ptr [rcx+29h], 2
0x14005e7b5  jb      short loc_14005E742
0x14005e7b7  mov     edx, 1Ch
0x14005e7bc  mov     rcx, [rcx+18h]
0x14005e7c0  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005e7c7  mov     [rsp+98h+var_70], edi
0x14005e7cb  mov     r9, rsi
0x14005e7ce  mov     [rsp+98h+var_78], rbp
0x14005e7d3  call    WPP_SF_qqd
0x14005e7d8  jmp     loc_14005E742
```
