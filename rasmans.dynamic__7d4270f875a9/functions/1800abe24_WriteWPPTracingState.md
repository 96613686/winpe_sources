# WriteWPPTracingState

- ea: `0x1800abe24`
- end: `0x1800ac097`
- name: `WriteWPPTracingState`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800aba58`

## callees

- `0x18000eb54`
- `0x1800aa0f4`
- `0x1800abe24`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800abf42`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800abf75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800abfa8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac009`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac04b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800abf42`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800abf75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800abfa8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac009`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac04b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ac061`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ac061`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800abf04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800abf04`

## string_xrefs

- `0x1800abeb0`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
__int64 __fastcall WriteWPPTracingState(__int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rdi
  __int64 v4; // rax
  const BYTE *v5; // rdx
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v9[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v10[524]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR SubKey[2]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v12[524]; // [rsp+274h] [rbp+174h] BYREF

  hKey = 0;
  *(_DWORD *)SubKey = 0;
  v2 = 0;
  memset_0(v12, 0, 0x206u);
  *(_DWORD *)v9 = 0;
  memset_0(v10, 0, 0x206u);
  if ( a1 && *(_QWORD *)(a1 + 32) )
  {
    StringCchPrintfW(
      SubKey,
      0x105u,
      L"%s%s",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
      a1 + 562);
    if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0) )
    {
      *(_DWORD *)Data = *(_DWORD *)a1;
      RegSetValueExW(hKey, L"Active", 0, 4u, Data, 4u);
      *(_DWORD *)Data = *(_DWORD *)(a1 + 4);
      RegSetValueExW(hKey, L"ControlFlags", 0, 4u, Data, 4u);
      *(_DWORD *)Data = *(_DWORD *)(a1 + 8);
      RegSetValueExW(hKey, L"ControlLevel", 0, 4u, Data, 4u);
      ConvertGuid2String(a1 + 12, 261, v9);
      v3 = -1;
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)&v9[2 * v4] );
      v2 = 1;
      RegSetValueExW(hKey, L"Guid", 0, 1u, v9, 2 * v4 + 2);
      v5 = (const BYTE *)(*(_QWORD *)(a1 + 32) + *(unsigned int *)(*(_QWORD *)(a1 + 32) + 112LL));
      do
        ++v3;
      while ( *(_WORD *)&v5[2 * v3] );
      RegSetValueExW(hKey, L"LogFileName", 0, 1u, v5, 2 * v3 + 2);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800abe24  mov     [rsp-8+arg_8], rbx
