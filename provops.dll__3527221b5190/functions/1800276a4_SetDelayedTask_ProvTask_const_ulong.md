# SetDelayedTask(ProvTask const &,ulong)

- ea: `0x1800276a4`
- end: `0x1800278c7`
- name: `?SetDelayedTask@@YAXAEBUProvTask@@K@Z`
- size: `547`
- prototype: `void __fastcall(const struct ProvTask *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180017938`

## callees

- `0x180007ea4`
- `0x18001b388`
- `0x180020710`
- `0x18002627c`
- `0x1800276a4`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800276d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800276d9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180027748`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180027748`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800276ef`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800276ef`

## string_xrefs

- `0x180027835`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180027851`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x18002786d`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180027883`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x180027899`: `onecoreuap\admin\prov\lib\taskhelper.cpp`
- `0x1800278b2`: `onecoreuap\admin\prov\lib\taskhelper.cpp`

## pseudocode

```c
void __fastcall SetDelayedTask(const struct ProvTask *a1, unsigned int a2)
{
  unsigned __int64 v3; // rbx
  const char *v4; // r9
  struct _FILETIME v5; // rax
  const char *v6; // r9
  int v7; // eax
  int v8; // eax
  int v9; // [rsp+20h] [rbp-69h]
  int wMonth; // [rsp+20h] [rbp-69h]
  int v11; // [rsp+20h] [rbp-69h]
  struct _FILETIME FileTime; // [rsp+50h] [rbp-39h] BYREF
  struct _FILETIME v13; // [rsp+58h] [rbp-31h]
  _QWORD v14[2]; // [rsp+60h] [rbp-29h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int16 v16[20]; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int16 v17[20]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = a2;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      v4);
  v13 = FileTime;
  v14[0] = 0;
  if ( !is_mul_ok(v3, 0x989680u) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)0x80070216LL,
      v9);
  v5 = (struct _FILETIME)(*(_QWORD *)&v13 + 10000000 * v3);
  if ( *(_QWORD *)&v5 < *(unsigned __int64 *)&v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)0x80070216LL,
      v9);
  *(_QWORD *)&v13 += 10000000 * v3;
  FileTime = v5;
  if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      v6);
  wMonth = SystemTime.wMonth;
  v7 = StringCchPrintfW(v16, 0x14u, L"%04d-%02d-%02dT%02d:%02d:%02d", SystemTime.wYear);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v7,
      wMonth);
  v11 = SystemTime.wMonth;
  v8 = StringCchPrintfW(v17, 0x14u, L"%04d-%02d-%02dT%02d:%02d:%02d", SystemTime.wYear);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\taskhelper.cpp",
      (const char *)(unsigned int)v8,
      v11);
  v14[0] = v16;
  v14[1] = v17;
  SetTaskInternal__lambda_e2795d2c095b532abc38e34a2a3e1764_(a1, v14);
}

```

## disassembly

