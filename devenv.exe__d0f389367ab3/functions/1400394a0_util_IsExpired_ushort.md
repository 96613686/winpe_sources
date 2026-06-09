# util_IsExpired(ushort *)

- ea: `0x1400394a0`
- end: `0x1400395c3`
- name: `?util_IsExpired@@YAHPEAG@Z`
- size: `291`
- prototype: `__int64 __fastcall(wchar_t *String)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140033ae0`

## callees

- `0x140001020`
- `0x14001fa6c`
- `0x1400394a0`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x140039573`
- `KERNEL32!SystemTimeToFileTime` at `0x140039581`
- `KERNEL32!SystemTimeToFileTime` at `0x140039573`
- `KERNEL32!SystemTimeToFileTime` at `0x140039581`
- `KERNEL32!GetSystemTime` at `0x140039565`
- `KERNEL32!GetSystemTime` at `0x140039565`
- `KERNEL32!CompareFileTime` at `0x14003958f`
- `KERNEL32!CompareFileTime` at `0x14003958f`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x140039500`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x140039537`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x140039557`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x140039500`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x140039537`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x140039557`

## pseudocode

```c
__int64 __fastcall util_IsExpired(wchar_t *String)
{
  wchar_t *v2; // rax
  wchar_t *v3; // rdi
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  SYSTEMTIME v7; // [rsp+20h] [rbp-40h] BYREF
  FILETIME FileTime2; // [rsp+30h] [rbp-30h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-20h] BYREF

  if ( !String )
    return 1;
  v7 = 0;
  v2 = wcschr_0(String, 0x2Fu);
  v3 = v2;
  if ( !v2 )
    return 1;
  *v2 = 0;
  v7.wMonth = _wtoi(String);
  *v3 = 47;
  if ( (unsigned __int16)(v7.wMonth - 1) > 0xBu )
    return 1;
  v4 = wcschr_0(v3 + 1, 0x2Fu);
  v5 = v4;
  if ( !v4 )
    return 1;
  *v4 = 0;
  v7.wDay = _wtoi(v3 + 1);
  *v5 = 47;
  if ( (unsigned __int16)(v7.wDay - 1) > 0x1Eu )
    return 1;
  v7.wYear = _wtoi(v5 + 1);
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&v7, &FileTime);
  SystemTimeToFileTime(&SystemTime, &FileTime2);
  return (unsigned int)CompareFileTime(&FileTime, &FileTime2) >> 31;
}

```

## disassembly

```asm
0x1400394a0  mov     [rsp-18h+arg_8], rbx
0x1400394a5  mov     [rsp-18h+arg_10], rsi
0x1400394aa  mov     [rsp-18h+arg_18], rdi
0x1400394af  push    rbp
0x1400394b0  push    r14
0x1400394b2  push    r15
0x1400394b4  mov     rbp, rsp
0x1400394b7  sub     rsp, 60h
0x1400394bb  mov     rax, cs:__security_cookie
0x1400394c2  xor     rax, rsp
0x1400394c5  mov     [rbp+var_10], rax
0x1400394c9  xor     esi, esi
0x1400394cb  mov     rbx, rcx
0x1400394ce  lea     r14d, [rsi+1]
0x1400394d2  test    rcx, rcx
0x1400394d5  jz      loc_14003959A
0x1400394db  xorps   xmm0, xmm0
0x1400394de  lea     r15d, [rsi+2Fh]
0x1400394e2  mov     edx, r15d; Ch
0x1400394e5  movups  xmmword ptr [rbp+var_40.wYear], xmm0
0x1400394e9  call    wcschr_0
0x1400394ee  mov     rdi, rax
0x1400394f1  test    rax, rax
0x1400394f4  jz      loc_14003959A
0x1400394fa  mov     rcx, rbx; String
0x1400394fd  mov     [rax], si
0x140039500  call    cs:__imp__wtoi
0x140039506  mov     [rbp+var_40.wMonth], ax
0x14003950a  mov     [rdi], r15w
0x14003950e  movzx   eax, [rbp+var_40.wMonth]
0x140039512  sub     ax, r14w
0x140039516  cmp     ax, 0Bh
0x14003951a  ja      short loc_14003959A
0x14003951c  mov     edx, r15d; Ch
0x14003951f  lea     rcx, [rdi+2]; Str
0x140039523  call    wcschr_0
0x140039528  mov     rbx, rax
0x14003952b  test    rax, rax
0x14003952e  jz      short loc_14003959A
0x140039530  lea     rcx, [rdi+2]; String
0x140039534  mov     [rax], si
0x140039537  call    cs:__imp__wtoi
0x14003953d  mov     [rbp+var_40.wDay], ax
0x140039541  mov     [rbx], r15w
0x140039545  movzx   eax, [rbp+var_40.wDay]
0x140039549  sub     ax, r14w
0x14003954d  cmp     ax, 1Eh
0x140039551  ja      short loc_14003959A
0x140039553  lea     rcx, [rbx+2]; String
0x140039557  call    cs:__imp__wtoi
0x14003955d  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x140039561  mov     [rbp+var_40.wYear], ax
0x140039565  call    cs:__imp_GetSystemTime
0x14003956b  lea     rdx, [rbp+FileTime]; lpFileTime
0x14003956f  lea     rcx, [rbp+var_40]; lpSystemTime
0x140039573  call    cs:__imp_SystemTimeToFileTime
0x140039579  lea     rdx, [rbp+FileTime2]; lpFileTime
0x14003957d  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x140039581  call    cs:__imp_SystemTimeToFileTime
0x140039587  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x14003958b  lea     rcx, [rbp+FileTime]; lpFileTime1
0x14003958f  call    cs:__imp_CompareFileTime
0x140039595  shr     eax, 1Fh
0x140039598  jmp     short loc_14003959D
0x14003959a  mov     eax, r14d
0x14003959d  mov     rcx, [rbp+var_10]
0x1400395a1  xor     rcx, rsp; StackCookie
0x1400395a4  call    __security_check_cookie
0x1400395a9  lea     r11, [rsp+60h+var_s0]
0x1400395ae  mov     rbx, [r11+28h]
0x1400395b2  mov     rsi, [r11+30h]
0x1400395b6  mov     rdi, [r11+38h]
0x1400395ba  mov     rsp, r11
0x1400395bd  pop     r15
0x1400395bf  pop     r14
0x1400395c1  pop     rbp
0x1400395c2  retn
```
