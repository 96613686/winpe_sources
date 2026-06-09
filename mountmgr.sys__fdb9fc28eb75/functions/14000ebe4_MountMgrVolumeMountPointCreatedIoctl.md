# MountMgrVolumeMountPointCreatedIoctl

- ea: `0x14000ebe4`
- end: `0x14000ecb5`
- name: `MountMgrVolumeMountPointCreatedIoctl`
- size: `209`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000e340`
- `0x14000ebe4`
- `0x140010e70`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14000ec9d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ec9d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ec45`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ec45`

## pseudocode

```c
__int64 __fastcall MountMgrVolumeMountPointCreatedIoctl(__int64 a1, int a2)
{
  int v4; // eax
  __int64 v5; // r8
  int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // r8
  unsigned int v9; // esi

  v4 = WaitForRemoteDatabaseSemaphore();
  v6 = v4;
  if ( v4 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 341, v5, (unsigned int)v4);
  }
  KeWaitForSingleObject((PVOID)(a1 + 56), Executive, 0, 0, 0);
  v7 = MountMgrVolumeMountPointCreated(a1, a2, v6);
  v9 = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 342, v8, v7);
  }
  if ( v6 >= 0 )
    KeReleaseSemaphore((PRKSEMAPHORE)(a1 + 112), 0, 1, 0);
  return v9;
}

```

## disassembly

```asm
0x14000ebe4  push    rbx
0x14000ebe6  push    rbp
0x14000ebe7  push    rsi
0x14000ebe8  push    rdi
0x14000ebe9  sub     rsp, 38h
0x14000ebed  mov     rsi, rdx
0x14000ebf0  mov     rdi, rcx
0x14000ebf3  call    WaitForRemoteDatabaseSemaphore
0x14000ebf8  lea     rbp, WPP_GLOBAL_Control
0x14000ebff  mov     ebx, eax
0x14000ec01  test    eax, eax
0x14000ec03  jns     short loc_14000EC30
0x14000ec05  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec0c  cmp     rcx, rbp
0x14000ec0f  jz      short loc_14000EC30
0x14000ec11  mov     edx, [rcx+2Ch]
0x14000ec14  test    dl, 1
0x14000ec17  jz      short loc_14000EC30
0x14000ec19  cmp     byte ptr [rcx+29h], 2
0x14000ec1d  jb      short loc_14000EC30
0x14000ec1f  mov     rcx, [rcx+18h]
0x14000ec23  mov     edx, 155h
0x14000ec28  mov     r9d, eax
0x14000ec2b  call    WPP_SF_L
0x14000ec30  lea     rcx, [rdi+38h]; Object
0x14000ec34  mov     [rsp+58h+Timeout], 0; Timeout
0x14000ec3d  xor     r9d, r9d; Alertable
0x14000ec40  xor     r8d, r8d; WaitMode
0x14000ec43  xor     edx, edx; WaitReason
0x14000ec45  call    cs:__imp_KeWaitForSingleObject
0x14000ec4c  nop     dword ptr [rax+rax+00h]
0x14000ec51  mov     r8d, ebx; int
0x14000ec54  mov     rdx, rsi; int
0x14000ec57  mov     rcx, rdi; int
0x14000ec5a  call    MountMgrVolumeMountPointCreated
0x14000ec5f  mov     esi, eax
0x14000ec61  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec68  cmp     rcx, rbp
0x14000ec6b  jz      short loc_14000EC8C
0x14000ec6d  mov     edx, [rcx+2Ch]
0x14000ec70  test    dl, 1
0x14000ec73  jz      short loc_14000EC8C
0x14000ec75  cmp     byte ptr [rcx+29h], 2
0x14000ec79  jb      short loc_14000EC8C
0x14000ec7b  mov     rcx, [rcx+18h]
0x14000ec7f  mov     edx, 156h
0x14000ec84  mov     r9d, eax
0x14000ec87  call    WPP_SF_L
0x14000ec8c  test    ebx, ebx
0x14000ec8e  js      short loc_14000ECA9
0x14000ec90  xor     r9d, r9d; Wait
0x14000ec93  lea     rcx, [rdi+70h]; Semaphore
0x14000ec97  xor     edx, edx; Increment
0x14000ec99  lea     r8d, [r9+1]; Adjustment
0x14000ec9d  call    cs:__imp_KeReleaseSemaphore
0x14000eca4  nop     dword ptr [rax+rax+00h]
0x14000eca9  mov     eax, esi
0x14000ecab  add     rsp, 38h
0x14000ecaf  pop     rdi
0x14000ecb0  pop     rsi
0x14000ecb1  pop     rbp
0x14000ecb2  pop     rbx
0x14000ecb3  retn
```
