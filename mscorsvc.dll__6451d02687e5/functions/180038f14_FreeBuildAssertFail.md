# __FreeBuildAssertFail

- ea: `0x180038f14`
- end: `0x180039052`
- name: `__FreeBuildAssertFail`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039054`

## callees

- `0x180001de0`
- `0x180001e8c`
- `0x180002440`
- `0x180006488`
- `0x180032654`
- `0x180038834`
- `0x180038898`
- `0x180038ef0`
- `0x180038f14`
- `0x18003b7b8`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18003904b`
- `KERNEL32!DebugBreak` at `0x18003904b`
- `KERNEL32!TerminateProcess` at `0x180039045`
- `KERNEL32!TerminateProcess` at `0x180039045`
- `KERNEL32!GetCurrentProcess` at `0x180039037`
- `KERNEL32!GetCurrentProcess` at `0x180039037`
- `KERNEL32!GetCurrentProcessId` at `0x180038f73`
- `KERNEL32!GetCurrentProcessId` at `0x180038f7b`
- `KERNEL32!GetCurrentProcessId` at `0x180038f73`
- `KERNEL32!GetCurrentProcessId` at `0x180038f7b`
- `KERNEL32!GetCurrentThreadId` at `0x180038f63`
- `KERNEL32!GetCurrentThreadId` at `0x180038f6b`
- `KERNEL32!GetCurrentThreadId` at `0x180038f63`
- `KERNEL32!GetCurrentThreadId` at `0x180038f6b`
- `KERNEL32!OutputDebugStringW` at `0x180038fdf`
- `KERNEL32!OutputDebugStringW` at `0x180038fdf`
- `ucrtbase_clr0400!_flushall` at `0x180039031`
- `ucrtbase_clr0400!_flushall` at `0x180039031`
- `ucrtbase_clr0400!_putws` at `0x180038ff2`
- `ucrtbase_clr0400!_putws` at `0x180038ff2`

## string_xrefs

- `0x180038fa1`: `CLR: Assert failure(PID %d [0x%08x], Thread: %d [0x%x]): %hs\n    File: %hs, Line: %d Image:\n`
- `0x180038f30`: `!"Error during NGen:  expected no exceptions to be thrown"`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __noreturn _FreeBuildAssertFail()
{
  HINSTANCE v0; // rcx
  DWORD CurrentThreadId; // esi
  DWORD v2; // edi
  DWORD CurrentProcessId; // ebx
  DWORD v4; // eax
  const WCHAR *Path; // rax
  const wchar_t *v6; // rax
  unsigned int v7; // r10d
  HANDLE CurrentProcess; // rax
  DWORD v9; // [rsp+20h] [rbp-78h]
  DWORD v10; // [rsp+28h] [rbp-70h]
  int v11; // [rsp+40h] [rbp-58h]
  Image v12[24]; // [rsp+60h] [rbp-38h] BYREF
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
  Path = Image::GetPath(v12);
  OutputDebugStringW(Path);
  v6 = Image::GetPath(v12);
  _putws(v6);
  if ( (unsigned int)StressLog::LogOn(0x10000u, 0) )
    StressLog::LogMsg(0, v7, 2, "ASSERT:%s, line:%d\n", "clr/src/Utilcode/Debug.cpp", 952);
  _flushall();
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0x80131506);
  DebugBreak();
  JUMPOUT(0x180039051LL);
}

