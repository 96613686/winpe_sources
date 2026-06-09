# DWMIndirect::DWMIndirect(void)

- ea: `0x180003db8`
- end: `0x180003fa3`
- name: `??0DWMIndirect@@IEAA@XZ`
- size: `491`
- prototype: `DWMIndirect *__fastcall(DWMIndirect *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004670`

## callees

- `0x180001ca4`
- `0x180003db8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003ef6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180003ef6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003eb1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003eb1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180003ed1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180003ed1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003f3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003f3e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180003f4a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180003f4a`

## pseudocode

```c
DWMIndirect *__fastcall DWMIndirect::DWMIndirect(DWMIndirect *this)
{
  _DWORD *v1; // r9
  unsigned __int32 v3; // eax
  int v4; // edx
  DWORD CurrentProcessId; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v10; // [rsp+40h] [rbp-18h] BYREF
  DWORD pSessionId; // [rsp+80h] [rbp+28h] BYREF
  DWORD v12; // [rsp+88h] [rbp+30h] BYREF
  LARGE_INTEGER Frequency; // [rsp+90h] [rbp+38h] BYREF
  DWMIndirect *v14; // [rsp+98h] [rbp+40h] BYREF

  *((_DWORD *)this + 6) = -607474739;
  *((_QWORD *)this + 2) = "DWMIndirect";
  v1 = (_DWORD *)((char *)this + 56);
  *((_DWORD *)this + 7) = 1;
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 4) = this;
  *((_QWORD *)this + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
  *((_DWORD *)this + 10) = 0;
  v3 = _InterlockedIncrement(&dword_180044910);
  *((_DWORD *)this + 14) = -1;
  if ( v3 <= 0x20 )
  {
    v4 = 0;
    while ( _InterlockedCompareExchange64(
              &TSRegisteredObject<DWMIndirect,32>::s_RegisteredObjects[v4],
              (unsigned __int64)this & -(__int64)(v1 != 0),
              0) )
    {
      if ( (unsigned int)++v4 >= 0x20 )
        goto LABEL_7;
    }
    *v1 = v4;
  }
LABEL_7:
  pSessionId = 0;
  *(_QWORD *)this = &DWMIndirect::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 114) = 0;
  *((_QWORD *)this + 1) = &DWMIndirect::`vftable'{for `CTSObject'};
  Frequency.QuadPart = 0;
  *((_QWORD *)this + 6) = &DWMIndirect::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 22) = 0;
  QueryPerformanceCounter((LARGE_INTEGER *)this + 24);
  *((_QWORD *)this + 26) = *((_QWORD *)this + 24);
  *((_DWORD *)this + 46) = 0;
  *((_DWORD *)this + 50) = 0;
  QueryPerformanceFrequency(&Frequency);
  *((LARGE_INTEGER *)this + 27) = Frequency;
  *((_DWORD *)this + 56) = 0;
  *((_BYTE *)this + 228) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 74) = 0;
  *((_DWORD *)this + 205) = 0;
  *(_QWORD *)((char *)this + 900) = 0;
  *((_DWORD *)this + 227) = 0;
  *((_DWORD *)this + 208) = 31;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v12 = pSessionId;
    v10 = "Allocating DWMIndirect instance %p for session %d.";
    v14 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)byte_180037949,
      v7,
      v8,
      (const unsigned __int16 **)&v10,
      (__int64)&v14,
      (__int64)&v12);
  }
  return this;
}

