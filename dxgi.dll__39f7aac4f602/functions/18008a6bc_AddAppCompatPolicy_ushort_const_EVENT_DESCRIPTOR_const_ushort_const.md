# AddAppCompatPolicy(ushort const *,_EVENT_DESCRIPTOR const *,ushort const *)

- ea: `0x18008a6bc`
- end: `0x18008a8f6`
- name: `?AddAppCompatPolicy@@YAXPEBGPEBU_EVENT_DESCRIPTOR@@0@Z`
- size: `570`
- prototype: `void __fastcall(const unsigned __int16 *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008a8fc`
- `0x18009beec`

## callees

- `0x18001b22c`
- `0x18001c574`
- `0x18004db5c`
- `0x180075fa0`
- `0x18008a6bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18008a80d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18008a80d`
- `ntdll!EtwEventWriteNoRegistration` at `0x18008a870`
- `ntdll!EtwEventWriteNoRegistration` at `0x18008a8ba`
- `ntdll!EtwEventWriteNoRegistration` at `0x18008a870`
- `ntdll!EtwEventWriteNoRegistration` at `0x18008a8ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008a74e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008a74e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008a786`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008a7fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008a786`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008a7fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008a8c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008a8c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008a855`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008a89f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008a855`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008a89f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008a731`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008a731`

## string_xrefs

- `0x18008a703`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
void __fastcall AddAppCompatPolicy(const BYTE *a1, const struct _EVENT_DESCRIPTOR *a2, const unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  __int64 v6; // rcx
  DWORD v7; // r15d
  unsigned __int16 *v8; // rbx
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  hkey = 0;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &hkey,
          0) )
  {
    if ( GetModuleFileNameW(0, Filename, 0x104u) < 0x104 )
    {
      pcbData = 0;
      ValueW = RegGetValueW(hkey, 0, Filename, 2u, 0, 0, &pcbData);
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&a1[2 * v6] );
      if ( ValueW )
      {
        RegSetValueExW(hkey, Filename, 0, 1u, a1, 2 * v6);
        if ( a2 )
          EtwEventWriteNoRegistration(AE_LOG, a2, 0, 0);
      }
      else
      {
        v7 = v6 + 2 * pcbData + 1;
        v8 = (unsigned __int16 *)operator new(saturated_mul(v7, 2u));
        if ( v8 )
        {
          if ( !RegGetValueW(hkey, 0, Filename, 2u, 0, v8, &pcbData) )
          {
            if ( !wcsstr(v8, (const wchar_t *)a1) )
            {
              StringCchCatW(v8, v7, L" ");
              StringCchCatW(v8, v7, (const unsigned __int16 *)a1);
              RegSetValueExW(hkey, Filename, 0, 1u, (const BYTE *)v8, v7);
            }
            if ( a2 )
              EtwEventWriteNoRegistration(AE_LOG, a2, 0, 0);
          }
          operator delete(v8);
        }
      }
    }
    RegCloseKey(hkey);
  }
}

```

## disassembly

