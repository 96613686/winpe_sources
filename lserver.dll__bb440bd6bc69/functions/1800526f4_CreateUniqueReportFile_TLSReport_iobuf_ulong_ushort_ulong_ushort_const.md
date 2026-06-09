# CreateUniqueReportFile(_TLSReport *,_iobuf * *,ulong,ushort *,ulong,ushort const *)

- ea: `0x1800526f4`
- end: `0x18005297c`
- name: `?CreateUniqueReportFile@@YAKPEAU_TLSReport@@PEAPEAU_iobuf@@KPEAGKPEBG@Z`
- size: `648`
- prototype: `__int64 __fastcall(struct _TLSReport *, struct _iobuf **, __int64, unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800553a4`

## callees

- `0x18000cff0`
- `0x18000d060`
- `0x1800526f4`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!_wfopen_s` at `0x1800528d9`
- `msvcrt!_wfopen_s` at `0x1800528d9`
- `KERNEL32!GetLocalTime` at `0x180052749`
- `KERNEL32!GetLocalTime` at `0x180052749`
- `KERNEL32!CreateDirectoryW` at `0x180052894`
- `KERNEL32!CreateDirectoryW` at `0x180052894`
- `KERNEL32!Sleep` at `0x180052865`
- `KERNEL32!Sleep` at `0x180052865`
- `KERNEL32!CreateFileW` at `0x18005283f`
- `KERNEL32!CreateFileW` at `0x18005283f`
- `KERNEL32!GetLastError` at `0x180052851`
- `KERNEL32!GetLastError` at `0x180052876`
- `KERNEL32!GetLastError` at `0x1800528a8`
- `KERNEL32!GetLastError` at `0x180052851`
- `KERNEL32!GetLastError` at `0x180052876`
- `KERNEL32!GetLastError` at `0x1800528a8`
- `KERNEL32!CloseHandle` at `0x1800528be`
- `KERNEL32!CloseHandle` at `0x1800528be`

## pseudocode

```c
__int64 __fastcall CreateUniqueReportFile(
        struct _TLSReport *a1,
        struct _iobuf **a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6)
{
  const unsigned __int16 *v6; // rsi
  unsigned int v7; // ebx
  HANDLE FileW; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  FILE *Stream; // [rsp+40h] [rbp-C0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v20[256]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v21[256]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v22[256]; // [rsp+460h] [rbp+360h] BYREF

