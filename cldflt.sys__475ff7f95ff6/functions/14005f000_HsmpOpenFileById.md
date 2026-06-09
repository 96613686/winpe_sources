# HsmpOpenFileById

- ea: `0x14005f000`
- end: `0x14005f192`
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
- `0x14005e3f0`
- `0x14005f000`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005f083`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005f083`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f106`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f106`
- `ntoskrnl!ExAllocatePool2` at `0x14005f046`
- `ntoskrnl!ExAllocatePool2` at `0x14005f046`

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
  int v13; // edi
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
    if ( v13 < 0 )
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
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14005f000  push    rbx
0x14005f002  push    rbp
0x14005f003  push    rsi
0x14005f004  push    rdi
0x14005f005  push    r12
0x14005f007  push    r14
0x14005f009  push    r15
0x14005f00b  sub     rsp, 60h
0x14005f00f  movzx   eax, word ptr [rcx+40h]
0x14005f013  mov     rbp, rdx
0x14005f016  mov     r12, [rcx+20h]
0x14005f01a  add     ax, 8
0x14005f01e  movzx   edx, ax
0x14005f021  xorps   xmm0, xmm0
0x14005f024  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x14005f029  xor     eax, eax
0x14005f02b  mov     [rsp+98h+DestinationString.MaximumLength], dx
0x14005f030  mov     r15d, r8d
0x14005f033  mov     [rsp+98h+DestinationString.Length], ax
0x14005f038  mov     rsi, rcx
0x14005f03b  mov     r8d, 73557348h
0x14005f041  mov     ecx, 100h
0x14005f046  call    cs:__imp_ExAllocatePool2
0x14005f04d  nop     dword ptr [rax+rax+00h]
0x14005f052  mov     rcx, rax
0x14005f055  mov     [rsp+98h+DestinationString.Buffer], rax
0x14005f05a  neg     rcx
0x14005f05d  mov     rbx, rax
0x14005f060  sbb     edi, edi
0x14005f062  not     edi
0x14005f064  and     edi, 0C000009Ah
0x14005f06a  mov     ecx, edi
0x14005f06c  call    HsmDbgBreakOnStatus
0x14005f071  test    rbx, rbx
0x14005f074  jz      loc_14005F124
0x14005f07a  lea     rdx, [rsi+40h]; SourceString
0x14005f07e  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14005f083  call    cs:__imp_RtlCopyUnicodeString
0x14005f08a  nop     dword ptr [rax+rax+00h]
0x14005f08f  movzx   ecx, [rsp+98h+DestinationString.Length]
0x14005f094  lea     r8, [rsp+98h+DestinationString]
0x14005f099  mov     rax, [rsp+98h+DestinationString.Buffer]
0x14005f09e  mov     r9d, r15d
0x14005f0a1  mov     rdx, r12
0x14005f0a4  mov     [rcx+rax], rbp
0x14005f0a8  mov     rax, [rsp+98h+arg_38]
0x14005f0b0  mov     ecx, [rsp+98h+arg_20]
0x14005f0b7  add     [rsp+98h+DestinationString.Length], 8
0x14005f0bd  bts     ecx, 0Dh
0x14005f0c1  mov     [rsp+98h+var_58], rax
0x14005f0c6  mov     rax, [rsp+98h+arg_30]
0x14005f0ce  mov     [rsp+98h+var_60], rax
0x14005f0d3  mov     al, [rsp+98h+arg_28]
0x14005f0da  mov     [rsp+98h+var_68], al
0x14005f0de  mov     [rsp+98h+var_70], ecx
0x14005f0e2  mov     rcx, rsi
0x14005f0e5  call    HsmiOpenFile
0x14005f0ea  mov     ecx, eax
0x14005f0ec  mov     edi, eax
0x14005f0ee  call    HsmDbgBreakOnStatus
0x14005f0f3  test    edi, edi
0x14005f0f5  js      short loc_14005F14B
0x14005f0f7  mov     rcx, [rsp+98h+DestinationString.Buffer]; P
0x14005f0fc  test    rcx, rcx
0x14005f0ff  jz      short loc_14005F112
0x14005f101  mov     edx, 73557348h; Tag
0x14005f106  call    cs:__imp_ExFreePoolWithTag
0x14005f10d  nop     dword ptr [rax+rax+00h]
0x14005f112  mov     eax, edi
0x14005f114  add     rsp, 60h
0x14005f118  pop     r15
0x14005f11a  pop     r14
0x14005f11c  pop     r12
0x14005f11e  pop     rdi
0x14005f11f  pop     rsi
0x14005f120  pop     rbp
0x14005f121  pop     rbx
0x14005f122  retn
0x14005f124  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f12b  lea     rax, WPP_GLOBAL_Control
0x14005f132  cmp     rcx, rax
0x14005f135  jz      short loc_14005F0F7
0x14005f137  mov     eax, [rcx+2Ch]
0x14005f13a  test    al, 8
0x14005f13c  jz      short loc_14005F0F7
0x14005f13e  cmp     byte ptr [rcx+29h], 2
0x14005f142  jb      short loc_14005F0F7
0x14005f144  mov     edx, 1Bh
0x14005f149  jmp     short loc_14005F171
0x14005f14b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f152  lea     rax, WPP_GLOBAL_Control
0x14005f159  cmp     rcx, rax
0x14005f15c  jz      short loc_14005F0F7
0x14005f15e  mov     edx, [rcx+2Ch]
0x14005f161  test    dl, 8
0x14005f164  jz      short loc_14005F0F7
0x14005f166  cmp     byte ptr [rcx+29h], 2
0x14005f16a  jb      short loc_14005F0F7
0x14005f16c  mov     edx, 1Ch
0x14005f171  mov     rcx, [rcx+18h]
0x14005f175  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005f17c  mov     [rsp+98h+var_70], edi
0x14005f180  mov     r9, rsi
0x14005f183  mov     [rsp+98h+var_78], rbp
0x14005f188  call    WPP_SF_qqd
0x14005f18d  jmp     loc_14005F0F7
```
