# CTxtEdit::CUnknown::~CUnknown(void)

- ea: `0x180046e30`
- end: `0x180046f06`
- name: `??1CUnknown@CTxtEdit@@QEAA@XZ`
- size: `214`
- prototype: `void __fastcall(CTxtEdit::CUnknown *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003b7d4`

## callees

- `0x180044ff4`
- `0x180046e30`
- `0x18004915c`
- `0x18008e4a4`
- `0x18008e4c0`
- `0x180090024`
- `0x18009110a`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180046e4a`
- `KERNEL32!EnterCriticalSection` at `0x180046eb4`
- `KERNEL32!EnterCriticalSection` at `0x180046e4a`
- `KERNEL32!EnterCriticalSection` at `0x180046eb4`
- `KERNEL32!LeaveCriticalSection` at `0x180046eed`
- `KERNEL32!LeaveCriticalSection` at `0x180046eed`
- `KERNEL32!LeaveCriticalSection` at `0x180046eff`
- `KERNEL32!GetCurrentThreadId` at `0x180046e6f`
- `KERNEL32!GetCurrentThreadId` at `0x180046e6f`
- `KERNEL32!FreeLibrary` at `0x180046ec1`
- `KERNEL32!FreeLibrary` at `0x180046ec1`

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
    if ( qword_1800A4478 )
    {
      EnterCriticalSection(&g_CriticalSection);
      FreeLibrary(qword_1800A4478);
      qword_1800A4478 = 0;
      memset_0(qword_1800A3FA0, 0, 0x150u);
      LeaveCriticalSection(&g_CriticalSection);
    }
  }
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x180046e30  push    rbx
0x180046e32  sub     rsp, 20h
0x180046e36  lea     rax, ??_7CUnknown@CTxtEdit@@6B@; const CTxtEdit::CUnknown::`vftable'
0x180046e3d  mov     rbx, rcx
0x180046e40  mov     [rcx], rax
0x180046e43  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046e4a  call    cs:__imp_EnterCriticalSection
0x180046e50  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x180046e57  jnz     short loc_180046E95
0x180046e59  cmp     cs:?_dwTlsIndex@CThreadData@@0KA, 0FFFFFFFFh; ulong CThreadData::_dwTlsIndex
0x180046e60  jz      short loc_180046E95
0x180046e62  mov     ebx, [rbx+0Ch]
0x180046e65  call    ?GetThreadState@CThreadData@@CA?AW4ThreadState@1@XZ; CThreadData::GetThreadState(void)
0x180046e6a  cmp     eax, 1
0x180046e6d  jnz     short loc_180046E95
0x180046e6f  call    cs:__imp_GetCurrentThreadId
0x180046e75  cmp     ebx, eax
0x180046e77  jnz     short loc_180046E95
0x180046e79  call    ?GetThreadData@CThreadData@@CAPEAV1@XZ; CThreadData::GetThreadData(void)
0x180046e7e  sub     dword ptr [rax], 1
0x180046e81  jnz     short loc_180046E95
0x180046e83  cmp     byte ptr [rax+4], 0
0x180046e87  jz      short loc_180046E8E
0x180046e89  call    ?OleUninitialize@CW32System@@SAXXZ; CW32System::OleUninitialize(void)
0x180046e8e  xor     ecx, ecx
0x180046e90  call    ?SetThreadState@CThreadData@@CAXW4ThreadState@1@@Z; CThreadData::SetThreadState(CThreadData::ThreadState)
0x180046e95  add     cs:?_cRefs@CW32System@@0KA, 0FFFFFFFFh; ulong CW32System::_cRefs
0x180046e9c  jnz     short loc_180046EF3
0x180046e9e  call    ?FreeIME@CW32System@@SAXXZ; CW32System::FreeIME(void)
0x180046ea3  cmp     cs:qword_1800A4478, 0
0x180046eab  jz      short loc_180046EF3
0x180046ead  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046eb4  call    cs:__imp_EnterCriticalSection
0x180046eba  mov     rcx, cs:qword_1800A4478; hLibModule
0x180046ec1  call    cs:__imp_FreeLibrary
0x180046ec7  xor     edx, edx; Val
0x180046ec9  mov     cs:qword_1800A4478, 0
0x180046ed4  mov     r8d, 150h; Size
0x180046eda  lea     rcx, qword_1800A3FA0; void *
0x180046ee1  call    memset_0
0x180046ee6  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180046eed  call    cs:__imp_LeaveCriticalSection
0x180046ef3  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x180046efa  add     rsp, 20h
0x180046efe  pop     rbx
0x180046eff  jmp     cs:__imp_LeaveCriticalSection
```
