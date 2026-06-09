# CscEnpEvictpCreateThread

- ea: `0x140024a64`
- end: `0x140024ab8`
- name: `CscEnpEvictpCreateThread`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400140a4`
- `0x14005837c`

## import_xrefs

- `ntoskrnl!PsCreateSystemThread` at `0x140024aa6`
- `ntoskrnl!PsCreateSystemThread` at `0x140024aa6`

## pseudocode

```c
NTSTATUS __fastcall CscEnpEvictpCreateThread(void **a1, KSTART_ROUTINE *a2, void *a3)
{
  struct _OBJECT_ATTRIBUTES v4; // [rsp+40h] [rbp-38h] BYREF

  v4.RootDirectory = 0;
  v4.ObjectName = 0;
  *(_QWORD *)&v4.Length = 48;
  *(_QWORD *)&v4.Attributes = 512;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  return PsCreateSystemThread(a1, 0x1FFFFFu, &v4, 0, 0, a2, a3);
}

```

## disassembly

```asm
0x140024a64  mov     r11, rsp
0x140024a67  sub     rsp, 78h
0x140024a6b  xor     eax, eax
0x140024a6d  mov     [r11-48h], r8
0x140024a71  mov     [r11-50h], rdx
0x140024a75  lea     r8, [r11-38h]; ObjectAttributes
0x140024a79  xorps   xmm0, xmm0
0x140024a7c  mov     [r11-30h], rax
0x140024a80  mov     [r11-28h], rax
0x140024a84  mov     edx, 1FFFFFh; DesiredAccess
0x140024a89  mov     qword ptr [r11-38h], 30h ; '0'
0x140024a91  xor     r9d, r9d; ProcessHandle
0x140024a94  mov     qword ptr [r11-20h], 200h
0x140024a9c  movdqu  [rsp+78h+var_18], xmm0
0x140024aa2  mov     [r11-58h], rax
0x140024aa6  call    cs:__imp_PsCreateSystemThread
0x140024aad  nop     dword ptr [rax+rax+00h]
0x140024ab2  add     rsp, 78h
0x140024ab6  retn
```
