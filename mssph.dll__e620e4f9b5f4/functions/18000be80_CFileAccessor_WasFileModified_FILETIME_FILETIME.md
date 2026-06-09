# CFileAccessor::WasFileModified(_FILETIME,_FILETIME)

- ea: `0x18000be80`
- end: `0x18000bf03`
- name: `?WasFileModified@CFileAccessor@@AEAA_NU_FILETIME@@0@Z`
- size: `131`
- prototype: `bool __fastcall(CFileAccessor *__hidden this, struct _FILETIME, struct _FILETIME)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x180008da0`
- `0x18000be80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000beb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000beb6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000be9e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000be9e`

## pseudocode

```c
bool __fastcall CFileAccessor::WasFileModified(CFileAccessor *this, FILETIME a2, FILETIME a3)
{
  bool v3; // bl
  const wchar_t *v4; // rdx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF
  FILETIME v7; // [rsp+38h] [rbp+10h] BYREF
  FILETIME v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = a3;
  v7 = a2;
  SystemTimeAsFileTime = (struct _FILETIME)this;
  v3 = 1;
  if ( !CompareFileTime(&v7, &v8) )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = L"no";
    v3 = *(_QWORD *)&v8 + 50000000LL >= *(_QWORD *)&SystemTimeAsFileTime;
    if ( *(_QWORD *)&v8 + 50000000LL < *(_QWORD *)&SystemTimeAsFileTime )
      v4 = L"yes";
    ETWLog::Log(
      L"File times are identical.  Treating as identical: %s  (%d delta time)",
      v4,
      *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v8);
  }
  return v3;
}

```

## disassembly

```asm
0x18000be80  mov     rax, rsp
0x18000be83  mov     [rax+18h], r8
0x18000be87  mov     [rax+10h], rdx
0x18000be8b  mov     [rax+8], rcx
0x18000be8f  push    rbx
0x18000be90  sub     rsp, 20h
0x18000be94  lea     rdx, [rax+18h]; lpFileTime2
0x18000be98  mov     bl, 1
0x18000be9a  lea     rcx, [rax+10h]; lpFileTime1
0x18000be9e  call    cs:__imp_CompareFileTime
0x18000bea4  test    eax, eax
0x18000bea6  jnz     short loc_18000BEFB
0x18000bea8  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000bead  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000beb6  call    cs:__imp_GetSystemTimeAsFileTime
0x18000bebc  mov     rcx, [rsp+28h+arg_10]
0x18000bec1  xor     eax, eax
0x18000bec3  mov     r8, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x18000bec8  movzx   ebx, bl
0x18000becb  lea     rdx, [rcx+2FAF080h]
0x18000bed2  cmp     rdx, r8
0x18000bed5  lea     rdx, aNo; "no"
0x18000bedc  cmovl   ebx, eax
0x18000bedf  sub     r8, rcx
0x18000bee2  test    bl, bl
0x18000bee4  lea     rax, aYes; "yes"
0x18000beeb  lea     rcx, aFileTimesAreId; "File times are identical.  Treating as "...
0x18000bef2  cmovz   rdx, rax
0x18000bef6  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x18000befb  mov     al, bl
0x18000befd  add     rsp, 20h
0x18000bf01  pop     rbx
0x18000bf02  retn
```
