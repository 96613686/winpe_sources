# WpcWebFilterIsEnabledForCurrentUser(void)

- ea: `0x1810c2824`
- end: `0x1810c2a60`
- name: `?WpcWebFilterIsEnabledForCurrentUser@@YAHXZ`
- size: `572`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1810934f0`

## callees

- `0x1801bf528`
- `0x1801c0b08`
- `0x18028ecdc`
- `0x1805ae48c`
- `0x18083eda0`
- `0x1810c2824`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x1810c2911`
- `KERNEL32!InitOnceExecuteOnce` at `0x1810c2911`
- `KERNEL32!LocalFree` at `0x1810c2a2f`
- `KERNEL32!LocalFree` at `0x1810c2a39`
- `KERNEL32!LocalFree` at `0x1810c2a2f`
- `KERNEL32!LocalFree` at `0x1810c2a39`
- `KERNEL32!CloseHandle` at `0x1810c2a43`
- `KERNEL32!CloseHandle` at `0x1810c2a43`
- `KERNEL32!GetCurrentProcess` at `0x1810c287f`
- `KERNEL32!GetCurrentProcess` at `0x1810c287f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1810c29fe`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1810c29fe`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1810c29c7`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1810c29c7`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x1810c2891`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x1810c2891`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1810c2a16`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1810c2a16`
- `iertutil!__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z` at `0x1810c28af`
- `iertutil!__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z` at `0x1810c28af`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x1810c28cd`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x1810c28cd`

## pseudocode

```c
__int64 WpcWebFilterIsEnabledForCurrentUser(void)
{
  char v0; // al
  HANDLE CurrentProcess; // rax
  bool v2; // si
  HKEY v3; // rdi
  __int64 v4; // rax
  WCHAR *v5; // rbx
  const wchar_t *v6; // r9
  void *v7; // r8
  BYTE Data[4]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-34h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  PSID Sid; // [rsp+48h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-18h] BYREF

  if ( !byte_181592D1D )
  {
    if ( (unsigned __int8)IsWpcWebFilterDestroyPresent()
      && (unsigned __int8)IsWpcWebFilterDestroyPresent()
      && (unsigned __int8)IsWpcWebFilterDestroyPresent() )
    {
      v0 = byte_181592D1D;
    }
    else
    {
      v0 = 1;
      byte_181592D1C = 0;
      byte_181592D1D = 1;
    }
    if ( !v0 )
    {
      TokenHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        Sid = 0;
        if ( !GetUserSid(TokenHandle, &Sid) )
        {
          StringSid = 0;
          if ( ConvertSidToStringSidW(Sid, &StringSid) )
          {
            hKey = 0;
            if ( (int)StringCchLengthW(StringSid, 0x7FFFFFFFu, (unsigned __int64 *)&hKey) >= 0 )
            {
              InitOnceExecuteOnce(&stru_181592D20, DeviceFamilyInfo::InitOnceDeviceFamily, 0, 0);
              v2 = DeviceFamilyInfo::g_deviceFamilyInfo == 5;
              v3 = hKey + 19;
              if ( DeviceFamilyInfo::g_deviceFamilyInfo != 5 )
                v3 = hKey + 17;
              v4 = 2LL * (_QWORD)v3;
              if ( !is_mul_ok((unsigned __int64)v3, 2u) )
                v4 = -1;
              v5 = (WCHAR *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v4);
              if ( v5 )
              {
                v6 = L"OSDATA\\";
                if ( !v2 )
                  v6 = &LocaleName;
                if ( (int)StringCchPrintfW(
                            v5,
                            (unsigned __int64)v3,
                            L"%s%s%s",
                            v6,
                            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Parental Controls\\Users\\",
                            StringSid) >= 0 )
                {
                  hKey = 0;
                  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x101u, &hKey) )
                  {
                    *(_DWORD *)Data = 0;
                    cbData = 4;
                    if ( !RegQueryValueExW(hKey, L"EnableTridentWebFilter", 0, 0, Data, &cbData) )
                      byte_181592D1C = *(_DWORD *)Data != 0;
                    RegCloseKey(hKey);
                  }
                }
                MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v5, v7);
              }
            }
            LocalFree(StringSid);
          }
          LocalFree(Sid);
        }
        CloseHandle(TokenHandle);
      }
      byte_181592D1D = 1;
    }
  }
  return (unsigned __int8)byte_181592D1C;
}

