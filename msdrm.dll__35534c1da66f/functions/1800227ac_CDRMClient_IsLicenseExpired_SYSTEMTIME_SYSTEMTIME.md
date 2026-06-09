# CDRMClient::IsLicenseExpired(_SYSTEMTIME *,_SYSTEMTIME *)

- ea: `0x1800227ac`
- end: `0x180022890`
- name: `?IsLicenseExpired@CDRMClient@@AEAAHPEAU_SYSTEMTIME@@0@Z`
- size: `228`
- prototype: `int(CDRMClient *__hidden this, struct _SYSTEMTIME *, struct _SYSTEMTIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022190`

## callees

- `0x1800227ac`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002284a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180022862`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18002284a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180022862`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180022815`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180022826`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180022838`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180022815`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180022826`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180022838`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800227f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800227f2`

## pseudocode

```c
__int64 __fastcall CDRMClient::IsLicenseExpired(CDRMClient *this, struct _SYSTEMTIME *a2, struct _SYSTEMTIME *a3)
{
  unsigned int v3; // edi
  FILETIME FileTime2; // [rsp+20h] [rbp-30h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-28h] BYREF
  FILETIME FileTime1; // [rsp+30h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-18h] BYREF

  FileTime = 0;
  v3 = 0;
  FileTime2 = 0;
  FileTime1 = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a2->wYear )
      {
        if ( a3->wYear )
        {
          if ( SystemTimeToFileTime(a2, &FileTime) )
          {
            if ( SystemTimeToFileTime(a3, &FileTime2) )
            {
              if ( SystemTimeToFileTime(&SystemTime, &FileTime1) )
              {
                LOBYTE(v3) = CompareFileTime(&FileTime, &FileTime2) == 1;
                if ( CompareFileTime(&FileTime1, &FileTime2) == 1 )
                  return 1;
              }
            }
          }
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800227ac  mov     [rsp-18h+arg_0], rbx
0x1800227b1  mov     [rsp-18h+arg_18], rsi
0x1800227b6  push    rbp
0x1800227b7  push    rdi
0x1800227b8  push    r14
0x1800227ba  mov     rbp, rsp
0x1800227bd  sub     rsp, 50h
0x1800227c1  mov     rax, cs:__security_cookie
0x1800227c8  xor     rax, rsp
0x1800227cb  mov     [rbp+var_8], rax
0x1800227cf  xor     r14d, r14d
0x1800227d2  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800227d6  xorps   xmm0, xmm0
0x1800227d9  mov     qword ptr [rbp+FileTime.dwLowDateTime], r14
0x1800227dd  mov     edi, r14d
0x1800227e0  mov     qword ptr [rbp+FileTime2.dwLowDateTime], r14
0x1800227e4  mov     qword ptr [rbp+FileTime1.dwLowDateTime], r14
0x1800227e8  mov     rbx, r8
0x1800227eb  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800227ef  mov     rsi, rdx
0x1800227f2  call    cs:__imp_GetSystemTime
0x1800227f8  test    rsi, rsi
0x1800227fb  jz      short loc_18002286D
0x1800227fd  test    rbx, rbx
0x180022800  jz      short loc_18002286D
0x180022802  cmp     [rsi], r14w
0x180022806  jbe     short loc_18002286D
0x180022808  cmp     [rbx], r14w
0x18002280c  jbe     short loc_18002286D
0x18002280e  lea     rdx, [rbp+FileTime]; lpFileTime
0x180022812  mov     rcx, rsi; lpSystemTime
0x180022815  call    cs:__imp_SystemTimeToFileTime
0x18002281b  test    eax, eax
0x18002281d  jz      short loc_18002286D
0x18002281f  lea     rdx, [rbp+FileTime2]; lpFileTime
0x180022823  mov     rcx, rbx; lpSystemTime
0x180022826  call    cs:__imp_SystemTimeToFileTime
0x18002282c  test    eax, eax
0x18002282e  jz      short loc_18002286D
0x180022830  lea     rdx, [rbp+FileTime1]; lpFileTime
0x180022834  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180022838  call    cs:__imp_SystemTimeToFileTime
0x18002283e  test    eax, eax
0x180022840  jz      short loc_18002286D
0x180022842  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x180022846  lea     rcx, [rbp+FileTime]; lpFileTime1
0x18002284a  call    cs:__imp_CompareFileTime
0x180022850  lea     ebx, [r14+1]
0x180022854  cmp     eax, ebx
0x180022856  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18002285a  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18002285e  setz    dil
0x180022862  call    cs:__imp_CompareFileTime
0x180022868  cmp     eax, ebx
0x18002286a  cmovz   edi, ebx
0x18002286d  mov     eax, edi
0x18002286f  mov     rcx, [rbp+var_8]
0x180022873  xor     rcx, rsp; StackCookie
0x180022876  call    __security_check_cookie
0x18002287b  lea     r11, [rsp+50h+var_s0]
0x180022880  mov     rbx, [r11+20h]
0x180022884  mov     rsi, [r11+38h]
0x180022888  mov     rsp, r11
0x18002288b  pop     r14
0x18002288d  pop     rdi
0x18002288e  pop     rbp
0x18002288f  retn
```
