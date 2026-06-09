# CompressedStreamDump::CompressedMemStream::WriteCompressedStreamMetaData(void)

- ea: `0x18040af10`
- end: `0x18040b0bc`
- name: `?WriteCompressedStreamMetaData@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ`
- size: `428`
- prototype: `bool __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180409f68`

## callees

- `0x18040ad64`
- `0x18040af10`
- `0x180411be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040af64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040b076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040af64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040b076`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18040b02d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18040b02d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18040af54`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18040af54`

## string_xrefs

- `0x18040b085`: `WriteFile for compressed stream header failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n`
- `0x18040b061`: `WriteCompressedStreamMetaData to dump file completed successfully.\n`
- `0x18040b04e`: `Failed to write the memory bucket list to the dump file.\n`

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
0x18040af10  mov     [rsp-28h+arg_10], rbx
0x18040af15  mov     [rsp-28h+arg_18], rsi
0x18040af1a  push    rbp
0x18040af1b  push    rdi
0x18040af1c  push    r12
0x18040af1e  push    r14
0x18040af20  push    r15
0x18040af22  mov     rbp, rsp
0x18040af25  sub     rsp, 50h
0x18040af29  mov     esi, [rcx+78h]
0x18040af2c  lea     rdx, [rbp+FileSize]; lpFileSize
0x18040af30  mov     r14, [rcx+0B8h]
0x18040af37  mov     rbx, rcx
0x18040af3a  mov     r15, [rcx+0F0h]
0x18040af41  mov     r12, [rcx+0D8h]
0x18040af48  mov     rcx, [rcx+18h]; hFile
0x18040af4c  mov     qword ptr [rbp+FileSize], 0
0x18040af54  call    cs:__imp_GetFileSizeEx
0x18040af5b  nop     dword ptr [rax+rax+00h]
0x18040af60  test    eax, eax
0x18040af62  jnz     short loc_18040AF89
0x18040af64  call    cs:__imp_GetLastError
0x18040af6b  nop     dword ptr [rax+rax+00h]
0x18040af70  lea     rdx, aGetfilesizeexF; "GetFileSizeEx failed. GetLastError: %u"...
0x18040af77  mov     ecx, 4; this
0x18040af7c  mov     r8d, eax; char *
0x18040af7f  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040af84  jmp     loc_18040B0A0
0x18040af89  mov     rax, [rbx+48h]
0x18040af8d  mov     rcx, [rax+30h]
0x18040af91  mov     rax, qword ptr [rbp+FileSize]
0x18040af95  cmp     rax, rcx
0x18040af98  jz      short loc_18040AFBC
0x18040af9a  mov     rax, [rbx+48h]
0x18040af9e  lea     rdx, aInvalidDumpFil_0; "Invalid dump file size detected. Actual"...
0x18040afa5  mov     r9, [rax+30h]
0x18040afa9  mov     r8, qword ptr [rbp+FileSize]; char *
0x18040afad  mov     ecx, 4; this
0x18040afb2  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040afb7  jmp     loc_18040B0A0
0x18040afbc  lea     r9, [r12+rsi]
0x18040afc0  add     r9, r15
0x18040afc3  add     r9, r14
0x18040afc6  cmp     rax, r9
0x18040afc9  jnb     short loc_18040AFD7
0x18040afcb  mov     r8, rax
0x18040afce  lea     rdx, aInvalidDumpFil; "Invalid dump file size detected: %I64u "...
0x18040afd5  jmp     short loc_18040AFAD
0x18040afd7  mov     rcx, [rbx+70h]
0x18040afdb  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18040afdf  sub     rax, rcx
0x18040afe2  mov     dword ptr [rbp+Overlapped.10h], ecx
0x18040afe5  mov     [rbx+0A8h], rax
0x18040afec  lea     rdx, [rbx+78h]; lpBuffer
0x18040aff0  mov     eax, ecx
0x18040aff2  mov     [rbp+Overlapped.Internal], 0
0x18040affa  shr     rcx, 20h
0x18040affe  lea     rax, [rbp+Overlapped]
0x18040b002  mov     dword ptr [rbp+Overlapped.10h+4], ecx
0x18040b005  mov     esi, 0C0h
0x18040b00a  mov     rcx, [rbx+18h]; hFile
0x18040b00e  mov     r8d, esi; nNumberOfBytesToWrite
0x18040b011  mov     [rbp+Overlapped.InternalHigh], 0
0x18040b019  mov     [rbp+Overlapped.hEvent], 0
0x18040b021  mov     [rbp+NumberOfBytesWritten], 0
0x18040b028  mov     [rsp+50h+lpOverlapped], rax; lpOverlapped
0x18040b02d  call    cs:__imp_WriteFile
0x18040b034  nop     dword ptr [rax+rax+00h]
0x18040b039  test    eax, eax
0x18040b03b  jz      short loc_18040B076
0x18040b03d  cmp     [rbp+NumberOfBytesWritten], esi
0x18040b040  jnz     short loc_18040B076
0x18040b042  mov     rcx, rbx; this
0x18040b045  call    ?WriteBucketList@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ; CompressedStreamDump::CompressedMemStream::WriteBucketList(void)
0x18040b04a  test    al, al
0x18040b04c  jnz     short loc_18040B061
0x18040b04e  lea     rdx, aFailedToWriteT; "Failed to write the memory bucket list "...
0x18040b055  mov     ecx, 4; this
0x18040b05a  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040b05f  jmp     short loc_18040B0A0
0x18040b061  lea     rdx, aWritecompresse; "WriteCompressedStreamMetaData to dump f"...
0x18040b068  mov     ecx, 1; this
0x18040b06d  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040b072  mov     al, 1
0x18040b074  jmp     short loc_18040B0A2
0x18040b076  call    cs:__imp_GetLastError
0x18040b07d  nop     dword ptr [rax+rax+00h]
0x18040b082  mov     ecx, [rbp+NumberOfBytesWritten]
0x18040b085  lea     rdx, aWritefileForCo; "WriteFile for compressed stream header "...
0x18040b08c  mov     dword ptr [rsp+50h+lpOverlapped], ecx
0x18040b090  mov     r9d, esi
0x18040b093  mov     ecx, 4; this
0x18040b098  mov     r8d, eax; char *
0x18040b09b  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040b0a0  xor     al, al
0x18040b0a2  lea     r11, [rsp+50h+var_s0]
0x18040b0a7  mov     rbx, [r11+40h]
0x18040b0ab  mov     rsi, [r11+48h]
0x18040b0af  mov     rsp, r11
0x18040b0b2  pop     r15
0x18040b0b4  pop     r14
0x18040b0b6  pop     r12
0x18040b0b8  pop     rdi
0x18040b0b9  pop     rbp
0x18040b0ba  retn
```
