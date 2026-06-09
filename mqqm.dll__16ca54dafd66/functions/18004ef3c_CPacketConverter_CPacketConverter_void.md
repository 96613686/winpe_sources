# CPacketConverter::CPacketConverter(void)

- ea: `0x18004ef3c`
- end: `0x18004f033`
- name: `??0CPacketConverter@@QEAA@XZ`
- size: `247`
- prototype: `CPacketConverter *__fastcall(CPacketConverter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004fa04`

## callees

- `0x180004d91`
- `0x18000d7e0`
- `0x18000f35c`
- `0x18002c6c8`
- `0x18004ef3c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18004efff`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18004efff`
- `KERNEL32!GetLastError` at `0x18004efa9`
- `KERNEL32!GetLastError` at `0x18004efce`
- `KERNEL32!GetLastError` at `0x18004efa9`
- `KERNEL32!GetLastError` at `0x18004efce`
- `KERNEL32!CreateEventW` at `0x18004ef7d`
- `KERNEL32!CreateEventW` at `0x18004ef7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CPacketConverter *__fastcall CPacketConverter::CPacketConverter(CPacketConverter *this)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  DWORD v4; // eax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CPacketConverter::`vftable';
  CCriticalSection::CCriticalSection((CPacketConverter *)((char *)this + 32));
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 4) = 0;
  EventW = CreateEventW(0, 0, 1, 0);
  *((_QWORD *)this + 3) = EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_19f8b94ca7133f49ecc35037585359e2_Traceguids, LastError);
    }
    v4 = GetLastError();
    if ( v4 )
      LogMsgNTStatus(v4, (wchar_t *)L"recovery", 0x5DDu);
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  g_pPacketConverter = this;
  return this;
}

```

## disassembly

```asm
0x18004ef3c  mov     [rsp+arg_0], rcx
0x18004ef41  push    rbx
0x18004ef42  sub     rsp, 40h
0x18004ef46  mov     rbx, rcx
0x18004ef49  mov     dword ptr [rcx+8], 1
0x18004ef50  lea     rax, ??_7CPacketConverter@@6B@; const CPacketConverter::`vftable'
0x18004ef57  mov     [rcx], rax
0x18004ef5a  add     rcx, 20h ; ' '; this
0x18004ef5e  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x18004ef63  nop
0x18004ef64  mov     dword ptr [rbx+48h], 0
0x18004ef6b  mov     dword ptr [rbx+10h], 0
0x18004ef72  xor     r9d, r9d; lpName
0x18004ef75  xor     edx, edx; bManualReset
0x18004ef77  xor     ecx, ecx; lpEventAttributes
0x18004ef79  lea     r8d, [r9+1]; bInitialState
0x18004ef7d  call    cs:__imp_CreateEventW
0x18004ef83  mov     [rbx+18h], rax
0x18004ef87  test    rax, rax
0x18004ef8a  jnz     loc_18004F023
0x18004ef90  lea     rcx, WPP_GLOBAL_Control
0x18004ef97  mov     rax, cs:WPP_GLOBAL_Control
0x18004ef9e  cmp     rax, rcx
0x18004efa1  jz      short loc_18004EFCE
0x18004efa3  test    byte ptr [rax+1Ch], 1
0x18004efa7  jz      short loc_18004EFCE
0x18004efa9  call    cs:__imp_GetLastError
0x18004efaf  mov     edx, 0Ch
0x18004efb4  mov     r9d, eax
0x18004efb7  lea     r8, WPP_19f8b94ca7133f49ecc35037585359e2_Traceguids
0x18004efbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efc5  mov     rcx, [rcx+10h]
0x18004efc9  call    WPP_SF_d
0x18004efce  call    cs:__imp_GetLastError
0x18004efd4  test    eax, eax
0x18004efd6  jz      short loc_18004EFED
0x18004efd8  mov     r8d, 5DDh; unsigned __int16
0x18004efde  lea     rdx, aRecovery; "recovery"
0x18004efe5  mov     ecx, eax; int
0x18004efe7  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x18004efec  nop
0x18004efed  mov     r8d, 1
0x18004eff3  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x18004effa  lea     rcx, [rsp+48h+pExceptionObject]
0x18004efff  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18004f005  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18004f00c  mov     [rsp+48h+pExceptionObject], rax
0x18004f011  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18004f018  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18004f01d  call    _CxxThrowException_0
0x18004f023  mov     cs:?g_pPacketConverter@@3PEAVCPacketConverter@@EA, rbx; CPacketConverter * g_pPacketConverter
0x18004f02a  mov     rax, rbx
0x18004f02d  add     rsp, 40h
0x18004f031  pop     rbx
0x18004f032  retn
```
