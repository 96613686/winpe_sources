# CKsQualityF::CKsQualityF(IUnknown *,ushort *,long *)

- ea: `0x10034f5a`
- end: `0x10035033`
- name: `??0CKsQualityF@@QAE@PAUIUnknown@@PAGPAJ@Z`
- size: `217`
- prototype: `CKsQualityF *__thiscall(CKsQualityF *__hidden this, struct IUnknown *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10034f20`

## callees

- `0x1001f2b0`
- `0x1002f736`
- `0x10034f5a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10035009`
- `KERNEL32!GetLastError` at `0x10035009`
- `KERNEL32!CreateEventW` at `0x10034fb1`
- `KERNEL32!CreateEventW` at `0x10034fd7`
- `KERNEL32!CreateEventW` at `0x10034fb1`
- `KERNEL32!CreateEventW` at `0x10034fd7`
- `KERNEL32!CreateThread` at `0x10034ff1`
- `KERNEL32!CreateThread` at `0x10034ff1`
- `KERNEL32!CreateSemaphoreW` at `0x10034fc6`
- `KERNEL32!CreateSemaphoreW` at `0x10034fc6`
- `KERNEL32!SetThreadPriority` at `0x10035001`
- `KERNEL32!SetThreadPriority` at `0x10035001`

## pseudocode

