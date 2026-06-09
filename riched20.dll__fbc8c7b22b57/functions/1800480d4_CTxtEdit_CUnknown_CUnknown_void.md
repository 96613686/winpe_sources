# CTxtEdit::CUnknown::~CUnknown(void)

- ea: `0x1800480d4`
- end: `0x1800481cd`
- name: `??1CUnknown@CTxtEdit@@QEAA@XZ`
- size: `249`
- prototype: `void __fastcall(CTxtEdit::CUnknown *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003c384`

## callees

- `0x180046124`
- `0x1800480d4`
- `0x18004a2c4`
- `0x180090d50`
- `0x180090d74`
- `0x18009299c`
- `0x180093bca`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800480ee`
- `KERNEL32!EnterCriticalSection` at `0x180048164`
- `KERNEL32!EnterCriticalSection` at `0x1800480ee`
- `KERNEL32!EnterCriticalSection` at `0x180048164`
- `KERNEL32!LeaveCriticalSection` at `0x1800481a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800481a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800481c1`
- `KERNEL32!GetCurrentThreadId` at `0x180048119`
- `KERNEL32!GetCurrentThreadId` at `0x180048119`
- `KERNEL32!FreeLibrary` at `0x180048177`
- `KERNEL32!FreeLibrary` at `0x180048177`

## pseudocode

```c
void __fastcall CTxtEdit::CUnknown::~CUnknown(CTxtEdit::CUnknown *this)
{
  int v2; // ebx
  struct CThreadData *ThreadData; // rax
  __int64 v4; // rdx
  __int64 v5; // r8

  *(_QWORD *)this = &CTxtEdit::CUnknown::`vftable';
  EnterCriticalSection(&g_CriticalSection);
  if ( !CW32System::_fOleinitCheckDisabled && CThreadData::_dwTlsIndex != -1 )
  {
    v2 = *((_DWORD *)this + 3);
    if ( (unsigned int)CThreadData::GetThreadState() == 1 && v2 == GetCurrentThreadId() )
    {
      ThreadData = CThreadData::GetThreadData();
      if ( (*(_DWORD *)ThreadData)-- == 1 )
      {
        if ( *((_BYTE *)ThreadData + 4) )
          CW32System::OleUninitialize();
        CThreadData::SetThreadState(0, v4, v5);
      }
    }
  }
  if ( !--CW32System::_cRefs )
  {
    CW32System::FreeIME();
    if ( qword_1800A7558 )
    {
      EnterCriticalSection(&g_CriticalSection);
      FreeLibrary(qword_1800A7558);
      qword_1800A7558 = 0;
      memset_0(qword_1800A7080, 0, 0x150u);
      LeaveCriticalSection(&g_CriticalSection);
    }
  }
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x1800480d4  push    rbx
0x1800480d6  sub     rsp, 20h
0x1800480da  lea     rax, ??_7CUnknown@CTxtEdit@@6B@; const CTxtEdit::CUnknown::`vftable'
0x1800480e1  mov     rbx, rcx
0x1800480e4  mov     [rcx], rax
0x1800480e7  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800480ee  call    cs:__imp_EnterCriticalSection
0x1800480f5  nop     dword ptr [rax+rax+00h]
0x1800480fa  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x180048101  jnz     short loc_180048145
0x180048103  cmp     cs:?_dwTlsIndex@CThreadData@@0KA, 0FFFFFFFFh; ulong CThreadData::_dwTlsIndex
0x18004810a  jz      short loc_180048145
0x18004810c  mov     ebx, [rbx+0Ch]
0x18004810f  call    ?GetThreadState@CThreadData@@CA?AW4ThreadState@1@XZ; CThreadData::GetThreadState(void)
0x180048114  cmp     eax, 1
0x180048117  jnz     short loc_180048145
0x180048119  call    cs:__imp_GetCurrentThreadId
0x180048120  nop     dword ptr [rax+rax+00h]
0x180048125  cmp     ebx, eax
0x180048127  jnz     short loc_180048145
0x180048129  call    ?GetThreadData@CThreadData@@CAPEAV1@XZ; CThreadData::GetThreadData(void)
0x18004812e  sub     dword ptr [rax], 1
0x180048131  jnz     short loc_180048145
0x180048133  cmp     byte ptr [rax+4], 0
0x180048137  jz      short loc_18004813E
0x180048139  call    ?OleUninitialize@CW32System@@SAXXZ; CW32System::OleUninitialize(void)
0x18004813e  xor     ecx, ecx
0x180048140  call    ?SetThreadState@CThreadData@@CAXW4ThreadState@1@@Z; CThreadData::SetThreadState(CThreadData::ThreadState)
0x180048145  add     cs:?_cRefs@CW32System@@0KA, 0FFFFFFFFh; ulong CW32System::_cRefs
0x18004814c  jnz     short loc_1800481B5
0x18004814e  call    ?FreeIME@CW32System@@SAXXZ; CW32System::FreeIME(void)
0x180048153  cmp     cs:qword_1800A7558, 0
0x18004815b  jz      short loc_1800481B5
0x18004815d  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180048164  call    cs:__imp_EnterCriticalSection
0x18004816b  nop     dword ptr [rax+rax+00h]
0x180048170  mov     rcx, cs:qword_1800A7558; hLibModule
0x180048177  call    cs:__imp_FreeLibrary
0x18004817e  nop     dword ptr [rax+rax+00h]
0x180048183  xor     edx, edx; Val
0x180048185  mov     cs:qword_1800A7558, 0
0x180048190  mov     r8d, 150h; Size
0x180048196  lea     rcx, qword_1800A7080; void *
0x18004819d  call    memset_0
0x1800481a2  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800481a9  call    cs:__imp_LeaveCriticalSection
0x1800481b0  nop     dword ptr [rax+rax+00h]
0x1800481b5  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x1800481bc  add     rsp, 20h
0x1800481c0  pop     rbx
0x1800481c1  jmp     cs:__imp_LeaveCriticalSection
```
