# CopyReparsePoint

- ea: `0x180119f28`
- end: `0x18011a127`
- name: `CopyReparsePoint`
- size: `511`
- prototype: `__int64 __fastcall(HANDLE FileHandle, HANDLE, HANDLE Handle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x1800d770c`

## callees

- `0x18004b9d0`
- `0x180119f28`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x180119fcd`
- `ntdll!NtFsControlFile` at `0x18011a090`
- `ntdll!NtFsControlFile` at `0x180119fcd`
- `ntdll!NtFsControlFile` at `0x18011a090`
- `ntdll!NtWaitForSingleObject` at `0x180119ff0`
- `ntdll!NtWaitForSingleObject` at `0x18011a0ad`
- `ntdll!NtWaitForSingleObject` at `0x180119ff0`
- `ntdll!NtWaitForSingleObject` at `0x18011a0ad`
- `ntdll!RtlReleasePrivilege` at `0x18011a0d7`
- `ntdll!RtlReleasePrivilege` at `0x18011a0d7`
- `ntdll!RtlAcquirePrivilege` at `0x18011a03f`
- `ntdll!RtlAcquirePrivilege` at `0x18011a03f`
- `ntdll!RtlFreeHeap` at `0x18011a0f5`
- `ntdll!RtlFreeHeap` at `0x18011a0f5`
- `ntdll!RtlAllocateHeap` at `0x180119f6c`
- `ntdll!RtlAllocateHeap` at `0x180119f6c`

## pseudocode

```c
__int64 __fastcall CopyReparsePoint(HANDLE FileHandle, HANDLE a2, HANDLE Handle)
{
  unsigned __int16 *OutputBuffer; // rdi
  __int64 v7; // rcx
  NTSTATUS Status; // ebx
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  PVOID ReturnedState; // [rsp+50h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-30h] BYREF
  ULONG Privilege; // [rsp+A8h] [rbp+20h] BYREF

  ReturnedState = 0;
  IoStatusBlock = 0;
  OutputBuffer = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x4000u);
  if ( !OutputBuffer )
  {
    v7 = 3221225495LL;
LABEL_3:
    BaseSetLastNTError(v7);
    return 0;
  }
  Status = NtFsControlFile(FileHandle, Handle, 0, 0, &IoStatusBlock, 0x900A8u, 0, 0, OutputBuffer, 0x4000u);
  if ( Status == 259 )
  {
    do
    {
      do
      {
        v10 = NtWaitForSingleObject(Handle, 1u, 0);
        Status = v10;
      }
      while ( v10 == 257 );
      if ( v10 < 0 )
        break;
      Status = IoStatusBlock.Status;
    }
    while ( IoStatusBlock.Status == 257 );
  }
  if ( Status >= 0 )
  {
    if ( *(_DWORD *)OutputBuffer != -1610612724
      || (Privilege = 35, Status = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState), Status >= 0) )
    {
      Status = NtFsControlFile(a2, Handle, 0, 0, &IoStatusBlock, 0x900A4u, OutputBuffer, OutputBuffer[2] + 8, 0, 0);
      if ( Status == 259 )
      {
        do
        {
          do
          {
            v11 = NtWaitForSingleObject(Handle, 1u, 0);
            Status = v11;
          }
          while ( v11 == 257 );
          if ( v11 < 0 )
            break;
          Status = IoStatusBlock.Status;
        }
        while ( IoStatusBlock.Status == 257 );
      }
    }
  }
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBuffer);
  if ( Status < 0 )
  {
    v7 = (unsigned int)Status;
    goto LABEL_3;
  }
  return 1;
}

