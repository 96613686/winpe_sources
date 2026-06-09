# CHiveUploadTaskSchedule::_IncreaseTime(_SYSTEMTIME &,ushort)

- ea: `0x18001a14c`
- end: `0x18001a1dc`
- name: `?_IncreaseTime@CHiveUploadTaskSchedule@@AEAAJAEAU_SYSTEMTIME@@G@Z`
- size: `144`
- prototype: `__int64 __fastcall(CHiveUploadTaskSchedule *this, struct _SYSTEMTIME *, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800196a8`

## callees

- `0x18000547c`
- `0x18001a14c`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a1be`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a1be`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001a172`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001a172`

## string_xrefs

- `0x18001a186`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskSchedule::_IncreaseTime(
        CHiveUploadTaskSchedule *this,
        struct _SYSTEMTIME *a2,
        unsigned __int16 a3)
{
  __int64 v4; // rdi
  const char *v5; // r9
  __int64 v6; // rdx
  __int64 v8; // rdi
  __int64 v9; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  FILETIME FileTime; // [rsp+30h] [rbp+8h] BYREF

  v4 = a3;
  FileTime = 0;
  if ( !SystemTimeToFileTime(a2, &FileTime) )
  {
    v6 = 166;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
             v5);
  }
  v8 = 36000000000LL * v4;
  v9 = v8 + *(_QWORD *)&FileTime;
  FileTime.dwLowDateTime += v8;
  FileTime.dwHighDateTime = HIDWORD(v9);
  if ( !FileTimeToSystemTime(&FileTime, a2) )
  {
    v6 = 176;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
             v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18001a14c  mov     rax, rsp
0x18001a14f  mov     [rax+10h], rbx
0x18001a153  mov     [rax+8], rcx
0x18001a157  push    rdi
0x18001a158  sub     rsp, 20h
0x18001a15c  mov     rbx, rdx
0x18001a15f  movzx   edi, r8w
0x18001a163  mov     rcx, rbx; lpSystemTime
0x18001a166  mov     qword ptr [rax+8], 0
0x18001a16e  lea     rdx, [rax+8]; lpFileTime
0x18001a172  call    cs:__imp_SystemTimeToFileTime
0x18001a178  test    eax, eax
0x18001a17a  jnz     short loc_18001A194
0x18001a17c  mov     edx, 0A6h; void *
0x18001a181  mov     rcx, [rsp+28h]; this
0x18001a186  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18001a18d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a192  jmp     short loc_18001A1D1
0x18001a194  mov     rax, qword ptr [rsp+28h+FileTime.dwLowDateTime]
0x18001a199  lea     rcx, [rsp+28h+FileTime]; lpFileTime
0x18001a19e  mov     rdx, 861C46800h
0x18001a1a8  imul    rdi, rdx
0x18001a1ac  mov     rdx, rbx; lpSystemTime
0x18001a1af  add     rax, rdi
0x18001a1b2  mov     [rsp+28h+FileTime.dwLowDateTime], eax
0x18001a1b6  shr     rax, 20h
0x18001a1ba  mov     [rsp+28h+FileTime.dwHighDateTime], eax
0x18001a1be  call    cs:__imp_FileTimeToSystemTime
0x18001a1c4  test    eax, eax
0x18001a1c6  jnz     short loc_18001A1CF
0x18001a1c8  mov     edx, 0B0h
0x18001a1cd  jmp     short loc_18001A181
0x18001a1cf  xor     eax, eax
0x18001a1d1  mov     rbx, [rsp+28h+arg_8]
0x18001a1d6  add     rsp, 20h
0x18001a1da  pop     rdi
0x18001a1db  retn
```
