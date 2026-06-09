# NgenTask::CreateFXUpdateFile(void)

- ea: `0x180016eb0`
- end: `0x180016fd3`
- name: `?CreateFXUpdateFile@NgenTask@@YAXXZ`
- size: `291`
- prototype: `void __fastcall(NgenTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180016fd4`

## callees

- `0x180001e8c`
- `0x1800020f0`
- `0x180016eb0`
- `0x180030d84`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180016f61`
- `KERNEL32!CreateFileW` at `0x180016f61`
- `KERNEL32!CloseHandle` at `0x180016f70`
- `KERNEL32!CloseHandle` at `0x180016f70`
- `KERNEL32!HeapFree` at `0x180016fa9`
- `KERNEL32!HeapFree` at `0x180016fa9`
- `KERNEL32!GetProcessHeap` at `0x180016f94`
- `KERNEL32!GetProcessHeap` at `0x180016f94`

## string_xrefs

- `0x180016f24`: `FXUpdate.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall NgenTask::CreateFXUpdateFile(NgenTask *this)
{
  HANDLE FileW; // rax
  WCHAR *v2; // rbx
  HANDLE ProcessHeap; // rax
  int v4; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v5; // [rsp+44h] [rbp-BCh]
  LPCWSTR lpFileName; // [rsp+50h] [rbp-B0h]
  __int16 v7; // [rsp+58h] [rbp-A8h] BYREF

  v5 = 512;
  lpFileName = (LPCWSTR)&v7;
  v4 = 2;
  v7 = 0;
  Helpers::GetVersionDirectoryPathFromCurrentModulePath((struct SString *)&v4);
  SString::Append((SString *)&v4, L"\\");
  SString::Append((SString *)&v4, L"FXUpdate.dat");
  SString::ConvertToUnicode((SString *)&v4);
  FileW = CreateFileW(lpFileName, 0x120116u, 7u, 0, 2u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( (v5 & 0x800000000LL) != 0 )
  {
    v2 = (WCHAR *)lpFileName;
    if ( lpFileName )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v2);
    }
  }
}

```

## disassembly

```asm
0x180016eb0  mov     [rsp-8+arg_0], rbx
0x180016eb5  mov     [rsp-8+arg_8], rdi
0x180016eba  push    rbp
0x180016ebb  lea     rbp, [rsp-170h]
0x180016ec3  sub     rsp, 270h
0x180016eca  mov     rax, cs:__security_cookie
0x180016ed1  xor     rax, rsp
0x180016ed4  mov     [rbp+170h+var_10], rax
0x180016edb  xor     edi, edi
0x180016edd  mov     [rsp+270h+var_230], rdi
0x180016ee2  mov     [rsp+270h+var_230+4], 200h
0x180016eeb  mov     [rsp+270h+lpFileName], rdi
0x180016ef0  lea     rax, [rsp+270h+var_218]
0x180016ef5  mov     [rsp+270h+lpFileName], rax
0x180016efa  lea     ebx, [rdi+2]
0x180016efd  mov     dword ptr [rsp+270h+var_230], ebx
0x180016f01  mov     rax, [rsp+270h+lpFileName]
0x180016f06  mov     [rax], di
0x180016f09  lea     rcx, [rsp+270h+var_230]; this
0x180016f0e  call    ?GetVersionDirectoryPathFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryPathFromCurrentModulePath(SString &)
0x180016f13  lea     rdx, asc_180049544; "\\"
0x180016f1a  lea     rcx, [rsp+270h+var_230]; this
0x180016f1f  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016f24  lea     rdx, aFxupdateDat; "FXUpdate.dat"
0x180016f2b  lea     rcx, [rsp+270h+var_230]; this
0x180016f30  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016f35  lea     rcx, [rsp+270h+var_230]; this
0x180016f3a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180016f3f  mov     [rsp+270h+hTemplateFile], rdi; hTemplateFile
0x180016f44  mov     [rsp+270h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180016f4c  mov     [rsp+270h+dwCreationDisposition], ebx; dwCreationDisposition
0x180016f50  xor     r9d, r9d; lpSecurityAttributes
0x180016f53  mov     edx, 120116h; dwDesiredAccess
0x180016f58  lea     r8d, [rdi+7]; dwShareMode
0x180016f5c  mov     rcx, [rsp+270h+lpFileName]; lpFileName
0x180016f61  call    cs:__imp_CreateFileW
0x180016f67  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016f6b  jz      short loc_180016F77
0x180016f6d  mov     rcx, rax; hObject
0x180016f70  call    cs:__imp_CloseHandle
0x180016f76  nop
0x180016f77  test    [rsp+270h+var_228], 8
0x180016f7c  jz      short loc_180016FAF
0x180016f7e  mov     rbx, [rsp+270h+lpFileName]
0x180016f83  test    rbx, rbx
0x180016f86  jz      short loc_180016FAF
0x180016f88  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180016f8f  test    rax, rax
0x180016f92  jnz     short loc_180016FA1
0x180016f94  call    cs:__imp_GetProcessHeap
0x180016f9a  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180016fa1  mov     r8, rbx; lpMem
0x180016fa4  xor     edx, edx; dwFlags
0x180016fa6  mov     rcx, rax; hHeap
0x180016fa9  call    cs:__imp_HeapFree
0x180016faf  mov     rcx, [rbp+170h+var_10]
0x180016fb6  xor     rcx, rsp; StackCookie
0x180016fb9  call    __security_check_cookie
0x180016fbe  lea     r11, [rsp+270h+var_s0]
0x180016fc6  mov     rbx, [r11+10h]
0x180016fca  mov     rdi, [r11+18h]
0x180016fce  mov     rsp, r11
0x180016fd1  pop     rbp
0x180016fd2  retn
```
