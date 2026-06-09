# CVidCtlTrace::CVidCtlTrace(void)

- ea: `0x1800ed58c`
- end: `0x1800ed771`
- name: `??0CVidCtlTrace@@QEAA@XZ`
- size: `485`
- prototype: `CVidCtlTrace *__fastcall(CVidCtlTrace *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001210`

## callees

- `0x180004640`
- `0x180004740`
- `0x180004b48`
- `0x1800054bc`
- `0x18000bcf0`
- `0x18000bd70`
- `0x1800ed58c`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x1800ed692`
- `KERNEL32!GetTempPath2W` at `0x1800ed692`
- `KERNEL32!CreateFileW` at `0x1800ed739`
- `KERNEL32!CreateFileW` at `0x1800ed739`
- `KERNEL32!InitializeCriticalSection` at `0x1800ed5e5`
- `KERNEL32!InitializeCriticalSection` at `0x1800ed5e5`
- `ADVAPI32!RegQueryValueExW` at `0x1800ed648`
- `ADVAPI32!RegQueryValueExW` at `0x1800ed648`
- `ADVAPI32!RegOpenKeyExW` at `0x1800ed60c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800ed60c`
- `ADVAPI32!RegCloseKey` at `0x1800ed668`
- `ADVAPI32!RegCloseKey` at `0x1800ed668`

## pseudocode

```c
CVidCtlTrace *__fastcall CVidCtlTrace::CVidCtlTrace(CVidCtlTrace *this)
{
  char v1; // bl
  int v2; // eax
  unsigned int TempPath2W; // eax
  unsigned __int64 v4; // rbx
  int v5; // eax
  unsigned __int64 v6; // rdx
  WCHAR *v7; // rcx
  const WCHAR *v8; // rcx
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v13[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(__m128i *)&lpFileName = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
  qword_18021D0F8 = 6;
  v1 = 0;
  hKey = 0;
  InitializeCriticalSection(&gCVidCtlTrace);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DirectShow\\Debug\\MSVIDCTL", 0, 0x20019u, &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"TracePriority", 0, 0, Data, &cbData) )
    {
      v2 = *(_DWORD *)Data;
      v1 = 1;
      if ( *(_DWORD *)Data > 6u )
        v2 = 6;
      LODWORD(qword_18021D0F8) = v2;
    }
    RegCloseKey(hKey);
  }
  memset_0(v13, 0, 0x208u);
  if ( v1 )
  {
    TempPath2W = GetTempPath2W(260, v13);
    if ( TempPath2W )
    {
      v4 = TempPath2W + 14LL;
      lpFileName = (LPCWSTR)operator new[](saturated_mul(v4, 2u));
      v5 = StringCchCopyW((unsigned __int16 *)lpFileName, v4, v13);
      v7 = (WCHAR *)lpFileName;
      if ( v5 < 0 )
      {
LABEL_12:
        operator delete(v7, v6);
        v8 = 0;
        lpFileName = 0;
        goto LABEL_14;
      }
      if ( StringCchCatW((unsigned __int16 *)lpFileName, v4, L"MSVIDCTL.txt") < 0 )
      {
        v7 = (WCHAR *)lpFileName;
        goto LABEL_12;
      }
    }
    v8 = lpFileName;
LABEL_14:
    if ( v8 )
      *(&lpFileName + 1) = (LPCWSTR)CreateFileW(v8, 4u, 3u, 0, 4u, 0, 0);
  }
  return (CVidCtlTrace *)&gCVidCtlTrace;
}

