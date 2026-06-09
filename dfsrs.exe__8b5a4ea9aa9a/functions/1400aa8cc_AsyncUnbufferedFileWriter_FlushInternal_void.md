# AsyncUnbufferedFileWriter::FlushInternal(void)

- ea: `0x1400aa8cc`
- end: `0x1400aae32`
- name: `?FlushInternal@AsyncUnbufferedFileWriter@@AEAAPEAVFrsStatus@@XZ`
- size: `1382`
- prototype: `struct FrsStatus *__fastcall(AsyncUnbufferedFileWriter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400aa4a0`

## callees

- `0x14000cdc0`
- `0x14000e34c`
- `0x1400aa8cc`
- `0x1400c0d00`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!CancelIoEx` at `0x1400aab85`
- `KERNEL32!CancelIoEx` at `0x1400aab85`
- `KERNEL32!GetOverlappedResult` at `0x1400aaca9`
- `KERNEL32!GetOverlappedResult` at `0x1400aaca9`
- `KERNEL32!WriteFile` at `0x1400aa995`
- `KERNEL32!WriteFile` at `0x1400aaa9f`
- `KERNEL32!WriteFile` at `0x1400aa995`
- `KERNEL32!WriteFile` at `0x1400aaa9f`
- `KERNEL32!GetLastError` at `0x1400aa9a5`
- `KERNEL32!GetLastError` at `0x1400aaaaf`
- `KERNEL32!GetLastError` at `0x1400aab99`
- `KERNEL32!GetLastError` at `0x1400aaccb`
- `KERNEL32!GetLastError` at `0x1400aa9a5`
- `KERNEL32!GetLastError` at `0x1400aaaaf`
- `KERNEL32!GetLastError` at `0x1400aab99`
- `KERNEL32!GetLastError` at `0x1400aaccb`
- `KERNEL32!GetCurrentThreadId` at `0x1400aa9bb`
- `KERNEL32!GetCurrentThreadId` at `0x1400aaac5`
- `KERNEL32!GetCurrentThreadId` at `0x1400aabb3`
- `KERNEL32!GetCurrentThreadId` at `0x1400aacbd`
- `KERNEL32!GetCurrentThreadId` at `0x1400aadd2`
- `KERNEL32!GetCurrentThreadId` at `0x1400aa9bb`
- `KERNEL32!GetCurrentThreadId` at `0x1400aaac5`
- `KERNEL32!GetCurrentThreadId` at `0x1400aabb3`
- `KERNEL32!GetCurrentThreadId` at `0x1400aacbd`
- `KERNEL32!GetCurrentThreadId` at `0x1400aadd2`

## string_xrefs

- `0x1400aac0d`: `AsyncUnbufferedFileWriter::FlushInternal`
- `0x1400aad56`: `AsyncUnbufferedFileWriter::FlushInternal`
- `0x1400aa9d9`: `AsyncUnbufferedFileWriter::FlushInternal`
- `0x1400aaae3`: `AsyncUnbufferedFileWriter::FlushInternal`
- `0x1400aab64`: `AsyncUnbufferedFileWriter::FlushInternal`
- `0x1400aac81`: `AsyncUnbufferedFileWriter::FlushInternal`
- `0x1400aadf2`: `AsyncUnbufferedFileWriter::FlushInternal`
- `0x1400aad68`: `(Ignored) Failed to wait for I/O to complete. Error:%?`

## pseudocode

```c
struct FrsStatus *__fastcall AsyncUnbufferedFileWriter::FlushInternal(AsyncUnbufferedFileWriter *this)
{
  __int64 v1; // rsi
  bool v3; // zf
  struct FrsStatus *v4; // r14
  unsigned int v6; // eax
  unsigned __int64 *v7; // rbx
  struct FrsStatus *v8; // r12
  HANDLE *v9; // r15
  void **v10; // rcx
  struct FrsStatus *v11; // r8
  DWORD LastError; // r13d
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // edx
  DWORD v17; // r15d
  DWORD v18; // eax
  __int64 v19; // rcx
  int v20; // r13d
  unsigned int v21; // edx
  unsigned int v22; // ebx
  struct FrsStatus *v23; // r13
  DWORD v24; // r15d
  DWORD v25; // eax
  __int64 v26; // rcx
  struct FrsStatus *v27; // rax
  void *v28; // rcx
  struct _OVERLAPPED *v29; // rdx
  DWORD v30; // ebx
  DWORD v31; // eax
  __int64 v32; // rcx
  struct FrsStatus *v33; // rax
  unsigned int v34; // edx
  DWORD v35; // eax
  __int64 v36; // rcx
  struct FrsStatus *v37; // [rsp+50h] [rbp-29h]
  HANDLE *v38; // [rsp+58h] [rbp-21h]
  struct FrsStatus *v39; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int64 *v40; // [rsp+68h] [rbp-11h]
  void **v41; // [rsp+70h] [rbp-9h]
  const wchar_t *v42; // [rsp+78h] [rbp-1h] BYREF
  int v43; // [rsp+80h] [rbp+7h]
  int v44; // [rsp+84h] [rbp+Bh]
  const wchar_t *v45; // [rsp+88h] [rbp+Fh]
  struct FrsStatus *v46; // [rsp+E0h] [rbp+67h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+E8h] [rbp+6Fh] BYREF
  void **v48; // [rsp+F0h] [rbp+77h]
  struct FrsStatus *v49; // [rsp+F8h] [rbp+7Fh]