```

## disassembly

```asm
0x180003db8  push    rbp
0x180003dba  push    rbx
0x180003dbb  push    rsi
0x180003dbc  push    rdi
0x180003dbd  mov     rbp, rsp
0x180003dc0  sub     rsp, 58h
0x180003dc4  mov     dword ptr [rcx+18h], 0DBCAABCDh
0x180003dcb  lea     rax, aDwmindirect; "DWMIndirect"
0x180003dd2  mov     [rcx+10h], rax
0x180003dd6  lea     r9, [rcx+38h]
0x180003dda  mov     r11d, 1
0x180003de0  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x180003de7  mov     [rcx+1Ch], r11d
0x180003deb  xor     esi, esi
0x180003ded  mov     [rcx], rax
0x180003df0  mov     rdi, rcx
0x180003df3  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180003dfa  mov     [rcx+20h], rcx
0x180003dfe  mov     [rcx+8], rax
0x180003e02  mov     eax, r11d
0x180003e05  mov     [rcx+28h], esi
0x180003e08  lock xadd cs:dword_180044910, eax
0x180003e10  add     eax, r11d
0x180003e13  mov     dword ptr [r9], 0FFFFFFFFh
0x180003e1a  cmp     eax, 20h ; ' '
0x180003e1d  ja      short loc_180003E4D
0x180003e1f  mov     rax, r9
0x180003e22  mov     edx, esi
0x180003e24  neg     rax
0x180003e27  sbb     r8, r8
0x180003e2a  and     r8, rcx
0x180003e2d  mov     ecx, edx
0x180003e2f  lea     r10, ?s_RegisteredObjects@?$TSRegisteredObject@VDWMIndirect@@$0CA@@@2U_REGISTERED_OBJ_ARRAY@1@A; TSRegisteredObject<DWMIndirect,32>::_REGISTERED_OBJ_ARRAY TSRegisteredObject<DWMIndirect,32>::s_RegisteredObjects
0x180003e36  xor     eax, eax
0x180003e38  lock cmpxchg [r10+rcx*8], r8
0x180003e3e  jz      short loc_180003E4A
0x180003e40  add     edx, r11d
0x180003e43  cmp     edx, 20h ; ' '
0x180003e46  jb      short loc_180003E2D
0x180003e48  jmp     short loc_180003E4D
0x180003e4a  mov     [r9], edx
0x180003e4d  lea     rax, ??_7DWMIndirect@@6BINonDelegatingUnknown@@@; const DWMIndirect::`vftable'{for `INonDelegatingUnknown'}
0x180003e54  mov     [rbp+pSessionId], esi
0x180003e57  mov     [rdi], rax
0x180003e5a  lea     rbx, [rdi+0C0h]
0x180003e61  lea     rax, ??_7DWMIndirect@@6BCTSObject@@@; const DWMIndirect::`vftable'{for `CTSObject'}
0x180003e68  mov     [rdi+390h], rsi
0x180003e6f  mov     [rdi+8], rax
0x180003e73  mov     rcx, rbx; lpPerformanceCount
0x180003e76  lea     rax, ??_7DWMIndirect@@6B@; const DWMIndirect::`vftable'
0x180003e7d  mov     qword ptr [rbp+Frequency], rsi
0x180003e81  mov     [rdi+30h], rax
0x180003e85  mov     [rdi+40h], rsi
0x180003e89  mov     [rdi+48h], rsi
0x180003e8d  mov     [rdi+50h], rsi
0x180003e91  mov     [rdi+58h], rsi
0x180003e95  mov     [rdi+80h], esi
0x180003e9b  mov     [rdi+68h], rsi
0x180003e9f  mov     [rdi+338h], rsi
0x180003ea6  mov     [rdi+60h], rsi
0x180003eaa  mov     [rdi+0B0h], rsi
0x180003eb1  call    cs:__imp_QueryPerformanceCounter
0x180003eb7  mov     rax, [rbx]
0x180003eba  lea     rcx, [rbp+Frequency]; lpFrequency
0x180003ebe  mov     [rdi+0D0h], rax
0x180003ec5  mov     [rdi+0B8h], esi
0x180003ecb  mov     [rdi+0C8h], esi
0x180003ed1  call    cs:__imp_QueryPerformanceFrequency
0x180003ed7  mov     rax, qword ptr [rbp+Frequency]
0x180003edb  lea     rcx, [rdi+88h]; lpCriticalSection
0x180003ee2  mov     [rdi+0D8h], rax
0x180003ee9  mov     [rdi+0E0h], esi
0x180003eef  mov     [rdi+0E4h], sil
0x180003ef6  call    cs:__imp_InitializeCriticalSection
0x180003efc  mov     [rdi+0E8h], rsi
0x180003f03  xor     eax, eax
0x180003f05  mov     [rdi+0F0h], rsi
0x180003f0c  mov     [rdi+0F8h], rsi
0x180003f13  mov     [rdi+78h], rsi
0x180003f17  mov     [rdi+70h], rsi
0x180003f1b  mov     [rdi+128h], esi
0x180003f21  mov     [rdi+334h], esi
0x180003f27  mov     [rdi+384h], rax
0x180003f2e  mov     [rdi+38Ch], esi
0x180003f34  mov     dword ptr [rdi+340h], 1Fh
0x180003f3e  call    cs:__imp_GetCurrentProcessId
0x180003f44  mov     ecx, eax; dwProcessId
0x180003f46  lea     rdx, [rbp+pSessionId]; pSessionId
0x180003f4a  call    cs:__imp_ProcessIdToSessionId
0x180003f50  mov     eax, cs:dword_180044008
0x180003f56  cmp     eax, 4
0x180003f59  jbe     short loc_180003F97
0x180003f5b  mov     eax, [rbp+pSessionId]
0x180003f5e  lea     rdx, byte_180037949
0x180003f65  mov     [rbp+arg_8], eax
0x180003f68  lea     rax, aAllocatingDwmi; "Allocating DWMIndirect instance %p for "...
0x180003f6f  mov     [rbp+var_18], rax
0x180003f73  lea     rax, [rbp+arg_8]
0x180003f77  mov     [rsp+58h+var_28], rax
0x180003f7c  lea     rax, [rbp+arg_18]
0x180003f80  mov     [rsp+58h+var_30], rax
0x180003f85  lea     rax, [rbp+var_18]
0x180003f89  mov     [rsp+58h+var_38], rax
0x180003f8e  mov     [rbp+arg_18], rdi
0x180003f92  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180003f97  mov     rax, rdi
0x180003f9a  add     rsp, 58h
0x180003f9e  pop     rdi
0x180003f9f  pop     rsi
0x180003fa0  pop     rbx
0x180003fa1  pop     rbp
0x180003fa2  retn
```
