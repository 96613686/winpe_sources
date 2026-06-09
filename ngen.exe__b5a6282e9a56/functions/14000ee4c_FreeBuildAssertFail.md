# __FreeBuildAssertFail

- ea: `0x14000ee4c`
- end: `0x14000ef8a`
- name: `__FreeBuildAssertFail`
- size: `318`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140015309`

## callees

- `0x140001214`
- `0x1400012c0`
- `0x14000a9bc`
- `0x14000a9dc`
- `0x14000bd40`
- `0x14000ee28`
- `0x14000ee4c`
- `0x14000f87c`
- `0x14000f8e0`
- `0x140011b6c`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x14000ef17`
- `KERNEL32!OutputDebugStringW` at `0x14000ef17`
- `KERNEL32!GetCurrentThreadId` at `0x14000ee9b`
- `KERNEL32!GetCurrentThreadId` at `0x14000eea3`
- `KERNEL32!GetCurrentThreadId` at `0x14000ee9b`
- `KERNEL32!GetCurrentThreadId` at `0x14000eea3`
- `KERNEL32!TerminateProcess` at `0x14000ef7d`
- `KERNEL32!TerminateProcess` at `0x14000ef7d`
- `KERNEL32!GetCurrentProcess` at `0x14000ef6f`
- `KERNEL32!GetCurrentProcess` at `0x14000ef6f`
- `KERNEL32!DebugBreak` at `0x14000ef83`
- `KERNEL32!DebugBreak` at `0x14000ef83`
- `KERNEL32!GetCurrentProcessId` at `0x14000eeab`
- `KERNEL32!GetCurrentProcessId` at `0x14000eeb3`
- `KERNEL32!GetCurrentProcessId` at `0x14000eeab`
- `KERNEL32!GetCurrentProcessId` at `0x14000eeb3`
- `ucrtbase_clr0400!_putws` at `0x14000ef2a`
- `ucrtbase_clr0400!_putws` at `0x14000ef2a`
- `ucrtbase_clr0400!_flushall` at `0x14000ef69`
- `ucrtbase_clr0400!_flushall` at `0x14000ef69`

## string_xrefs

- `0x14000eed9`: `CLR: Assert failure(PID %d [0x%08x], Thread: %d [0x%x]): %hs\n    File: %hs, Line: %d Image:\n`
- `0x14000ee68`: `!"Error during NGen:  expected no exceptions to be thrown"`

## pseudocode

```c
void __noreturn _FreeBuildAssertFail()
{
  HINSTANCE v0; // rcx
  DWORD CurrentThreadId; // esi
  DWORD v2; // edi
  DWORD CurrentProcessId; // ebx
  DWORD v4; // eax
  const WCHAR *v5; // rax
  const wchar_t *v6; // rax
  unsigned int v7; // r10d
  HANDLE CurrentProcess; // rax
  DWORD v9; // [rsp+20h] [rbp-78h]
  DWORD v10; // [rsp+28h] [rbp-70h]
  int v11; // [rsp+40h] [rbp-58h]
  _BYTE v12[24]; // [rsp+60h] [rbp-38h] BYREF
  _BYTE v13[32]; // [rsp+78h] [rbp-20h] BYREF

  _FreeBuildDebugBreak();
  SString::SString((SString *)v12);
  SString::SString((SString *)v13);
  ClrGetModuleFileName(v0, (struct SString *)v13);
  CurrentThreadId = GetCurrentThreadId();
  v2 = GetCurrentThreadId();
  CurrentProcessId = GetCurrentProcessId();
  v4 = GetCurrentProcessId();
  v11 = 952;
  v10 = CurrentThreadId;
  v9 = v2;
  SString::Printf(
    (SString *)v12,
    L"CLR: Assert failure(PID %d [0x%08x], Thread: %d [0x%x]): %hs\n    File: %hs, Line: %d Image:\n",
    v4,
    CurrentProcessId,
    v9,
    v10,
    "!\"Error during NGen:  expected no exceptions to be thrown\"",
    "clr/src/Utilcode/Debug.cpp",
    v11);
  SString::Append((SString *)v12, (const struct SString *)v13);
  SString::Append((SString *)v12, L"\n");
  v5 = (const WCHAR *)SString::operator unsigned short const *(v12);
  OutputDebugStringW(v5);
  v6 = (const wchar_t *)SString::operator unsigned short const *(v12);
  _putws(v6);
  if ( (unsigned int)StressLog::LogOn(0x10000u, 0) )
    StressLog::LogMsg(0, v7, 2, "ASSERT:%s, line:%d\n", "clr/src/Utilcode/Debug.cpp", 952);
  _flushall();
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0x80131506);
  DebugBreak();
  JUMPOUT(0x14000EF89LL);
}

```

