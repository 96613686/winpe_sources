# UxSslStartSenderModule

- ea: `0x14013ab70`
- end: `0x14013ad3c`
- name: `UxSslStartSenderModule`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14013ab70`
- `0x1401c3f58`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14013ac3e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14013acda`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14013ac3e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14013acda`
- `ntoskrnl!MmSizeOfMdl` at `0x14013aba8`
- `ntoskrnl!MmSizeOfMdl` at `0x14013ac50`
- `ntoskrnl!MmSizeOfMdl` at `0x14013aba8`
- `ntoskrnl!MmSizeOfMdl` at `0x14013ac50`
- `ntoskrnl!ExAllocatePool3` at `0x14013abd6`
- `ntoskrnl!ExAllocatePool3` at `0x14013ac79`
- `ntoskrnl!ExAllocatePool3` at `0x14013abd6`
- `ntoskrnl!ExAllocatePool3` at `0x14013ac79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013acfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013acfb`

## pseudocode

```c
__int64 UxSslStartSenderModule()
{
  unsigned int v0; // ebx
  struct _MDL *Pool3; // rax
  struct _MDL *v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned int v4; // ebp
  struct _MDL *v5; // rax
  struct _MDL *v6; // rdi
  unsigned int v7; // ebx
  unsigned __int64 v8; // rdx

  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_(1041, 10, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids);
  v0 = (MmSizeOfMdl((PVOID)0xFFF, 2u) + 7) & 0xFFFFFFF8;
  Pool3 = (struct _MDL *)ExAllocatePool3(66, v0 + 2, 1129543765, UxLowPriorityPool, 1);
  v2 = Pool3;
  if ( Pool3 )
  {
    v3 = (unsigned __int64)Pool3 + v0;
    *(_WORD *)v3 = 1;
    Pool3->Next = 0;
    Pool3->ByteCount = 2;
    Pool3->Size = 8 * (((unsigned __int16)((((_WORD)Pool3 + v0) & 0xFFF) + 4097) >> 12) + 6);
    Pool3->MdlFlags = 0;
    Pool3->ByteOffset = v3 & 0xFFF;
    Pool3->StartVa = (PVOID)(v3 & 0xFFFFFFFFFFFFF000uLL);
    MmBuildMdlForNonPagedPool(Pool3);
    v4 = (MmSizeOfMdl((PVOID)0xFFF, 4u) + 7) & 0xFFFFFFF8;
    v5 = (struct _MDL *)ExAllocatePool3(66, v4 + 4, 1213429845, UxLowPriorityPool, 1);
    v6 = v5;
    if ( v5 )
    {
      v7 = 0;
      v8 = (unsigned __int64)v5 + v4;
      *(_DWORD *)v8 = 0;
      v5->Next = 0;
      v5->ByteCount = 4;
      v5->MdlFlags = 0;
      v5->Size = 8 * (((unsigned __int16)((((_WORD)v5 + v4) & 0xFFF) + 4099) >> 12) + 6);
      v5->StartVa = (PVOID)(v8 & 0xFFFFFFFFFFFFF000uLL);
      v5->ByteOffset = v8 & 0xFFF;
      MmBuildMdlForNonPagedPool(v5);
      UxSslCloseNotifyMdl = v2;
      UxSslHelloRequestMdl = v6;
      goto LABEL_8;
    }
    ExFreePoolWithTag(v2, 0);
  }
  v7 = -1073741670;
LABEL_8:
  if ( (BYTE2(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1041, 11, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x14013ab70  push    rbx
0x14013ab72  push    rbp
0x14013ab73  push    rsi
0x14013ab74  push    rdi
0x14013ab75  push    r13
0x14013ab77  sub     rsp, 30h
0x14013ab7b  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14013ab82  jz      short loc_14013AB9A
0x14013ab84  mov     edx, 0Ah
0x14013ab89  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14013ab90  mov     ecx, 411h
0x14013ab95  call    WPP_SF_
0x14013ab9a  mov     r13d, 0FFFh
0x14013aba0  mov     edx, 2; Length
0x14013aba5  mov     ecx, r13d; Base
0x14013aba8  call    cs:__imp_MmSizeOfMdl
0x14013abaf  nop     dword ptr [rax+rax+00h]
0x14013abb4  mov     edi, 1
0x14013abb9  lea     r9, UxLowPriorityPool
0x14013abc0  mov     r8d, 43537855h
0x14013abc6  mov     [rsp+58h+var_38], edi
0x14013abca  lea     ebx, [rax+7]
0x14013abcd  and     ebx, 0FFFFFFF8h
0x14013abd0  lea     ecx, [rdi+41h]
0x14013abd3  lea     edx, [rbx+2]
0x14013abd6  call    cs:__imp_ExAllocatePool3
0x14013abdd  nop     dword ptr [rax+rax+00h]
0x14013abe2  mov     rsi, rax
0x14013abe5  test    rax, rax
0x14013abe8  jz      loc_14013AD07
0x14013abee  lea     edx, [r13+2]
0x14013abf2  mov     ecx, ebx
0x14013abf4  add     rcx, rax
0x14013abf7  mov     [rcx], di
0x14013abfa  mov     qword ptr [rax], 0
0x14013ac01  movzx   eax, cx
0x14013ac04  and     ax, r13w
0x14013ac08  mov     dword ptr [rsi+28h], 2
0x14013ac0f  add     ax, dx
0x14013ac12  shr     ax, 0Ch
0x14013ac16  add     ax, 6
0x14013ac1a  shl     ax, 3
0x14013ac1e  mov     [rsi+8], ax
0x14013ac22  xor     eax, eax
0x14013ac24  mov     [rsi+0Ah], ax
0x14013ac28  mov     rax, rcx
0x14013ac2b  and     ecx, r13d
0x14013ac2e  and     rax, 0FFFFFFFFFFFFF000h
0x14013ac34  mov     [rsi+2Ch], ecx
0x14013ac37  mov     rcx, rsi; MemoryDescriptorList
0x14013ac3a  mov     [rsi+20h], rax
0x14013ac3e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14013ac45  nop     dword ptr [rax+rax+00h]
0x14013ac4a  lea     edx, [rdi+3]; Length
0x14013ac4d  mov     ecx, r13d; Base
0x14013ac50  call    cs:__imp_MmSizeOfMdl
0x14013ac57  nop     dword ptr [rax+rax+00h]
0x14013ac5c  lea     r9, UxLowPriorityPool
0x14013ac63  mov     [rsp+58h+var_38], edi
0x14013ac67  lea     ecx, [rdi+41h]
0x14013ac6a  mov     r8d, 48537855h
0x14013ac70  lea     ebp, [rax+7]
0x14013ac73  and     ebp, 0FFFFFFF8h
0x14013ac76  lea     edx, [rbp+4]
0x14013ac79  call    cs:__imp_ExAllocatePool3
0x14013ac80  nop     dword ptr [rax+rax+00h]
0x14013ac85  mov     rdi, rax
0x14013ac88  test    rax, rax
0x14013ac8b  jz      short loc_14013ACF6
0x14013ac8d  xor     ebx, ebx
0x14013ac8f  mov     edx, ebp
0x14013ac91  add     rdx, rax
0x14013ac94  movzx   ecx, dx
0x14013ac97  and     cx, r13w
0x14013ac9b  mov     [rdx], ebx
0x14013ac9d  mov     [rax], rbx
0x14013aca0  lea     eax, [r13+4]
0x14013aca4  add     cx, ax
0x14013aca7  mov     dword ptr [rdi+28h], 4
0x14013acae  shr     cx, 0Ch
0x14013acb2  xor     eax, eax
0x14013acb4  add     cx, 6
0x14013acb8  mov     [rdi+0Ah], ax
0x14013acbc  shl     cx, 3
0x14013acc0  mov     rax, rdx
0x14013acc3  mov     [rdi+8], cx
0x14013acc7  and     rax, 0FFFFFFFFFFFFF000h
0x14013accd  and     edx, r13d
0x14013acd0  mov     [rdi+20h], rax
0x14013acd4  mov     rcx, rdi; MemoryDescriptorList
0x14013acd7  mov     [rdi+2Ch], edx
0x14013acda  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14013ace1  nop     dword ptr [rax+rax+00h]
0x14013ace6  mov     cs:UxSslCloseNotifyMdl, rsi
0x14013aced  mov     cs:UxSslHelloRequestMdl, rdi
0x14013acf4  jmp     short loc_14013AD0C
0x14013acf6  xor     edx, edx; Tag
0x14013acf8  mov     rcx, rsi; P
0x14013acfb  call    cs:__imp_ExFreePoolWithTag
0x14013ad02  nop     dword ptr [rax+rax+00h]
0x14013ad07  mov     ebx, 0C000009Ah
0x14013ad0c  test    byte ptr cs:xmmword_1401A2CA0+2, 2
0x14013ad13  jz      short loc_14013AD2E
0x14013ad15  mov     edx, 0Bh
0x14013ad1a  lea     r8, WPP_d5f4526382113844ae5de18c9e74c0dd_Traceguids
0x14013ad21  mov     ecx, 411h
0x14013ad26  mov     r9d, ebx
0x14013ad29  call    WPP_SF_d
0x14013ad2e  mov     eax, ebx
0x14013ad30  add     rsp, 30h
0x14013ad34  pop     r13
0x14013ad36  pop     rdi
0x14013ad37  pop     rsi
0x14013ad38  pop     rbp
0x14013ad39  pop     rbx
0x14013ad3a  retn
```
