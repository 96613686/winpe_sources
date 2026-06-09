# CompressedStreamDump::CompressedMemStream::WriteCompressedStreamMetaData(void)

- ea: `0x18001ee10`
- end: `0x18001efa3`
- name: `?WriteCompressedStreamMetaData@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ`
- size: `403`
- prototype: `bool __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ddd8`

## callees

- `0x18001ec7c`
- `0x18001ee10`
- `0x1800289b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef64`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001ee54`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001ee54`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ef21`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001ef21`

## string_xrefs

- `0x18001ef6d`: `WriteFile for compressed stream header failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n`
- `0x18001ef3c`: `Failed to write the memory bucket list to the dump file.\n`
- `0x18001ef4f`: `WriteCompressedStreamMetaData to dump file completed successfully.\n`

## pseudocode

```c
char __fastcall CompressedStreamDump::CompressedMemStream::WriteCompressedStreamMetaData(
        CompressedStreamDump::CompressedMemStream *this)
{
  __int64 v1; // rsi
  __int64 v2; // r14
  __int64 v4; // r15
  __int64 v5; // r12
  void *v6; // rcx
  DWORD v7; // eax
  union _LARGE_INTEGER v8; // r9
  __int64 v9; // rcx
  void *v10; // rcx
  __int64 v11; // rdx
  const char *v12; // r8
  const char *v13; // r8
  DWORD LastError; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-30h]
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-20h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+30h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+88h] [rbp+38h] BYREF

  v1 = *((unsigned int *)this + 30);
  v2 = *((_QWORD *)this + 23);
  v4 = *((_QWORD *)this + 30);
  v5 = *((_QWORD *)this + 27);
  v6 = (void *)*((_QWORD *)this + 3);
  FileSize.QuadPart = 0;
  if ( GetFileSizeEx(v6, &FileSize) )
  {
    if ( FileSize.QuadPart == *(_QWORD *)(*((_QWORD *)this + 9) + 48LL) )
    {
      v8.QuadPart = v2 + v4 + v5 + v1;
      if ( FileSize.QuadPart >= (unsigned __int64)v8.QuadPart )
      {
        v9 = *((_QWORD *)this + 14);
        Overlapped.Offset = v9;
        *((_QWORD *)this + 21) = FileSize.QuadPart - v9;
        Overlapped.Internal = 0;
        Overlapped.OffsetHigh = HIDWORD(v9);
        v10 = (void *)*((_QWORD *)this + 3);
        Overlapped.InternalHigh = 0;
        Overlapped.hEvent = 0;
        NumberOfBytesWritten = 0;
        if ( WriteFile(v10, (char *)this + 120, 0xC0u, &NumberOfBytesWritten, &Overlapped)
          && NumberOfBytesWritten == 192 )
        {
          if ( CompressedStreamDump::CompressedMemStream::WriteBucketList(this, v11, v12) )
          {
            CompressedStreamDump::LogMessage(
              (CompressedStreamDump *)1,
              (int)"WriteCompressedStreamMetaData to dump file completed successfully.\n",
              v13);
            return 1;
          }
          CompressedStreamDump::LogMessage(
            (CompressedStreamDump *)4,
            (int)"Failed to write the memory bucket list to the dump file.\n",
            v13);
        }
        else
        {
          LastError = GetLastError();
          LODWORD(lpOverlapped) = NumberOfBytesWritten;
          CompressedStreamDump::LogMessage(
            (CompressedStreamDump *)4,
            (int)"WriteFile for compressed stream header failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n",
            (const char *)LastError,
            192,
            lpOverlapped);
        }
      }
      else
      {
        CompressedStreamDump::LogMessage(
          (CompressedStreamDump *)4,
          (int)"Invalid dump file size detected: %I64u bytes, it should be greater than %I64u bytes.\n",
          (const char *)FileSize.QuadPart,
          v8.QuadPart);
      }
    }
    else
    {
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        (int)"Invalid dump file size detected. Actual: %I64u bytes, expected: %I64u bytes.\n",
        (const char *)FileSize.QuadPart,
        *(_QWORD *)(*((_QWORD *)this + 9) + 48LL));
    }
  }
  else
  {
    v7 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"GetFileSizeEx failed. GetLastError: %u\n",
      (const char *)v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ee10  mov     [rsp-28h+arg_10], rbx
0x18001ee15  mov     [rsp-28h+arg_18], rsi
0x18001ee1a  push    rbp
0x18001ee1b  push    rdi
0x18001ee1c  push    r12
0x18001ee1e  push    r14
0x18001ee20  push    r15
0x18001ee22  mov     rbp, rsp
0x18001ee25  sub     rsp, 50h
0x18001ee29  mov     esi, [rcx+78h]
0x18001ee2c  lea     rdx, [rbp+FileSize]; lpFileSize
0x18001ee30  mov     r14, [rcx+0B8h]
0x18001ee37  mov     rbx, rcx
0x18001ee3a  mov     r15, [rcx+0F0h]
0x18001ee41  mov     r12, [rcx+0D8h]
0x18001ee48  mov     rcx, [rcx+18h]; hFile
0x18001ee4c  mov     qword ptr [rbp+FileSize], 0
0x18001ee54  call    cs:__imp_GetFileSizeEx
0x18001ee5a  test    eax, eax
0x18001ee5c  jnz     short loc_18001EE7D
0x18001ee5e  call    cs:__imp_GetLastError
0x18001ee64  lea     rdx, aGetfilesizeexF; "GetFileSizeEx failed. GetLastError: %u"...
0x18001ee6b  mov     ecx, 4; this
0x18001ee70  mov     r8d, eax; char *
0x18001ee73  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001ee78  jmp     loc_18001EF88
0x18001ee7d  mov     rax, [rbx+48h]
0x18001ee81  mov     rcx, [rax+30h]
0x18001ee85  mov     rax, qword ptr [rbp+FileSize]
0x18001ee89  cmp     rax, rcx
0x18001ee8c  jz      short loc_18001EEB0
0x18001ee8e  mov     rax, [rbx+48h]
0x18001ee92  lea     rdx, aInvalidDumpFil_0; "Invalid dump file size detected. Actual"...
0x18001ee99  mov     r9, [rax+30h]
0x18001ee9d  mov     r8, qword ptr [rbp+FileSize]; char *
0x18001eea1  mov     ecx, 4; this
0x18001eea6  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001eeab  jmp     loc_18001EF88
0x18001eeb0  lea     r9, [r12+rsi]
0x18001eeb4  add     r9, r15
0x18001eeb7  add     r9, r14
0x18001eeba  cmp     rax, r9
0x18001eebd  jnb     short loc_18001EECB
0x18001eebf  mov     r8, rax
0x18001eec2  lea     rdx, aInvalidDumpFil; "Invalid dump file size detected: %I64u "...
0x18001eec9  jmp     short loc_18001EEA1
0x18001eecb  mov     rcx, [rbx+70h]
0x18001eecf  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001eed3  sub     rax, rcx
0x18001eed6  mov     dword ptr [rbp+Overlapped.10h], ecx
0x18001eed9  mov     [rbx+0A8h], rax
0x18001eee0  lea     rdx, [rbx+78h]; lpBuffer
0x18001eee4  mov     eax, ecx
0x18001eee6  mov     [rbp+Overlapped.Internal], 0
0x18001eeee  shr     rcx, 20h
0x18001eef2  lea     rax, [rbp+Overlapped]
0x18001eef6  mov     dword ptr [rbp+Overlapped.10h+4], ecx
0x18001eef9  mov     esi, 0C0h
0x18001eefe  mov     rcx, [rbx+18h]; hFile
0x18001ef02  mov     r8d, esi; nNumberOfBytesToWrite
0x18001ef05  mov     [rbp+Overlapped.InternalHigh], 0
0x18001ef0d  mov     [rbp+Overlapped.hEvent], 0
0x18001ef15  mov     [rbp+NumberOfBytesWritten], 0
0x18001ef1c  mov     [rsp+50h+lpOverlapped], rax; lpOverlapped
0x18001ef21  call    cs:__imp_WriteFile
0x18001ef27  test    eax, eax
0x18001ef29  jz      short loc_18001EF64
0x18001ef2b  cmp     [rbp+NumberOfBytesWritten], esi
0x18001ef2e  jnz     short loc_18001EF64
0x18001ef30  mov     rcx, rbx; this
0x18001ef33  call    ?WriteBucketList@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ; CompressedStreamDump::CompressedMemStream::WriteBucketList(void)
0x18001ef38  test    al, al
0x18001ef3a  jnz     short loc_18001EF4F
0x18001ef3c  lea     rdx, aFailedToWriteT; "Failed to write the memory bucket list "...
0x18001ef43  mov     ecx, 4; this
0x18001ef48  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001ef4d  jmp     short loc_18001EF88
0x18001ef4f  lea     rdx, aWritecompresse; "WriteCompressedStreamMetaData to dump f"...
0x18001ef56  mov     ecx, 1; this
0x18001ef5b  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001ef60  mov     al, 1
0x18001ef62  jmp     short loc_18001EF8A
0x18001ef64  call    cs:__imp_GetLastError
0x18001ef6a  mov     ecx, [rbp+NumberOfBytesWritten]
0x18001ef6d  lea     rdx, aWritefileForCo; "WriteFile for compressed stream header "...
0x18001ef74  mov     dword ptr [rsp+50h+lpOverlapped], ecx
0x18001ef78  mov     r9d, esi
0x18001ef7b  mov     ecx, 4; this
0x18001ef80  mov     r8d, eax; char *
0x18001ef83  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001ef88  xor     al, al
0x18001ef8a  lea     r11, [rsp+50h+var_s0]
0x18001ef8f  mov     rbx, [r11+40h]
0x18001ef93  mov     rsi, [r11+48h]
0x18001ef97  mov     rsp, r11
0x18001ef9a  pop     r15
0x18001ef9c  pop     r14
0x18001ef9e  pop     r12
0x18001efa0  pop     rdi
0x18001efa1  pop     rbp
0x18001efa2  retn
```
