# MuslConstructPartStream::CopyIStreamContentsToPStream(IStream *,ulong *)

- ea: `0x140042c98`
- end: `0x140042f48`
- name: `?CopyIStreamContentsToPStream@MuslConstructPartStream@@QEAAXPEAUIStream@@PEAK@Z`
- size: `688`
- prototype: `void(MuslConstructPartStream *__hidden this, struct IStream *, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140025b48`
- `0x140025d5c`
- `0x140025ee4`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000fb28`
- `0x140021020`
- `0x140042c98`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140046314`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x140042e18`
- `KERNEL32!GlobalUnlock` at `0x140042e18`
- `KERNEL32!GlobalLock` at `0x140042e00`
- `KERNEL32!GlobalLock` at `0x140042e00`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x140042de1`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x140042de1`

## string_xrefs

- `0x140042eab`: `CopyIStreamContentsToPStream(): Number of bytes written is incorrect.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall MuslConstructPartStream::CopyIStreamContentsToPStream(
        struct IImgFilePool **this,
        struct IStream *a2,
        unsigned int *a3)
{
  int v6; // eax
  int v7; // edx
  const char *v8; // r8
  unsigned int v9; // r9d
  int v10; // eax
  int v11; // edx
  const char *v12; // r8
  unsigned int v13; // r9d
  const struct SplException::TSystemException *v14; // r8
  const struct _GUID *v15; // r9
  HRESULT HGlobalFromStream; // eax
  int v17; // edx
  const char *v18; // r8
  unsigned int v19; // r9d
  HGLOBAL v20; // rdi
  const char *v21; // rdx
  unsigned int v22; // r8d
  void *v23; // r15
  ProgressiveFileBuffer *v24; // rax
  ProgressiveFileBuffer *v25; // rcx
  int v26; // ebx
  const struct SplException::TSystemException *v27; // r8
  const struct _GUID *v28; // r9
  const struct SplException::TSystemException *v29; // r8
  const struct _GUID *v30; // r9
  unsigned int v31; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v32; // [rsp+28h] [rbp-D8h]
  HINSTANCE v33; // [rsp+30h] [rbp-D0h]
  ProgressiveFileBuffer *v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  HGLOBAL phglobal[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[160]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+110h] [rbp+10h] BYREF

  if ( !a2 || !a3 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v37, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v37,
      0x80070057,
      v29,
      v30,
      v31,
      v32,
      v33);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v37,
      "Invalid IStream pointer or cbWritten buffer.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v37);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v35 = 0;
  v34 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, __int64 *))(*(_QWORD *)a2 + 40LL))(a2, 0, 1, &v35);
  if ( v6 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v6, v7, v8, v9);
  v10 = (*(__int64 (__fastcall **)(struct IStream *, ProgressiveFileBuffer *, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(
          a2,
          v34,
          0,
          0);
  if ( v10 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v10, v11, v12, v13);
  if ( HIDWORD(v35) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v37, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v37,
      0x80004005,
      v14,
      v15,
      v31,
      v32,
      v33);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v37,
      "liCurr.HighPart is not equal to zero.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v37);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( (_DWORD)v35 )
  {
    phglobal[0] = 0;
    HGlobalFromStream = GetHGlobalFromStream(a2, phglobal);
    if ( HGlobalFromStream < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)HGlobalFromStream, v17, v18, v19);
    v20 = phglobal[0];
    phglobal[1] = phglobal[0];
    v23 = GlobalLock(phglobal[0]);
    phglobal[2] = v23;
    if ( v23 )
    {
      v24 = (ProgressiveFileBuffer *)operator new(0xE0u, v21, v22);
      v34 = v24;
      if ( v24 )
        v25 = ProgressiveFileBuffer::ProgressiveFileBuffer(v24, this[9], this[10]);
      else
        v25 = 0;
      v34 = this[13];
      this[13] = v25;
      PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)&v34);
      v26 = v35;
      (*(void (__fastcall **)(__int64, void *, _QWORD, unsigned int *))(*((_QWORD *)this[13] + 2) + 40LL))(
        (__int64)this[13] + 16,
        v23,
        (unsigned int)v35,
        a3);
      if ( v26 != *a3 )
      {
        SplException::THResultException::THResultException((SplException::THResultException *)v37, "-", 0);
        SplException::TSystemException::InternalInit(
          (SplException::TSystemException *)v37,
          0x80004005,
          v27,
          v28,
          v31,
          v32,
          v33);
        SplException::TSystemException::Message(
          (SplException::TSystemException *)v37,
          "CopyIStreamContentsToPStream(): Number of bytes written is incorrect.");
        SplException::THResultException::THResultException(
          (SplException::THResultException *)pExceptionObject,
          (const struct SplException::THResultException *)v37);
        throw (SplException::THResultException *)pExceptionObject;
      }
      (*(void (__fastcall **)(__int64))(*((_QWORD *)this[13] + 2) + 32LL))((__int64)this[13] + 16);
    }
    else
    {
      *a3 = 0;
    }
    GlobalUnlock(v20);
  }
  else
  {
    *a3 = 0;
  }
}

