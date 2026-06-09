# CTxtEdit::CUnknown::~CUnknown(void)

- ea: `0x1800dd178`
- end: `0x1800dd213`
- name: `??1CUnknown@CTxtEdit@@AEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CTxtEdit::CUnknown *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18010c83c`

## callees

- `0x18000f358`
- `0x18005921c`
- `0x1800dd178`
- `0x1800dd21c`
- `0x1800dd748`
- `0x1800dd958`
- `0x1800dd9f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dd1cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800dd1cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800dd1e7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800dd1e7`

## pseudocode

```c
void __fastcall CTxtEdit::CUnknown::~CUnknown(CTxtEdit::CUnknown *this)
{
  int v2; // ebx
  _BYTE *v3; // rcx
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CTxtEdit::CUnknown::`vftable';
  CWriteLock::CWriteLock(&v5, 0);
  if ( !CW32System::_fOleinitCheckDisabled && CThreadData::_dwTlsIndex != -1 )
  {
    v2 = *((_DWORD *)this + 3);
    if ( (unsigned int)CThreadData::GetThreadState() == 1 && v2 == GetCurrentThreadId() )
    {
      v3 = CThreadData::_dwTlsIndex == -1 ? 0LL : TlsGetValue(CThreadData::_dwTlsIndex);
      if ( (*(_DWORD *)v3)-- == 1 )
      {
        if ( v3[4] )
          CW32System::OleUninitialize();
        CThreadData::SetThreadState(0);
      }
    }
  }
  CW32System::GlobalRelease();
  CWriteLock::~CWriteLock((CWriteLock *)&v5);
}

```

## disassembly

```asm
0x1800dd178  push    rbx
0x1800dd17a  sub     rsp, 20h
0x1800dd17e  lea     rax, ??_7CUnknown@CTxtEdit@@6B@; const CTxtEdit::CUnknown::`vftable'
0x1800dd185  mov     rbx, rcx
0x1800dd188  mov     [rcx], rax
0x1800dd18b  xor     edx, edx
0x1800dd18d  lea     rcx, [rsp+28h+arg_0]
0x1800dd192  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x1800dd197  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x1800dd19e  jz      short loc_1800DD1B6
0x1800dd1a0  call    ?GlobalRelease@CW32System@@SAXXZ; CW32System::GlobalRelease(void)
0x1800dd1a5  lea     rcx, [rsp+28h+arg_0]; this
0x1800dd1aa  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800dd1af  add     rsp, 20h
0x1800dd1b3  pop     rbx
0x1800dd1b4  retn
0x1800dd1b6  cmp     cs:?_dwTlsIndex@CThreadData@@0KA, 0FFFFFFFFh; ulong CThreadData::_dwTlsIndex
0x1800dd1bd  jz      short loc_1800DD1A0
0x1800dd1bf  mov     ebx, [rbx+0Ch]
0x1800dd1c2  call    ?GetThreadState@CThreadData@@CA?AW4ThreadState@1@XZ; CThreadData::GetThreadState(void)
0x1800dd1c7  cmp     eax, 1
0x1800dd1ca  jnz     short loc_1800DD1A0
0x1800dd1cc  call    cs:__imp_GetCurrentThreadId
0x1800dd1d3  nop     dword ptr [rax+rax+00h]
0x1800dd1d8  cmp     ebx, eax
0x1800dd1da  jnz     short loc_1800DD1A0
0x1800dd1dc  mov     ecx, cs:?_dwTlsIndex@CThreadData@@0KA; dwTlsIndex
0x1800dd1e2  cmp     ecx, 0FFFFFFFFh
0x1800dd1e5  jz      short loc_1800DD20F
0x1800dd1e7  call    cs:__imp_TlsGetValue
0x1800dd1ee  nop     dword ptr [rax+rax+00h]
0x1800dd1f3  mov     rcx, rax
0x1800dd1f6  sub     dword ptr [rcx], 1
0x1800dd1f9  jnz     short loc_1800DD1A0
0x1800dd1fb  cmp     byte ptr [rcx+4], 0
0x1800dd1ff  jz      short loc_1800DD206
0x1800dd201  call    ?OleUninitialize@CW32System@@SAXXZ; CW32System::OleUninitialize(void)
0x1800dd206  xor     ecx, ecx
0x1800dd208  call    ?SetThreadState@CThreadData@@CAXW4ThreadState@1@@Z; CThreadData::SetThreadState(CThreadData::ThreadState)
0x1800dd20d  jmp     short loc_1800DD1A0
0x1800dd20f  xor     ecx, ecx
0x1800dd211  jmp     short loc_1800DD1F6
```
