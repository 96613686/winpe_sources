# HsmpFileCacheSetFileSize

- ea: `0x14001c5d4`
- end: `0x14001c72f`
- name: `HsmpFileCacheSetFileSize`
- size: `347`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140070984`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14001c5d4`
- `0x14001c738`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!CcSetFileSizes` at `0x14001c698`
- `ntoskrnl!CcSetFileSizes` at `0x14001c698`

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
      HsmDbgBreakOnStatus(-1073741808);
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
    HsmDbgBreakOnStatus(-1073741808);
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
0x14001c5d4  mov     [rsp+arg_10], rbx
0x14001c5d9  push    rbp
0x14001c5da  push    rsi
0x14001c5db  push    rdi
0x14001c5dc  sub     rsp, 80h
0x14001c5e3  mov     rax, cs:__security_cookie
0x14001c5ea  xor     rax, rsp
0x14001c5ed  mov     [rsp+98h+var_20], rax
0x14001c5f2  mov     rdi, [rcx+18h]
0x14001c5f6  mov     rbx, rdx
0x14001c5f9  mov     rbp, rcx
0x14001c5fc  test    rdi, rdi
0x14001c5ff  jnz     short loc_14001C65A
0x14001c601  mov     ebx, 0C0000010h
0x14001c606  mov     ecx, ebx
0x14001c608  mov     esi, ebx
0x14001c60a  call    HsmDbgBreakOnStatus
0x14001c60f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c616  lea     rax, WPP_GLOBAL_Control
0x14001c61d  cmp     rcx, rax
0x14001c620  jz      loc_14001C70C
0x14001c626  mov     eax, [rcx+2Ch]
0x14001c629  test    al, 8
0x14001c62b  jz      loc_14001C70C
0x14001c631  cmp     byte ptr [rcx+29h], 2
0x14001c635  jb      loc_14001C70C
0x14001c63b  mov     rcx, [rcx+18h]
0x14001c63f  lea     edx, [rdi+6Dh]
0x14001c642  mov     r9, rbp
0x14001c645  mov     [rsp+98h+var_78], ebx
0x14001c649  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c650  call    WPP_SF_qd
0x14001c655  jmp     loc_14001C70C
0x14001c65a  mov     eax, 0D01h
0x14001c65f  cmp     [rdi], ax
0x14001c662  jnz     short loc_14001C6AA
0x14001c664  mov     eax, 138h
0x14001c669  cmp     [rdi+2], ax
0x14001c66d  jnz     short loc_14001C6AA
0x14001c66f  mov     al, [rdi+7]
0x14001c672  and     al, 0F0h
0x14001c674  cmp     al, 10h
0x14001c676  jnz     short loc_14001C6AA
0x14001c678  xor     esi, esi
0x14001c67a  cmp     rbx, [rdi+20h]
0x14001c67e  jle     loc_14001C70C
0x14001c684  lea     rdx, [rsp+98h+FileSizes]; FileSizes
0x14001c689  mov     qword ptr [rsp+98h+FileSizes.AllocationSize], rbx
0x14001c68e  mov     qword ptr [rsp+98h+FileSizes.FileSize], rbx
0x14001c693  mov     qword ptr [rsp+98h+FileSizes.ValidDataLength], rbx
0x14001c698  call    cs:__imp_CcSetFileSizes
0x14001c69f  nop     dword ptr [rax+rax+00h]
0x14001c6a4  mov     [rdi+20h], rbx
0x14001c6a8  jmp     short loc_14001C70C
0x14001c6aa  mov     ebx, 0C0000010h
0x14001c6af  mov     ecx, ebx
0x14001c6b1  mov     esi, ebx
0x14001c6b3  call    HsmDbgBreakOnStatus
0x14001c6b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c6bf  lea     rax, WPP_GLOBAL_Control
0x14001c6c6  cmp     rcx, rax
0x14001c6c9  jz      short loc_14001C70C
0x14001c6cb  mov     eax, [rcx+2Ch]
0x14001c6ce  test    al, 8
0x14001c6d0  jz      short loc_14001C70C
0x14001c6d2  cmp     byte ptr [rcx+29h], 2
0x14001c6d6  jb      short loc_14001C70C
0x14001c6d8  movzx   r10d, byte ptr [rdi+7]
0x14001c6dd  mov     edx, 6Eh ; 'n'
0x14001c6e2  movsx   r8d, word ptr [rdi+2]
0x14001c6e7  movsx   r9d, word ptr [rdi]
0x14001c6eb  mov     rcx, [rcx+18h]
0x14001c6ef  mov     [rsp+98h+var_50], rbp
0x14001c6f4  shr     r10d, 4
0x14001c6f8  mov     [rsp+98h+var_58], r10d
0x14001c6fd  mov     [rsp+98h+var_60], r8d
0x14001c702  mov     [rsp+98h+var_68], r9d
0x14001c707  call    WPP_SF_DDDDDDqd
0x14001c70c  mov     eax, esi
0x14001c70e  mov     rcx, [rsp+98h+var_20]
0x14001c713  xor     rcx, rsp; StackCookie
0x14001c716  call    __security_check_cookie
0x14001c71b  mov     rbx, [rsp+98h+arg_10]
0x14001c723  add     rsp, 80h
0x14001c72a  pop     rdi
0x14001c72b  pop     rsi
0x14001c72c  pop     rbp
0x14001c72d  retn
```
