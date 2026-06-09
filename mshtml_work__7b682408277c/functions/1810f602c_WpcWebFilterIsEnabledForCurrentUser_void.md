# WpcWebFilterIsEnabledForCurrentUser(void)

- ea: `0x1810f602c`
- end: `0x1810f62af`
- name: `?WpcWebFilterIsEnabledForCurrentUser@@YAHXZ`
- size: `643`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1810c5910`

## callees

- `0x18005d080`
- `0x18005e684`
- `0x1804e4c1c`
- `0x180590d6c`
- `0x1808418d0`
- `0x1810f602c`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x1810f6131`
- `KERNEL32!InitOnceExecuteOnce` at `0x1810f6131`
- `KERNEL32!LocalFree` at `0x1810f626b`
- `KERNEL32!LocalFree` at `0x1810f627b`
- `KERNEL32!LocalFree` at `0x1810f626b`
- `KERNEL32!LocalFree` at `0x1810f627b`
- `KERNEL32!CloseHandle` at `0x1810f628b`
- `KERNEL32!CloseHandle` at `0x1810f628b`
- `KERNEL32!GetCurrentProcess` at `0x1810f6087`
- `KERNEL32!GetCurrentProcess` at `0x1810f6087`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1810f622e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegQueryValueExW` at `0x1810f622e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1810f61f1`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegOpenKeyExW` at `0x1810f61f1`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x1810f609f`
- `api-ms-win-downlevel-advapi32-l1-1-0!OpenProcessToken` at `0x1810f609f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1810f624c`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1810f624c`
- `iertutil!__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z` at `0x1810f60c3`
- `iertutil!__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z` at `0x1810f60c3`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x1810f60e7`
- `api-ms-win-downlevel-advapi32-l2-1-0!ConvertSidToStringSidW` at `0x1810f60e7`

## pseudocode

```c
__int64 WpcWebFilterIsEnabledForCurrentUser(void)
{
  char v0; // al
  HANDLE CurrentProcess; // rax
  __int64 v2; // r8
  bool v3; // si
  HKEY v4; // rdi
  __int64 v5; // rax
  WCHAR *v6; // rbx
  const wchar_t *v7; // r9
  void *v8; // r8
  BYTE Data[4]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-34h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  PSID Sid; // [rsp+48h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-18h] BYREF

  if ( !byte_1815C5E1C )
  {
    if ( (unsigned __int8)IsWpcWebFilterDestroyPresent()
      && (unsigned __int8)IsWpcWebFilterDestroyPresent()
      && (unsigned __int8)IsWpcWebFilterDestroyPresent() )
    {
      v0 = byte_1815C5E1C;
    }
    else
    {
      v0 = 1;
      byte_1815C5E1D = 0;
      byte_1815C5E1C = 1;
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
              InitOnceExecuteOnce(&stru_1815C5E20, DeviceFamilyInfo::InitOnceDeviceFamily, 0, 0);
              v3 = DeviceFamilyInfo::g_deviceFamilyInfo == 5;
              v4 = hKey + 19;
              if ( DeviceFamilyInfo::g_deviceFamilyInfo != 5 )
                v4 = hKey + 17;
              v5 = 2LL * (_QWORD)v4;
              if ( !is_mul_ok((unsigned __int64)v4, 2u) )
                v5 = -1;
              v6 = (WCHAR *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v5, v2);
              if ( v6 )
              {
                v7 = L"OSDATA\\";
                if ( !v3 )
                  v7 = &Source;
                if ( (int)StringCchPrintfW(
                            v6,
                            (unsigned __int64)v4,
                            L"%s%s%s",
                            v7,
                            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Parental Controls\\Users\\",
                            StringSid) >= 0 )
                {
                  hKey = 0;
                  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x101u, &hKey) )
                  {
                    *(_DWORD *)Data = 0;
                    cbData = 4;
                    if ( !RegQueryValueExW(hKey, L"EnableTridentWebFilter", 0, 0, Data, &cbData) )
                      byte_1815C5E1D = *(_DWORD *)Data != 0;
                    RegCloseKey(hKey);
                  }
                }
                MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v6, v8);
              }
            }
            LocalFree(StringSid);
          }
          LocalFree(Sid);
        }
        CloseHandle(TokenHandle);
      }
      byte_1815C5E1C = 1;
    }
  }
  return (unsigned __int8)byte_1815C5E1D;
}

