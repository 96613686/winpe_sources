# CSPrintAssert(char const *,char const *,ulong,char const *)

- ea: `0x180028260`
- end: `0x180028357`
- name: `?CSPrintAssert@@YAXPEBD0K0@Z`
- size: `247`
- prototype: `void __fastcall(const char *, const char *Str1, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180007da0`
- `0x18000e9b0`
- `0x180028530`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180028299`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180028299`

## string_xrefs

- `0x1800282eb`: `\n*** Certificate Services Assertion failed: %hs %hs\n*** Source File: %hs, line %ld:<%i/%i/%i, %i:%02i:%02i>\n\n`

## pseudocode

```c
void __fastcall CSPrintAssert(const char *a1, const char *Str1, unsigned int a3, const char *a4)
{
  unsigned __int64 v8; // r8
  const char *v9; // rax
  const char *v10; // r8
  const char *v11; // rdi
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-258h] BYREF
  char v13[528]; // [rsp+70h] [rbp-248h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v9 = csTrimPath(Str1, v13, v8);
  v10 = (const char *)&dword_180061D54;
  v11 = v9;
  if ( a4 )
    v10 = a4;
  DbgPrintf(
    2u,
    "\n*** Certificate Services Assertion failed: %hs %hs\n*** Source File: %hs, line %ld:<%i/%i/%i, %i:%02i:%02i>\n\n",
    v10,
    a1,
    v9,
    a3,
    SystemTime.wYear,
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond);
  CSPrintCallback(&SystemTime, a1, L"CSASSERT", v11, a3, -2147024228);
}

```

## disassembly

```asm
0x180028260  push    rbx
0x180028262  push    rbp
0x180028263  push    rsi
0x180028264  push    rdi
0x180028265  push    r14
0x180028267  sub     rsp, 290h
0x18002826e  mov     rax, cs:__security_cookie
0x180028275  xor     rax, rsp
0x180028278  mov     [rsp+2B8h+var_38], rax
0x180028280  mov     r14, rcx
0x180028283  xorps   xmm0, xmm0
0x180028286  lea     rcx, [rsp+2B8h+SystemTime]; lpSystemTime
0x18002828b  mov     rsi, r9
0x18002828e  movups  xmmword ptr [rsp+2B8h+SystemTime.wYear], xmm0
0x180028293  mov     ebp, r8d
0x180028296  mov     rbx, rdx
0x180028299  call    cs:__imp_GetLocalTime
0x18002829f  lea     rdx, [rsp+2B8h+var_248]; char *
0x1800282a4  mov     rcx, rbx; Str1
0x1800282a7  call    ?csTrimPath@@YAPEBDPEBDPEAD_K@Z; csTrimPath(char const *,char *,unsigned __int64)
0x1800282ac  movzx   ecx, [rsp+2B8h+SystemTime.wSecond]
0x1800282b1  lea     r8, dword_180061D54
0x1800282b8  movzx   edx, [rsp+2B8h+SystemTime.wMinute]
0x1800282bd  test    rsi, rsi
0x1800282c0  movzx   r9d, [rsp+2B8h+SystemTime.wHour]
0x1800282c6  mov     rdi, rax
0x1800282c9  movzx   r10d, [rsp+2B8h+SystemTime.wDay]
0x1800282cf  cmovnz  r8, rsi
0x1800282d3  movzx   r11d, [rsp+2B8h+SystemTime.wMonth]
0x1800282d9  movzx   ebx, [rsp+2B8h+SystemTime.wYear]
0x1800282de  mov     [rsp+2B8h+var_260], ecx
0x1800282e2  mov     ecx, 2; unsigned int
0x1800282e7  mov     [rsp+2B8h+var_268], edx
0x1800282eb  lea     rdx, aCertificateSer; "\n*** Certificate Services Assertion fa"...
0x1800282f2  mov     [rsp+2B8h+var_270], r9d
0x1800282f7  mov     r9, r14
0x1800282fa  mov     [rsp+2B8h+var_278], r10d
0x1800282ff  mov     [rsp+2B8h+var_280], r11d
0x180028304  mov     [rsp+2B8h+var_288], ebx
0x180028308  mov     [rsp+2B8h+var_290], ebp
0x18002830c  mov     qword ptr [rsp+2B8h+var_298], rax
0x180028311  call    ?DbgPrintf@@YAHKPEBDZZ; DbgPrintf(ulong,char const *,...)
0x180028316  mov     r9, rdi; char *
0x180028319  mov     [rsp+2B8h+var_290], 8007029Ch; int
0x180028321  lea     r8, aCsassert; "CSASSERT"
0x180028328  mov     [rsp+2B8h+var_298], ebp; unsigned int
0x18002832c  mov     rdx, r14; char *
0x18002832f  lea     rcx, [rsp+2B8h+SystemTime]; struct _SYSTEMTIME *
0x180028334  call    ?CSPrintCallback@@YAXPEBU_SYSTEMTIME@@PEBDPEBG1KJ@Z; CSPrintCallback(_SYSTEMTIME const *,char const *,ushort const *,char const *,ulong,long)
0x180028339  mov     rcx, [rsp+2B8h+var_38]
0x180028341  xor     rcx, rsp; StackCookie
0x180028344  call    __security_check_cookie
0x180028349  add     rsp, 290h
0x180028350  pop     r14
0x180028352  pop     rdi
0x180028353  pop     rsi
0x180028354  pop     rbp
0x180028355  pop     rbx
0x180028356  retn
```
