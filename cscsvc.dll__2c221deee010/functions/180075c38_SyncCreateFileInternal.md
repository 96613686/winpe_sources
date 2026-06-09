# SyncCreateFileInternal

- ea: `0x180075c38`
- end: `0x180075e72`
- name: `SyncCreateFileInternal`
- size: `570`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, unsigned int, ULONG, __int64, ULONG CreateDisposition, int, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180075a00`
- `0x18007635c`

## callees

- `0x1800360c0`
- `0x180036394`
- `0x180069094`
- `0x18006d2d4`
- `0x18006d4d4`
- `0x180075c38`
- `0x180076ed8`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180075d80`
- `ntdll!NtCreateFile` at `0x180075d80`

## string_xrefs

- `0x180075ca7`: `SyncCreateFileInternal: Handle: 0x%p FileAttributes 0x%x DesiredAccess: 0x%x ShareAccess: 0x%x Disposition: 0x%x `
- `0x180075ce9`: `SyncCreateFileInternal:CreateOptions: 0x%x File: 0x%p ParentDirHandle: 0x%p`
- `0x180075da1`: `SyncCreateFileInternal: Unable to open file %wZ`
- `0x180075de9`: `SyncCreateFileInternal:  [%wZ] -> %p`
- `0x180075e33`: `SyncCreateFileInternal: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncCreateFileInternal(
        PHANDLE FileHandle,
        unsigned int a2,
        ULONG a3,
        __int64 a4,
        ULONG CreateDisposition,
        int a6,
        struct _UNICODE_STRING *a7)
{
  CObjectMonitor *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // ebx
  CObjectMonitor *v14; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncCreateFileInternal: Handle: 0x%p FileAttributes 0x%x DesiredAccess: 0x%x ShareAccess: 0x%x Disposition: 0x%x ",
        FileHandle,
        a2,
        a3,
        5,
        CreateDisposition);
      WPP_SF_qDDDD(*((_QWORD *)WPP_GLOBAL_Control + 12), v11, v12, FileHandle, a2, a3);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncCreateFileInternal:CreateOptions: 0x%x File: 0x%p ParentDirHandle: 0x%p", 0, a7, 0);
      WPP_SF_Dqq(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, 0, a7, 0);
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = a7;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = NtCreateFile(
          FileHandle,
          a2 | 0x100000,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          a3,
          5u,
          CreateDisposition,
          0x20u,
          0,
          0);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncCreateFileInternal: Unable to open file %wZ", a7);
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, a7);
    }
    _InterlockedIncrement64(&OpenedHandles);
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncCreateFileInternal:  [%wZ] -> %p", a7, *FileHandle);
      WPP_SF_Zq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        13,
        (unsigned int)WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
        (_DWORD)a7,
        (char)*FileHandle);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncCreateFileInternal: 0x%x", v13);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v13);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180075c38  push    rbp
0x180075c3a  push    rbx
0x180075c3b  push    rsi
0x180075c3c  push    rdi
0x180075c3d  push    r12
0x180075c3f  push    r14
0x180075c41  push    r15
0x180075c43  lea     rbp, [rsp-7]
0x180075c48  sub     rsp, 0A0h
0x180075c4f  xorps   xmm0, xmm0
0x180075c52  mov     r14d, r8d
0x180075c55  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x180075c59  mov     ebx, edx
0x180075c5b  mov     rsi, rcx
0x180075c5e  movups  xmmword ptr [rbp+37h+ObjectAttributes+1Ch], xmm0
0x180075c62  xor     eax, eax
0x180075c64  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x180075c68  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x180075c6c  mov     rax, cs:WPP_GLOBAL_Control
0x180075c73  lea     r12, WPP_GLOBAL_Control
0x180075c7a  mov     rdi, [rbp+37h+arg_30]
0x180075c7e  mov     r15d, [rbp+37h+arg_20]
0x180075c82  cmp     rax, r12
0x180075c85  jz      loc_180075D27
0x180075c8b  test    byte ptr [rax+6Ch], 4
0x180075c8f  jz      short loc_180075CDB
0x180075c91  mov     r9d, r8d
0x180075c94  mov     [rsp+0D0h+FileAttributes], r15d
0x180075c99  mov     r8d, edx
0x180075c9c  mov     dword ptr [rsp+0D0h+AllocationSize], 5
0x180075ca4  mov     rdx, rcx
0x180075ca7  lea     rcx, aSynccreatefile_6; "SyncCreateFileInternal: Handle: 0x%p Fi"...
0x180075cae  call    SyncTraceOutputInternal
0x180075cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180075cba  mov     r9, rsi
0x180075cbd  mov     [rsp+0D0h+CreateDisposition], r15d
0x180075cc2  mov     [rsp+0D0h+FileAttributes], r14d
0x180075cc7  mov     dword ptr [rsp+0D0h+AllocationSize], ebx
0x180075ccb  mov     rcx, [rcx+60h]
0x180075ccf  call    WPP_SF_qDDDD
0x180075cd4  mov     rax, cs:WPP_GLOBAL_Control
0x180075cdb  cmp     rax, r12
0x180075cde  jz      short loc_180075D27
0x180075ce0  test    byte ptr [rax+6Ch], 4
0x180075ce4  jz      short loc_180075D27
0x180075ce6  xor     r9d, r9d
0x180075ce9  lea     rcx, aSynccreatefile_2; "SyncCreateFileInternal:CreateOptions: 0"...
0x180075cf0  mov     r8, rdi
0x180075cf3  xor     edx, edx
0x180075cf5  call    SyncTraceOutputInternal
0x180075cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180075d01  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180075d08  mov     edx, 0Bh
0x180075d0d  mov     qword ptr [rsp+0D0h+FileAttributes], 0
0x180075d16  xor     r9d, r9d
0x180075d19  mov     [rsp+0D0h+AllocationSize], rdi
0x180075d1e  mov     rcx, [rcx+60h]
0x180075d22  call    WPP_SF_Dqq
0x180075d27  xor     eax, eax
0x180075d29  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x180075d30  mov     [rsp+0D0h+EaLength], eax; EaLength
0x180075d34  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x180075d38  mov     [rsp+0D0h+EaBuffer], rax; EaBuffer
0x180075d3d  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x180075d41  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x180075d49  xorps   xmm0, xmm0
0x180075d4c  mov     [rsp+0D0h+CreateDisposition], r15d; CreateDisposition
0x180075d51  bts     ebx, 14h
0x180075d55  mov     [rsp+0D0h+ShareAccess], 5; ShareAccess
0x180075d5d  mov     edx, ebx; DesiredAccess
0x180075d5f  mov     [rsp+0D0h+FileAttributes], r14d; FileAttributes
0x180075d64  mov     rcx, rsi; FileHandle
0x180075d67  mov     [rsp+0D0h+AllocationSize], rax; AllocationSize
0x180075d6c  mov     [rbp+37h+ObjectAttributes.RootDirectory], rax
0x180075d70  mov     [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x180075d77  mov     [rbp+37h+ObjectAttributes.ObjectName], rdi
0x180075d7b  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180075d80  call    cs:__imp_NtCreateFile
0x180075d86  mov     ebx, eax
0x180075d88  test    eax, eax
0x180075d8a  jz      short loc_180075DD4
0x180075d8c  mov     rax, cs:WPP_GLOBAL_Control
0x180075d93  cmp     rax, r12
0x180075d96  jz      short loc_180075DCC
0x180075d98  test    byte ptr [rax+6Ch], 1
0x180075d9c  jz      short loc_180075DCC
0x180075d9e  mov     rdx, rdi
0x180075da1  lea     rcx, aSynccreatefile_7; "SyncCreateFileInternal: Unable to open "...
0x180075da8  call    SyncTraceOutputInternal
0x180075dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180075db4  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180075dbb  mov     edx, 0Ch
0x180075dc0  mov     r9, rdi
0x180075dc3  mov     rcx, [rcx+60h]
0x180075dc7  call    WPP_SF_Z
0x180075dcc  lock inc cs:OpenedHandles
0x180075dd4  mov     rax, cs:WPP_GLOBAL_Control
0x180075ddb  cmp     rax, r12
0x180075dde  jz      short loc_180075E5E
0x180075de0  test    byte ptr [rax+6Ch], 1
0x180075de4  jz      short loc_180075E26
0x180075de6  mov     r8, [rsi]
0x180075de9  lea     rcx, aSynccreatefile; "SyncCreateFileInternal:  [%wZ] -> %p"
0x180075df0  mov     rdx, rdi
0x180075df3  call    SyncTraceOutputInternal
0x180075df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180075dff  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180075e06  mov     rax, [rsi]
0x180075e09  mov     edx, 0Dh
0x180075e0e  mov     r9, rdi
0x180075e11  mov     [rsp+0D0h+AllocationSize], rax
0x180075e16  mov     rcx, [rcx+60h]
0x180075e1a  call    WPP_SF_Zq
0x180075e1f  mov     rax, cs:WPP_GLOBAL_Control
0x180075e26  cmp     rax, r12
0x180075e29  jz      short loc_180075E5E
0x180075e2b  test    byte ptr [rax+6Ch], 8
0x180075e2f  jz      short loc_180075E5E
0x180075e31  mov     edx, ebx
0x180075e33  lea     rcx, aSynccreatefile_1; "SyncCreateFileInternal: 0x%x"
0x180075e3a  call    SyncTraceOutputInternal
0x180075e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180075e46  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180075e4d  mov     edx, 0Eh
0x180075e52  mov     r9d, ebx
0x180075e55  mov     rcx, [rcx+60h]
0x180075e59  call    WPP_SF_d
0x180075e5e  mov     eax, ebx
0x180075e60  add     rsp, 0A0h
0x180075e67  pop     r15
0x180075e69  pop     r14
0x180075e6b  pop     r12
0x180075e6d  pop     rdi
0x180075e6e  pop     rsi
0x180075e6f  pop     rbx
0x180075e70  pop     rbp
0x180075e71  retn
```
