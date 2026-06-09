# HsmpFileCacheSetFileSize

- ea: `0x14001c554`
- end: `0x14001c6af`
- name: `HsmpFileCacheSetFileSize`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140070864`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14001c554`
- `0x14001c6b8`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!CcSetFileSizes` at `0x14001c618`
- `ntoskrnl!CcSetFileSizes` at `0x14001c618`

## pseudocode

```c
__int64 __fastcall HsmpFileCacheSetFileSize(struct _FILE_OBJECT *a1, LARGE_INTEGER a2)
{
  LARGE_INTEGER *FsContext; // rdi
  unsigned int v5; // esi
  _CC_FILE_SIZES FileSizes; // [rsp+60h] [rbp-38h] BYREF

  FsContext = (LARGE_INTEGER *)a1->FsContext;
  if ( FsContext )
  {
    if ( LOWORD(FsContext->LowPart) == 3329
      && HIWORD(FsContext->u.LowPart) == 312
      && (HIBYTE(FsContext->QuadPart) & 0xF0) == 0x10 )
    {
      v5 = 0;
      if ( a2.QuadPart > FsContext[4].QuadPart )
      {
        FileSizes.AllocationSize = a2;
        FileSizes.FileSize = a2;
        FileSizes.ValidDataLength = a2;
        CcSetFileSizes(a1, &FileSizes);
        FsContext[4] = a2;
      }
    }
    else
    {
      v5 = -1073741808;
      HsmDbgBreakOnStatus(3221225488LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_DDDDDDqd(
          WPP_GLOBAL_Control->AttachedDevice,
          110,
          SHIWORD(FsContext->u.LowPart),
          SLOWORD(FsContext->QuadPart));
      }
    }
  }
  else
  {
    v5 = -1073741808;
    HsmDbgBreakOnStatus(3221225488LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        109,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        a1,
        -1073741808);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14001c554  mov     [rsp+arg_10], rbx
0x14001c559  push    rbp
0x14001c55a  push    rsi
0x14001c55b  push    rdi
0x14001c55c  sub     rsp, 80h
0x14001c563  mov     rax, cs:__security_cookie
0x14001c56a  xor     rax, rsp
0x14001c56d  mov     [rsp+98h+var_20], rax
0x14001c572  mov     rdi, [rcx+18h]
0x14001c576  mov     rbx, rdx
0x14001c579  mov     rbp, rcx
0x14001c57c  test    rdi, rdi
0x14001c57f  jnz     short loc_14001C5DA
0x14001c581  mov     ebx, 0C0000010h
0x14001c586  mov     ecx, ebx
0x14001c588  mov     esi, ebx
0x14001c58a  call    HsmDbgBreakOnStatus
0x14001c58f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c596  lea     rax, WPP_GLOBAL_Control
0x14001c59d  cmp     rcx, rax
0x14001c5a0  jz      loc_14001C68C
0x14001c5a6  mov     eax, [rcx+2Ch]
0x14001c5a9  test    al, 8
0x14001c5ab  jz      loc_14001C68C
0x14001c5b1  cmp     byte ptr [rcx+29h], 2
0x14001c5b5  jb      loc_14001C68C
0x14001c5bb  mov     rcx, [rcx+18h]
0x14001c5bf  lea     edx, [rdi+6Dh]
0x14001c5c2  mov     r9, rbp
0x14001c5c5  mov     [rsp+98h+var_78], ebx
0x14001c5c9  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c5d0  call    WPP_SF_qd
0x14001c5d5  jmp     loc_14001C68C
0x14001c5da  mov     eax, 0D01h
0x14001c5df  cmp     [rdi], ax
0x14001c5e2  jnz     short loc_14001C62A
0x14001c5e4  mov     eax, 138h
0x14001c5e9  cmp     [rdi+2], ax
0x14001c5ed  jnz     short loc_14001C62A
0x14001c5ef  mov     al, [rdi+7]
0x14001c5f2  and     al, 0F0h
0x14001c5f4  cmp     al, 10h
0x14001c5f6  jnz     short loc_14001C62A
0x14001c5f8  xor     esi, esi
0x14001c5fa  cmp     rbx, [rdi+20h]
0x14001c5fe  jle     loc_14001C68C
0x14001c604  lea     rdx, [rsp+98h+FileSizes]; FileSizes
0x14001c609  mov     qword ptr [rsp+98h+FileSizes.AllocationSize], rbx
0x14001c60e  mov     qword ptr [rsp+98h+FileSizes.FileSize], rbx
0x14001c613  mov     qword ptr [rsp+98h+FileSizes.ValidDataLength], rbx
0x14001c618  call    cs:__imp_CcSetFileSizes
0x14001c61f  nop     dword ptr [rax+rax+00h]
0x14001c624  mov     [rdi+20h], rbx
0x14001c628  jmp     short loc_14001C68C
0x14001c62a  mov     ebx, 0C0000010h
0x14001c62f  mov     ecx, ebx
0x14001c631  mov     esi, ebx
0x14001c633  call    HsmDbgBreakOnStatus
0x14001c638  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c63f  lea     rax, WPP_GLOBAL_Control
0x14001c646  cmp     rcx, rax
0x14001c649  jz      short loc_14001C68C
0x14001c64b  mov     eax, [rcx+2Ch]
0x14001c64e  test    al, 8
0x14001c650  jz      short loc_14001C68C
0x14001c652  cmp     byte ptr [rcx+29h], 2
0x14001c656  jb      short loc_14001C68C
0x14001c658  movzx   r10d, byte ptr [rdi+7]
0x14001c65d  mov     edx, 6Eh ; 'n'
0x14001c662  movsx   r8d, word ptr [rdi+2]
0x14001c667  movsx   r9d, word ptr [rdi]
0x14001c66b  mov     rcx, [rcx+18h]
0x14001c66f  mov     [rsp+98h+var_50], rbp
0x14001c674  shr     r10d, 4
0x14001c678  mov     [rsp+98h+var_58], r10d
0x14001c67d  mov     [rsp+98h+var_60], r8d
0x14001c682  mov     [rsp+98h+var_68], r9d
0x14001c687  call    WPP_SF_DDDDDDqd
0x14001c68c  mov     eax, esi
0x14001c68e  mov     rcx, [rsp+98h+var_20]
0x14001c693  xor     rcx, rsp; StackCookie
0x14001c696  call    __security_check_cookie
0x14001c69b  mov     rbx, [rsp+98h+arg_10]
0x14001c6a3  add     rsp, 80h
0x14001c6aa  pop     rdi
0x14001c6ab  pop     rsi
0x14001c6ac  pop     rbp
0x14001c6ad  retn
```
