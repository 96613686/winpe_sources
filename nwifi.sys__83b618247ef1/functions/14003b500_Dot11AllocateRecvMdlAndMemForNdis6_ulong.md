# Dot11AllocateRecvMdlAndMemForNdis6(ulong *)

- ea: `0x14003b500`
- end: `0x14003b62b`
- name: `?Dot11AllocateRecvMdlAndMemForNdis6@@YAPEAU_MDL@@PEAK@Z`
- size: `299`
- prototype: `PMDL __stdcall(PULONG BufferSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callees

- `0x14003b500`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b60e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b60e`
- `ntoskrnl!MmSizeOfMdl` at `0x14003b528`
- `ntoskrnl!MmSizeOfMdl` at `0x14003b528`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b589`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b589`
- `ntoskrnl!ExAllocatePool2` at `0x14003b5a1`
- `ntoskrnl!ExAllocatePool2` at `0x14003b5a1`

## pseudocode

```c
PMDL __fastcall Dot11AllocateRecvMdlAndMemForNdis6(PULONG BufferSize)
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
          Pool2 = (char *)ExAllocatePool2(64, v5, 1383363154, v4);
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
    *((_DWORD *)Pool2 + 2) = 1383363154;
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
0x14003b500  push    rbx
0x14003b502  push    rbp
0x14003b503  push    rsi
0x14003b504  push    rdi
0x14003b505  push    r12
0x14003b507  push    r14
0x14003b509  sub     rsp, 28h
0x14003b50d  mov     ebp, [rcx]
0x14003b50f  xor     ebx, ebx
0x14003b511  cmp     ebp, 1F3Bh
0x14003b517  ja      loc_14003B61A
0x14003b51d  mov     r12d, 0FFFh
0x14003b523  mov     edx, ebp; Length
0x14003b525  mov     ecx, r12d; Base
0x14003b528  call    cs:__imp_MmSizeOfMdl
0x14003b52f  nop     dword ptr [rax+rax+00h]
0x14003b534  lea     esi, [rax+7]
0x14003b537  and     esi, 0FFFFFFF8h
0x14003b53a  lea     eax, [rbp+10h]
0x14003b53d  add     eax, esi
0x14003b53f  cmp     eax, 10h
0x14003b542  jb      loc_14003B61A
0x14003b548  lea     ecx, [rbx+40h]
0x14003b54b  cmp     eax, ecx
0x14003b54d  ja      short loc_14003B558
0x14003b54f  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14003b556  jmp     short loc_14003B586
0x14003b558  cmp     eax, 100h
0x14003b55d  ja      short loc_14003B568
0x14003b55f  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003b566  jmp     short loc_14003B586
0x14003b568  cmp     eax, 400h
0x14003b56d  ja      short loc_14003B578
0x14003b56f  lea     rdi, Lookaside
0x14003b576  jmp     short loc_14003B586
0x14003b578  cmp     eax, 800h
0x14003b57d  ja      short loc_14003B597
0x14003b57f  lea     rdi, stru_1400B0180
0x14003b586  mov     rcx, rdi; Lookaside
0x14003b589  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b590  nop     dword ptr [rax+rax+00h]
0x14003b595  jmp     short loc_14003B5AD
0x14003b597  xor     edi, edi
0x14003b599  mov     edx, eax
0x14003b59b  mov     r8d, 52747252h
0x14003b5a1  call    cs:__imp_ExAllocatePool2
0x14003b5a8  nop     dword ptr [rax+rax+00h]
0x14003b5ad  test    rax, rax
0x14003b5b0  jz      short loc_14003B61A
0x14003b5b2  lea     rbx, [rax+10h]
0x14003b5b6  mov     [rax], rdi
0x14003b5b9  mov     dword ptr [rax+8], 52747252h
0x14003b5c0  test    rbx, rbx
0x14003b5c3  jz      short loc_14003B61A
0x14003b5c5  xor     eax, eax
0x14003b5c7  mov     edx, esi
0x14003b5c9  add     rdx, rbx
0x14003b5cc  mov     qword ptr [rbx], 0
0x14003b5d3  mov     r8d, edx
0x14003b5d6  mov     [rbx+0Ah], ax
0x14003b5da  mov     ecx, r8d
0x14003b5dd  mov     [rbx+28h], ebp
0x14003b5e0  and     rcx, r12
0x14003b5e3  and     rdx, 0FFFFFFFFFFFFF000h
0x14003b5ea  add     rcx, r12
0x14003b5ed  mov     [rbx+20h], rdx
0x14003b5f1  add     rcx, rbp
0x14003b5f4  and     r8d, r12d
0x14003b5f7  shr     rcx, 0Ch
0x14003b5fb  add     cx, 6
0x14003b5ff  mov     [rbx+2Ch], r8d
0x14003b603  shl     cx, 3
0x14003b607  mov     [rbx+8], cx
0x14003b60b  mov     rcx, rbx; MemoryDescriptorList
0x14003b60e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003b615  nop     dword ptr [rax+rax+00h]
0x14003b61a  mov     rax, rbx
0x14003b61d  add     rsp, 28h
0x14003b621  pop     r14
0x14003b623  pop     r12
0x14003b625  pop     rdi
0x14003b626  pop     rsi
0x14003b627  pop     rbp
0x14003b628  pop     rbx
0x14003b629  retn
```
