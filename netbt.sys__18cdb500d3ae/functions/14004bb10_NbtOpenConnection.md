# NbtOpenConnection

- ea: `0x14004bb10`
- end: `0x14004bd74`
- name: `NbtOpenConnection`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14004b7a0`

## callees

- `0x140010be8`
- `0x140012a10`
- `0x140031440`
- `0x1400401c4`
- `0x1400439bc`
- `0x14004bb10`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14004bd63`
- `ntoskrnl!IoFreeMdl` at `0x14004bd63`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14004bc53`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x14004bc53`
- `ntoskrnl!IoAllocateMdl` at `0x14004bc0c`
- `ntoskrnl!IoAllocateMdl` at `0x14004bc0c`
- `ntoskrnl!KeInitializeSemaphore` at `0x14004bbe9`
- `ntoskrnl!KeInitializeSemaphore` at `0x14004bbe9`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004bb91`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004bb91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004bc75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004bcae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004bce1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004bc75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004bcae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004bce1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bc69`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bca2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bcd5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bc69`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bca2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bcd5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004bb38`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004bb38`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004bb23`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004bb23`
- `ntoskrnl!ExAllocatePool2` at `0x14004bb62`
- `ntoskrnl!ExAllocatePool2` at `0x14004bb62`

## pseudocode

```c
__int64 __fastcall NbtOpenConnection(_QWORD *a1, __int64 a2, struct _LIST_ENTRY *a3)
{
  char *Pool2; // rax
  char *v7; // rbx
  PMDL Mdl; // rax
  int v9; // edi

  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( !a3[40].Flink || (Pool2 = (char *)ExAllocatePool2(64, 272, 1148478030), (v7 = Pool2) == 0) )
  {
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    return 3221225626LL;
  }
  memset(Pool2, 0, 0x110u);
  KeInitializeSpinLock((PKSPIN_LOCK)v7 + 31);
  *((_QWORD *)v7 + 30) = v7 + 232;
  *((_QWORD *)v7 + 29) = v7 + 232;
  *((_DWORD *)v7 + 4) = 829321027;
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *((_DWORD *)v7 + 5),
      10,
      (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
      (_DWORD)v7,
      *((_DWORD *)v7 + 5),
      *((_DWORD *)v7 + 5) + 1,
      207,
      (__int64)"minio\\netbt\\sys\\name.c");
  _InterlockedIncrement((volatile signed __int32 *)v7 + 5);
  *((_DWORD *)v7 + 12) = 0;
  *((_QWORD *)v7 + 4) = a3;
  *((_QWORD *)v7 + 9) = a2;
  *((_QWORD *)v7 + 13) = v7 + 96;
  *((_QWORD *)v7 + 12) = v7 + 96;
  KeInitializeSemaphore((PRKSEMAPHORE)(v7 + 112), 1, 1);
  Mdl = IoAllocateMdl(v7, 0x1FFFFu, 0, 0, 0);
  *((_QWORD *)v7 + 28) = Mdl;
  if ( !Mdl )
  {
    v9 = -1073741670;
LABEL_12:
    FreeConnectionObj(v7);
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    return (unsigned int)v9;
  }
  v9 = NbtOpenAndAssocConnection((__int64)a3, 0, 0, 50);
  if ( v9 < 0 )
  {
    IoFreeMdl(*((PMDL *)v7 + 28));
    goto LABEL_12;
  }
  ExInterlockedInsertHeadList(a3 + 24, (PLIST_ENTRY)v7, &SpinLock);
  *a1 = v7;
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( (BYTE10(xmmword_140038420) & 8) != 0 )
    WPP_SF_qqq(1299, 12, WPP_8017b60c53a232e581eda6237e04704c_Traceguids, v7, *((_QWORD *)v7 + 3), *((_QWORD *)v7 + 4));
  return 0;
}