```

## disassembly

```asm
0x180038f14  mov     rax, rsp
0x180038f17  mov     [rax+8], rbx
0x180038f1b  mov     [rax+10h], rbp
0x180038f1f  mov     [rax+18h], rsi
0x180038f23  mov     [rax+20h], rdi
0x180038f27  push    r14
0x180038f29  sub     rsp, 90h
0x180038f30  lea     rbp, aErrorDuringNge; "!\"Error during NGen:  expected no exce"...
0x180038f37  lea     r14, aClrSrcUtilcode; "clr/src/Utilcode/Debug.cpp"
0x180038f3e  call    __FreeBuildDebugBreak
0x180038f43  lea     rcx, [rsp+98h+var_38]; this
0x180038f48  call    ??0SString@@QEAA@XZ; SString::SString(void)
0x180038f4d  nop
0x180038f4e  lea     rcx, [rsp+98h+var_20]; this
0x180038f53  call    ??0SString@@QEAA@XZ; SString::SString(void)
0x180038f58  nop
0x180038f59  lea     rdx, [rsp+98h+var_20]; struct SString *
0x180038f5e  call    ?ClrGetModuleFileName@@YAXPEAUHINSTANCE__@@AEAVSString@@@Z; ClrGetModuleFileName(HINSTANCE__ *,SString &)
0x180038f63  call    cs:__imp_GetCurrentThreadId
0x180038f69  mov     esi, eax
0x180038f6b  call    cs:__imp_GetCurrentThreadId
0x180038f71  mov     edi, eax
0x180038f73  call    cs:__imp_GetCurrentProcessId
0x180038f79  mov     ebx, eax
0x180038f7b  call    cs:__imp_GetCurrentProcessId
0x180038f81  mov     r8d, eax
0x180038f84  mov     [rsp+98h+var_58], 3B8h
0x180038f8c  mov     [rsp+98h+var_60], r14
0x180038f91  mov     [rsp+98h+var_68], rbp
0x180038f96  mov     dword ptr [rsp+98h+var_70], esi
0x180038f9a  mov     dword ptr [rsp+98h+var_78], edi
0x180038f9e  mov     r9d, ebx
0x180038fa1  lea     rdx, aClrAssertFailu; "CLR: Assert failure(PID %d [0x%08x], Th"...
0x180038fa8  lea     rcx, [rsp+98h+var_38]; this
0x180038fad  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180038fb2  lea     rdx, [rsp+98h+var_20]; struct SString *
0x180038fb7  lea     rcx, [rsp+98h+var_38]; this
0x180038fbc  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x180038fc1  lea     rdx, asc_180051EB0; "\n"
0x180038fc8  lea     rcx, [rsp+98h+var_38]; this
0x180038fcd  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180038fd2  lea     rcx, [rsp+98h+var_38]; this
0x180038fd7  call    ?GetPath@Image@@QEAAPEBGXZ; Image::GetPath(void)
0x180038fdc  mov     rcx, rax; lpOutputString
0x180038fdf  call    cs:__imp_OutputDebugStringW
0x180038fe5  lea     rcx, [rsp+98h+var_38]; this
0x180038fea  call    ?GetPath@Image@@QEAAPEBGXZ; Image::GetPath(void)
0x180038fef  mov     rcx, rax; Buffer
0x180038ff2  call    cs:__imp__putws
0x180038ff8  xor     edx, edx; unsigned int
0x180038ffa  mov     r10d, 10000h
0x180039000  mov     ecx, r10d; unsigned int
0x180039003  call    ?LogOn@StressLog@@SAHII@Z; StressLog::LogOn(uint,uint)
0x180039008  test    eax, eax
0x18003900a  jz      short loc_180039031
0x18003900c  mov     [rsp+98h+var_70], 3B8h
0x180039015  mov     [rsp+98h+var_78], r14
0x18003901a  lea     r9, aAssertSLineD; "ASSERT:%s, line:%d\n"
0x180039021  mov     r8d, 2; int
0x180039027  mov     edx, r10d; unsigned int
0x18003902a  xor     ecx, ecx; unsigned int
0x18003902c  call    ?LogMsg@StressLog@@SAXIIHPEBDZZ; StressLog::LogMsg(uint,uint,int,char const *,...)
0x180039031  call    cs:__imp__flushall
0x180039037  call    cs:__imp_GetCurrentProcess
0x18003903d  mov     rcx, rax; hProcess
0x180039040  mov     edx, 80131506h; uExitCode
0x180039045  call    cs:__imp_TerminateProcess
0x18003904b  call    cs:__imp_DebugBreak
```
