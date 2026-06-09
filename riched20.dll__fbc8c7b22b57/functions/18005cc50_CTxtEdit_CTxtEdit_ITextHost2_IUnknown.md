# CTxtEdit::CTxtEdit(ITextHost2 *,IUnknown *)

- ea: `0x18005cc50`
- end: `0x18005cdcd`
- name: `??0CTxtEdit@@QEAA@PEAVITextHost2@@PEAUIUnknown@@@Z`
- size: `381`
- prototype: `CTxtEdit *__fastcall(CTxtEdit *__hidden this, struct ITextHost2 *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002c7c0`

## callees

- `0x18004a2c4`
- `0x18005cc50`
- `0x180090d50`
- `0x180090d74`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18005ccb7`
- `KERNEL32!EnterCriticalSection` at `0x18005ccb7`
- `KERNEL32!LeaveCriticalSection` at `0x18005cd10`
- `KERNEL32!LeaveCriticalSection` at `0x18005cd10`
- `KERNEL32!GetCurrentThreadId` at `0x18005ccc9`
- `KERNEL32!GetCurrentThreadId` at `0x18005ccc9`

## pseudocode

```c
CTxtEdit *__fastcall CTxtEdit::CTxtEdit(CTxtEdit *this, struct ITextHost2 *a2, struct IUnknown *a3)
{
  struct IUnknown *v3; // rdi
  DWORD CurrentThreadId; // eax
  bool v8; // zf
  int ThreadState; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  struct CThreadData *ThreadData; // rax
  CTxtEdit *result; // rax

  v3 = (struct IUnknown *)((char *)this + 232);
  *(_QWORD *)this = &CTxtEdit::`vftable'{for `ITextServices'};
  *((_QWORD *)this + 1) = &CTxtEdit::`vftable'{for `IRichEditOle'};
  *((_QWORD *)this + 2) = &CTxtEdit::`vftable'{for `ITextDocument2'};
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_WORD *)this + 60) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 29) = &CTxtEdit::CUnknown::`vftable';
  EnterCriticalSection(&g_CriticalSection);
  ++CW32System::_cRefs;
  CurrentThreadId = GetCurrentThreadId();
  v8 = !CW32System::_fOleinitCheckDisabled;
  HIDWORD(v3[1].lpVtbl) = CurrentThreadId;
  if ( v8 && CThreadData::_dwTlsIndex != -1 )
  {
    ThreadState = CThreadData::GetThreadState();
    if ( ThreadState )
    {
      if ( ThreadState == 2 )
        goto LABEL_7;
    }
    else
    {
      CThreadData::SetThreadState(1, v10, v11);
    }
    ThreadData = CThreadData::GetThreadData();
    ++*(_DWORD *)ThreadData;
  }
LABEL_7:
  LeaveCriticalSection(&g_CriticalSection);
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_DWORD *)this + 66) = 24;
  if ( a3 )
    v3 = a3;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 60) = 1;
  *((_QWORD *)this + 12) = this;
  *((_WORD *)this + 98) = -1;
  *((_QWORD *)this + 28) = v3;
  *((_QWORD *)this + 6) = a2;
  *((_WORD *)this + 138) = -1;
  *((_WORD *)this + 139) = -1;
  result = this;
  *((_DWORD *)this + 54) = 0x7FFF;
  return result;
}

```

## disassembly