```c
CKsQualityF *__thiscall CKsQualityF::CKsQualityF(CKsQualityF *this, struct IUnknown *a2, unsigned __int16 *a3, int *a4)
{
  int v5; // eax
  HANDLE EventW; // eax
  HANDLE SemaphoreW; // eax
  HANDLE v8; // eax
  HANDLE v9; // eax
  signed int LastError; // eax
  unsigned int v11; // ecx
  DWORD ThreadId; // [esp+Ch] [ebp-4h] BYREF

  CUnknown::CUnknown(this, (const unsigned __int16 *)this, a2);
  this->CUnknown::INonDelegatingUnknown::__vftable = (CKsQualityF_vtbl *)&CKsQualityF::`vftable'{for `CUnknown'};
  this->IKsQualityForwarder::IKsObject::IUnknown::__vftable = (IKsQualityForwarder_vtbl *)&CKsQualityF::`vftable'{for `IKsQualityForwarder'};
  this->m_QualityManager = 0;
  this->m_Thread = 0;
  this->m_TerminateEvent = 0;
  this->m_FlushEvent = 0;
  if ( a2 )
  {
    v5 = KsOpenDefaultDevice(&_GUID_97ebaacb_95bd_11d0_a3ea_00a0c9223196, 0x80000000, (int)&this->m_QualityManager);
    *a4 = v5;
    if ( v5 >= 0 )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      this->m_FlushEvent = EventW;
      if ( EventW
        && (SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0), (this->m_FlushSemaphore = SemaphoreW) != 0)
        && (v8 = CreateEventW(0, 0, 0, 0), (this->m_TerminateEvent = v8) != 0)
        && (v9 = CreateThread(0, 0, CKsQualityF::QualityThread, this, 0, &ThreadId), (this->m_Thread = v9) != 0) )
      {
        SetThreadPriority(v9, 2);
      }
      else
      {
        LastError = GetLastError();
        v11 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v11 = LastError;
        *a4 = v11;
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
0x10034f5a  mov     edi, edi
0x10034f5c  push    ebp
0x10034f5d  mov     ebp, esp
0x10034f5f  push    ecx
0x10034f60  push    ebx
0x10034f61  push    esi
0x10034f62  push    edi
0x10034f63  push    [ebp+arg_0]; struct IUnknown *
0x10034f66  mov     esi, ecx
0x10034f68  push    ecx; unsigned __int16 *
0x10034f69  call    ??0CUnknown@@QAE@PBGPAUIUnknown@@@Z; CUnknown::CUnknown(ushort const *,IUnknown *)
0x10034f6e  xor     ebx, ebx
0x10034f70  mov     dword ptr [esi], offset ??_7CKsQualityF@@6BCUnknown@@@; const CKsQualityF::`vftable'{for `CUnknown'}
0x10034f76  lea     eax, [esi+10h]
0x10034f79  mov     dword ptr [esi+0Ch], offset ??_7CKsQualityF@@6BIKsQualityForwarder@@@; const CKsQualityF::`vftable'{for `IKsQualityForwarder'}
0x10034f80  mov     [eax], ebx
0x10034f82  mov     [esi+14h], ebx
0x10034f85  mov     [esi+18h], ebx
0x10034f88  mov     [esi+1Ch], ebx
0x10034f8b  cmp     [ebp+arg_0], ebx
0x10034f8e  jz      loc_10035021
0x10034f94  push    eax; int
0x10034f95  push    80000000h; int
0x10034f9a  push    offset __GUID_97ebaacb_95bd_11d0_a3ea_00a0c9223196; ClassGuid
0x10034f9f  call    _KsOpenDefaultDevice@12; KsOpenDefaultDevice(x,x,x)
0x10034fa4  mov     edi, [ebp+arg_8]
0x10034fa7  mov     [edi], eax
0x10034fa9  test    eax, eax
0x10034fab  js      short loc_1003502A
0x10034fad  push    ebx; lpName
0x10034fae  push    ebx; bInitialState
0x10034faf  push    ebx; bManualReset
0x10034fb0  push    ebx; lpEventAttributes
0x10034fb1  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10034fb7  mov     [esi+1Ch], eax
0x10034fba  test    eax, eax
0x10034fbc  jz      short loc_10035009
0x10034fbe  push    ebx; lpName
0x10034fbf  push    7FFFFFFFh; lMaximumCount
0x10034fc4  push    ebx; lInitialCount
0x10034fc5  push    ebx; lpSemaphoreAttributes
0x10034fc6  call    ds:__imp__CreateSemaphoreW@16; CreateSemaphoreW(x,x,x,x)
0x10034fcc  mov     [esi+20h], eax
0x10034fcf  test    eax, eax
0x10034fd1  jz      short loc_10035009
0x10034fd3  push    ebx; lpName
0x10034fd4  push    ebx; bInitialState
0x10034fd5  push    ebx; bManualReset
0x10034fd6  push    ebx; lpEventAttributes
0x10034fd7  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10034fdd  mov     [esi+18h], eax
0x10034fe0  test    eax, eax
0x10034fe2  jz      short loc_10035009
0x10034fe4  lea     eax, [ebp+ThreadId]
0x10034fe7  push    eax; lpThreadId
0x10034fe8  push    ebx; dwCreationFlags
0x10034fe9  push    esi; lpParameter
0x10034fea  push    offset ?QualityThread@CKsQualityF@@CGJPAV1@@Z; lpStartAddress
0x10034fef  push    ebx; dwStackSize
0x10034ff0  push    ebx; lpThreadAttributes
0x10034ff1  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x10034ff7  mov     [esi+14h], eax
0x10034ffa  test    eax, eax
0x10034ffc  jz      short loc_10035009
0x10034ffe  push    2; nPriority
0x10035000  push    eax; hThread
0x10035001  call    ds:__imp__SetThreadPriority@8; SetThreadPriority(x,x)
0x10035007  jmp     short loc_1003502A
0x10035009  call    ds:__imp__GetLastError@0; GetLastError()
0x1003500f  movzx   ecx, ax
0x10035012  or      ecx, 80070000h
0x10035018  test    eax, eax
0x1003501a  cmovle  ecx, eax
0x1003501d  mov     [edi], ecx
0x1003501f  jmp     short loc_1003502A
0x10035021  mov     eax, [ebp+arg_8]
0x10035024  mov     dword ptr [eax], 80040202h
0x1003502a  pop     edi
0x1003502b  mov     eax, esi
0x1003502d  pop     esi
0x1003502e  pop     ebx
0x1003502f  leave
0x10035030  retn    0Ch
```
