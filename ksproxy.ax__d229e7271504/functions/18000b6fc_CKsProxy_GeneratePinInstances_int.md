# CKsProxy::GeneratePinInstances(int)

- ea: `0x18000b6fc`
- end: `0x18000bdd3`
- name: `?GeneratePinInstances@CKsProxy@@QEAAJH@Z`
- size: `1751`
- prototype: `__int64 __fastcall(CKsProxy *__hidden this, int)`
- caller_count: `9`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x18000a840`
- `0x180019150`
- `0x1800196f0`
- `0x180026ac0`
- `0x180026da0`
- `0x180026de0`
- `0x180029ad0`
- `0x18002d780`
- `0x18002dc30`

## callees

- `0x180003d60`
- `0x18000b6fc`
- `0x18000bde0`
- `0x18000bf88`
- `0x18000c14c`
- `0x18000c93c`
- `0x18000c9f0`
- `0x18000cc78`
- `0x18000d4b0`
- `0x18000d7fc`
- `0x18000d88c`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x180036504`
- `0x18003f33c`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b787`
- `KERNEL32!GetLastError` at `0x18000b7f0`
- `KERNEL32!GetLastError` at `0x18000b835`
- `KERNEL32!GetLastError` at `0x18000b787`
- `KERNEL32!GetLastError` at `0x18000b7f0`
- `KERNEL32!GetLastError` at `0x18000b835`
- `KERNEL32!CreateEventW` at `0x18000b772`
- `KERNEL32!CreateEventW` at `0x18000b772`
- `KERNEL32!CloseHandle` at `0x18000b881`
- `KERNEL32!CloseHandle` at `0x18000b980`
- `KERNEL32!CloseHandle` at `0x18000b881`
- `KERNEL32!CloseHandle` at `0x18000b980`
- `KERNEL32!GetOverlappedResult` at `0x18000b825`
- `KERNEL32!GetOverlappedResult` at `0x18000b825`
- `KERNEL32!DeviceIoControl` at `0x18000b7e0`
- `KERNEL32!DeviceIoControl` at `0x18000b7e0`

## pseudocode

```c
__int64 __fastcall CKsProxy::GeneratePinInstances(CKsProxy *this, int a2)
{
  char *m_FilterHandle; // r14
  int v3; // r15d
  signed int v5; // eax
  signed int v6; // ebx
  signed int LastError; // eax
  signed int v8; // eax
  unsigned int v9; // r13d
  int v10; // ebx
  CGenericList<CBasePin> *p_m_PinList; // r14
  char *v12; // rcx
  signed int v13; // eax
  unsigned int v14; // edx
  CKsProxy *m_PinClockHandle; // rcx
  bool v16; // sf
  CBaseList::CNode *m_pFirst; // rax
  struct __POSITION *v18; // r12
  unsigned int v19; // esi
  CBasePin *m_pObject; // rbx
  CBaseList::CNode **p_m_pPrev; // r15
  unsigned int PinFactoryId; // eax
  unsigned __int64 v23; // rcx
  unsigned int v24; // r14d
  unsigned int m_pUnknown_high; // r12d
  IPin_vtbl *v26; // rax
  CBaseList::CNode **p_m_pLast; // r14
  CGenericList<CBasePin> *v28; // rcx
  CBasePin *v29; // rax
  struct __POSITION **v30; // rax
  CBaseList::CNode **v31; // rdx
  IPin_vtbl *v32; // rax
  bool v33; // zf
  void (*v34)(void); // rax
  unsigned __int16 *v35; // rdx
  struct _GUID *v36; // r8
  unsigned __int16 *v37; // rsi
  CKsInputPin *OutputPin; // rax
  CKsInputPin *v39; // rax
  struct _GUID *v40; // r9
  char *v41; // rbx
  unsigned __int64 v42; // rsi
  int (__fastcall **v43)(char *, GUID *, __int64 *); // rax
  void (*v44)(void); // rax
  CBaseList::CNode *v45; // rax
  CBaseList::CNode *m_pNext; // rbx
  __int64 v47; // rcx
  int v49; // [rsp+40h] [rbp-49h] BYREF
  int v50; // [rsp+44h] [rbp-45h]
  __int64 v51; // [rsp+48h] [rbp-41h] BYREF
  __int64 lpOutBuffer; // [rsp+50h] [rbp-39h] BYREF
  __int64 v53; // [rsp+58h] [rbp-31h] BYREF
  unsigned __int16 *v54; // [rsp+60h] [rbp-29h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-21h] BYREF
  GUID InBuffer; // [rsp+88h] [rbp-1h] BYREF
  int v57; // [rsp+98h] [rbp+Fh]
  int v58; // [rsp+9Ch] [rbp+13h]
  unsigned int OutBuffer; // [rsp+F0h] [rbp+67h] BYREF
  int v60; // [rsp+F8h] [rbp+6Fh]
  __int64 BytesReturned; // [rsp+100h] [rbp+77h] BYREF
  struct __POSITION *v62; // [rsp+108h] [rbp+7Fh] BYREF

  v60 = a2;
  m_FilterHandle = (char *)this->m_FilterHandle;
  v3 = a2;
  OutBuffer = 0;
  LODWORD(BytesReturned) = 0;
  v57 = 1;
  v58 = 1;
  InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  if ( (unsigned __int64)(m_FilterHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return (unsigned int)-2147024890;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(
           m_FilterHandle,
           0x2F0003u,
           &InBuffer,
           0x18u,
           &OutBuffer,
           4u,
           (LPDWORD)&BytesReturned,
           &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v6 = -2147024875;
          goto LABEL_19;
        case 0x105uLL:
          v6 = -2147024662;
          goto LABEL_19;
        case 0x107uLL:
          v6 = -2147023595;
          goto LABEL_19;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 != -2147023899 )
        goto LABEL_19;
      if ( !GetOverlappedResult(m_FilterHandle, &Overlapped, (LPDWORD)&BytesReturned, 1) )
      {
        v8 = GetLastError();
        v6 = v8;
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        goto LABEL_19;
      }
    }
    v6 = 0;
LABEL_19:
    CloseHandle(Overlapped.hEvent);
    goto LABEL_20;
  }
  v5 = GetLastError();
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
LABEL_20:
  if ( v6 < 0 )
    return (unsigned int)v6;
  v9 = OutBuffer;
  v10 = 0;
  v50 = 0;
  if ( !OutBuffer )
    goto LABEL_93;
  p_m_PinList = &this->m_PinList;
  do
  {
    v12 = (char *)this->m_FilterHandle;
    --v9;
    lpOutBuffer = 0;
    LODWORD(BytesReturned) = 0;
    *(GUID *)&Overlapped.Internal = GUID_8c134960_51ad_11cf_878a_94f801c10000;
    Overlapped.Pointer = (PVOID)0x100000000LL;
    Overlapped.hEvent = (HANDLE)v9;
    v13 = KsSynchronousDeviceControl(v12, 0x2F0003u, &Overlapped, 0x20u, &lpOutBuffer, 8u, (LPDWORD)&BytesReturned);
    v14 = lpOutBuffer;
    m_PinClockHandle = 0;
    v16 = v13 < 0;
    m_pFirst = p_m_PinList->m_pFirst;
    if ( v16 )
      v14 = 0;
    v18 = 0;
    v19 = 0;
    LODWORD(lpOutBuffer) = v14;
    v62 = 0;
    if ( m_pFirst )
    {
      while ( 1 )
      {
        m_pObject = (CBasePin *)m_pFirst->m_pObject;
        p_m_pPrev = &m_pFirst->m_pNext->m_pPrev;
        PinFactoryId = CKsProxy::GetPinFactoryId(m_PinClockHandle, m_pObject);
        v23 = v19 + 1;
        v24 = PinFactoryId;
        if ( PinFactoryId != v9 )
          v23 = v19;
        v19 = v23;
        if ( CKsProxy::GetPinHandle((CKsProxy *)v23, m_pObject) )
          goto LABEL_62;
        m_PinClockHandle = (CKsProxy *)this->m_PinClockHandle;
        if ( m_PinClockHandle && this->m_PinClockSource == m_pObject )
        {
          CloseHandle(m_PinClockHandle);
          this->m_PinClockHandle = 0;
          v50 = 1;
        }
        if ( v24 == v9 )
        {
          if ( v18 )
          {
            v49 = 0;
            m_pUnknown_high = 0;
            m_pObject->QueryDirection(&m_pObject->IPin, (_PinDirection *)&v49);
            if ( v49 )
            {
              if ( v49 == 1 )
              {
                v26 = m_pObject->IPin::IUnknown::__vftable;
                BytesReturned = 0;
                if ( v26->QueryInterface(
                       &m_pObject->IPin,
                       &GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed,
                       (void **)&BytesReturned) >= 0 )
                {
                  m_pUnknown_high = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)BytesReturned + 40LL))(BytesReturned);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)BytesReturned + 16LL))(BytesReturned);
                }
              }
            }
            else
            {
              m_pUnknown_high = HIDWORD(m_pObject[3].m_pUnknown);
            }
            p_m_pLast = &this->m_PinList.m_pLast;
            v28 = &this->m_PinList;
            if ( m_pUnknown_high <= 1 )
            {
              if ( p_m_pPrev )
                p_m_pLast = p_m_pPrev;
              v29 = (CBasePin *)CBaseList::RemoveI(v28, *p_m_pLast);
              v18 = v62;
            }
            else
            {
              v29 = (CBasePin *)CBaseList::RemoveI(v28, (CBaseList::CNode *)v62);
              if ( p_m_pPrev )
                p_m_pLast = p_m_pPrev;
              v18 = (struct __POSITION *)*p_m_pLast;
              v62 = (struct __POSITION *)*p_m_pLast;
            }
            m_pObject = v29;
            --v19;
          }
          else
          {
            v30 = (struct __POSITION **)&this->m_PinList.m_pLast;
            if ( p_m_pPrev )
              v30 = (struct __POSITION **)p_m_pPrev;
            m_pObject = 0;
            v18 = *v30;
            v62 = *v30;
          }
        }
        else
        {
          if ( v24 < OutBuffer )
            goto LABEL_62;
          v31 = &this->m_PinList.m_pLast;
          if ( p_m_pPrev )
            v31 = p_m_pPrev;
          CBaseList::RemoveI(&this->m_PinList, *v31);
        }
        if ( m_pObject )
        {
          LODWORD(BytesReturned) = 0;
          m_pObject->QueryDirection(&m_pObject->IPin, (_PinDirection *)&BytesReturned);
          m_PinClockHandle = (CKsProxy *)(unsigned int)BytesReturned;
          if ( !(_DWORD)BytesReturned )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&m_pObject[3].m_pUnknown + 1, 0xFFFFFFFF) == 1 )
            {
              ((void (__fastcall *)(CBasePin *, __int64))m_pObject->~CBasePin)(m_pObject, 1);
              goto LABEL_62;
            }
            goto LABEL_61;
          }
          if ( (_DWORD)BytesReturned != 1 )
            goto LABEL_62;
          v32 = m_pObject->IPin::IUnknown::__vftable;
          v51 = 0;
          if ( v32->QueryInterface(&m_pObject->IPin, &GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed, (void **)&v51) < 0 )
            goto LABEL_62;
          v33 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v51 + 48LL))(v51) == 1;
          v34 = *(void (**)(void))(*(_QWORD *)v51 + 16LL);
          if ( !v33 )
          {
            v34();
LABEL_61:
            DerefPipeFromPin(&m_pObject->IPin);
            goto LABEL_62;
          }
          v34();
        }
