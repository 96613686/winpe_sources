# TImgPipelineManager::CreateEventW(void)

- ea: `0x14001cebc`
- end: `0x14001cf67`
- name: `?CreateEventW@TImgPipelineManager@@AEAAPEAXXZ`
- size: `171`
- prototype: `void *__fastcall(TImgPipelineManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14001d970`
- `0x14001e238`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x14001cebc`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14001cee1`
- `KERNEL32!CreateEventW` at `0x14001cee1`

## string_xrefs

- `0x14001cf17`: `TImgPipelineManager::CreateEvent() : CreateEvent failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall TImgPipelineManager::CreateEventW(TImgPipelineManager *this)
{
  char *result; // rax
  NCoreLibrary *v2; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v4; // r8
  const struct _GUID *v5; // r9
  unsigned int v6; // [rsp+20h] [rbp-178h]
  const struct win_musl::TStringEllipseBase *v7; // [rsp+28h] [rbp-170h]
  HINSTANCE v8; // [rsp+30h] [rbp-168h]
  _BYTE v9[160]; // [rsp+40h] [rbp-158h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-B8h] BYREF

  result = (char *)CreateEventW(0, 1, 0, 0);
  if ( (unsigned __int64)(result - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v9, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v2);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v9,
      LastErrorAsHResult,
      v4,
      v5,
      v6,
      v7,
      v8);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v9,
      "TImgPipelineManager::CreateEvent() : CreateEvent failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x14001cebc  sub     rsp, 198h
0x14001cec3  mov     rax, cs:__security_cookie
0x14001ceca  xor     rax, rsp
0x14001cecd  mov     [rsp+198h+var_18], rax
0x14001ced5  xor     r9d, r9d; lpName
0x14001ced8  xor     r8d, r8d; bInitialState
0x14001cedb  lea     edx, [r9+1]; bManualReset
0x14001cedf  xor     ecx, ecx; lpEventAttributes
0x14001cee1  call    cs:__imp_CreateEventW
0x14001cee7  lea     rcx, [rax-1]
0x14001ceeb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14001ceef  jbe     short loc_14001CF4F
0x14001cef1  xor     r8d, r8d; unsigned int
0x14001cef4  lea     rdx, asc_1400696D8; "-"
0x14001cefb  lea     rcx, [rsp+198h+var_158]; this
0x14001cf00  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14001cf05  nop
0x14001cf06  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14001cf0b  mov     edx, eax; unsigned int
0x14001cf0d  lea     rcx, [rsp+198h+var_158]; this
0x14001cf12  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14001cf17  lea     rdx, aTimgpipelinema_0; "TImgPipelineManager::CreateEvent() : Cr"...
0x14001cf1e  lea     rcx, [rsp+198h+var_158]; this
0x14001cf23  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14001cf28  lea     rdx, [rsp+198h+var_158]; struct SplException::THResultException *
0x14001cf2d  lea     rcx, [rsp+198h+pExceptionObject]; this
0x14001cf35  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14001cf3a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14001cf41  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x14001cf49  call    _CxxThrowException_0
0x14001cf4f  mov     rcx, [rsp+198h+var_18]
0x14001cf57  xor     rcx, rsp; StackCookie
0x14001cf5a  call    __security_check_cookie
0x14001cf5f  add     rsp, 198h
0x14001cf66  retn
```