  v6 = a6;
  v7 = 0;
  Stream = 0;
  while ( 1 )
  {
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    dwFlagsAndAttributes[0] = SystemTime.wDay;
    dwCreationDisposition[0] = SystemTime.wMonth;
    StringCchPrintfW(
      v20,
      0xFFu,
      L"%04d%02d%02d",
      SystemTime.wYear,
      *(_QWORD *)dwCreationDisposition,
      *(_QWORD *)dwFlagsAndAttributes);
    dwFlagsAndAttributesa[0] = SystemTime.wSecond;
    dwCreationDispositiona[0] = SystemTime.wMinute;
    StringCchPrintfW(
      v21,
      0xFFu,
      L"%02d%02d%02d",
      SystemTime.wHour,
      *(_QWORD *)dwCreationDispositiona,
      *(_QWORD *)dwFlagsAndAttributesa);
    LODWORD(hTemplateFile) = SystemTime.wMilliseconds;
    StringCchPrintfW(v22, 0xFFu, L"%s%s-%s-%d%s", L"PER-USER_", v20, v21, hTemplateFile, L".dat");
    StringCchPrintfW(a4, 0xFFu, L"%s%s", &g_szReportDir, v22);
    FileW = CreateFileW(a4, 0x40000000u, 0, 0, 1u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
      break;
    if ( GetLastError() == 80 )
    {
      Sleep(1u);
    }
    else if ( GetLastError() == 3 && !CreateDirectoryW(&g_szReportDir, 0) )
    {
      return GetLastError();
    }
  }
  CloseHandle(FileW);
  _wfopen_s(&Stream, a4, L"wt");
  StringCchCopyW((unsigned __int16 *)a1 + 2, 0xFFu, v20);
  StringCchCopyW((unsigned __int16 *)a1 + 257, 0xFFu, v21);
  *((_DWORD *)a1 + 256) = a5;
  if ( !a6 )
    v6 = &pszSrc;
  StringCchCopyW((unsigned __int16 *)a1 + 514, 0xFFu, v6);
  StringCchCopyW((unsigned __int16 *)a1 + 772, 0xFFu, v22);
  *a2 = Stream;
  return v7;
}

```

## disassembly

```asm
0x1800526f4  push    rbp
0x1800526f6  push    rbx
0x1800526f7  push    rsi
0x1800526f8  push    rdi
0x1800526f9  push    r12
0x1800526fb  push    r14
0x1800526fd  push    r15
0x1800526ff  lea     rbp, [rsp-570h]
0x180052707  sub     rsp, 670h
0x18005270e  mov     rax, cs:__security_cookie
0x180052715  xor     rax, rsp
0x180052718  mov     [rbp+5A0h+var_40], rax
0x18005271f  mov     rsi, [rbp+5A0h+arg_28]
0x180052726  xor     ebx, ebx
0x180052728  mov     [rsp+6A0h+Stream], rbx
0x18005272d  mov     r14, r9
0x180052730  mov     r15, rdx
0x180052733  mov     rdi, rcx
0x180052736  mov     r12d, 0FFh
0x18005273c  xorps   xmm0, xmm0
0x18005273f  lea     rcx, [rsp+6A0h+SystemTime]; lpSystemTime
0x180052744  movups  xmmword ptr [rsp+6A0h+SystemTime.wYear], xmm0
0x180052749  call    cs:__imp_GetLocalTime
0x180052750  nop     dword ptr [rax+rax+00h]
0x180052755  movzx   ecx, [rsp+6A0h+SystemTime.wMonth]
0x18005275a  lea     r8, a04d02d02d; "%04d%02d%02d"
0x180052761  movzx   eax, [rsp+6A0h+SystemTime.wDay]
0x180052766  mov     rdx, r12; unsigned __int64
0x180052769  movzx   r9d, [rsp+6A0h+SystemTime.wYear]
0x18005276f  mov     [rsp+6A0h+dwFlagsAndAttributes], eax
0x180052773  mov     [rsp+6A0h+dwCreationDisposition], ecx
0x180052777  lea     rcx, [rsp+6A0h+var_640]; unsigned __int16 *
0x18005277c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180052781  movzx   ecx, [rsp+6A0h+SystemTime.wMinute]
0x180052786  lea     r8, a02d02d02d; "%02d%02d%02d"
0x18005278d  movzx   eax, [rsp+6A0h+SystemTime.wSecond]
0x180052792  mov     rdx, r12; unsigned __int64
0x180052795  movzx   r9d, [rsp+6A0h+SystemTime.wHour]
0x18005279b  mov     [rsp+6A0h+dwFlagsAndAttributes], eax
0x18005279f  mov     [rsp+6A0h+dwCreationDisposition], ecx
0x1800527a3  lea     rcx, [rbp+5A0h+var_440]; unsigned __int16 *
0x1800527aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800527af  movzx   eax, [rsp+6A0h+SystemTime.wMilliseconds]
0x1800527b4  lea     rcx, aDat; ".dat"
0x1800527bb  mov     [rsp+6A0h+var_668], rcx
0x1800527c0  lea     r9, aPerUser; "PER-USER_"
0x1800527c7  mov     dword ptr [rsp+6A0h+hTemplateFile], eax
0x1800527cb  lea     r8, aSSSDS; "%s%s-%s-%d%s"
0x1800527d2  lea     rax, [rbp+5A0h+var_440]
0x1800527d9  mov     rdx, r12; unsigned __int64
0x1800527dc  mov     qword ptr [rsp+6A0h+dwFlagsAndAttributes], rax
0x1800527e1  lea     rcx, [rbp+5A0h+var_240]; unsigned __int16 *
0x1800527e8  lea     rax, [rsp+6A0h+var_640]
0x1800527ed  mov     qword ptr [rsp+6A0h+dwCreationDisposition], rax
0x1800527f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800527f7  lea     rax, [rbp+5A0h+var_240]
0x1800527fe  mov     rdx, r12; unsigned __int64
0x180052801  lea     r9, ?g_szReportDir@@3PAGA; ushort near * g_szReportDir
0x180052808  mov     qword ptr [rsp+6A0h+dwCreationDisposition], rax
0x18005280d  lea     r8, aSS_1; "%s%s"
0x180052814  mov     rcx, r14; unsigned __int16 *
0x180052817  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005281c  mov     [rsp+6A0h+hTemplateFile], rbx; hTemplateFile
0x180052821  xor     r9d, r9d; lpSecurityAttributes
0x180052824  mov     [rsp+6A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005282c  xor     r8d, r8d; dwShareMode
0x18005282f  mov     edx, 40000000h; dwDesiredAccess
0x180052834  mov     [rsp+6A0h+dwCreationDisposition], 1; dwCreationDisposition
0x18005283c  mov     rcx, r14; lpFileName
0x18005283f  call    cs:__imp_CreateFileW
0x180052846  nop     dword ptr [rax+rax+00h]
0x18005284b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005284f  jnz     short loc_1800528BB
0x180052851  call    cs:__imp_GetLastError
0x180052858  nop     dword ptr [rax+rax+00h]
0x18005285d  cmp     eax, 50h ; 'P'
0x180052860  jnz     short loc_180052876
0x180052862  lea     ecx, [rax-4Fh]; dwMilliseconds
0x180052865  call    cs:__imp_Sleep
0x18005286c  nop     dword ptr [rax+rax+00h]
0x180052871  jmp     loc_18005273C
0x180052876  call    cs:__imp_GetLastError
0x18005287d  nop     dword ptr [rax+rax+00h]
0x180052882  cmp     eax, 3
0x180052885  jnz     loc_18005273C
0x18005288b  xor     edx, edx; lpSecurityAttributes
0x18005288d  lea     rcx, ?g_szReportDir@@3PAGA; lpPathName
0x180052894  call    cs:__imp_CreateDirectoryW
0x18005289b  nop     dword ptr [rax+rax+00h]
0x1800528a0  test    eax, eax
0x1800528a2  jnz     loc_18005273C
0x1800528a8  call    cs:__imp_GetLastError
0x1800528af  nop     dword ptr [rax+rax+00h]
0x1800528b4  mov     ebx, eax
0x1800528b6  jmp     loc_180052958
0x1800528bb  mov     rcx, rax; hObject
0x1800528be  call    cs:__imp_CloseHandle
0x1800528c5  nop     dword ptr [rax+rax+00h]
0x1800528ca  lea     r8, aWt; "wt"
0x1800528d1  mov     rdx, r14; FileName
0x1800528d4  lea     rcx, [rsp+6A0h+Stream]; Stream
0x1800528d9  call    cs:__imp__wfopen_s
0x1800528e0  nop     dword ptr [rax+rax+00h]
0x1800528e5  lea     rcx, [rdi+4]; unsigned __int16 *
0x1800528e9  mov     rdx, r12; unsigned __int64
0x1800528ec  lea     r8, [rsp+6A0h+var_640]; unsigned __int16 *
0x1800528f1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800528f6  lea     rcx, [rdi+202h]; unsigned __int16 *
0x1800528fd  mov     rdx, r12; unsigned __int64
0x180052900  lea     r8, [rbp+5A0h+var_440]; unsigned __int16 *
0x180052907  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005290c  mov     r11d, [rbp+5A0h+arg_20]
0x180052913  lea     rax, pszSrc
0x18005291a  test    rsi, rsi
0x18005291d  mov     [rdi+400h], r11d
0x180052924  lea     rcx, [rdi+404h]; unsigned __int16 *
0x18005292b  mov     rdx, r12; unsigned __int64
0x18005292e  cmovz   rsi, rax
0x180052932  mov     r8, rsi; unsigned __int16 *
0x180052935  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005293a  lea     rcx, [rdi+608h]; unsigned __int16 *
0x180052941  mov     rdx, r12; unsigned __int64
0x180052944  lea     r8, [rbp+5A0h+var_240]; unsigned __int16 *
0x18005294b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052950  mov     r11, [rsp+6A0h+Stream]
0x180052955  mov     [r15], r11
0x180052958  mov     eax, ebx
0x18005295a  mov     rcx, [rbp+5A0h+var_40]
0x180052961  xor     rcx, rsp; StackCookie
0x180052964  call    __security_check_cookie
0x180052969  add     rsp, 670h
0x180052970  pop     r15
0x180052972  pop     r14
0x180052974  pop     r12
0x180052976  pop     rdi
0x180052977  pop     rsi
0x180052978  pop     rbx
0x180052979  pop     rbp
0x18005297a  retn
```
