# Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo::IsExpired(void)

- ea: `0x18013c780`
- end: `0x18013c821`
- name: `?IsExpired@CertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA_NXZ`
- size: `161`
- prototype: `bool __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18012c72c`

## callees

- `0x180019080`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18013c7fb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18013c7fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18013c7a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18013c7a5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013c7cd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013c7e5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013c7cd`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18013c7e5`

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
0x18013c780  push    rbx
0x18013c782  sub     rsp, 50h
0x18013c786  mov     rax, cs:__security_cookie
0x18013c78d  xor     rax, rsp
0x18013c790  mov     [rsp+58h+var_18], rax
0x18013c795  mov     rbx, rcx
0x18013c798  xorps   xmm0, xmm0
0x18013c79b  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x18013c7a0  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x18013c7a5  call    cs:__imp_GetLocalTime
0x18013c7ac  nop     dword ptr [rax+rax+00h]
0x18013c7b1  lea     rdx, [rsp+58h+FileTime]; lpFileTime
0x18013c7b6  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], 0
0x18013c7bf  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x18013c7c4  mov     qword ptr [rsp+58h+FileTime2.dwLowDateTime], 0
0x18013c7cd  call    cs:__imp_SystemTimeToFileTime
0x18013c7d4  nop     dword ptr [rax+rax+00h]
0x18013c7d9  lea     rcx, [rbx+0A0h]; lpSystemTime
0x18013c7e0  lea     rdx, [rsp+58h+FileTime2]; lpFileTime
0x18013c7e5  call    cs:__imp_SystemTimeToFileTime
0x18013c7ec  nop     dword ptr [rax+rax+00h]
0x18013c7f1  lea     rdx, [rsp+58h+FileTime2]; lpFileTime2
0x18013c7f6  lea     rcx, [rsp+58h+FileTime]; lpFileTime1
0x18013c7fb  call    cs:__imp_CompareFileTime
0x18013c802  nop     dword ptr [rax+rax+00h]
0x18013c807  cmp     eax, 1
0x18013c80a  setz    al
0x18013c80d  mov     rcx, [rsp+58h+var_18]
0x18013c812  xor     rcx, rsp; StackCookie
0x18013c815  call    __security_check_cookie
0x18013c81a  add     rsp, 50h
0x18013c81e  pop     rbx
0x18013c81f  retn
```
