# win_musl::production::MXWriter::CoCreate(void)

- ea: `0x18006fd28`
- end: `0x18006fe3b`
- name: `?CoCreate@MXWriter@production@win_musl@@SA?AV123@XZ`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002f9a8`

## callees

- `0x180012468`
- `0x18002db70`
- `0x18006fd28`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fd97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fd97`

## string_xrefs

- `0x18006fddf`: `Call to ::CoCreateInstance failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID *__fastcall win_musl::production::MXWriter::CoCreate(LPVOID *ppv)
{
  HRESULT Instance; // edi
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-4B8h] BYREF
  wchar_t v5[512]; // [rsp+100h] [rbp-418h] BYREF

  *ppv = 0;
  *ppv = 0;
  *ppv = 0;
  Instance = CoCreateInstance(
               &GUID_88d96a0f_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_4d7ff4ba_1565_4ea8_94e1_6e724a46f98d,
               ppv);
  if ( Instance < 0 )
  {
    memset_0(v5, 0, sizeof(v5));
    StringCchPrintfW(v5, 0x200u, L"Call to ::CoCreateInstance failed with HResult 0x%X.", (unsigned int)Instance);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x149u,
      Instance,
      (struct win_musl::TStringEllipseBase *)v5);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return ppv;
}

```

## disassembly

```asm
0x18006fd28  mov     rax, rsp
0x18006fd2b  push    rdi
0x18006fd2c  sub     rsp, 510h
0x18006fd33  mov     [rsp+518h+var_4D0], 0FFFFFFFFFFFFFFFEh
0x18006fd3c  mov     [rax+10h], rbx
0x18006fd40  mov     rax, cs:__security_cookie
0x18006fd47  xor     rax, rsp
0x18006fd4a  mov     [rsp+518h+var_18], rax
0x18006fd52  mov     rbx, rcx
0x18006fd55  mov     [rsp+518h+var_4C8], rcx
0x18006fd5a  mov     [rsp+518h+var_4D8], 0
0x18006fd62  mov     qword ptr [rcx], 0
0x18006fd69  mov     r8d, 1; dwClsContext
0x18006fd6f  mov     [rsp+518h+var_4D8], r8d
0x18006fd74  mov     qword ptr [rcx], 0
0x18006fd7b  mov     qword ptr [rcx], 0
0x18006fd82  mov     [rsp+518h+ppv], rcx; ppv
0x18006fd87  lea     r9, _GUID_4d7ff4ba_1565_4ea8_94e1_6e724a46f98d; riid
0x18006fd8e  xor     edx, edx; pUnkOuter
0x18006fd90  lea     rcx, _GUID_88d96a0f_f192_11d4_a65f_0040963251e5; rclsid
0x18006fd97  call    cs:__imp_CoCreateInstance
0x18006fd9d  mov     edi, eax
0x18006fd9f  test    eax, eax
0x18006fda1  js      short loc_18006FDC7
0x18006fda3  mov     rax, rbx
0x18006fda6  mov     rcx, [rsp+518h+var_18]
0x18006fdae  xor     rcx, rsp; StackCookie
0x18006fdb1  call    __security_check_cookie
0x18006fdb6  mov     rbx, [rsp+518h+arg_8]
0x18006fdbe  add     rsp, 510h
0x18006fdc5  pop     rdi
0x18006fdc6  retn
0x18006fdc7  xor     edx, edx; Val
0x18006fdc9  mov     r8d, 400h; Size
0x18006fdcf  lea     rcx, [rsp+518h+var_418]; void *
0x18006fdd7  call    memset_0
0x18006fddc  mov     r9d, edi
0x18006fddf  lea     r8, aCallToCocreate_0; "Call to ::CoCreateInstance failed with "...
0x18006fde6  mov     edx, 200h; unsigned __int64
0x18006fdeb  lea     rcx, [rsp+518h+var_418]; wchar_t *
0x18006fdf3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18006fdf8  lea     rax, [rsp+518h+var_418]
0x18006fe00  mov     [rsp+518h+var_4E8], rax; struct win_musl::TStringEllipseBase *
0x18006fe05  mov     [rsp+518h+var_4F0], edi; unsigned int
0x18006fe09  mov     dword ptr [rsp+518h+ppv], 149h; unsigned int
0x18006fe11  lea     r9, word_180139126
0x18006fe18  lea     r8, aNoFilename; "(no filename)"
0x18006fe1f  lea     rcx, [rsp+518h+pExceptionObject]; this
0x18006fe24  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006fe29  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006fe30  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x18006fe35  call    _CxxThrowException_0
```
