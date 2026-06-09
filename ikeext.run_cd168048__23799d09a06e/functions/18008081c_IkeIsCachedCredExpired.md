# IkeIsCachedCredExpired

- ea: `0x18008081c`
- end: `0x1800808af`
- name: `IkeIsCachedCredExpired`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180083a0c`

## callees

- `0x180050850`
- `0x18008081c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008084b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008084b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180080885`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180080885`
- `CRYPT32!CertVerifyTimeValidity` at `0x180080863`
- `CRYPT32!CertVerifyTimeValidity` at `0x180080863`

## pseudocode

```c
_BOOL8 __fastcall IkeIsCachedCredExpired(__int64 a1)
{
  struct _CERT_INFO *v2; // rdx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-28h] BYREF
  FILETIME FileTime1; // [rsp+28h] [rbp-20h] BYREF

  SystemTimeAsFileTime = 0;
  FileTime1 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v2 = *(struct _CERT_INFO **)(*(_QWORD *)(a1 + 64) + 24LL);
  if ( !v2 || CertVerifyTimeValidity(&SystemTimeAsFileTime, v2) )
    return 1;
  FileTime1 = *(FILETIME *)(a1 + 88);
  return CompareFileTime(&FileTime1, &SystemTimeAsFileTime) != 1;
}

```

## disassembly

```asm
0x18008081c  push    rbx
0x18008081e  sub     rsp, 40h
0x180080822  mov     rax, cs:__security_cookie
0x180080829  xor     rax, rsp
0x18008082c  mov     [rsp+48h+var_18], rax
0x180080831  mov     rbx, rcx
0x180080834  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008083d  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180080842  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], 0
0x18008084b  call    cs:__imp_GetSystemTimeAsFileTime
0x180080851  mov     rax, [rbx+40h]
0x180080855  mov     rdx, [rax+18h]; pCertInfo
0x180080859  test    rdx, rdx
0x18008085c  jz      short loc_180080897
0x18008085e  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; pTimeToVerify
0x180080863  call    cs:__imp_CertVerifyTimeValidity
0x180080869  test    eax, eax
0x18008086b  jnz     short loc_180080897
0x18008086d  mov     eax, [rbx+5Ch]
0x180080870  lea     rdx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime2
0x180080875  mov     [rsp+48h+FileTime1.dwHighDateTime], eax
0x180080879  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x18008087e  mov     eax, [rbx+58h]
0x180080881  mov     [rsp+48h+FileTime1.dwLowDateTime], eax
0x180080885  call    cs:__imp_CompareFileTime
0x18008088b  xor     ecx, ecx
0x18008088d  cmp     eax, 1
0x180080890  setnz   cl
0x180080893  mov     eax, ecx
0x180080895  jmp     short loc_18008089C
0x180080897  mov     eax, 1
0x18008089c  mov     rcx, [rsp+48h+var_18]
0x1800808a1  xor     rcx, rsp; StackCookie
0x1800808a4  call    __security_check_cookie
0x1800808a9  add     rsp, 40h
0x1800808ad  pop     rbx
0x1800808ae  retn
```