  v1 = 0;
  v3 = *((_DWORD *)this + 34) == 3;
  v4 = 0;
  v37 = 0;
  NumberOfBytesWritten = 0;
  LODWORD(v46) = 0;
  if ( v3 )
    return 0;
  v6 = *((_DWORD *)this + 20);
  v7 = (unsigned __int64 *)((char *)this + 104);
  v8 = (AsyncUnbufferedFileWriter *)((char *)this + 72);
  v9 = (HANDLE *)((char *)this + 16);
  while ( 1 )
  {
    v10 = v9;
    v41 = v9;
    v11 = v8;
    v48 = v9;
    v40 = v7;
    v49 = v8;
    v38 = v9;
    v39 = v8;
    if ( !*((_DWORD *)this + 21) )
      break;
    v8 = (AsyncUnbufferedFileWriter *)((char *)this + 72);
    v7 = (unsigned __int64 *)((char *)this + 104);
    v9 = (HANDLE *)((char *)this + 16);
    *(_QWORD *)(32LL * *((unsigned int *)this + 24) + *((_QWORD *)this + 9) + 16) = *((_QWORD *)this + 13);
    if ( WriteFile(
           *((HANDLE *)this + 2),
           *(LPCVOID *)(*((_QWORD *)this + 8) + 8LL * *((unsigned int *)this + 24)),
           *((_DWORD *)this + 14),
           &NumberOfBytesWritten,
           (LPOVERLAPPED)(*((_QWORD *)this + 9) + 32LL * *((unsigned int *)this + 24))) )
    {
      ++*((_DWORD *)this + 30);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        ++*((_DWORD *)this + 29);
      }
      else
      {
        CurrentThreadId = GetCurrentThreadId();
        v4 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v14,
                                   LastError,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                   "AsyncUnbufferedFileWriter::FlushInternal",
                                   1126,
                                   CurrentThreadId,
                                   0);
        v37 = v4;
      }
    }
    if ( v4 )
      goto LABEL_20;
    *v7 += *((unsigned int *)this + 14);
    v15 = *((_DWORD *)this + 24);
    ++*((_DWORD *)this + 20);
    v16 = (unsigned int)(v15 + 1) % *((_DWORD *)this + 13);
    v6 = *((_DWORD *)this + 20);
    --*((_DWORD *)this + 21);
    *((_DWORD *)this + 24) = v16;
  }
  if ( !*((_DWORD *)this + 25) )
  {
    v20 = (int)v46;
    goto LABEL_34;
  }
  *(_QWORD *)(32LL * *((unsigned int *)this + 22) + *(_QWORD *)v8 + 16) = *v7;
  if ( WriteFile(
         *v9,
         *(LPCVOID *)(*((_QWORD *)this + 8) + 8LL * *((unsigned int *)this + 22)),
         -*((_DWORD *)this + 12) & (*((_DWORD *)this + 12) + *((_DWORD *)this + 25) - 1),
         &NumberOfBytesWritten,
         (LPOVERLAPPED)(*(_QWORD *)v8 + 32LL * *((unsigned int *)this + 22))) )
  {
    ++*((_DWORD *)this + 30);
  }
  else
  {
    v17 = GetLastError();
    if ( v17 == 997 )
    {
      ++*((_DWORD *)this + 29);
    }
    else
    {
      v18 = GetCurrentThreadId();
      v4 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v19,
                                 v17,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                 "AsyncUnbufferedFileWriter::FlushInternal",
                                 1173,
                                 v18,
                                 0);
      v37 = v4;
    }
  }
  if ( !v4 )
  {
    *v7 += *((unsigned int *)this + 25);
    v11 = v8;
    v20 = (int)v46;
    v21 = (unsigned int)(*((_DWORD *)this + 24) + 1) % *((_DWORD *)this + 13);
    v6 = ++*((_DWORD *)this + 20);
    *((_DWORD *)this + 24) = v21;
LABEL_33:
    v10 = v48;
    goto LABEL_34;
  }
