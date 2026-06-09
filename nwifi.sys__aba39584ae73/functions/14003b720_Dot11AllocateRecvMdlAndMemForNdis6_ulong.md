# Dot11AllocateRecvMdlAndMemForNdis6(ulong *)

- ea: `0x14003b720`
- end: `0x14003b84b`
- name: `?Dot11AllocateRecvMdlAndMemForNdis6@@YAPEAU_MDL@@PEAK@Z`
- size: `299`
- prototype: `PMDL __stdcall(PULONG BufferSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callees

- `0x14003b720`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b82e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b82e`
- `ntoskrnl!MmSizeOfMdl` at `0x14003b748`
- `ntoskrnl!MmSizeOfMdl` at `0x14003b748`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b7a9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b7a9`
- `ntoskrnl!ExAllocatePool2` at `0x14003b7c1`
- `ntoskrnl!ExAllocatePool2` at `0x14003b7c1`

## pseudocode

```c
PMDL __fastcall Dot11AllocateRecvMdlAndMemForNdis6(PULONG BufferSize)
{
  __int64 v1; // rbp
  struct _MDL *v2; // rbx
  int v3; // esi
  unsigned int v4; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rdi
  char *Pool2; // rax

  v1 = *BufferSize;
  v2 = 0;
  if ( (unsigned int)v1 > 0x1F3B )
    return v2;
  v3 = (MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v1) + 7) & 0xFFFFFFF8;
  v4 = v3 + v1 + 16;
  if ( v4 < 0x10 )
    return v2;
  if ( v4 > 0x40 )
  {
    if ( v4 > 0x100 )
    {
      if ( v4 > 0x400 )
      {
        if ( v4 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (char *)ExAllocatePool2(64, v4, 1383363154);
          goto LABEL_13;
        }
        p_WaitListHead = &stru_1400B31C0;
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
0x14003b720  push    rbx
0x14003b722  push    rbp
0x14003b723  push    rsi
0x14003b724  push    rdi
0x14003b725  push    r12
0x14003b727  push    r14
0x14003b729  sub     rsp, 28h
0x14003b72d  mov     ebp, [rcx]
0x14003b72f  xor     ebx, ebx
0x14003b731  cmp     ebp, 1F3Bh
0x14003b737  ja      loc_14003B83A
0x14003b73d  mov     r12d, 0FFFh
0x14003b743  mov     edx, ebp; Length
0x14003b745  mov     ecx, r12d; Base
0x14003b748  call    cs:__imp_MmSizeOfMdl
0x14003b74f  nop     dword ptr [rax+rax+00h]
0x14003b754  lea     esi, [rax+7]
0x14003b757  and     esi, 0FFFFFFF8h
0x14003b75a  lea     eax, [rbp+10h]
0x14003b75d  add     eax, esi
0x14003b75f  cmp     eax, 10h
0x14003b762  jb      loc_14003B83A
0x14003b768  lea     ecx, [rbx+40h]
0x14003b76b  cmp     eax, ecx
0x14003b76d  ja      short loc_14003B778
0x14003b76f  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x14003b776  jmp     short loc_14003B7A6
0x14003b778  cmp     eax, 100h
0x14003b77d  ja      short loc_14003B788
0x14003b77f  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003b786  jmp     short loc_14003B7A6
0x14003b788  cmp     eax, 400h
0x14003b78d  ja      short loc_14003B798
0x14003b78f  lea     rdi, Lookaside
0x14003b796  jmp     short loc_14003B7A6
0x14003b798  cmp     eax, 800h
0x14003b79d  ja      short loc_14003B7B7
0x14003b79f  lea     rdi, stru_1400B31C0
0x14003b7a6  mov     rcx, rdi; Lookaside
0x14003b7a9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b7b0  nop     dword ptr [rax+rax+00h]
0x14003b7b5  jmp     short loc_14003B7CD
0x14003b7b7  xor     edi, edi
0x14003b7b9  mov     edx, eax
0x14003b7bb  mov     r8d, 52747252h
0x14003b7c1  call    cs:__imp_ExAllocatePool2
0x14003b7c8  nop     dword ptr [rax+rax+00h]
0x14003b7cd  test    rax, rax
0x14003b7d0  jz      short loc_14003B83A
0x14003b7d2  lea     rbx, [rax+10h]
0x14003b7d6  mov     [rax], rdi
0x14003b7d9  mov     dword ptr [rax+8], 52747252h
0x14003b7e0  test    rbx, rbx
0x14003b7e3  jz      short loc_14003B83A
0x14003b7e5  xor     eax, eax
0x14003b7e7  mov     edx, esi
0x14003b7e9  add     rdx, rbx
0x14003b7ec  mov     qword ptr [rbx], 0
0x14003b7f3  mov     r8d, edx
0x14003b7f6  mov     [rbx+0Ah], ax
0x14003b7fa  mov     ecx, r8d
0x14003b7fd  mov     [rbx+28h], ebp
0x14003b800  and     rcx, r12
0x14003b803  and     rdx, 0FFFFFFFFFFFFF000h
0x14003b80a  add     rcx, r12
0x14003b80d  mov     [rbx+20h], rdx
0x14003b811  add     rcx, rbp
0x14003b814  and     r8d, r12d
0x14003b817  shr     rcx, 0Ch
0x14003b81b  add     cx, 6
0x14003b81f  mov     [rbx+2Ch], r8d
0x14003b823  shl     cx, 3
0x14003b827  mov     [rbx+8], cx
0x14003b82b  mov     rcx, rbx; MemoryDescriptorList
0x14003b82e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003b835  nop     dword ptr [rax+rax+00h]
0x14003b83a  mov     rax, rbx
0x14003b83d  add     rsp, 28h
0x14003b841  pop     r14
0x14003b843  pop     r12
0x14003b845  pop     rdi
0x14003b846  pop     rsi
0x14003b847  pop     rbp
0x14003b848  pop     rbx
0x14003b849  retn
```