LABEL_62:
        m_pFirst = (CBaseList::CNode *)p_m_pPrev;
        if ( !p_m_pPrev )
        {
          v14 = lpOutBuffer;
          p_m_PinList = &this->m_PinList;
          v3 = v60;
          break;
        }
      }
    }
    if ( v19 >= v14 && v19 | v14 || v18 )
    {
      if ( v19 > v14 && v14 && v18 )
      {
        LODWORD(BytesReturned) = 0;
        v41 = (char *)CBaseList::RemoveI(p_m_PinList, (CBaseList::CNode *)v18);
        v42 = (unsigned __int64)(v41 + 24);
        (*(void (__fastcall **)(char *, __int64 *))(*((_QWORD *)v41 + 3) + 72LL))(v41 + 24, &BytesReturned);
        if ( !(_DWORD)BytesReturned )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 + 165, 0xFFFFFFFF) != 1 )
            goto LABEL_90;
          goto LABEL_103;
        }
        if ( (_DWORD)BytesReturned == 1 )
        {
          v43 = *(int (__fastcall ***)(char *, GUID *, __int64 *))v42;
          v53 = 0;
          if ( (*v43)((char *)v42, &GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed, &v53) >= 0 )
          {
            v33 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v53 + 48LL))(v53) == 1;
            v44 = *(void (**)(void))(*(_QWORD *)v53 + 16LL);
            if ( v33 )
            {
              v44();
              continue;
            }
            v44();
