# CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)

- ea: `0x180013750`
- end: `0x180013902`
- name: `?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z`
- size: `434`
- prototype: `void __high(unsigned int, const char *, bool, enum RecordJournalOptions)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180004c8c`
- `0x180006228`
- `0x18000670c`
- `0x18000ae80`
- `0x18000f040`

## callees

- `0x18000b410`
- `0x18000be78`
- `0x18000de10`
- `0x1800136c4`
- `0x180013750`
- `0x180013908`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800138bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800137a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013844`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800138bd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001384a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800137ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001383c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800137ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001383c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180013804`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180013804`

## pseudocode

```c
USHORT __fastcall CJournal::RecordJournal(__int64 a1, int a2, const char *a3, __int64 a4, char a5)
{
  __int64 v7; // r12
  __int64 v8; // rdi
  USHORT result; // ax
  unsigned int v10; // r15d
  struct SJournalEntry *v11; // rsi
  DWORD TickCount; // ebx
  DWORD CurrentThreadId; // eax
  unsigned __int64 v14; // r10
  __int64 v15; // rcx
  unsigned __int64 v16; // r11
  __int64 v17; // rdx
  struct SJournalEntry *v18; // r8
  struct SJournalEntry *v19; // r9
  char v20; // al
  int v21; // edx
  int v22; // ecx
  PVOID BackTrace[50]; // [rsp+30h] [rbp-1D8h] BYREF

  v7 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&JournalCounter, 0xFFFFFFFF) - 1) & 0x3F;
  v8 = 120 * v7;
  *((_DWORD *)&Journal + 30 * v7) = a2;
  *(_DWORD *)((char *)&Journal + v8 + 4) = GetCurrentThreadId();
  *(_DWORD *)((char *)&Journal + v8 + 8) = GetTickCount();
  *(_OWORD *)((char *)&Journal + v8 + 16) = 0;
  *(struct SJournalEntry near **)((char *)&Journal + v8 + 32) = 0;
  *(struct SJournalEntry near **)((char *)&Journal + v8 + 40) = 0;
  *(struct SJournalEntry near **)((char *)&Journal + v8 + 48) = 0;
  StringCchCopyA((char *)&Journal + 120 * v7 + 56, 0x40u, a3);
  memset_0(BackTrace, 0, sizeof(BackTrace));
  result = RtlCaptureStackBackTrace(1u, 0x32u, BackTrace, 0);
  v10 = result;
  if ( result >= 3u )
  {
    v11 = (struct SJournalEntry *)BackTrace[0];
    *(struct SJournalEntry near **)((char *)&Journal + v8 + 24) = (struct SJournalEntry near *)BackTrace[1];
    *(struct SJournalEntry near **)((char *)&Journal + v8 + 32) = (struct SJournalEntry near *)BackTrace[2];
    *(struct SJournalEntry near **)((char *)&Journal + v8 + 16) = v11;
    if ( (a5 & 1) != 0 )
    {
      TickCount = GetTickCount();
      CurrentThreadId = GetCurrentThreadId();
      result = D3DOutputMessage((_DWORD)OutputDebugStringA, a2, CurrentThreadId, TickCount, (__int64)v11, (__int64)a3);
    }
  }
  v14 = qword_18001E9B8;
  v15 = 0;
  v16 = g_Journal;
  do
  {
    v17 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v17 >= v10 )
      break;
    v18 = (struct SJournalEntry *)BackTrace[v15];
    if ( (unsigned __int64)v18 >= v16 && (unsigned __int64)v18 <= v14 )
    {
      v19 = (struct SJournalEntry *)BackTrace[v17];
      if ( (unsigned __int64)v19 < v16 || (unsigned __int64)v19 > v14 )
      {
        *(struct SJournalEntry near **)((char *)&Journal + v8 + 40) = v18;
        LODWORD(v15) = v15 + 1;
        *(struct SJournalEntry near **)((char *)&Journal + v8 + 48) = v19;
      }
    }
    v15 = (unsigned int)(v15 + 1);
    result = v15 + 1;
  }
  while ( (unsigned int)(v15 + 1) < 0x32 );
  if ( (byte_18001C7C1 & 2) != 0 )
  {
    v20 = GetCurrentThreadId();
    return McTemplateU0qdqs_EventWriteTransfer(v22, v21, v7, a2, v20, (__int64)a3);
  }
  return result;
}

