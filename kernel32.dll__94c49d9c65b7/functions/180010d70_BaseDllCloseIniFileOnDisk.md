# BaseDllCloseIniFileOnDisk

- ea: `0x180010d70`
- end: `0x180010f06`
- name: `BaseDllCloseIniFileOnDisk`
- size: `406`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18001057c`
- `0x18004d650`

## callees

- `0x180010d70`

## import_xrefs

- `ntdll!NtClose` at `0x180010e26`
- `ntdll!NtClose` at `0x180010e26`
- `ntdll!NtSetInformationFile` at `0x180010eef`
- `ntdll!NtSetInformationFile` at `0x180010eef`
- `ntdll!NtFreeVirtualMemory` at `0x180010dcf`
- `ntdll!NtFreeVirtualMemory` at `0x180010dcf`
- `ntdll!NtWriteFile` at `0x180010eb6`
- `ntdll!NtWriteFile` at `0x180010eb6`
- `ntdll!NtUnlockFile` at `0x180010e1c`
- `ntdll!NtUnlockFile` at `0x180010e1c`
- `ntdll!RtlFreeHeap` at `0x180010e4b`
- `ntdll!RtlFreeHeap` at `0x180010e4b`

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
0x180010d70  mov     [rsp-18h+arg_10], rbx
0x180010d75  mov     [rsp-18h+arg_18], rsi
0x180010d7a  push    rbp
0x180010d7b  push    rdi
0x180010d7c  push    r14
0x180010d7e  mov     rbp, rsp
0x180010d81  sub     rsp, 60h
0x180010d85  mov     rdi, [rcx+10h]
0x180010d89  xor     esi, esi
0x180010d8b  mov     qword ptr [rbp+ByteOffset], 0
0x180010d93  xorps   xmm0, xmm0
0x180010d96  mov     qword ptr [rbp+Length], 0
0x180010d9e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180010da2  test    rdi, rdi
0x180010da5  jz      loc_180010E51
0x180010dab  lea     r14, [rdi+38h]
0x180010daf  cmp     [r14], rsi
0x180010db2  jz      short loc_180010DEC
0x180010db4  cmp     dword ptr [rdi+50h], 0FFFFFFFFh
0x180010db8  jnz     loc_180010E68
0x180010dbe  mov     r9d, 8000h; FreeType
0x180010dc4  lea     r8, [rdi+48h]; RegionSize
0x180010dc8  mov     rdx, r14; BaseAddress
0x180010dcb  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180010dcf  call    cs:__imp_NtFreeVirtualMemory
0x180010dd5  mov     qword ptr [r14], 0
0x180010ddc  mov     qword ptr [rdi+40h], 0
0x180010de4  mov     qword ptr [rdi+48h], 0
0x180010dec  cmp     byte ptr [rdi+32h], 0
0x180010df0  jz      short loc_180010E22
0x180010df2  mov     eax, cs:LockFileKey
0x180010df8  lea     r9, [rbp+Length]; Length
0x180010dfc  mov     qword ptr [rbp+ByteOffset], 0
0x180010e04  lea     r8, [rbp+ByteOffset]; ByteOffset
0x180010e08  mov     qword ptr [rbp+Length], 0FFFFFFFFFFFFFFFFh
0x180010e10  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180010e14  mov     rcx, [rdi+28h]; FileHandle
0x180010e18  mov     [rsp+60h+Key], eax; Key
0x180010e1c  call    cs:__imp_NtUnlockFile
0x180010e22  mov     rcx, [rdi+28h]; Handle
0x180010e26  call    cs:__imp_NtClose
0x180010e2c  mov     qword ptr [rdi+28h], 0
0x180010e34  test    esi, esi
0x180010e36  mov     rcx, gs:60h
0x180010e3f  mov     r8, rdi; P
0x180010e42  cmovns  esi, eax
0x180010e45  xor     edx, edx; Flags
0x180010e47  mov     rcx, [rcx+30h]; HeapHandle
0x180010e4b  call    cs:__imp_RtlFreeHeap
0x180010e51  lea     r11, [rsp+60h+var_s0]
0x180010e56  mov     eax, esi
0x180010e58  mov     rbx, [r11+30h]
0x180010e5c  mov     rsi, [r11+38h]
0x180010e60  mov     rsp, r11
0x180010e63  pop     r14
0x180010e65  pop     rdi
0x180010e66  pop     rbp
0x180010e67  retn
0x180010e68  cmp     [rdi+30h], sil
0x180010e6c  jz      loc_180010DBE
0x180010e72  mov     eax, [rdi+50h]
0x180010e75  lea     rcx, LockFileKey
0x180010e7c  mov     [rsp+60h+var_20], rcx; Key
0x180010e81  xor     r9d, r9d; ApcContext
0x180010e84  mov     dword ptr [rbp+ByteOffset], eax
0x180010e87  lea     rcx, [rbp+ByteOffset]
0x180010e8b  mov     eax, [rdi+50h]
0x180010e8e  xor     r8d, r8d; ApcRoutine
0x180010e91  mov     ebx, [rdi+54h]
0x180010e94  xor     edx, edx; Event
0x180010e96  mov     [rsp+60h+var_28], rcx; ByteOffset
0x180010e9b  sub     ebx, eax
0x180010e9d  add     rax, [r14]
0x180010ea0  mov     rcx, [rdi+28h]; FileHandle
0x180010ea4  mov     [rsp+60h+var_30], ebx; Length
0x180010ea8  mov     [rsp+60h+Buffer], rax; Buffer
0x180010ead  lea     rax, [rbp+IoStatusBlock]
0x180010eb1  mov     qword ptr [rsp+60h+Key], rax; IoStatusBlock
0x180010eb6  call    cs:__imp_NtWriteFile
0x180010ebc  mov     esi, eax
0x180010ebe  test    eax, eax
0x180010ec0  js      loc_180010DBE
0x180010ec6  mov     eax, ebx
0x180010ec8  cmp     [rbp+IoStatusBlock.Information], rax
0x180010ecc  jnz     short loc_180010EFC
0x180010ece  mov     eax, [rdi+34h]
0x180010ed1  lea     r8, [rbp+Length]; FileInformation
0x180010ed5  mov     qword ptr [rbp+Length], rax
0x180010ed9  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180010edd  mov     rcx, [rdi+28h]; FileHandle
0x180010ee1  mov     r9d, 8; Length
0x180010ee7  mov     [rsp+60h+Key], 14h; FileInformationClass
0x180010eef  call    cs:__imp_NtSetInformationFile
0x180010ef5  mov     esi, eax
0x180010ef7  jmp     loc_180010DBE
0x180010efc  mov     esi, 0C000007Fh
0x180010f01  jmp     loc_180010DBE
```