```

## disassembly

```asm
0x14004bb10  push    rbx
0x14004bb12  push    rsi
0x14004bb13  push    rdi
0x14004bb14  push    r14
0x14004bb16  sub     rsp, 48h
0x14004bb1a  mov     rsi, r8
0x14004bb1d  mov     rdi, rdx
0x14004bb20  mov     r14, rcx
0x14004bb23  call    cs:__imp_KeEnterCriticalRegion
0x14004bb2a  nop     dword ptr [rax+rax+00h]
0x14004bb2f  mov     dl, 1; Wait
0x14004bb31  lea     rcx, Resource; Resource
0x14004bb38  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004bb3f  nop     dword ptr [rax+rax+00h]
0x14004bb44  cmp     qword ptr [rsi+280h], 0
0x14004bb4c  jz      loc_14004BC9B
0x14004bb52  mov     edx, 110h
0x14004bb57  mov     ecx, 40h ; '@'
0x14004bb5c  mov     r8d, 4474624Eh
0x14004bb62  call    cs:__imp_ExAllocatePool2
0x14004bb69  nop     dword ptr [rax+rax+00h]
0x14004bb6e  mov     rbx, rax
0x14004bb71  test    rax, rax
0x14004bb74  jz      loc_14004BC9B
0x14004bb7a  xor     edx, edx; Val
0x14004bb7c  mov     r8d, 110h; Size
0x14004bb82  mov     rcx, rax; void *
0x14004bb85  call    memset
0x14004bb8a  lea     rcx, [rbx+0F8h]; SpinLock
0x14004bb91  call    cs:__imp_KeInitializeSpinLock
0x14004bb98  nop     dword ptr [rax+rax+00h]
0x14004bb9d  lea     rcx, [rbx+0E8h]
0x14004bba4  mov     [rcx+8], rcx
0x14004bba8  mov     [rcx], rcx
0x14004bbab  mov     dword ptr [rbx+10h], 316E6F43h
0x14004bbb2  test    byte ptr cs:xmmword_140038420+9, 40h
0x14004bbb9  jnz     loc_14004BCF1
0x14004bbbf  lock inc dword ptr [rbx+14h]
0x14004bbc3  lea     rax, [rbx+60h]
0x14004bbc7  mov     dword ptr [rbx+30h], 0
0x14004bbce  mov     [rbx+20h], rsi
0x14004bbd2  lea     rcx, [rbx+70h]; Semaphore
0x14004bbd6  mov     [rbx+48h], rdi
0x14004bbda  mov     edx, 1; Count
0x14004bbdf  mov     r8d, edx; Limit
0x14004bbe2  mov     [rax+8], rax
0x14004bbe6  mov     [rax], rax
0x14004bbe9  call    cs:__imp_KeInitializeSemaphore
0x14004bbf0  nop     dword ptr [rax+rax+00h]
0x14004bbf5  xor     r9d, r9d; ChargeQuota
0x14004bbf8  mov     [rsp+68h+Irp], 0; Irp
0x14004bc01  xor     r8d, r8d; SecondaryBuffer
0x14004bc04  mov     edx, 1FFFFh; Length
0x14004bc09  mov     rcx, rbx; VirtualAddress
0x14004bc0c  call    cs:__imp_IoAllocateMdl
0x14004bc13  nop     dword ptr [rax+rax+00h]
0x14004bc18  mov     [rbx+0E0h], rax
0x14004bc1f  test    rax, rax
0x14004bc22  jz      loc_14004BCC1
0x14004bc28  mov     r9b, 32h ; '2'
0x14004bc2b  xor     r8d, r8d
0x14004bc2e  xor     edx, edx
0x14004bc30  mov     rcx, rsi
0x14004bc33  call    NbtOpenAndAssocConnection
0x14004bc38  mov     edi, eax
0x14004bc3a  test    eax, eax
0x14004bc3c  js      loc_14004BD5C
0x14004bc42  lea     rcx, [rsi+180h]; ListHead
0x14004bc49  mov     rdx, rbx; ListEntry
0x14004bc4c  lea     r8, SpinLock; Lock
0x14004bc53  call    cs:__imp_ExInterlockedInsertHeadList
0x14004bc5a  nop     dword ptr [rax+rax+00h]
0x14004bc5f  lea     rcx, Resource; Resource
0x14004bc66  mov     [r14], rbx
0x14004bc69  call    cs:__imp_ExReleaseResourceLite
0x14004bc70  nop     dword ptr [rax+rax+00h]
0x14004bc75  call    cs:__imp_KeLeaveCriticalRegion
0x14004bc7c  nop     dword ptr [rax+rax+00h]
0x14004bc81  test    byte ptr cs:xmmword_140038420+0Ah, 8
0x14004bc88  jnz     loc_14004BD2C
0x14004bc8e  xor     eax, eax
0x14004bc90  add     rsp, 48h
0x14004bc94  pop     r14
0x14004bc96  pop     rdi
0x14004bc97  pop     rsi
0x14004bc98  pop     rbx
0x14004bc99  retn
0x14004bc9b  lea     rcx, Resource; Resource
0x14004bca2  call    cs:__imp_ExReleaseResourceLite
0x14004bca9  nop     dword ptr [rax+rax+00h]
0x14004bcae  call    cs:__imp_KeLeaveCriticalRegion
0x14004bcb5  nop     dword ptr [rax+rax+00h]
0x14004bcba  mov     eax, 0C000009Ah
0x14004bcbf  jmp     short loc_14004BC90
0x14004bcc1  mov     edi, 0C000009Ah
0x14004bcc6  mov     rcx, rbx; P
0x14004bcc9  call    FreeConnectionObj
0x14004bcce  lea     rcx, Resource; Resource
0x14004bcd5  call    cs:__imp_ExReleaseResourceLite
0x14004bcdc  nop     dword ptr [rax+rax+00h]
0x14004bce1  call    cs:__imp_KeLeaveCriticalRegion
0x14004bce8  nop     dword ptr [rax+rax+00h]
0x14004bced  mov     eax, edi
0x14004bcef  jmp     short loc_14004BC90
0x14004bcf1  mov     ecx, [rbx+14h]
0x14004bcf4  lea     r8, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x14004bcfb  mov     [rsp+68h+var_30], r8
0x14004bd00  mov     edx, 0Ah
0x14004bd05  mov     [rsp+68h+var_38], 6CFh
0x14004bd0d  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x14004bd14  mov     r9, rbx
0x14004bd17  lea     eax, [rcx+1]
0x14004bd1a  mov     dword ptr [rsp+68h+var_40], eax
0x14004bd1e  mov     dword ptr [rsp+68h+Irp], ecx
0x14004bd22  call    WPP_SF_qddds
0x14004bd27  jmp     loc_14004BBBF
0x14004bd2c  mov     rax, [rbx+20h]
0x14004bd30  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x14004bd37  mov     [rsp+68h+var_40], rax
0x14004bd3c  mov     edx, 0Ch
0x14004bd41  mov     rax, [rbx+18h]
0x14004bd45  mov     ecx, 513h
0x14004bd4a  mov     r9, rbx
0x14004bd4d  mov     [rsp+68h+Irp], rax
0x14004bd52  call    WPP_SF_qqq
0x14004bd57  jmp     loc_14004BC8E
0x14004bd5c  mov     rcx, [rbx+0E0h]; Mdl
0x14004bd63  call    cs:__imp_IoFreeMdl
0x14004bd6a  nop     dword ptr [rax+rax+00h]
0x14004bd6f  jmp     loc_14004BCC6
```