0x1800abe29  mov     [rsp-8+arg_10], rsi
0x1800abe2e  push    rbp
0x1800abe2f  push    rdi
0x1800abe30  push    r14
0x1800abe32  lea     rbp, [rsp-390h]
0x1800abe3a  sub     rsp, 490h
0x1800abe41  mov     rax, cs:__security_cookie
0x1800abe48  xor     rax, rsp
0x1800abe4b  mov     [rbp+3A0h+var_20], rax
0x1800abe52  xor     r14d, r14d
0x1800abe55  mov     rbx, rcx
0x1800abe58  mov     edi, 206h
0x1800abe5d  mov     [rsp+4A0h+hKey], r14
0x1800abe62  mov     r8d, edi; Size
0x1800abe65  mov     dword ptr [rbp+3A0h+SubKey], r14d
0x1800abe6c  xor     edx, edx; Val
0x1800abe6e  lea     rcx, [rbp+3A0h+var_22C]; void *
0x1800abe75  mov     esi, r14d
0x1800abe78  call    memset_0
0x1800abe7d  mov     r8d, edi; Size
0x1800abe80  mov     dword ptr [rsp+4A0h+var_440], r14d
0x1800abe85  xor     edx, edx; Val
0x1800abe87  lea     rcx, [rsp+4A0h+var_43C]; void *
0x1800abe8c  call    memset_0
0x1800abe91  test    rbx, rbx
0x1800abe94  jz      loc_1800AC06D
0x1800abe9a  cmp     [rbx+20h], r14
0x1800abe9e  jz      loc_1800AC06D
0x1800abea4  lea     rax, [rbx+232h]
0x1800abeab  mov     edx, 105h; unsigned __int64
0x1800abeb0  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800abeb7  mov     qword ptr [rsp+4A0h+dwOptions], rax
0x1800abebc  lea     r8, aSS_3; "%s%s"
0x1800abec3  lea     rcx, [rbp+3A0h+SubKey]; unsigned __int16 *
0x1800abeca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800abecf  mov     [rsp+4A0h+lpdwDisposition], r14; lpdwDisposition
0x1800abed4  lea     rax, [rsp+4A0h+hKey]
0x1800abed9  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800abede  lea     rdx, [rbp+3A0h+SubKey]; lpSubKey
0x1800abee5  mov     [rsp+4A0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800abeea  xor     r9d, r9d; lpClass
0x1800abeed  mov     [rsp+4A0h+samDesired], 20006h; samDesired
0x1800abef5  xor     r8d, r8d; Reserved
0x1800abef8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800abeff  mov     [rsp+4A0h+dwOptions], r14d; dwOptions
0x1800abf04  call    cs:__imp_RegCreateKeyExW
0x1800abf0b  nop     dword ptr [rax+rax+00h]
0x1800abf10  test    eax, eax
0x1800abf12  jnz     loc_1800AC057
0x1800abf18  mov     eax, [rbx]
0x1800abf1a  lea     edi, [r14+4]
0x1800abf1e  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800abf23  lea     rdx, aActive_0; "Active"
0x1800abf2a  mov     dword ptr [rsp+4A0h+Data], eax
0x1800abf2e  mov     r9d, edi; dwType
0x1800abf31  lea     rax, [rsp+4A0h+Data]
0x1800abf36  mov     [rsp+4A0h+samDesired], edi; cbData
0x1800abf3a  xor     r8d, r8d; Reserved
0x1800abf3d  mov     qword ptr [rsp+4A0h+dwOptions], rax; lpData
0x1800abf42  call    cs:__imp_RegSetValueExW
0x1800abf49  nop     dword ptr [rax+rax+00h]
0x1800abf4e  mov     eax, [rbx+4]
0x1800abf51  lea     rdx, aControlflags; "ControlFlags"
0x1800abf58  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800abf5d  mov     r9d, edi; dwType
0x1800abf60  mov     dword ptr [rsp+4A0h+Data], eax
0x1800abf64  xor     r8d, r8d; Reserved
0x1800abf67  lea     rax, [rsp+4A0h+Data]
0x1800abf6c  mov     [rsp+4A0h+samDesired], edi; cbData
0x1800abf70  mov     qword ptr [rsp+4A0h+dwOptions], rax; lpData
0x1800abf75  call    cs:__imp_RegSetValueExW
0x1800abf7c  nop     dword ptr [rax+rax+00h]
0x1800abf81  mov     eax, [rbx+8]
0x1800abf84  lea     rdx, aControllevel; "ControlLevel"
0x1800abf8b  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800abf90  mov     r9d, edi; dwType
0x1800abf93  mov     dword ptr [rsp+4A0h+Data], eax
0x1800abf97  xor     r8d, r8d; Reserved
0x1800abf9a  lea     rax, [rsp+4A0h+Data]
0x1800abf9f  mov     [rsp+4A0h+samDesired], edi; cbData
0x1800abfa3  mov     qword ptr [rsp+4A0h+dwOptions], rax; lpData
0x1800abfa8  call    cs:__imp_RegSetValueExW
0x1800abfaf  nop     dword ptr [rax+rax+00h]
0x1800abfb4  lea     rcx, [rbx+0Ch]
0x1800abfb8  mov     edx, 105h
0x1800abfbd  lea     r8, [rsp+4A0h+var_440]
0x1800abfc2  call    ConvertGuid2String
0x1800abfc7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800abfcb  lea     rcx, [rsp+4A0h+var_440]
0x1800abfd0  mov     rax, rdi
0x1800abfd3  inc     rax
0x1800abfd6  cmp     [rcx+rax*2], r14w
0x1800abfdb  jnz     short loc_1800ABFD3
0x1800abfdd  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800abfe2  lea     eax, ds:2[rax*2]
0x1800abfe9  mov     [rsp+4A0h+samDesired], eax; cbData
0x1800abfed  lea     rdx, aGuid_0; "Guid"
0x1800abff4  lea     rax, [rsp+4A0h+var_440]
0x1800abff9  mov     esi, 1
0x1800abffe  mov     r9d, esi; dwType
0x1800ac001  mov     qword ptr [rsp+4A0h+dwOptions], rax; lpData
0x1800ac006  xor     r8d, r8d; Reserved
0x1800ac009  call    cs:__imp_RegSetValueExW
0x1800ac010  nop     dword ptr [rax+rax+00h]
0x1800ac015  mov     rcx, [rbx+20h]
0x1800ac019  mov     edx, [rcx+70h]
0x1800ac01c  add     rdx, rcx
0x1800ac01f  inc     rdi
0x1800ac022  cmp     [rdx+rdi*2], r14w
0x1800ac027  jnz     short loc_1800AC01F
0x1800ac029  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800ac02e  lea     eax, ds:2[rdi*2]
0x1800ac035  mov     [rsp+4A0h+samDesired], eax; cbData
0x1800ac039  mov     r9d, esi; dwType
0x1800ac03c  mov     qword ptr [rsp+4A0h+dwOptions], rdx; lpData
0x1800ac041  xor     r8d, r8d; Reserved
0x1800ac044  lea     rdx, aLogfilename; "LogFileName"
0x1800ac04b  call    cs:__imp_RegSetValueExW
0x1800ac052  nop     dword ptr [rax+rax+00h]
0x1800ac057  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800ac05c  test    rcx, rcx
0x1800ac05f  jz      short loc_1800AC06D
0x1800ac061  call    cs:__imp_RegCloseKey
0x1800ac068  nop     dword ptr [rax+rax+00h]
0x1800ac06d  mov     eax, esi
0x1800ac06f  mov     rcx, [rbp+3A0h+var_20]
0x1800ac076  xor     rcx, rsp; StackCookie
0x1800ac079  call    __security_check_cookie
0x1800ac07e  lea     r11, [rsp+4A0h+var_10]
0x1800ac086  mov     rbx, [r11+28h]
0x1800ac08a  mov     rsi, [r11+30h]
0x1800ac08e  mov     rsp, r11
0x1800ac091  pop     r14
0x1800ac093  pop     rdi
0x1800ac094  pop     rbp
0x1800ac095  retn
```
