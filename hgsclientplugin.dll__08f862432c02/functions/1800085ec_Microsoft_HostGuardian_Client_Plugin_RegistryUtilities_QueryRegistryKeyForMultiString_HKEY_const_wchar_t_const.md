# Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString(HKEY__ * const,wchar_t const *,wchar_t const *)

- ea: `0x1800085ec`
- end: `0x1800087d7`
- name: `?QueryRegistryKeyForMultiString@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAUHKEY__@@PEB_W1@Z`
- size: `491`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800065c0`

## callees

- `0x180001520`
- `0x1800018f0`
- `0x180001970`
- `0x180001f9e`
- `0x180005ad8`
- `0x180005e18`
- `0x180005f34`
- `0x180006260`
- `0x180006b00`
- `0x1800085ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000865f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000865f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800086a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000870f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800086a6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000870f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800087a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800087a9`

## string_xrefs

- `0x180008699`: `FallbackService`
- `0x180008702`: `FallbackService`
- `0x180008789`: `FallbackService`
- `0x18000866f`: `Failed to call RegOpenKeyEx. subKey: %ws. Error code:0X%08X`

## pseudocode

```c
_QWORD *__fastcall Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString(
        _QWORD *a1)
{
  unsigned int v2; // eax
  unsigned int ValueW; // eax
  DWORD v4; // ebx
  void *pvData; // rsi
  unsigned __int64 v6; // rdx
  _WORD *v7; // rbx
  DWORD pcbData; // [rsp+40h] [rbp-9h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-1h] BYREF
  int v11; // [rsp+50h] [rbp+7h]
  DWORD pdwType; // [rsp+54h] [rbp+Bh] BYREF
  _QWORD *v13; // [rsp+58h] [rbp+Fh]
  void *v14; // [rsp+60h] [rbp+17h]
  _BYTE v15[16]; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v16; // [rsp+78h] [rbp+2Fh]

  v13 = a1;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v11 = 1;
  pcbData = 0;
  hkey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\HgsClient", 0, 0x20019u, &hkey);
  if ( v2 )
  {
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
      (wchar_t *)L"Failed to call RegOpenKeyEx. subKey: %ws. Error code:0X%08X",
      L"SOFTWARE\\Microsoft\\HgsClient",
      v2);
  }
  else
  {
    ValueW = RegGetValueW(hkey, 0, L"FallbackService", 0x20u, 0, 0, &pcbData);
    if ( ValueW || !pcbData )
    {
      Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
        (wchar_t *)L"Failed to call RegGetValue or bufferSize is 0. subKey: %ws. valueName: %ws. Error code:0X%08X",
        L"SOFTWARE\\Microsoft\\HgsClient",
        L"FallbackService",
        ValueW);
    }
    else
    {
      pdwType = 0;
      v4 = pcbData;
      pvData = operator new[](pcbData);
      memset_0(pvData, 0, v4);
      v14 = pvData;
      v11 = 3;
      if ( !RegGetValueW(hkey, 0, L"FallbackService", 0x20u, &pdwType, pvData, &pcbData) && pdwType == 7 )
      {
        v7 = pvData;
        while ( *v7 )
        {
          std::wstring::wstring(v15);
          if ( a1[1] == a1[2] )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1, a1[1], v15);
          }
          else
          {
            std::wstring::wstring(a1[1], v15);
            a1[1] += 32LL;
          }
          v7 += v16 + 1;
          std::wstring::~wstring(v15);
        }
      }
      operator delete(pvData, v6);
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return a1;
}

