# ProgressiveFileBuffer::InternalWriteBytesX(void const *,ulong,ulong *)

- ea: `0x140022514`
- end: `0x1400226e6`
- name: `?InternalWriteBytesX@ProgressiveFileBuffer@@QEAAXPEBXKPEAK@Z`
- size: `466`
- prototype: `void(ProgressiveFileBuffer *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x140021a8c`
- `0x140021f68`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140011728`
- `0x1400172e8`
- `0x14001a750`
- `0x140022514`
- `0x1400227e8`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x14004650c`
- `0x140063010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140022684`
- `KERNEL32!LeaveCriticalSection` at `0x140022684`
- `KERNEL32!WriteFile` at `0x14002259a`
- `KERNEL32!WriteFile` at `0x14002259a`

## string_xrefs

- `0x1400225ca`: `WriteBytesX failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ProgressiveFileBuffer::InternalWriteBytesX(
        ProgressiveFileBuffer *this,
        const void *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v5; // r14
  _QWORD *v8; // rbx
  int v9; // eax
  int v10; // edx
  const char *v11; // r8
  unsigned int v12; // r9d
  void *v13; // rax
  NCoreLibrary *v14; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v16; // r8
  const struct _GUID *v17; // r9
  unsigned __int64 v18; // rbp
  __int64 *v19; // rsi
  __int64 v20; // rcx
  unsigned int lpOverlapped; // [rsp+20h] [rbp-198h]
  const struct win_musl::TStringEllipseBase *v23; // [rsp+28h] [rbp-190h]
  HINSTANCE v24; // [rsp+30h] [rbp-188h]
  _BYTE v25[160]; // [rsp+40h] [rbp-178h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-D8h] BYREF

  v5 = a3;
  if ( a3 )
  {
    v8 = (_QWORD *)((char *)this + 96);
    if ( !*((_QWORD *)this + 12) )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11), v8);
      if ( v9 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v9, v10, v11, v12);
    }
    v13 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 24LL))(*v8);
    if ( !WriteFile(v13, a2, v5, a4, 0) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v25, "-", 0);
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v14);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v25,
        LastErrorAsFailHRNoBreak,
        v16,
        v17,
        lpOverlapped,
        v23,
        v24);
      SplException::TSystemException::Message((SplException::TSystemException *)v25, "WriteBytesX failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v25);
      throw (SplException::THResultException *)pExceptionObject;
    }
    NCoreLibrary::TCriticalSection::Enter((ProgressiveFileBuffer *)((char *)this + 32));
    *((_QWORD *)this + 13) += v5;
    v18 = *((_QWORD *)this + 18);
    if ( this == (ProgressiveFileBuffer *)-120LL )
      v19 = 0;
    else
      v19 = (__int64 *)*((_QWORD *)this + 15);
    while ( v18 != *((_QWORD *)this + 18) + *((_QWORD *)this + 19) )
    {
      if ( v19 )
        v20 = *v19;
      else
        v20 = 0;
      ProgressiveFileBufferReader::ProcessWriteCall(
        *(ProgressiveFileBufferReader **)(*(_QWORD *)(*(_QWORD *)(v20 + 8)
                                                    + 8 * ((*(_QWORD *)(v20 + 16) - 1LL) & (v18 >> 1)))
                                        + 8 * (v18 & 1)),
        0);
      ++v18;
    }
    if ( (*((_DWORD *)this + 19))-- == 1 )
      *((_DWORD *)this + 18) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_091d6adf7f6b398302582c7b7c9260ff_Traceguids,
        (unsigned int)v5,
        *((_DWORD *)this + 26));
    }
  }
  else
  {
    *a4 = 0;
  }
}

```

## disassembly

