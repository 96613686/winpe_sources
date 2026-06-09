# AsyncUnbufferedFileWriter::GetNextWriteBuffer(void)

- ea: `0x1400abe38`
- end: `0x1400ac139`
- name: `?GetNextWriteBuffer@AsyncUnbufferedFileWriter@@AEAAPEAVFrsStatus@@XZ`
- size: `769`
- prototype: `struct FrsStatus *__fastcall(AsyncUnbufferedFileWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400ae400`

## callees

- `0x1400abe38`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x1400abecb`
- `KERNEL32!GetOverlappedResult` at `0x1400abecb`
- `KERNEL32!WriteFile` at `0x1400ac006`
- `KERNEL32!WriteFile` at `0x1400ac006`
- `KERNEL32!GetLastError` at `0x1400abeed`
- `KERNEL32!GetLastError` at `0x1400ac016`
- `KERNEL32!GetLastError` at `0x1400abeed`
- `KERNEL32!GetLastError` at `0x1400ac016`
- `KERNEL32!GetCurrentThreadId` at `0x1400abf02`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac02c`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac0d6`
- `KERNEL32!GetCurrentThreadId` at `0x1400abf02`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac02c`
- `KERNEL32!GetCurrentThreadId` at `0x1400ac0d6`

## string_xrefs

- `0x1400abf20`: `AsyncUnbufferedFileWriter::GetNextWriteBuffer`
- `0x1400abf9c`: `AsyncUnbufferedFileWriter::GetNextWriteBuffer`
- `0x1400ac0f5`: `AsyncUnbufferedFileWriter::GetNextWriteBuffer`

## pseudocode

```c
struct FrsStatus *__fastcall AsyncUnbufferedFileWriter::GetNextWriteBuffer(AsyncUnbufferedFileWriter *this)
{
  __int64 v1; // rdi
  unsigned int *v3; // rsi
  unsigned int v4; // eax
  int v5; // edx
  unsigned int v6; // r15d
  int v7; // r12d
  _DWORD *v8; // r14
  int v9; // r8d
  char *v10; // rcx
  void *v11; // rcx
  struct _OVERLAPPED *v12; // rdx
  unsigned int v13; // edx
  DWORD LastError; // ebp
  DWORD CurrentThreadId; // eax
  __int64 v16; // rcx
  _DWORD *v17; // rax
  unsigned __int64 v18; // rdx
  unsigned int v19; // ebp
  DWORD v20; // r14d
  DWORD v21; // eax
  __int64 v22; // rcx
  bool v23; // zf
  int v24; // eax
  unsigned int v25; // edx
  unsigned int v26; // eax
  DWORD v27; // eax
  __int64 v28; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+90h] [rbp+8h] BYREF
  int v31; // [rsp+98h] [rbp+10h]
  int v32; // [rsp+A0h] [rbp+18h]

  v1 = 0;
  NumberOfBytesTransferred = 0;
  v3 = 0;
  v4 = *((_DWORD *)this + 22) + 1;
  v31 = 0;
  v5 = v4 % *((_DWORD *)this + 13);
  ++*((_DWORD *)this + 21);
  v6 = 0;
  v32 = v5;
  v7 = 0;
  while ( !v3 )
  {
    while ( !v3 )
    {
      v8 = (_DWORD *)((char *)this + 80);
      v9 = *((_DWORD *)this + 20);
      v10 = (char *)this + 80;
      if ( !v9 )
        goto LABEL_10;
      v11 = (void *)*((_QWORD *)this + 2);
      v12 = (struct _OVERLAPPED *)(*((_QWORD *)this + 9) + 32LL * *((unsigned int *)this + 23));
      v23 = *((_DWORD *)this + 21) + v9 == *((_DWORD *)this + 13);
      NumberOfBytesTransferred = 0;
      if ( GetOverlappedResult(v11, v12, &NumberOfBytesTransferred, v23) )
      {
        v13 = (unsigned int)(*((_DWORD *)this + 23) + 1) % *((_DWORD *)this + 13);
        --*v8;
        *((_DWORD *)this + 23) = v13;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError == 996 )
        {
          ++*((_DWORD *)this + 31);
          v10 = (char *)this + 80;
LABEL_10:
          v17 = (_DWORD *)((char *)this + 80);
          v18 = (unsigned int)(*((_DWORD *)this + 14) * *((_DWORD *)this + 13));
          if ( *((_QWORD *)this + 4) > v18 )
          {
            v17 = v10;
            if ( !*v8 )
              ++*((_DWORD *)this + 28);
          }
          if ( v7 || (v6 = *((_DWORD *)this + 21), !*v17) && v6 != *((_DWORD *)this + 13) && *((_QWORD *)this + 4) < v18 )
          {
            v6 = 0;
            v19 = 0;
            goto LABEL_19;
          }
          break;
        }
        CurrentThreadId = GetCurrentThreadId();
        v3 = (unsigned int *)FrsStatusList::PushNewError(
                               v16,
                               LastError,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                               "AsyncUnbufferedFileWriter::GetNextWriteBuffer",
                               967,
                               CurrentThreadId,
                               0);
      }
    }
    v19 = 0;
    if ( v3 )
      break;
LABEL_19:
    while ( v19 < v6 )
    {
      *(_QWORD *)(32LL * *((unsigned int *)this + 24) + *((_QWORD *)this + 9) + 16) = *((_QWORD *)this + 13);
      if ( WriteFile(
             *((HANDLE *)this + 2),
             *(LPCVOID *)(*((_QWORD *)this + 8) + 8LL * *((unsigned int *)this + 24)),
             *((_DWORD *)this + 14),
             &NumberOfBytesTransferred,
             (LPOVERLAPPED)(*((_QWORD *)this + 9) + 32LL * *((unsigned int *)this + 24))) )
      {
        ++*((_DWORD *)this + 30);
      }
      else
      {
        v20 = GetLastError();
        if ( v20 == 997 )
        {
          ++*((_DWORD *)this + 29);
        }
        else
        {
          v21 = GetCurrentThreadId();
          v3 = (unsigned int *)FrsStatusList::PushNewError(
                                 v22,
                                 v20,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                                 "AsyncUnbufferedFileWriter::GetNextWriteBuffer",
                                 1018,
                                 v21,
                                 0);
        }
      }
      v23 = v3 == 0;
      if ( v3 )
        goto LABEL_28;
      *((_QWORD *)this + 13) += *((unsigned int *)this + 14);
      v24 = *((_DWORD *)this + 24);
      ++*((_DWORD *)this + 20);
      v25 = (unsigned int)(v24 + 1) % *((_DWORD *)this + 13);
      --*((_DWORD *)this + 21);
      *((_DWORD *)this + 24) = v25;
      ++v19;
    }
    v23 = v3 == 0;
LABEL_28:
    v7 = v31;
    if ( v23 )
    {
      v7 = 1;
      v26 = *((_DWORD *)this + 21) + *((_DWORD *)this + 20);
      v31 = 1;
      if ( v26 < *((_DWORD *)this + 13) )
      {
        *((_DWORD *)this + 22) = v32;
        *((_DWORD *)this + 25) = 0;
        return (struct FrsStatus *)v1;
      }
    }
  }
  v27 = GetCurrentThreadId();
  return (struct FrsStatus *)FrsStatusList::PushNewError(
                               v28,
                               v3[1],
                               v3[2],
                               *v3,
                               "base\\fs\\remotefs\\frs\\src\\fs\\asyncio.cpp",
                               "AsyncUnbufferedFileWriter::GetNextWriteBuffer",
                               1058,
                               v27,
                               v3);
}

```

