# AddRemoteDatabaseEntry

- ea: `0x14000a810`
- end: `0x14000a964`
- name: `AddRemoteDatabaseEntry`
- size: `340`
- prototype: `__int64 __fastcall(__int64, void *, _DWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000a96c`
- `0x14000e340`
- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x14000a810`
- `0x14000bb40`
- `0x140012df0`

## import_xrefs

- `ntoskrnl!ZwWriteFile` at `0x14000a8ab`
- `ntoskrnl!ZwWriteFile` at `0x14000a8ab`
- `ntoskrnl!KeReleaseMutex` at `0x14000a857`
- `ntoskrnl!KeReleaseMutex` at `0x14000a857`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a8fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a8fe`

## pseudocode

```c
__int64 __fastcall AddRemoteDatabaseEntry(__int64 a1, void *a2, _DWORD *a3)
{
  __int64 v3; // rsi
  __int64 v4; // r15
  __int64 v6; // r14
  NTSTATUS v8; // eax
  __int64 v9; // r8
  int v10; // ebx
  int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+90h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 152);
  v4 = *(_QWORD *)(a1 + 176);
  IoStatusBlock = 0;
  ByteOffset.QuadPart = 0;
  v6 = *(_QWORD *)(v3 + 336);
  KeReleaseMutex((PRKMUTEX)(v3 + 56), 0);
  ByteOffset.QuadPart = (unsigned int)GetRemoteDatabaseSize(a2);
  v8 = ZwWriteFile(a2, 0, 0, 0, &IoStatusBlock, a3, *a3, &ByteOffset, 0);
  v10 = v8;
  if ( v8 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 67, v9, (unsigned int)v8);
  }
  KeWaitForSingleObject((PVOID)(v3 + 56), Executive, 0, 0, 0);
  v11 = VerifyEpoch(v3, v6, v4);
  v13 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 68, v12, (unsigned int)v11);
    if ( v10 >= 0 )
      return v13;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a810  mov     rax, rsp
0x14000a813  mov     [rax+10h], rbx
0x14000a817  mov     [rax+18h], rbp
0x14000a81b  push    rsi
0x14000a81c  push    rdi
0x14000a81d  push    r13
0x14000a81f  push    r14
0x14000a821  push    r15
0x14000a823  sub     rsp, 60h
0x14000a827  mov     rsi, [rcx+98h]
0x14000a82e  xorps   xmm0, xmm0
0x14000a831  mov     r15, [rcx+0B0h]
0x14000a838  mov     rdi, rdx
0x14000a83b  movups  xmmword ptr [rax-38h], xmm0
0x14000a83f  mov     qword ptr [rax+8], 0
0x14000a847  xor     edx, edx; Wait
0x14000a849  mov     r14, [rsi+150h]
0x14000a850  lea     rcx, [rsi+38h]; Mutex
0x14000a854  mov     rbx, r8
0x14000a857  call    cs:__imp_KeReleaseMutex
0x14000a85e  nop     dword ptr [rax+rax+00h]
0x14000a863  mov     rcx, rdi
0x14000a866  call    GetRemoteDatabaseSize
0x14000a86b  mov     eax, eax
0x14000a86d  xor     r9d, r9d; ApcContext
0x14000a870  mov     qword ptr [rsp+88h+arg_0], rax
0x14000a878  xor     r8d, r8d; ApcRoutine
0x14000a87b  mov     [rsp+88h+Key], 0; Key
0x14000a884  lea     rax, [rsp+88h+arg_0]
0x14000a88c  mov     [rsp+88h+ByteOffset], rax; ByteOffset
0x14000a891  xor     edx, edx; Event
0x14000a893  mov     eax, [rbx]
0x14000a895  mov     rcx, rdi; FileHandle
0x14000a898  mov     [rsp+88h+Length], eax; Length
0x14000a89c  lea     rax, [rsp+88h+var_38]
0x14000a8a1  mov     [rsp+88h+Buffer], rbx; Buffer
0x14000a8a6  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x14000a8ab  call    cs:__imp_ZwWriteFile
0x14000a8b2  nop     dword ptr [rax+rax+00h]
0x14000a8b7  lea     r13, WPP_GLOBAL_Control
0x14000a8be  mov     ebx, eax
0x14000a8c0  test    eax, eax
0x14000a8c2  jns     short loc_14000A8E9
0x14000a8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a8cb  cmp     rcx, r13
0x14000a8ce  jz      short loc_14000A8E9
0x14000a8d0  mov     edx, [rcx+2Ch]
0x14000a8d3  test    dl, 1
0x14000a8d6  jz      short loc_14000A8E9
0x14000a8d8  mov     rcx, [rcx+18h]
0x14000a8dc  mov     edx, 43h ; 'C'
0x14000a8e1  mov     r9d, eax
0x14000a8e4  call    WPP_SF_L
0x14000a8e9  xor     r9d, r9d; Alertable
0x14000a8ec  mov     [rsp+88h+IoStatusBlock], 0; Timeout
0x14000a8f5  xor     r8d, r8d; WaitMode
0x14000a8f8  lea     rcx, [rsi+38h]; Object
0x14000a8fc  xor     edx, edx; WaitReason
0x14000a8fe  call    cs:__imp_KeWaitForSingleObject
0x14000a905  nop     dword ptr [rax+rax+00h]
0x14000a90a  mov     r8, r15
0x14000a90d  mov     rdx, r14
0x14000a910  mov     rcx, rsi
0x14000a913  call    VerifyEpoch
0x14000a918  mov     edi, eax
0x14000a91a  test    eax, eax
0x14000a91c  jns     short loc_14000A948
0x14000a91e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a925  cmp     rcx, r13
0x14000a928  jz      short loc_14000A943
0x14000a92a  mov     edx, [rcx+2Ch]
0x14000a92d  test    dl, 1
0x14000a930  jz      short loc_14000A943
0x14000a932  mov     rcx, [rcx+18h]
0x14000a936  mov     edx, 44h ; 'D'
0x14000a93b  mov     r9d, eax
0x14000a93e  call    WPP_SF_L
0x14000a943  test    ebx, ebx
0x14000a945  cmovns  ebx, edi
0x14000a948  lea     r11, [rsp+88h+var_28]
0x14000a94d  mov     eax, ebx
0x14000a94f  mov     rbx, [r11+38h]
0x14000a953  mov     rbp, [r11+40h]
0x14000a957  mov     rsp, r11
0x14000a95a  pop     r15
0x14000a95c  pop     r14
0x14000a95e  pop     r13
0x14000a960  pop     rdi
0x14000a961  pop     rsi
0x14000a962  retn
```
