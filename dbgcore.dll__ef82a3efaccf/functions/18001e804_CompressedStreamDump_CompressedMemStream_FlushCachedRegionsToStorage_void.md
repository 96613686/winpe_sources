# CompressedStreamDump::CompressedMemStream::FlushCachedRegionsToStorage(void)

- ea: `0x18001e804`
- end: `0x18001e8e8`
- name: `?FlushCachedRegionsToStorage@CompressedMemStream@CompressedStreamDump@@AEAA_NXZ`
- size: `228`
- prototype: `bool __fastcall(CompressedStreamDump::CompressedMemStream *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ddd8`
- `0x18001df74`

## callees

- `0x18001e804`
- `0x1800289b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8b6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e871`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001e871`

## string_xrefs

- `0x18001e8c0`: `FlushCachedRegionsToStorage->WriteFile failed with error: %lu. BytesToWrite: %u, bytesWritten: %u.\n`
- `0x18001e885`: `FlushCachedRegionsToStorage completed. Region start id: %I64u, regions written: %zu\n`

## pseudocode

```c
char __fastcall CompressedStreamDump::CompressedMemStream::FlushCachedRegionsToStorage(
        CompressedStreamDump::CompressedMemStream *this)
{
  _QWORD *v1; // r10
  DWORD v3; // edi
  void *v4; // r8
  void *v5; // rcx
  __int64 v6; // rcx
  DWORD LastError; // eax
  __int64 v9; // [rsp+20h] [rbp-38h]
  struct _OVERLAPPED v10; // [rsp+30h] [rbp-28h] BYREF
  DWORD v11; // [rsp+60h] [rbp+8h] BYREF

  v1 = (_QWORD *)*((_QWORD *)this + 10);
  v3 = (*((_QWORD *)this + 11) - (_DWORD)v1) & 0xFFFFFFE0;
  v4 = (void *)(*((_QWORD *)this + 26) + 32LL * *v1);
  v5 = (void *)*((_QWORD *)this + 3);
  v10.Pointer = v4;
  v10.Internal = 0;
  v10.InternalHigh = 0;
  v10.hEvent = 0;
  v11 = 0;
  if ( WriteFile(v5, v1, v3, &v11, &v10) && v3 == v11 )
  {
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)1,
      (int)"FlushCachedRegionsToStorage completed. Region start id: %I64u, regions written: %zu\n",
      **((const char ***)this + 10),
      (__int64)(*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) >> 5);
    v6 = *((_QWORD *)this + 10);
    if ( v6 != *((_QWORD *)this + 11) )
      *((_QWORD *)this + 11) = v6;
    return 1;
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v9) = v11;
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"FlushCachedRegionsToStorage->WriteFile failed with error: %lu. BytesToWrite: %u, bytesWritten: %u.\n",
      (const char *)LastError,
      v3,
      v9);
    return 0;
  }
}

```

## disassembly

```asm
0x18001e804  mov     r11, rsp
0x18001e807  mov     [r11+10h], rbx
0x18001e80b  push    rdi
0x18001e80c  sub     rsp, 50h
0x18001e810  mov     r10, [rcx+50h]
0x18001e814  lea     rax, [r11-28h]
0x18001e818  mov     rdi, [rcx+58h]
0x18001e81c  lea     r9, [r11+8]; lpNumberOfBytesWritten
0x18001e820  sub     rdi, r10
0x18001e823  mov     [r11-38h], rax
0x18001e827  mov     rbx, rcx
0x18001e82a  and     edi, 0FFFFFFE0h
0x18001e82d  mov     r8, [r10]
0x18001e830  mov     rdx, r10; lpBuffer
0x18001e833  shl     r8, 5
0x18001e837  add     r8, [rcx+0D0h]
0x18001e83e  mov     rcx, [rcx+18h]; hFile
0x18001e842  mov     [r11-18h], r8d
0x18001e846  shr     r8, 20h
0x18001e84a  mov     [r11-14h], r8d
0x18001e84e  mov     r8d, edi; nNumberOfBytesToWrite
0x18001e851  mov     qword ptr [r11-28h], 0
0x18001e859  mov     qword ptr [r11-20h], 0
0x18001e861  mov     qword ptr [r11-10h], 0
0x18001e869  mov     [rsp+58h+arg_0], 0
0x18001e871  call    cs:__imp_WriteFile
0x18001e877  test    eax, eax
0x18001e879  jz      short loc_18001E8B6
0x18001e87b  cmp     edi, [rsp+58h+arg_0]
0x18001e87f  jnz     short loc_18001E8B6
0x18001e881  mov     r8, [rbx+50h]
0x18001e885  lea     rdx, aFlushcachedreg; "FlushCachedRegionsToStorage completed. "...
0x18001e88c  mov     r9, [rbx+58h]
0x18001e890  mov     ecx, 1; this
0x18001e895  sub     r9, r8
0x18001e898  sar     r9, 5
0x18001e89c  mov     r8, [r8]; char *
0x18001e89f  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001e8a4  mov     rcx, [rbx+50h]
0x18001e8a8  cmp     rcx, [rbx+58h]
0x18001e8ac  jz      short loc_18001E8B2
0x18001e8ae  mov     [rbx+58h], rcx
0x18001e8b2  mov     al, 1
0x18001e8b4  jmp     short loc_18001E8DD
0x18001e8b6  call    cs:__imp_GetLastError
0x18001e8bc  mov     ecx, [rsp+58h+arg_0]
0x18001e8c0  lea     rdx, aFlushcachedreg_0; "FlushCachedRegionsToStorage->WriteFile "...
0x18001e8c7  mov     [rsp+58h+var_38], ecx
0x18001e8cb  mov     r9d, edi
0x18001e8ce  mov     ecx, 4; this
0x18001e8d3  mov     r8d, eax; char *
0x18001e8d6  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18001e8db  xor     al, al
0x18001e8dd  mov     rbx, [rsp+58h+arg_8]
0x18001e8e2  add     rsp, 50h
0x18001e8e6  pop     rdi
0x18001e8e7  retn
```