```

## disassembly

```asm
0x180119f28  mov     rax, rsp
0x180119f2b  mov     [rax+8], rbx
0x180119f2f  mov     [rax+10h], rbp
0x180119f33  push    rsi
0x180119f34  push    rdi
0x180119f35  push    r12
0x180119f37  sub     rsp, 70h
0x180119f3b  mov     rbx, rcx
0x180119f3e  mov     qword ptr [rax-38h], 0
0x180119f46  xorps   xmm0, xmm0
0x180119f49  mov     rsi, r8
0x180119f4c  movups  xmmword ptr [rax-30h], xmm0
0x180119f50  mov     rcx, gs:60h
0x180119f59  mov     rbp, rdx
0x180119f5c  mov     edx, cs:KernelBaseGlobalData; Flags
0x180119f62  mov     r8d, 4000h; Size
0x180119f68  mov     rcx, [rcx+30h]; HeapHandle
0x180119f6c  call    cs:__imp_RtlAllocateHeap
0x180119f73  nop     dword ptr [rax+rax+00h]
0x180119f78  mov     rdi, rax
0x180119f7b  test    rax, rax
0x180119f7e  jnz     short loc_180119F91
0x180119f80  mov     ecx, 0C0000017h
0x180119f85  call    BaseSetLastNTError
0x180119f8a  xor     eax, eax
0x180119f8c  jmp     loc_18011A111
0x180119f91  mov     [rsp+88h+OutputBufferLength], 4000h; OutputBufferLength
0x180119f99  lea     rax, [rsp+88h+var_30]
0x180119f9e  mov     [rsp+88h+OutputBuffer], rdi; OutputBuffer
0x180119fa3  xor     r9d, r9d; ApcContext
0x180119fa6  mov     [rsp+88h+InputBufferLength], 0; InputBufferLength
0x180119fae  xor     r8d, r8d; ApcRoutine
0x180119fb1  mov     [rsp+88h+InputBuffer], 0; InputBuffer
0x180119fba  mov     rdx, rsi; Event
0x180119fbd  mov     [rsp+88h+FsControlCode], 900A8h; FsControlCode
0x180119fc5  mov     rcx, rbx; FileHandle
0x180119fc8  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x180119fcd  call    cs:__imp_NtFsControlFile
0x180119fd4  nop     dword ptr [rax+rax+00h]
0x180119fd9  mov     ebx, eax
0x180119fdb  mov     r12d, 101h
0x180119fe1  cmp     eax, 103h
0x180119fe6  jnz     short loc_18011A010
0x180119fe8  xor     r8d, r8d; Timeout
0x180119feb  mov     dl, 1; Alertable
0x180119fed  mov     rcx, rsi; Handle
0x180119ff0  call    cs:__imp_NtWaitForSingleObject
0x180119ff7  nop     dword ptr [rax+rax+00h]
0x180119ffc  mov     ebx, eax
0x180119ffe  cmp     eax, r12d
0x18011a001  jz      short loc_180119FE8
0x18011a003  test    eax, eax
0x18011a005  js      short loc_18011A010
0x18011a007  mov     ebx, dword ptr [rsp+88h+var_30]
0x18011a00b  cmp     ebx, r12d
0x18011a00e  jz      short loc_180119FE8
0x18011a010  test    ebx, ebx
0x18011a012  js      loc_18011A0CD
0x18011a018  cmp     dword ptr [rdi], 0A000000Ch
0x18011a01e  jnz     short loc_18011A051
0x18011a020  xor     r8d, r8d; Flags
0x18011a023  mov     [rsp+88h+Privilege], 23h ; '#'
0x18011a02e  lea     r9, [rsp+88h+ReturnedState]; ReturnedState
0x18011a033  lea     rcx, [rsp+88h+Privilege]; Privilege
0x18011a03b  lea     edx, [r8+1]; NumPriv
0x18011a03f  call    cs:__imp_RtlAcquirePrivilege
0x18011a046  nop     dword ptr [rax+rax+00h]
0x18011a04b  mov     ebx, eax
0x18011a04d  test    eax, eax
0x18011a04f  js      short loc_18011A0CD
0x18011a051  movzx   eax, word ptr [rdi+4]
0x18011a055  xor     r9d, r9d; ApcContext
0x18011a058  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x18011a060  add     eax, 8
0x18011a063  mov     [rsp+88h+OutputBuffer], 0; OutputBuffer
0x18011a06c  xor     r8d, r8d; ApcRoutine
0x18011a06f  mov     [rsp+88h+InputBufferLength], eax; InputBufferLength
0x18011a073  mov     rdx, rsi; Event
0x18011a076  mov     [rsp+88h+InputBuffer], rdi; InputBuffer
0x18011a07b  lea     rax, [rsp+88h+var_30]
0x18011a080  mov     [rsp+88h+FsControlCode], 900A4h; FsControlCode
0x18011a088  mov     rcx, rbp; FileHandle
0x18011a08b  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x18011a090  call    cs:__imp_NtFsControlFile
0x18011a097  nop     dword ptr [rax+rax+00h]
0x18011a09c  mov     ebx, eax
0x18011a09e  cmp     eax, 103h
0x18011a0a3  jnz     short loc_18011A0CD
0x18011a0a5  xor     r8d, r8d; Timeout
0x18011a0a8  mov     dl, 1; Alertable
0x18011a0aa  mov     rcx, rsi; Handle
0x18011a0ad  call    cs:__imp_NtWaitForSingleObject
0x18011a0b4  nop     dword ptr [rax+rax+00h]
0x18011a0b9  mov     ebx, eax
0x18011a0bb  cmp     eax, r12d
0x18011a0be  jz      short loc_18011A0A5
0x18011a0c0  test    eax, eax
0x18011a0c2  js      short loc_18011A0CD
0x18011a0c4  mov     ebx, dword ptr [rsp+88h+var_30]
0x18011a0c8  cmp     ebx, r12d
0x18011a0cb  jz      short loc_18011A0A5
0x18011a0cd  mov     rcx, [rsp+88h+ReturnedState]; ReturnedState
0x18011a0d2  test    rcx, rcx
0x18011a0d5  jz      short loc_18011A0E3
0x18011a0d7  call    cs:__imp_RtlReleasePrivilege
0x18011a0de  nop     dword ptr [rax+rax+00h]
0x18011a0e3  mov     rcx, gs:60h
0x18011a0ec  mov     r8, rdi; P
0x18011a0ef  xor     edx, edx; Flags
0x18011a0f1  mov     rcx, [rcx+30h]; HeapHandle
0x18011a0f5  call    cs:__imp_RtlFreeHeap
0x18011a0fc  nop     dword ptr [rax+rax+00h]
0x18011a101  test    ebx, ebx
0x18011a103  jns     short loc_18011A10C
0x18011a105  mov     ecx, ebx
0x18011a107  jmp     loc_180119F85
0x18011a10c  mov     eax, 1
0x18011a111  lea     r11, [rsp+88h+var_18]
0x18011a116  mov     rbx, [r11+20h]
0x18011a11a  mov     rbp, [r11+28h]
0x18011a11e  mov     rsp, r11
0x18011a121  pop     r12
0x18011a123  pop     rdi
0x18011a124  pop     rsi
0x18011a125  retn
```
