# CRight::SetValidityTime(_SYSTEMTIME *,_SYSTEMTIME *)

- ea: `0x180016b00`
- end: `0x180016ba7`
- name: `?SetValidityTime@CRight@@QEAAJPEAU_SYSTEMTIME@@0@Z`
- size: `167`
- prototype: `int(CRight *__hidden this, struct _SYSTEMTIME *, struct _SYSTEMTIME *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004ec0`
- `0x180014b20`

## callees

- `0x180016b00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016b1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016b1f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016b66`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016b66`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016b39`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016b52`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016b39`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016b52`

## pseudocode

```c
__int64 __fastcall CRight::SetValidityTime(CRight *this, struct _SYSTEMTIME *a2, struct _SYSTEMTIME *a3)
{
  unsigned int v6; // ebx
  FILETIME FileTime2; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME FileTime; // [rsp+58h] [rbp+20h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v6 = 0;
  FileTime = 0;
  FileTime2 = 0;
  if ( SystemTimeToFileTime(a2, &FileTime)
    && SystemTimeToFileTime(a3, &FileTime2)
    && CompareFileTime(&FileTime, &FileTime2) == -1 )
  {
    *((struct _SYSTEMTIME *)this + 10) = *a2;
    *((struct _SYSTEMTIME *)this + 11) = *a3;
  }
  else
  {
    v6 = -2147168431;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  return v6;
}

```

## disassembly

```asm
0x180016b00  mov     [rsp+arg_8], rbx
0x180016b05  mov     [rsp+arg_10], rbp
0x180016b0a  push    rsi
0x180016b0b  push    rdi
0x180016b0c  push    r14
0x180016b0e  sub     rsp, 20h
0x180016b12  mov     rdi, rcx
0x180016b15  mov     rsi, r8
0x180016b18  add     rcx, 58h ; 'X'; lpCriticalSection
0x180016b1c  mov     r14, rdx
0x180016b1f  call    cs:__imp_EnterCriticalSection
0x180016b25  xor     ebx, ebx
0x180016b27  lea     rdx, [rsp+38h+FileTime]; lpFileTime
0x180016b2c  mov     rcx, r14; lpSystemTime
0x180016b2f  mov     qword ptr [rsp+38h+FileTime.dwLowDateTime], rbx
0x180016b34  mov     qword ptr [rsp+38h+FileTime2.dwLowDateTime], rbx
0x180016b39  call    cs:__imp_SystemTimeToFileTime
0x180016b3f  test    eax, eax
0x180016b41  jnz     short loc_180016B4A
0x180016b43  mov     ebx, 8004CF51h
0x180016b48  jmp     short loc_180016B88
0x180016b4a  lea     rdx, [rsp+38h+FileTime2]; lpFileTime
0x180016b4f  mov     rcx, rsi; lpSystemTime
0x180016b52  call    cs:__imp_SystemTimeToFileTime
0x180016b58  test    eax, eax
0x180016b5a  jz      short loc_180016B43
0x180016b5c  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x180016b61  lea     rcx, [rsp+38h+FileTime]; lpFileTime1
0x180016b66  call    cs:__imp_CompareFileTime
0x180016b6c  cmp     eax, 0FFFFFFFFh
0x180016b6f  jnz     short loc_180016B43
0x180016b71  movups  xmm0, xmmword ptr [r14]
0x180016b75  movdqu  xmmword ptr [rdi+0A0h], xmm0
0x180016b7d  movups  xmm1, xmmword ptr [rsi]
0x180016b80  movdqu  xmmword ptr [rdi+0B0h], xmm1
0x180016b88  lea     rcx, [rdi+58h]; lpCriticalSection
0x180016b8c  call    cs:__imp_LeaveCriticalSection
0x180016b92  mov     rbp, [rsp+38h+arg_10]
0x180016b97  mov     eax, ebx
0x180016b99  mov     rbx, [rsp+38h+arg_8]
0x180016b9e  add     rsp, 20h
0x180016ba2  pop     r14
0x180016ba4  pop     rdi
0x180016ba5  pop     rsi
0x180016ba6  retn
```