```

## disassembly

```asm
0x1800085ec  mov     [rsp-8+arg_8], rbx
0x1800085f1  mov     [rsp-8+arg_10], rsi
0x1800085f6  push    rbp
0x1800085f7  push    rdi
0x1800085f8  push    r14
0x1800085fa  lea     rbp, [rsp-47h]
0x1800085ff  sub     rsp, 90h
0x180008606  mov     rax, cs:__security_cookie
0x18000860d  xor     rax, rsp
0x180008610  mov     [rbp+57h+var_18], rax
0x180008614  mov     rdi, rcx
0x180008617  mov     [rbp+57h+var_48], rcx
0x18000861b  mov     eax, 1
0x180008620  mov     [rbp+57h+var_50], eax
0x180008623  xor     r14d, r14d
0x180008626  mov     [rcx], r14
0x180008629  mov     [rcx+8], r14
0x18000862d  mov     [rcx+10h], r14
0x180008631  mov     [rbp+57h+var_50], eax
0x180008634  mov     [rbp+57h+var_60], r14d
0x180008638  mov     [rbp+57h+hkey], r14
0x18000863c  lea     rax, [rbp+57h+hkey]
0x180008640  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180008645  mov     r9d, 20019h; samDesired
0x18000864b  xor     r8d, r8d; ulOptions
0x18000864e  lea     rbx, aSoftwareMicros; "SOFTWARE\\Microsoft\\HgsClient"
0x180008655  mov     rdx, rbx; lpSubKey
0x180008658  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000865f  call    cs:__imp_RegOpenKeyExW
0x180008665  test    eax, eax
0x180008667  jz      short loc_180008680
0x180008669  mov     r8d, eax
0x18000866c  mov     rdx, rbx; wchar_t *
0x18000866f  lea     rcx, aFailedToCallRe; "Failed to call RegOpenKeyEx. subKey: %w"...
0x180008676  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x18000867b  jmp     loc_1800087A0
0x180008680  lea     rax, [rbp+57h+var_60]
0x180008684  mov     [rsp+0A0h+pcbData], rax; pcbData
0x180008689  mov     [rsp+0A0h+pvData], r14; pvData
0x18000868e  mov     [rsp+0A0h+phkResult], r14; pdwType
0x180008693  mov     r9d, 20h ; ' '; dwFlags
0x180008699  lea     r8, aFallbackservic; "FallbackService"
0x1800086a0  xor     edx, edx; lpSubKey
0x1800086a2  mov     rcx, [rbp+57h+hkey]; hkey
0x1800086a6  call    cs:__imp_RegGetValueW
0x1800086ac  test    eax, eax
0x1800086ae  jnz     loc_180008786
0x1800086b4  mov     ecx, [rbp+57h+var_60]; unsigned __int64
0x1800086b7  test    ecx, ecx
0x1800086b9  jz      loc_180008786
0x1800086bf  mov     [rbp+57h+pdwType], r14d
0x1800086c3  mov     ebx, ecx
0x1800086c5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800086ca  mov     rsi, rax
0x1800086cd  mov     r8d, ebx; Size
0x1800086d0  xor     edx, edx; Val
0x1800086d2  mov     rcx, rax; void *
0x1800086d5  call    memset_0
0x1800086da  mov     [rbp+57h+var_40], rsi
0x1800086de  mov     [rbp+57h+var_50], 3
0x1800086e5  lea     rax, [rbp+57h+var_60]
0x1800086e9  mov     [rsp+0A0h+pcbData], rax; pcbData
0x1800086ee  mov     [rsp+0A0h+pvData], rsi; pvData
0x1800086f3  lea     rax, [rbp+57h+pdwType]
0x1800086f7  mov     [rsp+0A0h+phkResult], rax; pdwType
0x1800086fc  mov     r9d, 20h ; ' '; dwFlags
0x180008702  lea     r8, aFallbackservic; "FallbackService"
0x180008709  xor     edx, edx; lpSubKey
0x18000870b  mov     rcx, [rbp+57h+hkey]; hkey
0x18000870f  call    cs:__imp_RegGetValueW
0x180008715  test    eax, eax
0x180008717  jnz     short loc_18000877C
0x180008719  cmp     [rbp+57h+pdwType], 7
0x18000871d  jnz     short loc_18000877C
0x18000871f  mov     rbx, rsi
0x180008722  cmp     [rsi], r14w
0x180008726  jz      short loc_18000877C
0x180008728  mov     rdx, rbx
0x18000872b  lea     rcx, [rbp+57h+var_38]
0x18000872f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180008734  nop
0x180008735  mov     rax, [rdi+8]
0x180008739  cmp     rax, [rdi+10h]
0x18000873d  jz      short loc_180008752
0x18000873f  lea     rdx, [rbp+57h+var_38]
0x180008743  mov     rcx, rax
0x180008746  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000874b  add     qword ptr [rdi+8], 20h ; ' '
0x180008750  jmp     short loc_180008761
0x180008752  lea     r8, [rbp+57h+var_38]
0x180008756  mov     rdx, rax
0x180008759  mov     rcx, rdi
0x18000875c  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180008761  mov     rax, [rbp+57h+var_28]
0x180008765  lea     rbx, [rbx+rax*2]
0x180008769  add     rbx, 2
0x18000876d  lea     rcx, [rbp+57h+var_38]
0x180008771  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008776  cmp     [rbx], r14w
0x18000877a  jnz     short loc_180008728
0x18000877c  mov     rcx, rsi; void *
0x18000877f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008784  jmp     short loc_1800087A0
0x180008786  mov     r9d, eax
0x180008789  lea     r8, aFallbackservic; "FallbackService"
0x180008790  mov     rdx, rbx; wchar_t *
0x180008793  lea     rcx, aFailedToCallRe_3; "Failed to call RegGetValue or bufferSiz"...
0x18000879a  call    ?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)
0x18000879f  nop
0x1800087a0  mov     rcx, [rbp+57h+hkey]; hKey
0x1800087a4  test    rcx, rcx
0x1800087a7  jz      short loc_1800087B0
0x1800087a9  call    cs:__imp_RegCloseKey
0x1800087af  nop
0x1800087b0  mov     rax, rdi
0x1800087b3  mov     rcx, [rbp+57h+var_18]
0x1800087b7  xor     rcx, rsp; StackCookie
0x1800087ba  call    __security_check_cookie
0x1800087bf  lea     r11, [rsp+0A0h+var_10]
0x1800087c7  mov     rbx, [r11+28h]
0x1800087cb  mov     rsi, [r11+30h]
0x1800087cf  mov     rsp, r11
0x1800087d2  pop     r14
0x1800087d4  pop     rdi
0x1800087d5  pop     rbp
0x1800087d6  retn
```
