# CDCMPoolManager::InitializeSweeperThreads(void)

- ea: `0x18005eed8`
- end: `0x18005f122`
- name: `?InitializeSweeperThreads@CDCMPoolManager@@AEAA_NXZ`
- size: `586`
- prototype: `bool __fastcall(CDCMPoolManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18005eba4`

## callees

- `0x180011bcc`
- `0x18005b280`
- `0x18005d910`
- `0x18005eed8`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18005ef69`
- `MSDART!MpHeapAlloc` at `0x18005ef9a`
- `MSDART!MpHeapAlloc` at `0x18005efcc`
- `MSDART!MpHeapAlloc` at `0x18005ef69`
- `MSDART!MpHeapAlloc` at `0x18005ef9a`
- `MSDART!MpHeapAlloc` at `0x18005efcc`
- `KERNEL32!TerminateThread` at `0x18005f10f`
- `KERNEL32!TerminateThread` at `0x18005f10f`
- `KERNEL32!CreateThread` at `0x18005f03b`
- `KERNEL32!CreateThread` at `0x18005f06e`
- `KERNEL32!CreateThread` at `0x18005f03b`
- `KERNEL32!CreateThread` at `0x18005f06e`
- `KERNEL32!CreateEventW` at `0x18005ef19`
- `KERNEL32!CreateEventW` at `0x18005ef34`
- `KERNEL32!CreateEventW` at `0x18005ef19`
- `KERNEL32!CreateEventW` at `0x18005ef34`
- `KERNEL32!CloseHandle` at `0x18005f0f0`
- `KERNEL32!CloseHandle` at `0x18005f0fe`
- `KERNEL32!CloseHandle` at `0x18005f0f0`
- `KERNEL32!CloseHandle` at `0x18005f0fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
char __fastcall CDCMPoolManager::InitializeSweeperThreads(CDCMPoolManager *this)
{
  HANDLE EventW; // r15
  void *v3; // r14
  void **v4; // rsi
  HANDLE v5; // rax
  union _SLIST_HEADER *v6; // rax
  union _SLIST_HEADER *v7; // rax
  void **v8; // rax
  void *v9; // rdx
  HANDLE v10; // rax
  HANDLE v11; // rax
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  DWORD ThreadId; // [rsp+88h] [rbp+10h] BYREF
  HANDLE v17; // [rsp+90h] [rbp+18h]
  HANDLE v18; // [rsp+98h] [rbp+20h]

  if ( g_dwQueueSize )
  {
    EventW = 0;
    v3 = 0;
    v4 = (void **)((char *)this + 80);
    if ( *((_QWORD *)this + 10) )
      goto LABEL_14;
    EventW = CreateEventW(0, 0, 0, 0);
    v17 = EventW;
    v5 = CreateEventW(0, 0, 0, 0);
    v3 = v5;
    v18 = v5;
    if ( EventW )
    {
      if ( v5 )
      {
        v6 = (union _SLIST_HEADER *)MpHeapAlloc(g_hHeapHandle, 19922944, 48);
        if ( v6 )
          v6 = (union _SLIST_HEADER *)_tagCQueue<CSweepInfo>::_tagCQueue<CSweepInfo>(v6);
        *v4 = v6;
        v7 = (union _SLIST_HEADER *)MpHeapAlloc(g_hHeapHandle, 19922944, 48);
        if ( v7 )
          v7 = (union _SLIST_HEADER *)_tagCQueue<CSweepInfo>::_tagCQueue<CSweepInfo>(v7);
        *((_QWORD *)this + 11) = v7;
        v8 = (void **)MpHeapAlloc(g_hHeapHandle, 19922944, 16);
        if ( v8 )
        {
          v9 = (void *)*((_QWORD *)this + 11);
          *v8 = *v4;
          v8[1] = v9;
        }
        *((_QWORD *)this + 12) = v8;
        if ( !*v4 )
          goto LABEL_19;
        if ( *((_QWORD *)this + 11) && v8 )
        {
LABEL_14:
          ThreadId = 0;
          v10 = CreateThread(0, 0, ReleaseResourceThread, *((LPVOID *)this + 11), 0, &ThreadId);
          *((_QWORD *)this + 8) = v10;
          if ( v10 )
          {
            v11 = CreateThread(0, 0, ResetResourceThread, *((LPVOID *)this + 12), 0, &ThreadId);
            *((_QWORD *)this + 9) = v11;
            if ( v11 )
              return 1;
          }
        }
      }
    }
    if ( *v4 )
    {
      _tagCQueue<CSweepInfo>::`scalar deleting destructor'(*v4);
      *v4 = 0;
      EventW = 0;
    }
LABEL_19:
    v13 = (void *)*((_QWORD *)this + 11);
    if ( v13 )
    {
      _tagCQueue<CSweepInfo>::`scalar deleting destructor'(v13);
      *((_QWORD *)this + 11) = 0;
      v3 = 0;
    }
    v14 = (void *)*((_QWORD *)this + 12);
    if ( v14 )
    {
      operator delete(v14);
      *((_QWORD *)this + 12) = 0;
    }
    if ( v3 )
      CloseHandle(v3);
    if ( EventW )
      CloseHandle(EventW);
    v15 = (void *)*((_QWORD *)this + 8);
    if ( v15 )
      TerminateThread(v15, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18005eed8  mov     [rsp+arg_0], rcx
0x18005eedd  push    rsi
0x18005eede  push    rdi
0x18005eedf  push    r14
0x18005eee1  push    r15
0x18005eee3  sub     rsp, 58h
0x18005eee7  mov     rdi, rcx
0x18005eeea  cmp     cs:?g_dwQueueSize@@3KA, 0; ulong g_dwQueueSize
0x18005eef1  jz      loc_18005F115
0x18005eef7  xor     r15d, r15d
0x18005eefa  xor     r14d, r14d
0x18005eefd  lea     rsi, [rcx+50h]
0x18005ef01  mov     [rsp+78h+var_40], rsi
0x18005ef06  cmp     [rsi], r14
0x18005ef09  jnz     loc_18005F00C
0x18005ef0f  xor     r9d, r9d; lpName
0x18005ef12  xor     r8d, r8d; bInitialState
0x18005ef15  xor     edx, edx; bManualReset
0x18005ef17  xor     ecx, ecx; lpEventAttributes
0x18005ef19  call    cs:__imp_CreateEventW
0x18005ef1f  mov     r15, rax
0x18005ef22  mov     [rsp+78h+arg_10], rax
0x18005ef2a  xor     r9d, r9d; lpName
0x18005ef2d  xor     r8d, r8d; bInitialState
0x18005ef30  xor     edx, edx; bManualReset
0x18005ef32  xor     ecx, ecx; lpEventAttributes
0x18005ef34  call    cs:__imp_CreateEventW
0x18005ef3a  mov     r14, rax
0x18005ef3d  mov     [rsp+78h+arg_18], rax
0x18005ef45  test    r15, r15
0x18005ef48  jz      loc_18005F0A1
0x18005ef4e  test    rax, rax
0x18005ef51  jz      loc_18005F0A1
0x18005ef57  mov     edx, 1300000h
0x18005ef5c  mov     r8d, 30h ; '0'
0x18005ef62  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18005ef69  call    cs:__imp_MpHeapAlloc
0x18005ef6f  mov     [rsp+78h+var_38], rax
0x18005ef74  test    rax, rax
0x18005ef77  jz      short loc_18005EF85
0x18005ef79  mov     rdx, r15
0x18005ef7c  mov     rcx, rax; union _SLIST_HEADER *
0x18005ef7f  call    ??0?$_tagCQueue@UCSweepInfo@@@@QEAA@PEAXK@Z; _tagCQueue<CSweepInfo>::_tagCQueue<CSweepInfo>(void *,ulong)
0x18005ef84  nop
0x18005ef85  mov     [rsi], rax
0x18005ef88  mov     edx, 1300000h
0x18005ef8d  mov     r8d, 30h ; '0'
0x18005ef93  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18005ef9a  call    cs:__imp_MpHeapAlloc
0x18005efa0  mov     [rsp+78h+var_38], rax
0x18005efa5  test    rax, rax
0x18005efa8  jz      short loc_18005EFB6
0x18005efaa  mov     rdx, r14
0x18005efad  mov     rcx, rax; union _SLIST_HEADER *
0x18005efb0  call    ??0?$_tagCQueue@UCSweepInfo@@@@QEAA@PEAXK@Z; _tagCQueue<CSweepInfo>::_tagCQueue<CSweepInfo>(void *,ulong)
0x18005efb5  nop
0x18005efb6  mov     [rdi+58h], rax
0x18005efba  mov     edx, 1300000h
0x18005efbf  mov     r8d, 10h
0x18005efc5  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18005efcc  call    cs:__imp_MpHeapAlloc
0x18005efd2  mov     [rsp+78h+var_38], rax
0x18005efd7  test    rax, rax
0x18005efda  jz      short loc_18005EFEA
0x18005efdc  mov     rdx, [rdi+58h]
0x18005efe0  mov     rcx, [rsi]
0x18005efe3  mov     [rax], rcx
0x18005efe6  mov     [rax+8], rdx
0x18005efea  mov     [rdi+60h], rax
0x18005efee  cmp     qword ptr [rsi], 0
0x18005eff2  jz      loc_18005F0B9
0x18005eff8  cmp     qword ptr [rdi+58h], 0
0x18005effd  jz      loc_18005F0A1
0x18005f003  test    rax, rax
0x18005f006  jz      loc_18005F0A1
0x18005f00c  mov     [rsp+78h+ThreadId], 0
0x18005f017  lea     rax, [rsp+78h+ThreadId]
0x18005f01f  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18005f024  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x18005f02c  mov     r9, [rdi+58h]; lpParameter
0x18005f030  lea     r8, ?ReleaseResourceThread@@YAKPEAX@Z; lpStartAddress
0x18005f037  xor     edx, edx; dwStackSize
0x18005f039  xor     ecx, ecx; lpThreadAttributes
0x18005f03b  call    cs:__imp_CreateThread
0x18005f041  mov     [rdi+40h], rax
0x18005f045  test    rax, rax
0x18005f048  jz      short loc_18005F0A1
0x18005f04a  lea     rax, [rsp+78h+ThreadId]
0x18005f052  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18005f057  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x18005f05f  mov     r9, [rdi+60h]; lpParameter
0x18005f063  lea     r8, ?ResetResourceThread@@YAKPEAX@Z; lpStartAddress
0x18005f06a  xor     edx, edx; dwStackSize
0x18005f06c  xor     ecx, ecx; lpThreadAttributes
0x18005f06e  call    cs:__imp_CreateThread
0x18005f074  mov     [rdi+48h], rax
0x18005f078  test    rax, rax
0x18005f07b  jz      short loc_18005F0A1
0x18005f07d  mov     al, 1
0x18005f07f  jmp     loc_18005F117
0x18005f084  mov     rdi, [rsp+78h+arg_0]
0x18005f08c  mov     r15, [rsp+78h+arg_10]
0x18005f094  mov     r14, [rsp+78h+arg_18]
0x18005f09c  mov     rsi, [rsp+78h+var_40]
0x18005f0a1  cmp     qword ptr [rsi], 0
0x18005f0a5  jz      short loc_18005F0B9
0x18005f0a7  mov     rcx, [rsi]; void *
0x18005f0aa  call    ??_G?$_tagCQueue@UCSweepInfo@@@@QEAAPEAXI@Z; _tagCQueue<CSweepInfo>::`scalar deleting destructor'(uint)
0x18005f0af  mov     qword ptr [rsi], 0
0x18005f0b6  xor     r15d, r15d
0x18005f0b9  mov     rcx, [rdi+58h]; void *
0x18005f0bd  test    rcx, rcx
0x18005f0c0  jz      short loc_18005F0D2
0x18005f0c2  call    ??_G?$_tagCQueue@UCSweepInfo@@@@QEAAPEAXI@Z; _tagCQueue<CSweepInfo>::`scalar deleting destructor'(uint)
0x18005f0c7  mov     qword ptr [rdi+58h], 0
0x18005f0cf  xor     r14d, r14d
0x18005f0d2  mov     rcx, [rdi+60h]; void *
0x18005f0d6  test    rcx, rcx
0x18005f0d9  jz      short loc_18005F0E8
0x18005f0db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005f0e0  mov     qword ptr [rdi+60h], 0
0x18005f0e8  test    r14, r14
0x18005f0eb  jz      short loc_18005F0F6
0x18005f0ed  mov     rcx, r14; hObject
0x18005f0f0  call    cs:__imp_CloseHandle
0x18005f0f6  test    r15, r15
0x18005f0f9  jz      short loc_18005F104
0x18005f0fb  mov     rcx, r15; hObject
0x18005f0fe  call    cs:__imp_CloseHandle
0x18005f104  mov     rcx, [rdi+40h]; hThread
0x18005f108  test    rcx, rcx
0x18005f10b  jz      short loc_18005F115
0x18005f10d  xor     edx, edx; dwExitCode
0x18005f10f  call    cs:__imp_TerminateThread
0x18005f115  xor     al, al
0x18005f117  add     rsp, 58h
0x18005f11b  pop     r15
0x18005f11d  pop     r14
0x18005f11f  pop     rdi
0x18005f120  pop     rsi
0x18005f121  retn
```
