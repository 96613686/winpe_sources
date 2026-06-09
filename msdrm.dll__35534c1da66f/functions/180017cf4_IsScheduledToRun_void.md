# IsScheduledToRun(void)

- ea: `0x180017cf4`
- end: `0x180017e98`
- name: `?IsScheduledToRun@@YAHXZ`
- size: `420`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180017acc`

## callees

- `0x180001284`
- `0x1800175c0`
- `0x18001789c`
- `0x180017968`
- `0x180017cf4`
- `0x1800182e8`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017db7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017e03`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017e57`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017db7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017e03`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017e57`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017d54`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017da1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017e45`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017d54`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017da1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180017e45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180017d46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180017d46`

## string_xrefs

- `0x180017e12`: `updateIfLastUpdatedBeforeTime`
- `0x180017e19`: `SOFTWARE\Policies\Microsoft\MSDRM\TemplateManagement`
- `0x180017d66`: `lastUpdatedTime`
- `0x180017d6d`: `SOFTWARE\Microsoft\MSDRM\TemplateManagement`

## pseudocode

```c
__int64 IsScheduledToRun(void)
{
  unsigned int v0; // ebx
  unsigned __int16 *v1; // rsi
  unsigned __int16 *v2; // rdi
  int RegString; // eax
  const unsigned __int16 *v4; // rdx
  const unsigned __int16 *v5; // rcx
  unsigned int v6; // ecx
  int v7; // eax
  struct _FILETIME FileTime; // [rsp+20h] [rbp-39h] BYREF
  unsigned int v10; // [rsp+28h] [rbp-31h] BYREF
  FILETIME FileTime2; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 *v12; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int16 *v13; // [rsp+40h] [rbp-19h] BYREF
  FILETIME v14; // [rsp+48h] [rbp-11h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-9h] BYREF
  SYSTEMTIME v16; // [rsp+60h] [rbp+7h] BYREF
  SYSTEMTIME v17; // [rsp+70h] [rbp+17h] BYREF

  v0 = 0;
  v10 = 0;
  FileTime = 0;
  v1 = 0;
  FileTime2 = 0;
  v2 = 0;
  v13 = 0;
  v12 = 0;
  v14 = 0;
  SystemTime = 0;
  v16 = 0;
  v17 = 0;
  GetSystemTime(&SystemTime);
  if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    RegString = GetRegString(L"SOFTWARE\\Microsoft\\MSDRM\\TemplateManagement", L"lastUpdatedTime", &v13);
    v1 = v13;
    if ( !RegString
      || (int)DecipherTime(v13, &v16) < 0
      || !SystemTimeToFileTime(&v16, &FileTime2)
      || CompareFileTime(&FileTime, &FileTime2) == -1 )
    {
      SetLastUpdatedTime();
LABEL_15:
      v0 = 1;
      goto LABEL_16;
    }
    GetRegDWORD(v5, v4, &v10);
    v6 = v10;
    if ( !v10 )
      v6 = 30;
    *(_QWORD *)&FileTime += -10000000LL * (int)(86400 * v6);
    if ( CompareFileTime(&FileTime2, &FileTime) == -1 )
      goto LABEL_15;
    v7 = GetRegString(
           L"SOFTWARE\\Policies\\Microsoft\\MSDRM\\TemplateManagement",
           L"updateIfLastUpdatedBeforeTime",
           &v12);
    v2 = v12;
    if ( v7 )
    {
      if ( (int)DecipherTime(v12, &v17) >= 0
        && SystemTimeToFileTime(&v17, &v14)
        && CompareFileTime(&FileTime2, &v14) == -1 )
      {
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  operator delete(v1);
  operator delete(v2);
  return v0;
}

```

## disassembly

```asm
0x180017cf4  push    rbp
0x180017cf6  push    rbx
0x180017cf7  push    rsi
0x180017cf8  push    rdi
0x180017cf9  lea     rbp, [rsp-3Fh]
0x180017cfe  sub     rsp, 98h
0x180017d05  mov     rax, cs:__security_cookie
0x180017d0c  xor     rax, rsp
0x180017d0f  mov     [rbp+57h+var_30], rax
0x180017d13  xor     ebx, ebx
0x180017d15  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180017d19  xorps   xmm0, xmm0
0x180017d1c  mov     [rbp+57h+var_88], ebx
0x180017d1f  xorps   xmm1, xmm1
0x180017d22  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rbx
0x180017d26  xor     esi, esi
0x180017d28  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rbx
0x180017d2c  xor     edi, edi
0x180017d2e  mov     [rbp+57h+var_70], rsi
0x180017d32  mov     [rbp+57h+var_78], rdi
0x180017d36  mov     qword ptr [rbp+57h+var_68.dwLowDateTime], rbx
0x180017d3a  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180017d3e  movups  xmmword ptr [rbp+57h+var_50.wYear], xmm1
0x180017d42  movups  xmmword ptr [rbp+57h+var_40.wYear], xmm0
0x180017d46  call    cs:__imp_GetSystemTime
0x180017d4c  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180017d50  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180017d54  call    cs:__imp_SystemTimeToFileTime
0x180017d5a  test    eax, eax
0x180017d5c  jz      loc_180017E6E
0x180017d62  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x180017d66  lea     rdx, ?g_wszTM_Value_lastUpdatedTime@@3QBGB; "lastUpdatedTime"
0x180017d6d  lea     rcx, ?g_wszTM_Key@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\TemplateMan"...
0x180017d74  call    ?GetRegString@@YAHPEBG0PEAPEAG@Z; GetRegString(ushort const *,ushort const *,ushort * *)
0x180017d79  mov     rsi, [rbp+57h+var_70]
0x180017d7d  test    eax, eax
0x180017d7f  jz      loc_180017E64
0x180017d85  lea     rdx, [rbp+57h+var_50]; struct _SYSTEMTIME *
0x180017d89  mov     rcx, rsi; unsigned __int16 *
0x180017d8c  call    ?DecipherTime@@YAJPEBGPEAU_SYSTEMTIME@@@Z; DecipherTime(ushort const *,_SYSTEMTIME *)
0x180017d91  test    eax, eax
0x180017d93  js      loc_180017E64
0x180017d99  lea     rdx, [rbp+57h+FileTime2]; lpFileTime
0x180017d9d  lea     rcx, [rbp+57h+var_50]; lpSystemTime
0x180017da1  call    cs:__imp_SystemTimeToFileTime
0x180017da7  test    eax, eax
0x180017da9  jz      loc_180017E64
0x180017daf  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x180017db3  lea     rcx, [rbp+57h+FileTime]; lpFileTime1
0x180017db7  call    cs:__imp_CompareFileTime
0x180017dbd  cmp     eax, 0FFFFFFFFh
0x180017dc0  jz      loc_180017E64
0x180017dc6  lea     r8, [rbp+57h+var_88]; unsigned int *
0x180017dca  call    ?GetRegDWORD@@YAHPEBG0PEAK@Z; GetRegDWORD(ushort const *,ushort const *,ulong *)
0x180017dcf  mov     ecx, [rbp+57h+var_88]
0x180017dd2  lea     eax, [rbx+1Eh]
0x180017dd5  test    ecx, ecx
0x180017dd7  cmovz   ecx, eax
0x180017dda  mov     rax, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180017dde  imul    ecx, 15180h
0x180017de4  movsxd  rdx, ecx
0x180017de7  imul    rcx, rdx, 0FFFFFFFFFF676980h
0x180017dee  lea     rdx, [rbp+57h+FileTime]; lpFileTime2
0x180017df2  add     rax, rcx
0x180017df5  lea     rcx, [rbp+57h+FileTime2]; lpFileTime1
0x180017df9  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180017dfc  shr     rax, 20h
0x180017e00  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x180017e03  call    cs:__imp_CompareFileTime
0x180017e09  cmp     eax, 0FFFFFFFFh
0x180017e0c  jz      short loc_180017E69
0x180017e0e  lea     r8, [rbp+57h+var_78]; unsigned __int16 **
0x180017e12  lea     rdx, ?g_wszTM_Value_updateIfLastUpdatedBeforeTime@@3QBGB; "updateIfLastUpdatedBeforeTime"
0x180017e19  lea     rcx, ?g_wszTM_Policy_Key@@3QBGB; "SOFTWARE\\Policies\\Microsoft\\MSDRM\\T"...
0x180017e20  call    ?GetRegString@@YAHPEBG0PEAPEAG@Z; GetRegString(ushort const *,ushort const *,ushort * *)
0x180017e25  mov     rdi, [rbp+57h+var_78]
0x180017e29  test    eax, eax
0x180017e2b  jz      short loc_180017E6E
0x180017e2d  lea     rdx, [rbp+57h+var_40]; struct _SYSTEMTIME *
0x180017e31  mov     rcx, rdi; unsigned __int16 *
0x180017e34  call    ?DecipherTime@@YAJPEBGPEAU_SYSTEMTIME@@@Z; DecipherTime(ushort const *,_SYSTEMTIME *)
0x180017e39  test    eax, eax
0x180017e3b  js      short loc_180017E6E
0x180017e3d  lea     rdx, [rbp+57h+var_68]; lpFileTime
0x180017e41  lea     rcx, [rbp+57h+var_40]; lpSystemTime
0x180017e45  call    cs:__imp_SystemTimeToFileTime
0x180017e4b  test    eax, eax
0x180017e4d  jz      short loc_180017E6E
0x180017e4f  lea     rdx, [rbp+57h+var_68]; lpFileTime2
0x180017e53  lea     rcx, [rbp+57h+FileTime2]; lpFileTime1
0x180017e57  call    cs:__imp_CompareFileTime
0x180017e5d  cmp     eax, 0FFFFFFFFh
0x180017e60  jnz     short loc_180017E6E
0x180017e62  jmp     short loc_180017E69
0x180017e64  call    ?SetLastUpdatedTime@@YAHXZ; SetLastUpdatedTime(void)
0x180017e69  mov     ebx, 1
0x180017e6e  mov     rcx, rsi; Block
0x180017e71  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017e76  mov     rcx, rdi; Block
0x180017e79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017e7e  mov     eax, ebx
0x180017e80  mov     rcx, [rbp+57h+var_30]
0x180017e84  xor     rcx, rsp; StackCookie
0x180017e87  call    __security_check_cookie
0x180017e8c  add     rsp, 98h
0x180017e93  pop     rdi
0x180017e94  pop     rsi
0x180017e95  pop     rbx
0x180017e96  pop     rbp
0x180017e97  retn
```