```asm
0x18008a6bc  mov     [rsp-8+arg_10], rbx
0x18008a6c1  mov     [rsp-8+arg_18], rsi
0x18008a6c6  push    rbp
0x18008a6c7  push    rdi
0x18008a6c8  push    r12
0x18008a6ca  push    r14
0x18008a6cc  push    r15
0x18008a6ce  lea     rbp, [rsp-180h]
0x18008a6d6  sub     rsp, 280h
0x18008a6dd  mov     rax, cs:__security_cookie
0x18008a6e4  xor     rax, rsp
0x18008a6e7  mov     [rbp+1A0h+var_30], rax
0x18008a6ee  xor     r12d, r12d
0x18008a6f1  lea     rax, [rsp+2A0h+hkey]
0x18008a6f6  mov     [rsp+2A0h+lpdwDisposition], r12; lpdwDisposition
0x18008a6fb  mov     rdi, rdx
0x18008a6fe  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18008a703  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x18008a70a  mov     [rsp+2A0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18008a70f  mov     rsi, rcx
0x18008a712  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x18008a71a  xor     r9d, r9d; lpClass
0x18008a71d  xor     r8d, r8d; Reserved
0x18008a720  mov     [rsp+2A0h+dwOptions], r12d; dwOptions
0x18008a725  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008a72c  mov     [rsp+2A0h+hkey], r12
0x18008a731  call    cs:__imp_RegCreateKeyExW
0x18008a737  test    eax, eax
0x18008a739  jnz     loc_18008A8CB
0x18008a73f  mov     ebx, 104h
0x18008a744  lea     rdx, [rsp+2A0h+Filename]; lpFilename
0x18008a749  mov     r8d, ebx; nSize
0x18008a74c  xor     ecx, ecx; hModule
0x18008a74e  call    cs:__imp_GetModuleFileNameW
0x18008a754  cmp     eax, ebx
0x18008a756  jnb     loc_18008A8C0
0x18008a75c  mov     rcx, [rsp+2A0h+hkey]; hkey
0x18008a761  lea     rax, [rsp+2A0h+pcbData]
0x18008a766  mov     [rsp+2A0h+lpSecurityAttributes], rax; pcbData
0x18008a76b  lea     r9d, [r12+2]; dwFlags
0x18008a770  mov     qword ptr [rsp+2A0h+samDesired], r12; pvData
0x18008a775  lea     r8, [rsp+2A0h+Filename]; lpValue
0x18008a77a  xor     edx, edx; lpSubKey
0x18008a77c  mov     qword ptr [rsp+2A0h+dwOptions], r12; pdwType
0x18008a781  mov     [rsp+2A0h+pcbData], r12d
0x18008a786  call    cs:__imp_RegGetValueW
0x18008a78c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008a790  mov     rcx, r8
0x18008a793  inc     rcx
0x18008a796  cmp     [rsi+rcx*2], r12w
0x18008a79b  jnz     short loc_18008A793
0x18008a79d  test    eax, eax
0x18008a79f  jnz     loc_18008A880
0x18008a7a5  mov     eax, [rsp+2A0h+pcbData]
0x18008a7a9  lea     r15d, ds:1[rax*2]
0x18008a7b1  mov     eax, 2
0x18008a7b6  add     r15d, ecx
0x18008a7b9  mov     r14d, r15d
0x18008a7bc  mul     r14
0x18008a7bf  cmovb   rax, r8
0x18008a7c3  mov     rcx, rax; dwBytes
0x18008a7c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008a7cb  mov     rbx, rax
0x18008a7ce  test    rax, rax
0x18008a7d1  jz      loc_18008A8C0
0x18008a7d7  mov     rcx, [rsp+2A0h+hkey]; hkey
0x18008a7dc  lea     rax, [rsp+2A0h+pcbData]
0x18008a7e1  mov     [rsp+2A0h+lpSecurityAttributes], rax; pcbData
0x18008a7e6  lea     r8, [rsp+2A0h+Filename]; lpValue
0x18008a7eb  mov     qword ptr [rsp+2A0h+samDesired], rbx; pvData
0x18008a7f0  mov     r9d, 2; dwFlags
0x18008a7f6  xor     edx, edx; lpSubKey
0x18008a7f8  mov     qword ptr [rsp+2A0h+dwOptions], r12; pdwType
0x18008a7fd  call    cs:__imp_RegGetValueW
0x18008a803  test    eax, eax
0x18008a805  jnz     short loc_18008A876
0x18008a807  mov     rdx, rsi; SubStr
0x18008a80a  mov     rcx, rbx; Str
0x18008a80d  call    cs:__imp_wcsstr
0x18008a813  test    rax, rax
0x18008a816  jnz     short loc_18008A85B
0x18008a818  lea     r8, Delimiter; " "
0x18008a81f  mov     edx, r14d; unsigned __int64
0x18008a822  mov     rcx, rbx; unsigned __int16 *
0x18008a825  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008a82a  mov     r8, rsi; unsigned __int16 *
0x18008a82d  mov     edx, r14d; unsigned __int64
0x18008a830  mov     rcx, rbx; unsigned __int16 *
0x18008a833  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008a838  mov     rcx, [rsp+2A0h+hkey]; hKey
0x18008a83d  lea     rdx, [rsp+2A0h+Filename]; lpValueName
0x18008a842  mov     r9d, 1; dwType
0x18008a848  mov     [rsp+2A0h+samDesired], r15d; cbData
0x18008a84d  xor     r8d, r8d; Reserved
0x18008a850  mov     qword ptr [rsp+2A0h+dwOptions], rbx; lpData
0x18008a855  call    cs:__imp_RegSetValueExW
0x18008a85b  test    rdi, rdi
0x18008a85e  jz      short loc_18008A876
0x18008a860  xor     r9d, r9d
0x18008a863  lea     rcx, AE_LOG
0x18008a86a  xor     r8d, r8d
0x18008a86d  mov     rdx, rdi
0x18008a870  call    cs:__imp_EtwEventWriteNoRegistration
0x18008a876  mov     rcx, rbx; lpMem
0x18008a879  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008a87e  jmp     short loc_18008A8C0
0x18008a880  lea     eax, [rcx+rcx]
0x18008a883  mov     r9d, 1; dwType
0x18008a889  mov     rcx, [rsp+2A0h+hkey]; hKey
0x18008a88e  lea     rdx, [rsp+2A0h+Filename]; lpValueName
0x18008a893  mov     [rsp+2A0h+samDesired], eax; cbData
0x18008a897  xor     r8d, r8d; Reserved
0x18008a89a  mov     qword ptr [rsp+2A0h+dwOptions], rsi; lpData
0x18008a89f  call    cs:__imp_RegSetValueExW
0x18008a8a5  test    rdi, rdi
0x18008a8a8  jz      short loc_18008A8C0
0x18008a8aa  xor     r9d, r9d
0x18008a8ad  lea     rcx, AE_LOG
0x18008a8b4  xor     r8d, r8d
0x18008a8b7  mov     rdx, rdi
0x18008a8ba  call    cs:__imp_EtwEventWriteNoRegistration
0x18008a8c0  mov     rcx, [rsp+2A0h+hkey]; hKey
0x18008a8c5  call    cs:__imp_RegCloseKey
0x18008a8cb  mov     rcx, [rbp+1A0h+var_30]
0x18008a8d2  xor     rcx, rsp; StackCookie
0x18008a8d5  call    __security_check_cookie
0x18008a8da  lea     r11, [rsp+2A0h+var_20]
0x18008a8e2  mov     rbx, [r11+40h]
0x18008a8e6  mov     rsi, [r11+48h]
0x18008a8ea  mov     rsp, r11
0x18008a8ed  pop     r15
0x18008a8ef  pop     r14
0x18008a8f1  pop     r12
0x18008a8f3  pop     rdi
0x18008a8f4  pop     rbp
0x18008a8f5  retn
```
