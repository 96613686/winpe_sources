# LkmdTelpWriteDumpFile

- ea: `0x140054f48`
- end: `0x140055125`
- name: `LkmdTelpWriteDumpFile`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140054e28`

## callees

- `0x140054f48`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140054f8d`
- `ntoskrnl!DbgPrintEx` at `0x140054f8d`
- `ntoskrnl!NtBuildNumber` at `0x140054fbb`
- `ntoskrnl!ZwWriteFile` at `0x140055024`
- `ntoskrnl!ZwWriteFile` at `0x140055073`
- `ntoskrnl!ZwWriteFile` at `0x1400550b5`
- `ntoskrnl!ZwWriteFile` at `0x1400550f6`
- `ntoskrnl!ZwWriteFile` at `0x140055024`
- `ntoskrnl!ZwWriteFile` at `0x140055073`
- `ntoskrnl!ZwWriteFile` at `0x1400550b5`
- `ntoskrnl!ZwWriteFile` at `0x1400550f6`
- `ntoskrnl!ZwClose` at `0x14005510d`
- `ntoskrnl!ZwClose` at `0x14005510d`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x140054f6c`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x140054f6c`

## string_xrefs

- `0x140054f81`: `LKMDTEL: LkmdTelpWriteDumpFile: WerLiveKernelOpenDumpFile failed, status 0x%X\n`

## pseudocode

