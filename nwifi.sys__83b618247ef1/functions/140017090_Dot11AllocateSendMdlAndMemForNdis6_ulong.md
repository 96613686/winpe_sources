# Dot11AllocateSendMdlAndMemForNdis6(ulong *)

- ea: `0x140017090`
- end: `0x1400171bb`
- name: `?Dot11AllocateSendMdlAndMemForNdis6@@YAPEAU_MDL@@PEAK@Z`
- size: `299`
- prototype: `PMDL __stdcall(PULONG BufferSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140017090`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001719e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001719e`
- `ntoskrnl!MmSizeOfMdl` at `0x1400170b8`
- `ntoskrnl!MmSizeOfMdl` at `0x1400170b8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017119`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140017119`
- `ntoskrnl!ExAllocatePool2` at `0x140017131`
- `ntoskrnl!ExAllocatePool2` at `0x140017131`

## pseudocode

```c
PMDL __fastcall Dot11AllocateSendMdlAndMemForNdis6(PULONG BufferSize)
{
  __int64 v1; // rbp
  struct _MDL *v2; // rbx
  int v3; // esi
  __int64 v4; // r9
  unsigned int v5; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  char *Pool2; // rax

  v1 = *BufferSize;
  v2 = 0;
  if ( (unsigned int)v1 > 0x1F3B )
    return v2;
  v3 = (MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v1) + 7) & 0xFFFFFFF8;
  v5 = v3 + v1 + 16;
  if ( v5 < 0x10 )
    return v2;
  if ( v5 > 0x40 )
  {
    if ( v5 > 0x100 )
    {
      if ( v5 > 0x400 )
      {
        if ( v5 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (char *)ExAllocatePool2(64, v5, 1400140370, v4);
          goto LABEL_13;
        }
        p_WaitListHead = &stru_1400B0180;
      }
      else
      {
        p_WaitListHead = &Lookaside;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    }
  }
  else
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_13:
  if ( Pool2 )
  {
    v2 = (struct _MDL *)(Pool2 + 16);
    *(_QWORD *)Pool2 = p_WaitListHead;
    *((_DWORD *)Pool2 + 2) = 1400140370;
    if ( Pool2 != (char *)-16LL )
    {
      v2->Next = 0;
      *((_WORD *)Pool2 + 13) = 0;
      *((_DWORD *)Pool2 + 14) = v1;
      *((_QWORD *)Pool2 + 6) = (unsigned __int64)&Pool2[v3 + 16] & 0xFFFFFFFFFFFFF000uLL;
      *((_DWORD *)Pool2 + 15) = ((_DWORD)Pool2 + 16 + v3) & 0xFFF;
      *((_WORD *)Pool2 + 12) = 8 * (((v1 + (((int)Pool2 + 16 + v3) & 0xFFFuLL) + 4095) >> 12) + 6);
      MmBuildMdlForNonPagedPool(v2);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140017090  push    rbx
0x140017092  push    rbp
0x140017093  push    rsi
0x140017094  push    rdi
0x140017095  push    r12
0x140017097  push    r14
0x140017099  sub     rsp, 28h
0x14001709d  mov     ebp, [rcx]
0x14001709f  xor     ebx, ebx
0x1400170a1  cmp     ebp, 1F3Bh
0x1400170a7  ja      loc_1400171AA
0x1400170ad  mov     r12d, 0FFFh
0x1400170b3  mov     edx, ebp; Length
0x1400170b5  mov     ecx, r12d; Base
0x1400170b8  call    cs:__imp_MmSizeOfMdl
0x1400170bf  nop     dword ptr [rax+rax+00h]
0x1400170c4  lea     esi, [rax+7]
0x1400170c7  and     esi, 0FFFFFFF8h
0x1400170ca  lea     eax, [rbp+10h]
0x1400170cd  add     eax, esi
0x1400170cf  cmp     eax, 10h
0x1400170d2  jb      loc_1400171AA
0x1400170d8  lea     ecx, [rbx+40h]
0x1400170db  cmp     eax, ecx
0x1400170dd  ja      short loc_1400170E8
0x1400170df  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400170e6  jmp     short loc_140017116
0x1400170e8  cmp     eax, 100h
0x1400170ed  ja      short loc_1400170F8
0x1400170ef  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400170f6  jmp     short loc_140017116
0x1400170f8  cmp     eax, 400h
0x1400170fd  ja      short loc_140017108
0x1400170ff  lea     rdi, Lookaside
0x140017106  jmp     short loc_140017116
0x140017108  cmp     eax, 800h
0x14001710d  ja      short loc_140017127
0x14001710f  lea     rdi, stru_1400B0180
0x140017116  mov     rcx, rdi; Lookaside
0x140017119  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140017120  nop     dword ptr [rax+rax+00h]
0x140017125  jmp     short loc_14001713D
0x140017127  xor     edi, edi
0x140017129  mov     edx, eax
0x14001712b  mov     r8d, 53747252h
0x140017131  call    cs:__imp_ExAllocatePool2
0x140017138  nop     dword ptr [rax+rax+00h]
0x14001713d  test    rax, rax
0x140017140  jz      short loc_1400171AA
0x140017142  lea     rbx, [rax+10h]
0x140017146  mov     [rax], rdi
0x140017149  mov     dword ptr [rax+8], 53747252h
0x140017150  test    rbx, rbx
0x140017153  jz      short loc_1400171AA
0x140017155  xor     eax, eax
0x140017157  mov     edx, esi
0x140017159  add     rdx, rbx
0x14001715c  mov     qword ptr [rbx], 0
0x140017163  mov     r8d, edx
0x140017166  mov     [rbx+0Ah], ax
0x14001716a  mov     ecx, r8d
0x14001716d  mov     [rbx+28h], ebp
0x140017170  and     rcx, r12
0x140017173  and     rdx, 0FFFFFFFFFFFFF000h
0x14001717a  add     rcx, r12
0x14001717d  mov     [rbx+20h], rdx
0x140017181  add     rcx, rbp
0x140017184  and     r8d, r12d
0x140017187  shr     rcx, 0Ch
0x14001718b  add     cx, 6
0x14001718f  mov     [rbx+2Ch], r8d
0x140017193  shl     cx, 3
0x140017197  mov     [rbx+8], cx
0x14001719b  mov     rcx, rbx; MemoryDescriptorList
0x14001719e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400171a5  nop     dword ptr [rax+rax+00h]
0x1400171aa  mov     rax, rbx
0x1400171ad  add     rsp, 28h
0x1400171b1  pop     r14
0x1400171b3  pop     r12
0x1400171b5  pop     rdi
0x1400171b6  pop     rsi
0x1400171b7  pop     rbp
0x1400171b8  pop     rbx
0x1400171b9  retn
```
