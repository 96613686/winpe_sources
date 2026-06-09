# CKsQualityF::CKsQualityF(IUnknown *,ushort *,long *)

- ea: `0x18001248c`
- end: `0x1800125ff`
- name: `??0CKsQualityF@@QEAA@PEAUIUnknown@@PEAGPEAJ@Z`
- size: `371`
- prototype: `CKsQualityF *__fastcall(CKsQualityF *__hidden this, struct IUnknown *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012440`

## callees

- `0x18001248c`
- `0x180012610`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800125cd`
- `KERNEL32!GetLastError` at `0x1800125cd`
- `KERNEL32!CreateEventW` at `0x180012528`
- `KERNEL32!CreateEventW` at `0x18001256d`
- `KERNEL32!CreateEventW` at `0x180012528`
- `KERNEL32!CreateEventW` at `0x18001256d`
- `KERNEL32!CreateThread` at `0x1800125a2`
- `KERNEL32!CreateThread` at `0x1800125a2`
- `KERNEL32!CreateSemaphoreW` at `0x18001254e`
- `KERNEL32!CreateSemaphoreW` at `0x18001254e`
- `KERNEL32!SetThreadPriority` at `0x1800125bf`
- `KERNEL32!SetThreadPriority` at `0x1800125bf`

## pseudocode

```c
CKsQualityF *__fastcall CKsQualityF::CKsQualityF(CKsQualityF *this, struct IUnknown *a2, unsigned __int16 *a3, int *a4)
{
  IUnknown *v6; // rax
  int v7; // eax
  HANDLE EventW; // rax
  HANDLE SemaphoreW; // rax
  HANDLE v10; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned __int16 *ThreadId; // [rsp+50h] [rbp+18h] BYREF

  ThreadId = a3;
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  this->m_Thread = 0;
  v6 = a2;
  this->m_TerminateEvent = 0;
  if ( !a2 )
    v6 = (IUnknown *)this;
  this->m_FlushEvent = 0;
  this->m_pUnknown = v6;
  this->m_cRef = 0;
  this->CUnknown::INonDelegatingUnknown::__vftable = (CKsQualityF_vtbl *)&CKsQualityF::`vftable'{for `CUnknown'};
  this->IKsQualityForwarder::IKsObject::IUnknown::__vftable = (IKsQualityForwarder_vtbl *)&CKsQualityF::`vftable'{for `IKsQualityForwarder'};
  this->m_QualityManager = 0;
  if ( a2 )
  {
    v7 = KsOpenDefaultDevice(&GUID_97ebaacb_95bd_11d0_a3ea_00a0c9223196);
    *a4 = v7;
    if ( v7 >= 0 )
    {
      LODWORD(ThreadId) = 0;
      EventW = CreateEventW(0, 0, 0, 0);
      this->m_FlushEvent = EventW;
      if ( EventW
        && (SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0), (this->m_FlushSemaphore = SemaphoreW) != 0)
        && (v10 = CreateEventW(0, 0, 0, 0), (this->m_TerminateEvent = v10) != 0)
        && (Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CKsQualityF::QualityThread, this, 0, (LPDWORD)&ThreadId),
            (this->m_Thread = Thread) != 0) )
      {
        SetThreadPriority(Thread, 2);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        *a4 = LastError;
      }
    }
  }
  else
  {
    *a4 = -2147220990;
  }
  return this;
}

