# HacAllocate

- ea: `0x14000c370`
- end: `0x14000c811`
- name: `HacAllocate`
- size: `1185`
- prototype: `struct _UNICODE_STRING *__fastcall(__int64, __int64, const UNICODE_STRING *, const UNICODE_STRING *)`
- caller_count: `7`
- callee_count: `10`
- tags: ``

## callers

- `0x140004530`
- `0x1400070a0`
- `0x14000be20`
- `0x14000fbc0`
- `0x140019044`
- `0x140020884`
- `0x140025484`

## callees

- `0x140005c90`
- `0x140009380`
- `0x140009540`
- `0x14000c370`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140019d7c`
- `0x1400206e4`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000c770`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000c770`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000c787`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000c7b9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000c787`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000c7b9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c3e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c62a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c3e6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c62a`
- `ntoskrnl!KeReleaseMutex` at `0x14000c4c9`
- `ntoskrnl!KeReleaseMutex` at `0x14000c653`
- `ntoskrnl!KeReleaseMutex` at `0x14000c4c9`
- `ntoskrnl!KeReleaseMutex` at `0x14000c653`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7fe`
- `ntoskrnl!ExAllocatePool2` at `0x14000c522`
- `ntoskrnl!ExAllocatePool2` at `0x14000c704`
- `ntoskrnl!ExAllocatePool2` at `0x14000c522`
- `ntoskrnl!ExAllocatePool2` at `0x14000c704`

## pseudocode

```c
struct _UNICODE_STRING *__fastcall HacAllocate(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4)
{
  unsigned int i; // r15d
  __int64 v9; // rbp
  __int64 Pool2; // rax
  struct _UNICODE_STRING *v11; // rsi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  int MaximumLength; // ecx
  struct _UNICODE_STRING *v16; // rax
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  PLARGE_INTEGER Timeout; // [rsp+20h] [rbp-48h]
  _OWORD v20[3]; // [rsp+30h] [rbp-38h] BYREF

  v20[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    WPP_SF_ZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      (unsigned int)WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids,
      (_DWORD)a3,
      (__int64)a4);
  KeWaitForSingleObject((PVOID)a2, Executive, 0, 0, 0);
  if ( (unsigned int)(*(_DWORD *)(a2 + 80) + 1024) >= *(_DWORD *)(a2 + 84) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
    for ( i = 0; i < 0xA; ++i )
    {
      v9 = *(_QWORD *)(a2 + 88);
      if ( !v9 )
      {
LABEL_17:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
        }
        break;
      }
      while ( *(_DWORD *)(v9 + 52) || *(_DWORD *)(v9 + 56) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
        {
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            44,
            WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids,
            v9 + 64,
            Timeout);
        }
        v9 = *(_QWORD *)(v9 + 16);
        if ( !v9 )
          goto LABEL_17;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          45,
          WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids,
          v9 + 64,
          Timeout);
      }
      ++*(_DWORD *)(v9 + 52);
      HacpRemoveEntry(v9);
      HacDereference(a1, v9);
    }
  }
  KeReleaseMutex((PRKMUTEX)a2, 0);
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids, a3, Timeout);
    Pool2 = ExAllocatePool2(258, a3->MaximumLength + 288LL, 1213359694);
    v11 = (struct _UNICODE_STRING *)Pool2;
    if ( !Pool2 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return 0;
      v13 = 28;
      goto LABEL_28;
    }
    *(_QWORD *)(Pool2 + 40) = a2;
    if ( a3->Length )
    {
      *(_QWORD *)(Pool2 + 72) = Pool2 + 288;
      *(_WORD *)(Pool2 + 64) = a3->Length;
      *(_WORD *)(Pool2 + 66) = a3->MaximumLength;
      memmove((void *)(Pool2 + 288), a3->Buffer, a3->MaximumLength);
    }
    else
    {
      *(_QWORD *)(Pool2 + 72) = 0;
      *(_DWORD *)(Pool2 + 64) = 0;
    }