```

## disassembly

```asm
0x1810f602c  push    rbp
0x1810f602e  push    rbx
0x1810f602f  push    rsi
0x1810f6030  push    rdi
0x1810f6031  mov     rbp, rsp
0x1810f6034  sub     rsp, 68h
0x1810f6038  cmp     cs:byte_1815C5E1C, 0
0x1810f603f  jnz     loc_1810F629E
0x1810f6045  call    IsWpcWebFilterDestroyPresent
0x1810f604a  test    al, al
0x1810f604c  jz      short loc_1810F6068
0x1810f604e  call    IsWpcWebFilterDestroyPresent
0x1810f6053  test    al, al
0x1810f6055  jz      short loc_1810F6068
0x1810f6057  call    IsWpcWebFilterDestroyPresent
0x1810f605c  test    al, al
0x1810f605e  jz      short loc_1810F6068
0x1810f6060  mov     al, cs:byte_1815C5E1C
0x1810f6066  jmp     short loc_1810F6077
0x1810f6068  mov     al, 1
0x1810f606a  mov     cs:byte_1815C5E1D, 0
0x1810f6071  mov     cs:byte_1815C5E1C, al
0x1810f6077  test    al, al
0x1810f6079  jnz     loc_1810F629E
0x1810f607f  mov     [rbp+TokenHandle], 0
0x1810f6087  call    cs:__imp_GetCurrentProcess
0x1810f608e  nop     dword ptr [rax+rax+00h]
0x1810f6093  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1810f6097  mov     edx, 8; DesiredAccess
0x1810f609c  mov     rcx, rax; ProcessHandle
0x1810f609f  call    cs:__imp_OpenProcessToken
0x1810f60a6  nop     dword ptr [rax+rax+00h]
0x1810f60ab  test    eax, eax
0x1810f60ad  jz      loc_1810F6297
0x1810f60b3  mov     rcx, [rbp+TokenHandle]
0x1810f60b7  lea     rdx, [rbp+Sid]
0x1810f60bb  mov     [rbp+Sid], 0
0x1810f60c3  call    cs:__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x1810f60ca  nop     dword ptr [rax+rax+00h]
0x1810f60cf  test    eax, eax
0x1810f60d1  jnz     loc_1810F6287
0x1810f60d7  mov     rcx, [rbp+Sid]; Sid
0x1810f60db  lea     rdx, [rbp+StringSid]; StringSid
0x1810f60df  mov     [rbp+StringSid], 0
0x1810f60e7  call    cs:__imp_ConvertSidToStringSidW
0x1810f60ee  nop     dword ptr [rax+rax+00h]
0x1810f60f3  test    eax, eax
0x1810f60f5  jz      loc_1810F6277
0x1810f60fb  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x1810f60ff  lea     r8, [rbp+hKey]; unsigned __int64 *
0x1810f6103  mov     edx, 7FFFFFFFh; unsigned __int64
0x1810f6108  mov     [rbp+hKey], 0
0x1810f6110  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1810f6115  test    eax, eax
0x1810f6117  js      loc_1810F6267
0x1810f611d  xor     r9d, r9d; Context
0x1810f6120  lea     rdx, ?InitOnceDeviceFamily@DeviceFamilyInfo@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1810f6127  xor     r8d, r8d; Parameter
0x1810f612a  lea     rcx, stru_1815C5E20; InitOnce
0x1810f6131  call    cs:__imp_InitOnceExecuteOnce
0x1810f6138  nop     dword ptr [rax+rax+00h]
0x1810f613d  cmp     cs:?g_deviceFamilyInfo@DeviceFamilyInfo@@3KA, 5; ulong DeviceFamilyInfo::g_deviceFamilyInfo
0x1810f6144  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1810f614b  mov     rax, [rbp+hKey]
0x1810f614f  setz    sil
0x1810f6153  add     rax, 44h ; 'D'
0x1810f6157  test    sil, sil
0x1810f615a  lea     rdi, [rax+8]
0x1810f615e  cmovz   rdi, rax
0x1810f6162  mov     eax, 2
0x1810f6167  mul     rdi
0x1810f616a  cmovb   rax, rcx
0x1810f616e  mov     rcx, cs:g_hProcessHeap
0x1810f6175  mov     rdx, rax
0x1810f6178  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x1810f617d  mov     rbx, rax
0x1810f6180  test    rax, rax
0x1810f6183  jz      loc_1810F6267
0x1810f6189  mov     rcx, [rbp+StringSid]
0x1810f618d  lea     rax, Source
0x1810f6194  mov     [rsp+68h+lpcbData], rcx
0x1810f6199  lea     r9, aOsdata; "OSDATA\\"
0x1810f61a0  test    sil, sil
0x1810f61a3  lea     r8, aSSS; "%s%s%s"
0x1810f61aa  mov     rdx, rdi; unsigned __int64
0x1810f61ad  mov     rcx, rbx; unsigned __int16 *
0x1810f61b0  cmovz   r9, rax
0x1810f61b4  lea     rax, aSoftwareMicros_28; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1810f61bb  mov     [rsp+68h+phkResult], rax
0x1810f61c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1810f61c5  test    eax, eax
0x1810f61c7  js      loc_1810F6258
0x1810f61cd  lea     rax, [rbp+hKey]
0x1810f61d1  mov     [rbp+hKey], 0
0x1810f61d9  mov     r9d, 101h; samDesired
0x1810f61df  mov     [rsp+68h+phkResult], rax; phkResult
0x1810f61e4  xor     r8d, r8d; ulOptions
0x1810f61e7  mov     rdx, rbx; lpSubKey
0x1810f61ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1810f61f1  call    cs:__imp_RegOpenKeyExW
0x1810f61f8  nop     dword ptr [rax+rax+00h]
0x1810f61fd  test    eax, eax
0x1810f61ff  jnz     short loc_1810F6258
0x1810f6201  mov     rcx, [rbp+hKey]; hKey
0x1810f6205  lea     rdx, aEnabletridentw; "EnableTridentWebFilter"
0x1810f620c  mov     dword ptr [rbp+Data], eax
0x1810f620f  xor     r9d, r9d; lpType
0x1810f6212  lea     rax, [rbp+cbData]
0x1810f6216  mov     [rbp+cbData], 4
0x1810f621d  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1810f6222  xor     r8d, r8d; lpReserved
0x1810f6225  lea     rax, [rbp+Data]
0x1810f6229  mov     [rsp+68h+phkResult], rax; lpData
0x1810f622e  call    cs:__imp_RegQueryValueExW
0x1810f6235  nop     dword ptr [rax+rax+00h]
0x1810f623a  test    eax, eax
0x1810f623c  jnz     short loc_1810F6248
0x1810f623e  cmp     dword ptr [rbp+Data], eax
0x1810f6241  setnz   cs:byte_1815C5E1D
0x1810f6248  mov     rcx, [rbp+hKey]; hKey
0x1810f624c  call    cs:__imp_RegCloseKey
0x1810f6253  nop     dword ptr [rax+rax+00h]
0x1810f6258  mov     rcx, cs:g_hProcessHeap; this
0x1810f625f  mov     rdx, rbx; void *
0x1810f6262  call    ?HeapFree@MemoryProtection@@YAHPEAX0@Z; MemoryProtection::HeapFree(void *,void *)
0x1810f6267  mov     rcx, [rbp+StringSid]; hMem
0x1810f626b  call    cs:__imp_LocalFree
0x1810f6272  nop     dword ptr [rax+rax+00h]
0x1810f6277  mov     rcx, [rbp+Sid]; hMem
0x1810f627b  call    cs:__imp_LocalFree
0x1810f6282  nop     dword ptr [rax+rax+00h]
0x1810f6287  mov     rcx, [rbp+TokenHandle]; hObject
0x1810f628b  call    cs:__imp_CloseHandle
0x1810f6292  nop     dword ptr [rax+rax+00h]
0x1810f6297  mov     cs:byte_1815C5E1C, 1
0x1810f629e  movzx   eax, cs:byte_1815C5E1D
0x1810f62a5  add     rsp, 68h
0x1810f62a9  pop     rdi
0x1810f62aa  pop     rsi
0x1810f62ab  pop     rbx
0x1810f62ac  pop     rbp
0x1810f62ad  retn
```
