# ProgressiveFileBufferReader::ProgressiveFileBufferReader(ProgressiveFileBuffer *)

- ea: `0x140021184`
- end: `0x1400212d3`
- name: `??0ProgressiveFileBufferReader@@QEAA@PEAVProgressiveFileBuffer@@@Z`
- size: `335`
- prototype: `ProgressiveFileBufferReader *__fastcall(ProgressiveFileBufferReader *__hidden this, struct ProgressiveFileBuffer *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140021e4c`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005470`
- `0x140011728`
- `0x14001b1f8`
- `0x140021184`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14002123a`
- `KERNEL32!CreateEventW` at `0x14002123a`

## string_xrefs

- `0x14002129b`: `CreateEvent failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ProgressiveFileBufferReader *__fastcall ProgressiveFileBufferReader::ProgressiveFileBufferReader(
        ProgressiveFileBufferReader *this,
        struct ProgressiveFileBuffer *a2)
{
  _QWORD *v3; // rbx
  HANDLE EventW; // rax
  NCoreLibrary *v6; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v8; // r8
  const struct _GUID *v9; // r9
  unsigned int v10; // [rsp+20h] [rbp-188h]
  const struct win_musl::TStringEllipseBase *v11; // [rsp+28h] [rbp-180h]
  HINSTANCE v12; // [rsp+30h] [rbp-178h]
  _BYTE v13[160]; // [rsp+50h] [rbp-158h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-B8h] BYREF

  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  *((_DWORD *)this + 2) = 1852534389;
  *((_DWORD *)this + 3) = 1;
  _InterlockedIncrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
  *(_QWORD *)this = &ProgressiveFileBufferReader::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &ProgressiveFileBufferReader::`vftable'{for `IPrintReadStreamX'};
  v3 = (_QWORD *)((char *)this + 24);
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = a2;
  PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(a2);
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_BYTE *)this + 96) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(v3, EventW);
  if ( *v3 == -1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v13, "-", 0);
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v6);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v13,
      LastErrorAsFailHRNoBreak,
      v8,
      v9,
      v10,
      v11,
      v12);
    SplException::TSystemException::Message((SplException::TSystemException *)v13, "CreateEvent failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v13);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x140021184  mov     [rsp+arg_8], rbx
0x140021189  push    rdi
0x14002118a  sub     rsp, 1A0h
0x140021191  mov     rax, cs:__security_cookie
0x140021198  xor     rax, rsp
0x14002119b  mov     [rsp+1A8h+var_18], rax
0x1400211a3  mov     rdi, rcx
0x1400211a6  mov     [rsp+1A8h+var_168], rcx
0x1400211ab  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x1400211b2  mov     [rcx], rax
0x1400211b5  mov     dword ptr [rcx+8], 6E6B6E75h
0x1400211bc  mov     dword ptr [rcx+0Ch], 1
0x1400211c3  lock inc cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x1400211ca  lea     rax, ??_7ProgressiveFileBufferReader@@6BTUnknown@NCOMLibrary@@@; const ProgressiveFileBufferReader::`vftable'{for `NCOMLibrary::TUnknown'}
0x1400211d1  mov     [rcx], rax
0x1400211d4  lea     rax, ??_7ProgressiveFileBufferReader@@6BIPrintReadStreamX@@@; const ProgressiveFileBufferReader::`vftable'{for `IPrintReadStreamX'}
0x1400211db  mov     [rcx+10h], rax
0x1400211df  lea     rbx, [rcx+18h]
0x1400211e3  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1400211ea  mov     qword ptr [rcx+20h], 0
0x1400211f2  mov     [rcx+28h], rdx
0x1400211f6  mov     qword ptr [rcx+30h], 0
0x1400211fe  mov     dword ptr [rcx+38h], 0
0x140021205  mov     qword ptr [rcx+40h], 0
0x14002120d  mov     [rcx+48h], rdx
0x140021211  mov     rcx, rdx
0x140021214  call    ??$SmartAddRef@V?$PiboResourceDictionary@VMuslConstructPartStream@@@@@PrnExcept@@YAXPEAV?$PiboResourceDictionary@VMuslConstructPartStream@@@@@Z; PrnExcept::SmartAddRef<PiboResourceDictionary<MuslConstructPartStream>>(PiboResourceDictionary<MuslConstructPartStream> *)
0x140021219  nop
0x14002121a  mov     qword ptr [rdi+50h], 0
0x140021222  mov     qword ptr [rdi+58h], 0
0x14002122a  mov     byte ptr [rdi+60h], 0
0x14002122e  xor     r9d, r9d; lpName
0x140021231  xor     r8d, r8d; bInitialState
0x140021234  lea     edx, [r9+1]; bManualReset
0x140021238  xor     ecx, ecx; lpEventAttributes
0x14002123a  call    cs:__imp_CreateEventW
0x140021240  mov     rdx, rax
0x140021243  mov     rcx, rbx
0x140021246  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x14002124b  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x14002124f  jz      short loc_140021275
0x140021251  mov     rax, rdi
0x140021254  mov     rcx, [rsp+1A8h+var_18]
0x14002125c  xor     rcx, rsp; StackCookie
0x14002125f  call    __security_check_cookie
0x140021264  mov     rbx, [rsp+1A8h+arg_8]
0x14002126c  add     rsp, 1A0h
0x140021273  pop     rdi
0x140021274  retn
0x140021275  xor     r8d, r8d; unsigned int
0x140021278  lea     rdx, asc_1400696D8; "-"
0x14002127f  lea     rcx, [rsp+1A8h+var_158]; this
0x140021284  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140021289  nop
0x14002128a  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14002128f  mov     edx, eax; unsigned int
0x140021291  lea     rcx, [rsp+1A8h+var_158]; this
0x140021296  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14002129b  lea     rdx, aCreateeventFai; "CreateEvent failed"
0x1400212a2  lea     rcx, [rsp+1A8h+var_158]; this
0x1400212a7  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400212ac  lea     rdx, [rsp+1A8h+var_158]; struct SplException::THResultException *
0x1400212b1  lea     rcx, [rsp+1A8h+pExceptionObject]; this
0x1400212b9  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400212be  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400212c5  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x1400212cd  call    _CxxThrowException_0
```
