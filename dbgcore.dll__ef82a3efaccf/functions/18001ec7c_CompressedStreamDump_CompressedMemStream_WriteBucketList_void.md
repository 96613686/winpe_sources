# CompressedStreamDump::CompressedMemStream::WriteBucketList(void)

- ea: `0x18001ec7c`
- end: `0x18001ee07`
- name: `?WriteBucketList@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ`
- size: `395`
- prototype: `bool __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ee10`

## callees

- `0x18001ec7c`
- `0x1800289b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edc1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ed26`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001eda0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ed26`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001eda0`

## string_xrefs

- `0x18001edcd`: `WriteBucketList->WriteFile failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n`
- `0x18001edb8`: `WriteBucketList->WriteFile for remainder failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n`

## pseudocode

```c
char __fastcall CompressedStreamDump::CompressedMemStream::WriteBucketList(
        CompressedStreamDump::CompressedMemStream *this,
        __int64 a2,
        const char *a3)
{
  __int64 v3; // r12
  unsigned __int64 v4; // rbx
  void **v5; // r15
  char *v6; // rsi
  unsigned __int64 v7; // rdi
  int v8; // r14d
  void *v9; // rcx
  DWORD v10; // ebx
  void *v11; // rcx
  DWORD LastError; // eax
  __int64 v13; // r9
  const char *v14; // rdx
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-30h]
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-20h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+30h] BYREF

  v3 = *((_QWORD *)this + 39);
  if ( v3 == *((_QWORD *)this + 40) )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"m_vMemoryBuckets.size() is 0 which is invalid.\n",
      a3);
    return 0;
  }
  v4 = *((_QWORD *)this + 30);
  v5 = (void **)((char *)this + 24);
  v6 = (char *)*((_QWORD *)this + 29);
  v7 = v4 >> 21;
  v8 = 0;
  if ( (unsigned int)(v4 >> 21) )
  {
    while ( 1 )
    {
      v9 = *v5;
      Overlapped.Internal = 0;
      Overlapped.InternalHigh = 0;
      Overlapped.hEvent = 0;
      Overlapped.Pointer = v6;
      NumberOfBytesWritten = 0;
      if ( !WriteFile(v9, (LPCVOID)(v3 + (unsigned int)(v8 << 21)), 0x200000u, &NumberOfBytesWritten, &Overlapped)
        || NumberOfBytesWritten != 0x200000 )
      {
        break;
      }
      v6 += 0x200000;
      if ( ++v8 >= (unsigned int)v7 )
        goto LABEL_7;
    }
    LastError = GetLastError();
    v13 = 0x200000;
    v14 = "WriteBucketList->WriteFile failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n";
    goto LABEL_12;
  }
LABEL_7:
  v10 = v4 & 0x1FFFFF;
  if ( v10 )
  {
    v11 = *v5;
    Overlapped.Pointer = v6;
    Overlapped.Internal = 0;
    Overlapped.InternalHigh = 0;
    Overlapped.hEvent = 0;
    NumberOfBytesWritten = 0;
    if ( !WriteFile(v11, (LPCVOID)(v3 + (unsigned int)((_DWORD)v7 << 21)), v10, &NumberOfBytesWritten, &Overlapped)
      || v10 != NumberOfBytesWritten )
    {
      LastError = GetLastError();
      v13 = v10;
      v14 = "WriteBucketList->WriteFile for remainder failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n";
LABEL_12:
      LODWORD(lpOverlapped) = NumberOfBytesWritten;
      CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)v14, (const char *)LastError, v13, lpOverlapped);
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001ec7c  mov     [rsp-28h+arg_8], rbx
0x18001ec81  mov     [rsp-28h+arg_10], rsi
0x18001ec86  push    rbp
0x18001ec87  push    rdi
0x18001ec88  push    r12
0x18001ec8a  push    r14
0x18001ec8c  push    r15
0x18001ec8e  mov     rbp, rsp
0x18001ec91  sub     rsp, 50h
0x18001ec95  mov     r12, [rcx+138h]
0x18001ec9c  cmp     r12, [rcx+140h]
0x18001eca3  jnz     short loc_18001ECBB
0x18001eca5  lea     rdx, aMVmemorybucket; "m_vMemoryBuckets.size() is 0 which is i"...
0x18001ecac  mov     ecx, 4; this
0x18001ecb1  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001ecb6  jmp     loc_18001EDE8
0x18001ecbb  mov     rbx, [rcx+0F0h]
0x18001ecc2  lea     r15, [rcx+18h]
0x18001ecc6  mov     rsi, [rcx+0E8h]
0x18001eccd  mov     rdi, rbx
0x18001ecd0  shr     rdi, 15h
0x18001ecd4  xor     r14d, r14d
0x18001ecd7  test    edi, edi
0x18001ecd9  jz      short loc_18001ED50
0x18001ecdb  mov     rcx, [r15]; hFile
0x18001ecde  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ece2  mov     edx, r14d
0x18001ece5  mov     [rbp+Overlapped.Internal], 0
0x18001eced  shl     edx, 15h
0x18001ecf0  mov     rax, rsi
0x18001ecf3  shr     rax, 20h
0x18001ecf7  add     rdx, r12; lpBuffer
0x18001ecfa  mov     dword ptr [rbp+Overlapped.10h+4], eax
0x18001ecfd  mov     r8d, 200000h; nNumberOfBytesToWrite
0x18001ed03  lea     rax, [rbp+Overlapped]
0x18001ed07  mov     [rbp+Overlapped.InternalHigh], 0
0x18001ed0f  mov     [rsp+50h+lpOverlapped], rax; lpOverlapped
0x18001ed14  mov     [rbp+Overlapped.hEvent], 0
0x18001ed1c  mov     dword ptr [rbp+Overlapped.10h], esi
0x18001ed1f  mov     [rbp+NumberOfBytesWritten], 0
0x18001ed26  call    cs:__imp_WriteFile
0x18001ed2c  test    eax, eax
0x18001ed2e  jz      loc_18001EDC1
0x18001ed34  cmp     [rbp+NumberOfBytesWritten], 200000h
0x18001ed3b  jnz     loc_18001EDC1
0x18001ed41  add     rsi, 200000h
0x18001ed48  inc     r14d
0x18001ed4b  cmp     r14d, edi
0x18001ed4e  jb      short loc_18001ECDB
0x18001ed50  and     ebx, 1FFFFFh
0x18001ed56  jbe     loc_18001EDEC
0x18001ed5c  mov     rcx, [r15]; hFile
0x18001ed5f  lea     rax, [rbp+Overlapped]
0x18001ed63  mov     dword ptr [rbp+Overlapped.10h], esi
0x18001ed66  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ed6a  shl     edi, 15h
0x18001ed6d  mov     r8d, ebx; nNumberOfBytesToWrite
0x18001ed70  mov     edx, edi
0x18001ed72  shr     rsi, 20h
0x18001ed76  add     rdx, r12; lpBuffer
0x18001ed79  mov     [rbp+Overlapped.Internal], 0
0x18001ed81  mov     [rbp+Overlapped.InternalHigh], 0
0x18001ed89  mov     [rbp+Overlapped.hEvent], 0
0x18001ed91  mov     dword ptr [rbp+Overlapped.10h+4], esi
0x18001ed94  mov     [rbp+NumberOfBytesWritten], 0
0x18001ed9b  mov     [rsp+50h+lpOverlapped], rax; lpOverlapped
0x18001eda0  call    cs:__imp_WriteFile
0x18001eda6  test    eax, eax
0x18001eda8  jz      short loc_18001EDAF
0x18001edaa  cmp     ebx, [rbp+NumberOfBytesWritten]
0x18001edad  jz      short loc_18001EDEC
0x18001edaf  call    cs:__imp_GetLastError
0x18001edb5  mov     r9d, ebx
0x18001edb8  lea     rdx, aWritebucketlis_0; "WriteBucketList->WriteFile for remainde"...
0x18001edbf  jmp     short loc_18001EDD4
0x18001edc1  call    cs:__imp_GetLastError
0x18001edc7  mov     r9d, 200000h
0x18001edcd  lea     rdx, aWritebucketlis; "WriteBucketList->WriteFile failed with "...
0x18001edd4  mov     ecx, [rbp+NumberOfBytesWritten]
0x18001edd7  mov     r8d, eax; char *
0x18001edda  mov     dword ptr [rsp+50h+lpOverlapped], ecx
0x18001edde  mov     ecx, 4; this
0x18001ede3  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001ede8  xor     al, al
0x18001edea  jmp     short loc_18001EDEE
0x18001edec  mov     al, 1
0x18001edee  lea     r11, [rsp+50h+var_s0]
0x18001edf3  mov     rbx, [r11+38h]
0x18001edf7  mov     rsi, [r11+40h]
0x18001edfb  mov     rsp, r11
0x18001edfe  pop     r15
0x18001ee00  pop     r14
0x18001ee02  pop     r12
0x18001ee04  pop     rdi
0x18001ee05  pop     rbp
0x18001ee06  retn
```