```

## disassembly

```asm
0x18001248c  mov     [rsp+arg_0], rbx
0x180012491  mov     [rsp+ThreadId], r8
0x180012496  push    rdi
0x180012497  sub     rsp, 30h
0x18001249b  mov     rdi, r9
0x18001249e  mov     rbx, rcx
0x1800124a1  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800124a8  test    rdx, rdx
0x1800124ab  mov     qword ptr [rcx+28h], 0
0x1800124b3  mov     rax, rdx
0x1800124b6  mov     qword ptr [rcx+30h], 0
0x1800124be  cmovz   rax, rcx
0x1800124c2  mov     qword ptr [rcx+38h], 0
0x1800124ca  mov     [rcx+8], rax
0x1800124ce  lea     r8, [rcx+20h]
0x1800124d2  lea     rax, ??_7CKsQualityF@@6BCUnknown@@@; const CKsQualityF::`vftable'{for `CUnknown'}
0x1800124d9  mov     dword ptr [rcx+10h], 0
0x1800124e0  mov     [rcx], rax
0x1800124e3  lea     rax, ??_7CKsQualityF@@6BIKsQualityForwarder@@@; const CKsQualityF::`vftable'{for `IKsQualityForwarder'}
0x1800124ea  mov     [rcx+18h], rax
0x1800124ee  mov     qword ptr [r8], 0
0x1800124f5  jz      loc_1800125E9
0x1800124fb  mov     edx, 80000000h
0x180012500  lea     rcx, _GUID_97ebaacb_95bd_11d0_a3ea_00a0c9223196; InterfaceClassGuid
0x180012507  call    KsOpenDefaultDevice
0x18001250c  mov     [rdi], eax
0x18001250e  test    eax, eax
0x180012510  js      loc_1800125F0
0x180012516  xor     r9d, r9d; lpName
0x180012519  mov     dword ptr [rsp+38h+ThreadId], 0
0x180012521  xor     r8d, r8d; bInitialState
0x180012524  xor     edx, edx; bManualReset
0x180012526  xor     ecx, ecx; lpEventAttributes
0x180012528  call    cs:__imp_CreateEventW
0x18001252f  nop     dword ptr [rax+rax+00h]
0x180012534  mov     [rbx+38h], rax
0x180012538  test    rax, rax
0x18001253b  jz      loc_1800125CD
0x180012541  xor     r9d, r9d; lpName
0x180012544  xor     edx, edx; lInitialCount
0x180012546  xor     ecx, ecx; lpSemaphoreAttributes
0x180012548  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18001254e  call    cs:__imp_CreateSemaphoreW
0x180012555  nop     dword ptr [rax+rax+00h]
0x18001255a  mov     [rbx+40h], rax
0x18001255e  test    rax, rax
0x180012561  jz      short loc_1800125CD
0x180012563  xor     r9d, r9d; lpName
0x180012566  xor     r8d, r8d; bInitialState
0x180012569  xor     edx, edx; bManualReset
0x18001256b  xor     ecx, ecx; lpEventAttributes
0x18001256d  call    cs:__imp_CreateEventW
0x180012574  nop     dword ptr [rax+rax+00h]
0x180012579  mov     [rbx+30h], rax
0x18001257d  test    rax, rax
0x180012580  jz      short loc_1800125CD
0x180012582  lea     rax, [rsp+38h+ThreadId]
0x180012587  mov     r9, rbx; lpParameter
0x18001258a  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18001258f  lea     r8, ?QualityThread@CKsQualityF@@CAJPEAV1@@Z; lpStartAddress
0x180012596  xor     edx, edx; dwStackSize
0x180012598  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800125a0  xor     ecx, ecx; lpThreadAttributes
0x1800125a2  call    cs:__imp_CreateThread
0x1800125a9  nop     dword ptr [rax+rax+00h]
0x1800125ae  mov     [rbx+28h], rax
0x1800125b2  test    rax, rax
0x1800125b5  jz      short loc_1800125CD
0x1800125b7  mov     edx, 2; nPriority
0x1800125bc  mov     rcx, rax; hThread
0x1800125bf  call    cs:__imp_SetThreadPriority
0x1800125c6  nop     dword ptr [rax+rax+00h]
0x1800125cb  jmp     short loc_1800125F0
0x1800125cd  call    cs:__imp_GetLastError
0x1800125d4  nop     dword ptr [rax+rax+00h]
0x1800125d9  test    eax, eax
0x1800125db  jle     short loc_1800125E5
0x1800125dd  movzx   eax, ax
0x1800125e0  or      eax, 80070000h
0x1800125e5  mov     [rdi], eax
0x1800125e7  jmp     short loc_1800125F0
0x1800125e9  mov     dword ptr [r9], 80040202h
0x1800125f0  mov     rax, rbx
0x1800125f3  mov     rbx, [rsp+38h+arg_0]
0x1800125f8  add     rsp, 30h
0x1800125fc  pop     rdi
0x1800125fd  retn
```
