# CFileListener::ChangeCallback(void)

- ea: `0x1800085e0`
- end: `0x180008710`
- name: `?ChangeCallback@CFileListener@@AEAAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(CFileListener *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ed50`

## callees

- `0x1800085e0`
- `0x180008718`
- `0x18000d374`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!FindNextChangeNotification` at `0x1800086c9`
- `KERNEL32!FindNextChangeNotification` at `0x1800086c9`
- `KERNEL32!LeaveCriticalSection` at `0x1800086ba`
- `KERNEL32!LeaveCriticalSection` at `0x1800086ba`
- `KERNEL32!EnterCriticalSection` at `0x1800086a1`
- `KERNEL32!EnterCriticalSection` at `0x1800086a1`
- `KERNEL32!CompareFileTime` at `0x18000865a`
- `KERNEL32!CompareFileTime` at `0x18000866c`
- `KERNEL32!CompareFileTime` at `0x18000865a`
- `KERNEL32!CompareFileTime` at `0x18000866c`
- `KERNEL32!GetLastError` at `0x180008630`
- `KERNEL32!GetLastError` at `0x1800086d3`
- `KERNEL32!GetLastError` at `0x180008630`
- `KERNEL32!GetLastError` at `0x1800086d3`
- `KERNEL32!GetFileAttributesExW` at `0x180008626`
- `KERNEL32!GetFileAttributesExW` at `0x180008626`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008616`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008616`

## pseudocode

```c
__int64 __fastcall CFileListener::ChangeCallback(CFileListener *this)
{
  const WCHAR *Str; // rax
  signed int LastError; // eax
  int v4; // ebx
  signed int v5; // eax
  __int128 FileInformation; // [rsp+20h] [rbp-38h] BYREF
  FILETIME FileTime1[2]; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+40h] [rbp-18h]

  FileInformation = 0;
  v9 = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  Str = STRU::QueryStr((CFileListener *)((char *)this + 264));
  if ( GetFileAttributesExW(Str, GetFileExInfoStandard, &FileInformation) )
  {
    if ( CompareFileTime((const FILETIME *)((char *)&FileInformation + 12), (const FILETIME *)this + 74)
      && CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, (const FILETIME *)this + 74)
      && (FileTime1[1].dwHighDateTime || v9 != 3) )
    {
      *((FILETIME *)this + 74) = *(FILETIME *)&FileTime1[0].dwHighDateTime;
      v4 = CFileListener::ProcessChanges((LPCWSTR *)this);
      if ( v4 < 0 )
        goto LABEL_11;
      EnterCriticalSection(&CriticalSection);
      FileTime2 = *(FILETIME *)&FileTime1[0].dwHighDateTime;
      LeaveCriticalSection(&CriticalSection);
    }
    v4 = 0;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_11:
  if ( !FindNextChangeNotification(*((HANDLE *)this + 72)) )
  {
    v5 = GetLastError();
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    CListenerController::ReportListenerFailure(*((CListenerController **)this + 75), v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800085e0  mov     [rsp+arg_8], rbx
0x1800085e5  push    rdi
0x1800085e6  sub     rsp, 50h
0x1800085ea  mov     rax, cs:__security_cookie
0x1800085f1  xor     rax, rsp
0x1800085f4  mov     [rsp+58h+var_10], rax
0x1800085f9  xorps   xmm0, xmm0
0x1800085fc  mov     rdi, rcx
0x1800085ff  xor     eax, eax
0x180008601  add     rcx, 108h
0x180008608  movups  [rsp+58h+FileInformation], xmm0
0x18000860d  mov     [rsp+58h+var_18], eax
0x180008611  movups  xmmword ptr [rsp+58h+FileTime1.dwLowDateTime], xmm0
0x180008616  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000861c  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x180008621  xor     edx, edx; fInfoLevelId
0x180008623  mov     rcx, rax; lpFileName
0x180008626  call    cs:__imp_GetFileAttributesExW
0x18000862c  test    eax, eax
0x18000862e  jnz     short loc_18000864B
0x180008630  call    cs:__imp_GetLastError
0x180008636  mov     ebx, eax
0x180008638  test    eax, eax
0x18000863a  jle     loc_1800086C2
0x180008640  movzx   ebx, ax
0x180008643  or      ebx, 80070000h
0x180008649  jmp     short loc_1800086C2
0x18000864b  lea     rbx, [rdi+250h]
0x180008652  mov     rdx, rbx; lpFileTime2
0x180008655  lea     rcx, [rsp+58h+FileInformation+0Ch]; lpFileTime1
0x18000865a  call    cs:__imp_CompareFileTime
0x180008660  test    eax, eax
0x180008662  jz      short loc_1800086C0
0x180008664  mov     rdx, rbx; lpFileTime2
0x180008667  lea     rcx, [rsp+58h+FileTime1.dwHighDateTime]; lpFileTime1
0x18000866c  call    cs:__imp_CompareFileTime
0x180008672  test    eax, eax
0x180008674  jz      short loc_1800086C0
0x180008676  cmp     [rsp+58h+FileTime1.dwHighDateTime+8], 0
0x18000867b  jnz     short loc_180008684
0x18000867d  cmp     [rsp+58h+var_18], 3
0x180008682  jz      short loc_1800086C0
0x180008684  mov     rax, qword ptr [rsp+58h+FileTime1.dwHighDateTime]
0x180008689  mov     rcx, rdi; this
0x18000868c  mov     [rbx], rax
0x18000868f  call    ?ProcessChanges@CFileListener@@AEAAJXZ; CFileListener::ProcessChanges(void)
0x180008694  mov     ebx, eax
0x180008696  test    eax, eax
0x180008698  js      short loc_1800086C2
0x18000869a  lea     rcx, CriticalSection; lpCriticalSection
0x1800086a1  call    cs:__imp_EnterCriticalSection
0x1800086a7  mov     rax, qword ptr [rsp+58h+FileTime1.dwHighDateTime]
0x1800086ac  lea     rcx, CriticalSection; lpCriticalSection
0x1800086b3  mov     qword ptr cs:FileTime2.dwLowDateTime, rax
0x1800086ba  call    cs:__imp_LeaveCriticalSection
0x1800086c0  xor     ebx, ebx
0x1800086c2  mov     rcx, [rdi+240h]; hChangeHandle
0x1800086c9  call    cs:__imp_FindNextChangeNotification
0x1800086cf  test    eax, eax
0x1800086d1  jnz     short loc_1800086F6
0x1800086d3  call    cs:__imp_GetLastError
0x1800086d9  mov     ebx, eax
0x1800086db  test    eax, eax
0x1800086dd  jle     short loc_1800086E8
0x1800086df  movzx   ebx, ax
0x1800086e2  or      ebx, 80070000h
0x1800086e8  mov     rcx, [rdi+258h]; this
0x1800086ef  mov     edx, ebx; int
0x1800086f1  call    ?ReportListenerFailure@CListenerController@@QEAAJJ@Z; CListenerController::ReportListenerFailure(long)
0x1800086f6  mov     eax, ebx
0x1800086f8  mov     rcx, [rsp+58h+var_10]
0x1800086fd  xor     rcx, rsp; StackCookie
0x180008700  call    __security_check_cookie
0x180008705  mov     rbx, [rsp+58h+arg_8]
0x18000870a  add     rsp, 50h
0x18000870e  pop     rdi
0x18000870f  retn
```