LABEL_35:
    MdaDissectNameTail(&v11[4], v20, &v11[5]);
    *(_QWORD *)&v11->Length = 0;
    v11[3].Length = 1;
    *(_QWORD *)(&v11[3].MaximumLength + 1) = 1;
    v11->Buffer = 0;
    *(_QWORD *)&v11[2].Length = 0;
    *(_QWORD *)&v11[1].Length = 0;
    v11[1].Buffer = 0;
    *(_QWORD *)&v11[6].Length = 0;
    v11[7].Buffer = 0;
    v11[6].Buffer = 0;
    *(_DWORD *)&v11[7].Length = 0;
    HIDWORD(v11[17].Buffer) = 0;
    KeWaitForSingleObject((PVOID)a2, Executive, 0, 0, 0);
    HacMakeEntryMRU(v11);
    MaximumLength = v11[4].MaximumLength;
    ++*(_DWORD *)(a2 + 76);
    *(_DWORD *)(a2 + 80) += MaximumLength + 288;
    KeReleaseMutex((PRKMUTEX)a2, 0);
    return v11;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
    WPP_SF_ZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      29,
      (unsigned int)WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids,
      (_DWORD)a3,
      (__int64)a4);
  v16 = (struct _UNICODE_STRING *)ExAllocatePool2(
                                    258,
                                    a4->Length + (unsigned __int64)a3->Length + Slash.Length + 290LL,
                                    1213359694);
  v11 = v16;
  if ( v16 )
  {
    v16[2].Buffer = (PWSTR)a2;
    v16[4].Length = 0;
    v16[4].Buffer = &v16[18].Length;
    v16[4].MaximumLength = Slash.Length + a4->Length + 2 + a3->Length;
    RtlCopyUnicodeString(v16 + 4, a3);
    if ( RtlAppendUnicodeStringToString(v11 + 4, &Slash) >= 0 )
    {
      if ( RtlAppendUnicodeStringToString(v11 + 4, a4) >= 0 )
        goto LABEL_35;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
LABEL_53:
        ExFreePoolWithTag(v11, 0);
        return 0;
      }
      v18 = 32;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_53;
      v18 = 31;
    }
    WPP_SF_d(v17->AttachedDevice, v18, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
    goto LABEL_53;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    return 0;
  v13 = 30;
LABEL_28:
  WPP_SF_(v12->AttachedDevice, v13, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14000c370  mov     [rsp+arg_10], rbx
0x14000c375  push    rsi
0x14000c376  push    rdi
0x14000c377  push    r12
0x14000c379  push    r13
0x14000c37b  push    r14
0x14000c37d  sub     rsp, 40h
0x14000c381  xorps   xmm0, xmm0
0x14000c384  mov     rdi, r9
0x14000c387  movups  [rsp+68h+var_38], xmm0
0x14000c38c  mov     r14, r8
0x14000c38f  mov     rbx, rdx
0x14000c392  mov     rsi, rcx
0x14000c395  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c39c  lea     r12, WPP_GLOBAL_Control
0x14000c3a3  cmp     rcx, r12
0x14000c3a6  jz      short loc_14000C3CE
0x14000c3a8  test    dword ptr [rcx+2Ch], 800h
0x14000c3af  jz      short loc_14000C3CE
0x14000c3b1  mov     rcx, [rcx+18h]
0x14000c3b5  mov     edx, 1Ah
0x14000c3ba  mov     [rsp+68h+Timeout], r9
0x14000c3bf  mov     r9, r8
0x14000c3c2  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c3c9  call    WPP_SF_ZZ
0x14000c3ce  xor     r13d, r13d
0x14000c3d1  mov     [rsp+68h+arg_8], r15
0x14000c3d6  xor     r9d, r9d; Alertable
0x14000c3d9  mov     [rsp+68h+Timeout], r13; Timeout
0x14000c3de  xor     r8d, r8d; WaitMode
0x14000c3e1  xor     edx, edx; WaitReason
0x14000c3e3  mov     rcx, rbx; Object
0x14000c3e6  call    cs:__imp_KeWaitForSingleObject
0x14000c3ed  nop     dword ptr [rax+rax+00h]
0x14000c3f2  mov     eax, [rbx+50h]
0x14000c3f5  add     eax, 400h
0x14000c3fa  cmp     eax, [rbx+54h]
0x14000c3fd  jb      loc_14000C4C4
0x14000c403  mov     [rsp+68h+arg_0], rbp
0x14000c408  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c40f  cmp     rcx, r12
0x14000c412  jz      short loc_14000C432
0x14000c414  test    dword ptr [rcx+2Ch], 800h
0x14000c41b  jz      short loc_14000C432
0x14000c41d  mov     rcx, [rcx+18h]
0x14000c421  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c428  mov     edx, 29h ; ')'
0x14000c42d  call    WPP_SF_
0x14000c432  mov     rax, ds:0FFFFF78000000014h
0x14000c43c  mov     r15d, r13d
0x14000c43f  cmp     r15d, 0Ah
0x14000c443  jnb     short loc_14000C4BF
0x14000c445  mov     rbp, [rbx+58h]
0x14000c449  test    rbp, rbp
0x14000c44c  jz      short loc_14000C495
0x14000c44e  cmp     [rbp+34h], r13d
0x14000c452  jnz     short loc_14000C45E
0x14000c454  cmp     [rbp+38h], r13d
0x14000c458  jz      loc_14000C56F
0x14000c45e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c465  cmp     rcx, r12
0x14000c468  jz      short loc_14000C48C
0x14000c46a  test    dword ptr [rcx+2Ch], 800h
0x14000c471  jz      short loc_14000C48C
0x14000c473  mov     rcx, [rcx+18h]
0x14000c477  lea     r9, [rbp+40h]
0x14000c47b  mov     edx, 2Ch ; ','
0x14000c480  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c487  call    WPP_SF_Z
0x14000c48c  mov     rbp, [rbp+10h]
0x14000c490  test    rbp, rbp
0x14000c493  jnz     short loc_14000C44E
0x14000c495  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c49c  cmp     rcx, r12
0x14000c49f  jz      short loc_14000C4BF
0x14000c4a1  test    dword ptr [rcx+2Ch], 800h
0x14000c4a8  jz      short loc_14000C4BF
0x14000c4aa  mov     rcx, [rcx+18h]
0x14000c4ae  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c4b5  mov     edx, 2Eh ; '.'
0x14000c4ba  call    WPP_SF_
0x14000c4bf  mov     rbp, [rsp+68h+arg_0]
0x14000c4c4  xor     edx, edx; Wait
0x14000c4c6  mov     rcx, rbx; Mutex
0x14000c4c9  call    cs:__imp_KeReleaseMutex
0x14000c4d0  nop     dword ptr [rax+rax+00h]
0x14000c4d5  test    rdi, rdi
0x14000c4d8  jnz     loc_14000C6AC
0x14000c4de  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c4e5  cmp     rcx, r12
0x14000c4e8  jz      short loc_14000C50B
0x14000c4ea  test    dword ptr [rcx+2Ch], 2000h
0x14000c4f1  jz      short loc_14000C50B
0x14000c4f3  mov     rcx, [rcx+18h]
0x14000c4f7  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c4fe  mov     edx, 1Bh
0x14000c503  mov     r9, r14
0x14000c506  call    WPP_SF_Z
0x14000c50b  movzx   edx, word ptr [r14+2]
0x14000c510  mov     ecx, 102h
0x14000c515  add     rdx, 120h
0x14000c51c  mov     r8d, 4852664Eh
0x14000c522  call    cs:__imp_ExAllocatePool2
0x14000c529  nop     dword ptr [rax+rax+00h]
0x14000c52e  mov     rsi, rax
0x14000c531  test    rax, rax
0x14000c534  jnz     loc_14000C5BB
0x14000c53a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c541  cmp     rcx, r12
0x14000c544  jz      loc_14000C80A
0x14000c54a  mov     eax, [rcx+2Ch]
0x14000c54d  test    al, 1
0x14000c54f  jz      loc_14000C80A
0x14000c555  mov     edx, 1Ch
0x14000c55a  mov     rcx, [rcx+18h]
0x14000c55e  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c565  call    WPP_SF_
0x14000c56a  jmp     loc_14000C80A
0x14000c56f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c576  cmp     rcx, r12
0x14000c579  jz      short loc_14000C59D
0x14000c57b  test    dword ptr [rcx+2Ch], 800h
0x14000c582  jz      short loc_14000C59D
0x14000c584  mov     rcx, [rcx+18h]
0x14000c588  lea     r9, [rbp+40h]
0x14000c58c  mov     edx, 2Dh ; '-'
0x14000c591  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c598  call    WPP_SF_Z
0x14000c59d  inc     dword ptr [rbp+34h]
0x14000c5a0  mov     rcx, rbp
0x14000c5a3  call    HacpRemoveEntry
0x14000c5a8  mov     rdx, rbp
0x14000c5ab  mov     rcx, rsi
0x14000c5ae  call    HacDereference
0x14000c5b3  inc     r15d
0x14000c5b6  jmp     loc_14000C43F
0x14000c5bb  mov     [rax+28h], rbx
0x14000c5bf  cmp     [r14], r13w
0x14000c5c3  jnz     loc_14000C67D
0x14000c5c9  mov     [rax+48h], r13
0x14000c5cd  mov     [rax+40h], r13d
0x14000c5d1  lea     r8, [rsi+50h]
0x14000c5d5  lea     rcx, [rsi+40h]
0x14000c5d9  lea     rdx, [rsp+68h+var_38]
0x14000c5de  call    MdaDissectNameTail
0x14000c5e3  mov     eax, 1
0x14000c5e8  mov     [rsi], r13
0x14000c5eb  xor     r9d, r9d; Alertable
0x14000c5ee  mov     [rsi+30h], ax
0x14000c5f2  xor     r8d, r8d; WaitMode
0x14000c5f5  mov     [rsi+34h], rax
0x14000c5f9  xor     edx, edx; WaitReason
0x14000c5fb  mov     [rsi+8], r13
0x14000c5ff  mov     rcx, rbx; Object
0x14000c602  mov     [rsi+20h], r13
0x14000c606  mov     [rsi+10h], r13
0x14000c60a  mov     [rsi+18h], r13
0x14000c60e  mov     [rsi+60h], r13
0x14000c612  mov     [rsi+78h], r13
0x14000c616  mov     [rsi+68h], r13
0x14000c61a  mov     [rsi+70h], r13d
0x14000c61e  mov     [rsi+11Ch], r13d
0x14000c625  mov     [rsp+68h+Timeout], r13; Timeout
0x14000c62a  call    cs:__imp_KeWaitForSingleObject
0x14000c631  nop     dword ptr [rax+rax+00h]
0x14000c636  mov     rcx, rsi
0x14000c639  call    HacMakeEntryMRU
0x14000c63e  movzx   ecx, word ptr [rsi+42h]
0x14000c642  xor     edx, edx; Wait
0x14000c644  inc     dword ptr [rbx+4Ch]
0x14000c647  add     ecx, 120h
0x14000c64d  add     [rbx+50h], ecx
0x14000c650  mov     rcx, rbx; Mutex
0x14000c653  call    cs:__imp_KeReleaseMutex
0x14000c65a  nop     dword ptr [rax+rax+00h]
0x14000c65f  mov     rax, rsi
0x14000c662  mov     r15, [rsp+68h+arg_8]
0x14000c667  mov     rbx, [rsp+68h+arg_10]
0x14000c66f  add     rsp, 40h
0x14000c673  pop     r14
0x14000c675  pop     r13
0x14000c677  pop     r12
0x14000c679  pop     rdi
0x14000c67a  pop     rsi
0x14000c67b  retn
0x14000c67d  lea     rcx, [rax+120h]; void *
0x14000c684  mov     [rax+48h], rcx
0x14000c688  movzx   eax, word ptr [r14]
0x14000c68c  mov     [rsi+40h], ax
0x14000c690  movzx   eax, word ptr [r14+2]
0x14000c695  mov     [rsi+42h], ax
0x14000c699  movzx   r8d, word ptr [r14+2]; Size
0x14000c69e  mov     rdx, [r14+8]; Src
0x14000c6a2  call    memmove
0x14000c6a7  jmp     loc_14000C5D1
0x14000c6ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c6b3  cmp     rcx, r12
0x14000c6b6  jz      short loc_14000C6DE
0x14000c6b8  test    dword ptr [rcx+2Ch], 2000h
0x14000c6bf  jz      short loc_14000C6DE
0x14000c6c1  mov     rcx, [rcx+18h]
0x14000c6c5  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c6cc  mov     edx, 1Dh
0x14000c6d1  mov     [rsp+68h+Timeout], rdi
0x14000c6d6  mov     r9, r14
0x14000c6d9  call    WPP_SF_ZZ
0x14000c6de  movzx   ecx, word ptr [r14]
0x14000c6e2  mov     r8d, 4852664Eh
0x14000c6e8  movzx   eax, word ptr [rdi]
0x14000c6eb  movzx   edx, cs:Slash.Length
0x14000c6f2  add     rcx, rax
0x14000c6f5  add     rdx, 122h
0x14000c6fc  add     rdx, rcx
0x14000c6ff  mov     ecx, 102h
0x14000c704  call    cs:__imp_ExAllocatePool2
0x14000c70b  nop     dword ptr [rax+rax+00h]
0x14000c710  mov     rsi, rax
0x14000c713  test    rax, rax
0x14000c716  jnz     short loc_14000C73D
0x14000c718  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c71f  cmp     rcx, r12
0x14000c722  jz      loc_14000C80A
0x14000c728  mov     eax, [rcx+2Ch]
0x14000c72b  test    al, 1
0x14000c72d  jz      loc_14000C80A
0x14000c733  mov     edx, 1Eh
0x14000c738  jmp     loc_14000C55A
0x14000c73d  mov     [rax+28h], rbx
0x14000c741  mov     rdx, r14; SourceString
0x14000c744  add     rax, 120h
0x14000c74a  mov     [rsi+40h], r13w
0x14000c74f  mov     [rsi+48h], rax
0x14000c753  movzx   ecx, word ptr [r14]
0x14000c757  movzx   eax, word ptr [rdi]
0x14000c75a  add     ax, 2
0x14000c75e  add     cx, ax
0x14000c761  add     cx, cs:Slash.Length
0x14000c768  mov     [rsi+42h], cx
0x14000c76c  lea     rcx, [rsi+40h]; DestinationString
0x14000c770  call    cs:__imp_RtlCopyUnicodeString
0x14000c777  nop     dword ptr [rax+rax+00h]
0x14000c77c  lea     rdx, Slash; Source
0x14000c783  lea     rcx, [rsi+40h]; Destination
0x14000c787  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000c78e  nop     dword ptr [rax+rax+00h]
0x14000c793  test    eax, eax
0x14000c795  jns     short loc_14000C7B2
0x14000c797  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c79e  cmp     rcx, r12
0x14000c7a1  jz      short loc_14000C7F9
0x14000c7a3  mov     edx, [rcx+2Ch]
0x14000c7a6  test    dl, 1
0x14000c7a9  jz      short loc_14000C7F9
0x14000c7ab  mov     edx, 1Fh
0x14000c7b0  jmp     short loc_14000C7E6
0x14000c7b2  mov     rdx, rdi; Source
0x14000c7b5  lea     rcx, [rsi+40h]; Destination
0x14000c7b9  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000c7c0  nop     dword ptr [rax+rax+00h]
0x14000c7c5  test    eax, eax
0x14000c7c7  jns     loc_14000C5D1
0x14000c7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c7d4  cmp     rcx, r12
0x14000c7d7  jz      short loc_14000C7F9
0x14000c7d9  mov     edx, [rcx+2Ch]
0x14000c7dc  test    dl, 1
0x14000c7df  jz      short loc_14000C7F9
0x14000c7e1  mov     edx, 20h ; ' '
0x14000c7e6  mov     rcx, [rcx+18h]
0x14000c7ea  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14000c7f1  mov     r9d, eax
0x14000c7f4  call    WPP_SF_d
0x14000c7f9  xor     edx, edx; Tag
0x14000c7fb  mov     rcx, rsi; P
0x14000c7fe  call    cs:__imp_ExFreePoolWithTag
0x14000c805  nop     dword ptr [rax+rax+00h]
0x14000c80a  xor     eax, eax
0x14000c80c  jmp     loc_14000C662
```