```asm
0x18005cc50  push    rbx
0x18005cc52  push    rbp
0x18005cc53  push    rsi
0x18005cc54  push    rdi
0x18005cc55  push    r14
0x18005cc57  sub     rsp, 20h
0x18005cc5b  xor     r14d, r14d
0x18005cc5e  lea     rdi, [rcx+0E8h]
0x18005cc65  lea     rax, ??_7CTxtEdit@@6BITextServices@@@; const CTxtEdit::`vftable'{for `ITextServices'}
0x18005cc6c  mov     rbx, rcx
0x18005cc6f  mov     [rcx], rax
0x18005cc72  mov     rsi, r8
0x18005cc75  lea     rax, ??_7CTxtEdit@@6BIRichEditOle@@@; const CTxtEdit::`vftable'{for `IRichEditOle'}
0x18005cc7c  mov     rbp, rdx
0x18005cc7f  mov     [rcx+8], rax
0x18005cc83  lea     rax, ??_7CTxtEdit@@6BITextDocument2@@@; const CTxtEdit::`vftable'{for `ITextDocument2'}
0x18005cc8a  mov     [rcx+10h], rax
0x18005cc8e  lea     rax, ??_7CUnknown@CTxtEdit@@6B@; const CTxtEdit::CUnknown::`vftable'
0x18005cc95  mov     [rcx+60h], r14
0x18005cc99  mov     [rcx+68h], r14
0x18005cc9d  mov     [rcx+70h], r14
0x18005cca1  mov     [rcx+78h], r14w
0x18005cca6  mov     [rcx+80h], r14
0x18005ccad  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005ccb4  mov     [rdi], rax
0x18005ccb7  call    cs:__imp_EnterCriticalSection
0x18005ccbe  nop     dword ptr [rax+rax+00h]
0x18005ccc3  inc     cs:?_cRefs@CW32System@@0KA; ulong CW32System::_cRefs
0x18005ccc9  call    cs:__imp_GetCurrentThreadId
0x18005ccd0  nop     dword ptr [rax+rax+00h]
0x18005ccd5  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, r14b; bool CW32System::_fOleinitCheckDisabled
0x18005ccdc  mov     [rdi+0Ch], eax
0x18005ccdf  jnz     short loc_18005CD09
0x18005cce1  cmp     cs:?_dwTlsIndex@CThreadData@@0KA, 0FFFFFFFFh; ulong CThreadData::_dwTlsIndex
0x18005cce8  jz      short loc_18005CD09
0x18005ccea  call    ?GetThreadState@CThreadData@@CA?AW4ThreadState@1@XZ; CThreadData::GetThreadState(void)
0x18005ccef  test    eax, eax
0x18005ccf1  jnz     short loc_18005CCFD
0x18005ccf3  lea     ecx, [rax+1]
0x18005ccf6  call    ?SetThreadState@CThreadData@@CAXW4ThreadState@1@@Z; CThreadData::SetThreadState(CThreadData::ThreadState)
0x18005ccfb  jmp     short loc_18005CD02
0x18005ccfd  cmp     eax, 2
0x18005cd00  jz      short loc_18005CD09
0x18005cd02  call    ?GetThreadData@CThreadData@@CAPEAV1@XZ; CThreadData::GetThreadData(void)
0x18005cd07  inc     dword ptr [rax]
0x18005cd09  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005cd10  call    cs:__imp_LeaveCriticalSection
0x18005cd17  nop     dword ptr [rax+rax+00h]
0x18005cd1c  mov     [rbx+0F8h], r14
0x18005cd23  test    rsi, rsi
0x18005cd26  mov     [rbx+100h], r14
0x18005cd2d  mov     dword ptr [rbx+108h], 18h
0x18005cd37  cmovnz  rdi, rsi
0x18005cd3b  mov     [rbx+118h], r14
0x18005cd42  or      eax, 0FFFFFFFFh
0x18005cd45  mov     [rbx+120h], r14
0x18005cd4c  mov     [rbx+40h], r14
0x18005cd50  mov     [rbx+48h], r14
0x18005cd54  mov     [rbx+50h], r14
0x18005cd58  mov     [rbx+58h], r14
0x18005cd5c  mov     [rbx+88h], r14
0x18005cd63  mov     [rbx+98h], r14
0x18005cd6a  mov     [rbx+0A0h], r14
0x18005cd71  mov     [rbx+0A8h], r14
0x18005cd78  mov     [rbx+128h], r14
0x18005cd7f  mov     [rbx+130h], r14
0x18005cd86  mov     dword ptr [rbx+0F0h], 1
0x18005cd90  mov     [rbx+60h], rbx
0x18005cd94  mov     [rbx+0C4h], ax
0x18005cd9b  mov     [rbx+0E0h], rdi
0x18005cda2  mov     [rbx+30h], rbp
0x18005cda6  mov     [rbx+114h], ax
0x18005cdad  mov     [rbx+116h], ax
0x18005cdb4  mov     rax, rbx
0x18005cdb7  mov     dword ptr [rbx+0D8h], 7FFFh
0x18005cdc1  add     rsp, 20h
0x18005cdc5  pop     r14
0x18005cdc7  pop     rdi
0x18005cdc8  pop     rsi
0x18005cdc9  pop     rbp
0x18005cdca  pop     rbx
0x18005cdcb  retn
```