LABEL_90:
            DerefPipeFromPin((struct IPin *)(v42 & -(__int64)(v41 != 0)));
          }
        }
      }
    }
    else
    {
      LODWORD(BytesReturned) = 0;
      v54 = 0;
      if ( CKsProxy::GetPinFactoryDataFlow(this, v9, (enum KSPIN_DATAFLOW *)&BytesReturned) >= 0
        && (int)CKsProxy::ConstructPinName(this, v9, (enum KSPIN_DATAFLOW)BytesReturned, &v54) >= 0 )
      {
        v37 = v54;
        LODWORD(v62) = 0;
        if ( (_DWORD)BytesReturned == 1 )
        {
          v39 = (CKsInputPin *)operator new(0x298u);
          if ( !v39 )
            goto LABEL_77;
          OutputPin = CKsInputPin::CKsInputPin(v39, v35, v9, v40, this, (int *)&v62, v37);
LABEL_76:
          v41 = (char *)OutputPin;
        }
        else
        {
          if ( (_DWORD)BytesReturned == 2 )
          {
            OutputPin = (CKsInputPin *)CreateOutputPin((unsigned __int16 *)1, v9, v36, this, (int *)&v62, v54, v3);
            goto LABEL_76;
          }
LABEL_77:
          v41 = 0;
        }
        operator delete(v37, (unsigned __int64)v35);
        if ( !v41 )
          continue;
        if ( (int)v62 >= 0 )
        {
          CBaseList::AddHeadI(p_m_PinList, v41);
          continue;
        }
LABEL_103:
        (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v41 + 24LL))(v41, 1);
      }
    }
  }
  while ( v9 );
  v10 = v50;
