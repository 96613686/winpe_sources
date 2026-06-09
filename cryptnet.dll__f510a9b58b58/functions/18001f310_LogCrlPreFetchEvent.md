# _LogCrlPreFetchEvent

- ea: `0x18001f310`
- end: `0x18001f3d7`
- name: `_LogCrlPreFetchEvent`
- size: `199`
- prototype: `void __fastcall(__int64, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dde0`
- `0x18001e660`
- `0x18001f61c`

## callees

- `0x18000a990`
- `0x18001eb48`
- `0x18001ec64`
- `0x18001f310`
- `0x18001f4fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f3be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f3be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f32b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f32b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f380`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f380`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f35d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f35d`

## string_xrefs

- `0x18001f342`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config\CrlPreFetch`

## pseudocode

```c
void __fastcall LogCrlPreFetchEvent(__int64 a1, __int64 a2, unsigned int a3)
{
  DWORD LastError; // eax
  DWORD v7; // esi
  void *SZValueFromRegistry; // rbx
  __int64 Event; // rax
  void *v10; // rdi
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  LastError = GetLastError();
  hKey = 0;
  v7 = LastError;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config\\CrlPreFetch",
          0,
          0x20119u,
          &hKey) )
  {
    SZValueFromRegistry = (void *)ReadSZValueFromRegistry(hKey, L"LogFileName");
    RegCloseKey(hKey);
    if ( SZValueFromRegistry )
    {
      Event = FormatCrlPreFetchEvent(a1, a2, a3);
      v10 = (void *)Event;
      if ( Event )
      {
        AppendCrlPreFetchEventToLogFile(SZValueFromRegistry, Event);
        operator delete(v10);
      }
      operator delete(SZValueFromRegistry);
    }
  }
  SetLastError(v7);
}

```

## disassembly

```asm
0x18001f310  mov     [rsp+arg_0], rbx
0x18001f315  mov     [rsp+arg_8], rbp
0x18001f31a  push    rsi
0x18001f31b  push    rdi
0x18001f31c  push    r14
0x18001f31e  sub     rsp, 30h
0x18001f322  mov     edi, r8d
0x18001f325  mov     rbp, rdx
0x18001f328  mov     r14, rcx
0x18001f32b  call    cs:__imp_GetLastError
0x18001f331  mov     r9d, 20119h; samDesired
0x18001f337  mov     [rsp+48h+hKey], 0
0x18001f340  mov     esi, eax
0x18001f342  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\OID"...
0x18001f349  lea     rax, [rsp+48h+hKey]
0x18001f34e  xor     r8d, r8d; ulOptions
0x18001f351  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f358  mov     [rsp+48h+phkResult], rax; phkResult
0x18001f35d  call    cs:__imp_RegOpenKeyExW
0x18001f363  test    eax, eax
0x18001f365  jnz     short loc_18001F3BC
0x18001f367  mov     rcx, [rsp+48h+hKey]; hKey
0x18001f36c  lea     rdx, aLogfilename; "LogFileName"
0x18001f373  call    _ReadSZValueFromRegistry
0x18001f378  mov     rcx, [rsp+48h+hKey]; hKey
0x18001f37d  mov     rbx, rax
0x18001f380  call    cs:__imp_RegCloseKey
0x18001f386  test    rbx, rbx
0x18001f389  jz      short loc_18001F3BC
0x18001f38b  mov     r8d, edi
0x18001f38e  mov     rdx, rbp
0x18001f391  mov     rcx, r14
0x18001f394  call    _FormatCrlPreFetchEvent
0x18001f399  mov     rdi, rax
0x18001f39c  test    rax, rax
0x18001f39f  jz      short loc_18001F3B4
0x18001f3a1  mov     rdx, rax
0x18001f3a4  mov     rcx, rbx
0x18001f3a7  call    _AppendCrlPreFetchEventToLogFile
0x18001f3ac  mov     rcx, rdi; hMem
0x18001f3af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f3b4  mov     rcx, rbx; hMem
0x18001f3b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f3bc  mov     ecx, esi; dwErrCode
0x18001f3be  call    cs:__imp_SetLastError
0x18001f3c4  mov     rbx, [rsp+48h+arg_0]
0x18001f3c9  mov     rbp, [rsp+48h+arg_8]
0x18001f3ce  add     rsp, 30h
0x18001f3d2  pop     r14
0x18001f3d4  pop     rdi
0x18001f3d5  pop     rsi
0x18001f3d6  retn
```
