# HsmpOpenFileById

- ea: `0x14005eee0`
- end: `0x14005f072`
- name: `HsmpOpenFileById`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002aec`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e2d0`
- `0x14005eee0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005ef63`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005ef63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005efe6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005efe6`
- `ntoskrnl!ExAllocatePool2` at `0x14005ef26`
- `ntoskrnl!ExAllocatePool2` at `0x14005ef26`

## pseudocode

```c
__int64 __fastcall HsmpOpenFileById(
        __int64 a1,
        __int64 a2,
        ACCESS_MASK a3,
        __int64 a4,
        int a5,
        char a6,
        void **a7,
        PFILE_OBJECT *a8)
{
  struct _FLT_INSTANCE *v9; // r12
  __int64 v10; // rdx
  unsigned int v13; // edi
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // [rsp+20h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-48h] BYREF

  v9 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v10 = (unsigned __int16)(*(_WORD *)(a1 + 64) + 8);
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  DestinationString.MaximumLength = v10;
  DestinationString.Length = 0;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v10, 1934979912);
  v13 = DestinationString.Buffer == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(v13);
  if ( DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1 + 64));
    *(_QWORD *)((char *)DestinationString.Buffer + DestinationString.Length) = a2;
    DestinationString.Length += 8;
    v13 = HsmiOpenFile(a1, v9, &DestinationString, a3, v17, a5 | 0x2000u, a6, a7, a8);
    HsmDbgBreakOnStatus(v13);
    if ( (v13 & 0x80000000) != 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v16 = 28;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v16 = 27;
LABEL_14:
      WPP_SF_qqd(v15->AttachedDevice, v16, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a2, v13);
    }
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
  return v13;
}

```

## disassembly

```asm
0x14005eee0  push    rbx
0x14005eee2  push    rbp
0x14005eee3  push    rsi
0x14005eee4  push    rdi
0x14005eee5  push    r12
0x14005eee7  push    r14
0x14005eee9  push    r15
0x14005eeeb  sub     rsp, 60h
0x14005eeef  movzx   eax, word ptr [rcx+40h]
0x14005eef3  mov     rbp, rdx
0x14005eef6  mov     r12, [rcx+20h]
0x14005eefa  add     ax, 8
0x14005eefe  movzx   edx, ax
0x14005ef01  xorps   xmm0, xmm0
0x14005ef04  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x14005ef09  xor     eax, eax
0x14005ef0b  mov     [rsp+98h+DestinationString.MaximumLength], dx
0x14005ef10  mov     r15d, r8d
0x14005ef13  mov     [rsp+98h+DestinationString.Length], ax
0x14005ef18  mov     rsi, rcx
0x14005ef1b  mov     r8d, 73557348h
0x14005ef21  mov     ecx, 100h
0x14005ef26  call    cs:__imp_ExAllocatePool2
0x14005ef2d  nop     dword ptr [rax+rax+00h]
0x14005ef32  mov     rcx, rax
0x14005ef35  mov     [rsp+98h+DestinationString.Buffer], rax
0x14005ef3a  neg     rcx
0x14005ef3d  mov     rbx, rax
0x14005ef40  sbb     edi, edi
0x14005ef42  not     edi
0x14005ef44  and     edi, 0C000009Ah
0x14005ef4a  mov     ecx, edi
0x14005ef4c  call    HsmDbgBreakOnStatus
0x14005ef51  test    rbx, rbx
0x14005ef54  jz      loc_14005F004
0x14005ef5a  lea     rdx, [rsi+40h]; SourceString
0x14005ef5e  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14005ef63  call    cs:__imp_RtlCopyUnicodeString
0x14005ef6a  nop     dword ptr [rax+rax+00h]
0x14005ef6f  movzx   ecx, [rsp+98h+DestinationString.Length]
0x14005ef74  lea     r8, [rsp+98h+DestinationString]
0x14005ef79  mov     rax, [rsp+98h+DestinationString.Buffer]
0x14005ef7e  mov     r9d, r15d
0x14005ef81  mov     rdx, r12
0x14005ef84  mov     [rcx+rax], rbp
0x14005ef88  mov     rax, [rsp+98h+arg_38]
0x14005ef90  mov     ecx, [rsp+98h+arg_20]
0x14005ef97  add     [rsp+98h+DestinationString.Length], 8
0x14005ef9d  bts     ecx, 0Dh
0x14005efa1  mov     [rsp+98h+var_58], rax
0x14005efa6  mov     rax, [rsp+98h+arg_30]
0x14005efae  mov     [rsp+98h+var_60], rax
0x14005efb3  mov     al, [rsp+98h+arg_28]
0x14005efba  mov     [rsp+98h+var_68], al
0x14005efbe  mov     [rsp+98h+var_70], ecx
0x14005efc2  mov     rcx, rsi
0x14005efc5  call    HsmiOpenFile
0x14005efca  mov     ecx, eax
0x14005efcc  mov     edi, eax
0x14005efce  call    HsmDbgBreakOnStatus
0x14005efd3  test    edi, edi
0x14005efd5  js      short loc_14005F02B
0x14005efd7  mov     rcx, [rsp+98h+DestinationString.Buffer]; P
0x14005efdc  test    rcx, rcx
0x14005efdf  jz      short loc_14005EFF2
0x14005efe1  mov     edx, 73557348h; Tag
0x14005efe6  call    cs:__imp_ExFreePoolWithTag
0x14005efed  nop     dword ptr [rax+rax+00h]
0x14005eff2  mov     eax, edi
0x14005eff4  add     rsp, 60h
0x14005eff8  pop     r15
0x14005effa  pop     r14
0x14005effc  pop     r12
0x14005effe  pop     rdi
0x14005efff  pop     rsi
0x14005f000  pop     rbp
0x14005f001  pop     rbx
0x14005f002  retn
0x14005f004  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f00b  lea     rax, WPP_GLOBAL_Control
0x14005f012  cmp     rcx, rax
0x14005f015  jz      short loc_14005EFD7
0x14005f017  mov     eax, [rcx+2Ch]
0x14005f01a  test    al, 8
0x14005f01c  jz      short loc_14005EFD7
0x14005f01e  cmp     byte ptr [rcx+29h], 2
0x14005f022  jb      short loc_14005EFD7
0x14005f024  mov     edx, 1Bh
0x14005f029  jmp     short loc_14005F051
0x14005f02b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f032  lea     rax, WPP_GLOBAL_Control
0x14005f039  cmp     rcx, rax
0x14005f03c  jz      short loc_14005EFD7
0x14005f03e  mov     edx, [rcx+2Ch]
0x14005f041  test    dl, 8
0x14005f044  jz      short loc_14005EFD7
0x14005f046  cmp     byte ptr [rcx+29h], 2
0x14005f04a  jb      short loc_14005EFD7
0x14005f04c  mov     edx, 1Ch
0x14005f051  mov     rcx, [rcx+18h]
0x14005f055  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005f05c  mov     [rsp+98h+var_70], edi
0x14005f060  mov     r9, rsi
0x14005f063  mov     [rsp+98h+var_78], rbp
0x14005f068  call    WPP_SF_qqd
0x14005f06d  jmp     loc_14005EFD7
```