```

## disassembly

```asm
0x140042c98  mov     [rsp-8+arg_18], rbx
0x140042c9d  push    rbp
0x140042c9e  push    rsi
0x140042c9f  push    rdi
0x140042ca0  push    r14
0x140042ca2  push    r15
0x140042ca4  lea     rbp, [rsp-0C0h]
0x140042cac  sub     rsp, 1C0h
0x140042cb3  mov     rax, cs:__security_cookie
0x140042cba  xor     rax, rsp
0x140042cbd  mov     [rbp+0E0h+var_30], rax
0x140042cc4  mov     rsi, r8
0x140042cc7  mov     rbx, rdx
0x140042cca  mov     r14, rcx
0x140042ccd  test    rdx, rdx
0x140042cd0  jz      loc_140042EF4
0x140042cd6  test    r8, r8
0x140042cd9  jz      loc_140042EF4
0x140042cdf  mov     [rsp+1E0h+var_198], 0
0x140042ce8  mov     [rsp+1E0h+var_1A0], 0
0x140042cf1  mov     rax, [rdx]
0x140042cf4  lea     r9, [rsp+1E0h+var_198]
0x140042cf9  mov     r8d, 1
0x140042cff  mov     rdx, [rsp+1E0h+var_1A0]
0x140042d04  mov     rcx, rbx
0x140042d07  mov     rax, [rax+28h]
0x140042d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042d10  test    eax, eax
0x140042d12  jns     short loc_140042D1C
0x140042d14  mov     ecx, eax; this
0x140042d16  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140042d1c  mov     rax, [rbx]
0x140042d1f  xor     r9d, r9d
0x140042d22  xor     r8d, r8d
0x140042d25  mov     rdx, [rsp+1E0h+var_1A0]
0x140042d2a  mov     rcx, rbx
0x140042d2d  mov     rax, [rax+28h]
0x140042d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042d36  test    eax, eax
0x140042d38  jns     short loc_140042D42
0x140042d3a  mov     ecx, eax; this
0x140042d3c  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140042d42  cmp     dword ptr [rsp+1E0h+var_198+4], 0
0x140042d47  jz      short loc_140042D9D
0x140042d49  xor     r8d, r8d; unsigned int
0x140042d4c  lea     rdx, asc_1400696D8; "-"
0x140042d53  lea     rcx, [rsp+1E0h+var_170]; this
0x140042d58  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140042d5d  nop
0x140042d5e  mov     edx, 80004005h; unsigned int
0x140042d63  lea     rcx, [rsp+1E0h+var_170]; this
0x140042d68  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140042d6d  lea     rdx, aLicurrHighpart; "liCurr.HighPart is not equal to zero."
0x140042d74  lea     rcx, [rsp+1E0h+var_170]; this
0x140042d79  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140042d7e  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x140042d83  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140042d87  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140042d8c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140042d93  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x140042d97  call    _CxxThrowException_0
0x140042d9d  cmp     dword ptr [rsp+1E0h+var_198], 0
0x140042da2  jnz     short loc_140042DD0
0x140042da4  mov     dword ptr [rsi], 0
0x140042daa  mov     rcx, [rbp+0E0h+var_30]
0x140042db1  xor     rcx, rsp; StackCookie
0x140042db4  call    __security_check_cookie
0x140042db9  mov     rbx, [rsp+1E0h+arg_18]
0x140042dc1  add     rsp, 1C0h
0x140042dc8  pop     r15
0x140042dca  pop     r14
0x140042dcc  pop     rdi
0x140042dcd  pop     rsi
0x140042dce  pop     rbp
0x140042dcf  retn
0x140042dd0  mov     [rsp+1E0h+phglobal], 0
0x140042dd9  lea     rdx, [rsp+1E0h+phglobal]; phglobal
0x140042dde  mov     rcx, rbx; pstm
0x140042de1  call    cs:__imp_GetHGlobalFromStream
0x140042de7  test    eax, eax
0x140042de9  jns     short loc_140042DF3
0x140042deb  mov     ecx, eax; this
0x140042ded  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140042df3  mov     rdi, [rsp+1E0h+phglobal]
0x140042df8  mov     [rsp+1E0h+var_188], rdi
0x140042dfd  mov     rcx, rdi; hMem
0x140042e00  call    cs:__imp_GlobalLock
0x140042e06  mov     r15, rax
0x140042e09  mov     [rsp+1E0h+var_180], rax
0x140042e0e  test    rax, rax
0x140042e11  jnz     short loc_140042E20
0x140042e13  mov     [rsi], eax
0x140042e15  mov     rcx, rdi; hMem
0x140042e18  call    cs:__imp_GlobalUnlock
0x140042e1e  jmp     short loc_140042DAA
0x140042e20  mov     ecx, 0E0h; unsigned __int64
0x140042e25  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x140042e2a  mov     [rsp+1E0h+var_1A0], rax
0x140042e2f  test    rax, rax
0x140042e32  jz      short loc_140042E49
0x140042e34  mov     r8, [r14+50h]; struct IMemoryPool *
0x140042e38  mov     rdx, [r14+48h]; struct IImgFilePool *
0x140042e3c  mov     rcx, rax; this
0x140042e3f  call    ??0ProgressiveFileBuffer@@QEAA@PEAUIImgFilePool@@PEAUIMemoryPool@@@Z; ProgressiveFileBuffer::ProgressiveFileBuffer(IImgFilePool *,IMemoryPool *)
0x140042e44  mov     rcx, rax
0x140042e47  jmp     short loc_140042E4B
0x140042e49  xor     ecx, ecx
0x140042e4b  mov     rax, [r14+68h]
0x140042e4f  mov     [rsp+1E0h+var_1A0], rax
0x140042e54  mov     [r14+68h], rcx
0x140042e58  lea     rcx, [rsp+1E0h+var_1A0]
0x140042e5d  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x140042e62  mov     ebx, dword ptr [rsp+1E0h+var_198]
0x140042e66  mov     rcx, [r14+68h]
0x140042e6a  add     rcx, 10h
0x140042e6e  mov     rax, [rcx]
0x140042e71  mov     r9, rsi
0x140042e74  mov     r8d, ebx
0x140042e77  mov     rdx, r15
0x140042e7a  mov     rax, [rax+28h]
0x140042e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042e83  cmp     ebx, [rsi]
0x140042e85  jz      short loc_140042EDB
0x140042e87  xor     r8d, r8d; unsigned int
0x140042e8a  lea     rdx, asc_1400696D8; "-"
0x140042e91  lea     rcx, [rsp+1E0h+var_170]; this
0x140042e96  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140042e9b  nop
0x140042e9c  mov     edx, 80004005h; unsigned int
0x140042ea1  lea     rcx, [rsp+1E0h+var_170]; this
0x140042ea6  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140042eab  lea     rdx, aCopyistreamcon; "CopyIStreamContentsToPStream(): Number "...
0x140042eb2  lea     rcx, [rsp+1E0h+var_170]; this
0x140042eb7  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140042ebc  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x140042ec1  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140042ec5  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140042eca  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140042ed1  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x140042ed5  call    _CxxThrowException_0
0x140042edb  mov     rcx, [r14+68h]
0x140042edf  add     rcx, 10h
0x140042ee3  mov     rax, [rcx]
0x140042ee6  mov     rax, [rax+20h]
0x140042eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042eef  jmp     loc_140042E15
0x140042ef4  xor     r8d, r8d; unsigned int
0x140042ef7  lea     rdx, asc_1400696D8; "-"
0x140042efe  lea     rcx, [rsp+1E0h+var_170]; this
0x140042f03  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140042f08  nop
0x140042f09  mov     edx, 80070057h; unsigned int
0x140042f0e  lea     rcx, [rsp+1E0h+var_170]; this
0x140042f13  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140042f18  lea     rdx, aInvalidIstream; "Invalid IStream pointer or cbWritten bu"...
0x140042f1f  lea     rcx, [rsp+1E0h+var_170]; this
0x140042f24  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140042f29  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x140042f2e  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140042f32  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140042f37  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140042f3e  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x140042f42  call    _CxxThrowException_0
```
