# LkmdTelpWriteDumpFile

- ea: `0x140848808`
- end: `0x1408489b8`
- name: `LkmdTelpWriteDumpFile`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14084870c`

## callees

- `0x1402a2f90`
- `0x1406dd4e0`
- `0x1406dd5c0`
- `0x140848808`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x14084882c`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelOpenDumpFile` at `0x14084882c`

## string_xrefs

- `0x140848841`: `LKMDTEL: LkmdTelpWriteDumpFile: WerLiveKernelOpenDumpFile failed, status 0x%X\n`

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
0x140848808  push    rbp
0x14084880a  push    rbx
0x14084880b  push    rsi
0x14084880c  push    rdi
0x14084880d  mov     rbp, rsp
0x140848810  sub     rsp, 68h
0x140848814  mov     rbx, rcx
0x140848817  lea     rdx, [rbp+FileHandle]
0x14084881b  mov     rcx, [rcx+60h]
0x14084881f  xorps   xmm0, xmm0
0x140848822  xor     esi, esi
0x140848824  movups  xmmword ptr [rbp+var_18], xmm0
0x140848828  mov     [rbp+FileHandle], rsi
0x14084882c  call    cs:__imp_WerLiveKernelOpenDumpFile
0x140848833  nop     dword ptr [rax+rax+00h]
0x140848838  mov     edi, eax
0x14084883a  test    eax, eax
0x14084883c  jns     short loc_140848857
0x14084883e  mov     r9d, eax
0x140848841  lea     r8, aLkmdtelLkmdtel_1; "LKMDTEL: LkmdTelpWriteDumpFile: WerLive"...
0x140848848  xor     edx, edx; Level
0x14084884a  lea     ecx, [rsi+5]; ComponentId
0x14084884d  call    DbgPrintEx
0x140848852  jmp     loc_14084899E
0x140848857  mov     eax, [rbx+18h]
0x14084885a  test    eax, eax
0x14084885c  jz      short loc_1408488AC
0x14084885e  cmp     [rbx+10h], rsi
0x140848862  jz      short loc_1408488AC
0x140848864  lea     ecx, [rax+40030h]
0x14084886a  mov     rax, [rbx]
0x14084886d  mov     [rax+0FA0h], rcx
0x140848874  mov     dword ptr [rbx+2Ch], 706D7544h
0x14084887b  mov     dword ptr [rbx+30h], 626F6C42h
0x140848882  mov     dword ptr [rbx+34h], 10h
0x140848889  mov     eax, cs:NtBuildNumber
0x14084888f  mov     [rbx+38h], eax
0x140848892  mov     dword ptr [rbx+3Ch], 20h ; ' '
0x140848899  movups  xmm0, xmmword ptr [rbx+1Ch]
0x14084889d  mov     [rbx+54h], rsi
0x1408488a1  movdqu  xmmword ptr [rbx+40h], xmm0
0x1408488a6  mov     eax, [rbx+18h]
0x1408488a9  mov     [rbx+50h], eax
0x1408488ac  mov     eax, [rbx+8]
0x1408488af  xor     r9d, r9d; ApcContext
0x1408488b2  mov     rcx, [rbp+FileHandle]; FileHandle
0x1408488b6  xor     r8d, r8d; ApcRoutine
0x1408488b9  mov     [rsp+68h+Key], rsi; Key
0x1408488be  xor     edx, edx; Event
0x1408488c0  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x1408488c5  mov     [rsp+68h+Length], eax; Length
0x1408488c9  mov     rax, [rbx]
0x1408488cc  mov     [rsp+68h+Buffer], rax; Buffer
0x1408488d1  lea     rax, [rbp+var_18]
0x1408488d5  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1408488da  call    ZwWriteFile
0x1408488df  mov     edi, eax
0x1408488e1  test    eax, eax
0x1408488e3  js      loc_14084899E
0x1408488e9  cmp     [rbx+18h], esi
0x1408488ec  jbe     loc_14084899E
0x1408488f2  mov     rcx, [rbp+FileHandle]; FileHandle
0x1408488f6  lea     rax, [rbx+2Ch]
0x1408488fa  mov     [rsp+68h+Key], rsi; Key
0x1408488ff  xor     r9d, r9d; ApcContext
0x140848902  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140848907  xor     r8d, r8d; ApcRoutine
0x14084890a  mov     [rsp+68h+Length], 10h; Length
0x140848912  xor     edx, edx; Event
0x140848914  mov     [rsp+68h+Buffer], rax; Buffer
0x140848919  lea     rax, [rbp+var_18]
0x14084891d  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140848922  call    ZwWriteFile
0x140848927  mov     edi, eax
0x140848929  test    eax, eax
0x14084892b  js      short loc_14084899E
0x14084892d  mov     rcx, [rbp+FileHandle]; FileHandle
0x140848931  lea     rax, [rbx+3Ch]
0x140848935  mov     [rsp+68h+Key], rsi; Key
0x14084893a  xor     r9d, r9d; ApcContext
0x14084893d  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140848942  xor     r8d, r8d; ApcRoutine
0x140848945  mov     [rsp+68h+Length], 20h ; ' '; Length
0x14084894d  xor     edx, edx; Event
0x14084894f  mov     [rsp+68h+Buffer], rax; Buffer
0x140848954  lea     rax, [rbp+var_18]
0x140848958  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14084895d  call    ZwWriteFile
0x140848962  mov     edi, eax
0x140848964  test    eax, eax
0x140848966  js      short loc_14084899E
0x140848968  mov     eax, [rbx+18h]
0x14084896b  xor     r9d, r9d; ApcContext
0x14084896e  mov     rcx, [rbp+FileHandle]; FileHandle
0x140848972  xor     r8d, r8d; ApcRoutine
0x140848975  mov     [rsp+68h+Key], rsi; Key
0x14084897a  xor     edx, edx; Event
0x14084897c  mov     [rsp+68h+ByteOffset], rsi; ByteOffset
0x140848981  mov     [rsp+68h+Length], eax; Length
0x140848985  mov     rax, [rbx+10h]
0x140848989  mov     [rsp+68h+Buffer], rax; Buffer
0x14084898e  lea     rax, [rbp+var_18]
0x140848992  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140848997  call    ZwWriteFile
0x14084899c  mov     edi, eax
0x14084899e  mov     rcx, [rbp+FileHandle]; Handle
0x1408489a2  test    rcx, rcx
0x1408489a5  jz      short loc_1408489AC
0x1408489a7  call    ZwClose
0x1408489ac  mov     eax, edi
0x1408489ae  add     rsp, 68h
0x1408489b2  pop     rdi
0x1408489b3  pop     rsi
0x1408489b4  pop     rbx
0x1408489b5  pop     rbp
0x1408489b6  retn
```