## disassembly

```asm
0x1400abe38  mov     rax, rsp
0x1400abe3b  mov     [rax+20h], rbx
0x1400abe3f  push    rbp
0x1400abe40  push    rsi
0x1400abe41  push    rdi
0x1400abe42  push    r12
0x1400abe44  push    r13
0x1400abe46  push    r14
0x1400abe48  push    r15
0x1400abe4a  sub     rsp, 50h
0x1400abe4e  xor     edi, edi
0x1400abe50  xor     edx, edx
0x1400abe52  mov     [rax+8], edi
0x1400abe55  mov     rbx, rcx
0x1400abe58  mov     eax, [rcx+58h]
0x1400abe5b  mov     esi, edi
0x1400abe5d  inc     eax
0x1400abe5f  mov     [rsp+88h+arg_8], edi
0x1400abe66  div     dword ptr [rcx+34h]
0x1400abe69  inc     dword ptr [rcx+54h]
0x1400abe6c  mov     r15d, edi
0x1400abe6f  mov     [rsp+88h+arg_10], edx
0x1400abe76  mov     r12d, edi
0x1400abe79  test    rsi, rsi
0x1400abe7c  jnz     loc_1400AC0D6
0x1400abe82  test    rsi, rsi
0x1400abe85  jnz     loc_1400ABF91
0x1400abe8b  lea     r14, [rbx+50h]
0x1400abe8f  mov     r8d, [r14]
0x1400abe92  mov     rcx, r14
0x1400abe95  test    r8d, r8d
0x1400abe98  jz      loc_1400ABF56
0x1400abe9e  add     r8d, [rbx+54h]
0x1400abea2  mov     r9d, edi
0x1400abea5  mov     edx, [rbx+5Ch]
0x1400abea8  mov     rcx, [rbx+10h]; hFile
0x1400abeac  shl     rdx, 5
0x1400abeb0  add     rdx, [rbx+48h]; lpOverlapped
0x1400abeb4  cmp     r8d, [rbx+34h]
0x1400abeb8  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400abec0  mov     [rsp+88h+NumberOfBytesTransferred], edi
0x1400abec7  setz    r9b; bWait
0x1400abecb  call    cs:__imp_GetOverlappedResult
0x1400abed2  nop     dword ptr [rax+rax+00h]
0x1400abed7  test    eax, eax
0x1400abed9  jz      short loc_1400ABEED
0x1400abedb  mov     eax, [rbx+5Ch]
0x1400abede  xor     edx, edx
0x1400abee0  inc     eax
0x1400abee2  div     dword ptr [rbx+34h]
0x1400abee5  dec     dword ptr [r14]
0x1400abee8  mov     [rbx+5Ch], edx
0x1400abeeb  jmp     short loc_1400ABE82
0x1400abeed  call    cs:__imp_GetLastError
0x1400abef4  nop     dword ptr [rax+rax+00h]
0x1400abef9  mov     ebp, eax
0x1400abefb  cmp     eax, 3E4h
0x1400abf00  jz      short loc_1400ABF4F
0x1400abf02  call    cs:__imp_GetCurrentThreadId
0x1400abf09  nop     dword ptr [rax+rax+00h]
0x1400abf0e  mov     [rsp+88h+var_48], rdi
0x1400abf13  mov     r9d, 1
0x1400abf19  mov     [rsp+88h+var_50], eax
0x1400abf1d  xor     r8d, r8d
0x1400abf20  lea     rax, aAsyncunbuffere_7; "AsyncUnbufferedFileWriter::GetNextWrite"...
0x1400abf27  mov     [rsp+88h+var_58], 3C7h
0x1400abf2f  mov     [rsp+88h+var_60], rax
0x1400abf34  mov     edx, ebp
0x1400abf36  lea     rax, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400abf3d  mov     [rsp+88h+lpOverlapped], rax
0x1400abf42  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400abf47  mov     rsi, rax
0x1400abf4a  jmp     loc_1400ABE82
0x1400abf4f  inc     dword ptr [rbx+7Ch]
0x1400abf52  lea     rcx, [rbx+50h]
0x1400abf56  mov     edx, [rbx+34h]
0x1400abf59  mov     rax, r14
0x1400abf5c  imul    edx, [rbx+38h]
0x1400abf60  cmp     [rbx+20h], rdx
0x1400abf64  jbe     short loc_1400ABF71
0x1400abf66  mov     rax, rcx
0x1400abf69  cmp     [r14], edi
0x1400abf6c  jnz     short loc_1400ABF71
0x1400abf6e  inc     dword ptr [rbx+70h]
0x1400abf71  test    r12d, r12d
0x1400abf74  jz      short loc_1400ABF7D
0x1400abf76  mov     r15d, edi
0x1400abf79  mov     ebp, edi
0x1400abf7b  jmp     short loc_1400ABF9C
0x1400abf7d  mov     r15d, [rbx+54h]
0x1400abf81  cmp     [rax], edi
0x1400abf83  jnz     short loc_1400ABF91
0x1400abf85  cmp     r15d, [rbx+34h]
0x1400abf89  jz      short loc_1400ABF91
0x1400abf8b  cmp     [rbx+20h], rdx
0x1400abf8f  jb      short loc_1400ABF76
0x1400abf91  mov     ebp, edi
0x1400abf93  test    rsi, rsi
0x1400abf96  jnz     loc_1400AC0D6
0x1400abf9c  lea     r13, aAsyncunbuffere_7; "AsyncUnbufferedFileWriter::GetNextWrite"...
0x1400abfa3  lea     r12, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400abfaa  cmp     ebp, r15d
0x1400abfad  jnb     loc_1400AC097
0x1400abfb3  mov     edx, [rbx+60h]
0x1400abfb6  lea     r9, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesWritten
0x1400abfbe  mov     rcx, [rbx+48h]
0x1400abfc2  mov     eax, [rbx+68h]
0x1400abfc5  shl     rdx, 5
0x1400abfc9  mov     [rdx+rcx+10h], eax
0x1400abfcd  mov     ecx, [rbx+60h]
0x1400abfd0  mov     rax, [rbx+48h]
0x1400abfd4  mov     rdx, [rbx+68h]
0x1400abfd8  shl     rcx, 5
0x1400abfdc  shr     rdx, 20h
0x1400abfe0  mov     [rcx+rax+14h], edx
0x1400abfe4  mov     edx, [rbx+60h]
0x1400abfe7  mov     rax, [rbx+40h]
0x1400abfeb  mov     ecx, edx
0x1400abfed  mov     r8d, [rbx+38h]; nNumberOfBytesToWrite
0x1400abff1  shl     rcx, 5
0x1400abff5  add     rcx, [rbx+48h]
0x1400abff9  mov     rdx, [rax+rdx*8]; lpBuffer
0x1400abffd  mov     [rsp+88h+lpOverlapped], rcx; lpOverlapped
0x1400ac002  mov     rcx, [rbx+10h]; hFile
0x1400ac006  call    cs:__imp_WriteFile
0x1400ac00d  nop     dword ptr [rax+rax+00h]
0x1400ac012  test    eax, eax
0x1400ac014  jnz     short loc_1400AC06E
0x1400ac016  call    cs:__imp_GetLastError
0x1400ac01d  nop     dword ptr [rax+rax+00h]
0x1400ac022  mov     r14d, eax
0x1400ac025  cmp     eax, 3E5h
0x1400ac02a  jz      short loc_1400AC069
0x1400ac02c  call    cs:__imp_GetCurrentThreadId
0x1400ac033  nop     dword ptr [rax+rax+00h]
0x1400ac038  mov     [rsp+88h+var_48], rdi
0x1400ac03d  mov     r9d, 1
0x1400ac043  mov     [rsp+88h+var_50], eax
0x1400ac047  xor     r8d, r8d
0x1400ac04a  mov     [rsp+88h+var_58], 3FAh
0x1400ac052  mov     edx, r14d
0x1400ac055  mov     [rsp+88h+var_60], r13
0x1400ac05a  mov     [rsp+88h+lpOverlapped], r12
0x1400ac05f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ac064  mov     rsi, rax
0x1400ac067  jmp     short loc_1400AC071
0x1400ac069  inc     dword ptr [rbx+74h]
0x1400ac06c  jmp     short loc_1400AC071
0x1400ac06e  inc     dword ptr [rbx+78h]
0x1400ac071  test    rsi, rsi
0x1400ac074  jnz     short loc_1400AC09A
0x1400ac076  mov     eax, [rbx+38h]
0x1400ac079  xor     edx, edx
0x1400ac07b  add     [rbx+68h], rax
0x1400ac07f  mov     eax, [rbx+60h]
0x1400ac082  inc     dword ptr [rbx+50h]
0x1400ac085  inc     eax
0x1400ac087  div     dword ptr [rbx+34h]
0x1400ac08a  dec     dword ptr [rbx+54h]
0x1400ac08d  mov     [rbx+60h], edx
0x1400ac090  inc     ebp
0x1400ac092  jmp     loc_1400ABFAA
0x1400ac097  test    rsi, rsi
0x1400ac09a  mov     r12d, [rsp+88h+arg_8]
0x1400ac0a2  mov     r13d, [rsp+88h+arg_10]
0x1400ac0aa  jnz     loc_1400ABE79
0x1400ac0b0  mov     eax, [rbx+50h]
0x1400ac0b3  mov     r12d, 1
0x1400ac0b9  add     eax, [rbx+54h]
0x1400ac0bc  mov     [rsp+88h+arg_8], r12d
0x1400ac0c4  cmp     eax, [rbx+34h]
0x1400ac0c7  jnb     loc_1400ABE79
0x1400ac0cd  mov     [rbx+58h], r13d
0x1400ac0d1  mov     [rbx+64h], edi
0x1400ac0d4  jmp     short loc_1400AC11D
0x1400ac0d6  call    cs:__imp_GetCurrentThreadId
0x1400ac0dd  nop     dword ptr [rax+rax+00h]
0x1400ac0e2  mov     r9d, [rsi]
0x1400ac0e5  mov     r8d, [rsi+8]
0x1400ac0e9  mov     edx, [rsi+4]
0x1400ac0ec  mov     [rsp+88h+var_48], rsi
0x1400ac0f1  mov     [rsp+88h+var_50], eax
0x1400ac0f5  lea     rax, aAsyncunbuffere_7; "AsyncUnbufferedFileWriter::GetNextWrite"...
0x1400ac0fc  mov     [rsp+88h+var_58], 422h
0x1400ac104  mov     [rsp+88h+var_60], rax
0x1400ac109  lea     rax, aBaseFsRemotefs_14; "base\\fs\\remotefs\\frs\\src\\fs\\async"...
0x1400ac110  mov     [rsp+88h+lpOverlapped], rax
0x1400ac115  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400ac11a  mov     rdi, rax
0x1400ac11d  mov     rbx, [rsp+88h+arg_18]
0x1400ac125  mov     rax, rdi
0x1400ac128  add     rsp, 50h
0x1400ac12c  pop     r15
0x1400ac12e  pop     r14
0x1400ac130  pop     r13
0x1400ac132  pop     r12
0x1400ac134  pop     rdi
0x1400ac135  pop     rsi
0x1400ac136  pop     rbp
0x1400ac137  retn
```
