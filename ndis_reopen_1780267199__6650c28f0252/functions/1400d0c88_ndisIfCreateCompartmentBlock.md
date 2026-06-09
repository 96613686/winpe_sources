# ndisIfCreateCompartmentBlock

- ea: `0x1400d0c88`
- end: `0x1400d0f97`
- name: `ndisIfCreateCompartmentBlock`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400d0198`
- `0x1400d07f8`

## callees

- `0x1400d0c88`
- `0x1400d164c`
- `0x1400d1c0c`
- `0x1400d1d00`
- `0x1400d1ec8`
- `0x1400d208c`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f19`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0f19`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0cea`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0cea`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0e7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0f08`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0f48`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0e7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0f08`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400d0f48`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0de1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400d0de1`
- `ntoskrnl!ExUuidCreate` at `0x1400d0d88`
- `ntoskrnl!ExUuidCreate` at `0x1400d0d88`

## pseudocode

```c
__int64 __fastcall ndisIfCreateCompartmentBlock(
        unsigned int a1,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        _QWORD *a4)
{
  __int64 Pool2; // rax
  int v9; // edx
  int v10; // r8d
  int v11; // r9d
  _QWORD *v12; // rdi
  int v13; // ebx
  _QWORD *v14; // rax
  size_t v15; // r8
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // r8d
  KIRQL v20; // r15
  int v21; // edx
  unsigned int AvailableCompartmentId; // r14d
  struct _GUID v23; // xmm0
  struct _NDIS_IF_COMPARTMENT_BLOCK *v24; // rax
  struct _NDIS_IF_COMPARTMENT_BLOCK **v25; // rdx
  __int64 *v26; // rcx
  __int64 v27; // rax

  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_L_guid_q(*((_QWORD *)WPP_GLOBAL_Control + 8), (_DWORD)a2, (_DWORD)a3, (_DWORD)a4);
  *a4 = 0;
  Pool2 = ExAllocatePool2(64, 1768, 1718174798);
  v12 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 16) = a1;
    v14 = (_QWORD *)(Pool2 + 24);
    *(_QWORD *)((char *)v12 + 44) = 1;
    *((_DWORD *)v12 + 10) = 8;
    v14[1] = v14;
    *v14 = v14;
    v12[217] = v12 + 216;
    v12[216] = v12 + 216;
    if ( a3 )
    {
      v13 = 0;
      v15 = 1640;
      if ( a3[1] < 0x668u )
        v15 = a3[1];
      memmove(v12 + 8, a3, v15);
    }
    else
    {
      v16 = ExUuidCreate((UUID *)v12 + 5);
      v13 = v16;
      if ( v16 < 0 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_l_guid_d(*((_QWORD *)WPP_GLOBAL_Control + 8), v17, v18, 15);
        goto LABEL_37;
      }
      if ( v16 == 1073872982 )
        v13 = 0;
    }
    v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
    if ( a2 )
    {
      AvailableCompartmentId = ndisIfFindAvailableCompartmentId(a2);
      if ( !AvailableCompartmentId )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = 2;
          WPP_RECORDER_SF_l_guid_(*((_QWORD *)WPP_GLOBAL_Control + 8), v21, v19, 16);
        }
        v13 = -1073741270;
LABEL_25:
        KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v20);
        if ( v13 >= 0 )
        {
LABEL_39:
          *a4 = v12;
          goto LABEL_40;
        }
LABEL_37:
        ExFreePoolWithTag(v12, 0);
        goto LABEL_40;
      }
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = 4;
        WPP_RECORDER_SF_l_guid_(*((_QWORD *)WPP_GLOBAL_Control + 8), v21, v19, 17);
      }
      v23 = *a2;
      a1 = AvailableCompartmentId;
      *((_DWORD *)v12 + 4) = AvailableCompartmentId;
      *(struct _GUID *)(v12 + 143) = v23;
    }
    if ( !v13 )
    {
      v24 = qword_1401229D8;
      v25 = &qword_1401229D8;
      while ( 1 )
      {
        if ( v24 == (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_1401229D8 )
        {
LABEL_32:
          _InterlockedIncrement((volatile signed __int32 *)v12 + 11);
          v26 = (__int64 *)*((_QWORD *)v24 + 1);
          v27 = *v26;
          if ( *(__int64 **)(*v26 + 8) != v26 )
            __fastfail(3u);
          *v12 = v27;
          v12[1] = v26;
          *(_QWORD *)(v27 + 8) = v12;
          *v26 = (__int64)v12;
          _InterlockedIncrement(&dword_140123634);
          KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v20);
          goto LABEL_39;
        }
        if ( *((_DWORD *)v24 + 4) == a1 )
          break;
        if ( *((_DWORD *)v24 + 4) > a1 )
          goto LABEL_32;
        v24 = *(struct _NDIS_IF_COMPARTMENT_BLOCK **)v24;
      }
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v25) = 2;
        WPP_RECORDER_SF_l_guid_(*((_QWORD *)WPP_GLOBAL_Control + 8), (_DWORD)v25, v19, 18);
      }
      v13 = -1073741270;
      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v20);
      goto LABEL_37;
    }
    goto LABEL_25;
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_l_guid_(*((_QWORD *)WPP_GLOBAL_Control + 8), v9, v10, 14);
  }
  v13 = -1073741670;
LABEL_40:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_L_guid_qd(*((_QWORD *)WPP_GLOBAL_Control + 8), v9, v10, v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400d0c88  push    rbx
0x1400d0c8a  push    rbp
0x1400d0c8b  push    rsi
0x1400d0c8c  push    rdi
0x1400d0c8d  push    r12
0x1400d0c8f  push    r13
0x1400d0c91  push    r14
0x1400d0c93  push    r15
0x1400d0c95  sub     rsp, 58h
0x1400d0c99  mov     r12, r9
0x1400d0c9c  mov     r14, r8
0x1400d0c9f  mov     rbp, rdx
0x1400d0ca2  mov     esi, ecx
0x1400d0ca4  lea     r13, WPP_RECORDER_INITIALIZED
0x1400d0cab  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400d0cb2  jz      short loc_1400D0CD2
0x1400d0cb4  mov     [rsp+98h+var_60], r8
0x1400d0cb9  mov     [rsp+98h+var_68], rdx
0x1400d0cbe  mov     [rsp+98h+var_70], ecx
0x1400d0cc2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0cc9  mov     rcx, [rcx+40h]
0x1400d0ccd  call    WPP_RECORDER_SF_L_guid_q
0x1400d0cd2  mov     edx, 6E8h
0x1400d0cd7  mov     qword ptr [r12], 0
0x1400d0cdf  mov     ecx, 40h ; '@'
0x1400d0ce4  mov     r8d, 6669444Eh
0x1400d0cea  call    cs:__imp_ExAllocatePool2
0x1400d0cf1  nop     dword ptr [rax+rax+00h]
0x1400d0cf6  mov     rdi, rax
0x1400d0cf9  test    rax, rax
0x1400d0cfc  jnz     short loc_1400D0D30
0x1400d0cfe  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400d0d05  jz      short loc_1400D0D26
0x1400d0d07  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0d0e  lea     r9d, [rax+0Eh]
0x1400d0d12  mov     [rsp+98h+var_68], rbp
0x1400d0d17  mov     dl, 2
0x1400d0d19  mov     [rsp+98h+var_70], esi
0x1400d0d1d  mov     rcx, [rcx+40h]
0x1400d0d21  call    WPP_RECORDER_SF_l_guid_
0x1400d0d26  mov     ebx, 0C000009Ah
0x1400d0d2b  jmp     loc_1400D0F58
0x1400d0d30  mov     [rax+10h], esi
0x1400d0d33  add     rax, 18h
0x1400d0d37  mov     qword ptr [rdi+2Ch], 1
0x1400d0d3f  mov     dword ptr [rdi+28h], 8
0x1400d0d46  mov     [rax+8], rax
0x1400d0d4a  mov     [rax], rax
0x1400d0d4d  lea     rax, [rdi+6C0h]
0x1400d0d54  mov     [rax+8], rax
0x1400d0d58  mov     [rax], rax
0x1400d0d5b  test    r14, r14
0x1400d0d5e  jz      short loc_1400D0D84
0x1400d0d60  movzx   eax, word ptr [r14+2]
0x1400d0d65  xor     ebx, ebx
0x1400d0d67  mov     r8d, 668h
0x1400d0d6d  cmp     ax, r8w
0x1400d0d71  jnb     short loc_1400D0D76
0x1400d0d73  mov     r8d, eax; Size
0x1400d0d76  lea     rcx, [rdi+40h]; void *
0x1400d0d7a  mov     rdx, r14; Src
0x1400d0d7d  call    memmove
0x1400d0d82  jmp     short loc_1400D0DDA
0x1400d0d84  lea     rcx, [rdi+50h]; Uuid
0x1400d0d88  call    cs:__imp_ExUuidCreate
0x1400d0d8f  nop     dword ptr [rax+rax+00h]
0x1400d0d94  mov     ebx, eax
0x1400d0d96  test    eax, eax
0x1400d0d98  jns     short loc_1400D0DCF
0x1400d0d9a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400d0da1  jz      loc_1400D0F14
0x1400d0da7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0dae  mov     r9d, 0Fh
0x1400d0db4  mov     dword ptr [rsp+98h+var_60], eax
0x1400d0db8  mov     [rsp+98h+var_68], rbp
0x1400d0dbd  mov     [rsp+98h+var_70], esi
0x1400d0dc1  mov     rcx, [rcx+40h]
0x1400d0dc5  call    WPP_RECORDER_SF_l_guid_d
0x1400d0dca  jmp     loc_1400D0F14
0x1400d0dcf  xor     eax, eax
0x1400d0dd1  cmp     ebx, 40020056h
0x1400d0dd7  cmovz   ebx, eax
0x1400d0dda  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400d0de1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400d0de8  nop     dword ptr [rax+rax+00h]
0x1400d0ded  mov     r15b, al
0x1400d0df0  test    rbp, rbp
0x1400d0df3  jz      short loc_1400D0E71
0x1400d0df5  mov     rcx, rbp; struct _GUID *
0x1400d0df8  call    ?ndisIfFindAvailableCompartmentId@@YAIPEBU_GUID@@@Z; ndisIfFindAvailableCompartmentId(_GUID const *)
0x1400d0dfd  mov     r14d, eax
0x1400d0e00  test    eax, eax
0x1400d0e02  jnz     short loc_1400D0E33
0x1400d0e04  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400d0e0b  jz      short loc_1400D0E2C
0x1400d0e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0e14  lea     r9d, [rax+10h]
0x1400d0e18  mov     [rsp+98h+var_68], rbp
0x1400d0e1d  mov     dl, 2
0x1400d0e1f  mov     [rsp+98h+var_70], esi
0x1400d0e23  mov     rcx, [rcx+40h]
0x1400d0e27  call    WPP_RECORDER_SF_l_guid_
0x1400d0e2c  mov     ebx, 0C000022Ah
0x1400d0e31  jmp     short loc_1400D0E75
0x1400d0e33  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400d0e3a  jz      short loc_1400D0E5E
0x1400d0e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0e43  mov     r9d, 11h
0x1400d0e49  mov     [rsp+98h+var_68], rbp
0x1400d0e4e  mov     dl, 4
0x1400d0e50  mov     [rsp+98h+var_70], r14d
0x1400d0e55  mov     rcx, [rcx+40h]
0x1400d0e59  call    WPP_RECORDER_SF_l_guid_
0x1400d0e5e  movups  xmm0, xmmword ptr [rbp+0]
0x1400d0e62  mov     esi, r14d
0x1400d0e65  mov     [rdi+10h], r14d
0x1400d0e69  movdqu  xmmword ptr [rdi+478h], xmm0
0x1400d0e71  test    ebx, ebx
0x1400d0e73  jz      short loc_1400D0E98
0x1400d0e75  mov     dl, r15b; NewIrql
0x1400d0e78  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400d0e7f  call    cs:__imp_KeReleaseSpinLock
0x1400d0e86  nop     dword ptr [rax+rax+00h]
0x1400d0e8b  test    ebx, ebx
0x1400d0e8d  js      loc_1400D0F14
0x1400d0e93  jmp     loc_1400D0F54
0x1400d0e98  mov     rax, cs:qword_1401229D8
0x1400d0e9f  lea     rdx, qword_1401229D8
0x1400d0ea6  jmp     short loc_1400D0EB2
0x1400d0ea8  cmp     [rax+10h], esi
0x1400d0eab  jz      short loc_1400D0ECF
0x1400d0ead  ja      short loc_1400D0EB7
0x1400d0eaf  mov     rax, [rax]
0x1400d0eb2  cmp     rax, rdx
0x1400d0eb5  jnz     short loc_1400D0EA8
0x1400d0eb7  lock inc dword ptr [rdi+2Ch]
0x1400d0ebb  mov     rcx, [rax+8]
0x1400d0ebf  mov     rax, [rcx]
0x1400d0ec2  cmp     [rax+8], rcx
0x1400d0ec6  jz      short loc_1400D0F29
0x1400d0ec8  mov     ecx, 3
0x1400d0ecd  int     29h; Win8: RtlFailFast(ecx)
0x1400d0ecf  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400d0ed6  jz      short loc_1400D0EF9
0x1400d0ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0edf  mov     r9d, 12h
0x1400d0ee5  mov     [rsp+98h+var_68], rbp
0x1400d0eea  mov     dl, 2
0x1400d0eec  mov     [rsp+98h+var_70], esi
0x1400d0ef0  mov     rcx, [rcx+40h]
0x1400d0ef4  call    WPP_RECORDER_SF_l_guid_
0x1400d0ef9  mov     dl, r15b; NewIrql
0x1400d0efc  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400d0f03  mov     ebx, 0C000022Ah
0x1400d0f08  call    cs:__imp_KeReleaseSpinLock
0x1400d0f0f  nop     dword ptr [rax+rax+00h]
0x1400d0f14  xor     edx, edx; Tag
0x1400d0f16  mov     rcx, rdi; P
0x1400d0f19  call    cs:__imp_ExFreePoolWithTag
0x1400d0f20  nop     dword ptr [rax+rax+00h]
0x1400d0f25  xor     edi, edi
0x1400d0f27  jmp     short loc_1400D0F58
0x1400d0f29  mov     [rdi], rax
0x1400d0f2c  mov     [rdi+8], rcx
0x1400d0f30  mov     [rax+8], rdi
0x1400d0f34  mov     [rcx], rdi
0x1400d0f37  lock inc cs:dword_140123634
0x1400d0f3e  mov     dl, r15b; NewIrql
0x1400d0f41  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400d0f48  call    cs:__imp_KeReleaseSpinLock
0x1400d0f4f  nop     dword ptr [rax+rax+00h]
0x1400d0f54  mov     [r12], rdi
0x1400d0f58  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400d0f5f  jz      short loc_1400D0F83
0x1400d0f61  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0f68  mov     [rsp+98h+var_58], ebx
0x1400d0f6c  mov     [rsp+98h+var_60], rdi
0x1400d0f71  mov     [rsp+98h+var_68], rbp
0x1400d0f76  mov     rcx, [rcx+40h]
0x1400d0f7a  mov     [rsp+98h+var_70], esi
0x1400d0f7e  call    WPP_RECORDER_SF_L_guid_qd
0x1400d0f83  mov     eax, ebx
0x1400d0f85  add     rsp, 58h
0x1400d0f89  pop     r15
0x1400d0f8b  pop     r14
0x1400d0f8d  pop     r13
0x1400d0f8f  pop     r12
0x1400d0f91  pop     rdi
0x1400d0f92  pop     rsi
0x1400d0f93  pop     rbp
0x1400d0f94  pop     rbx
0x1400d0f95  retn
```
