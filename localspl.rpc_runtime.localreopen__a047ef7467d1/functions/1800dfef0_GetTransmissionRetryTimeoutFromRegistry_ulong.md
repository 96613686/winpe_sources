# GetTransmissionRetryTimeoutFromRegistry(ulong *)

- ea: `0x1800dfef0`
- end: `0x1800e0053`
- name: `?GetTransmissionRetryTimeoutFromRegistry@@YAXPEAK@Z`
- size: `355`
- prototype: `void __fastcall(unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800dfcdc`
- `0x1800e13e8`
- `0x1800e2b70`

## callees

- `0x180047480`
- `0x1800df488`
- `0x1800dfef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dff9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dfff3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dff9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dfff3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e0044`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e0044`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dff40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dff40`
- `SPOOLSS!DllFreeSplMem` at `0x1800dffab`
- `SPOOLSS!DllFreeSplMem` at `0x1800e0035`
- `SPOOLSS!DllFreeSplMem` at `0x1800dffab`
- `SPOOLSS!DllFreeSplMem` at `0x1800e0035`
- `SPOOLSS!DllAllocSplMem` at `0x1800dff54`
- `SPOOLSS!DllAllocSplMem` at `0x1800dffb7`
- `SPOOLSS!DllAllocSplMem` at `0x1800dff54`
- `SPOOLSS!DllAllocSplMem` at `0x1800dffb7`

## string_xrefs

- `0x1800dff08`: `GetTransmissionRetryTimeoutFromRegistry`

## pseudocode

