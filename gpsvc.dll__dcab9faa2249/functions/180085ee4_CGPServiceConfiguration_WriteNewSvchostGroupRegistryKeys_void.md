# CGPServiceConfiguration::WriteNewSvchostGroupRegistryKeys(void)

- ea: `0x180085ee4`
- end: `0x180086075`
- name: `?WriteNewSvchostGroupRegistryKeys@CGPServiceConfiguration@@CAKXZ`
- size: `401`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008607c`

## callees

- `0x18000a504`
- `0x18001ee6c`
- `0x180022bd4`
- `0x18002c690`
- `0x180085ee4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180085f18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180085f18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085f95`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008600d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180086040`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085f95`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008600d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180086040`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085f67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180085f67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085fdb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085fdb`

## string_xrefs

- `0x180086027`: `CoInitializeSecurityParam`

## pseudocode

```c
__int64 CGPServiceConfiguration::WriteNewSvchostGroupRegistryKeys(void)
{
  unsigned int v0; // edi
  HLOCAL v1; // rax
  BYTE *v2; // rbx
  LSTATUS v3; // eax
  int Data; // [rsp+70h] [rbp+20h] BYREF
  HKEY v6; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  BYTE *lpData; // [rsp+88h] [rbp+38h] BYREF

  v0 = 14;
  hKey = 0;
  v6 = 0;
  Data = 0;
  lpData = 0;
  v1 = LocalAlloc(0x40u, 0xEu);
  XPtrLF<unsigned short>::operator=((void **)&lpData, v1);
  v2 = lpData;
  if ( lpData )
  {
    StringCchCopyW((unsigned __int16 *)lpData, 7u, L"GPSvc");
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SvcHost", 0, 2u, &hKey);
    if ( v3
      || (v3 = RegSetValueExW(hKey, L"GPSvcGroup", 0, 7u, v2, 0xEu)) != 0
      || (v3 = RegCreateKeyExW(hKey, L"GPSvcGroup", 0, 0, 0, 2u, 0, &v6, 0)) != 0
      || (Data = 12320, (v3 = RegSetValueExW(v6, L"AuthenticationCapabilities", 0, 4u, (const BYTE *)&Data, 4u)) != 0)
      || (Data = 1, (v3 = RegSetValueExW(v6, L"CoInitializeSecurityParam", 0, 4u, (const BYTE *)&Data, 4u)) != 0) )
    {
      v0 = v3;
    }
    else
    {
      v0 = 0;
    }
  }
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpData);
  XKey::Free((XKey *)&v6);
  XKey::Free((XKey *)&hKey);
  return v0;
}

```

## disassembly

```asm
0x180085ee4  push    rbp
0x180085ee6  push    rbx
0x180085ee7  push    rdi
0x180085ee8  mov     rbp, rsp
0x180085eeb  sub     rsp, 50h
0x180085eef  mov     edi, 0Eh
0x180085ef4  mov     [rbp+hKey], 0
0x180085efc  mov     edx, edi; uBytes
0x180085efe  mov     [rbp+arg_8], 0
0x180085f06  mov     [rbp+Data], 0
0x180085f0d  mov     [rbp+lpData], 0
0x180085f15  lea     ecx, [rdi+32h]; uFlags
0x180085f18  call    cs:__imp_LocalAlloc
0x180085f1e  mov     rdx, rax
0x180085f21  lea     rcx, [rbp+lpData]
0x180085f25  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180085f2a  mov     rbx, [rbp+lpData]
0x180085f2e  test    rbx, rbx
0x180085f31  jz      loc_180086050
0x180085f37  lea     r8, aGpsvc_0; "GPSvc"
0x180085f3e  mov     rcx, rbx; unsigned __int16 *
0x180085f41  lea     edx, [rdi-7]; unsigned __int64
0x180085f44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180085f49  lea     rax, [rbp+hKey]
0x180085f4d  xor     r8d, r8d; ulOptions
0x180085f50  lea     r9d, [rdi-0Ch]; samDesired
0x180085f54  mov     [rsp+50h+phkResult], rax; phkResult
0x180085f59  lea     rdx, aSoftwareMicros_22; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180085f60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180085f67  call    cs:__imp_RegOpenKeyExW
0x180085f6d  test    eax, eax
0x180085f6f  jz      short loc_180085F78
0x180085f71  mov     edi, eax
0x180085f73  jmp     loc_180086050
0x180085f78  mov     rcx, [rbp+hKey]; hKey
0x180085f7c  lea     rdx, aGpsvcgroup; "GPSvcGroup"
0x180085f83  mov     [rsp+50h+cbData], edi; cbData
0x180085f87  mov     r9d, 7; dwType
0x180085f8d  xor     r8d, r8d; Reserved
0x180085f90  mov     [rsp+50h+phkResult], rbx; lpData
0x180085f95  call    cs:__imp_RegSetValueExW
0x180085f9b  test    eax, eax
0x180085f9d  jnz     short loc_180085F71
0x180085f9f  mov     rcx, [rbp+hKey]; hKey
0x180085fa3  lea     rax, [rbp+arg_8]
0x180085fa7  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180085fb0  lea     rdx, aGpsvcgroup; "GPSvcGroup"
0x180085fb7  mov     [rsp+50h+var_18], rax; phkResult
0x180085fbc  xor     r9d, r9d; lpClass
0x180085fbf  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180085fc8  xor     r8d, r8d; Reserved
0x180085fcb  mov     [rsp+50h+cbData], 2; samDesired
0x180085fd3  mov     dword ptr [rsp+50h+phkResult], 0; dwOptions
0x180085fdb  call    cs:__imp_RegCreateKeyExW
0x180085fe1  test    eax, eax
0x180085fe3  jnz     short loc_180085F71
0x180085fe5  mov     rcx, [rbp+arg_8]; hKey
0x180085fe9  lea     ebx, [rax+4]
0x180085fec  lea     rax, [rbp+Data]
0x180085ff0  mov     [rsp+50h+cbData], ebx; cbData
0x180085ff4  mov     r9d, ebx; dwType
0x180085ff7  mov     [rsp+50h+phkResult], rax; lpData
0x180085ffc  xor     r8d, r8d; Reserved
0x180085fff  mov     [rbp+Data], 3020h
0x180086006  lea     rdx, aAuthentication; "AuthenticationCapabilities"
0x18008600d  call    cs:__imp_RegSetValueExW
0x180086013  test    eax, eax
0x180086015  jnz     loc_180085F71
0x18008601b  mov     rcx, [rbp+arg_8]; hKey
0x18008601f  lea     rax, [rbp+Data]
0x180086023  mov     [rsp+50h+cbData], ebx; cbData
0x180086027  lea     rdx, aCoinitializese; "CoInitializeSecurityParam"
0x18008602e  mov     r9d, ebx; dwType
0x180086031  mov     [rsp+50h+phkResult], rax; lpData
0x180086036  xor     r8d, r8d; Reserved
0x180086039  mov     [rbp+Data], 1
0x180086040  call    cs:__imp_RegSetValueExW
0x180086046  test    eax, eax
0x180086048  jnz     loc_180085F71
0x18008604e  xor     edi, edi
0x180086050  lea     rcx, [rbp+lpData]
0x180086054  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180086059  lea     rcx, [rbp+arg_8]; this
0x18008605d  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180086062  lea     rcx, [rbp+hKey]; this
0x180086066  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x18008606b  mov     eax, edi
0x18008606d  add     rsp, 50h
0x180086071  pop     rdi
0x180086072  pop     rbx
0x180086073  pop     rbp
0x180086074  retn
```
