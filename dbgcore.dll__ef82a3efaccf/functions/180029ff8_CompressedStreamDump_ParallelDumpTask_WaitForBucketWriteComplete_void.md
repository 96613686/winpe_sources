# CompressedStreamDump::ParallelDumpTask::WaitForBucketWriteComplete(void)

- ea: `0x180029ff8`
- end: `0x18002a0b7`
- name: `?WaitForBucketWriteComplete@ParallelDumpTask@CompressedStreamDump@@QEAA_NXZ`
- size: `191`
- prototype: `bool __fastcall(CompressedStreamDump::ParallelDumpTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002978c`
- `0x180029974`

## callees

- `0x1800289b8`
- `0x180029ff8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a015`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a026`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0a0`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a068`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a068`

## string_xrefs

- `0x18002a078`: `Task %u: GetOverlappedResult returned false. GetLastError: %u\n`
- `0x18002a0a6`: `Task %u: GetOverlappedResult bytesWritten not equal to bytesToWrite. GetLastError: %u\n`
- `0x18002a03b`: `Task %u: WaitForBucketWriteComplete timeout after %u seconds.\n`
- `0x18002a02c`: `Task %u: WaitForBucketWriteComplete->WaitForSingleObject returned error: %u.\n`

## pseudocode

```c
char __fastcall CompressedStreamDump::ParallelDumpTask::WaitForBucketWriteComplete(
        CompressedStreamDump::ParallelDumpTask *this)
{
  DWORD v2; // eax
  DWORD LastError; // eax
  const char *v4; // rdx
  __int64 v5; // r9
  __int64 v6; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+30h] [rbp+8h] BYREF

  NumberOfBytesTransferred = 0;
  v2 = WaitForSingleObject(*((HANDLE *)this + 29), 0xEA60u);
  if ( v2 )
  {
    if ( v2 == 258 )
    {
      v5 = 60000;
      v4 = "Task %u: WaitForBucketWriteComplete timeout after %u seconds.\n";
LABEL_8:
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        (int)v4,
        (const char *)*((unsigned int *)this + 24),
        v5);
      return 0;
    }
    LastError = GetLastError();
    v4 = "Task %u: WaitForBucketWriteComplete->WaitForSingleObject returned error: %u.\n";
LABEL_7:
    v5 = LastError;
    goto LABEL_8;
  }
  v6 = *((_QWORD *)this + 2);
  ++*((_QWORD *)this + 18);
  --*((_DWORD *)this + 38);
  if ( !GetOverlappedResult(*(HANDLE *)(v6 + 24), (LPOVERLAPPED)((char *)this + 240), &NumberOfBytesTransferred, 0) )
  {
    LastError = GetLastError();
    v4 = "Task %u: GetOverlappedResult returned false. GetLastError: %u\n";
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 68) != NumberOfBytesTransferred )
  {
    LastError = GetLastError();
    v4 = "Task %u: GetOverlappedResult bytesWritten not equal to bytesToWrite. GetLastError: %u\n";
    goto LABEL_7;
  }
  return 1;
}

```

## disassembly

```asm
0x180029ff8  push    rbx
0x180029ffa  sub     rsp, 20h
0x180029ffe  mov     rbx, rcx
0x18002a001  mov     [rsp+28h+NumberOfBytesTransferred], 0
0x18002a009  mov     rcx, [rcx+0E8h]; hHandle
0x18002a010  mov     edx, 0EA60h; dwMilliseconds
0x18002a015  call    cs:__imp_WaitForSingleObject
0x18002a01b  test    eax, eax
0x18002a01d  jz      short loc_18002A044
0x18002a01f  cmp     eax, 102h
0x18002a024  jz      short loc_18002A035
0x18002a026  call    cs:__imp_GetLastError
0x18002a02c  lea     rdx, aTaskUWaitforbu_0; "Task %u: WaitForBucketWriteComplete->Wa"...
0x18002a033  jmp     short loc_18002A07F
0x18002a035  mov     r9d, 0EA60h
0x18002a03b  lea     rdx, aTaskUWaitforbu; "Task %u: WaitForBucketWriteComplete tim"...
0x18002a042  jmp     short loc_18002A082
0x18002a044  mov     rcx, [rbx+10h]
0x18002a048  lea     rdx, [rbx+0F0h]; lpOverlapped
0x18002a04f  inc     qword ptr [rbx+90h]
0x18002a056  lea     r8, [rsp+28h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002a05b  dec     dword ptr [rbx+98h]
0x18002a061  xor     r9d, r9d; bWait
0x18002a064  mov     rcx, [rcx+18h]; hFile
0x18002a068  call    cs:__imp_GetOverlappedResult
0x18002a06e  test    eax, eax
0x18002a070  jnz     short loc_18002A094
0x18002a072  call    cs:__imp_GetLastError
0x18002a078  lea     rdx, aTaskUGetoverla; "Task %u: GetOverlappedResult returned f"...
0x18002a07f  mov     r9d, eax
0x18002a082  mov     r8d, [rbx+60h]; char *
0x18002a086  mov     ecx, 4; this
0x18002a08b  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18002a090  xor     al, al
0x18002a092  jmp     short loc_18002A0B1
0x18002a094  mov     eax, [rsp+28h+NumberOfBytesTransferred]
0x18002a098  cmp     [rbx+110h], eax
0x18002a09e  jz      short loc_18002A0AF
0x18002a0a0  call    cs:__imp_GetLastError
0x18002a0a6  lea     rdx, aTaskUGetoverla_0; "Task %u: GetOverlappedResult bytesWritt"...
0x18002a0ad  jmp     short loc_18002A07F
0x18002a0af  mov     al, 1
0x18002a0b1  add     rsp, 20h
0x18002a0b5  pop     rbx
0x18002a0b6  retn
```