```c
__int64 __fastcall LkmdTelpWriteDumpFile(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  NTSTATUS v4; // edi
  int v5; // eax
  __int128 v6; // xmm0
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  HANDLE FileHandle; // [rsp+90h] [rbp+28h] BYREF

  v2 = *(_QWORD *)(a1 + 96);
  IoStatusBlock = 0;
  FileHandle = 0;
  v3 = WerLiveKernelOpenDumpFile(v2, &FileHandle);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = *(_DWORD *)(a1 + 24);
    if ( v5 && *(_QWORD *)(a1 + 16) )
    {
      *(_QWORD *)(*(_QWORD *)a1 + 4000LL) = (unsigned int)(v5 + 262192);
      *(_DWORD *)(a1 + 44) = 1886221636;
      *(_DWORD *)(a1 + 48) = 1651469378;
      *(_DWORD *)(a1 + 52) = 16;
      *(_DWORD *)(a1 + 56) = NtBuildNumber;
      *(_DWORD *)(a1 + 60) = 32;
      v6 = *(_OWORD *)(a1 + 28);
      *(_QWORD *)(a1 + 84) = 0;
      *(_OWORD *)(a1 + 64) = v6;
      *(_DWORD *)(a1 + 80) = *(_DWORD *)(a1 + 24);
    }
    v4 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)a1, *(_DWORD *)(a1 + 8), 0, 0);
    if ( v4 >= 0 )
    {
      if ( *(_DWORD *)(a1 + 24) )
      {
        v4 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, (PVOID)(a1 + 44), 0x10u, 0, 0);
        if ( v4 >= 0 )
        {
          v4 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, (PVOID)(a1 + 60), 0x20u, 0, 0);
          if ( v4 >= 0 )
            v4 = ZwWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, *(PVOID *)(a1 + 16), *(_DWORD *)(a1 + 24), 0, 0);
        }
      }
    }
  }
  else
  {
    DbgPrintEx(5u, 0, "LKMDTEL: LkmdTelpWriteDumpFile: WerLiveKernelOpenDumpFile failed, status 0x%X\n", v3);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140054f48  push    rbp
0x140054f4a  push    rbx
0x140054f4b  push    rsi
0x140054f4c  push    rdi
0x140054f4d  mov     rbp, rsp
0x140054f50  sub     rsp, 68h
0x140054f54  mov     rbx, rcx
0x140054f57  lea     rdx, [rbp+FileHandle]
0x140054f5b  mov     rcx, [rcx+60h]
0x140054f5f  xorps   xmm0, xmm0
0x140054f62  xor     esi, esi
0x140054f64  movups  xmmword ptr [rbp+var_18], xmm0
0x140054f68  mov     [rbp+FileHandle], rsi
0x140054f6c  call    cs:__imp_WerLiveKernelOpenDumpFile
0x140054f73  nop     dword ptr [rax+rax+00h]
0x140054f78  mov     edi, eax
0x140054f7a  test    eax, eax
0x140054f7c  jns     short loc_140054F9E
0x140054f7e  mov     r9d, eax
0x140054f81  lea     r8, aLkmdtelLkmdtel_1; "LKMDTEL: LkmdTelpWriteDumpFile: WerLive"...
0x140054f88  xor     edx, edx; Level
0x140054f8a  lea     ecx, [rsi+5]; ComponentId
0x140054f8d  call    cs:__imp_DbgPrintEx
0x140054f94  nop     dword ptr [rax+rax+00h]
0x140054f99  jmp     loc_140055104
0x140054f9e  mov     eax, [rbx+18h]
0x140054fa1  test    eax, eax
0x140054fa3  jz      short loc_140054FF6
0x140054fa5  cmp     [rbx+10h], rsi
0x140054fa9  jz      short loc_140054FF6
0x140054fab  lea     ecx, [rax+40030h]
0x140054fb1  mov     rax, [rbx]
0x140054fb4  mov     [rax+0FA0h], rcx
0x140054fbb  mov     rax, cs:NtBuildNumber
0x140054fc2  mov     dword ptr [rbx+2Ch], 706D7544h
0x140054fc9  mov     dword ptr [rbx+30h], 626F6C42h
0x140054fd0  mov     dword ptr [rbx+34h], 10h
0x140054fd7  mov     ecx, [rax]
0x140054fd9  mov     [rbx+38h], ecx
0x140054fdc  mov     dword ptr [rbx+3Ch], 20h ; ' '
0x140054fe3  movups  xmm0, xmmword ptr [rbx+1Ch]
0x140054fe7  mov     [rbx+54h], rsi
0x140054feb  movdqu  xmmword ptr [rbx+40h], xmm0
0x140054ff0  mov     eax, [rbx+18h]
0x140054ff3  mov     [rbx+50h], eax
0x140054ff6  mov     eax, [rbx+8]
0x140054ff9  xor     r9d, r9d; ApcContext
0x140054ffc  mov     rcx, [rbp+FileHandle]; FileHandle
0x140055000  xor     r8d, r8d; ApcRoutine
0x140055003  mov     [rsp+68h+Key], rsi; Key
0x140055008  xor     edx, edx; Event
0x14005500a  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x14005500f  mov     [rsp+68h+Length], eax; Length
0x140055013  mov     rax, [rbx]
0x140055016  mov     [rsp+68h+Buffer], rax; Buffer
0x14005501b  lea     rax, [rbp+var_18]
0x14005501f  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140055024  call    cs:__imp_ZwWriteFile
0x14005502b  nop     dword ptr [rax+rax+00h]
0x140055030  mov     edi, eax
0x140055032  test    eax, eax
0x140055034  js      loc_140055104
0x14005503a  cmp     [rbx+18h], esi
0x14005503d  jbe     loc_140055104
0x140055043  mov     rcx, [rbp+FileHandle]; FileHandle
0x140055047  lea     rax, [rbx+2Ch]
0x14005504b  mov     [rsp+68h+Key], rsi; Key
0x140055050  xor     r9d, r9d; ApcContext
0x140055053  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140055058  xor     r8d, r8d; ApcRoutine
0x14005505b  mov     [rsp+68h+Length], 10h; Length
0x140055063  xor     edx, edx; Event
0x140055065  mov     [rsp+68h+Buffer], rax; Buffer
0x14005506a  lea     rax, [rbp+var_18]
0x14005506e  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140055073  call    cs:__imp_ZwWriteFile
0x14005507a  nop     dword ptr [rax+rax+00h]
0x14005507f  mov     edi, eax
0x140055081  test    eax, eax
0x140055083  js      short loc_140055104
0x140055085  mov     rcx, [rbp+FileHandle]; FileHandle
0x140055089  lea     rax, [rbx+3Ch]
0x14005508d  mov     [rsp+68h+Key], rsi; Key
0x140055092  xor     r9d, r9d; ApcContext
0x140055095  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x14005509a  xor     r8d, r8d; ApcRoutine
0x14005509d  mov     [rsp+68h+Length], 20h ; ' '; Length
0x1400550a5  xor     edx, edx; Event
0x1400550a7  mov     [rsp+68h+Buffer], rax; Buffer
0x1400550ac  lea     rax, [rbp+var_18]
0x1400550b0  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400550b5  call    cs:__imp_ZwWriteFile
0x1400550bc  nop     dword ptr [rax+rax+00h]
0x1400550c1  mov     edi, eax
0x1400550c3  test    eax, eax
0x1400550c5  js      short loc_140055104
0x1400550c7  mov     eax, [rbx+18h]
0x1400550ca  xor     r9d, r9d; ApcContext
0x1400550cd  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400550d1  xor     r8d, r8d; ApcRoutine
0x1400550d4  mov     [rsp+68h+Key], rsi; Key
0x1400550d9  xor     edx, edx; Event
0x1400550db  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x1400550e0  mov     [rsp+68h+Length], eax; Length
0x1400550e4  mov     rax, [rbx+10h]
0x1400550e8  mov     [rsp+68h+Buffer], rax; Buffer
0x1400550ed  lea     rax, [rbp+var_18]
0x1400550f1  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400550f6  call    cs:__imp_ZwWriteFile
0x1400550fd  nop     dword ptr [rax+rax+00h]
0x140055102  mov     edi, eax
0x140055104  mov     rcx, [rbp+FileHandle]; Handle
0x140055108  test    rcx, rcx
0x14005510b  jz      short loc_140055119
0x14005510d  call    cs:__imp_ZwClose
0x140055114  nop     dword ptr [rax+rax+00h]
0x140055119  mov     eax, edi
0x14005511b  add     rsp, 68h
0x14005511f  pop     rdi
0x140055120  pop     rsi
0x140055121  pop     rbx
0x140055122  pop     rbp
0x140055123  retn
```
