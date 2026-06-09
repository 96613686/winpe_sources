# CompressedStreamDump::ParallelDumpTask::ReadBucket(MemoryBucket *)

- ea: `0x180029d68`
- end: `0x180029fef`
- name: `?ReadBucket@ParallelDumpTask@CompressedStreamDump@@QEAA_NPEAUMemoryBucket@@@Z`
- size: `647`
- prototype: `char __fastcall(CompressedStreamDump::ParallelDumpTask *this, struct MemoryBucket *, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002978c`

## callees

- `0x1800021f4`
- `0x18001f14c`
- `0x1800289b8`
- `0x1800292a0`
- `0x180029d68`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029fbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029fbb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180029ebb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180029ebb`

## string_xrefs

- `0x180029fc6`: `LoadMemoryRegions->ReadFile failed. GetLastError: %d\n`
- `0x180029f3f`: `ReadProcessMemory failed at reading 0x%I64X, size: %u. GetLastError: %u.\n`
- `0x180029fa5`: `ReadProcessMemory failed to read more than %I64u KB. Stop reading memory.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CompressedStreamDump::ParallelDumpTask::ReadBucket(
        CompressedStreamDump::ParallelDumpTask *this,
        struct MemoryBucket *a2,
        unsigned __int64 a3,
        __int64 a4)
{
  unsigned int v4; // r12d
  struct MemoryBucket *v5; // r13
  char v7; // r15
  char *v8; // r14
  unsigned __int64 *v9; // rbp
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  void *v14; // r13
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  __int64 v17; // rcx
  void *v18; // rdx
  __int64 v19; // rbx
  unsigned __int64 v20; // rsi
  __int64 v21; // rsi
  DWORD LastError; // eax
  DWORD v24; // eax
  const char *v25; // r8
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-68h]
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-58h] BYREF
  struct MemoryBucket *v28; // [rsp+98h] [rbp+10h]
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+18h] BYREF
  DWORD nNumberOfBytesToRead; // [rsp+A8h] [rbp+20h]

  v28 = a2;
  v4 = 0;
  v5 = a2;
  v7 = 1;
  if ( !*((_DWORD *)a2 + 8) )
    return v7;
  v8 = (char *)this + 200;
  while ( 1 )
  {
    v9 = *(unsigned __int64 **)v8;
    v10 = *((_QWORD *)this + 26);
    v11 = *((_QWORD *)v5 + 3) + v4;
    if ( *(_QWORD *)v8 != v10 && v11 >= *v9 && v11 <= *(_QWORD *)(v10 - 32) )
      goto LABEL_22;
    v12 = *((_QWORD *)this + 23);
    v13 = v12;
    if ( v12 >= *((_QWORD *)this + 28) )
      v13 = *((_QWORD *)this + 28);
    v14 = (void *)(*((_QWORD *)this + 24) + 32 * v11);
    *((_QWORD *)this + 23) = v12 - v13;
    nNumberOfBytesToRead = 32 * v13;
    if ( v9 == *((unsigned __int64 **)v8 + 1) )
      v9 = (unsigned __int64 *)*((_QWORD *)v8 + 1);
    else
      *((_QWORD *)v8 + 1) = v9;
    v15 = ((__int64)v9 - *(_QWORD *)v8) >> 5;
    if ( v13 >= v15 )
    {
      if ( v13 > v15 )
      {
        if ( v13 <= (__int64)(*((_QWORD *)v8 + 2) - *(_QWORD *)v8) >> 5 )
        {
          v16 = v13 - v15;
          if ( v16 )
          {
            LOBYTE(a2) = 0;
            memset_0(v9, (int)a2, 32 * v16);
            do
            {
              v9 += 4;
              --v16;
            }
            while ( v16 );
          }
          *((_QWORD *)v8 + 1) = v9;
        }
        else
        {
          std::vector<MemoryRegion>::_Resize_reallocate<std::_Value_init_tag>(v8, v13);
        }
      }
    }
    else
    {
      *((_QWORD *)v8 + 1) = *(_QWORD *)v8 + 32 * v13;
    }
    v17 = *(_QWORD *)this;
    v18 = *(void **)v8;
    Overlapped.Pointer = v14;
    NumberOfBytesRead = 0;
    Overlapped.Internal = 0;
    Overlapped.InternalHigh = 0;
    Overlapped.hEvent = 0;
    if ( !ReadFile(*(HANDLE *)(v17 + 24), v18, nNumberOfBytesToRead, &NumberOfBytesRead, &Overlapped) )
      break;
    v5 = v28;
LABEL_22:
    v19 = *(_QWORD *)v8;
    v20 = v11 - **(_QWORD **)v8;
    if ( (__int64)(*((_QWORD *)this + 26) - *(_QWORD *)v8) >> 5 <= v20 )
      std::vector<MemoryBucket *>::_Xrange(this, a2, a3, a4, lpOverlapped);
    v21 = 32 * v20;
    LODWORD(lpOverlapped) = *(_DWORD *)(v21 + v19 + 24);
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)this + 48LL) + 240LL))(
           *(_QWORD *)(*(_QWORD *)this + 48LL),
           **(_QWORD **)this,
           *(_QWORD *)(v21 + v19 + 8),
           *((_QWORD *)this + 4) + *(unsigned int *)(v21 + v19 + 28)) )
    {
      LastError = GetLastError();
      *((_QWORD *)this + 42) += *(unsigned int *)(v21 + v19 + 24);
      LODWORD(lpOverlapped) = LastError;
      CompressedStreamDump::LogMessage(
        (CompressedStreamDump *)4,
        (int)"ReadProcessMemory failed at reading 0x%I64X, size: %u. GetLastError: %u.\n",
        *(const char **)(v21 + v19 + 8),
        *(unsigned int *)(v21 + v19 + 24));
      *(_DWORD *)(v21 + v19 + 24) = 0;
      a3 = *((_QWORD *)this + 41);
      if ( *((_QWORD *)this + 42) > a3 )
      {
        CompressedStreamDump::LogMessage(
          (CompressedStreamDump *)4,
          (int)"ReadProcessMemory failed to read more than %I64u KB. Stop reading memory.\n",
          (const char *)(a3 >> 10));
        return 0;
      }
    }
    else
    {
      *((_QWORD *)this + 13) += *(unsigned int *)(v21 + v19 + 24);
    }
    if ( ++v4 >= *((_DWORD *)v5 + 8) )
      return v7;
  }
  v24 = GetLastError();
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)4,
    (int)"LoadMemoryRegions->ReadFile failed. GetLastError: %d\n",
    (const char *)v24);
  CompressedStreamDump::LogMessage((CompressedStreamDump *)4, (int)"LoadMemoryRegions failed.\n", v25);
  return 0;
}

