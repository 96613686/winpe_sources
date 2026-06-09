# WaitingLockedQueue<IUnknown>::WaitingLockedQueue<IUnknown>(void)

- ea: `0x140029934`
- end: `0x140029b87`
- name: `??0?$WaitingLockedQueue@UIUnknown@@@@QEAA@XZ`
- size: `595`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x140020630`
- `0x14002a660`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005470`
- `0x140011728`
- `0x14001b304`
- `0x140029934`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140029a2f`
- `KERNEL32!CreateEventW` at `0x140029a53`
- `KERNEL32!CreateEventW` at `0x140029a2f`
- `KERNEL32!CreateEventW` at `0x140029a53`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14002998d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14002998d`
- `KERNEL32!CreateSemaphoreW` at `0x140029a07`
- `KERNEL32!CreateSemaphoreW` at `0x140029a07`

## string_xrefs

- `0x140029b57`: `CreateSemaphore failed`
- `0x140029ab1`: `CreateEvent failed`
- `0x140029b04`: `CreateEvent failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaitingLockedQueue<IUnknown>::WaitingLockedQueue<IUnknown>(__int64 a1)
{
  NCoreLibrary *v2; // rcx
  int LastErrorAsFailHRNoBreak; // eax
  int v4; // edx
  const char *v5; // r8
  unsigned int v6; // r9d
  _QWORD *v7; // rdi
  SplException *v8; // rcx
  HANDLE SemaphoreW; // rax
  HANDLE EventW; // rax
  HANDLE v11; // rax
  NCoreLibrary *v13; // rcx
  unsigned int v14; // eax
  const struct SplException::TSystemException *v15; // r8
  const struct _GUID *v16; // r9
  NCoreLibrary *v17; // rcx
  unsigned int v18; // eax
  const struct SplException::TSystemException *v19; // r8
  const struct _GUID *v20; // r9
  NCoreLibrary *v21; // rcx
  unsigned int v22; // eax
  const struct SplException::TSystemException *v23; // r8
  const struct _GUID *v24; // r9
  unsigned int v25; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v26; // [rsp+28h] [rbp-D8h]
  HINSTANCE v27; // [rsp+30h] [rbp-D0h]
  _BYTE v28[160]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-10h] BYREF

  *(_DWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 44) = 0;
  *(_DWORD *)(a1 + 48) = -2147467259;
  *(_DWORD *)(a1 + 44) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)a1, 0x80000000) )
    LastErrorAsFailHRNoBreak = 0;
  else
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v2);
  *(_DWORD *)(a1 + 48) = LastErrorAsFailHRNoBreak;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>();
  v7 = (_QWORD *)(a1 + 96);
  *(_QWORD *)(a1 + 96) = -1;
  *(_QWORD *)(a1 + 104) = -1;
  *(_QWORD *)(a1 + 112) = -1;
  v8 = (SplException *)*(unsigned int *)(a1 + 48);
  if ( (int)v8 < 0 )
    SplException::RealThrowFromHR(v8, v4, v5, v6);
  SemaphoreW = CreateSemaphoreW(0, 0, 10000000, 0);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(v7, SemaphoreW);
  if ( *v7 == -1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v28, "-", 0);
    v22 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v21);
    SplException::TSystemException::InternalInit((SplException::TSystemException *)v28, v22, v23, v24, v25, v26, v27);
    SplException::TSystemException::Message((SplException::TSystemException *)v28, "CreateSemaphore failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(a1 + 104, EventW);
  if ( *(_QWORD *)(a1 + 104) == -1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v28, "-", 0);
    v18 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v17);
    SplException::TSystemException::InternalInit((SplException::TSystemException *)v28, v18, v19, v20, v25, v26, v27);
    SplException::TSystemException::Message((SplException::TSystemException *)v28, "CreateEvent failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v11 = CreateEventW(0, 1, 0, 0);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(a1 + 112, v11);
  if ( *(_QWORD *)(a1 + 112) == -1 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v28, "-", 0);
    v14 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v13);
    SplException::TSystemException::InternalInit((SplException::TSystemException *)v28, v14, v15, v16, v25, v26, v27);
    SplException::TSystemException::Message((SplException::TSystemException *)v28, "CreateEvent failed");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v28);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x140029934  push    rbp
0x140029936  push    rbx
0x140029937  push    rsi
0x140029938  push    rdi
0x140029939  push    r12
0x14002993b  push    r14
0x14002993d  lea     rbp, [rsp-0A8h]
0x140029945  sub     rsp, 1A8h
0x14002994c  mov     rax, cs:__security_cookie
0x140029953  xor     rax, rsp
0x140029956  mov     [rbp+0D0h+var_40], rax
0x14002995d  mov     rbx, rcx
0x140029960  mov     [rsp+1D0h+var_190], rcx
0x140029965  mov     dword ptr [rcx+28h], 0
0x14002996c  mov     dword ptr [rcx+2Ch], 0
0x140029973  mov     dword ptr [rcx+30h], 80004005h
0x14002997a  mov     dword ptr [rcx+2Ch], 0
0x140029981  mov     dword ptr [rcx+28h], 0
0x140029988  mov     edx, 80000000h; dwSpinCount
0x14002998d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140029993  test    eax, eax
0x140029995  jz      short loc_14002999B
0x140029997  xor     eax, eax
0x140029999  jmp     short loc_1400299A0
0x14002999b  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400299a0  mov     [rbx+30h], eax
0x1400299a3  lea     rcx, [rbx+38h]
0x1400299a7  mov     qword ptr [rcx], 0
0x1400299ae  mov     qword ptr [rcx+8], 0
0x1400299b6  mov     qword ptr [rcx+10h], 0
0x1400299be  mov     qword ptr [rcx+18h], 0
0x1400299c6  mov     qword ptr [rcx+20h], 0
0x1400299ce  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x1400299d3  nop
0x1400299d4  lea     rdi, [rbx+60h]
0x1400299d8  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400299dc  mov     [rdi], r12
0x1400299df  lea     r14, [rbx+68h]
0x1400299e3  mov     [r14], r12
0x1400299e6  lea     rsi, [rbx+70h]
0x1400299ea  mov     [rsi], r12
0x1400299ed  mov     ecx, [rbx+30h]; this
0x1400299f0  test    ecx, ecx
0x1400299f2  jns     short loc_1400299FA
0x1400299f4  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400299fa  xor     r9d, r9d; lpName
0x1400299fd  xor     edx, edx; lInitialCount
0x1400299ff  xor     ecx, ecx; lpSemaphoreAttributes
0x140029a01  mov     r8d, 989680h; lMaximumCount
0x140029a07  call    cs:__imp_CreateSemaphoreW
0x140029a0d  mov     rdx, rax
0x140029a10  mov     rcx, rdi
0x140029a13  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x140029a18  xor     r8d, r8d; unsigned int
0x140029a1b  cmp     [rdi], r12
0x140029a1e  jz      loc_140029B34
0x140029a24  xor     r9d, r9d; lpName
0x140029a27  lea     edi, [r8+1]
0x140029a2b  mov     edx, edi; bManualReset
0x140029a2d  xor     ecx, ecx; lpEventAttributes
0x140029a2f  call    cs:__imp_CreateEventW
0x140029a35  mov     rdx, rax
0x140029a38  mov     rcx, r14
0x140029a3b  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x140029a40  xor     r8d, r8d; unsigned int
0x140029a43  cmp     [r14], r12
0x140029a46  jz      loc_140029AE1
0x140029a4c  xor     r9d, r9d; lpName
0x140029a4f  mov     edx, edi; bManualReset
0x140029a51  xor     ecx, ecx; lpEventAttributes
0x140029a53  call    cs:__imp_CreateEventW
0x140029a59  mov     rdx, rax
0x140029a5c  mov     rcx, rsi
0x140029a5f  call    ?Attach@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXPEAX@Z; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Attach(void *)
0x140029a64  cmp     [rsi], r12
0x140029a67  jz      short loc_140029A8B
0x140029a69  mov     rax, rbx
0x140029a6c  mov     rcx, [rbp+0D0h+var_40]
0x140029a73  xor     rcx, rsp; StackCookie
0x140029a76  call    __security_check_cookie
0x140029a7b  add     rsp, 1A8h
0x140029a82  pop     r14
0x140029a84  pop     r12
0x140029a86  pop     rdi
0x140029a87  pop     rsi
0x140029a88  pop     rbx
0x140029a89  pop     rbp
0x140029a8a  retn
0x140029a8b  xor     r8d, r8d; unsigned int
0x140029a8e  lea     rdx, asc_1400696D8; "-"
0x140029a95  lea     rcx, [rsp+1D0h+var_180]; this
0x140029a9a  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140029a9f  nop
0x140029aa0  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140029aa5  mov     edx, eax; unsigned int
0x140029aa7  lea     rcx, [rsp+1D0h+var_180]; this
0x140029aac  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140029ab1  lea     rdx, aCreateeventFai; "CreateEvent failed"
0x140029ab8  lea     rcx, [rsp+1D0h+var_180]; this
0x140029abd  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140029ac2  lea     rdx, [rsp+1D0h+var_180]; struct SplException::THResultException *
0x140029ac7  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x140029acb  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140029ad0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140029ad7  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x140029adb  call    _CxxThrowException_0
0x140029ae1  lea     rdx, asc_1400696D8; "-"
0x140029ae8  lea     rcx, [rsp+1D0h+var_180]; this
0x140029aed  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140029af2  nop
0x140029af3  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140029af8  mov     edx, eax; unsigned int
0x140029afa  lea     rcx, [rsp+1D0h+var_180]; this
0x140029aff  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140029b04  lea     rdx, aCreateeventFai; "CreateEvent failed"
0x140029b0b  lea     rcx, [rsp+1D0h+var_180]; this
0x140029b10  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140029b15  lea     rdx, [rsp+1D0h+var_180]; struct SplException::THResultException *
0x140029b1a  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x140029b1e  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140029b23  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140029b2a  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x140029b2e  call    _CxxThrowException_0
0x140029b34  lea     rdx, asc_1400696D8; "-"
0x140029b3b  lea     rcx, [rsp+1D0h+var_180]; this
0x140029b40  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140029b45  nop
0x140029b46  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140029b4b  mov     edx, eax; unsigned int
0x140029b4d  lea     rcx, [rsp+1D0h+var_180]; this
0x140029b52  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140029b57  lea     rdx, aCreatesemaphor; "CreateSemaphore failed"
0x140029b5e  lea     rcx, [rsp+1D0h+var_180]; this
0x140029b63  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140029b68  lea     rdx, [rsp+1D0h+var_180]; struct SplException::THResultException *
0x140029b6d  lea     rcx, [rbp+0D0h+pExceptionObject]; this
0x140029b71  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140029b76  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140029b7d  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x140029b81  call    _CxxThrowException_0
```