LABEL_93:
  if ( !this->m_PinClockHandle )
    CKsProxy::DetermineClockSource(this);
  if ( v10 )
    CBaseFilter::NotifyEvent(this, 81, 0, 0);
  v45 = this->m_MarshalerList.m_pFirst;
  if ( v45 )
  {
    do
    {
      m_pNext = v45->m_pNext;
      v47 = *((_QWORD *)v45->m_pObject + 5);
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 56LL))(v47);
      v45 = m_pNext;
    }
    while ( m_pNext );
  }
  return 0;
}

```

## disassembly

```asm
0x18000b6fc  mov     [rsp-8+arg_8], edx
0x18000b700  push    rbp
0x18000b701  push    rbx
0x18000b702  push    rsi
0x18000b703  push    rdi
0x18000b704  push    r12
0x18000b706  push    r13
0x18000b708  push    r14
0x18000b70a  push    r15
0x18000b70c  lea     rbp, [rsp-1Fh]
0x18000b711  sub     rsp, 0A8h
0x18000b718  mov     r14, [rcx+170h]
0x18000b71f  mov     r15d, edx
0x18000b722  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x18000b729  mov     rdi, rcx
0x18000b72c  mov     [rbp+57h+OutBuffer], 0
0x18000b733  mov     dword ptr [rbp+57h+BytesReturned], 0
0x18000b73a  lea     rax, [r14-1]
0x18000b73e  mov     [rbp+57h+var_48], 1
0x18000b745  mov     [rbp+57h+var_44], 1
0x18000b74c  movdqu  [rbp+57h+InBuffer], xmm0
0x18000b751  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b755  ja      loc_18000BDB7
0x18000b75b  xorps   xmm0, xmm0
0x18000b75e  xor     r9d, r9d; lpName
0x18000b761  xor     r8d, r8d; bInitialState
0x18000b764  xor     ecx, ecx; lpEventAttributes
0x18000b766  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18000b76a  lea     edx, [r9+1]; bManualReset
0x18000b76e  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18000b772  call    cs:__imp_CreateEventW
0x18000b779  nop     dword ptr [rax+rax+00h]
0x18000b77e  mov     [rbp+57h+Overlapped.hEvent], rax
0x18000b782  test    rax, rax
0x18000b785  jnz     short loc_18000B7AB
0x18000b787  call    cs:__imp_GetLastError
0x18000b78e  nop     dword ptr [rax+rax+00h]
0x18000b793  mov     ebx, eax
0x18000b795  test    eax, eax
0x18000b797  jle     loc_18000B88D
0x18000b79d  movzx   ebx, ax
0x18000b7a0  or      ebx, 80070000h
0x18000b7a6  jmp     loc_18000B88D
0x18000b7ab  lea     rax, [rbp+57h+Overlapped]
0x18000b7af  mov     r9d, 18h; nInBufferSize
0x18000b7b5  mov     [rsp+0E0h+lpOverlapped], rax; lpOverlapped
0x18000b7ba  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18000b7be  lea     rax, [rbp+57h+BytesReturned]
0x18000b7c2  mov     edx, 2F0003h; dwIoControlCode
0x18000b7c7  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x18000b7cc  mov     rcx, r14; hDevice
0x18000b7cf  lea     rax, [rbp+57h+OutBuffer]
0x18000b7d3  mov     [rsp+0E0h+nOutBufferSize], 4; nOutBufferSize
0x18000b7db  mov     [rsp+0E0h+lpOutBuffer], rax; lpOutBuffer
0x18000b7e0  call    cs:__imp_DeviceIoControl
0x18000b7e7  nop     dword ptr [rax+rax+00h]
0x18000b7ec  test    eax, eax
0x18000b7ee  jnz     short loc_18000B84E
0x18000b7f0  call    cs:__imp_GetLastError
0x18000b7f7  nop     dword ptr [rax+rax+00h]
0x18000b7fc  mov     ebx, eax
0x18000b7fe  mov     esi, 80070000h
0x18000b803  test    eax, eax
0x18000b805  jle     short loc_18000B80C
0x18000b807  movzx   ebx, ax
0x18000b80a  or      ebx, esi
0x18000b80c  cmp     ebx, 800703E5h
0x18000b812  jnz     short loc_18000B87D
0x18000b814  mov     r9d, 1; bWait
0x18000b81a  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x18000b81e  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18000b822  mov     rcx, r14; hFile
0x18000b825  call    cs:__imp_GetOverlappedResult
0x18000b82c  nop     dword ptr [rax+rax+00h]
0x18000b831  test    eax, eax
0x18000b833  jnz     short loc_18000B866
0x18000b835  call    cs:__imp_GetLastError
0x18000b83c  nop     dword ptr [rax+rax+00h]
0x18000b841  mov     ebx, eax
0x18000b843  test    eax, eax
0x18000b845  jle     short loc_18000B87D
0x18000b847  movzx   ebx, ax
0x18000b84a  or      ebx, esi
0x18000b84c  jmp     short loc_18000B87D
0x18000b84e  mov     rax, [rbp+57h+Overlapped.Internal]
0x18000b852  sub     rax, 101h
0x18000b858  jz      short loc_18000B878
0x18000b85a  sub     rax, 4
0x18000b85e  jz      short loc_18000B871
0x18000b860  cmp     rax, 2
0x18000b864  jz      short loc_18000B86A
0x18000b866  xor     ebx, ebx
0x18000b868  jmp     short loc_18000B87D
0x18000b86a  mov     ebx, 80070515h
0x18000b86f  jmp     short loc_18000B87D
0x18000b871  mov     ebx, 800700EAh
0x18000b876  jmp     short loc_18000B87D
0x18000b878  mov     ebx, 80070015h
0x18000b87d  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x18000b881  call    cs:__imp_CloseHandle
0x18000b888  nop     dword ptr [rax+rax+00h]
0x18000b88d  test    ebx, ebx
0x18000b88f  js      loc_18000BDBC
0x18000b895  mov     r13d, [rbp+57h+OutBuffer]
0x18000b899  xor     ebx, ebx
0x18000b89b  mov     [rbp+57h+var_9C], ebx
0x18000b89e  test    r13d, r13d
0x18000b8a1  jz      loc_18000BD2D
0x18000b8a7  lea     r14, [rdi+120h]
0x18000b8ae  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x18000b8b5  mov     rcx, [rdi+170h]; hFile
0x18000b8bc  lea     rax, [rbp+57h+BytesReturned]
0x18000b8c0  mov     [rsp+0E0h+lpBytesReturned], rax; lpNumberOfBytesTransferred
0x18000b8c5  lea     r8, [rbp+57h+Overlapped]; lpInBuffer
0x18000b8c9  lea     rax, [rbp+57h+var_90]
0x18000b8cd  mov     [rsp+0E0h+nOutBufferSize], 8; DWORD
0x18000b8d5  dec     r13d
0x18000b8d8  mov     [rsp+0E0h+lpOutBuffer], rax; LPVOID
0x18000b8dd  mov     r9d, 20h ; ' '; nInBufferSize
0x18000b8e3  mov     [rbp+57h+var_90], 0
0x18000b8eb  mov     edx, 2F0003h; dwIoControlCode
0x18000b8f0  mov     dword ptr [rbp+57h+BytesReturned], 0
0x18000b8f7  movdqu  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18000b8fc  mov     dword ptr [rbp+57h+Overlapped.10h], 0
0x18000b903  mov     dword ptr [rbp+57h+Overlapped.10h+4], 1
0x18000b90a  mov     dword ptr [rbp+57h+Overlapped.hEvent], r13d
0x18000b90e  mov     dword ptr [rbp+57h+Overlapped.hEvent+4], 0
0x18000b915  call    KsSynchronousDeviceControl
0x18000b91a  mov     edx, dword ptr [rbp+57h+var_90]
0x18000b91d  xor     ecx, ecx; this
0x18000b91f  test    eax, eax
0x18000b921  mov     rax, [r14]
0x18000b924  cmovs   edx, ecx
0x18000b927  xor     r12d, r12d
0x18000b92a  xor     esi, esi
0x18000b92c  mov     dword ptr [rbp+57h+var_90], edx
0x18000b92f  mov     [rbp+57h+arg_18], r12
0x18000b933  test    rax, rax
0x18000b936  jz      loc_18000BB5B
0x18000b93c  mov     rbx, [rax+10h]
0x18000b940  mov     r15, [rax+8]
0x18000b944  mov     rdx, rbx; struct CBasePin *
0x18000b947  call    ?GetPinFactoryId@CKsProxy@@QEAAKPEAVCBasePin@@@Z; CKsProxy::GetPinFactoryId(CBasePin *)
0x18000b94c  lea     ecx, [rsi+1]
0x18000b94f  cmp     eax, r13d
0x18000b952  mov     rdx, rbx; struct CBasePin *
0x18000b955  mov     r14d, eax
0x18000b958  cmovnz  ecx, esi; this
0x18000b95b  mov     esi, ecx
0x18000b95d  call    ?GetPinHandle@CKsProxy@@QEAAPEAXPEAVCBasePin@@@Z; CKsProxy::GetPinHandle(CBasePin *)
0x18000b962  test    rax, rax
0x18000b965  jnz     loc_18000BB41
0x18000b96b  mov     rcx, [rdi+180h]; hObject
0x18000b972  test    rcx, rcx
0x18000b975  jz      short loc_18000B99E
0x18000b977  cmp     [rdi+1E0h], rbx
0x18000b97e  jnz     short loc_18000B99E
0x18000b980  call    cs:__imp_CloseHandle
0x18000b987  nop     dword ptr [rax+rax+00h]
0x18000b98c  mov     qword ptr [rdi+180h], 0
0x18000b997  mov     [rbp+57h+var_9C], 1
0x18000b99e  cmp     r14d, r13d
0x18000b9a1  jnz     loc_18000BA8A
0x18000b9a7  test    r12, r12
0x18000b9aa  jz      loc_18000BA71
0x18000b9b0  lea     r14, [rbx+18h]
0x18000b9b4  mov     [rbp+57h+var_A0], 0
0x18000b9bb  mov     rax, [r14]
0x18000b9be  lea     rdx, [rbp+57h+var_A0]
0x18000b9c2  mov     rcx, r14
0x18000b9c5  xor     r12d, r12d
0x18000b9c8  mov     rax, [rax+48h]
0x18000b9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9d1  mov     edx, [rbp+57h+var_A0]
0x18000b9d4  test    edx, edx
0x18000b9d6  jz      short loc_18000BA23
0x18000b9d8  cmp     edx, 1
0x18000b9db  jnz     short loc_18000BA2A
0x18000b9dd  mov     rax, [r14]
0x18000b9e0  lea     r8, [rbp+57h+BytesReturned]
0x18000b9e4  lea     rdx, _GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed
0x18000b9eb  mov     [rbp+57h+BytesReturned], r12
0x18000b9ef  mov     rcx, r14
0x18000b9f2  mov     rax, [rax]
0x18000b9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9fa  test    eax, eax
0x18000b9fc  js      short loc_18000BA2A
0x18000b9fe  mov     rcx, [rbp+57h+BytesReturned]
0x18000ba02  mov     rax, [rcx]
0x18000ba05  mov     rax, [rax+28h]
0x18000ba09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba0e  mov     rcx, [rbp+57h+BytesReturned]
0x18000ba12  mov     r12d, eax
0x18000ba15  mov     rdx, [rcx]
0x18000ba18  mov     rax, [rdx+10h]
0x18000ba1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba21  jmp     short loc_18000BA2A
0x18000ba23  mov     r12d, [rbx+294h]
0x18000ba2a  lea     r14, [rdi+128h]
0x18000ba31  lea     rcx, [rdi+120h]; this
0x18000ba38  cmp     r12d, 1
0x18000ba3c  jbe     short loc_18000BA57
0x18000ba3e  mov     rdx, [rbp+57h+arg_18]; struct __POSITION *
0x18000ba42  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000ba47  test    r15, r15
0x18000ba4a  cmovnz  r14, r15
0x18000ba4e  mov     r12, [r14]
0x18000ba51  mov     [rbp+57h+arg_18], r12
0x18000ba55  jmp     short loc_18000BA6A
0x18000ba57  test    r15, r15
0x18000ba5a  cmovnz  r14, r15
0x18000ba5e  mov     rdx, [r14]; struct __POSITION *
0x18000ba61  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000ba66  mov     r12, [rbp+57h+arg_18]
0x18000ba6a  mov     rbx, rax
0x18000ba6d  dec     esi
0x18000ba6f  jmp     short loc_18000BAB1
0x18000ba71  test    r15, r15
0x18000ba74  lea     rax, [rdi+128h]
0x18000ba7b  cmovnz  rax, r15
0x18000ba7f  xor     ebx, ebx
0x18000ba81  mov     r12, [rax]
0x18000ba84  mov     [rbp+57h+arg_18], r12
0x18000ba88  jmp     short loc_18000BAB1
0x18000ba8a  cmp     r14d, [rbp+57h+OutBuffer]
0x18000ba8e  jb      loc_18000BB41
0x18000ba94  test    r15, r15
0x18000ba97  lea     rdx, [rdi+128h]
0x18000ba9e  lea     rcx, [rdi+120h]; this
0x18000baa5  cmovnz  rdx, r15
0x18000baa9  mov     rdx, [rdx]; struct __POSITION *
0x18000baac  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000bab1  test    rbx, rbx
0x18000bab4  jz      loc_18000BB41
0x18000baba  lea     r14, [rbx+18h]
0x18000babe  mov     dword ptr [rbp+57h+BytesReturned], 0
0x18000bac5  mov     rax, [r14]
0x18000bac8  lea     rdx, [rbp+57h+BytesReturned]
0x18000bacc  mov     rcx, r14
0x18000bacf  mov     rax, [rax+48h]
0x18000bad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bad8  mov     ecx, dword ptr [rbp+57h+BytesReturned]
0x18000badb  test    ecx, ecx
0x18000badd  jz      loc_18000BBE1
0x18000bae3  cmp     ecx, 1
0x18000bae6  jnz     short loc_18000BB41
0x18000bae8  mov     rax, [r14]
0x18000baeb  lea     r8, [rbp+57h+var_98]
0x18000baef  lea     rdx, _GUID_48c5e0d4_99ee_454b_a672_8ac5fb5deaed
0x18000baf6  mov     [rbp+57h+var_98], 0
0x18000bafe  mov     rcx, r14
0x18000bb01  mov     rax, [rax]
0x18000bb04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb09  test    eax, eax
0x18000bb0b  js      short loc_18000BB41
0x18000bb0d  mov     rcx, [rbp+57h+var_98]
0x18000bb11  mov     rax, [rcx]
0x18000bb14  mov     rax, [rax+30h]
0x18000bb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb1d  mov     rcx, [rbp+57h+var_98]
0x18000bb21  cmp     eax, 1
0x18000bb24  mov     rax, [rcx]
0x18000bb27  mov     rax, [rax+10h]
0x18000bb2b  jnz     short loc_18000BB34
0x18000bb2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb32  jmp     short loc_18000BB41
0x18000bb34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb39  mov     rcx, r14; struct IPin *
0x18000bb3c  call    ?DerefPipeFromPin@@YAHPEAUIPin@@@Z; DerefPipeFromPin(IPin *)
0x18000bb41  mov     rax, r15
0x18000bb44  test    r15, r15
0x18000bb47  jnz     loc_18000B93C
0x18000bb4d  mov     edx, dword ptr [rbp+57h+var_90]
0x18000bb50  lea     r14, [rdi+120h]
0x18000bb57  mov     r15d, [rbp+57h+arg_8]
0x18000bb5b  cmp     esi, edx
0x18000bb5d  jb      short loc_18000BB69
0x18000bb5f  mov     eax, edx
0x18000bb61  or      eax, esi
0x18000bb63  jnz     loc_18000BC6D
0x18000bb69  test    r12, r12
0x18000bb6c  jnz     loc_18000BC6D
0x18000bb72  lea     r8, [rbp+57h+BytesReturned]; enum KSPIN_DATAFLOW *
0x18000bb76  mov     dword ptr [rbp+57h+BytesReturned], r12d
0x18000bb7a  mov     edx, r13d; unsigned int
0x18000bb7d  mov     [rbp+57h+var_80], r12
0x18000bb81  mov     rcx, rdi; this
0x18000bb84  call    ?GetPinFactoryDataFlow@CKsProxy@@QEAAJKPEAW4KSPIN_DATAFLOW@@@Z; CKsProxy::GetPinFactoryDataFlow(ulong,KSPIN_DATAFLOW *)
0x18000bb89  test    eax, eax
0x18000bb8b  js      loc_18000BD21
0x18000bb91  mov     r8d, dword ptr [rbp+57h+BytesReturned]; enum KSPIN_DATAFLOW
0x18000bb95  lea     r9, [rbp+57h+var_80]; unsigned __int16 **
0x18000bb99  mov     edx, r13d; unsigned int
0x18000bb9c  mov     rcx, rdi; this
0x18000bb9f  call    ?ConstructPinName@CKsProxy@@QEAAJKW4KSPIN_DATAFLOW@@PEAPEAG@Z; CKsProxy::ConstructPinName(ulong,KSPIN_DATAFLOW,ushort * *)
0x18000bba4  test    eax, eax
0x18000bba6  js      loc_18000BD21
0x18000bbac  mov     ecx, dword ptr [rbp+57h+BytesReturned]
0x18000bbaf  mov     rsi, [rbp+57h+var_80]
0x18000bbb3  mov     dword ptr [rbp+57h+arg_18], r12d
  ... truncated ...
```
