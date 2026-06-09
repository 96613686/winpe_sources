# WriteAdapterIndexToReg(ulong)

- ea: `0x180068358`
- end: `0x18006847e`
- name: `?WriteAdapterIndexToReg@@YAKK@Z`
- size: `294`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18006fa64`

## callees

- `0x18000c750`
- `0x180068358`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068426`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180068426`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068438`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068438`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800683f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800683f8`

## string_xrefs

- `0x1800683b9`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
0x180068358  mov     [rsp+arg_10], rbx
0x18006835d  mov     [rsp+dwDisposition], ecx
0x180068361  push    rsi
0x180068362  sub     rsp, 60h
0x180068366  mov     r9d, cs:?gICSPublicAdapterIndex@@3KA; ulong gICSPublicAdapterIndex
0x18006836d  mov     dword ptr [rsp+68h+Data], r9d
0x180068372  mov     rcx, cs:WPP_GLOBAL_Control
0x180068379  lea     rsi, WPP_GLOBAL_Control
0x180068380  cmp     rcx, rsi
0x180068383  jz      short loc_1800683A6
0x180068385  test    byte ptr [rcx+1Ch], 80h
0x180068389  jz      short loc_1800683A6
0x18006838b  cmp     byte ptr [rcx+19h], 6
0x18006838f  jb      short loc_1800683A6
0x180068391  mov     rcx, [rcx+10h]
0x180068395  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18006839c  mov     edx, 16h
0x1800683a1  call    WPP_SF_d
0x1800683a6  lea     rax, [rsp+68h+dwDisposition]
0x1800683ab  mov     [rsp+68h+hKey], 0
0x1800683b4  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x1800683b9  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x1800683c0  lea     rax, [rsp+68h+hKey]
0x1800683c5  mov     [rsp+68h+dwDisposition], 0
0x1800683cd  mov     [rsp+68h+phkResult], rax; phkResult
0x1800683d2  xor     r9d, r9d; lpClass
0x1800683d5  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800683de  xor     r8d, r8d; Reserved
0x1800683e1  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x1800683e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800683f0  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800683f8  call    cs:__imp_RegCreateKeyExW
0x1800683fe  mov     ebx, eax
0x180068400  test    eax, eax
0x180068402  jnz     short loc_18006842E
0x180068404  mov     rcx, [rsp+68h+hKey]; hKey
0x180068409  lea     r9d, [rax+4]; dwType
0x18006840d  lea     rax, [rsp+68h+Data]
0x180068412  mov     [rsp+68h+samDesired], r9d; cbData
0x180068417  xor     r8d, r8d; Reserved
0x18006841a  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18006841f  lea     rdx, aIcsPublicadapt; "ICS_PublicAdapterIndex"
0x180068426  call    cs:__imp_RegSetValueExW
0x18006842c  mov     ebx, eax
0x18006842e  mov     rcx, [rsp+68h+hKey]; hKey
0x180068433  test    rcx, rcx
0x180068436  jz      short loc_18006843E
0x180068438  call    cs:__imp_RegCloseKey
0x18006843e  mov     rcx, cs:WPP_GLOBAL_Control
0x180068445  cmp     rcx, rsi
0x180068448  jz      short loc_18006846E
0x18006844a  test    byte ptr [rcx+1Ch], 80h
0x18006844e  jz      short loc_18006846E
0x180068450  cmp     byte ptr [rcx+19h], 6
0x180068454  jb      short loc_18006846E
0x180068456  mov     rcx, [rcx+10h]
0x18006845a  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x180068461  mov     edx, 17h
0x180068466  mov     r9d, ebx
0x180068469  call    WPP_SF_d
0x18006846e  mov     eax, ebx
0x180068470  mov     rbx, [rsp+68h+arg_10]
0x180068478  add     rsp, 60h
0x18006847c  pop     rsi
0x18006847d  retn
```
