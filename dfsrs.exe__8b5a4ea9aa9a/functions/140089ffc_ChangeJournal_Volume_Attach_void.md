# ChangeJournal::Volume::Attach(void)

- ea: `0x140089ffc`
- end: `0x14008a194`
- name: `?Attach@Volume@ChangeJournal@@QEAAPEAVFrsStatus@@XZ`
- size: `408`
- prototype: `struct FrsStatus *__fastcall(ULONG_PTR CompletionKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140089e20`

## callees

- `0x14005c620`
- `0x140089ffc`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14008a03f`
- `KERNEL32!CreateFileW` at `0x14008a084`
- `KERNEL32!CreateFileW` at `0x14008a03f`
- `KERNEL32!CreateFileW` at `0x14008a084`
- `KERNEL32!CreateIoCompletionPort` at `0x14008a0c6`
- `KERNEL32!CreateIoCompletionPort` at `0x14008a0c6`
- `KERNEL32!GetLastError` at `0x14008a0e9`
- `KERNEL32!GetLastError` at `0x14008a127`
- `KERNEL32!GetLastError` at `0x14008a0e9`
- `KERNEL32!GetLastError` at `0x14008a127`
- `KERNEL32!GetCurrentThreadId` at `0x14008a107`
- `KERNEL32!GetCurrentThreadId` at `0x14008a13d`
- `KERNEL32!GetCurrentThreadId` at `0x14008a107`
- `KERNEL32!GetCurrentThreadId` at `0x14008a13d`

## pseudocode

```c
struct FrsStatus *__fastcall ChangeJournal::Volume::Attach(ULONG_PTR CompletionKey)
{
  char *FileW; // rax
  HANDLE *v3; // rsi
  void **v4; // rdi
  DWORD v6; // eax
  void **v7; // rcx
  DWORD v8; // ebx
  __int64 v9; // rcx
  DWORD LastError; // eax
  void **v11; // rcx
  DWORD v12; // ebx
  __int64 v13; // rcx
  DWORD v14; // [rsp+38h] [rbp-20h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-20h]