```asm
0x140022514  push    rbx
0x140022516  push    rbp
0x140022517  push    rsi
0x140022518  push    rdi
0x140022519  push    r14
0x14002251b  sub     rsp, 190h
0x140022522  mov     rax, cs:__security_cookie
0x140022529  xor     rax, rsp
0x14002252c  mov     [rsp+1B8h+var_38], rax
0x140022534  mov     rsi, r9
0x140022537  mov     r14d, r8d
0x14002253a  mov     rbp, rdx
0x14002253d  mov     rdi, rcx
0x140022540  test    r8d, r8d
0x140022543  jnz     short loc_14002254D
0x140022545  mov     [r9], r8d
0x140022548  jmp     loc_1400226C8
0x14002254d  lea     rbx, [rcx+60h]
0x140022551  cmp     qword ptr [rbx], 0
0x140022555  jnz     short loc_140022576
0x140022557  mov     rcx, [rcx+58h]
0x14002255b  mov     rax, [rcx]
0x14002255e  mov     rdx, rbx
0x140022561  mov     rax, [rax+20h]
0x140022565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002256a  test    eax, eax
0x14002256c  jns     short loc_140022576
0x14002256e  mov     ecx, eax; this
0x140022570  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140022576  mov     rcx, [rbx]
0x140022579  mov     rax, [rcx]
0x14002257c  mov     rax, [rax+18h]
0x140022580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022585  mov     rcx, rax; hFile
0x140022588  mov     [rsp+1B8h+lpOverlapped], 0; unsigned int
0x140022591  mov     r9, rsi; lpNumberOfBytesWritten
0x140022594  mov     r8d, r14d; nNumberOfBytesToWrite
0x140022597  mov     rdx, rbp; lpBuffer
0x14002259a  call    cs:__imp_WriteFile
0x1400225a0  test    eax, eax
0x1400225a2  jnz     short loc_140022602
0x1400225a4  xor     r8d, r8d; unsigned int
0x1400225a7  lea     rdx, asc_1400696D8; "-"
0x1400225ae  lea     rcx, [rsp+1B8h+var_178]; this
0x1400225b3  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400225b8  nop
0x1400225b9  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1400225be  mov     edx, eax; unsigned int
0x1400225c0  lea     rcx, [rsp+1B8h+var_178]; this
0x1400225c5  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400225ca  lea     rdx, aWritebytesxFai; "WriteBytesX failed"
0x1400225d1  lea     rcx, [rsp+1B8h+var_178]; this
0x1400225d6  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400225db  lea     rdx, [rsp+1B8h+var_178]; struct SplException::THResultException *
0x1400225e0  lea     rcx, [rsp+1B8h+pExceptionObject]; this
0x1400225e8  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400225ed  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400225f4  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x1400225fc  call    _CxxThrowException_0
0x140022602  lea     rcx, [rdi+20h]; this
0x140022606  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14002260b  add     [rdi+68h], r14
0x14002260f  lea     rax, [rdi+78h]
0x140022613  mov     rbp, [rax+18h]
0x140022617  test    rax, rax
0x14002261a  jz      short loc_140022621
0x14002261c  mov     rsi, [rax]
0x14002261f  jmp     short loc_140022623
0x140022621  xor     esi, esi
0x140022623  mov     rax, [rdi+98h]
0x14002262a  add     rax, [rdi+90h]
0x140022631  cmp     rbp, rax
0x140022634  jz      short loc_140022670
0x140022636  test    rsi, rsi
0x140022639  jz      short loc_140022640
0x14002263b  mov     rcx, [rsi]
0x14002263e  jmp     short loc_140022642
0x140022640  xor     ecx, ecx
0x140022642  mov     rdx, rbp
0x140022645  shr     rdx, 1
0x140022648  mov     rax, [rcx+10h]
0x14002264c  dec     rax
0x14002264f  and     rdx, rax
0x140022652  mov     rcx, [rcx+8]
0x140022656  mov     rax, rbp
0x140022659  and     eax, 1
0x14002265c  mov     rcx, [rcx+rdx*8]
0x140022660  xor     edx, edx; bool
0x140022662  mov     rcx, [rcx+rax*8]; this
0x140022666  call    ?ProcessWriteCall@ProgressiveFileBufferReader@@QEAAX_N@Z; ProgressiveFileBufferReader::ProcessWriteCall(bool)
0x14002266b  inc     rbp
0x14002266e  jmp     short loc_140022623
0x140022670  add     dword ptr [rdi+4Ch], 0FFFFFFFFh
0x140022674  mov     eax, [rdi+4Ch]
0x140022677  jnz     short loc_140022680
0x140022679  mov     dword ptr [rdi+48h], 0
0x140022680  lea     rcx, [rdi+20h]; lpCriticalSection
0x140022684  call    cs:__imp_LeaveCriticalSection
0x14002268a  lea     rax, WPP_GLOBAL_Control
0x140022691  mov     rcx, cs:WPP_GLOBAL_Control
0x140022698  cmp     rcx, rax
0x14002269b  jz      short loc_1400226C8
0x14002269d  test    byte ptr [rcx+1Ch], 8
0x1400226a1  jz      short loc_1400226C8
0x1400226a3  cmp     byte ptr [rcx+19h], 3
0x1400226a7  jb      short loc_1400226C8
0x1400226a9  mov     edx, 17h
0x1400226ae  mov     eax, [rdi+68h]
0x1400226b1  mov     dword ptr [rsp+1B8h+lpOverlapped], eax
0x1400226b5  mov     r9d, r14d
0x1400226b8  lea     r8, WPP_091d6adf7f6b398302582c7b7c9260ff_Traceguids
0x1400226bf  mov     rcx, [rcx+10h]
0x1400226c3  call    WPP_SF_dd
0x1400226c8  mov     rcx, [rsp+1B8h+var_38]
0x1400226d0  xor     rcx, rsp; StackCookie
0x1400226d3  call    __security_check_cookie
0x1400226d8  add     rsp, 190h
0x1400226df  pop     r14
0x1400226e1  pop     rdi
0x1400226e2  pop     rsi
0x1400226e3  pop     rbp
0x1400226e4  pop     rbx
0x1400226e5  retn
```
