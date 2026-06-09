# TextLogGenerateBackupLogFileName

- ea: `0x180004ec4`
- end: `0x18000500f`
- name: `TextLogGenerateBackupLogFileName`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005430`
- `0x1800054d4`

## callees

- `0x180004560`
- `0x180004ec4`
- `0x18000a1a0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004f4e`
- `msvcrt!wcsrchr` at `0x180004f4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004fd9`
- `KERNEL32!GetLocalTime` at `0x180004f68`
- `KERNEL32!GetLocalTime` at `0x180004f68`

## pseudocode

```c
_BOOL8 __fastcall TextLogGenerateBackupLogFileName(wchar_t *a1, wchar_t *a2)
{
  wchar_t *v2; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  wchar_t *v7; // rcx
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  DWORD v10; // esi
  int wYear; // [rsp+20h] [rbp-288h]
  int wMonth; // [rsp+28h] [rbp-280h]
  int wDay; // [rsp+30h] [rbp-278h]
  int wHour; // [rsp+38h] [rbp-270h]
  int wMinute; // [rsp+40h] [rbp-268h]
  int wSecond; // [rsp+48h] [rbp-260h]
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-248h] BYREF
  wchar_t Str[264]; // [rsp+70h] [rbp-238h] BYREF

  v2 = Str;
  SystemTime = 0;
  v5 = 2147483646;
  v6 = 260;
  do
  {
    if ( !v5 )
      break;
    if ( !*a1 )
      break;
    *v2++ = *a1++;
    --v5;
    --v6;
  }
  while ( v6 );
  v7 = v2 - 1;
  if ( v6 )
    v7 = v2;
  *v7 = 0;
  if ( !v6 )
    goto LABEL_10;
  v8 = wcsrchr(Str, 0x2Eu);
  v9 = v8;
  if ( !v8 )
    goto LABEL_10;
  *v8 = 0;
  v10 = 0;
  GetLocalTime(&SystemTime);
  wSecond = SystemTime.wSecond;
  wMinute = SystemTime.wMinute;
  wHour = SystemTime.wHour;
  wDay = SystemTime.wDay;
  wMonth = SystemTime.wMonth;
  wYear = SystemTime.wYear;
  if ( StringCchPrintfW(
         a2,
         0x104u,
         L"%s.%04d%02d%02d_%02d%02d%02d.%s",
         Str,
         wYear,
         wMonth,
         wDay,
         wHour,
         wMinute,
         wSecond,
         v9 + 1) < 0 )
LABEL_10:
    v10 = 13;
  SetLastError(v10);
  return v10 == 0;
}

```

## disassembly

```asm
0x180004ec4  mov     [rsp+arg_0], rbx
0x180004ec9  mov     [rsp+arg_10], rbp
0x180004ece  push    rsi
0x180004ecf  push    rdi
0x180004ed0  push    r14
0x180004ed2  sub     rsp, 290h
0x180004ed9  mov     rax, cs:__security_cookie
0x180004ee0  xor     rax, rsp
0x180004ee3  mov     [rsp+2A8h+var_28], rax
0x180004eeb  xorps   xmm0, xmm0
0x180004eee  lea     rax, [rsp+2A8h+Str]
0x180004ef3  mov     rbp, rdx
0x180004ef6  mov     r8, rcx
0x180004ef9  movups  xmmword ptr [rsp+2A8h+SystemTime.wYear], xmm0
0x180004efe  mov     ecx, 7FFFFFFEh
0x180004f03  mov     edx, 104h
0x180004f08  xor     r14d, r14d
0x180004f0b  test    rcx, rcx
0x180004f0e  jz      short loc_180004F2F
0x180004f10  movzx   r9d, word ptr [r8]
0x180004f14  test    r9w, r9w
0x180004f18  jz      short loc_180004F2F
0x180004f1a  mov     [rax], r9w
0x180004f1e  add     r8, 2
0x180004f22  add     rax, 2
0x180004f26  dec     rcx
0x180004f29  sub     rdx, 1
0x180004f2d  jnz     short loc_180004F0B
0x180004f2f  test    rdx, rdx
0x180004f32  lea     rcx, [rax-2]
0x180004f36  cmovnz  rcx, rax
0x180004f3a  mov     [rcx], r14w
0x180004f3e  jz      loc_180004FD2
0x180004f44  mov     edx, 2Eh ; '.'; Ch
0x180004f49  lea     rcx, [rsp+2A8h+Str]; Str
0x180004f4e  call    cs:__imp_wcsrchr
0x180004f54  mov     rbx, rax
0x180004f57  test    rax, rax
0x180004f5a  jz      short loc_180004FD2
0x180004f5c  lea     rcx, [rsp+2A8h+SystemTime]; lpSystemTime
0x180004f61  mov     [rax], r14w
0x180004f65  mov     esi, r14d
0x180004f68  call    cs:__imp_GetLocalTime
0x180004f6e  movzx   r8d, [rsp+2A8h+SystemTime.wSecond]
0x180004f74  lea     rax, [rbx+2]
0x180004f78  movzx   r9d, [rsp+2A8h+SystemTime.wMinute]
0x180004f7e  mov     edx, 104h; cchDest
0x180004f83  movzx   r10d, [rsp+2A8h+SystemTime.wHour]
0x180004f89  mov     rcx, rbp; pszDest
0x180004f8c  movzx   r11d, [rsp+2A8h+SystemTime.wDay]
0x180004f92  movzx   ebx, [rsp+2A8h+SystemTime.wMonth]
0x180004f97  movzx   edi, [rsp+2A8h+SystemTime.wYear]
0x180004f9c  mov     [rsp+2A8h+var_258], rax
0x180004fa1  mov     [rsp+2A8h+var_260], r8d
0x180004fa6  lea     r8, aS04d02d02d02d0; "%s.%04d%02d%02d_%02d%02d%02d.%s"
0x180004fad  mov     [rsp+2A8h+var_268], r9d
0x180004fb2  lea     r9, [rsp+2A8h+Str]
0x180004fb7  mov     [rsp+2A8h+var_270], r10d
0x180004fbc  mov     [rsp+2A8h+var_278], r11d
0x180004fc1  mov     [rsp+2A8h+var_280], ebx
0x180004fc5  mov     [rsp+2A8h+var_288], edi
0x180004fc9  call    StringCchPrintfW
0x180004fce  test    eax, eax
0x180004fd0  jns     short loc_180004FD7
0x180004fd2  mov     esi, 0Dh
0x180004fd7  mov     ecx, esi; dwErrCode
0x180004fd9  call    cs:__imp_SetLastError
0x180004fdf  test    esi, esi
0x180004fe1  mov     eax, r14d
0x180004fe4  setz    al
0x180004fe7  mov     rcx, [rsp+2A8h+var_28]
0x180004fef  xor     rcx, rsp; StackCookie
0x180004ff2  call    __security_check_cookie
0x180004ff7  lea     r11, [rsp+2A8h+var_18]
0x180004fff  mov     rbx, [r11+20h]
0x180005003  mov     rbp, [r11+30h]
0x180005007  mov     rsp, r11
0x18000500a  pop     r14
0x18000500c  pop     rdi
0x18000500d  pop     rsi
0x18000500e  retn
```