```

## disassembly

```asm
0x180029d68  mov     [rsp+arg_0], rbx
0x180029d6d  mov     [rsp+arg_8], rdx
0x180029d72  push    rbp
0x180029d73  push    rsi
0x180029d74  push    rdi
0x180029d75  push    r12
0x180029d77  push    r13
0x180029d79  push    r14
0x180029d7b  push    r15
0x180029d7d  sub     rsp, 50h
0x180029d81  xor     r12d, r12d
0x180029d84  mov     r13, rdx
0x180029d87  mov     rdi, rcx
0x180029d8a  mov     r15d, 1
0x180029d90  cmp     [rdx+20h], r12d
0x180029d94  jbe     loc_180029F86
0x180029d9a  lea     r14, [rcx+0C8h]
0x180029da1  mov     rbp, [r14]
0x180029da4  mov     rax, [rdi+0D0h]
0x180029dab  mov     esi, r12d
0x180029dae  add     rsi, [r13+18h]
0x180029db2  cmp     rbp, rax
0x180029db5  jz      short loc_180029DC7
0x180029db7  cmp     rsi, [rbp+0]
0x180029dbb  jb      short loc_180029DC7
0x180029dbd  cmp     rsi, [rax-20h]
0x180029dc1  jbe     loc_180029ED3
0x180029dc7  mov     rcx, [rdi+0B8h]
0x180029dce  mov     r13, rsi
0x180029dd1  mov     rax, [rdi+0E0h]
0x180029dd8  mov     rbx, rcx
0x180029ddb  cmp     rcx, rax
0x180029dde  cmovnb  rbx, rax
0x180029de2  shl     r13, 5
0x180029de6  add     r13, [rdi+0C0h]
0x180029ded  sub     rcx, rbx
0x180029df0  mov     [rdi+0B8h], rcx
0x180029df7  mov     ecx, ebx
0x180029df9  shl     ecx, 5
0x180029dfc  mov     [rsp+88h+nNumberOfBytesToRead], ecx
0x180029e03  cmp     rbp, [r14+8]
0x180029e07  jz      short loc_180029E0F
0x180029e09  mov     [r14+8], rbp
0x180029e0d  jmp     short loc_180029E13
0x180029e0f  mov     rbp, [r14+8]
0x180029e13  mov     rcx, rbp
0x180029e16  sub     rcx, [r14]
0x180029e19  sar     rcx, 5
0x180029e1d  cmp     rbx, rcx
0x180029e20  jnb     short loc_180029E2F
0x180029e22  shl     rbx, 5
0x180029e26  add     rbx, [r14]
0x180029e29  mov     [r14+8], rbx
0x180029e2d  jmp     short loc_180029E71
0x180029e2f  jbe     short loc_180029E71
0x180029e31  mov     rax, [r14+10h]
0x180029e35  sub     rax, [r14]
0x180029e38  sar     rax, 5
0x180029e3c  cmp     rbx, rax
0x180029e3f  jbe     short loc_180029E4E
0x180029e41  mov     rdx, rbx
0x180029e44  mov     rcx, r14
0x180029e47  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UMemoryRegion@@V?$allocator@UMemoryRegion@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<MemoryRegion>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180029e4c  jmp     short loc_180029E71
0x180029e4e  sub     rbx, rcx
0x180029e51  jz      short loc_180029E6D
0x180029e53  mov     r8, rbx
0x180029e56  xor     dl, dl; Val
0x180029e58  shl     r8, 5; Size
0x180029e5c  mov     rcx, rbp; void *
0x180029e5f  call    memset_0
0x180029e64  add     rbp, 20h ; ' '
0x180029e68  sub     rbx, r15
0x180029e6b  jnz     short loc_180029E64
0x180029e6d  mov     [r14+8], rbp
0x180029e71  mov     rcx, [rdi]
0x180029e74  lea     rax, [rsp+88h+Overlapped]
0x180029e79  mov     r8d, [rsp+88h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180029e81  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180029e89  mov     rdx, [r14]; lpBuffer
0x180029e8c  xor     ebp, ebp
0x180029e8e  mov     dword ptr [rsp+88h+Overlapped.10h], r13d
0x180029e93  mov     [rsp+88h+NumberOfBytesRead], ebp
0x180029e9a  mov     [rsp+88h+Overlapped.Internal], rbp
0x180029e9f  mov     [rsp+88h+Overlapped.InternalHigh], rbp
0x180029ea4  mov     [rsp+88h+Overlapped.hEvent], rbp
0x180029ea9  shr     r13, 20h
0x180029ead  mov     dword ptr [rsp+88h+Overlapped.10h+4], r13d
0x180029eb2  mov     rcx, [rcx+18h]; hFile
0x180029eb6  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x180029ebb  call    cs:__imp_ReadFile
0x180029ec1  test    eax, eax
0x180029ec3  jz      loc_180029FBB
0x180029ec9  mov     r13, [rsp+88h+arg_8]
0x180029ed1  jmp     short loc_180029ED5
0x180029ed3  xor     ebp, ebp
0x180029ed5  mov     rbx, [r14]
0x180029ed8  mov     rax, [rdi+0D0h]
0x180029edf  sub     rax, rbx
0x180029ee2  sar     rax, 5
0x180029ee6  sub     rsi, [rbx]
0x180029ee9  cmp     rax, rsi
0x180029eec  jbe     loc_180029FE9
0x180029ef2  mov     rdx, [rdi]
0x180029ef5  shl     rsi, 5
0x180029ef9  mov     rcx, [rdx+30h]
0x180029efd  mov     r8d, [rsi+rbx+18h]
0x180029f02  mov     r9d, [rsi+rbx+1Ch]
0x180029f07  add     r9, [rdi+20h]
0x180029f0b  mov     rax, [rcx]
0x180029f0e  mov     rdx, [rdx]
0x180029f11  mov     dword ptr [rsp+88h+lpOverlapped], r8d
0x180029f16  mov     r8, [rsi+rbx+8]
0x180029f1b  mov     rax, [rax+0F0h]
0x180029f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f27  test    eax, eax
0x180029f29  jnz     short loc_180029F35
0x180029f2b  mov     eax, [rsi+rbx+18h]
0x180029f2f  add     [rdi+68h], rax
0x180029f33  jmp     short loc_180029F79
0x180029f35  call    cs:__imp_GetLastError
0x180029f3b  mov     ecx, [rsi+rbx+18h]
0x180029f3f  lea     rdx, aReadprocessmem; "ReadProcessMemory failed at reading 0x%"...
0x180029f46  add     [rdi+150h], rcx
0x180029f4d  mov     ecx, 4; this
0x180029f52  mov     r9d, [rsi+rbx+18h]
0x180029f57  mov     r8, [rsi+rbx+8]; char *
0x180029f5c  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x180029f60  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029f65  mov     [rsi+rbx+18h], ebp
0x180029f69  mov     r8, [rdi+148h]
0x180029f70  cmp     [rdi+150h], r8
0x180029f77  ja      short loc_180029FA1
0x180029f79  add     r12d, r15d
0x180029f7c  cmp     r12d, [r13+20h]
0x180029f80  jb      loc_180029DA1
0x180029f86  mov     al, r15b
0x180029f89  mov     rbx, [rsp+88h+arg_0]
0x180029f91  add     rsp, 50h
0x180029f95  pop     r15
0x180029f97  pop     r14
0x180029f99  pop     r13
0x180029f9b  pop     r12
0x180029f9d  pop     rdi
0x180029f9e  pop     rsi
0x180029f9f  pop     rbp
0x180029fa0  retn
0x180029fa1  shr     r8, 0Ah; char *
0x180029fa5  lea     rdx, aReadprocessmem_0; "ReadProcessMemory failed to read more t"...
0x180029fac  mov     ecx, 4; this
0x180029fb1  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029fb6  mov     r15b, bpl
0x180029fb9  jmp     short loc_180029F86
0x180029fbb  call    cs:__imp_GetLastError
0x180029fc1  mov     ebx, 4
0x180029fc6  lea     rdx, aLoadmemoryregi; "LoadMemoryRegions->ReadFile failed. Get"...
0x180029fcd  mov     r8d, eax; char *
0x180029fd0  mov     ecx, ebx; this
0x180029fd2  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029fd7  lea     rdx, aLoadmemoryregi_0; "LoadMemoryRegions failed.\n"
0x180029fde  mov     ecx, ebx; this
0x180029fe0  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029fe5  xor     al, al
0x180029fe7  jmp     short loc_180029F89
0x180029fe9  call    ?_Xrange@?$vector@PEAUMemoryBucket@@V?$allocator@PEAUMemoryBucket@@@std@@@std@@CAXXZ; std::vector<MemoryBucket *>::_Xrange(void)
```
