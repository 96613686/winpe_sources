# Smb2Negotiate_Receive

- ea: `0x140022ac0`
- end: `0x140022bfe`
- name: `Smb2Negotiate_Receive`
- size: `318`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, size_t Size, _DWORD *, void *Src)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140022ac0`
- `0x14002cb78`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140022b46`
- `ntoskrnl!ExAllocatePool2` at `0x140022b46`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140022bb3`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140022bb3`
- `rdbss!RxAllocateMdl2` at `0x140022b98`
- `rdbss!RxAllocateMdl2` at `0x140022b98`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140022bdc`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x140022bdc`

## pseudocode

```c
__int64 __fastcall Smb2Negotiate_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        size_t Size,
        _DWORD *a6,
        void *Src)
{
  unsigned int v7; // ebx
  unsigned int v10; // ebp
  int v11; // esi
  void *Pool2; // rax
  struct _MDL *Mdl2; // rax

  v7 = *(_DWORD *)(a3 + 16);
  if ( v7 )
  {
    v10 = 0;
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x8000) != 0 )
      McTemplateK0qqhzr2_EtwWriteTransfer(
        *(_WORD *)(*(_QWORD *)(a1 + 72) + 80LL) >> 1,
        (unsigned int)NegotiateFailure,
        a3,
        0,
        v7,
        *(_WORD *)(*(_QWORD *)(a1 + 72) + 80LL) >> 1,
        *(_QWORD *)(*(_QWORD *)(a1 + 72) + 88LL));
    v11 = Size;
  }
  else
  {
    v11 = Size;
    *(_DWORD *)(a2 + 748) = Size;
    Pool2 = (void *)ExAllocatePool2(66, (unsigned int)Size, 1834182478);
    *(_QWORD *)(a2 + 712) = Pool2;
    if ( Pool2 )
    {
      if ( (unsigned int)Size <= a4 )
      {
        memmove(Pool2, Src, (unsigned int)Size);
        v10 = 0;
        goto LABEL_11;
      }
      Mdl2 = (struct _MDL *)RxAllocateMdl2(Pool2, *(unsigned int *)(a2 + 748), 0, 0, 0);
      *(_QWORD *)(a2 + 720) = Mdl2;
      if ( Mdl2 )
      {
        MmBuildMdlForNonPagedPool(Mdl2);
        v11 = 0;
        v10 = -1073741802;
        goto LABEL_11;
      }
    }
    v10 = 0;
    v7 = -1073741670;
  }
LABEL_11:
  *a6 = v11;
  SmbCseUpdateBufferContextStatus(a2, v7);
  return v10;
}

```

## disassembly

```asm
0x140022ac0  mov     [rsp+arg_8], rbx
0x140022ac5  mov     [rsp+arg_10], rbp
0x140022aca  push    rsi
0x140022acb  push    rdi
0x140022acc  push    r14
0x140022ace  sub     rsp, 40h
0x140022ad2  mov     ebx, [r8+10h]
0x140022ad6  mov     r14d, r9d
0x140022ad9  mov     [rsp+58h+arg_0], 0
0x140022ae2  mov     rdi, rdx
0x140022ae5  test    ebx, ebx
0x140022ae7  jz      short loc_140022B2C
0x140022ae9  xor     ebp, ebp
0x140022aeb  cmp     byte ptr cs:WPP_MAIN_CB.Queue+11h, bpl
0x140022af2  jge     short loc_140022B20
0x140022af4  mov     rax, [rcx+48h]
0x140022af8  lea     rdx, NegotiateFailure
0x140022aff  xor     r9d, r9d
0x140022b02  movzx   ecx, word ptr [rax+50h]
0x140022b06  mov     rax, [rax+58h]
0x140022b0a  mov     [rsp+58h+var_28], rax
0x140022b0f  shr     cx, 1
0x140022b12  mov     [rsp+58h+var_30], cx
0x140022b17  mov     dword ptr [rsp+58h+var_38], ebx
0x140022b1b  call    McTemplateK0qqhzr2_EtwWriteTransfer
0x140022b20  mov     esi, dword ptr [rsp+58h+Size]
0x140022b27  jmp     loc_140022BC6
0x140022b2c  mov     esi, dword ptr [rsp+58h+Size]
0x140022b33  mov     r8d, 6D53674Eh
0x140022b39  mov     [rdx+2ECh], esi
0x140022b3f  mov     ecx, 42h ; 'B'
0x140022b44  mov     edx, esi
0x140022b46  call    cs:__imp_ExAllocatePool2
0x140022b4d  nop     dword ptr [rax+rax+00h]
0x140022b52  mov     [rdi+2C8h], rax
0x140022b59  test    rax, rax
0x140022b5c  jnz     short loc_140022B67
0x140022b5e  xor     ebp, ebp
0x140022b60  mov     ebx, 0C000009Ah
0x140022b65  jmp     short loc_140022BC6
0x140022b67  mov     rcx, rax; void *
0x140022b6a  cmp     esi, r14d
0x140022b6d  ja      short loc_140022B83
0x140022b6f  mov     rdx, [rsp+58h+Src]; Src
0x140022b77  mov     r8, rsi; Size
0x140022b7a  call    memmove
0x140022b7f  xor     ebp, ebp
0x140022b81  jmp     short loc_140022BC6
0x140022b83  mov     edx, [rdi+2ECh]
0x140022b89  xor     r9d, r9d
0x140022b8c  xor     r8d, r8d
0x140022b8f  mov     [rsp+58h+var_38], 0
0x140022b98  call    cs:__imp_RxAllocateMdl2
0x140022b9f  nop     dword ptr [rax+rax+00h]
0x140022ba4  mov     [rdi+2D0h], rax
0x140022bab  test    rax, rax
0x140022bae  jz      short loc_140022B5E
0x140022bb0  mov     rcx, rax; MemoryDescriptorList
0x140022bb3  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140022bba  nop     dword ptr [rax+rax+00h]
0x140022bbf  xor     esi, esi
0x140022bc1  mov     ebp, 0C0000016h
0x140022bc6  mov     rcx, [rsp+58h+arg_28]
0x140022bce  mov     dword ptr [rsp+58h+arg_0], ebx
0x140022bd2  mov     rdx, [rsp+58h+arg_0]
0x140022bd7  mov     [rcx], esi
0x140022bd9  mov     rcx, rdi
0x140022bdc  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x140022be3  nop     dword ptr [rax+rax+00h]
0x140022be8  mov     rbx, [rsp+58h+arg_8]
0x140022bed  mov     eax, ebp
0x140022bef  mov     rbp, [rsp+58h+arg_10]
0x140022bf4  add     rsp, 40h
0x140022bf8  pop     r14
0x140022bfa  pop     rdi
0x140022bfb  pop     rsi
0x140022bfc  retn
```
