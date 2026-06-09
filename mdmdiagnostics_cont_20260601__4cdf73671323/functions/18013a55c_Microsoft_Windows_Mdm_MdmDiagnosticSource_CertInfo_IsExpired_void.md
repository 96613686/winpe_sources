# Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo::IsExpired(void)

- ea: `0x18013a55c`
- end: `0x18013a5e4`
- name: `?IsExpired@CertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA_NXZ`
- size: `136`
- prototype: `bool __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18012aaf0`

## callees

- `0x180019000`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18013a5c5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18013a5c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18013a581`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18013a581`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013a5a3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013a5b5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013a5a3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013a5b5`

## pseudocode

```c
bool __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo::IsExpired(const SYSTEMTIME *this)
{
  FILETIME FileTime2; // [rsp+20h] [rbp-38h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-28h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  FileTime = 0;
  FileTime2 = 0;
  SystemTimeToFileTime(&SystemTime, &FileTime);
  SystemTimeToFileTime(this + 10, &FileTime2);
  return CompareFileTime(&FileTime, &FileTime2) == 1;
}

```

## disassembly

```asm
0x18013a55c  push    rbx
0x18013a55e  sub     rsp, 50h
0x18013a562  mov     rax, cs:__security_cookie
0x18013a569  xor     rax, rsp
0x18013a56c  mov     [rsp+58h+var_18], rax
0x18013a571  mov     rbx, rcx
0x18013a574  xorps   xmm0, xmm0
0x18013a577  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x18013a57c  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x18013a581  call    cs:__imp_GetLocalTime
0x18013a587  lea     rdx, [rsp+58h+FileTime]; lpFileTime
0x18013a58c  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], 0
0x18013a595  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x18013a59a  mov     qword ptr [rsp+58h+FileTime2.dwLowDateTime], 0
0x18013a5a3  call    cs:__imp_SystemTimeToFileTime
0x18013a5a9  lea     rcx, [rbx+0A0h]; lpSystemTime
0x18013a5b0  lea     rdx, [rsp+58h+FileTime2]; lpFileTime
0x18013a5b5  call    cs:__imp_SystemTimeToFileTime
0x18013a5bb  lea     rdx, [rsp+58h+FileTime2]; lpFileTime2
0x18013a5c0  lea     rcx, [rsp+58h+FileTime]; lpFileTime1
0x18013a5c5  call    cs:__imp_CompareFileTime
0x18013a5cb  cmp     eax, 1
0x18013a5ce  setz    al
0x18013a5d1  mov     rcx, [rsp+58h+var_18]
0x18013a5d6  xor     rcx, rsp; StackCookie
0x18013a5d9  call    __security_check_cookie
0x18013a5de  add     rsp, 50h
0x18013a5e2  pop     rbx
0x18013a5e3  retn
```