```

## disassembly

```asm
0x180013750  mov     [rsp+arg_0], rbx
0x180013755  push    rbp
0x180013756  push    rsi
0x180013757  push    rdi
0x180013758  push    r12
0x18001375a  push    r13
0x18001375c  push    r14
0x18001375e  push    r15
0x180013760  sub     rsp, 1D0h
0x180013767  mov     rax, cs:__security_cookie
0x18001376e  xor     rax, rsp
0x180013771  mov     [rsp+208h+var_48], rax
0x180013779  mov     r14, r8
0x18001377c  mov     ebp, edx
0x18001377e  or      r12d, 0FFFFFFFFh
0x180013782  lock xadd cs:?JournalCounter@@3IC, r12d; uint volatile JournalCounter
0x18001378b  dec     r12d
0x18001378e  lea     r13, ?Journal@@3PAUSJournalEntry@@A; SJournalEntry near * Journal
0x180013795  and     r12d, 3Fh
0x180013799  imul    rdi, r12, 78h ; 'x'
0x18001379d  mov     [rdi+r13], edx
0x1800137a1  call    cs:__imp_GetCurrentThreadId
0x1800137a7  mov     [rdi+r13+4], eax
0x1800137ac  call    cs:__imp_GetTickCount
0x1800137b2  mov     [rdi+r13+8], eax
0x1800137b7  xorps   xmm0, xmm0
0x1800137ba  xor     eax, eax
0x1800137bc  lea     rcx, [r13+38h]
0x1800137c0  movups  xmmword ptr [rdi+r13+10h], xmm0
0x1800137c6  mov     [rdi+r13+20h], rax
0x1800137cb  add     rcx, rdi; char *
0x1800137ce  mov     r8, r14; char *
0x1800137d1  mov     [rdi+r13+28h], rax
0x1800137d6  lea     edx, [rax+40h]; unsigned __int64
0x1800137d9  mov     [rdi+r13+30h], rax
0x1800137de  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800137e3  xor     edx, edx; Val
0x1800137e5  lea     rcx, [rsp+208h+BackTrace]; void *
0x1800137ea  mov     r8d, 190h; Size
0x1800137f0  call    memset_0
0x1800137f5  xor     r9d, r9d; BackTraceHash
0x1800137f8  lea     r8, [rsp+208h+BackTrace]; BackTrace
0x1800137fd  lea     edx, [r9+32h]; FramesToCapture
0x180013801  lea     ecx, [rdx-31h]; FramesToSkip
0x180013804  call    cs:__imp_RtlCaptureStackBackTrace
0x18001380a  movzx   r15d, ax
0x18001380e  cmp     r15d, 3
0x180013812  jb      short loc_180013868
0x180013814  test    [rsp+208h+arg_20], 1
0x18001381c  mov     rcx, [rsp+208h+var_1D0]
0x180013821  mov     rsi, [rsp+208h+BackTrace]
0x180013826  mov     [rdi+r13+18h], rcx
0x18001382b  mov     rcx, [rsp+208h+var_1C8]
0x180013830  mov     [rdi+r13+20h], rcx
0x180013835  mov     [rdi+r13+10h], rsi
0x18001383a  jz      short loc_180013868
0x18001383c  call    cs:__imp_GetTickCount
0x180013842  mov     ebx, eax
0x180013844  call    cs:__imp_GetCurrentThreadId
0x18001384a  mov     rcx, cs:__imp_OutputDebugStringA
0x180013851  mov     r9d, ebx
0x180013854  mov     r8d, eax
0x180013857  mov     [rsp+208h+var_1E0], r14
0x18001385c  mov     edx, ebp
0x18001385e  mov     [rsp+208h+var_1E8], rsi
0x180013863  call    D3DOutputMessage
0x180013868  mov     r10, cs:qword_18001E9B8
0x18001386f  xor     ecx, ecx
0x180013871  mov     r11, cs:?g_Journal@@3VCJournal@@A; CJournal g_Journal
0x180013878  lea     edx, [rcx+1]
0x18001387b  cmp     edx, r15d
0x18001387e  jnb     short loc_1800138B4
0x180013880  mov     r8, [rsp+rcx*8+208h+BackTrace]
0x180013885  cmp     r8, r11
0x180013888  jb      short loc_1800138AA
0x18001388a  cmp     r8, r10
0x18001388d  ja      short loc_1800138AA
0x18001388f  mov     r9, [rsp+rdx*8+208h+BackTrace]
0x180013894  cmp     r9, r11
0x180013897  jb      short loc_18001389E
0x180013899  cmp     r9, r10
0x18001389c  jbe     short loc_1800138AA
0x18001389e  mov     [rdi+r13+28h], r8
0x1800138a3  mov     ecx, edx
0x1800138a5  mov     [rdi+r13+30h], r9
0x1800138aa  inc     ecx
0x1800138ac  lea     eax, [rcx+1]
0x1800138af  cmp     eax, 32h ; '2'
0x1800138b2  jb      short loc_180013878
0x1800138b4  test    cs:byte_18001C7C1, 2
0x1800138bb  jz      short loc_1800138D7
0x1800138bd  call    cs:__imp_GetCurrentThreadId
0x1800138c3  mov     r9d, ebp
0x1800138c6  mov     [rsp+208h+var_1E0], r14
0x1800138cb  mov     r8d, r12d
0x1800138ce  mov     dword ptr [rsp+208h+var_1E8], eax
0x1800138d2  call    McTemplateU0qdqs_EventWriteTransfer
0x1800138d7  mov     rcx, [rsp+208h+var_48]
0x1800138df  xor     rcx, rsp; StackCookie
0x1800138e2  call    __security_check_cookie
0x1800138e7  mov     rbx, [rsp+208h+arg_0]
0x1800138ef  add     rsp, 1D0h
0x1800138f6  pop     r15
0x1800138f8  pop     r14
0x1800138fa  pop     r13
0x1800138fc  pop     r12
0x1800138fe  pop     rdi
0x1800138ff  pop     rsi
0x180013900  pop     rbp
0x180013901  retn
```
