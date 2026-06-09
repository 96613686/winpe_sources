# HsmpOpenFileByIdEx

- ea: `0x14005e76c`
- end: `0x14005e8fd`
- name: `HsmpOpenFileByIdEx`
- size: `401`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: ``

## callers

- `0x140033f48`
- `0x1400431dc`
- `0x140043324`
- `0x14004357c`
- `0x140043c9c`
- `0x140043ff4`
- `0x14004ba24`
- `0x140054bbc`
- `0x14005f324`
- `0x14005fde4`
- `0x140065b68`
- `0x14006f558`
- `0x14007807c`
- `0x14007ee6c`
- `0x14007f5dc`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e3f0`
- `0x14005e76c`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005e7ee`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005e7ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e871`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e871`
- `ntoskrnl!ExAllocatePool2` at `0x14005e7b1`
- `ntoskrnl!ExAllocatePool2` at `0x14005e7b1`

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
  int v14; // edi
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
    if ( v14 < 0 )
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
      WPP_SF_qqd(v16->AttachedDevice, v17, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a3, v14);
    }
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14005e76c  push    rbx
0x14005e76e  push    rbp
0x14005e76f  push    rsi
0x14005e770  push    rdi
0x14005e771  push    r12
0x14005e773  push    r14
0x14005e775  push    r15
0x14005e777  sub     rsp, 60h
0x14005e77b  movzx   eax, word ptr [rcx+40h]
0x14005e77f  mov     r12, rdx
0x14005e782  add     ax, 8
0x14005e786  xorps   xmm0, xmm0
0x14005e789  movzx   edx, ax
0x14005e78c  mov     rbp, r8
0x14005e78f  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x14005e794  xor     eax, eax
0x14005e796  mov     [rsp+98h+DestinationString.MaximumLength], dx
0x14005e79b  mov     rsi, rcx
0x14005e79e  mov     [rsp+98h+DestinationString.Length], ax
0x14005e7a3  mov     ecx, 100h
0x14005e7a8  mov     r8d, 73557348h
0x14005e7ae  mov     r15d, r9d
0x14005e7b1  call    cs:__imp_ExAllocatePool2
0x14005e7b8  nop     dword ptr [rax+rax+00h]
0x14005e7bd  mov     rcx, rax
0x14005e7c0  mov     [rsp+98h+DestinationString.Buffer], rax
0x14005e7c5  neg     rcx
0x14005e7c8  mov     rbx, rax
0x14005e7cb  sbb     edi, edi
0x14005e7cd  not     edi
0x14005e7cf  and     edi, 0C000009Ah
0x14005e7d5  mov     ecx, edi
0x14005e7d7  call    HsmDbgBreakOnStatus
0x14005e7dc  test    rbx, rbx
0x14005e7df  jz      loc_14005E88F
0x14005e7e5  lea     rdx, [rsi+40h]; SourceString
0x14005e7e9  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14005e7ee  call    cs:__imp_RtlCopyUnicodeString
0x14005e7f5  nop     dword ptr [rax+rax+00h]
0x14005e7fa  movzx   ecx, [rsp+98h+DestinationString.Length]
0x14005e7ff  lea     r8, [rsp+98h+DestinationString]
0x14005e804  mov     rax, [rsp+98h+DestinationString.Buffer]
0x14005e809  mov     r9d, r15d
0x14005e80c  mov     rdx, r12
0x14005e80f  mov     [rcx+rax], rbp
0x14005e813  mov     rax, [rsp+98h+arg_40]
0x14005e81b  mov     ecx, [rsp+98h+arg_28]
0x14005e822  add     [rsp+98h+DestinationString.Length], 8
0x14005e828  bts     ecx, 0Dh
0x14005e82c  mov     [rsp+98h+var_58], rax
0x14005e831  mov     rax, [rsp+98h+arg_38]
0x14005e839  mov     [rsp+98h+var_60], rax
0x14005e83e  mov     al, [rsp+98h+arg_30]
0x14005e845  mov     [rsp+98h+var_68], al
0x14005e849  mov     [rsp+98h+var_70], ecx
0x14005e84d  mov     rcx, rsi
0x14005e850  call    HsmiOpenFile
0x14005e855  mov     ecx, eax
0x14005e857  mov     edi, eax
0x14005e859  call    HsmDbgBreakOnStatus
0x14005e85e  test    edi, edi
0x14005e860  js      short loc_14005E8B6
0x14005e862  mov     rcx, [rsp+98h+DestinationString.Buffer]; P
0x14005e867  test    rcx, rcx
0x14005e86a  jz      short loc_14005E87D
0x14005e86c  mov     edx, 73557348h; Tag
0x14005e871  call    cs:__imp_ExFreePoolWithTag
0x14005e878  nop     dword ptr [rax+rax+00h]
0x14005e87d  mov     eax, edi
0x14005e87f  add     rsp, 60h
0x14005e883  pop     r15
0x14005e885  pop     r14
0x14005e887  pop     r12
0x14005e889  pop     rdi
0x14005e88a  pop     rsi
0x14005e88b  pop     rbp
0x14005e88c  pop     rbx
0x14005e88d  retn
0x14005e88f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e896  lea     rax, WPP_GLOBAL_Control
0x14005e89d  cmp     rcx, rax
0x14005e8a0  jz      short loc_14005E862
0x14005e8a2  mov     eax, [rcx+2Ch]
0x14005e8a5  test    al, 8
0x14005e8a7  jz      short loc_14005E862
0x14005e8a9  cmp     byte ptr [rcx+29h], 2
0x14005e8ad  jb      short loc_14005E862
0x14005e8af  mov     edx, 1Bh
0x14005e8b4  jmp     short loc_14005E8DC
0x14005e8b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e8bd  lea     rax, WPP_GLOBAL_Control
0x14005e8c4  cmp     rcx, rax
0x14005e8c7  jz      short loc_14005E862
0x14005e8c9  mov     edx, [rcx+2Ch]
0x14005e8cc  test    dl, 8
0x14005e8cf  jz      short loc_14005E862
0x14005e8d1  cmp     byte ptr [rcx+29h], 2
0x14005e8d5  jb      short loc_14005E862
0x14005e8d7  mov     edx, 1Ch
0x14005e8dc  mov     rcx, [rcx+18h]
0x14005e8e0  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005e8e7  mov     [rsp+98h+var_70], edi
0x14005e8eb  mov     r9, rsi
0x14005e8ee  mov     [rsp+98h+var_78], rbp
0x14005e8f3  call    WPP_SF_qqd
0x14005e8f8  jmp     loc_14005E862
```
