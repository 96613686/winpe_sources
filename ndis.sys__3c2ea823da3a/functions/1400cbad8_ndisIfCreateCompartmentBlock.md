# ndisIfCreateCompartmentBlock

- ea: `0x1400cbad8`
- end: `0x1400cbde7`
- name: `ndisIfCreateCompartmentBlock`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400cafe8`
- `0x1400cb648`

## callees

- `0x1400cbad8`
- `0x1400cc49c`
- `0x1400cca5c`
- `0x1400ccb50`
- `0x1400ccd18`
- `0x1400ccedc`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400cbd69`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cbd69`
- `ntoskrnl!ExAllocatePool2` at `0x1400cbb3a`
- `ntoskrnl!ExAllocatePool2` at `0x1400cbb3a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cbccf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cbd58`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cbd98`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cbccf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cbd58`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400cbd98`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cbc31`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400cbc31`
- `ntoskrnl!ExUuidCreate` at `0x1400cbbd8`
- `ntoskrnl!ExUuidCreate` at `0x1400cbbd8`

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
      v24 = qword_14011C9D8;
      v25 = &qword_14011C9D8;
      while ( 1 )
      {
        if ( v24 == (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_14011C9D8 )
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
          _InterlockedIncrement(&dword_14011D644);
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
0x1400cbad8  push    rbx
0x1400cbada  push    rbp
0x1400cbadb  push    rsi
0x1400cbadc  push    rdi
0x1400cbadd  push    r12
0x1400cbadf  push    r13
0x1400cbae1  push    r14
0x1400cbae3  push    r15
0x1400cbae5  sub     rsp, 58h
0x1400cbae9  mov     r12, r9
0x1400cbaec  mov     r14, r8
0x1400cbaef  mov     rbp, rdx
0x1400cbaf2  mov     esi, ecx
0x1400cbaf4  lea     r13, WPP_RECORDER_INITIALIZED
0x1400cbafb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400cbb02  jz      short loc_1400CBB22
0x1400cbb04  mov     [rsp+98h+var_60], r8
0x1400cbb09  mov     [rsp+98h+var_68], rdx
0x1400cbb0e  mov     [rsp+98h+var_70], ecx
0x1400cbb12  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbb19  mov     rcx, [rcx+40h]
0x1400cbb1d  call    WPP_RECORDER_SF_L_guid_q
0x1400cbb22  mov     edx, 6E8h
0x1400cbb27  mov     qword ptr [r12], 0
0x1400cbb2f  mov     ecx, 40h ; '@'
0x1400cbb34  mov     r8d, 6669444Eh
0x1400cbb3a  call    cs:__imp_ExAllocatePool2
0x1400cbb41  nop     dword ptr [rax+rax+00h]
0x1400cbb46  mov     rdi, rax
0x1400cbb49  test    rax, rax
0x1400cbb4c  jnz     short loc_1400CBB80
0x1400cbb4e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400cbb55  jz      short loc_1400CBB76
0x1400cbb57  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbb5e  lea     r9d, [rax+0Eh]
0x1400cbb62  mov     [rsp+98h+var_68], rbp
0x1400cbb67  mov     dl, 2
0x1400cbb69  mov     [rsp+98h+var_70], esi
0x1400cbb6d  mov     rcx, [rcx+40h]
0x1400cbb71  call    WPP_RECORDER_SF_l_guid_
0x1400cbb76  mov     ebx, 0C000009Ah
0x1400cbb7b  jmp     loc_1400CBDA8
0x1400cbb80  mov     [rax+10h], esi
0x1400cbb83  add     rax, 18h
0x1400cbb87  mov     qword ptr [rdi+2Ch], 1
0x1400cbb8f  mov     dword ptr [rdi+28h], 8
0x1400cbb96  mov     [rax+8], rax
0x1400cbb9a  mov     [rax], rax
0x1400cbb9d  lea     rax, [rdi+6C0h]
0x1400cbba4  mov     [rax+8], rax
0x1400cbba8  mov     [rax], rax
0x1400cbbab  test    r14, r14
0x1400cbbae  jz      short loc_1400CBBD4
0x1400cbbb0  movzx   eax, word ptr [r14+2]
0x1400cbbb5  xor     ebx, ebx
0x1400cbbb7  mov     r8d, 668h
0x1400cbbbd  cmp     ax, r8w
0x1400cbbc1  jnb     short loc_1400CBBC6
0x1400cbbc3  mov     r8d, eax; Size
0x1400cbbc6  lea     rcx, [rdi+40h]; void *
0x1400cbbca  mov     rdx, r14; Src
0x1400cbbcd  call    memmove
0x1400cbbd2  jmp     short loc_1400CBC2A
0x1400cbbd4  lea     rcx, [rdi+50h]; Uuid
0x1400cbbd8  call    cs:__imp_ExUuidCreate
0x1400cbbdf  nop     dword ptr [rax+rax+00h]
0x1400cbbe4  mov     ebx, eax
0x1400cbbe6  test    eax, eax
0x1400cbbe8  jns     short loc_1400CBC1F
0x1400cbbea  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400cbbf1  jz      loc_1400CBD64
0x1400cbbf7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbbfe  mov     r9d, 0Fh
0x1400cbc04  mov     dword ptr [rsp+98h+var_60], eax
0x1400cbc08  mov     [rsp+98h+var_68], rbp
0x1400cbc0d  mov     [rsp+98h+var_70], esi
0x1400cbc11  mov     rcx, [rcx+40h]
0x1400cbc15  call    WPP_RECORDER_SF_l_guid_d
0x1400cbc1a  jmp     loc_1400CBD64
0x1400cbc1f  xor     eax, eax
0x1400cbc21  cmp     ebx, 40020056h
0x1400cbc27  cmovz   ebx, eax
0x1400cbc2a  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400cbc31  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400cbc38  nop     dword ptr [rax+rax+00h]
0x1400cbc3d  mov     r15b, al
0x1400cbc40  test    rbp, rbp
0x1400cbc43  jz      short loc_1400CBCC1
0x1400cbc45  mov     rcx, rbp; struct _GUID *
0x1400cbc48  call    ?ndisIfFindAvailableCompartmentId@@YAIPEBU_GUID@@@Z; ndisIfFindAvailableCompartmentId(_GUID const *)
0x1400cbc4d  mov     r14d, eax
0x1400cbc50  test    eax, eax
0x1400cbc52  jnz     short loc_1400CBC83
0x1400cbc54  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400cbc5b  jz      short loc_1400CBC7C
0x1400cbc5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbc64  lea     r9d, [rax+10h]
0x1400cbc68  mov     [rsp+98h+var_68], rbp
0x1400cbc6d  mov     dl, 2
0x1400cbc6f  mov     [rsp+98h+var_70], esi
0x1400cbc73  mov     rcx, [rcx+40h]
0x1400cbc77  call    WPP_RECORDER_SF_l_guid_
0x1400cbc7c  mov     ebx, 0C000022Ah
0x1400cbc81  jmp     short loc_1400CBCC5
0x1400cbc83  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400cbc8a  jz      short loc_1400CBCAE
0x1400cbc8c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbc93  mov     r9d, 11h
0x1400cbc99  mov     [rsp+98h+var_68], rbp
0x1400cbc9e  mov     dl, 4
0x1400cbca0  mov     [rsp+98h+var_70], r14d
0x1400cbca5  mov     rcx, [rcx+40h]
0x1400cbca9  call    WPP_RECORDER_SF_l_guid_
0x1400cbcae  movups  xmm0, xmmword ptr [rbp+0]
0x1400cbcb2  mov     esi, r14d
0x1400cbcb5  mov     [rdi+10h], r14d
0x1400cbcb9  movdqu  xmmword ptr [rdi+478h], xmm0
0x1400cbcc1  test    ebx, ebx
0x1400cbcc3  jz      short loc_1400CBCE8
0x1400cbcc5  mov     dl, r15b; NewIrql
0x1400cbcc8  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400cbccf  call    cs:__imp_KeReleaseSpinLock
0x1400cbcd6  nop     dword ptr [rax+rax+00h]
0x1400cbcdb  test    ebx, ebx
0x1400cbcdd  js      loc_1400CBD64
0x1400cbce3  jmp     loc_1400CBDA4
0x1400cbce8  mov     rax, cs:qword_14011C9D8
0x1400cbcef  lea     rdx, qword_14011C9D8
0x1400cbcf6  jmp     short loc_1400CBD02
0x1400cbcf8  cmp     [rax+10h], esi
0x1400cbcfb  jz      short loc_1400CBD1F
0x1400cbcfd  ja      short loc_1400CBD07
0x1400cbcff  mov     rax, [rax]
0x1400cbd02  cmp     rax, rdx
0x1400cbd05  jnz     short loc_1400CBCF8
0x1400cbd07  lock inc dword ptr [rdi+2Ch]
0x1400cbd0b  mov     rcx, [rax+8]
0x1400cbd0f  mov     rax, [rcx]
0x1400cbd12  cmp     [rax+8], rcx
0x1400cbd16  jz      short loc_1400CBD79
0x1400cbd18  mov     ecx, 3
0x1400cbd1d  int     29h; Win8: RtlFailFast(ecx)
0x1400cbd1f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400cbd26  jz      short loc_1400CBD49
0x1400cbd28  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbd2f  mov     r9d, 12h
0x1400cbd35  mov     [rsp+98h+var_68], rbp
0x1400cbd3a  mov     dl, 2
0x1400cbd3c  mov     [rsp+98h+var_70], esi
0x1400cbd40  mov     rcx, [rcx+40h]
0x1400cbd44  call    WPP_RECORDER_SF_l_guid_
0x1400cbd49  mov     dl, r15b; NewIrql
0x1400cbd4c  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400cbd53  mov     ebx, 0C000022Ah
0x1400cbd58  call    cs:__imp_KeReleaseSpinLock
0x1400cbd5f  nop     dword ptr [rax+rax+00h]
0x1400cbd64  xor     edx, edx; Tag
0x1400cbd66  mov     rcx, rdi; P
0x1400cbd69  call    cs:__imp_ExFreePoolWithTag
0x1400cbd70  nop     dword ptr [rax+rax+00h]
0x1400cbd75  xor     edi, edi
0x1400cbd77  jmp     short loc_1400CBDA8
0x1400cbd79  mov     [rdi], rax
0x1400cbd7c  mov     [rdi+8], rcx
0x1400cbd80  mov     [rax+8], rdi
0x1400cbd84  mov     [rcx], rdi
0x1400cbd87  lock inc cs:dword_14011D644
0x1400cbd8e  mov     dl, r15b; NewIrql
0x1400cbd91  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400cbd98  call    cs:__imp_KeReleaseSpinLock
0x1400cbd9f  nop     dword ptr [rax+rax+00h]
0x1400cbda4  mov     [r12], rdi
0x1400cbda8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400cbdaf  jz      short loc_1400CBDD3
0x1400cbdb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cbdb8  mov     [rsp+98h+var_58], ebx
0x1400cbdbc  mov     [rsp+98h+var_60], rdi
0x1400cbdc1  mov     [rsp+98h+var_68], rbp
0x1400cbdc6  mov     rcx, [rcx+40h]
0x1400cbdca  mov     [rsp+98h+var_70], esi
0x1400cbdce  call    WPP_RECORDER_SF_L_guid_qd
0x1400cbdd3  mov     eax, ebx
0x1400cbdd5  add     rsp, 58h
0x1400cbdd9  pop     r15
0x1400cbddb  pop     r14
0x1400cbddd  pop     r13
0x1400cbddf  pop     r12
0x1400cbde1  pop     rdi
0x1400cbde2  pop     rsi
0x1400cbde3  pop     rbp
0x1400cbde4  pop     rbx
0x1400cbde5  retn
```
