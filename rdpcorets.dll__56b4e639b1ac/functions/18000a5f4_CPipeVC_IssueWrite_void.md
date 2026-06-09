# CPipeVC::IssueWrite(void)

- ea: `0x18000a5f4`
- end: `0x18000a8d8`
- name: `?IssueWrite@CPipeVC@@IEAAJXZ`
- size: `740`
- prototype: `__int64 __fastcall(CPipeVC *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a020`

## callees

- `0x1800091a8`
- `0x18000a5f4`
- `0x18000a8e0`
- `0x180012200`
- `0x18002e600`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000a6c8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000a6c8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a7ad`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a7ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7c2`
- `api-ms-win-core-file-l1-1-0!WriteFileEx` at `0x18000a6f3`
- `api-ms-win-core-file-l1-1-0!WriteFileEx` at `0x18000a6f3`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a617`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a63d`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a696`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a617`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a63d`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18000a696`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a651`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a682`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a70f`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a78b`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a651`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a682`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a70f`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18000a78b`

## string_xrefs

- `0x18000a80c`: `WriteFileEx failed`

## pseudocode

```c
__int64 __fastcall CPipeVC::IssueWrite(CPipeVC *this, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // r14
  bool v8; // zf
  unsigned int v9; // edi
  signed int LastError; // eax
  unsigned int v12; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v14; // eax
  _QWORD *v15; // [rsp+50h] [rbp+8h] BYREF

  v3 = (_QWORD *)((char *)this + 88);
  if ( *((_DWORD *)this + 24) )
    PAL_System_CritSecEnter(*v3, a2, a3);
  if ( !(unsigned int)CPipeVC::IsValidObjectState(this) )
  {
    v9 = -2147024884;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"!IsValidObjectState()",
        12);
    }
    if ( v3 && *((_DWORD *)v3 + 2) )
      PAL_System_CritSecLeave(*v3);
    goto LABEL_25;
  }
  if ( *((_DWORD *)this + 70) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 34), v5, v6);
  if ( v3 && *((_DWORD *)v3 + 2) )
    PAL_System_CritSecLeave(*v3);
  v7 = (_QWORD *)((char *)this + 216);
  if ( !*((_QWORD *)this + 27) )
  {
    (*(void (__fastcall **)(char *, _QWORD, char *))(*((_QWORD *)this + 23) + 48LL))(
      (char *)this + 184,
      0,
      (char *)this + 216);
    (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 23) + 16LL))((char *)this + 184, *v7);
  }
  *((_DWORD *)this + 58) = 1;
  if ( *((_DWORD *)this + 70) )
    PAL_System_CritSecLeave(*((_QWORD *)this + 34));
  v8 = *((_DWORD *)v3 + 2) == 0;
  v15 = v3;
  if ( !v8 )
    PAL_System_CritSecEnter(*v3, v5, v6);
  if ( !(unsigned int)CPipeVC::IsValidObjectState(this) )
  {
    v9 = -2147024884;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v14,
        (__int64)"!IsValidObjectState()",
        12);
    }
    goto LABEL_33;
  }
  v9 = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6) + 8LL))((char *)this + 48);
  ResetEvent(*((HANDLE *)this + 41));
  if ( !WriteFileEx(
          *((HANDLE *)this + 16),
          *(LPCVOID *)(*v7 + 48LL),
          *(_DWORD *)(*v7 + 60LL),
          (LPOVERLAPPED)((char *)this + 240),
          CPipeVC::StaticWriteToPipeComplete) )
  {
    SetEvent(*((HANDLE *)this + 41));
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6) + 16LL))((char *)this + 48);
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
          v12,
          (__int64)"WriteFileEx failed",
          v9);
      }
LABEL_33:
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v15);
LABEL_25:
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 6) + 40LL))((char *)this + 48);
      return v9;
    }
  }
  if ( v3 && *((_DWORD *)v3 + 2) )
    PAL_System_CritSecLeave(*v3);
  return v9;
}

```

## disassembly