```

## disassembly

```asm
0x1800ed58c  mov     [rsp-8+arg_0], rbx
0x1800ed591  mov     [rsp-8+arg_8], rsi
0x1800ed596  push    rbp
0x1800ed597  lea     rbp, [rsp-170h]
0x1800ed59f  sub     rsp, 270h
0x1800ed5a6  mov     rax, cs:__security_cookie
0x1800ed5ad  xor     rax, rsp
0x1800ed5b0  mov     [rbp+170h+var_10], rax
0x1800ed5b7  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x1800ed5bf  lea     rcx, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; lpCriticalSection
0x1800ed5c6  mov     esi, 6
0x1800ed5cb  movdqa  cs:lpFileName, xmm0
0x1800ed5d3  mov     cs:qword_18021D0F8, rsi
0x1800ed5da  xor     bl, bl
0x1800ed5dc  mov     [rsp+270h+hKey], 0
0x1800ed5e5  call    cs:__imp_InitializeCriticalSection
0x1800ed5eb  lea     rax, [rsp+270h+hKey]
0x1800ed5f0  mov     r9d, 20019h; samDesired
0x1800ed5f6  xor     r8d, r8d; ulOptions
0x1800ed5f9  mov     [rsp+270h+phkResult], rax; phkResult
0x1800ed5fe  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\DirectShow\\Debug"...
0x1800ed605  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ed60c  call    cs:__imp_RegOpenKeyExW
0x1800ed612  test    eax, eax
0x1800ed614  jnz     short loc_1800ED66E
0x1800ed616  mov     rcx, [rsp+270h+hKey]; hKey
0x1800ed61b  lea     rdx, aTracepriority; "TracePriority"
0x1800ed622  mov     dword ptr [rsp+270h+Data], eax
0x1800ed626  xor     r9d, r9d; lpType
0x1800ed629  lea     rax, [rsp+270h+cbData]
0x1800ed62e  mov     [rsp+270h+cbData], 4
0x1800ed636  mov     [rsp+270h+lpcbData], rax; lpcbData
0x1800ed63b  xor     r8d, r8d; lpReserved
0x1800ed63e  lea     rax, [rsp+270h+Data]
0x1800ed643  mov     [rsp+270h+phkResult], rax; lpData
0x1800ed648  call    cs:__imp_RegQueryValueExW
0x1800ed64e  test    eax, eax
0x1800ed650  jnz     short loc_1800ED663
0x1800ed652  mov     eax, dword ptr [rsp+270h+Data]
0x1800ed656  mov     bl, 1
0x1800ed658  cmp     eax, esi
0x1800ed65a  cmova   eax, esi
0x1800ed65d  mov     dword ptr cs:qword_18021D0F8, eax
0x1800ed663  mov     rcx, [rsp+270h+hKey]; hKey
0x1800ed668  call    cs:__imp_RegCloseKey
0x1800ed66e  xor     edx, edx; Val
0x1800ed670  lea     rcx, [rsp+270h+var_220]; void *
0x1800ed675  mov     r8d, 208h; Size
0x1800ed67b  call    memset_0
0x1800ed680  test    bl, bl
0x1800ed682  jz      loc_1800ED746
0x1800ed688  lea     rdx, [rsp+270h+var_220]
0x1800ed68d  mov     ecx, 104h
0x1800ed692  call    cs:__imp_GetTempPath2W
0x1800ed698  test    eax, eax
0x1800ed69a  jz      short loc_1800ED709
0x1800ed69c  mov     ebx, eax
0x1800ed69e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ed6a5  add     rbx, 0Eh
0x1800ed6a9  mov     eax, 2
0x1800ed6ae  mul     rbx
0x1800ed6b1  cmovb   rax, rcx
0x1800ed6b5  mov     rcx, rax; unsigned __int64
0x1800ed6b8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ed6bd  lea     r8, [rsp+270h+var_220]; unsigned __int16 *
0x1800ed6c2  mov     qword ptr cs:lpFileName, rax
0x1800ed6c9  mov     rdx, rbx; unsigned __int64
0x1800ed6cc  mov     rcx, rax; unsigned __int16 *
0x1800ed6cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ed6d4  mov     rcx, qword ptr cs:lpFileName; unsigned __int16 *
0x1800ed6db  test    eax, eax
0x1800ed6dd  js      short loc_1800ED6F9
0x1800ed6df  lea     r8, aMsvidctlTxt; "MSVIDCTL.txt"
0x1800ed6e6  mov     rdx, rbx; unsigned __int64
0x1800ed6e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ed6ee  test    eax, eax
0x1800ed6f0  jns     short loc_1800ED709
0x1800ed6f2  mov     rcx, qword ptr cs:lpFileName; void *
0x1800ed6f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ed6fe  xor     ecx, ecx
0x1800ed700  mov     qword ptr cs:lpFileName, rcx
0x1800ed707  jmp     short loc_1800ED710
0x1800ed709  mov     rcx, qword ptr cs:lpFileName; lpFileName
0x1800ed710  test    rcx, rcx
0x1800ed713  jz      short loc_1800ED746
0x1800ed715  xor     r9d, r9d; lpSecurityAttributes
0x1800ed718  mov     [rsp+270h+hTemplateFile], 0; hTemplateFile
0x1800ed721  mov     dword ptr [rsp+270h+lpcbData], 0; dwFlagsAndAttributes
0x1800ed729  mov     dword ptr [rsp+270h+phkResult], 4; dwCreationDisposition
0x1800ed731  lea     edx, [r9+4]; dwDesiredAccess
0x1800ed735  lea     r8d, [r9+3]; dwShareMode
0x1800ed739  call    cs:__imp_CreateFileW
0x1800ed73f  mov     qword ptr cs:lpFileName+8, rax
0x1800ed746  lea     rax, ?gCVidCtlTrace@@3VCVidCtlTrace@@A; CVidCtlTrace gCVidCtlTrace
0x1800ed74d  mov     rcx, [rbp+170h+var_10]
0x1800ed754  xor     rcx, rsp; StackCookie
0x1800ed757  call    __security_check_cookie
0x1800ed75c  lea     r11, [rsp+270h+var_s0]
0x1800ed764  mov     rbx, [r11+10h]
0x1800ed768  mov     rsi, [r11+18h]
0x1800ed76c  mov     rsp, r11
0x1800ed76f  pop     rbp
0x1800ed770  retn
```