  FileW = (char *)CreateFileW(
                    (LPCWSTR)(*(_QWORD *)(*(_QWORD *)(CompletionKey + 104) + 176LL) + 18LL),
                    0x80000000,
                    3u,
                    0,
                    3u,
                    0x40000000u,
                    0);
  v3 = (HANDLE *)(CompletionKey + 112);
  *(_QWORD *)(CompletionKey + 112) = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    *(_QWORD *)(CompletionKey + 120) = CreateFileW(
                                         (LPCWSTR)(*(_QWORD *)(*(_QWORD *)(CompletionKey + 104) + 176LL) + 18LL),
                                         0x80000000,
                                         3u,
                                         0,
                                         3u,
                                         0,
                                         0);
  if ( (char *)*v3 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL
    || (v4 = (void **)(CompletionKey + 120),
        (unsigned __int64)(*(_QWORD *)(CompletionKey + 120) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL) )
  {
    LastError = GetLastError();
    v11 = (void **)(CompletionKey + 112);
    v12 = LastError;
    CloseHandleEx(v11);
    CurrentThreadId = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v13,
                                 v12,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\db\\changejournal.cpp",
                                 "ChangeJournal::Volume::Attach",
                                 150,
                                 CurrentThreadId,
                                 0);
  }
  else if ( (char *)CreateIoCompletionPort(*v3, *(HANDLE *)(*(_QWORD *)(CompletionKey + 96) + 8LL), CompletionKey, 1u)
          - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v6 = GetLastError();
    v7 = (void **)(CompletionKey + 112);
    v8 = v6;
    CloseHandleEx(v7);
    CloseHandleEx(v4);
    v14 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v9,
                                 v8,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\db\\changejournal.cpp",
                                 "ChangeJournal::Volume::Attach",
                                 167,
                                 v14,
                                 0);
  }
  else
  {
    *(_DWORD *)(CompletionKey + 88) = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x140089ffc  mov     [rsp+arg_0], rbx
0x14008a001  mov     [rsp+arg_8], rsi
0x14008a006  push    rdi
0x14008a007  sub     rsp, 50h
0x14008a00b  mov     rax, [rcx+68h]
0x14008a00f  mov     rbx, rcx
0x14008a012  and     [rsp+58h+var_28], 0
0x14008a018  mov     edi, 3
0x14008a01d  mov     [rsp+58h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x14008a025  xor     r9d, r9d; lpSecurityAttributes
0x14008a028  mov     r8d, edi; dwShareMode
0x14008a02b  mov     [rsp+58h+dwCreationDisposition], edi; dwCreationDisposition
0x14008a02f  mov     rcx, [rax+0B0h]
0x14008a036  mov     edx, 80000000h; dwDesiredAccess
0x14008a03b  add     rcx, 12h; lpFileName
0x14008a03f  call    cs:__imp_CreateFileW
0x14008a046  nop     dword ptr [rax+rax+00h]
0x14008a04b  lea     rsi, [rbx+70h]
0x14008a04f  mov     [rsi], rax
0x14008a052  dec     rax
0x14008a055  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14008a059  ja      short loc_14008A094
0x14008a05b  and     [rsp+58h+var_28], 0
0x14008a061  xor     r9d, r9d; lpSecurityAttributes
0x14008a064  mov     rax, [rbx+68h]
0x14008a068  mov     r8d, edi; dwShareMode
0x14008a06b  and     [rsp+58h+dwFlagsAndAttributes], 0
0x14008a070  mov     edx, 80000000h; dwDesiredAccess
0x14008a075  mov     [rsp+58h+dwCreationDisposition], edi; dwCreationDisposition
0x14008a079  mov     rcx, [rax+0B0h]
0x14008a080  add     rcx, 12h; lpFileName
0x14008a084  call    cs:__imp_CreateFileW
0x14008a08b  nop     dword ptr [rax+rax+00h]
0x14008a090  mov     [rbx+78h], rax
0x14008a094  mov     rcx, [rsi]; FileHandle
0x14008a097  lea     rax, [rcx-1]
0x14008a09b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14008a09f  ja      loc_14008A127
0x14008a0a5  lea     rdi, [rbx+78h]
0x14008a0a9  mov     rax, [rdi]
0x14008a0ac  dec     rax
0x14008a0af  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14008a0b3  ja      short loc_14008A127
0x14008a0b5  mov     rdx, [rbx+60h]
0x14008a0b9  mov     r9d, 1; NumberOfConcurrentThreads
0x14008a0bf  mov     r8, rbx; CompletionKey
0x14008a0c2  mov     rdx, [rdx+8]; ExistingCompletionPort
0x14008a0c6  call    cs:__imp_CreateIoCompletionPort
0x14008a0cd  nop     dword ptr [rax+rax+00h]
0x14008a0d2  dec     rax
0x14008a0d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14008a0d9  ja      short loc_14008A0E9
0x14008a0db  mov     dword ptr [rbx+58h], 1
0x14008a0e2  xor     eax, eax
0x14008a0e4  jmp     loc_14008A183
0x14008a0e9  call    cs:__imp_GetLastError
0x14008a0f0  nop     dword ptr [rax+rax+00h]
0x14008a0f5  mov     rcx, rsi; void **
0x14008a0f8  mov     ebx, eax
0x14008a0fa  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14008a0ff  mov     rcx, rdi; void **
0x14008a102  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14008a107  call    cs:__imp_GetCurrentThreadId
0x14008a10e  nop     dword ptr [rax+rax+00h]
0x14008a113  and     [rsp+58h+var_18], 0
0x14008a119  mov     [rsp+58h+var_20], eax
0x14008a11d  mov     dword ptr [rsp+58h+var_28], 0A7h
0x14008a125  jmp     short loc_14008A15B
0x14008a127  call    cs:__imp_GetLastError
0x14008a12e  nop     dword ptr [rax+rax+00h]
0x14008a133  mov     rcx, rsi; void **
0x14008a136  mov     ebx, eax
0x14008a138  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14008a13d  call    cs:__imp_GetCurrentThreadId
0x14008a144  nop     dword ptr [rax+rax+00h]
0x14008a149  and     [rsp+58h+var_18], 0
0x14008a14f  mov     [rsp+58h+var_20], eax
0x14008a153  mov     dword ptr [rsp+58h+var_28], 96h
0x14008a15b  lea     rax, aChangejournalV_10; "ChangeJournal::Volume::Attach"
0x14008a162  mov     r9d, 1
0x14008a168  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rax
0x14008a16d  xor     r8d, r8d
0x14008a170  lea     rax, aBaseFsRemotefs_27; "base\\fs\\remotefs\\frs\\src\\db\\chang"...
0x14008a177  mov     edx, ebx
0x14008a179  mov     qword ptr [rsp+58h+dwCreationDisposition], rax
0x14008a17e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14008a183  mov     rbx, [rsp+58h+arg_0]
0x14008a188  mov     rsi, [rsp+58h+arg_8]
0x14008a18d  add     rsp, 50h
0x14008a191  pop     rdi
0x14008a192  retn
```
