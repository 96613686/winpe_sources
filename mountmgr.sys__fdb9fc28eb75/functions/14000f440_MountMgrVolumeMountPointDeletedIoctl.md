# MountMgrVolumeMountPointDeletedIoctl

- ea: `0x14000f440`
- end: `0x14000f511`
- name: `MountMgrVolumeMountPointDeletedIoctl`
- size: `209`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000ecbc`
- `0x14000f440`
- `0x140010e70`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14000f4f9`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000f4f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f4a1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f4a1`

## pseudocode

```c
__int64 __fastcall MountMgrVolumeMountPointDeletedIoctl(__int64 a1, int a2)
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
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 343, v5, (unsigned int)v4);
  }
  KeWaitForSingleObject((PVOID)(a1 + 56), Executive, 0, 0, 0);
  v7 = MountMgrVolumeMountPointDeleted(a1, a2, v6);
  v9 = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 344, v8, v7);
  }
  if ( v6 >= 0 )
    KeReleaseSemaphore((PRKSEMAPHORE)(a1 + 112), 0, 1, 0);
  return v9;
}

```

## disassembly

```asm
0x14000f440  push    rbx
0x14000f442  push    rbp
0x14000f443  push    rsi
0x14000f444  push    rdi
0x14000f445  sub     rsp, 38h
0x14000f449  mov     rsi, rdx
0x14000f44c  mov     rdi, rcx
0x14000f44f  call    WaitForRemoteDatabaseSemaphore
0x14000f454  lea     rbp, WPP_GLOBAL_Control
0x14000f45b  mov     ebx, eax
0x14000f45d  test    eax, eax
0x14000f45f  jns     short loc_14000F48C
0x14000f461  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f468  cmp     rcx, rbp
0x14000f46b  jz      short loc_14000F48C
0x14000f46d  mov     edx, [rcx+2Ch]
0x14000f470  test    dl, 1
0x14000f473  jz      short loc_14000F48C
0x14000f475  cmp     byte ptr [rcx+29h], 2
0x14000f479  jb      short loc_14000F48C
0x14000f47b  mov     rcx, [rcx+18h]
0x14000f47f  mov     edx, 157h
0x14000f484  mov     r9d, eax
0x14000f487  call    WPP_SF_L
0x14000f48c  lea     rcx, [rdi+38h]; Object
0x14000f490  mov     [rsp+58h+Timeout], 0; Timeout
0x14000f499  xor     r9d, r9d; Alertable
0x14000f49c  xor     r8d, r8d; WaitMode
0x14000f49f  xor     edx, edx; WaitReason
0x14000f4a1  call    cs:__imp_KeWaitForSingleObject
0x14000f4a8  nop     dword ptr [rax+rax+00h]
0x14000f4ad  mov     r8d, ebx; int
0x14000f4b0  mov     rdx, rsi; int
0x14000f4b3  mov     rcx, rdi; int
0x14000f4b6  call    MountMgrVolumeMountPointDeleted
0x14000f4bb  mov     esi, eax
0x14000f4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f4c4  cmp     rcx, rbp
0x14000f4c7  jz      short loc_14000F4E8
0x14000f4c9  mov     edx, [rcx+2Ch]
0x14000f4cc  test    dl, 1
0x14000f4cf  jz      short loc_14000F4E8
0x14000f4d1  cmp     byte ptr [rcx+29h], 2
0x14000f4d5  jb      short loc_14000F4E8
0x14000f4d7  mov     rcx, [rcx+18h]
0x14000f4db  mov     edx, 158h
0x14000f4e0  mov     r9d, eax
0x14000f4e3  call    WPP_SF_L
0x14000f4e8  test    ebx, ebx
0x14000f4ea  js      short loc_14000F505
0x14000f4ec  xor     r9d, r9d; Wait
0x14000f4ef  lea     rcx, [rdi+70h]; Semaphore
0x14000f4f3  xor     edx, edx; Increment
0x14000f4f5  lea     r8d, [r9+1]; Adjustment
0x14000f4f9  call    cs:__imp_KeReleaseSemaphore
0x14000f500  nop     dword ptr [rax+rax+00h]
0x14000f505  mov     eax, esi
0x14000f507  add     rsp, 38h
0x14000f50b  pop     rdi
0x14000f50c  pop     rsi
0x14000f50d  pop     rbp
0x14000f50e  pop     rbx
0x14000f50f  retn
```
