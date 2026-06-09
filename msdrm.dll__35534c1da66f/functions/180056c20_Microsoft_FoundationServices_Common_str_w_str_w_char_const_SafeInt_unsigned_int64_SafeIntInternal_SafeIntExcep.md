# Microsoft::FoundationServices::Common::str_w::str_w(char const *,SafeInt<unsigned __int64,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)

- ea: `0x180056c20`
- end: `0x180056e19`
- name: `??0str_w@Common@FoundationServices@Microsoft@@QEAA@PEBDV?$SafeInt@_KV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005e60a`

## callees

- `0x180001290`
- `0x18000343a`
- `0x180015438`
- `0x1800516b8`
- `0x180053c68`
- `0x180056c20`
- `0x180057340`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056dd2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180056cd1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180056d1c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180056cd1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180056d1c`

## string_xrefs

- `0x180056d77`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\str_t.h`
- `0x180056daf`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\str_t.h`
- `0x180056df0`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\str_t.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LPWSTR *__fastcall Microsoft::FoundationServices::Common::str_w::str_w(LPWSTR *a1, const CHAR *a2, unsigned __int64 a3)
{
  LPWSTR *v5; // r14
  const CHAR *i; // rax
  signed int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  int cchWideChar; // ebx
  void *v11; // rax
  DWORD v13; // eax
  int v14; // eax
  DWORD LastError; // eax
  int v16; // eax
  _BYTE pExceptionObject[1216]; // [rsp+40h] [rbp-4E8h] BYREF

  *a1 = 0;
  v5 = a1 + 1;
  a1[1] = 0;
  if ( a2 )
  {
    if ( a3 > 0x7FFFFFFF )
    {
      v7 = -2147024809;
    }
    else
    {
      for ( i = a2; a3; --a3 )
      {
        if ( !*i )
          break;
        ++i;
      }
      v7 = a3 == 0 ? 0x80070057 : 0;
    }
    if ( v7 < 0 )
    {
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\str_t.h",
        0x39u,
        L"0 == psz || SUCCEEDED(StringCchLengthA(psz, cchMaxLength, 0))",
        -2147024809);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    v8 = MultiByteToWideChar(0, 0, a2, -1, 0, 0);
    cchWideChar = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v16 = HR_FROM_WIN32(LastError);
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\str_t.h",
        0x3Eu,
        L"0 != cch",
        v16);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    if ( v8 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v9);
    v11 = operator new[](saturated_mul(v8, 2u));
    Microsoft::FoundationServices::Common::auto_array<unsigned short>::reset(v5, v11);
    if ( !MultiByteToWideChar(0, 0, a2, -1, *v5, cchWideChar) )
    {
      v13 = GetLastError();
      v14 = HR_FROM_WIN32(v13);
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\str_t.h",
        0x40u,
        L"0 != MultiByteToWideChar(CP_ACP, 0, psz, -1, m_wsz, cch)",
        v14);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    *a1 = *v5;
  }
  return a1;
}

```

## disassembly

