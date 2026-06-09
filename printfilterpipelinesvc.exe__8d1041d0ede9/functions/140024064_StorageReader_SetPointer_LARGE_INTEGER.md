# StorageReader::SetPointer(_LARGE_INTEGER)

- ea: `0x140024064`
- end: `0x1400241a4`
- name: `?SetPointer@StorageReader@@QEAAXT_LARGE_INTEGER@@@Z`
- size: `320`
- prototype: `void(StorageReader *__hidden this, union _LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140022dd0`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140011728`
- `0x140022250`
- `0x140024064`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140063010`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x140024144`
- `KERNEL32!SetFilePointerEx` at `0x140024144`

## string_xrefs

- `0x140024174`: `SetFilePointerEx failed`
- `0x1400240d1`: `SetFilePointerEx failed. Tried to move beyond end of buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StorageReader::SetPointer(StorageReader *this, LARGE_INTEGER a2)
{
  const struct SplException::TSystemException *v4; // r8
  const struct _GUID *v5; // r9
  void *v6; // rax
  NCoreLibrary *v7; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // eax
  const struct SplException::TSystemException *v9; // r8
  const struct _GUID *v10; // r9
  unsigned int v11; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v12; // [rsp+28h] [rbp-D8h]
  HINSTANCE v13; // [rsp+30h] [rbp-D0h]
  _BYTE v14[160]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF

  StorageReader::GetDataFromParent(this);
  if ( *((_QWORD *)this + 2) )
  {
    if ( a2.QuadPart >= *((unsigned int *)this + 6) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v14, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v14,
        0x80070057,
        v4,
        v5,
        v11,
        v12,
        v13);
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v14,
        "SetFilePointerEx failed. Tried to move beyond end of buffer");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v14);
      throw (SplException::THResultException *)pExceptionObject;
    }
    *((LARGE_INTEGER *)this + 4) = a2;
  }
  else
  {
    v6 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this);
    if ( !SetFilePointerEx(v6, a2, 0, 0) )
    {
      SplException::THResultException::THResultException((SplException::THResultException *)v14, "-", 0);
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v7);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v14,
        LastErrorAsFailHRNoBreak,
        v9,
        v10,
        v11,
        v12,
        v13);
      SplException::TSystemException::Message((SplException::TSystemException *)v14, "SetFilePointerEx failed");
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v14);
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x140024064  mov     [rsp-8+arg_10], rbx
0x140024069  mov     [rsp-8+arg_18], rdi
0x14002406e  push    rbp
0x14002406f  lea     rbp, [rsp-90h]
0x140024077  sub     rsp, 190h
0x14002407e  mov     rax, cs:__security_cookie
0x140024085  xor     rax, rsp
0x140024088  mov     [rbp+90h+var_10], rax
0x14002408f  mov     rbx, rdx
0x140024092  mov     rdi, rcx
0x140024095  call    ?GetDataFromParent@StorageReader@@AEAAXXZ; StorageReader::GetDataFromParent(void)
0x14002409a  cmp     qword ptr [rdi+10h], 0
0x14002409f  jz      loc_140024129
0x1400240a5  mov     eax, [rdi+18h]
0x1400240a8  cmp     rbx, rax
0x1400240ab  jl      short loc_140024101
0x1400240ad  xor     r8d, r8d; unsigned int
0x1400240b0  lea     rdx, asc_1400696D8; "-"
0x1400240b7  lea     rcx, [rsp+190h+var_150]; this
0x1400240bc  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x1400240c1  nop
0x1400240c2  mov     edx, 80070057h; unsigned int
0x1400240c7  lea     rcx, [rsp+190h+var_150]; this
0x1400240cc  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x1400240d1  lea     rdx, aSetfilepointer; "SetFilePointerEx failed. Tried to move "...
0x1400240d8  lea     rcx, [rsp+190h+var_150]; this
0x1400240dd  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x1400240e2  lea     rdx, [rsp+190h+var_150]; struct SplException::THResultException *
0x1400240e7  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1400240eb  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x1400240f0  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1400240f7  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1400240fb  call    _CxxThrowException_0
0x140024101  mov     [rdi+20h], rbx
0x140024105  mov     rcx, [rbp+90h+var_10]
0x14002410c  xor     rcx, rsp; StackCookie
0x14002410f  call    __security_check_cookie
0x140024114  lea     r11, [rsp+190h+var_s0]
0x14002411c  mov     rbx, [r11+20h]
0x140024120  mov     rdi, [r11+28h]
0x140024124  mov     rsp, r11
0x140024127  pop     rbp
0x140024128  retn
0x140024129  mov     rcx, [rdi]
0x14002412c  mov     rax, [rcx]
0x14002412f  mov     rax, [rax+18h]
0x140024133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024138  mov     rcx, rax; hFile
0x14002413b  xor     r9d, r9d; dwMoveMethod
0x14002413e  xor     r8d, r8d; lpNewFilePointer
0x140024141  mov     rdx, rbx; liDistanceToMove
0x140024144  call    cs:__imp_SetFilePointerEx
0x14002414a  test    eax, eax
0x14002414c  jnz     short loc_140024105
0x14002414e  xor     r8d, r8d; unsigned int
0x140024151  lea     rdx, asc_1400696D8; "-"
0x140024158  lea     rcx, [rsp+190h+var_150]; this
0x14002415d  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140024162  nop
0x140024163  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x140024168  mov     edx, eax; unsigned int
0x14002416a  lea     rcx, [rsp+190h+var_150]; this
0x14002416f  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140024174  lea     rdx, aSetfilepointer_0; "SetFilePointerEx failed"
0x14002417b  lea     rcx, [rsp+190h+var_150]; this
0x140024180  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140024185  lea     rdx, [rsp+190h+var_150]; struct SplException::THResultException *
0x14002418a  lea     rcx, [rbp+90h+pExceptionObject]; this
0x14002418e  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140024193  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14002419a  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x14002419e  call    _CxxThrowException_0
```
