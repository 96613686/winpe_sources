# HsmiValidateAndAttachAttributionEcpToStreamHandleContext

- ea: `0x140048acc`
- end: `0x140048dd1`
- name: `HsmiValidateAndAttachAttributionEcpToStreamHandleContext`
- size: `773`
- prototype: `__int64 __fastcall(__int64, void *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140047a84`

## callees

- `0x140003c50`
- `0x14001888c`
- `0x14001d930`
- `0x14001e300`
- `0x140048acc`
- `0x140048dd8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140048bdc`
- `ntoskrnl!ProbeForRead` at `0x140048bdc`
- `ntoskrnl!IoFreeMdl` at `0x140048cf8`
- `ntoskrnl!IoFreeMdl` at `0x140048db2`
- `ntoskrnl!IoFreeMdl` at `0x140048cf8`
- `ntoskrnl!IoFreeMdl` at `0x140048db2`
- `ntoskrnl!IoAllocateMdl` at `0x140048b68`
- `ntoskrnl!IoAllocateMdl` at `0x140048b68`
- `ntoskrnl!MmProbeAndLockPages` at `0x140048bf0`
- `ntoskrnl!MmProbeAndLockPages` at `0x140048bf0`
- `ntoskrnl!MmUnlockPages` at `0x140048d9e`
- `ntoskrnl!MmUnlockPages` at `0x140048d9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d8a`
- `ntoskrnl!ExAllocatePool2` at `0x140048c12`
- `ntoskrnl!ExAllocatePool2` at `0x140048c12`

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
        HsmDbgBreakOnStatus(v9);
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
        HsmDbgBreakOnStatus(-1073741670);
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
      HsmDbgBreakOnStatus(-1073741670);
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
0x140048acc  mov     rax, rsp
0x140048acf  mov     [rax+18h], r8d
0x140048ad3  mov     [rax+10h], rdx
0x140048ad7  mov     [rax+8], rcx
0x140048adb  push    rbx
0x140048adc  push    rsi
0x140048add  push    rdi
0x140048ade  push    r12
0x140048ae0  push    r13
0x140048ae2  push    r14
0x140048ae4  push    r15
0x140048ae6  sub     rsp, 40h
0x140048aea  mov     ebx, r8d
0x140048aed  mov     r12, rdx
0x140048af0  mov     r15, rcx
0x140048af3  xor     edi, edi
0x140048af5  mov     [rax-40h], rdi
0x140048af9  xor     r13b, r13b
0x140048afc  mov     [rax-48h], r13b
0x140048b00  cmp     r8d, 50h ; 'P'
0x140048b04  jnb     short loc_140048B58
0x140048b06  xor     r14d, r14d
0x140048b09  mov     esi, 0C0000023h
0x140048b0e  lea     rax, WPP_GLOBAL_Control
0x140048b15  mov     rcx, cs:WPP_GLOBAL_Control
0x140048b1c  cmp     rcx, rax
0x140048b1f  jz      loc_140048D7D
0x140048b25  mov     eax, [rcx+2Ch]
0x140048b28  test    al, 1
0x140048b2a  jz      loc_140048D7D
0x140048b30  cmp     byte ptr [rcx+29h], 2
0x140048b34  jb      loc_140048D7D
0x140048b3a  mov     edx, 0D1h
0x140048b3f  mov     [rsp+78h+var_50], esi
0x140048b43  mov     dword ptr [rsp+78h+Irp], ebx
0x140048b47  mov     r9, r12
0x140048b4a  mov     rcx, [rcx+18h]
0x140048b4e  call    WPP_SF_qdd
0x140048b53  jmp     loc_140048D7D
0x140048b58  mov     [rsp+78h+Irp], rdi; Irp
0x140048b5d  xor     r9d, r9d; ChargeQuota
0x140048b60  xor     r8d, r8d; SecondaryBuffer
0x140048b63  mov     edx, ebx; Length
0x140048b65  mov     rcx, r12; VirtualAddress
0x140048b68  call    cs:__imp_IoAllocateMdl
0x140048b6f  nop     dword ptr [rax+rax+00h]
0x140048b74  mov     r14, rax
0x140048b77  mov     [rsp+78h+Mdl], rax
0x140048b7f  test    rax, rax
0x140048b82  jnz     short loc_140048BD0
0x140048b84  mov     r15d, 0C000009Ah
0x140048b8a  mov     esi, r15d
0x140048b8d  mov     ecx, r15d
0x140048b90  call    HsmDbgBreakOnStatus
0x140048b95  lea     rax, WPP_GLOBAL_Control
0x140048b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048ba3  cmp     rcx, rax
0x140048ba6  jz      loc_140048D7D
0x140048bac  mov     eax, [rcx+2Ch]
0x140048baf  test    al, 1
0x140048bb1  jz      loc_140048D7D
0x140048bb7  cmp     byte ptr [rcx+29h], 2
0x140048bbb  jb      loc_140048D7D
0x140048bc1  mov     edx, 0D2h
0x140048bc6  mov     [rsp+78h+var_50], r15d
0x140048bcb  jmp     loc_140048B43
0x140048bd0  mov     r8d, 4; Alignment
0x140048bd6  mov     rdx, rbx; Length
0x140048bd9  mov     rcx, r12; Address
0x140048bdc  call    cs:__imp_ProbeForRead
0x140048be3  nop     dword ptr [rax+rax+00h]
0x140048be8  xor     r8d, r8d; Operation
0x140048beb  mov     dl, 1; AccessMode
0x140048bed  mov     rcx, r14; MemoryDescriptorList
0x140048bf0  call    cs:__imp_MmProbeAndLockPages
0x140048bf7  nop     dword ptr [rax+rax+00h]
0x140048bfc  mov     r13b, 1
0x140048bff  mov     [rsp+78h+var_48], r13b
0x140048c04  mov     r8d, 69417348h
0x140048c0a  mov     rdx, rbx
0x140048c0d  mov     ecx, 102h
0x140048c12  call    cs:__imp_ExAllocatePool2
0x140048c19  nop     dword ptr [rax+rax+00h]
0x140048c1e  mov     rdi, rax
0x140048c21  mov     [rsp+78h+var_40], rax
0x140048c26  test    rax, rax
0x140048c29  jnz     short loc_140048C81
0x140048c2b  mov     r15d, 0C000009Ah
0x140048c31  mov     esi, r15d
0x140048c34  mov     [rsp+78h+var_44], r15d
0x140048c39  mov     ecx, r15d
0x140048c3c  call    HsmDbgBreakOnStatus
0x140048c41  lea     rax, WPP_GLOBAL_Control
0x140048c48  mov     rcx, cs:WPP_GLOBAL_Control
0x140048c4f  cmp     rcx, rax
0x140048c52  jz      short loc_140048C7C
0x140048c54  mov     eax, [rcx+2Ch]
0x140048c57  test    r13b, al
0x140048c5a  jz      short loc_140048C7C
0x140048c5c  cmp     byte ptr [rcx+29h], 2
0x140048c60  jb      short loc_140048C7C
0x140048c62  mov     edx, 0D3h
0x140048c67  mov     [rsp+78h+var_50], r15d
0x140048c6c  mov     dword ptr [rsp+78h+Irp], ebx
0x140048c70  mov     r9, r12
0x140048c73  mov     rcx, [rcx+18h]
0x140048c77  call    WPP_SF_qdd
0x140048c7c  jmp     loc_140048D7D
0x140048c81  mov     r8, rbx; Size
0x140048c84  mov     rdx, r12; Src
0x140048c87  mov     rcx, rax; void *
0x140048c8a  call    memmove
0x140048c8f  jmp     loc_140048D19
0x140048c94  mov     ebx, eax
0x140048c96  mov     [rsp+78h+var_44], eax
0x140048c9a  mov     ecx, eax
0x140048c9c  call    HsmDbgBreakOnStatus
0x140048ca1  lea     rax, WPP_GLOBAL_Control
0x140048ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x140048caf  cmp     rcx, rax
0x140048cb2  jz      short loc_140048CE9
0x140048cb4  mov     edx, [rcx+2Ch]
0x140048cb7  test    dl, 1
0x140048cba  jz      short loc_140048CE9
0x140048cbc  cmp     byte ptr [rcx+29h], 2
0x140048cc0  jb      short loc_140048CE9
0x140048cc2  mov     edx, 0D4h
0x140048cc7  mov     [rsp+78h+var_50], ebx
0x140048ccb  mov     ebx, [rsp+78h+arg_10]
0x140048cd2  mov     dword ptr [rsp+78h+Irp], ebx
0x140048cd6  mov     r9, [rsp+78h+arg_8]
0x140048cde  mov     rcx, [rcx+18h]
0x140048ce2  call    WPP_SF_qdd
0x140048ce7  jmp     short loc_140048CF0
0x140048ce9  mov     ebx, [rsp+78h+arg_10]
0x140048cf0  mov     rcx, [rsp+78h+Mdl]; Mdl
0x140048cf8  call    cs:__imp_IoFreeMdl
0x140048cff  nop     dword ptr [rax+rax+00h]
0x140048d04  xor     r14d, r14d
0x140048d07  mov     r15, [rsp+78h+arg_0]
0x140048d0f  mov     rdi, [rsp+78h+var_40]
0x140048d14  mov     r13b, [rsp+78h+var_48]
0x140048d19  mov     edx, ebx
0x140048d1b  mov     rcx, rdi
0x140048d1e  call    HsmpValidateAttributionEcp
0x140048d23  mov     esi, eax
0x140048d25  mov     ecx, eax
0x140048d27  call    HsmDbgBreakOnStatus
0x140048d2c  test    esi, esi
0x140048d2e  jns     short loc_140048D73
0x140048d30  lea     rax, WPP_GLOBAL_Control
0x140048d37  mov     rcx, cs:WPP_GLOBAL_Control
0x140048d3e  cmp     rcx, rax
0x140048d41  jz      short loc_140048D7D
0x140048d43  mov     edx, [rcx+2Ch]
0x140048d46  test    dl, 1
0x140048d49  jz      short loc_140048D7D
0x140048d4b  cmp     byte ptr [rcx+29h], 2
0x140048d4f  jb      short loc_140048D7D
0x140048d51  mov     edx, 0D5h
0x140048d56  mov     [rsp+78h+var_50], esi
0x140048d5a  mov     dword ptr [rsp+78h+Irp], ebx
0x140048d5e  mov     r9d, [rdi]
0x140048d61  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140048d68  mov     rcx, [rcx+18h]
0x140048d6c  call    WPP_SF_DDd
0x140048d71  jmp     short loc_140048D7D
0x140048d73  mov     [r15+50h], rdi
0x140048d77  xor     edi, edi
0x140048d79  mov     [r15+58h], ebx
0x140048d7d  test    rdi, rdi
0x140048d80  jz      short loc_140048D96
0x140048d82  mov     edx, 69417348h; Tag
0x140048d87  mov     rcx, rdi; P
0x140048d8a  call    cs:__imp_ExFreePoolWithTag
0x140048d91  nop     dword ptr [rax+rax+00h]
0x140048d96  test    r13b, r13b
0x140048d99  jz      short loc_140048DAA
0x140048d9b  mov     rcx, r14; MemoryDescriptorList
0x140048d9e  call    cs:__imp_MmUnlockPages
0x140048da5  nop     dword ptr [rax+rax+00h]
0x140048daa  test    r14, r14
0x140048dad  jz      short loc_140048DBE
0x140048daf  mov     rcx, r14; Mdl
0x140048db2  call    cs:__imp_IoFreeMdl
0x140048db9  nop     dword ptr [rax+rax+00h]
0x140048dbe  mov     eax, esi
0x140048dc0  add     rsp, 40h
0x140048dc4  pop     r15
0x140048dc6  pop     r14
0x140048dc8  pop     r13
0x140048dca  pop     r12
0x140048dcc  pop     rdi
0x140048dcd  pop     rsi
0x140048dce  pop     rbx
0x140048dcf  retn
```
