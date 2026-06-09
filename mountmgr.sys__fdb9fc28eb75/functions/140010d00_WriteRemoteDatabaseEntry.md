# WriteRemoteDatabaseEntry

- ea: `0x140010d00`
- end: `0x140010e6a`
- name: `WriteRemoteDatabaseEntry`
- size: `362`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000e340`
- `0x14000ecbc`
- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140010d00`
- `0x140012df0`

## import_xrefs

- `ntoskrnl!ZwWriteFile` at `0x140010d86`
- `ntoskrnl!ZwWriteFile` at `0x140010d86`
- `ntoskrnl!KeReleaseMutex` at `0x140010d45`
- `ntoskrnl!KeReleaseMutex` at `0x140010d45`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010db9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010db9`

## pseudocode

```c
__int64 __fastcall WriteRemoteDatabaseEntry(__int64 a1, void *a2, unsigned int a3, _DWORD *a4)
{
  __int64 v4; // rsi
  __int64 v5; // r15
  __int64 v7; // r14
  NTSTATUS v9; // ebx
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // edi
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+B0h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 152);
  v5 = *(_QWORD *)(a1 + 176);
  IoStatusBlock = 0;
  ByteOffset.QuadPart = a3;
  v7 = *(_QWORD *)(v4 + 336);
  KeReleaseMutex((PRKMUTEX)(v4 + 56), 0);
  v9 = ZwWriteFile(a2, 0, 0, 0, &IoStatusBlock, a4, *a4, &ByteOffset, 0);
  if ( v9 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v16 = 53;
      v17 = (unsigned int)v9;
LABEL_11:
      WPP_SF_L(v15->AttachedDevice, v16, v10, v17);
    }
  }
  else if ( IoStatusBlock.Information < (unsigned int)*a4 )
  {
    v9 = -1073741670;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v16 = 54;
      v17 = 3221225626LL;
      goto LABEL_11;
    }
  }
  KeWaitForSingleObject((PVOID)(v4 + 56), Executive, 0, 0, 0);
  v11 = VerifyEpoch(v4, v7, v5);
  v13 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 55, v12, (unsigned int)v11);
    if ( v9 >= 0 )
      return v13;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140010d00  push    rbx
0x140010d02  push    rbp
0x140010d03  push    rsi
0x140010d04  push    rdi
0x140010d05  push    r12
0x140010d07  push    r13
0x140010d09  push    r14
0x140010d0b  push    r15
0x140010d0d  sub     rsp, 68h
0x140010d11  mov     rsi, [rcx+98h]
0x140010d18  xorps   xmm0, xmm0
0x140010d1b  mov     r15, [rcx+0B0h]
0x140010d22  mov     rbx, rdx
0x140010d25  mov     eax, r8d
0x140010d28  xor     edx, edx; Wait
0x140010d2a  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x140010d2f  mov     qword ptr [rsp+0A8h+arg_0], rax
0x140010d37  lea     rcx, [rsi+38h]; Mutex
0x140010d3b  mov     r14, [rsi+150h]
0x140010d42  mov     rdi, r9
0x140010d45  call    cs:__imp_KeReleaseMutex
0x140010d4c  nop     dword ptr [rax+rax+00h]
0x140010d51  lea     rax, [rsp+0A8h+arg_0]
0x140010d59  xor     r12d, r12d
0x140010d5c  mov     [rsp+0A8h+Key], r12; Key
0x140010d61  xor     r9d, r9d; ApcContext
0x140010d64  mov     [rsp+0A8h+ByteOffset], rax; ByteOffset
0x140010d69  xor     r8d, r8d; ApcRoutine
0x140010d6c  mov     eax, [rdi]
0x140010d6e  xor     edx, edx; Event
0x140010d70  mov     [rsp+0A8h+Length], eax; Length
0x140010d74  mov     rcx, rbx; FileHandle
0x140010d77  lea     rax, [rsp+0A8h+var_58]
0x140010d7c  mov     [rsp+0A8h+Buffer], rdi; Buffer
0x140010d81  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x140010d86  call    cs:__imp_ZwWriteFile
0x140010d8d  nop     dword ptr [rax+rax+00h]
0x140010d92  lea     r13, WPP_GLOBAL_Control
0x140010d99  mov     ebx, eax
0x140010d9b  test    eax, eax
0x140010d9d  js      short loc_140010DED
0x140010d9f  mov     eax, [rdi]
0x140010da1  cmp     [rsp+0A8h+var_58.Information], rax
0x140010da6  jb      short loc_140010E0A
0x140010da8  xor     r9d, r9d; Alertable
0x140010dab  mov     [rsp+0A8h+IoStatusBlock], r12; Timeout
0x140010db0  xor     r8d, r8d; WaitMode
0x140010db3  lea     rcx, [rsi+38h]; Object
0x140010db7  xor     edx, edx; WaitReason
0x140010db9  call    cs:__imp_KeWaitForSingleObject
0x140010dc0  nop     dword ptr [rax+rax+00h]
0x140010dc5  mov     r8, r15
0x140010dc8  mov     rdx, r14
0x140010dcb  mov     rcx, rsi
0x140010dce  call    VerifyEpoch
0x140010dd3  mov     edi, eax
0x140010dd5  test    eax, eax
0x140010dd7  js      short loc_140010E3B
0x140010dd9  mov     eax, ebx
0x140010ddb  add     rsp, 68h
0x140010ddf  pop     r15
0x140010de1  pop     r14
0x140010de3  pop     r13
0x140010de5  pop     r12
0x140010de7  pop     rdi
0x140010de8  pop     rsi
0x140010de9  pop     rbp
0x140010dea  pop     rbx
0x140010deb  retn
0x140010ded  mov     rcx, cs:WPP_GLOBAL_Control
0x140010df4  cmp     rcx, r13
0x140010df7  jz      short loc_140010DA8
0x140010df9  mov     eax, [rcx+2Ch]
0x140010dfc  test    al, 1
0x140010dfe  jz      short loc_140010DA8
0x140010e00  mov     edx, 35h ; '5'
0x140010e05  mov     r9d, ebx
0x140010e08  jmp     short loc_140010E2D
0x140010e0a  mov     ebx, 0C000009Ah
0x140010e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e16  cmp     rcx, r13
0x140010e19  jz      short loc_140010DA8
0x140010e1b  mov     eax, [rcx+2Ch]
0x140010e1e  test    al, 1
0x140010e20  jz      short loc_140010DA8
0x140010e22  mov     edx, 36h ; '6'
0x140010e27  mov     r9d, 0C000009Ah
0x140010e2d  mov     rcx, [rcx+18h]
0x140010e31  call    WPP_SF_L
0x140010e36  jmp     loc_140010DA8
0x140010e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e42  cmp     rcx, r13
0x140010e45  jz      short loc_140010E60
0x140010e47  mov     edx, [rcx+2Ch]
0x140010e4a  test    dl, 1
0x140010e4d  jz      short loc_140010E60
0x140010e4f  mov     rcx, [rcx+18h]
0x140010e53  mov     edx, 37h ; '7'
0x140010e58  mov     r9d, edi
0x140010e5b  call    WPP_SF_L
0x140010e60  test    ebx, ebx
0x140010e62  cmovns  ebx, edi
0x140010e65  jmp     loc_140010DD9
```
