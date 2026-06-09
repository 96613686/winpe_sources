# WriteAdapterIndexToReg(ulong)

- ea: `0x18006d550`
- end: `0x18006d689`
- name: `?WriteAdapterIndexToReg@@YAKK@Z`
- size: `313`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800753a8`

## callees

- `0x18000d090`
- `0x18006d550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006d624`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006d624`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d63c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d63c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d5f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d5f0`

## string_xrefs

- `0x18006d5b1`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 __fastcall WriteAdapterIndexToReg(DWORD a1)
{
  unsigned int v1; // ebx
  BYTE Data[24]; // [rsp+50h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  dwDisposition = a1;
  *(_DWORD *)Data = gICSPublicAdapterIndex;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_b002d07646b635308a4693336a4759d4_Traceguids,
      gICSPublicAdapterIndex);
  }
  hKey = 0;
  dwDisposition = 0;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition);
  if ( !v1 )
    v1 = RegSetValueExW(hKey, L"ICS_PublicAdapterIndex", 0, 4u, Data, 4u);
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_b002d07646b635308a4693336a4759d4_Traceguids, v1);
  }
  return v1;
}

```

## disassembly

```asm
0x18006d550  mov     [rsp+arg_10], rbx
0x18006d555  mov     [rsp+dwDisposition], ecx
0x18006d559  push    rsi
0x18006d55a  sub     rsp, 60h
0x18006d55e  mov     r9d, cs:?gICSPublicAdapterIndex@@3KA; ulong gICSPublicAdapterIndex
0x18006d565  mov     dword ptr [rsp+68h+Data], r9d
0x18006d56a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d571  lea     rsi, WPP_GLOBAL_Control
0x18006d578  cmp     rcx, rsi
0x18006d57b  jz      short loc_18006D59E
0x18006d57d  test    byte ptr [rcx+1Ch], 80h
0x18006d581  jz      short loc_18006D59E
0x18006d583  cmp     byte ptr [rcx+19h], 6
0x18006d587  jb      short loc_18006D59E
0x18006d589  mov     rcx, [rcx+10h]
0x18006d58d  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18006d594  mov     edx, 16h
0x18006d599  call    WPP_SF_d
0x18006d59e  lea     rax, [rsp+68h+dwDisposition]
0x18006d5a3  mov     [rsp+68h+hKey], 0
0x18006d5ac  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18006d5b1  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18006d5b8  lea     rax, [rsp+68h+hKey]
0x18006d5bd  mov     [rsp+68h+dwDisposition], 0
0x18006d5c5  mov     [rsp+68h+phkResult], rax; phkResult
0x18006d5ca  xor     r9d, r9d; lpClass
0x18006d5cd  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006d5d6  xor     r8d, r8d; Reserved
0x18006d5d9  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x18006d5e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d5e8  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18006d5f0  call    cs:__imp_RegCreateKeyExW
0x18006d5f7  nop     dword ptr [rax+rax+00h]
0x18006d5fc  mov     ebx, eax
0x18006d5fe  test    eax, eax
0x18006d600  jnz     short loc_18006D632
0x18006d602  mov     rcx, [rsp+68h+hKey]; hKey
0x18006d607  lea     r9d, [rax+4]; dwType
0x18006d60b  lea     rax, [rsp+68h+Data]
0x18006d610  mov     [rsp+68h+samDesired], r9d; cbData
0x18006d615  xor     r8d, r8d; Reserved
0x18006d618  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18006d61d  lea     rdx, aIcsPublicadapt; "ICS_PublicAdapterIndex"
0x18006d624  call    cs:__imp_RegSetValueExW
0x18006d62b  nop     dword ptr [rax+rax+00h]
0x18006d630  mov     ebx, eax
0x18006d632  mov     rcx, [rsp+68h+hKey]; hKey
0x18006d637  test    rcx, rcx
0x18006d63a  jz      short loc_18006D648
0x18006d63c  call    cs:__imp_RegCloseKey
0x18006d643  nop     dword ptr [rax+rax+00h]
0x18006d648  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d64f  cmp     rcx, rsi
0x18006d652  jz      short loc_18006D678
0x18006d654  test    byte ptr [rcx+1Ch], 80h
0x18006d658  jz      short loc_18006D678
0x18006d65a  cmp     byte ptr [rcx+19h], 6
0x18006d65e  jb      short loc_18006D678
0x18006d660  mov     rcx, [rcx+10h]
0x18006d664  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18006d66b  mov     edx, 17h
0x18006d670  mov     r9d, ebx
0x18006d673  call    WPP_SF_d
0x18006d678  mov     eax, ebx
0x18006d67a  mov     rbx, [rsp+68h+arg_10]
0x18006d682  add     rsp, 60h
0x18006d686  pop     rsi
0x18006d687  retn
```
