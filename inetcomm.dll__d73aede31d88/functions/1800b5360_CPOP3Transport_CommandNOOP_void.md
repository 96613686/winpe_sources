# CPOP3Transport::CommandNOOP(void)

- ea: `0x1800b5360`
- end: `0x1800b548f`
- name: `?CommandNOOP@CPOP3Transport@@UEAAJXZ`
- size: `303`
- prototype: `__int64 __fastcall(CPOP3Transport *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180028848`
- `0x1800b5360`
- `0x1800c43f0`
- `0x1800c4624`
- `0x1800cca00`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x1800b53b8`
- `KERNEL32!SystemTimeToFileTime` at `0x1800b53b8`
- `KERNEL32!GetSystemTime` at `0x1800b53a8`
- `KERNEL32!GetSystemTime` at `0x1800b53a8`
- `KERNEL32!LeaveCriticalSection` at `0x1800b544e`
- `KERNEL32!LeaveCriticalSection` at `0x1800b5465`
- `KERNEL32!LeaveCriticalSection` at `0x1800b544e`
- `KERNEL32!LeaveCriticalSection` at `0x1800b5465`
- `KERNEL32!EnterCriticalSection` at `0x1800b539d`
- `KERNEL32!EnterCriticalSection` at `0x1800b541a`
- `KERNEL32!EnterCriticalSection` at `0x1800b539d`
- `KERNEL32!EnterCriticalSection` at `0x1800b541a`
- `KERNEL32!CompareFileTime` at `0x1800b53ca`
- `KERNEL32!CompareFileTime` at `0x1800b53ca`

## pseudocode

```c
__int64 __fastcall CPOP3Transport::CommandNOOP(CPOP3Transport *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  int v3; // ebx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-48h] BYREF
  __int64 v6; // [rsp+28h] [rbp-40h]
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-38h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2736);
  v3 = 0;
  FileTime = 0;
  SystemTime = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2736));
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( CompareFileTime(&FileTime, &FileTime2) >= 0 )
  {
    v6 = *(_QWORD *)&FileTime + 600000000LL;
    FileTime2 = (FILETIME)(*(_QWORD *)&FileTime + 600000000LL);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2736));
    v3 = CIxpBase::HrEnterBusy((CPOP3Transport *)((char *)this + 8));
    if ( v3 >= 0 )
      v3 = CIxpBase::HrSendLine((CPOP3Transport *)((char *)this + 8), "NOOP\r\n");
    if ( v3 < 0 )
      CIxpBase::LeaveBusy((CPOP3Transport *)((char *)this + 8));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2736));
    if ( v3 >= 0 )
      *((_DWORD *)this + 824) = 12;
  }
  LeaveCriticalSection(v1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800b5360  mov     [rsp+arg_8], rbx
0x1800b5365  mov     [rsp+arg_10], rbp
0x1800b536a  push    rsi
0x1800b536b  push    rdi
0x1800b536c  push    r14
0x1800b536e  sub     rsp, 50h
0x1800b5372  mov     rax, cs:__security_cookie
0x1800b5379  xor     rax, rsp
0x1800b537c  mov     [rsp+68h+var_28], rax
0x1800b5381  lea     rbp, [rcx+0AB0h]
0x1800b5388  mov     rsi, rcx
0x1800b538b  xorps   xmm0, xmm0
0x1800b538e  xor     ebx, ebx
0x1800b5390  mov     rcx, rbp; lpCriticalSection
0x1800b5393  mov     qword ptr [rsp+68h+FileTime.dwLowDateTime], rbx
0x1800b5398  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x1800b539d  call    cs:__imp_EnterCriticalSection
0x1800b53a3  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x1800b53a8  call    cs:__imp_GetSystemTime
0x1800b53ae  lea     rdx, [rsp+68h+FileTime]; lpFileTime
0x1800b53b3  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x1800b53b8  call    cs:__imp_SystemTimeToFileTime
0x1800b53be  lea     rdx, FileTime2; lpFileTime2
0x1800b53c5  lea     rcx, [rsp+68h+FileTime]; lpFileTime1
0x1800b53ca  call    cs:__imp_CompareFileTime
0x1800b53d0  test    eax, eax
0x1800b53d2  js      loc_1800B5462
0x1800b53d8  mov     eax, [rsp+68h+FileTime.dwHighDateTime]
0x1800b53dc  lea     rdi, [rsi+8]
0x1800b53e0  mov     dword ptr [rsp+68h+var_40+4], eax
0x1800b53e4  lea     r14, [rdi+0AA8h]
0x1800b53eb  mov     eax, [rsp+68h+FileTime.dwLowDateTime]
0x1800b53ef  mov     rcx, r14; lpCriticalSection
0x1800b53f2  mov     dword ptr [rsp+68h+var_40], eax
0x1800b53f6  mov     rax, [rsp+68h+var_40]
0x1800b53fb  add     rax, 23C34600h
0x1800b5401  mov     [rsp+68h+var_40], rax
0x1800b5406  shr     rax, 20h
0x1800b540a  mov     cs:FileTime2.dwHighDateTime, eax
0x1800b5410  mov     eax, dword ptr [rsp+68h+var_40]
0x1800b5414  mov     cs:FileTime2.dwLowDateTime, eax
0x1800b541a  call    cs:__imp_EnterCriticalSection
0x1800b5420  mov     rcx, rdi; this
0x1800b5423  call    ?HrEnterBusy@CIxpBase@@IEAAJXZ; CIxpBase::HrEnterBusy(void)
0x1800b5428  mov     ebx, eax
0x1800b542a  test    eax, eax
0x1800b542c  js      short loc_1800B543F
0x1800b542e  lea     rdx, POP3_NOOP_STR; "NOOP\r\n"
0x1800b5435  mov     rcx, rdi; this
0x1800b5438  call    ?HrSendLine@CIxpBase@@IEAAJPEAD@Z; CIxpBase::HrSendLine(char *)
0x1800b543d  mov     ebx, eax
0x1800b543f  test    ebx, ebx
0x1800b5441  jns     short loc_1800B544B
0x1800b5443  mov     rcx, rdi; this
0x1800b5446  call    ?LeaveBusy@CIxpBase@@IEAAXXZ; CIxpBase::LeaveBusy(void)
0x1800b544b  mov     rcx, r14; lpCriticalSection
0x1800b544e  call    cs:__imp_LeaveCriticalSection
0x1800b5454  test    ebx, ebx
0x1800b5456  js      short loc_1800B5462
0x1800b5458  mov     dword ptr [rsi+0CE0h], 0Ch
0x1800b5462  mov     rcx, rbp; lpCriticalSection
0x1800b5465  call    cs:__imp_LeaveCriticalSection
0x1800b546b  mov     eax, ebx
0x1800b546d  mov     rcx, [rsp+68h+var_28]
0x1800b5472  xor     rcx, rsp; StackCookie
0x1800b5475  call    __security_check_cookie
0x1800b547a  lea     r11, [rsp+68h+var_18]
0x1800b547f  mov     rbx, [r11+28h]
0x1800b5483  mov     rbp, [r11+30h]
0x1800b5487  mov     rsp, r11
0x1800b548a  pop     r14
0x1800b548c  pop     rdi
0x1800b548d  pop     rsi
0x1800b548e  retn
```
