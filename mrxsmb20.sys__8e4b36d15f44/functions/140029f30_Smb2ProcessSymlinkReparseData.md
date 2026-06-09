# Smb2ProcessSymlinkReparseData

- ea: `0x140029f30`
- end: `0x14002a039`
- name: `Smb2ProcessSymlinkReparseData`
- size: `265`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140007020`
- `0x140032640`

## callees

- `0x14000fa00`
- `0x140029f30`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140029fd5`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x140029fd5`
- `ntoskrnl!ExAllocatePool2` at `0x140029ff4`
- `ntoskrnl!ExAllocatePool2` at `0x140029ff4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029f88`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029f88`

## pseudocode

```c
__int64 __fastcall Smb2ProcessSymlinkReparseData(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  PVOID v5; // rax
  int v6; // ebx
  __int64 v7; // rsi
  size_t v8; // rdi
  void *Pool2; // rax
  unsigned int v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  v3 = *(_QWORD *)(a2 + 752);
  v11 = 0;
  if ( !v3 )
    return (unsigned int)-1073741629;
  if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    v5 = *(PVOID *)(v3 + 24);
  else
    v5 = MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000010u);
  v6 = Smb2QueryErrorDataFromResponse((__int64)v5, *(_DWORD *)(*(_QWORD *)(a2 + 752) + 40LL), 0, &v12, &v11);
  if ( v6 >= 0 )
  {
    if ( v11 >= 8 )
    {
      v7 = v12;
      v8 = v11 - 8;
      v6 = FsRtlValidateReparsePointBuffer(v8, (PREPARSE_DATA_BUFFER)(v12 + 8));
      if ( v6 >= 0 )
      {
        Pool2 = (void *)ExAllocatePool2(66, (unsigned int)v8, 2035513426);
        *(_QWORD *)(a1 + 800) = Pool2;
        if ( Pool2 )
          memmove(Pool2, (const void *)(v7 + 8), v8);
        else
          return (unsigned int)-1073741670;
      }
      return (unsigned int)v6;
    }
    return (unsigned int)-1073741629;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140029f30  mov     [rsp+arg_0], rbx
0x140029f35  push    rbp
0x140029f36  push    rsi
0x140029f37  push    rdi
0x140029f38  sub     rsp, 30h
0x140029f3c  mov     rbp, rcx
0x140029f3f  mov     [rsp+48h+arg_10], 0
0x140029f48  mov     rcx, [rdx+2F0h]; MemoryDescriptorList
0x140029f4f  mov     rbx, rdx
0x140029f52  mov     [rsp+48h+arg_8], 0
0x140029f5a  test    rcx, rcx
0x140029f5d  jz      loc_14002A024
0x140029f63  test    byte ptr [rcx+0Ah], 5
0x140029f67  jz      short loc_140029F6F
0x140029f69  mov     rax, [rcx+18h]
0x140029f6d  jmp     short loc_140029F94
0x140029f6f  xor     r9d, r9d; RequestedAddress
0x140029f72  mov     [rsp+48h+Priority], 40000010h; Priority
0x140029f7a  xor     edx, edx; AccessMode
0x140029f7c  mov     [rsp+48h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140029f84  lea     r8d, [r9+1]; CacheType
0x140029f88  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140029f8f  nop     dword ptr [rax+rax+00h]
0x140029f94  mov     rdx, [rbx+2F0h]
0x140029f9b  lea     rcx, [rsp+48h+arg_8]
0x140029fa0  mov     qword ptr [rsp+48h+BugCheckOnFailure], rcx
0x140029fa5  lea     r9, [rsp+48h+arg_10]
0x140029faa  xor     r8d, r8d
0x140029fad  mov     rcx, rax
0x140029fb0  mov     edx, [rdx+28h]
0x140029fb3  call    Smb2QueryErrorDataFromResponse
0x140029fb8  mov     ebx, eax
0x140029fba  test    eax, eax
0x140029fbc  js      short loc_14002A029
0x140029fbe  mov     edi, [rsp+48h+arg_8]
0x140029fc2  cmp     edi, 8
0x140029fc5  jb      short loc_14002A024
0x140029fc7  mov     rsi, [rsp+48h+arg_10]
0x140029fcc  add     edi, 0FFFFFFF8h
0x140029fcf  mov     ecx, edi; BufferLength
0x140029fd1  lea     rdx, [rsi+8]; ReparseBuffer
0x140029fd5  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x140029fdc  nop     dword ptr [rax+rax+00h]
0x140029fe1  mov     ebx, eax
0x140029fe3  test    eax, eax
0x140029fe5  js      short loc_14002A029
0x140029fe7  mov     r8d, 79537852h
0x140029fed  mov     edx, edi
0x140029fef  mov     ecx, 42h ; 'B'
0x140029ff4  call    cs:__imp_ExAllocatePool2
0x140029ffb  nop     dword ptr [rax+rax+00h]
0x14002a000  mov     [rbp+320h], rax
0x14002a007  test    rax, rax
0x14002a00a  jnz     short loc_14002A013
0x14002a00c  mov     ebx, 0C000009Ah
0x14002a011  jmp     short loc_14002A029
0x14002a013  mov     r8, rdi; Size
0x14002a016  lea     rdx, [rsi+8]; Src
0x14002a01a  mov     rcx, rax; void *
0x14002a01d  call    memmove
0x14002a022  jmp     short loc_14002A029
0x14002a024  mov     ebx, 0C00000C3h
0x14002a029  mov     eax, ebx
0x14002a02b  mov     rbx, [rsp+48h+arg_0]
0x14002a030  add     rsp, 30h
0x14002a034  pop     rdi
0x14002a035  pop     rsi
0x14002a036  pop     rbp
0x14002a037  retn
```
