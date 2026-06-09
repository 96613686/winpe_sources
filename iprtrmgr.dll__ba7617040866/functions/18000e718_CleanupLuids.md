# CleanupLuids

- ea: `0x18000e718`
- end: `0x18000e99a`
- name: `CleanupLuids`
- size: `642`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a4f0`

## callees

- `0x18000ac60`
- `0x18000e718`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18000e940`
- `KERNEL32!DeviceIoControl` at `0x18000e940`
- `KERNEL32!GetLastError` at `0x18000e805`
- `KERNEL32!GetLastError` at `0x18000e957`
- `KERNEL32!GetLastError` at `0x18000e805`
- `KERNEL32!GetLastError` at `0x18000e957`
- `KERNEL32!HeapFree` at `0x18000e88b`
- `KERNEL32!HeapFree` at `0x18000e88b`
- `KERNEL32!HeapAlloc` at `0x18000e7f3`
- `KERNEL32!HeapAlloc` at `0x18000e7f3`
- `ADVAPI32!RegOpenKeyExA` at `0x18000e7a1`
- `ADVAPI32!RegOpenKeyExA` at `0x18000e7a1`
- `ADVAPI32!RegQueryValueExA` at `0x18000e7ce`
- `ADVAPI32!RegQueryValueExA` at `0x18000e8d3`
- `ADVAPI32!RegQueryValueExA` at `0x18000e7ce`
- `ADVAPI32!RegQueryValueExA` at `0x18000e8d3`
- `ADVAPI32!RegDeleteKeyA` at `0x18000e81e`
- `ADVAPI32!RegDeleteKeyA` at `0x18000e81e`
- `ADVAPI32!RegCloseKey` at `0x18000e874`
- `ADVAPI32!RegCloseKey` at `0x18000e874`

## string_xrefs

- `0x18000e793`: `System\CurrentControlSet\Services\Rasman\Parameters`
- `0x18000e835`: `CleanupLuids: RegDeleteValue failed with error %d`

## pseudocode

```c
__int64 __fastcall CleanupLuids(HANDLE hDevice)
{
  BYTE *v2; // rsi
  DWORD LastError; // ebx
  DWORD v4; // edi
  unsigned int v6; // edi
  __int64 i; // r14
  DWORD v8; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  int v13; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v14[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  OutBuffer = 0;
  cbData = 0;
  v13 = 0;
  BytesReturned = 0;
  hKey = 0;
  v2 = 0;
  memset_0(v14, 0, sizeof(v14));
  LastError = RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "System\\CurrentControlSet\\Services\\Rasman\\Parameters",
                0,
                0x20007u,
                &hKey);
  if ( LastError )
    goto LABEL_6;
  LastError = RegQueryValueExA(hKey, "AllocatedLuids", 0, 0, 0, &cbData);
  if ( LastError )
    goto LABEL_6;
  v4 = cbData;
  if ( !cbData )
    goto LABEL_17;
  v2 = (BYTE *)HeapAlloc(IPRouterHeap, 8u, cbData);
  if ( !v2 )
  {
    LastError = GetLastError();
    goto LABEL_6;
  }
  LastError = RegQueryValueExA(hKey, "AllocatedLuids", 0, 0, v2, &cbData);
  if ( !LastError )
  {
    v4 = cbData;
LABEL_17:
    v6 = v4 >> 2;
    for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
    {
      LOWORD(OutBuffer) = 23;
      HIDWORD(OutBuffer) = *(_DWORD *)&v2[4 * i];
      if ( !DeviceIoControl(hDevice, 0x90018020, &OutBuffer, 8u, &OutBuffer, 8u, &BytesReturned, 0)
        && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v13) = 0;
        v8 = GetLastError();
        FormatRRASErrorString(&v13, L"CleanupLuids: DeviceIoControl failed with error %d", v8);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
      }
    }
  }
LABEL_6:
  if ( hKey )
  {
    LastError = RegDeleteKeyA(hKey, "AllocatedLuids");
    if ( LastError )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"CleanupLuids: RegDeleteValue failed with error %d", LastError);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v13);
      }
    }
    RegCloseKey(hKey);
  }
  if ( v2 )
    HeapFree(IPRouterHeap, 0, v2);
  return LastError;
}

```

