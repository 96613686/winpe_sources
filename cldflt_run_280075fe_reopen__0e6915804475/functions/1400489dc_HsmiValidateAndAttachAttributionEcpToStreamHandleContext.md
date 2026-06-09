# HsmiValidateAndAttachAttributionEcpToStreamHandleContext

- ea: `0x1400489dc`
- end: `0x140048ce1`
- name: `HsmiValidateAndAttachAttributionEcpToStreamHandleContext`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140047994`

## callees

- `0x140003c50`
- `0x14001880c`
- `0x14001d8b0`
- `0x14001e280`
- `0x1400489dc`
- `0x140048ce8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140048aec`
- `ntoskrnl!ProbeForRead` at `0x140048aec`
- `ntoskrnl!IoFreeMdl` at `0x140048c08`
- `ntoskrnl!IoFreeMdl` at `0x140048cc2`
- `ntoskrnl!IoFreeMdl` at `0x140048c08`
- `ntoskrnl!IoFreeMdl` at `0x140048cc2`
- `ntoskrnl!IoAllocateMdl` at `0x140048a78`
- `ntoskrnl!IoAllocateMdl` at `0x140048a78`
- `ntoskrnl!MmProbeAndLockPages` at `0x140048b00`
- `ntoskrnl!MmProbeAndLockPages` at `0x140048b00`
- `ntoskrnl!MmUnlockPages` at `0x140048cae`
- `ntoskrnl!MmUnlockPages` at `0x140048cae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c9a`
- `ntoskrnl!ExAllocatePool2` at `0x140048b22`
- `ntoskrnl!ExAllocatePool2` at `0x140048b22`

## pseudocode

```c
__int64 __fastcall HsmiValidateAndAttachAttributionEcpToStreamHandleContext(__int64 a1, void *a2, __int64 a3)
{
  SIZE_T v3; // rbx
  unsigned int *v6; // rdi
  char v7; // r13
  struct _MDL *Mdl; // r14
  int v9; // esi
  __int64 v10; // r8
  unsigned int *Pool2; // rax
  __int64 v12; // r8

  v3 = (unsigned int)a3;
  v6 = 0;
  v7 = 0;
  if ( (unsigned int)a3 >= 0x50 )
  {
    Mdl = IoAllocateMdl(a2, a3, 0, 0, 0);
    if ( Mdl )
    {
      ProbeForRead(a2, v3, 4u);
      MmProbeAndLockPages(Mdl, 1, IoReadAccess);
      v7 = 1;
      Pool2 = (unsigned int *)ExAllocatePool2(258, v3, 1765897032);
      v6 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, a2, v3);
        v9 = HsmpValidateAttributionEcp(v6, (unsigned int)v3);
        HsmDbgBreakOnStatus((unsigned int)v9);
        if ( v9 >= 0 )
        {
          *(_QWORD *)(a1 + 80) = v6;
          v6 = 0;
          *(_DWORD *)(a1 + 88) = v3;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_DDd(
            WPP_GLOBAL_Control->AttachedDevice,
            213,
            WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
            *v6,
            v3,
            v9);
        }
      }
      else
      {
        v9 = -1073741670;
        HsmDbgBreakOnStatus(3221225626LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 211, v12, a2, v3, -1073741670, 1, 0);
        }
      }
    }
    else
    {
      v9 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 210, v10, a2, v3, -1073741670, 0, 0);
      }
    }
  }
  else
  {
    Mdl = 0;
    v9 = -1073741789;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 209, a3, a2, a3, -1073741789, 0, 0);
    }
  }
  if ( v6 )
    ExFreePoolWithTag(v6, 0x69417348u);
  if ( v7 )
    MmUnlockPages(Mdl);
  if ( Mdl )
    IoFreeMdl(Mdl);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400489dc  mov     rax, rsp
