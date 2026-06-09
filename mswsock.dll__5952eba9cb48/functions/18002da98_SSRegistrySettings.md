# SSRegistrySettings

- ea: `0x18002da98`
- end: `0x18002dcb5`
- name: `SSRegistrySettings`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002df24`

## callees

- `0x1800119a0`
- `0x18001757c`
- `0x18002da98`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002dc3c`
- `ntdll!RtlFreeHeap` at `0x18002dc3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dc4a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002daf7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002db53`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002daf7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002db53`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc22`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dc22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dc99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002dc87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002dc87`
- `RPCRT4!UuidToStringW` at `0x18002db6e`
- `RPCRT4!UuidToStringW` at `0x18002db6e`
- `RPCRT4!RpcStringFreeW` at `0x18002dc5c`
- `RPCRT4!RpcStringFreeW` at `0x18002dc5c`

## string_xrefs

- `0x18002dae5`: `SYSTEM\CurrentControlSet\Control\ServiceProvider\ServiceTypes`

## pseudocode

```c
__int64 __fastcall SSRegistrySettings(int a1, const WCHAR *a2, const UUID *a3)
{
  DWORD LastError; // ebx
  unsigned __int64 v7; // rax
  __int64 v8; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // rdi
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+C8h] [rbp+50h] BYREF

  hKey = 0;
  dwDisposition = 0;
  LastError = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\CurrentControlSet\\Control\\ServiceProvider\\ServiceTypes",
                0,
                (LPWSTR)&Data,
                0,
                0x2001Fu,
                0,
                &hKey,
                &dwDisposition);
  if ( !LastError )
  {
    if ( a1 == 4 )
    {
      phkResult = 0;
      StringUuid = 0;
      if ( RegCreateKeyExW(hKey, a2, 0, (LPWSTR)&Data, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
      {
        LastError = RegDeleteKeyExW(hKey, a2, 0, 0);
      }
      else
      {
        LastError = UuidToStringW(a3, &StringUuid);
        if ( !LastError )
        {
          v7 = -1;
          do
            ++v7;
          while ( StringUuid[v7] );
          if ( v7 <= 0x7FFC )
          {
            v8 = 2 * v7 + 6;
            v9 = (wchar_t *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                              SockPrivateHeap,
                              0,
                              (unsigned int)v8);
            v10 = v9;
            if ( v9 )
            {
              StringCbCopyW(v9, v8, L"{");
              StringCbCatW(v10, v8, StringUuid);
              StringCbCatW(v10, v8, L"}");
              LastError = RegSetValueExW(phkResult, L"GUID", 0, 1u, (const BYTE *)v10, v8);
              RtlFreeHeap(SockPrivateHeap, 0, v10);
            }
            else
            {
              LastError = GetLastError();
            }
          }
          else
          {
            LastError = 534;
          }
          RpcStringFreeW(&StringUuid);
        }
        RegCloseKey(phkResult);
      }
    }
    RegCloseKey(hKey);
  }
  return LastError;
}

```

## disassembly

```asm
0x18002da98  push    rbp
0x18002da9a  push    rbx
0x18002da9b  push    rsi
0x18002da9c  push    rdi
0x18002da9d  push    r14
0x18002da9f  push    r15
0x18002daa1  mov     rbp, rsp
0x18002daa4  sub     rsp, 78h
0x18002daa8  xor     r15d, r15d
0x18002daab  lea     rax, [rbp+dwDisposition]
0x18002daaf  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18002dab4  lea     r9, Data; lpClass
0x18002dabb  lea     rax, [rbp+hKey]
0x18002dabf  mov     [rbp+hKey], r15
0x18002dac3  mov     [rsp+78h+phkResult], rax; phkResult
0x18002dac8  mov     r14, r8
0x18002dacb  mov     [rsp+78h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002dad0  mov     rdi, rdx
0x18002dad3  mov     esi, ecx
0x18002dad5  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18002dadd  xor     r8d, r8d; Reserved
0x18002dae0  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x18002dae5  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Ser"...
0x18002daec  mov     [rbp+dwDisposition], r15d
0x18002daf0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002daf7  call    cs:__imp_RegCreateKeyExW
0x18002dafe  nop     dword ptr [rax+rax+00h]
0x18002db03  mov     ebx, eax
0x18002db05  test    eax, eax
0x18002db07  jnz     loc_18002DCA5
0x18002db0d  cmp     esi, 4
0x18002db10  jnz     loc_18002DC95
0x18002db16  mov     rcx, [rbp+hKey]; hKey
0x18002db1a  lea     rax, [rbp+dwDisposition]
0x18002db1e  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18002db23  lea     r9, Data; lpClass
0x18002db2a  lea     rax, [rbp+var_18]
0x18002db2e  mov     [rbp+var_18], r15
0x18002db32  mov     [rsp+78h+phkResult], rax; phkResult
0x18002db37  xor     r8d, r8d; Reserved
0x18002db3a  mov     [rsp+78h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18002db3f  mov     rdx, rdi; lpSubKey
0x18002db42  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18002db4a  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x18002db4f  mov     [rbp+StringUuid], r15
0x18002db53  call    cs:__imp_RegCreateKeyExW
0x18002db5a  nop     dword ptr [rax+rax+00h]
0x18002db5f  test    eax, eax
0x18002db61  jnz     loc_18002DC7A
0x18002db67  lea     rdx, [rbp+StringUuid]; StringUuid
0x18002db6b  mov     rcx, r14; Uuid
0x18002db6e  call    cs:__imp_UuidToStringW
0x18002db75  nop     dword ptr [rax+rax+00h]
0x18002db7a  mov     ebx, eax
0x18002db7c  test    eax, eax
0x18002db7e  jnz     loc_18002DC68
0x18002db84  mov     rcx, [rbp+StringUuid]
0x18002db88  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002db8c  inc     rax
0x18002db8f  cmp     [rcx+rax*2], r15w
0x18002db94  jnz     short loc_18002DB8C
0x18002db96  cmp     rax, 7FFCh
0x18002db9c  jbe     short loc_18002DBA8
0x18002db9e  mov     ebx, 216h
0x18002dba3  jmp     loc_18002DC58
0x18002dba8  mov     rcx, cs:SockPrivateHeap
0x18002dbaf  lea     rbx, ds:6[rax*2]
0x18002dbb7  mov     rax, cs:SockAllocateHeapRoutine
0x18002dbbe  xor     edx, edx
0x18002dbc0  mov     r8d, ebx
0x18002dbc3  mov     esi, ebx
0x18002dbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbca  mov     rdi, rax
0x18002dbcd  test    rax, rax
0x18002dbd0  jz      short loc_18002DC4A
0x18002dbd2  lea     r8, asc_18005692C; "{"
0x18002dbd9  mov     rdx, rbx; cbDest
0x18002dbdc  mov     rcx, rax; pszDest
0x18002dbdf  call    StringCbCopyW
0x18002dbe4  mov     r8, [rbp+StringUuid]; pszSrc
0x18002dbe8  mov     rdx, rbx; cbDest
0x18002dbeb  mov     rcx, rdi; pszDest
0x18002dbee  call    StringCbCatW
0x18002dbf3  lea     r8, asc_180056930; "}"
0x18002dbfa  mov     rdx, rbx; cbDest
0x18002dbfd  mov     rcx, rdi; pszDest
0x18002dc00  call    StringCbCatW
0x18002dc05  mov     rcx, [rbp+var_18]; hKey
0x18002dc09  lea     rdx, aGuid; "GUID"
0x18002dc10  mov     r9d, 1; dwType
0x18002dc16  mov     [rsp+78h+samDesired], esi; cbData
0x18002dc1a  xor     r8d, r8d; Reserved
0x18002dc1d  mov     qword ptr [rsp+78h+dwOptions], rdi; lpData
0x18002dc22  call    cs:__imp_RegSetValueExW
0x18002dc29  nop     dword ptr [rax+rax+00h]
0x18002dc2e  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002dc35  mov     r8, rdi; P
0x18002dc38  xor     edx, edx; Flags
0x18002dc3a  mov     ebx, eax
0x18002dc3c  call    cs:__imp_RtlFreeHeap
0x18002dc43  nop     dword ptr [rax+rax+00h]
0x18002dc48  jmp     short loc_18002DC58
0x18002dc4a  call    cs:__imp_GetLastError
0x18002dc51  nop     dword ptr [rax+rax+00h]
0x18002dc56  mov     ebx, eax
0x18002dc58  lea     rcx, [rbp+StringUuid]; String
0x18002dc5c  call    cs:__imp_RpcStringFreeW
0x18002dc63  nop     dword ptr [rax+rax+00h]
0x18002dc68  mov     rcx, [rbp+var_18]; hKey
0x18002dc6c  call    cs:__imp_RegCloseKey
0x18002dc73  nop     dword ptr [rax+rax+00h]
0x18002dc78  jmp     short loc_18002DC95
0x18002dc7a  mov     rcx, [rbp+hKey]; hKey
0x18002dc7e  xor     r9d, r9d; Reserved
0x18002dc81  xor     r8d, r8d; samDesired
0x18002dc84  mov     rdx, rdi; lpSubKey
0x18002dc87  call    cs:__imp_RegDeleteKeyExW
0x18002dc8e  nop     dword ptr [rax+rax+00h]
0x18002dc93  mov     ebx, eax
0x18002dc95  mov     rcx, [rbp+hKey]; hKey
0x18002dc99  call    cs:__imp_RegCloseKey
0x18002dca0  nop     dword ptr [rax+rax+00h]
0x18002dca5  mov     eax, ebx
0x18002dca7  add     rsp, 78h
0x18002dcab  pop     r15
0x18002dcad  pop     r14
0x18002dcaf  pop     rdi
0x18002dcb0  pop     rsi
0x18002dcb1  pop     rbx
0x18002dcb2  pop     rbp
0x18002dcb3  retn
```
