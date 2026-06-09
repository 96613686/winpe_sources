# BaseDllCloseIniFileOnDisk

- ea: `0x18000e2a4`
- end: `0x18000e45f`
- name: `BaseDllCloseIniFileOnDisk`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18000da14`
- `0x1800532f0`

## callees

- `0x18000e2a4`

## import_xrefs

- `ntdll!NtClose` at `0x18000e366`
- `ntdll!NtClose` at `0x18000e366`
- `ntdll!NtSetInformationFile` at `0x18000e442`
- `ntdll!NtSetInformationFile` at `0x18000e442`
- `ntdll!NtFreeVirtualMemory` at `0x18000e303`
- `ntdll!NtFreeVirtualMemory` at `0x18000e303`
- `ntdll!NtWriteFile` at `0x18000e403`
- `ntdll!NtWriteFile` at `0x18000e403`
- `ntdll!NtUnlockFile` at `0x18000e356`
- `ntdll!NtUnlockFile` at `0x18000e356`
- `ntdll!RtlFreeHeap` at `0x18000e391`
- `ntdll!RtlFreeHeap` at `0x18000e391`

## pseudocode

```c
__int64 __fastcall BaseDllCloseIniFileOnDisk(__int64 a1)
{
  __int64 v1; // rdi
  NTSTATUS v2; // esi
  _QWORD *v3; // r14
  NTSTATUS v4; // eax
  struct _PEB *v5; // rcx
  __int64 v7; // rax
  ULONG v8; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-10h] BYREF
  union _LARGE_INTEGER Length; // [rsp+80h] [rbp+20h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+88h] [rbp+28h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v2 = 0;
  ByteOffset.QuadPart = 0;
  Length.QuadPart = 0;
  IoStatusBlock = 0;
  if ( v1 )
  {
    v3 = (_QWORD *)(v1 + 56);
    if ( *(_QWORD *)(v1 + 56) )
    {
      if ( *(_DWORD *)(v1 + 80) != -1 )
      {
        if ( *(_BYTE *)(v1 + 48) )
        {
          ByteOffset.LowPart = *(_DWORD *)(v1 + 80);
          v7 = *(unsigned int *)(v1 + 80);
          v8 = *(_DWORD *)(v1 + 84) - v7;
          v2 = NtWriteFile(
                 *(HANDLE *)(v1 + 40),
                 0,
                 0,
                 0,
                 &IoStatusBlock,
                 (PVOID)(*v3 + v7),
                 v8,
                 &ByteOffset,
                 &LockFileKey);
          if ( v2 >= 0 )
          {
            if ( IoStatusBlock.Information == v8 )
            {
              Length.QuadPart = *(unsigned int *)(v1 + 52);
              v2 = NtSetInformationFile(*(HANDLE *)(v1 + 40), &IoStatusBlock, &Length, 8u, FileEndOfFileInformation);
            }
            else
            {
              v2 = -1073741697;
            }
          }
        }
      }
      NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, (PVOID *)(v1 + 56), (PSIZE_T)(v1 + 72), 0x8000u);
      *v3 = 0;
      *(_QWORD *)(v1 + 64) = 0;
      *(_QWORD *)(v1 + 72) = 0;
    }
    if ( *(_BYTE *)(v1 + 50) )
    {
      ByteOffset.QuadPart = 0;
      Length.QuadPart = -1;
      NtUnlockFile(*(HANDLE *)(v1 + 40), &IoStatusBlock, &ByteOffset, &Length, LockFileKey);
    }
    v4 = NtClose(*(HANDLE *)(v1 + 40));
    *(_QWORD *)(v1 + 40) = 0;
    v5 = NtCurrentPeb();
    if ( v2 >= 0 )
      v2 = v4;
    RtlFreeHeap(v5->ProcessHeap, 0, (PVOID)v1);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000e2a4  mov     [rsp-18h+arg_10], rbx