```asm
0x180056c20  mov     rax, rsp
0x180056c23  push    rdi
0x180056c24  push    r14
0x180056c26  push    r15
0x180056c28  sub     rsp, 510h
0x180056c2f  mov     [rsp+528h+var_4F8], 0FFFFFFFFFFFFFFFEh
0x180056c38  mov     [rax+18h], rbx
0x180056c3c  mov     [rax+20h], rsi
0x180056c40  mov     rax, cs:__security_cookie
0x180056c47  xor     rax, rsp
0x180056c4a  mov     [rsp+528h+var_28], rax
0x180056c52  mov     rsi, rdx
0x180056c55  mov     rdi, rcx
0x180056c58  mov     [rsp+528h+var_4F0], rcx
0x180056c5d  mov     qword ptr [rcx], 0
0x180056c64  lea     r14, [rcx+8]
0x180056c68  mov     qword ptr [r14], 0
0x180056c6f  test    rdx, rdx
0x180056c72  jz      loc_180056D2C
0x180056c78  cmp     r8, 7FFFFFFFh
0x180056c7f  ja      short loc_180056CA5
0x180056c81  mov     rax, rdx
0x180056c84  test    r8, r8
0x180056c87  jz      short loc_180056C97
0x180056c89  cmp     byte ptr [rax], 0
0x180056c8c  jz      short loc_180056C97
0x180056c8e  inc     rax
0x180056c91  sub     r8, 1
0x180056c95  jnz     short loc_180056C89
0x180056c97  neg     r8
0x180056c9a  sbb     eax, eax
0x180056c9c  not     eax
0x180056c9e  and     eax, 80070057h
0x180056ca3  jmp     short loc_180056CAA
0x180056ca5  mov     eax, 80070057h
0x180056caa  test    eax, eax
0x180056cac  js      loc_180056D9A
0x180056cb2  mov     [rsp+528h+cchWideChar], 0; cchWideChar
0x180056cba  mov     [rsp+528h+lpWideCharStr], 0; lpWideCharStr
0x180056cc3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180056cc7  mov     r9d, r15d; cbMultiByte
0x180056cca  mov     r8, rsi; lpMultiByteStr
0x180056ccd  xor     edx, edx; dwFlags
0x180056ccf  xor     ecx, ecx; CodePage
0x180056cd1  call    cs:__imp_MultiByteToWideChar
0x180056cd7  movsxd  rbx, eax
0x180056cda  test    eax, eax
0x180056cdc  jz      loc_180056DD2
0x180056ce2  js      loc_180056E13
0x180056ce8  lea     eax, [r15+3]
0x180056cec  mul     rbx
0x180056cef  cmovb   rax, r15
0x180056cf3  mov     rcx, rax; unsigned __int64
0x180056cf6  call    ??_U@YAPEAX_K@Z
0x180056cfb  mov     rdx, rax
0x180056cfe  mov     rcx, r14
0x180056d01  call    ?reset@?$auto_array@G@Common@FoundationServices@Microsoft@@QEAAXPEAG@Z
0x180056d06  mov     [rsp+528h+cchWideChar], ebx; cchWideChar
0x180056d0a  mov     rax, [r14]
0x180056d0d  mov     [rsp+528h+lpWideCharStr], rax; lpWideCharStr
0x180056d12  mov     r9d, r15d; cbMultiByte
0x180056d15  mov     r8, rsi; lpMultiByteStr
0x180056d18  xor     edx, edx; dwFlags
0x180056d1a  xor     ecx, ecx; CodePage
0x180056d1c  call    cs:__imp_MultiByteToWideChar
0x180056d22  test    eax, eax
0x180056d24  jz      short loc_180056D58
0x180056d26  mov     rcx, [r14]
0x180056d29  mov     [rdi], rcx
0x180056d2c  mov     rax, rdi
0x180056d2f  mov     rcx, [rsp+528h+var_28]
0x180056d37  xor     rcx, rsp; StackCookie
0x180056d3a  call    __security_check_cookie
0x180056d3f  lea     r11, [rsp+528h+var_18]
0x180056d47  mov     rbx, [r11+30h]
0x180056d4b  mov     rsi, [r11+38h]
0x180056d4f  mov     rsp, r11
0x180056d52  pop     r15
0x180056d54  pop     r14
0x180056d56  pop     rdi
0x180056d57  retn
0x180056d58  call    cs:__imp_GetLastError
0x180056d5e  nop
0x180056d5f  mov     ecx, eax; unsigned int
0x180056d61  call    ?HR_FROM_WIN32@@YAJK@Z
0x180056d66  mov     dword ptr [rsp+528h+lpWideCharStr], eax; int
0x180056d6a  lea     r9, a0Multibytetowi
0x180056d71  mov     r8d, 40h ; '@'; unsigned int
0x180056d77  lea     rdx, aDsSecurityRmSr_8
0x180056d7e  lea     rcx, [rsp+528h+pExceptionObject]; this
0x180056d83  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z
0x180056d88  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180056d8f  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x180056d94  call    _CxxThrowException_0
0x180056d9a  mov     dword ptr [rsp+528h+lpWideCharStr], 80070057h; int
0x180056da2  lea     r9, a0PszSucceededS
0x180056da9  mov     r8d, 39h ; '9'; unsigned int
0x180056daf  lea     rdx, aDsSecurityRmSr_8
0x180056db6  lea     rcx, [rsp+528h+pExceptionObject]; this
0x180056dbb  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z
0x180056dc0  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180056dc7  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x180056dcc  call    _CxxThrowException_0
0x180056dd2  call    cs:__imp_GetLastError
0x180056dd8  mov     ecx, eax; unsigned int
0x180056dda  call    ?HR_FROM_WIN32@@YAJK@Z
0x180056ddf  mov     dword ptr [rsp+528h+lpWideCharStr], eax; int
0x180056de3  lea     r9, a0Cch
0x180056dea  mov     r8d, 3Eh ; '>'; unsigned int
0x180056df0  lea     rdx, aDsSecurityRmSr_8
0x180056df7  lea     rcx, [rsp+528h+pExceptionObject]; this
0x180056dfc  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z
0x180056e01  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180056e08  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x180056e0d  call    _CxxThrowException_0
0x180056e13  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ
```