## disassembly

```asm
0x18000e718  push    rbp
0x18000e71a  push    rbx
0x18000e71b  push    rsi
0x18000e71c  push    rdi
0x18000e71d  push    r14
0x18000e71f  push    r15
0x18000e721  lea     rbp, [rsp-778h]
0x18000e729  sub     rsp, 878h
0x18000e730  mov     rax, cs:__security_cookie
0x18000e737  xor     rax, rsp
0x18000e73a  mov     [rbp+7A0h+var_40], rax
0x18000e741  mov     r15, rcx
0x18000e744  mov     [rsp+8A0h+OutBuffer], 0
0x18000e74d  xor     eax, eax
0x18000e74f  mov     [rsp+8A0h+cbData], 0
0x18000e757  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18000e75c  mov     [rsp+8A0h+var_840], eax
0x18000e760  xor     edx, edx; Val
0x18000e762  mov     [rsp+8A0h+BytesReturned], 0
0x18000e76a  mov     r8d, 7FCh; Size
0x18000e770  mov     [rsp+8A0h+hKey], 0
0x18000e779  xor     esi, esi
0x18000e77b  call    memset_0
0x18000e780  lea     rax, [rsp+8A0h+hKey]
0x18000e785  mov     r9d, 20007h; samDesired
0x18000e78b  xor     r8d, r8d; ulOptions
0x18000e78e  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18000e793  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ra"...
0x18000e79a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e7a1  call    cs:__imp_RegOpenKeyExA
0x18000e7a7  mov     ebx, eax
0x18000e7a9  test    eax, eax
0x18000e7ab  jnz     short loc_18000E80D
0x18000e7ad  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18000e7b2  lea     rax, [rsp+8A0h+cbData]
0x18000e7b7  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18000e7bc  lea     rdx, ValueName; "AllocatedLuids"
0x18000e7c3  xor     r9d, r9d; lpType
0x18000e7c6  mov     [rsp+8A0h+phkResult], rsi; lpData
0x18000e7cb  xor     r8d, r8d; lpReserved
0x18000e7ce  call    cs:__imp_RegQueryValueExA
0x18000e7d4  mov     ebx, eax
0x18000e7d6  test    eax, eax
0x18000e7d8  jnz     short loc_18000E80D
0x18000e7da  mov     edi, [rsp+8A0h+cbData]
0x18000e7de  test    edi, edi
0x18000e7e0  jz      loc_18000E8E7
0x18000e7e6  mov     rcx, cs:IPRouterHeap; hHeap
0x18000e7ed  lea     edx, [rsi+8]; dwFlags
0x18000e7f0  mov     r8d, edi; dwBytes
0x18000e7f3  call    cs:__imp_HeapAlloc
0x18000e7f9  mov     rsi, rax
0x18000e7fc  test    rax, rax
0x18000e7ff  jnz     loc_18000E8B2
0x18000e805  call    cs:__imp_GetLastError
0x18000e80b  mov     ebx, eax
0x18000e80d  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18000e812  test    rcx, rcx
0x18000e815  jz      short loc_18000E87A
0x18000e817  lea     rdx, ValueName; "AllocatedLuids"
0x18000e81e  call    cs:__imp_RegDeleteKeyA
0x18000e824  mov     ebx, eax
0x18000e826  test    eax, eax
0x18000e828  jz      short loc_18000E86F
0x18000e82a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000e831  jge     short loc_18000E86F
0x18000e833  xor     eax, eax
0x18000e835  lea     rdx, aCleanupluidsRe; "CleanupLuids: RegDeleteValue failed wit"...
0x18000e83c  mov     r8d, ebx
0x18000e83f  mov     word ptr [rsp+8A0h+var_840], ax
0x18000e844  lea     rcx, [rsp+8A0h+var_840]
0x18000e849  call    FormatRRASErrorString
0x18000e84e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000e855  jge     short loc_18000E86F
0x18000e857  lea     r8, [rsp+8A0h+var_840]
0x18000e85c  lea     rdx, RasRtrmgrTraceInfo
0x18000e863  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e86a  call    McTemplateU0z_EventWriteTransfer
0x18000e86f  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18000e874  call    cs:__imp_RegCloseKey
0x18000e87a  test    rsi, rsi
0x18000e87d  jz      short loc_18000E891
0x18000e87f  mov     rcx, cs:IPRouterHeap; hHeap
0x18000e886  mov     r8, rsi; lpMem
0x18000e889  xor     edx, edx; dwFlags
0x18000e88b  call    cs:__imp_HeapFree
0x18000e891  mov     eax, ebx
0x18000e893  mov     rcx, [rbp+7A0h+var_40]
0x18000e89a  xor     rcx, rsp; StackCookie
0x18000e89d  call    __security_check_cookie
0x18000e8a2  add     rsp, 878h
0x18000e8a9  pop     r15
0x18000e8ab  pop     r14
0x18000e8ad  pop     rdi
0x18000e8ae  pop     rsi
0x18000e8af  pop     rbx
0x18000e8b0  pop     rbp
0x18000e8b1  retn
0x18000e8b2  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18000e8b7  lea     rax, [rsp+8A0h+cbData]
0x18000e8bc  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18000e8c1  lea     rdx, ValueName; "AllocatedLuids"
0x18000e8c8  xor     r9d, r9d; lpType
0x18000e8cb  mov     [rsp+8A0h+phkResult], rsi; lpData
0x18000e8d0  xor     r8d, r8d; lpReserved
0x18000e8d3  call    cs:__imp_RegQueryValueExA
0x18000e8d9  mov     ebx, eax
0x18000e8db  test    eax, eax
0x18000e8dd  jnz     loc_18000E80D
0x18000e8e3  mov     edi, [rsp+8A0h+cbData]
0x18000e8e7  shr     edi, 2
0x18000e8ea  xor     r14d, r14d
0x18000e8ed  cmp     r14d, edi
0x18000e8f0  jnb     loc_18000E80D
0x18000e8f6  mov     [rsp+8A0h+lpOverlapped], 0; lpOverlapped
0x18000e8ff  lea     r8, [rsp+8A0h+OutBuffer]; lpInBuffer
0x18000e904  mov     eax, 17h
0x18000e909  mov     r9d, 8; nInBufferSize
0x18000e90f  mov     word ptr [rsp+8A0h+OutBuffer], ax
0x18000e914  mov     edx, 90018020h; dwIoControlCode
0x18000e919  mov     ecx, [rsi+r14*4]
0x18000e91d  lea     rax, [rsp+8A0h+BytesReturned]
0x18000e922  mov     [rsp+8A0h+lpBytesReturned], rax; lpBytesReturned
0x18000e927  lea     rax, [rsp+8A0h+OutBuffer]
0x18000e92c  mov     dword ptr [rsp+8A0h+OutBuffer+4], ecx
0x18000e930  mov     rcx, r15; hDevice
0x18000e933  mov     dword ptr [rsp+8A0h+lpcbData], 8; nOutBufferSize
0x18000e93b  mov     [rsp+8A0h+phkResult], rax; lpOutBuffer
0x18000e940  call    cs:__imp_DeviceIoControl
0x18000e946  test    eax, eax
0x18000e948  jnz     short loc_18000E992
0x18000e94a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, al
0x18000e950  jge     short loc_18000E992
0x18000e952  mov     word ptr [rsp+8A0h+var_840], ax
0x18000e957  call    cs:__imp_GetLastError
0x18000e95d  mov     r8d, eax
0x18000e960  lea     rdx, aCleanupluidsDe; "CleanupLuids: DeviceIoControl failed wi"...
0x18000e967  lea     rcx, [rsp+8A0h+var_840]
0x18000e96c  call    FormatRRASErrorString
0x18000e971  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000e978  jge     short loc_18000E992
0x18000e97a  lea     r8, [rsp+8A0h+var_840]
0x18000e97f  lea     rdx, RasRtrmgrTraceInfo
0x18000e986  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000e98d  call    McTemplateU0z_EventWriteTransfer
0x18000e992  inc     r14d
0x18000e995  jmp     loc_18000E8ED
```