0x18000e2a9  mov     [rsp-18h+arg_18], rsi
0x18000e2ae  push    rbp
0x18000e2af  push    rdi
0x18000e2b0  push    r14
0x18000e2b2  mov     rbp, rsp
0x18000e2b5  sub     rsp, 60h
0x18000e2b9  mov     rdi, [rcx+10h]
0x18000e2bd  xor     esi, esi
0x18000e2bf  mov     qword ptr [rbp+ByteOffset], 0
0x18000e2c7  xorps   xmm0, xmm0
0x18000e2ca  mov     qword ptr [rbp+Length], 0
0x18000e2d2  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18000e2d6  test    rdi, rdi
0x18000e2d9  jz      loc_18000E39D
0x18000e2df  lea     r14, [rdi+38h]
0x18000e2e3  cmp     [r14], rsi
0x18000e2e6  jz      short loc_18000E326
0x18000e2e8  cmp     dword ptr [rdi+50h], 0FFFFFFFFh
0x18000e2ec  jnz     loc_18000E3B5
0x18000e2f2  mov     r9d, 8000h; FreeType
0x18000e2f8  lea     r8, [rdi+48h]; RegionSize
0x18000e2fc  mov     rdx, r14; BaseAddress
0x18000e2ff  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000e303  call    cs:__imp_NtFreeVirtualMemory
0x18000e30a  nop     dword ptr [rax+rax+00h]
0x18000e30f  mov     qword ptr [r14], 0
0x18000e316  mov     qword ptr [rdi+40h], 0
0x18000e31e  mov     qword ptr [rdi+48h], 0
0x18000e326  cmp     byte ptr [rdi+32h], 0
0x18000e32a  jz      short loc_18000E362
0x18000e32c  mov     eax, cs:LockFileKey
0x18000e332  lea     r9, [rbp+Length]; Length
0x18000e336  mov     qword ptr [rbp+ByteOffset], 0
0x18000e33e  lea     r8, [rbp+ByteOffset]; ByteOffset
0x18000e342  mov     qword ptr [rbp+Length], 0FFFFFFFFFFFFFFFFh
0x18000e34a  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18000e34e  mov     rcx, [rdi+28h]; FileHandle
0x18000e352  mov     [rsp+60h+Key], eax; Key
0x18000e356  call    cs:__imp_NtUnlockFile
0x18000e35d  nop     dword ptr [rax+rax+00h]
0x18000e362  mov     rcx, [rdi+28h]; Handle
0x18000e366  call    cs:__imp_NtClose
0x18000e36d  nop     dword ptr [rax+rax+00h]
0x18000e372  mov     qword ptr [rdi+28h], 0
0x18000e37a  test    esi, esi
0x18000e37c  mov     rcx, gs:60h
0x18000e385  mov     r8, rdi; P
0x18000e388  cmovns  esi, eax
0x18000e38b  xor     edx, edx; Flags
0x18000e38d  mov     rcx, [rcx+30h]; HeapHandle
0x18000e391  call    cs:__imp_RtlFreeHeap
0x18000e398  nop     dword ptr [rax+rax+00h]
0x18000e39d  lea     r11, [rsp+60h+var_s0]
0x18000e3a2  mov     eax, esi
0x18000e3a4  mov     rbx, [r11+30h]
0x18000e3a8  mov     rsi, [r11+38h]
0x18000e3ac  mov     rsp, r11
0x18000e3af  pop     r14
0x18000e3b1  pop     rdi
0x18000e3b2  pop     rbp
0x18000e3b3  retn
0x18000e3b5  cmp     [rdi+30h], sil
0x18000e3b9  jz      loc_18000E2F2
0x18000e3bf  mov     eax, [rdi+50h]
0x18000e3c2  lea     rcx, LockFileKey
0x18000e3c9  mov     [rsp+60h+var_20], rcx; Key
0x18000e3ce  xor     r9d, r9d; ApcContext
0x18000e3d1  mov     dword ptr [rbp+ByteOffset], eax
0x18000e3d4  lea     rcx, [rbp+ByteOffset]
0x18000e3d8  mov     eax, [rdi+50h]
0x18000e3db  xor     r8d, r8d; ApcRoutine
0x18000e3de  mov     ebx, [rdi+54h]
0x18000e3e1  xor     edx, edx; Event
0x18000e3e3  mov     [rsp+60h+var_28], rcx; ByteOffset
0x18000e3e8  sub     ebx, eax
0x18000e3ea  add     rax, [r14]
0x18000e3ed  mov     rcx, [rdi+28h]; FileHandle
0x18000e3f1  mov     [rsp+60h+var_30], ebx; Length
0x18000e3f5  mov     [rsp+60h+Buffer], rax; Buffer
0x18000e3fa  lea     rax, [rbp+IoStatusBlock]
0x18000e3fe  mov     qword ptr [rsp+60h+Key], rax; IoStatusBlock
0x18000e403  call    cs:__imp_NtWriteFile
0x18000e40a  nop     dword ptr [rax+rax+00h]
0x18000e40f  mov     esi, eax
0x18000e411  test    eax, eax
0x18000e413  js      loc_18000E2F2
0x18000e419  mov     eax, ebx
0x18000e41b  cmp     [rbp+IoStatusBlock.Information], rax
0x18000e41f  jnz     short loc_18000E455
0x18000e421  mov     eax, [rdi+34h]
0x18000e424  lea     r8, [rbp+Length]; FileInformation
0x18000e428  mov     qword ptr [rbp+Length], rax
0x18000e42c  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18000e430  mov     rcx, [rdi+28h]; FileHandle
0x18000e434  mov     r9d, 8; Length
0x18000e43a  mov     [rsp+60h+Key], 14h; FileInformationClass
0x18000e442  call    cs:__imp_NtSetInformationFile
0x18000e449  nop     dword ptr [rax+rax+00h]
0x18000e44e  mov     esi, eax
0x18000e450  jmp     loc_18000E2F2
0x18000e455  mov     esi, 0C000007Fh
0x18000e45a  jmp     loc_18000E2F2
```