```asm
0x1800276a4  mov     [rsp-8+arg_10], rbx
0x1800276a9  mov     [rsp-8+arg_18], rdi
0x1800276ae  push    rbp
0x1800276af  lea     rbp, [rsp-57h]
0x1800276b4  sub     rsp, 0E0h
0x1800276bb  mov     rax, cs:__security_cookie
0x1800276c2  xor     rax, rsp
0x1800276c5  mov     [rbp+57h+var_10], rax
0x1800276c9  mov     rdi, rcx
0x1800276cc  mov     ebx, edx
0x1800276ce  xorps   xmm0, xmm0
0x1800276d1  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800276d5  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800276d9  call    cs:__imp_GetLocalTime
0x1800276df  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1800276e3  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x1800276eb  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800276ef  call    cs:__imp_SystemTimeToFileTime
0x1800276f5  test    eax, eax
0x1800276f7  jz      loc_180027869
0x1800276fd  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x180027700  mov     dword ptr [rbp+57h+var_88+4], eax
0x180027703  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x180027706  mov     dword ptr [rbp+57h+var_88], eax
0x180027709  mov     eax, 989680h
0x18002770e  mul     rbx
0x180027711  mov     [rbp+57h+var_80], 0
0x180027719  test    rdx, rdx
0x18002771c  jnz     loc_18002784D
0x180027722  add     rax, [rbp+57h+var_88]
0x180027726  cmp     rax, [rbp+57h+var_88]
0x18002772a  jb      loc_180027831
0x180027730  mov     [rbp+57h+var_88], rax
0x180027734  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x180027738  mov     eax, dword ptr [rbp+57h+var_88+4]
0x18002773b  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x18002773f  mov     [rbp+57h+FileTime.dwHighDateTime], eax
0x180027742  mov     eax, dword ptr [rbp+57h+var_88]
0x180027745  mov     [rbp+57h+FileTime.dwLowDateTime], eax
0x180027748  call    cs:__imp_FileTimeToSystemTime
0x18002774e  test    eax, eax
0x180027750  jz      loc_18002787F
0x180027756  movzx   ecx, [rbp+57h+SystemTime.wMinute]
0x18002775a  movzx   edx, [rbp+57h+SystemTime.wHour]
0x18002775e  movzx   r8d, [rbp+57h+SystemTime.wDay]
0x180027763  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x180027767  movzx   r10d, [rbp+57h+SystemTime.wMonth]
0x18002776c  movzx   r9d, [rbp+57h+SystemTime.wYear]
0x180027771  mov     [rsp+0E0h+var_A0], eax
0x180027775  mov     [rsp+0E0h+var_A8], ecx
0x180027779  lea     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18002777d  mov     [rsp+0E0h+var_B0], edx
0x180027781  mov     edx, 14h; unsigned __int64
0x180027786  mov     [rsp+0E0h+var_B8], r8d
0x18002778b  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d"
0x180027792  mov     [rsp+0E0h+var_C0], r10d; int
0x180027797  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002779c  test    eax, eax
0x18002779e  js      loc_180027895
0x1800277a4  movzx   ecx, [rbp+57h+SystemTime.wSecond]
0x1800277a8  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d"
0x1800277af  movzx   r10d, [rbp+57h+SystemTime.wMinute]
0x1800277b4  mov     edx, 14h; unsigned __int64
0x1800277b9  movzx   ebx, [rbp+57h+SystemTime.wDay]
0x1800277bd  movzx   r11d, [rbp+57h+SystemTime.wHour]
0x1800277c2  inc     ebx
0x1800277c4  movzx   eax, [rbp+57h+SystemTime.wMonth]
0x1800277c8  movzx   r9d, [rbp+57h+SystemTime.wYear]
0x1800277cd  mov     [rsp+0E0h+var_A0], ecx
0x1800277d1  lea     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x1800277d5  mov     [rsp+0E0h+var_A8], r10d
0x1800277da  mov     [rsp+0E0h+var_B0], r11d
0x1800277df  mov     [rsp+0E0h+var_B8], ebx
0x1800277e3  mov     [rsp+0E0h+var_C0], eax; int
0x1800277e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800277ec  test    eax, eax
0x1800277ee  js      loc_1800278AE
0x1800277f4  lea     rax, [rbp+57h+var_60]
0x1800277f8  mov     rcx, rdi
0x1800277fb  mov     [rbp+57h+var_80], rax
0x1800277ff  lea     rdx, [rbp+57h+var_80]
0x180027803  lea     rax, [rbp+57h+var_38]
0x180027807  mov     [rbp+57h+var_78], rax
0x18002780b  call    SetTaskInternal__lambda_e2795d2c095b532abc38e34a2a3e1764___; SetTaskInternal__lambda_e2795d2c095b532abc38e34a2a3e1764_
0x180027810  mov     rcx, [rbp+57h+var_10]
0x180027814  xor     rcx, rsp; StackCookie
0x180027817  call    __security_check_cookie
0x18002781c  lea     r11, [rsp+0E0h+var_s0]
0x180027824  mov     rbx, [r11+20h]
0x180027828  mov     rdi, [r11+28h]
0x18002782c  mov     rsp, r11
0x18002782f  pop     rbp
0x180027830  retn
0x180027831  mov     rcx, [rbp+5Fh]; this
0x180027835  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x18002783c  mov     r9d, 80070216h; char *
0x180027842  mov     edx, 0ACh; void *
0x180027847  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002784d  mov     rcx, [rbp+5Fh]; this
0x180027851  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180027858  mov     r9d, 80070216h; char *
0x18002785e  mov     edx, 0ABh; void *
0x180027863  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027869  mov     rcx, [rbp+5Fh]; this
0x18002786d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x180027874  mov     edx, 0A4h; void *
0x180027879  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002787f  mov     rcx, [rbp+5Fh]; this
0x180027883  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x18002788a  mov     edx, 0B0h; void *
0x18002788f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180027895  mov     rcx, [rbp+5Fh]; this
0x180027899  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800278a0  mov     r9d, eax; char *
0x1800278a3  mov     edx, 0B7h; void *
0x1800278a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800278ae  mov     rcx, [rbp+5Fh]; this
0x1800278b2  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\lib\\taskhelpe"...
0x1800278b9  mov     r9d, eax; char *
0x1800278bc  mov     edx, 0BEh; void *
0x1800278c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