```

## disassembly

```asm
0x1810c2824  push    rbp
0x1810c2826  push    rbx
0x1810c2827  push    rsi
0x1810c2828  push    rdi
0x1810c2829  mov     rbp, rsp
0x1810c282c  sub     rsp, 68h
0x1810c2830  cmp     cs:byte_181592D1D, 0
0x1810c2837  jnz     loc_1810C2A50
0x1810c283d  call    IsWpcWebFilterDestroyPresent
0x1810c2842  test    al, al
0x1810c2844  jz      short loc_1810C2860
0x1810c2846  call    IsWpcWebFilterDestroyPresent
0x1810c284b  test    al, al
0x1810c284d  jz      short loc_1810C2860
0x1810c284f  call    IsWpcWebFilterDestroyPresent
0x1810c2854  test    al, al
0x1810c2856  jz      short loc_1810C2860
0x1810c2858  mov     al, cs:byte_181592D1D
0x1810c285e  jmp     short loc_1810C286F
0x1810c2860  mov     al, 1
0x1810c2862  mov     cs:byte_181592D1C, 0
0x1810c2869  mov     cs:byte_181592D1D, al
0x1810c286f  test    al, al
0x1810c2871  jnz     loc_1810C2A50
0x1810c2877  mov     [rbp+TokenHandle], 0
0x1810c287f  call    cs:__imp_GetCurrentProcess
0x1810c2885  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1810c2889  mov     edx, 8; DesiredAccess
0x1810c288e  mov     rcx, rax; ProcessHandle
0x1810c2891  call    cs:__imp_OpenProcessToken
0x1810c2897  test    eax, eax
0x1810c2899  jz      loc_1810C2A49
0x1810c289f  mov     rcx, [rbp+TokenHandle]
0x1810c28a3  lea     rdx, [rbp+Sid]
0x1810c28a7  mov     [rbp+Sid], 0
0x1810c28af  call    cs:__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x1810c28b5  test    eax, eax
0x1810c28b7  jnz     loc_1810C2A3F
0x1810c28bd  mov     rcx, [rbp+Sid]; Sid
0x1810c28c1  lea     rdx, [rbp+StringSid]; StringSid
0x1810c28c5  mov     [rbp+StringSid], 0
0x1810c28cd  call    cs:__imp_ConvertSidToStringSidW
0x1810c28d3  test    eax, eax
0x1810c28d5  jz      loc_1810C2A35
0x1810c28db  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x1810c28df  lea     r8, [rbp+hKey]; unsigned __int64 *
0x1810c28e3  mov     edx, 7FFFFFFFh; unsigned __int64
0x1810c28e8  mov     [rbp+hKey], 0
0x1810c28f0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1810c28f5  test    eax, eax
0x1810c28f7  js      loc_1810C2A2B
0x1810c28fd  xor     r9d, r9d; Context
0x1810c2900  lea     rdx, ?InitOnceDeviceFamily@DeviceFamilyInfo@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1810c2907  xor     r8d, r8d; Parameter
0x1810c290a  lea     rcx, stru_181592D20; InitOnce
0x1810c2911  call    cs:__imp_InitOnceExecuteOnce
0x1810c2917  cmp     cs:?g_deviceFamilyInfo@DeviceFamilyInfo@@3KA, 5; ulong DeviceFamilyInfo::g_deviceFamilyInfo
0x1810c291e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1810c2925  mov     rax, [rbp+hKey]
0x1810c2929  setz    sil
0x1810c292d  add     rax, 44h ; 'D'
0x1810c2931  test    sil, sil
0x1810c2934  lea     rdi, [rax+8]
0x1810c2938  cmovz   rdi, rax
0x1810c293c  mov     eax, 2
0x1810c2941  mul     rdi
0x1810c2944  cmovb   rax, rcx
0x1810c2948  mov     rcx, cs:g_hProcessHeap
0x1810c294f  mov     rdx, rax
0x1810c2952  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1810c2957  mov     rbx, rax
0x1810c295a  test    rax, rax
0x1810c295d  jz      loc_1810C2A2B
0x1810c2963  mov     rcx, [rbp+StringSid]
0x1810c2967  lea     rax, LocaleName
0x1810c296e  mov     [rsp+68h+lpcbData], rcx
0x1810c2973  lea     r9, aOsdata; "OSDATA\\"
0x1810c297a  test    sil, sil
0x1810c297d  lea     r8, aSSS; "%s%s%s"
0x1810c2984  mov     rdx, rdi; unsigned __int64
0x1810c2987  mov     rcx, rbx; unsigned __int16 *
0x1810c298a  cmovz   r9, rax
0x1810c298e  lea     rax, aSoftwareMicros_28; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1810c2995  mov     [rsp+68h+phkResult], rax
0x1810c299a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1810c299f  test    eax, eax
0x1810c29a1  js      short loc_1810C2A1C
0x1810c29a3  lea     rax, [rbp+hKey]
0x1810c29a7  mov     [rbp+hKey], 0
0x1810c29af  mov     r9d, 101h; samDesired
0x1810c29b5  mov     [rsp+68h+phkResult], rax; phkResult
0x1810c29ba  xor     r8d, r8d; ulOptions
0x1810c29bd  mov     rdx, rbx; lpSubKey
0x1810c29c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1810c29c7  call    cs:__imp_RegOpenKeyExW
0x1810c29cd  test    eax, eax
0x1810c29cf  jnz     short loc_1810C2A1C
0x1810c29d1  mov     rcx, [rbp+hKey]; hKey
0x1810c29d5  lea     rdx, aEnabletridentw; "EnableTridentWebFilter"
0x1810c29dc  mov     dword ptr [rbp+Data], eax
0x1810c29df  xor     r9d, r9d; lpType
0x1810c29e2  lea     rax, [rbp+cbData]
0x1810c29e6  mov     [rbp+cbData], 4
0x1810c29ed  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1810c29f2  xor     r8d, r8d; lpReserved
0x1810c29f5  lea     rax, [rbp+Data]
0x1810c29f9  mov     [rsp+68h+phkResult], rax; lpData
0x1810c29fe  call    cs:__imp_RegQueryValueExW
0x1810c2a04  test    eax, eax
0x1810c2a06  jnz     short loc_1810C2A12
0x1810c2a08  cmp     dword ptr [rbp+Data], eax
0x1810c2a0b  setnz   cs:byte_181592D1C
0x1810c2a12  mov     rcx, [rbp+hKey]; hKey
0x1810c2a16  call    cs:__imp_RegCloseKey
0x1810c2a1c  mov     rcx, cs:g_hProcessHeap; this
0x1810c2a23  mov     rdx, rbx; void *
0x1810c2a26  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x1810c2a2b  mov     rcx, [rbp+StringSid]; hMem
0x1810c2a2f  call    cs:__imp_LocalFree
0x1810c2a35  mov     rcx, [rbp+Sid]; hMem
0x1810c2a39  call    cs:__imp_LocalFree
0x1810c2a3f  mov     rcx, [rbp+TokenHandle]; hObject
0x1810c2a43  call    cs:__imp_CloseHandle
0x1810c2a49  mov     cs:byte_181592D1D, 1
0x1810c2a50  movzx   eax, cs:byte_181592D1C
0x1810c2a57  add     rsp, 68h
0x1810c2a5b  pop     rdi
0x1810c2a5c  pop     rsi
0x1810c2a5d  pop     rbx
0x1810c2a5e  pop     rbp
0x1810c2a5f  retn
```
