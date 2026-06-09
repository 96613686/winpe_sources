# CBackgroundSyncHandler::_InBlockoutPeriod(void)

- ea: `0x180023898`
- end: `0x180023a18`
- name: `?_InBlockoutPeriod@CBackgroundSyncHandler@@AEAAEXZ`
- size: `384`
- prototype: `unsigned __int8 __fastcall(CBackgroundSyncHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023728`

## callees

- `0x180023898`
- `0x1800249c8`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800239a3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800239b5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800239a3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800239b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800238f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800238f2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002392a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180023995`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002392a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180023995`

## pseudocode

```c
bool __fastcall CBackgroundSyncHandler::_InBlockoutPeriod(
        CBackgroundSyncHandler *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // edi
  bool v5; // bl
  __int64 v6; // rsi
  FILETIME FileTime1; // [rsp+20h] [rbp-58h] BYREF
  FILETIME FileTime2; // [rsp+28h] [rbp-50h] BYREF
  struct _FILETIME FileTime; // [rsp+30h] [rbp-48h] BYREF
  SYSTEMTIME v11; // [rsp+40h] [rbp-38h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-28h] BYREF

  v4 = *((_DWORD *)this + 68);
  v5 = 0;
  if ( v4 )
  {
    v6 = *((unsigned int *)this + 69);
    if ( (_DWORD)v6 )
    {
      FileTime = 0;
      FileTime2 = 0;
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      v11 = SystemTime;
      v11.wHour = v4 / 0x64;
      v11.wSecond = 0;
      v11.wMinute = v4 % 0x64;
      if ( SystemTimeToFileTime(&v11, &FileTime) )
      {
        FileTime1 = FileTime;
        if ( *(__int64 *)&FileTime < 0
          || (a3 = 0x7FFFFFFFFFFFFFFFLL,
              *(unsigned __int64 *)&FileTime >> 63 == (unsigned __int64)(*(_QWORD *)&FileTime + 600000000 * v6) > 0x7FFFFFFFFFFFFFFFLL) )
        {
          FileTime2 = (FILETIME)(*(_QWORD *)&FileTime + 600000000 * v6);
          FileTime1 = 0;
          SystemTimeToFileTime(&SystemTime, &FileTime1);
          if ( CompareFileTime(&FileTime1, &FileTime) >= 0 )
            v5 = CompareFileTime(&FileTime1, &FileTime2) < 0;
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
  {
    LOBYTE(a4) = v5 ? 89 : 78;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, a3, a4);
  }
  return v5;
}

```

## disassembly

```asm
0x180023898  push    rbp
0x18002389a  push    rbx
0x18002389b  push    rsi
0x18002389c  push    rdi
0x18002389d  mov     rbp, rsp
0x1800238a0  sub     rsp, 78h
0x1800238a4  mov     rax, cs:__security_cookie
0x1800238ab  xor     rax, rsp
0x1800238ae  mov     [rbp+var_18], rax
0x1800238b2  mov     edi, [rcx+110h]
0x1800238b8  xor     bl, bl
0x1800238ba  test    edi, edi
0x1800238bc  jz      loc_1800239C8
0x1800238c2  mov     esi, [rcx+114h]
0x1800238c8  test    esi, esi
0x1800238ca  jz      loc_1800239C8
0x1800238d0  xorps   xmm0, xmm0
0x1800238d3  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x1800238db  xorps   xmm1, xmm1
0x1800238de  mov     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x1800238e6  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800238ea  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800238ee  movups  xmmword ptr [rbp+var_38.wYear], xmm1
0x1800238f2  call    cs:__imp_GetLocalTime
0x1800238f8  movaps  xmm0, xmmword ptr [rbp+SystemTime.wYear]
0x1800238fc  mov     eax, 51EB851Fh
0x180023901  mul     edi
0x180023903  movdqa  xmmword ptr [rbp+var_38.wYear], xmm0
0x180023908  shr     edx, 5
0x18002390b  movzx   eax, dx
0x18002390e  imul    ecx, eax, 64h ; 'd'
0x180023911  xor     eax, eax
0x180023913  mov     [rbp+var_38.wHour], dx
0x180023917  lea     rdx, [rbp+FileTime]; lpFileTime
0x18002391b  mov     [rbp+var_38.wSecond], ax
0x18002391f  sub     di, cx
0x180023922  lea     rcx, [rbp+var_38]; lpSystemTime
0x180023926  mov     [rbp+var_38.wMinute], di
0x18002392a  call    cs:__imp_SystemTimeToFileTime
0x180023930  test    eax, eax
0x180023932  jz      loc_1800239C8
0x180023938  mov     eax, [rbp+FileTime.dwLowDateTime]
0x18002393b  mov     ecx, [rbp+FileTime.dwHighDateTime]
0x18002393e  imul    rdx, rsi, 23C34600h
0x180023945  mov     [rbp+FileTime1.dwLowDateTime], eax
0x180023948  mov     [rbp+FileTime1.dwHighDateTime], ecx
0x18002394b  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x18002394f  add     rdx, rax
0x180023952  shr     rax, 3Fh
0x180023956  test    eax, eax
0x180023958  jnz     short loc_180023970
0x18002395a  xor     ecx, ecx
0x18002395c  mov     r8, 7FFFFFFFFFFFFFFFh
0x180023966  cmp     rdx, r8
0x180023969  setnbe  cl
0x18002396c  cmp     eax, ecx
0x18002396e  jnz     short loc_1800239C8
0x180023970  mov     [rbp+FileTime2.dwLowDateTime], edx
0x180023973  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180023977  mov     rax, rdx
0x18002397a  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x180023982  sar     rax, 20h
0x180023986  lea     rdx, [rbp+FileTime1]; lpFileTime
0x18002398a  mov     [rbp+FileTime2.dwHighDateTime], eax
0x18002398d  mov     rax, qword ptr [rbp+FileTime2.dwLowDateTime]
0x180023991  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x180023995  call    cs:__imp_SystemTimeToFileTime
0x18002399b  lea     rdx, [rbp+FileTime]; lpFileTime2
0x18002399f  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800239a3  call    cs:__imp_CompareFileTime
0x1800239a9  test    eax, eax
0x1800239ab  js      short loc_1800239C8
0x1800239ad  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800239b1  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800239b5  call    cs:__imp_CompareFileTime
0x1800239bb  movzx   ebx, bl
0x1800239be  mov     ecx, 1
0x1800239c3  test    eax, eax
0x1800239c5  cmovs   ebx, ecx
0x1800239c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239cf  lea     rax, WPP_GLOBAL_Control
0x1800239d6  cmp     rcx, rax
0x1800239d9  jz      short loc_180023A01
0x1800239db  test    dword ptr [rcx+1Ch], 100000h
0x1800239e2  jz      short loc_180023A01
0x1800239e4  mov     rcx, [rcx+10h]
0x1800239e8  mov     dl, bl
0x1800239ea  neg     dl
0x1800239ec  mov     edx, 18h
0x1800239f1  sbb     r9b, r9b
0x1800239f4  and     r9b, 0Bh
0x1800239f8  add     r9b, 4Eh ; 'N'
0x1800239fc  call    WPP_SF_c
0x180023a01  mov     al, bl
0x180023a03  mov     rcx, [rbp+var_18]
0x180023a07  xor     rcx, rsp; StackCookie
0x180023a0a  call    __security_check_cookie
0x180023a0f  add     rsp, 78h
0x180023a13  pop     rdi
0x180023a14  pop     rsi
0x180023a15  pop     rbx
0x180023a16  pop     rbp
0x180023a17  retn
```