LABEL_20:
  v6 = *((_DWORD *)this + 20);
  v22 = 0;
  v20 = v6 != 0;
  LODWORD(v46) = v20;
  if ( !v6 )
  {
    v11 = v49;
    goto LABEL_33;
  }
  v23 = v39;
  do
  {
    if ( !CancelIoEx(
            *v38,
            (LPOVERLAPPED)(*(_QWORD *)v23 + 32LL * ((v22 + *((_DWORD *)this + 23)) % *((_DWORD *)this + 13)))) )
    {
      v24 = GetLastError();
      if ( v24 != 1168 )
      {
        v25 = GetCurrentThreadId();
        v27 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v26,
                                    v24,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                    "AsyncUnbufferedFileWriter::FlushInternal",
                                    1201,
                                    v25,
                                    0);
        v39 = v27;
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
        {
          v43 = 1202;
          v42 = L"AsyncUnbufferedFileWriter::FlushInternal";
          v44 = 3;
          v45 = L"ASYN";
          dbgobj::DbgPrint<unsigned short,FrsStatus>(&v42, L"(Ignored) Failed to cancel I/O. Error:%?", v27);
        }
        CLEAR_ERROR(&v39);
      }
    }
    v6 = *((_DWORD *)this + 20);
    ++v22;
  }
  while ( v22 < v6 );
  v20 = (int)v46;
  v10 = v38;
  v4 = v37;
  v11 = v49;
LABEL_34:
  if ( v6 )
  {
    do
    {
      v28 = *v10;
      v29 = (struct _OVERLAPPED *)(*(_QWORD *)v11 + 32LL * *((unsigned int *)this + 23));
      NumberOfBytesWritten = 0;
      if ( !GetOverlappedResult(v28, v29, &NumberOfBytesWritten, 1) )
      {
        v30 = GetCurrentThreadId();
        v31 = GetLastError();
        v33 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                    v32,
                                    v31,
                                    0,
                                    1,
                                    "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                    "AsyncUnbufferedFileWriter::FlushInternal",
                                    1221,
                                    v30,
                                    0);
        v46 = v33;
        if ( v20 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
          {
            v43 = 1224;
            goto LABEL_47;
          }
          goto LABEL_48;
        }
        if ( v4 )
        {
          if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 3 )
          {
            v43 = 1233;
LABEL_47:
            v44 = 3;
            v42 = L"AsyncUnbufferedFileWriter::FlushInternal";
            v45 = L"ASYN";
            dbgobj::DbgPrint<unsigned short,FrsStatus>(
              &v42,
              L"(Ignored) Failed to wait for I/O to complete. Error:%?",
              v33);
          }
LABEL_48:
          CLEAR_ERROR(&v46);
          goto LABEL_49;
        }
        v4 = v33;
      }
