# CompressedStreamDump::CompressedMemStream::WriteBucketList(void)

- ea: `0x18040ad64`
- end: `0x18040af08`
- name: `?WriteBucketList@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ`
- size: `420`
- prototype: `bool __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18040af10`

## callees

- `0x18040ad64`
- `0x180411be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040aea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040aebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040aea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18040aebb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18040ae0e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18040ae8e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18040ae0e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18040ae8e`

## string_xrefs

- `0x18040aeb2`: `WriteBucketList->WriteFile for remainder failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n`
- `0x18040aecd`: `WriteBucketList->WriteFile failed with error: %lu, BytesToWrite: %u, bytesWritten: %u.\n`

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
0x18040ad64  mov     [rsp-28h+arg_8], rbx
0x18040ad69  mov     [rsp-28h+arg_10], rsi
0x18040ad6e  push    rbp
0x18040ad6f  push    rdi
0x18040ad70  push    r12
0x18040ad72  push    r14
0x18040ad74  push    r15
0x18040ad76  mov     rbp, rsp
0x18040ad79  sub     rsp, 50h
0x18040ad7d  mov     r12, [rcx+138h]
0x18040ad84  cmp     r12, [rcx+140h]
0x18040ad8b  jnz     short loc_18040ADA3
0x18040ad8d  lea     rdx, aMVmemorybucket; "m_vMemoryBuckets.size() is 0 which is i"...
0x18040ad94  mov     ecx, 4; this
0x18040ad99  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040ad9e  jmp     loc_18040AEE8
0x18040ada3  mov     rbx, [rcx+0F0h]
0x18040adaa  lea     r15, [rcx+18h]
0x18040adae  mov     rsi, [rcx+0E8h]
0x18040adb5  mov     rdi, rbx
0x18040adb8  shr     rdi, 15h
0x18040adbc  xor     r14d, r14d
0x18040adbf  test    edi, edi
0x18040adc1  jz      short loc_18040AE3E
0x18040adc3  mov     rcx, [r15]; hFile
0x18040adc6  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18040adca  mov     edx, r14d
0x18040adcd  mov     [rbp+Overlapped.Internal], 0
0x18040add5  shl     edx, 15h
0x18040add8  mov     rax, rsi
0x18040addb  shr     rax, 20h
0x18040addf  add     rdx, r12; lpBuffer
0x18040ade2  mov     dword ptr [rbp+Overlapped.10h+4], eax
0x18040ade5  mov     r8d, 200000h; nNumberOfBytesToWrite
0x18040adeb  lea     rax, [rbp+Overlapped]
0x18040adef  mov     [rbp+Overlapped.InternalHigh], 0
0x18040adf7  mov     [rsp+50h+lpOverlapped], rax; lpOverlapped
0x18040adfc  mov     [rbp+Overlapped.hEvent], 0
0x18040ae04  mov     dword ptr [rbp+Overlapped.10h], esi
0x18040ae07  mov     [rbp+NumberOfBytesWritten], 0
0x18040ae0e  call    cs:__imp_WriteFile
0x18040ae15  nop     dword ptr [rax+rax+00h]
0x18040ae1a  test    eax, eax
0x18040ae1c  jz      loc_18040AEBB
0x18040ae22  cmp     [rbp+NumberOfBytesWritten], 200000h
0x18040ae29  jnz     loc_18040AEBB
0x18040ae2f  add     rsi, 200000h
0x18040ae36  inc     r14d
0x18040ae39  cmp     r14d, edi
0x18040ae3c  jb      short loc_18040ADC3
0x18040ae3e  and     ebx, 1FFFFFh
0x18040ae44  jbe     loc_18040AEEC
0x18040ae4a  mov     rcx, [r15]; hFile
0x18040ae4d  lea     rax, [rbp+Overlapped]
0x18040ae51  mov     dword ptr [rbp+Overlapped.10h], esi
0x18040ae54  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18040ae58  shl     edi, 15h
0x18040ae5b  mov     r8d, ebx; nNumberOfBytesToWrite
0x18040ae5e  mov     edx, edi
0x18040ae60  shr     rsi, 20h
0x18040ae64  add     rdx, r12; lpBuffer
0x18040ae67  mov     [rbp+Overlapped.Internal], 0
0x18040ae6f  mov     [rbp+Overlapped.InternalHigh], 0
0x18040ae77  mov     [rbp+Overlapped.hEvent], 0
0x18040ae7f  mov     dword ptr [rbp+Overlapped.10h+4], esi
0x18040ae82  mov     [rbp+NumberOfBytesWritten], 0
0x18040ae89  mov     [rsp+50h+lpOverlapped], rax; lpOverlapped
0x18040ae8e  call    cs:__imp_WriteFile
0x18040ae95  nop     dword ptr [rax+rax+00h]
0x18040ae9a  test    eax, eax
0x18040ae9c  jz      short loc_18040AEA3
0x18040ae9e  cmp     ebx, [rbp+NumberOfBytesWritten]
0x18040aea1  jz      short loc_18040AEEC
0x18040aea3  call    cs:__imp_GetLastError
0x18040aeaa  nop     dword ptr [rax+rax+00h]
0x18040aeaf  mov     r9d, ebx
0x18040aeb2  lea     rdx, aWritebucketlis_0; "WriteBucketList->WriteFile for remainde"...
0x18040aeb9  jmp     short loc_18040AED4
0x18040aebb  call    cs:__imp_GetLastError
0x18040aec2  nop     dword ptr [rax+rax+00h]
0x18040aec7  mov     r9d, 200000h
0x18040aecd  lea     rdx, aWritebucketlis; "WriteBucketList->WriteFile failed with "...
0x18040aed4  mov     ecx, [rbp+NumberOfBytesWritten]
0x18040aed7  mov     r8d, eax; char *
0x18040aeda  mov     dword ptr [rsp+50h+lpOverlapped], ecx
0x18040aede  mov     ecx, 4; this
0x18040aee3  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18040aee8  xor     al, al
0x18040aeea  jmp     short loc_18040AEEE
0x18040aeec  mov     al, 1
0x18040aeee  lea     r11, [rsp+50h+var_s0]
0x18040aef3  mov     rbx, [r11+38h]
0x18040aef7  mov     rsi, [r11+40h]
0x18040aefb  mov     rsp, r11
0x18040aefe  pop     r15
0x18040af00  pop     r14
0x18040af02  pop     r12
0x18040af04  pop     rdi
0x18040af05  pop     rbp
0x18040af06  retn
```