```c
void __fastcall GetTransmissionRetryTimeoutFromRegistry(unsigned int *a1)
{
  const wchar_t *v2; // rbx
  BYTE *v3; // rax
  DWORD v4; // edi
  LSTATUS v5; // eax
  BYTE *v6; // rax
  bool v7; // zf
  unsigned int v8; // eax
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  DWORD Type; // [rsp+68h] [rbp+30h] BYREF
  unsigned int v11; // [rsp+70h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+40h] BYREF

  cbData = 10;
  v2 = 0;
  v11 = 0;
  hKey = 0;
  LocalMonTelemetry::WriteDbgTraceInfo("GetTransmissionRetryTimeoutFromRegistry", L"Entering");
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, gszWindows, 0, 1u, &hKey) )
    goto LABEL_9;
  v3 = (BYTE *)DllAllocSplMem(cbData + 2);
  v2 = (const wchar_t *)v3;
  if ( !v3 )
    goto LABEL_9;
  v4 = cbData;
  Type = 0;
  *(_WORD *)&v3[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v5 = RegQueryValueExW(hKey, szINIKey_TransmissionRetryTimeout, 0, &Type, v3, &cbData);
  if ( v5 == 234 )
  {
    DllFreeSplMem(v2);
    v6 = (BYTE *)DllAllocSplMem(cbData + 2);
    v2 = (const wchar_t *)v6;
    if ( !v6 )
    {
LABEL_9:
      v8 = 45;
      goto LABEL_10;
    }
    v4 = cbData;
    *(_WORD *)&v6[2 * ((unsigned __int64)cbData >> 1)] = 0;
    v5 = RegQueryValueExW(hKey, szINIKey_TransmissionRetryTimeout, 0, &Type, v6, &cbData);
  }
  if ( v5 )
    goto LABEL_9;
  if ( Type != 1 )
    goto LABEL_9;
  v2[(v4 >> 1) - 1] = 0;
  v7 = swscanf_s(v2, L"%lu", &v11) == 1;
  v8 = v11;
  if ( !v7 )
    goto LABEL_9;
LABEL_10:
  *a1 = v8;
  if ( v2 )
    DllFreeSplMem(v2);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800dfef0  push    rbp
0x1800dfef2  push    rbx
0x1800dfef3  push    rsi
0x1800dfef4  push    rdi
0x1800dfef5  mov     rbp, rsp
0x1800dfef8  sub     rsp, 38h
0x1800dfefc  mov     rsi, rcx
0x1800dfeff  mov     [rbp+cbData], 0Ah
0x1800dff06  xor     ebx, ebx
0x1800dff08  lea     rcx, aGettransmissio; "GetTransmissionRetryTimeoutFromRegistry"
0x1800dff0f  lea     rdx, aEntering; "Entering"
0x1800dff16  mov     [rbp+arg_10], ebx
0x1800dff19  mov     [rbp+hKey], rbx
0x1800dff1d  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800dff22  lea     rax, [rbp+hKey]
0x1800dff26  xor     r8d, r8d; ulOptions
0x1800dff29  lea     r9d, [rbx+1]; samDesired
0x1800dff2d  mov     [rsp+38h+phkResult], rax; phkResult
0x1800dff32  lea     rdx, ?gszWindows@@3PAGA; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800dff39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dff40  call    cs:__imp_RegOpenKeyExW
0x1800dff46  test    eax, eax
0x1800dff48  jnz     loc_1800E0026
0x1800dff4e  mov     ecx, [rbp+cbData]
0x1800dff51  add     ecx, 2
0x1800dff54  call    cs:__imp_DllAllocSplMem
0x1800dff5a  mov     rbx, rax
0x1800dff5d  test    rax, rax
0x1800dff60  jz      loc_1800E0026
0x1800dff66  mov     edi, [rbp+cbData]
0x1800dff69  lea     r9, [rbp+Type]; lpType
0x1800dff6d  xor     ecx, ecx
0x1800dff6f  mov     [rbp+Type], 0
0x1800dff76  mov     edx, edi
0x1800dff78  xor     r8d, r8d; lpReserved
0x1800dff7b  shr     rdx, 1
0x1800dff7e  mov     [rax+rdx*2], cx
0x1800dff82  lea     rax, [rbp+cbData]
0x1800dff86  mov     rcx, [rbp+hKey]; hKey
0x1800dff8a  lea     rdx, ?szINIKey_TransmissionRetryTimeout@@3PAGA; "TransmissionRetryTimeout"
0x1800dff91  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800dff96  mov     [rsp+38h+phkResult], rbx; lpData
0x1800dff9b  call    cs:__imp_RegQueryValueExW
0x1800dffa1  cmp     eax, 0EAh
0x1800dffa6  jnz     short loc_1800DFFF9
0x1800dffa8  mov     rcx, rbx
0x1800dffab  call    cs:__imp_DllFreeSplMem
0x1800dffb1  mov     ecx, [rbp+cbData]
0x1800dffb4  add     ecx, 2
0x1800dffb7  call    cs:__imp_DllAllocSplMem
0x1800dffbd  mov     rbx, rax
0x1800dffc0  test    rax, rax
0x1800dffc3  jz      short loc_1800E0026
0x1800dffc5  mov     edi, [rbp+cbData]
0x1800dffc8  lea     r9, [rbp+Type]; lpType
0x1800dffcc  xor     eax, eax
0x1800dffce  lea     rdx, ?szINIKey_TransmissionRetryTimeout@@3PAGA; "TransmissionRetryTimeout"
0x1800dffd5  mov     ecx, edi
0x1800dffd7  xor     r8d, r8d; lpReserved
0x1800dffda  shr     rcx, 1
0x1800dffdd  mov     [rbx+rcx*2], ax
0x1800dffe1  lea     rax, [rbp+cbData]
0x1800dffe5  mov     rcx, [rbp+hKey]; hKey
0x1800dffe9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800dffee  mov     [rsp+38h+phkResult], rbx; lpData
0x1800dfff3  call    cs:__imp_RegQueryValueExW
0x1800dfff9  test    eax, eax
0x1800dfffb  jnz     short loc_1800E0026
0x1800dfffd  cmp     [rbp+Type], 1
0x1800e0001  jnz     short loc_1800E0026
0x1800e0003  shr     edi, 1
0x1800e0005  lea     r8, [rbp+arg_10]
0x1800e0009  dec     edi
0x1800e000b  lea     rdx, aLu; "%lu"
0x1800e0012  mov     rcx, rbx; Buffer
0x1800e0015  mov     [rbx+rdi*2], ax
0x1800e0019  call    swscanf_s
0x1800e001e  cmp     eax, 1
0x1800e0021  mov     eax, [rbp+arg_10]
0x1800e0024  jz      short loc_1800E002B
0x1800e0026  mov     eax, 2Dh ; '-'
0x1800e002b  mov     [rsi], eax
0x1800e002d  test    rbx, rbx
0x1800e0030  jz      short loc_1800E003B
0x1800e0032  mov     rcx, rbx
0x1800e0035  call    cs:__imp_DllFreeSplMem
0x1800e003b  mov     rcx, [rbp+hKey]; hKey
0x1800e003f  test    rcx, rcx
0x1800e0042  jz      short loc_1800E004A
0x1800e0044  call    cs:__imp_RegCloseKey
0x1800e004a  add     rsp, 38h
0x1800e004e  pop     rdi
0x1800e004f  pop     rsi
0x1800e0050  pop     rbx
0x1800e0051  pop     rbp
0x1800e0052  retn
```