LABEL_49:
      v10 = v48;
      v34 = (unsigned int)(*((_DWORD *)this + 23) + 1) % *((_DWORD *)this + 13);
      v3 = (*((_DWORD *)this + 20))-- == 1;
      v11 = v49;
      *((_DWORD *)this + 23) = v34;
    }
    while ( !v3 );
  }
  if ( !v4 )
    v4 = FileUtil::SetFileSize(*v41, v40);
  *((_DWORD *)this + 34) = 3;
  if ( v4 )
  {
    v35 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v36,
                                 *((unsigned int *)v4 + 1),
                                 *((unsigned int *)v4 + 2),
                                 *(unsigned int *)v4,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                 "AsyncUnbufferedFileWriter::FlushInternal",
                                 1260,
                                 v35,
                                 v4);
  }
  return (struct FrsStatus *)v1;
}

```

## disassembly

```asm
0x1400aa8cc  push    rbp
0x1400aa8ce  push    rbx
0x1400aa8cf  push    rsi
0x1400aa8d0  push    rdi
0x1400aa8d1  push    r12
0x1400aa8d3  push    r13
0x1400aa8d5  push    r14
0x1400aa8d7  push    r15
0x1400aa8d9  lea     rbp, [rsp-1Fh]
0x1400aa8de  sub     rsp, 98h
0x1400aa8e5  xor     esi, esi
0x1400aa8e7  mov     rdi, rcx
0x1400aa8ea  cmp     dword ptr [rcx+88h], 3
0x1400aa8f1  mov     r14d, esi
0x1400aa8f4  mov     [rbp+57h+var_80], rsi
0x1400aa8f8  mov     [rbp+57h+NumberOfBytesWritten], esi
0x1400aa8fb  mov     dword ptr [rbp+57h+arg_0], esi
0x1400aa8fe  jnz     short loc_1400AA907
0x1400aa900  xor     eax, eax
0x1400aa902  jmp     loc_1400AAE1D
0x1400aa907  mov     eax, [rcx+50h]
0x1400aa90a  lea     rbx, [rcx+68h]
0x1400aa90e  lea     r12, [rcx+48h]
0x1400aa912  lea     r15, [rcx+10h]
0x1400aa916  mov     rcx, r15
0x1400aa919  mov     [rbp+57h+var_60], r15
0x1400aa91d  mov     r8, r12
0x1400aa920  mov     [rbp+57h+arg_10], rcx
0x1400aa924  mov     [rbp+57h+var_68], rbx
0x1400aa928  mov     [rbp+57h+arg_18], r12
0x1400aa92c  mov     [rbp+57h+var_78], r15
0x1400aa930  mov     [rbp+57h+var_70], r12
0x1400aa934  cmp     [rdi+54h], esi
0x1400aa937  jbe     loc_1400AAA3C
0x1400aa93d  mov     edx, [rdi+60h]
0x1400aa940  lea     r12, [rdi+48h]
0x1400aa944  mov     rcx, [r12]
0x1400aa948  lea     rbx, [rdi+68h]
0x1400aa94c  mov     eax, [rbx]
0x1400aa94e  lea     r15, [rdi+10h]
0x1400aa952  shl     rdx, 5
0x1400aa956  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400aa95a  mov     [rdx+rcx+10h], eax
0x1400aa95e  mov     ecx, [rdi+60h]
0x1400aa961  mov     rax, [r12]
0x1400aa965  mov     rdx, [rbx]
0x1400aa968  shl     rcx, 5
0x1400aa96c  shr     rdx, 20h
0x1400aa970  mov     [rcx+rax+14h], edx
0x1400aa974  mov     edx, [rdi+60h]
0x1400aa977  mov     rax, [rdi+40h]
0x1400aa97b  mov     ecx, edx
0x1400aa97d  mov     r8d, [rdi+38h]; nNumberOfBytesToWrite
0x1400aa981  shl     rcx, 5
0x1400aa985  add     rcx, [r12]
0x1400aa989  mov     rdx, [rax+rdx*8]; lpBuffer
0x1400aa98d  mov     [rsp+0D0h+lpOverlapped], rcx; lpOverlapped
0x1400aa992  mov     rcx, [r15]; hFile
0x1400aa995  call    cs:__imp_WriteFile
0x1400aa99c  nop     dword ptr [rax+rax+00h]
0x1400aa9a1  test    eax, eax
0x1400aa9a3  jnz     short loc_1400AAA0F
0x1400aa9a5  call    cs:__imp_GetLastError
0x1400aa9ac  nop     dword ptr [rax+rax+00h]
0x1400aa9b1  mov     r13d, eax
0x1400aa9b4  cmp     eax, 3E5h
0x1400aa9b9  jz      short loc_1400AAA0A
0x1400aa9bb  call    cs:__imp_GetCurrentThreadId
0x1400aa9c2  nop     dword ptr [rax+rax+00h]
0x1400aa9c7  mov     [rsp+0D0h+var_90], rsi
0x1400aa9cc  mov     r9d, 1
0x1400aa9d2  mov     [rsp+0D0h+var_98], eax
0x1400aa9d6  xor     r8d, r8d
0x1400aa9d9  lea     rax, aAsyncunbuffere_14; "AsyncUnbufferedFileWriter::FlushInterna"...
0x1400aa9e0  mov     [rsp+0D0h+var_A0], 466h
0x1400aa9e8  mov     [rsp+0D0h+var_A8], rax
0x1400aa9ed  mov     edx, r13d
0x1400aa9f0  lea     rax, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400aa9f7  mov     [rsp+0D0h+lpOverlapped], rax
0x1400aa9fc  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400aaa01  mov     r14, rax
0x1400aaa04  mov     [rbp+57h+var_80], rax
0x1400aaa08  jmp     short loc_1400AAA12
0x1400aaa0a  inc     dword ptr [rdi+74h]
0x1400aaa0d  jmp     short loc_1400AAA12
0x1400aaa0f  inc     dword ptr [rdi+78h]
0x1400aaa12  test    r14, r14
0x1400aaa15  jnz     loc_1400AAB46
0x1400aaa1b  mov     eax, [rdi+38h]
0x1400aaa1e  xor     edx, edx
0x1400aaa20  add     [rbx], rax
0x1400aaa23  mov     eax, [rdi+60h]
0x1400aaa26  inc     dword ptr [rdi+50h]
0x1400aaa29  inc     eax
0x1400aaa2b  div     dword ptr [rdi+34h]
0x1400aaa2e  mov     eax, [rdi+50h]
0x1400aaa31  dec     dword ptr [rdi+54h]
0x1400aaa34  mov     [rdi+60h], edx
0x1400aaa37  jmp     loc_1400AA916
0x1400aaa3c  cmp     [rdi+64h], esi
0x1400aaa3f  jbe     loc_1400AAC6B
0x1400aaa45  mov     edx, [rdi+58h]
0x1400aaa48  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400aaa4c  mov     rcx, [r12]
0x1400aaa50  mov     eax, [rbx]
0x1400aaa52  shl     rdx, 5
0x1400aaa56  mov     [rdx+rcx+10h], eax
0x1400aaa5a  mov     ecx, [rdi+58h]
0x1400aaa5d  mov     rax, [r12]
0x1400aaa61  mov     rdx, [rbx]
0x1400aaa64  shl     rcx, 5
0x1400aaa68  shr     rdx, 20h
0x1400aaa6c  mov     [rcx+rax+14h], edx
0x1400aaa70  mov     ecx, [rdi+30h]
0x1400aaa73  mov     edx, [rdi+58h]
0x1400aaa76  mov     r8d, [rdi+64h]
0x1400aaa7a  mov     rax, [rdi+40h]
0x1400aaa7e  dec     r8d
0x1400aaa81  add     r8d, ecx
0x1400aaa84  neg     ecx
0x1400aaa86  and     r8d, ecx; nNumberOfBytesToWrite
0x1400aaa89  mov     ecx, edx
0x1400aaa8b  shl     rcx, 5
0x1400aaa8f  add     rcx, [r12]
0x1400aaa93  mov     rdx, [rax+rdx*8]; lpBuffer
0x1400aaa97  mov     [rsp+0D0h+lpOverlapped], rcx; lpOverlapped
0x1400aaa9c  mov     rcx, [r15]; hFile
0x1400aaa9f  call    cs:__imp_WriteFile
0x1400aaaa6  nop     dword ptr [rax+rax+00h]
0x1400aaaab  test    eax, eax
0x1400aaaad  jnz     short loc_1400AAB19
0x1400aaaaf  call    cs:__imp_GetLastError
0x1400aaab6  nop     dword ptr [rax+rax+00h]
0x1400aaabb  mov     r15d, eax
0x1400aaabe  cmp     eax, 3E5h
0x1400aaac3  jz      short loc_1400AAB14
0x1400aaac5  call    cs:__imp_GetCurrentThreadId
0x1400aaacc  nop     dword ptr [rax+rax+00h]
0x1400aaad1  mov     [rsp+0D0h+var_90], rsi
0x1400aaad6  mov     r9d, 1
0x1400aaadc  mov     [rsp+0D0h+var_98], eax
0x1400aaae0  xor     r8d, r8d
0x1400aaae3  lea     rax, aAsyncunbuffere_14; "AsyncUnbufferedFileWriter::FlushInterna"...
0x1400aaaea  mov     [rsp+0D0h+var_A0], 495h
0x1400aaaf2  mov     [rsp+0D0h+var_A8], rax
0x1400aaaf7  mov     edx, r15d
0x1400aaafa  lea     rax, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400aab01  mov     [rsp+0D0h+lpOverlapped], rax
0x1400aab06  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400aab0b  mov     r14, rax
0x1400aab0e  mov     [rbp+57h+var_80], rax
0x1400aab12  jmp     short loc_1400AAB1C
0x1400aab14  inc     dword ptr [rdi+74h]
0x1400aab17  jmp     short loc_1400AAB1C
0x1400aab19  inc     dword ptr [rdi+78h]
0x1400aab1c  test    r14, r14
0x1400aab1f  jnz     short loc_1400AAB46
0x1400aab21  mov     eax, [rdi+64h]
0x1400aab24  xor     edx, edx
0x1400aab26  add     [rbx], rax
0x1400aab29  mov     r8, r12
0x1400aab2c  mov     eax, [rdi+60h]
0x1400aab2f  mov     r13d, dword ptr [rbp+57h+arg_0]
0x1400aab33  inc     eax
0x1400aab35  div     dword ptr [rdi+34h]
0x1400aab38  inc     dword ptr [rdi+50h]
0x1400aab3b  mov     eax, [rdi+50h]
0x1400aab3e  mov     [rdi+60h], edx
0x1400aab41  jmp     loc_1400AAC75
0x1400aab46  mov     eax, [rdi+50h]
0x1400aab49  mov     r13d, esi
0x1400aab4c  test    eax, eax
0x1400aab4e  mov     ebx, esi
0x1400aab50  setnz   r13b
0x1400aab54  mov     dword ptr [rbp+57h+arg_0], r13d
0x1400aab58  test    eax, eax
0x1400aab5a  jz      loc_1400AAC71
0x1400aab60  mov     r12, [rbp+57h+var_78]
0x1400aab64  lea     r14, aAsyncunbuffere_14; "AsyncUnbufferedFileWriter::FlushInterna"...
0x1400aab6b  mov     r13, [rbp+57h+var_70]
0x1400aab6f  mov     eax, [rdi+5Ch]
0x1400aab72  xor     edx, edx
0x1400aab74  mov     rcx, [r12]; hFile
0x1400aab78  add     eax, ebx
0x1400aab7a  div     dword ptr [rdi+34h]
0x1400aab7d  shl     rdx, 5
0x1400aab81  add     rdx, [r13+0]; lpOverlapped
0x1400aab85  call    cs:__imp_CancelIoEx
0x1400aab8c  nop     dword ptr [rax+rax+00h]
0x1400aab91  test    eax, eax
0x1400aab93  jnz     loc_1400AAC4D
0x1400aab99  call    cs:__imp_GetLastError
0x1400aaba0  nop     dword ptr [rax+rax+00h]
0x1400aaba5  mov     r15d, eax
0x1400aaba8  cmp     eax, 490h
0x1400aabad  jz      loc_1400AAC4D
0x1400aabb3  call    cs:__imp_GetCurrentThreadId
0x1400aabba  nop     dword ptr [rax+rax+00h]
0x1400aabbf  mov     [rsp+0D0h+var_90], rsi
0x1400aabc4  mov     r9d, 1
0x1400aabca  mov     [rsp+0D0h+var_98], eax
0x1400aabce  xor     r8d, r8d
0x1400aabd1  mov     [rsp+0D0h+var_A0], 4B1h
0x1400aabd9  lea     rax, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400aabe0  mov     [rsp+0D0h+var_A8], r14
0x1400aabe5  mov     edx, r15d
0x1400aabe8  mov     [rsp+0D0h+lpOverlapped], rax
0x1400aabed  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400aabf2  mov     rcx, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400aabf9  mov     [rbp+57h+var_70], rax
0x1400aabfd  test    rcx, rcx
0x1400aac00  jz      short loc_1400AAC44
0x1400aac02  cmp     [rcx+40h], esi
0x1400aac05  jz      short loc_1400AAC44
0x1400aac07  cmp     dword ptr [rcx+38h], 3
0x1400aac0b  jl      short loc_1400AAC44
0x1400aac0d  lea     rcx, aAsyncunbuffere_37; "AsyncUnbufferedFileWriter::FlushInterna"...
0x1400aac14  mov     [rbp+57h+var_50], 4B2h
0x1400aac1b  mov     [rbp+57h+var_58], rcx
0x1400aac1f  lea     rdx, aIgnoredFailedT_37; "(Ignored) Failed to cancel I/O. Error:%"...
0x1400aac26  lea     rcx, aAsyn; "ASYN"
0x1400aac2d  mov     [rbp+57h+var_4C], 3
0x1400aac34  mov     [rbp+57h+var_48], rcx
0x1400aac38  mov     r8, rax
0x1400aac3b  lea     rcx, [rbp+57h+var_58]
0x1400aac3f  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400aac44  lea     rcx, [rbp+57h+var_70]; struct FrsStatus **
0x1400aac48  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400aac4d  mov     eax, [rdi+50h]
0x1400aac50  inc     ebx
0x1400aac52  cmp     ebx, eax
0x1400aac54  jb      loc_1400AAB6F
0x1400aac5a  mov     r13d, dword ptr [rbp+57h+arg_0]
0x1400aac5e  mov     rcx, r12
0x1400aac61  mov     r14, [rbp+57h+var_80]
0x1400aac65  mov     r8, [rbp+57h+arg_18]
0x1400aac69  jmp     short loc_1400AAC79
0x1400aac6b  mov     r13d, dword ptr [rbp+57h+arg_0]
0x1400aac6f  jmp     short loc_1400AAC79
0x1400aac71  mov     r8, [rbp+57h+arg_18]
0x1400aac75  mov     rcx, [rbp+57h+arg_10]
0x1400aac79  test    eax, eax
0x1400aac7b  jz      loc_1400AADAB
0x1400aac81  lea     r15, aAsyncunbuffere_14; "AsyncUnbufferedFileWriter::FlushInterna"...
0x1400aac88  lea     r12, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400aac8f  mov     edx, [rdi+5Ch]
0x1400aac92  mov     r9d, 1; bWait
0x1400aac98  mov     rcx, [rcx]; hFile
0x1400aac9b  shl     rdx, 5
0x1400aac9f  add     rdx, [r8]; lpOverlapped
0x1400aaca2  lea     r8, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x1400aaca6  mov     [rbp+57h+NumberOfBytesWritten], esi
0x1400aaca9  call    cs:__imp_GetOverlappedResult
0x1400aacb0  nop     dword ptr [rax+rax+00h]
0x1400aacb5  test    eax, eax
0x1400aacb7  jnz     loc_1400AAD8C
0x1400aacbd  call    cs:__imp_GetCurrentThreadId
0x1400aacc4  nop     dword ptr [rax+rax+00h]
0x1400aacc9  mov     ebx, eax
0x1400aaccb  call    cs:__imp_GetLastError
0x1400aacd2  nop     dword ptr [rax+rax+00h]
0x1400aacd7  mov     [rsp+0D0h+var_90], rsi
0x1400aacdc  mov     r9d, 1
0x1400aace2  mov     [rsp+0D0h+var_98], ebx
0x1400aace6  xor     r8d, r8d
0x1400aace9  mov     [rsp+0D0h+var_A0], 4C5h
0x1400aacf1  mov     edx, eax
0x1400aacf3  mov     [rsp+0D0h+var_A8], r15
0x1400aacf8  mov     [rsp+0D0h+lpOverlapped], r12
0x1400aacfd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400aad02  mov     [rbp+57h+arg_0], rax
0x1400aad06  mov     r8, rax
0x1400aad09  test    r13d, r13d
0x1400aad0c  jz      short loc_1400AAD2E
0x1400aad0e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400aad15  test    rax, rax
0x1400aad18  jz      short loc_1400AAD83
0x1400aad1a  cmp     [rax+40h], esi
0x1400aad1d  jz      short loc_1400AAD83
0x1400aad1f  cmp     dword ptr [rax+38h], 3
0x1400aad23  jl      short loc_1400AAD83
0x1400aad25  mov     [rbp+57h+var_50], 4C8h
0x1400aad2c  jmp     short loc_1400AAD56
0x1400aad2e  test    r14, r14
0x1400aad31  jnz     short loc_1400AAD38
0x1400aad33  mov     r14, r8
0x1400aad36  jmp     short loc_1400AAD8C
0x1400aad38  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400aad3f  test    rax, rax
0x1400aad42  jz      short loc_1400AAD83
0x1400aad44  cmp     [rax+40h], esi
0x1400aad47  jz      short loc_1400AAD83
0x1400aad49  cmp     dword ptr [rax+38h], 3
0x1400aad4d  jl      short loc_1400AAD83
0x1400aad4f  mov     [rbp+57h+var_50], 4D1h
0x1400aad56  lea     rax, aAsyncunbuffere_37; "AsyncUnbufferedFileWriter::FlushInterna"...
0x1400aad5d  mov     [rbp+57h+var_4C], 3
0x1400aad64  mov     [rbp+57h+var_58], rax
0x1400aad68  lea     rdx, aIgnoredFailedT_92; "(Ignored) Failed to wait for I/O to com"...
0x1400aad6f  lea     rax, aAsyn; "ASYN"
  ... truncated ...
```