0x1400489df  mov     [rax+18h], r8d
0x1400489e3  mov     [rax+10h], rdx
0x1400489e7  mov     [rax+8], rcx
0x1400489eb  push    rbx
0x1400489ec  push    rsi
0x1400489ed  push    rdi
0x1400489ee  push    r12
0x1400489f0  push    r13
0x1400489f2  push    r14
0x1400489f4  push    r15
0x1400489f6  sub     rsp, 40h
0x1400489fa  mov     ebx, r8d
0x1400489fd  mov     r12, rdx
0x140048a00  mov     r15, rcx
0x140048a03  xor     edi, edi
0x140048a05  mov     [rax-40h], rdi
0x140048a09  xor     r13b, r13b
0x140048a0c  mov     [rax-48h], r13b
0x140048a10  cmp     r8d, 50h ; 'P'
0x140048a14  jnb     short loc_140048A68
0x140048a16  xor     r14d, r14d
0x140048a19  mov     esi, 0C0000023h
0x140048a1e  lea     rax, WPP_GLOBAL_Control
0x140048a25  mov     rcx, cs:WPP_GLOBAL_Control
0x140048a2c  cmp     rcx, rax
0x140048a2f  jz      loc_140048C8D
0x140048a35  mov     eax, [rcx+2Ch]
0x140048a38  test    al, 1
0x140048a3a  jz      loc_140048C8D
0x140048a40  cmp     byte ptr [rcx+29h], 2
0x140048a44  jb      loc_140048C8D
0x140048a4a  mov     edx, 0D1h
0x140048a4f  mov     [rsp+78h+var_50], esi
0x140048a53  mov     dword ptr [rsp+78h+Irp], ebx
0x140048a57  mov     r9, r12
0x140048a5a  mov     rcx, [rcx+18h]
0x140048a5e  call    WPP_SF_qdd
0x140048a63  jmp     loc_140048C8D
0x140048a68  mov     [rsp+78h+Irp], rdi; Irp
0x140048a6d  xor     r9d, r9d; ChargeQuota
0x140048a70  xor     r8d, r8d; SecondaryBuffer
0x140048a73  mov     edx, ebx; Length
0x140048a75  mov     rcx, r12; VirtualAddress
0x140048a78  call    cs:__imp_IoAllocateMdl
0x140048a7f  nop     dword ptr [rax+rax+00h]
0x140048a84  mov     r14, rax
0x140048a87  mov     [rsp+78h+Mdl], rax
0x140048a8f  test    rax, rax
0x140048a92  jnz     short loc_140048AE0
0x140048a94  mov     r15d, 0C000009Ah
0x140048a9a  mov     esi, r15d
0x140048a9d  mov     ecx, r15d
0x140048aa0  call    HsmDbgBreakOnStatus
0x140048aa5  lea     rax, WPP_GLOBAL_Control
0x140048aac  mov     rcx, cs:WPP_GLOBAL_Control
0x140048ab3  cmp     rcx, rax
0x140048ab6  jz      loc_140048C8D
0x140048abc  mov     eax, [rcx+2Ch]
0x140048abf  test    al, 1
0x140048ac1  jz      loc_140048C8D
0x140048ac7  cmp     byte ptr [rcx+29h], 2
0x140048acb  jb      loc_140048C8D
0x140048ad1  mov     edx, 0D2h
0x140048ad6  mov     [rsp+78h+var_50], r15d
0x140048adb  jmp     loc_140048A53
0x140048ae0  mov     r8d, 4; Alignment
0x140048ae6  mov     rdx, rbx; Length
0x140048ae9  mov     rcx, r12; Address
0x140048aec  call    cs:__imp_ProbeForRead
0x140048af3  nop     dword ptr [rax+rax+00h]
0x140048af8  xor     r8d, r8d; Operation
0x140048afb  mov     dl, 1; AccessMode
0x140048afd  mov     rcx, r14; MemoryDescriptorList
0x140048b00  call    cs:__imp_MmProbeAndLockPages
0x140048b07  nop     dword ptr [rax+rax+00h]
0x140048b0c  mov     r13b, 1
0x140048b0f  mov     [rsp+78h+var_48], r13b
0x140048b14  mov     r8d, 69417348h
0x140048b1a  mov     rdx, rbx
0x140048b1d  mov     ecx, 102h
0x140048b22  call    cs:__imp_ExAllocatePool2
0x140048b29  nop     dword ptr [rax+rax+00h]
0x140048b2e  mov     rdi, rax
0x140048b31  mov     [rsp+78h+var_40], rax
0x140048b36  test    rax, rax
0x140048b39  jnz     short loc_140048B91
0x140048b3b  mov     r15d, 0C000009Ah
0x140048b41  mov     esi, r15d
0x140048b44  mov     [rsp+78h+var_44], r15d
0x140048b49  mov     ecx, r15d
0x140048b4c  call    HsmDbgBreakOnStatus
0x140048b51  lea     rax, WPP_GLOBAL_Control
0x140048b58  mov     rcx, cs:WPP_GLOBAL_Control
0x140048b5f  cmp     rcx, rax
0x140048b62  jz      short loc_140048B8C
0x140048b64  mov     eax, [rcx+2Ch]
0x140048b67  test    r13b, al
0x140048b6a  jz      short loc_140048B8C
0x140048b6c  cmp     byte ptr [rcx+29h], 2
0x140048b70  jb      short loc_140048B8C
0x140048b72  mov     edx, 0D3h
0x140048b77  mov     [rsp+78h+var_50], r15d
0x140048b7c  mov     dword ptr [rsp+78h+Irp], ebx
0x140048b80  mov     r9, r12
0x140048b83  mov     rcx, [rcx+18h]
0x140048b87  call    WPP_SF_qdd
0x140048b8c  jmp     loc_140048C8D
0x140048b91  mov     r8, rbx; Size
0x140048b94  mov     rdx, r12; Src
0x140048b97  mov     rcx, rax; void *
0x140048b9a  call    memmove
0x140048b9f  jmp     loc_140048C29
0x140048ba4  mov     ebx, eax
0x140048ba6  mov     [rsp+78h+var_44], eax
0x140048baa  mov     ecx, eax
0x140048bac  call    HsmDbgBreakOnStatus
0x140048bb1  lea     rax, WPP_GLOBAL_Control
0x140048bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140048bbf  cmp     rcx, rax
0x140048bc2  jz      short loc_140048BF9
0x140048bc4  mov     edx, [rcx+2Ch]
0x140048bc7  test    dl, 1
0x140048bca  jz      short loc_140048BF9
0x140048bcc  cmp     byte ptr [rcx+29h], 2
0x140048bd0  jb      short loc_140048BF9
0x140048bd2  mov     edx, 0D4h
0x140048bd7  mov     [rsp+78h+var_50], ebx
0x140048bdb  mov     ebx, [rsp+78h+arg_10]
0x140048be2  mov     dword ptr [rsp+78h+Irp], ebx
0x140048be6  mov     r9, [rsp+78h+arg_8]
0x140048bee  mov     rcx, [rcx+18h]
0x140048bf2  call    WPP_SF_qdd
0x140048bf7  jmp     short loc_140048C00
0x140048bf9  mov     ebx, [rsp+78h+arg_10]
0x140048c00  mov     rcx, [rsp+78h+Mdl]; Mdl
0x140048c08  call    cs:__imp_IoFreeMdl
0x140048c0f  nop     dword ptr [rax+rax+00h]
0x140048c14  xor     r14d, r14d
0x140048c17  mov     r15, [rsp+78h+arg_0]
0x140048c1f  mov     rdi, [rsp+78h+var_40]
0x140048c24  mov     r13b, [rsp+78h+var_48]
0x140048c29  mov     edx, ebx
0x140048c2b  mov     rcx, rdi
0x140048c2e  call    HsmpValidateAttributionEcp
0x140048c33  mov     esi, eax
0x140048c35  mov     ecx, eax
0x140048c37  call    HsmDbgBreakOnStatus
0x140048c3c  test    esi, esi
0x140048c3e  jns     short loc_140048C83
0x140048c40  lea     rax, WPP_GLOBAL_Control
0x140048c47  mov     rcx, cs:WPP_GLOBAL_Control
0x140048c4e  cmp     rcx, rax
0x140048c51  jz      short loc_140048C8D
0x140048c53  mov     edx, [rcx+2Ch]
0x140048c56  test    dl, 1
0x140048c59  jz      short loc_140048C8D
0x140048c5b  cmp     byte ptr [rcx+29h], 2
0x140048c5f  jb      short loc_140048C8D
0x140048c61  mov     edx, 0D5h
0x140048c66  mov     [rsp+78h+var_50], esi
0x140048c6a  mov     dword ptr [rsp+78h+Irp], ebx
0x140048c6e  mov     r9d, [rdi]
0x140048c71  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140048c78  mov     rcx, [rcx+18h]
0x140048c7c  call    WPP_SF_DDd
0x140048c81  jmp     short loc_140048C8D
0x140048c83  mov     [r15+50h], rdi
0x140048c87  xor     edi, edi
0x140048c89  mov     [r15+58h], ebx
0x140048c8d  test    rdi, rdi
0x140048c90  jz      short loc_140048CA6
0x140048c92  mov     edx, 69417348h; Tag
0x140048c97  mov     rcx, rdi; P
0x140048c9a  call    cs:__imp_ExFreePoolWithTag
0x140048ca1  nop     dword ptr [rax+rax+00h]
0x140048ca6  test    r13b, r13b
0x140048ca9  jz      short loc_140048CBA
0x140048cab  mov     rcx, r14; MemoryDescriptorList
0x140048cae  call    cs:__imp_MmUnlockPages
0x140048cb5  nop     dword ptr [rax+rax+00h]
0x140048cba  test    r14, r14
0x140048cbd  jz      short loc_140048CCE
0x140048cbf  mov     rcx, r14; Mdl
0x140048cc2  call    cs:__imp_IoFreeMdl
0x140048cc9  nop     dword ptr [rax+rax+00h]
0x140048cce  mov     eax, esi
0x140048cd0  add     rsp, 40h
0x140048cd4  pop     r15
0x140048cd6  pop     r14
0x140048cd8  pop     r13
0x140048cda  pop     r12
0x140048cdc  pop     rdi
0x140048cdd  pop     rsi
0x140048cde  pop     rbx
0x140048cdf  retn
```