## disassembly

```asm
0x14000ee4c  mov     rax, rsp
0x14000ee4f  mov     [rax+8], rbx
0x14000ee53  mov     [rax+10h], rbp
0x14000ee57  mov     [rax+18h], rsi
0x14000ee5b  mov     [rax+20h], rdi
0x14000ee5f  push    r14
0x14000ee61  sub     rsp, 90h
0x14000ee68  lea     rbp, aErrorDuringNge; "!\"Error during NGen:  expected no exce"...
0x14000ee6f  lea     r14, aClrSrcUtilcode; "clr/src/Utilcode/Debug.cpp"
0x14000ee76  call    __FreeBuildDebugBreak
0x14000ee7b  lea     rcx, [rsp+98h+var_38]; this
0x14000ee80  call    ??0SString@@QEAA@XZ; SString::SString(void)
0x14000ee85  nop
0x14000ee86  lea     rcx, [rsp+98h+var_20]; this
0x14000ee8b  call    ??0SString@@QEAA@XZ; SString::SString(void)
0x14000ee90  nop
0x14000ee91  lea     rdx, [rsp+98h+var_20]; struct SString *
0x14000ee96  call    ?ClrGetModuleFileName@@YAXPEAUHINSTANCE__@@AEAVSString@@@Z; ClrGetModuleFileName(HINSTANCE__ *,SString &)
0x14000ee9b  call    cs:__imp_GetCurrentThreadId
0x14000eea1  mov     esi, eax
0x14000eea3  call    cs:__imp_GetCurrentThreadId
0x14000eea9  mov     edi, eax
0x14000eeab  call    cs:__imp_GetCurrentProcessId
0x14000eeb1  mov     ebx, eax
0x14000eeb3  call    cs:__imp_GetCurrentProcessId
0x14000eeb9  mov     r8d, eax
0x14000eebc  mov     [rsp+98h+var_58], 3B8h
0x14000eec4  mov     [rsp+98h+var_60], r14
0x14000eec9  mov     [rsp+98h+var_68], rbp
0x14000eece  mov     dword ptr [rsp+98h+var_70], esi
0x14000eed2  mov     dword ptr [rsp+98h+var_78], edi
0x14000eed6  mov     r9d, ebx
0x14000eed9  lea     rdx, aClrAssertFailu; "CLR: Assert failure(PID %d [0x%08x], Th"...
0x14000eee0  lea     rcx, [rsp+98h+var_38]; this
0x14000eee5  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x14000eeea  lea     rdx, [rsp+98h+var_20]; struct SString *
0x14000eeef  lea     rcx, [rsp+98h+var_38]; this
0x14000eef4  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x14000eef9  lea     rdx, asc_1400168B8; "\n"
0x14000ef00  lea     rcx, [rsp+98h+var_38]; this
0x14000ef05  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x14000ef0a  lea     rcx, [rsp+98h+var_38]
0x14000ef0f  call    ??BSString@@QEBAPEBGXZ; SString::operator ushort const *(void)
0x14000ef14  mov     rcx, rax; lpOutputString
0x14000ef17  call    cs:__imp_OutputDebugStringW
0x14000ef1d  lea     rcx, [rsp+98h+var_38]
0x14000ef22  call    ??BSString@@QEBAPEBGXZ; SString::operator ushort const *(void)
0x14000ef27  mov     rcx, rax; Buffer
0x14000ef2a  call    cs:__imp__putws
0x14000ef30  xor     edx, edx; unsigned int
0x14000ef32  mov     r10d, 10000h
0x14000ef38  mov     ecx, r10d; unsigned int
0x14000ef3b  call    ?LogOn@StressLog@@SAHII@Z; StressLog::LogOn(uint,uint)
0x14000ef40  test    eax, eax
0x14000ef42  jz      short loc_14000EF69
0x14000ef44  mov     [rsp+98h+var_70], 3B8h
0x14000ef4d  mov     [rsp+98h+var_78], r14
0x14000ef52  lea     r9, aAssertSLineD; "ASSERT:%s, line:%d\n"
0x14000ef59  mov     r8d, 2; int
0x14000ef5f  mov     edx, r10d; unsigned int
0x14000ef62  xor     ecx, ecx; unsigned int
0x14000ef64  call    ?LogMsg@StressLog@@SAXIIHPEBDZZ; StressLog::LogMsg(uint,uint,int,char const *,...)
0x14000ef69  call    cs:__imp__flushall
0x14000ef6f  call    cs:__imp_GetCurrentProcess
0x14000ef75  mov     rcx, rax; hProcess
0x14000ef78  mov     edx, 80131506h; uExitCode
0x14000ef7d  call    cs:__imp_TerminateProcess
0x14000ef83  call    cs:__imp_DebugBreak
```