```asm
0x18000a5f4  mov     [rsp+arg_8], rbx
0x18000a5f9  mov     [rsp+arg_10], rsi
0x18000a5fe  push    rdi
0x18000a5ff  push    r14
0x18000a601  push    r15
0x18000a603  sub     rsp, 30h
0x18000a607  lea     rbx, [rcx+58h]
0x18000a60b  mov     rsi, rcx
0x18000a60e  cmp     dword ptr [rbx+8], 0
0x18000a612  jz      short loc_18000A61D
0x18000a614  mov     rcx, [rbx]
0x18000a617  call    cs:__imp_PAL_System_CritSecEnter
0x18000a61d  mov     rcx, rsi; this
0x18000a620  call    ?IsValidObjectState@CPipeVC@@IEAAHXZ; CPipeVC::IsValidObjectState(void)
0x18000a625  test    eax, eax
0x18000a627  jz      loc_18000A761
0x18000a62d  cmp     dword ptr [rsi+118h], 0
0x18000a634  jz      short loc_18000A643
0x18000a636  mov     rcx, [rsi+110h]
0x18000a63d  call    cs:__imp_PAL_System_CritSecEnter
0x18000a643  test    rbx, rbx
0x18000a646  jz      short loc_18000A657
0x18000a648  cmp     dword ptr [rbx+8], 0
0x18000a64c  jz      short loc_18000A657
0x18000a64e  mov     rcx, [rbx]
0x18000a651  call    cs:__imp_PAL_System_CritSecLeave
0x18000a657  lea     r14, [rsi+0D8h]
0x18000a65e  cmp     qword ptr [r14], 0
0x18000a662  jz      loc_18000A72F
0x18000a668  mov     dword ptr [rsi+0E8h], 1
0x18000a672  cmp     dword ptr [rsi+118h], 0
0x18000a679  jz      short loc_18000A688
0x18000a67b  mov     rcx, [rsi+110h]
0x18000a682  call    cs:__imp_PAL_System_CritSecLeave
0x18000a688  cmp     dword ptr [rbx+8], 0
0x18000a68c  mov     [rsp+48h+arg_0], rbx
0x18000a691  jz      short loc_18000A69C
0x18000a693  mov     rcx, [rbx]
0x18000a696  call    cs:__imp_PAL_System_CritSecEnter
0x18000a69c  mov     rcx, rsi; this
0x18000a69f  call    ?IsValidObjectState@CPipeVC@@IEAAHXZ; CPipeVC::IsValidObjectState(void)
0x18000a6a4  test    eax, eax
0x18000a6a6  jz      loc_18000A892
0x18000a6ac  lea     r15, [rsi+30h]
0x18000a6b0  xor     edi, edi
0x18000a6b2  mov     rax, [r15]
0x18000a6b5  mov     rcx, r15
0x18000a6b8  mov     rax, [rax+8]
0x18000a6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6c1  mov     rcx, [rsi+148h]; hEvent
0x18000a6c8  call    cs:__imp_ResetEvent
0x18000a6ce  mov     rdx, [r14]
0x18000a6d1  lea     rax, ?StaticWriteToPipeComplete@CPipeVC@@KAXKKPEAU_OVERLAPPED@@@Z; CPipeVC::StaticWriteToPipeComplete(ulong,ulong,_OVERLAPPED *)
0x18000a6d8  mov     rcx, [rsi+80h]; hFile
0x18000a6df  lea     r9, [rsi+0F0h]; lpOverlapped
0x18000a6e6  mov     [rsp+48h+lpCompletionRoutine], rax; lpCompletionRoutine
0x18000a6eb  mov     r8d, [rdx+3Ch]; nNumberOfBytesToWrite
0x18000a6ef  mov     rdx, [rdx+30h]; lpBuffer
0x18000a6f3  call    cs:__imp_WriteFileEx
0x18000a6f9  test    eax, eax
0x18000a6fb  jz      loc_18000A7A6
0x18000a701  test    rbx, rbx
0x18000a704  jz      short loc_18000A715
0x18000a706  cmp     dword ptr [rbx+8], 0
0x18000a70a  jz      short loc_18000A715
0x18000a70c  mov     rcx, [rbx]
0x18000a70f  call    cs:__imp_PAL_System_CritSecLeave
0x18000a715  test    edi, edi
0x18000a717  js      short loc_18000A791
0x18000a719  mov     rbx, [rsp+48h+arg_8]
0x18000a71e  mov     eax, edi
0x18000a720  mov     rsi, [rsp+48h+arg_10]
0x18000a725  add     rsp, 30h
0x18000a729  pop     r15
0x18000a72b  pop     r14
0x18000a72d  pop     rdi
0x18000a72e  retn
0x18000a72f  lea     rdi, [rsi+0B8h]
0x18000a736  mov     r8, r14
0x18000a739  mov     rax, [rdi]
0x18000a73c  xor     edx, edx
0x18000a73e  mov     rcx, rdi
0x18000a741  mov     rax, [rax+30h]
0x18000a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a74a  mov     rax, [rdi]
0x18000a74d  mov     rcx, rdi
0x18000a750  mov     rdx, [r14]
0x18000a753  mov     rax, [rax+10h]
0x18000a757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a75c  jmp     loc_18000A668
0x18000a761  mov     edi, 8007000Ch
0x18000a766  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a76d  lea     rax, WPP_GLOBAL_Control
0x18000a774  cmp     rcx, rax
0x18000a777  jnz     loc_18000A841
0x18000a77d  test    rbx, rbx
0x18000a780  jz      short loc_18000A791
0x18000a782  cmp     dword ptr [rbx+8], 0
0x18000a786  jz      short loc_18000A791
0x18000a788  mov     rcx, [rbx]
0x18000a78b  call    cs:__imp_PAL_System_CritSecLeave
0x18000a791  lea     rcx, [rsi+30h]
0x18000a795  mov     rdx, [rcx]
0x18000a798  mov     rax, [rdx+28h]
0x18000a79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a1  jmp     loc_18000A719
0x18000a7a6  mov     rcx, [rsi+148h]; hEvent
0x18000a7ad  call    cs:__imp_SetEvent
0x18000a7b3  mov     rax, [r15]
0x18000a7b6  mov     rcx, r15
0x18000a7b9  mov     rax, [rax+10h]
0x18000a7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c2  call    cs:__imp_GetLastError
0x18000a7c8  mov     edi, eax
0x18000a7ca  test    eax, eax
0x18000a7cc  jle     short loc_18000A7D7
0x18000a7ce  movzx   edi, ax
0x18000a7d1  or      edi, 80070000h
0x18000a7d7  test    edi, edi
0x18000a7d9  jns     loc_18000A701
0x18000a7df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7e6  lea     rax, WPP_GLOBAL_Control
0x18000a7ed  cmp     rcx, rax
0x18000a7f0  jz      short loc_18000A832
0x18000a7f2  test    byte ptr [rcx+1Ch], 8
0x18000a7f6  jz      short loc_18000A832
0x18000a7f8  cmp     byte ptr [rcx+19h], 2
0x18000a7fc  jb      short loc_18000A832
0x18000a7fe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a803  mov     edx, 6Bh ; 'k'
0x18000a808  mov     [rsp+48h+var_20], edi
0x18000a80c  lea     rcx, aWritefileexFai; "WriteFileEx failed"
0x18000a813  mov     [rsp+48h+lpCompletionRoutine], rcx
0x18000a818  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x18000a81f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a826  mov     r9d, eax
0x18000a829  mov     rcx, [rcx+10h]
0x18000a82d  call    WPP_SF_DsD
0x18000a832  lea     rcx, [rsp+48h+arg_0]; this
0x18000a837  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18000a83c  jmp     loc_18000A791
0x18000a841  test    byte ptr [rcx+1Ch], 8
0x18000a845  jz      loc_18000A77D
0x18000a84b  cmp     byte ptr [rcx+19h], 2
0x18000a84f  jb      loc_18000A77D
0x18000a855  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a85a  lea     rcx, aIsvalidobjects; "!IsValidObjectState()"
0x18000a861  mov     [rsp+48h+var_20], 8007000Ch
0x18000a869  mov     [rsp+48h+lpCompletionRoutine], rcx
0x18000a86e  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x18000a875  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a87c  mov     edx, 69h ; 'i'
0x18000a881  mov     r9d, eax
0x18000a884  mov     rcx, [rcx+10h]
0x18000a888  call    WPP_SF_DsD
0x18000a88d  jmp     loc_18000A77D
0x18000a892  mov     edi, 8007000Ch
0x18000a897  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a89e  lea     rax, WPP_GLOBAL_Control
0x18000a8a5  cmp     rcx, rax
0x18000a8a8  jz      short loc_18000A832
0x18000a8aa  test    byte ptr [rcx+1Ch], 8
0x18000a8ae  jz      short loc_18000A832
0x18000a8b0  cmp     byte ptr [rcx+19h], 2
0x18000a8b4  jb      loc_18000A832
0x18000a8ba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000a8bf  mov     edx, 6Ah ; 'j'
0x18000a8c4  mov     [rsp+48h+var_20], 8007000Ch
0x18000a8cc  lea     rcx, aIsvalidobjects; "!IsValidObjectState()"
0x18000a8d3  jmp     loc_18000A813
```
