# ReadDwordRegistry(ushort const *,ushort const *,ulong *)

- ea: `0x18003d384`
- end: `0x18003d495`
- name: `?ReadDwordRegistry@@YAJPEBG0PEAK@Z`
- size: `273`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035140`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18003d384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d3ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d3ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d434`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003d434`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d446`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d446`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadDwordRegistry(unsigned __int16 *a1, const unsigned __int16 *a2, BYTE *a3)
{
  LSTATUS Value; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 *cbData; // [rsp+48h] [rbp+10h] BYREF

  cbData = a2;
  hKey = (HKEY)a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 16, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids);
  }
  LODWORD(cbData) = 0;
  hKey = 0;
  Value = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\dot3svc\\MigrationData\\dot3svc", 0, 0x20019u, &hKey);
  if ( !Value )
  {
    LODWORD(cbData) = 4;
    Value = RegQueryValueExW(hKey, L"BlockTime", 0, 0, a3, (LPDWORD)&cbData);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 17, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids, (unsigned int)Value);
  }
  if ( Value > 0 )
    return (unsigned __int16)Value | 0x80070000;
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x18003d384  mov     rax, rsp
0x18003d387  mov     [rax+18h], rbx
0x18003d38b  mov     [rax+20h], rsi
0x18003d38f  mov     [rax+10h], rdx
0x18003d393  mov     [rax+8], rcx
0x18003d397  push    rdi
0x18003d398  sub     rsp, 30h
0x18003d39c  mov     rdi, r8
0x18003d39f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3a6  lea     rsi, WPP_GLOBAL_Control
0x18003d3ad  cmp     rcx, rsi
0x18003d3b0  jz      short loc_18003D3CD
0x18003d3b2  test    byte ptr [rcx+1Ch], 10h
0x18003d3b6  jz      short loc_18003D3CD
0x18003d3b8  mov     rcx, [rcx+10h]
0x18003d3bc  lea     r8, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids
0x18003d3c3  mov     edx, 10h
0x18003d3c8  call    WPP_SF_
0x18003d3cd  lea     rax, [rsp+38h+hKey]
0x18003d3d2  mov     dword ptr [rsp+38h+cbData], 0
0x18003d3da  mov     r9d, 20019h; samDesired
0x18003d3e0  mov     [rsp+38h+phkResult], rax; phkResult
0x18003d3e5  xor     r8d, r8d; ulOptions
0x18003d3e8  mov     [rsp+38h+hKey], 0
0x18003d3f1  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\dot3svc\\Migration"...
0x18003d3f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d3ff  call    cs:__imp_RegOpenKeyExW
0x18003d405  mov     ebx, eax
0x18003d407  test    eax, eax
0x18003d409  jnz     short loc_18003D43C
0x18003d40b  mov     rcx, [rsp+38h+hKey]; hKey
0x18003d410  lea     rax, [rsp+38h+cbData]
0x18003d415  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003d41a  lea     rdx, aBlocktime_0; "BlockTime"
0x18003d421  xor     r9d, r9d; lpType
0x18003d424  mov     [rsp+38h+phkResult], rdi; lpData
0x18003d429  xor     r8d, r8d; lpReserved
0x18003d42c  mov     dword ptr [rsp+38h+cbData], 4
0x18003d434  call    cs:__imp_RegQueryValueExW
0x18003d43a  mov     ebx, eax
0x18003d43c  mov     rcx, [rsp+38h+hKey]; hKey
0x18003d441  test    rcx, rcx
0x18003d444  jz      short loc_18003D44C
0x18003d446  call    cs:__imp_RegCloseKey
0x18003d44c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d453  cmp     rcx, rsi
0x18003d456  jz      short loc_18003D476
0x18003d458  test    byte ptr [rcx+1Ch], 10h
0x18003d45c  jz      short loc_18003D476
0x18003d45e  mov     rcx, [rcx+10h]
0x18003d462  lea     r8, WPP_12e48a9d849435eac3405c86722d7b90_Traceguids
0x18003d469  mov     edx, 11h
0x18003d46e  mov     r9d, ebx
0x18003d471  call    WPP_SF_d
0x18003d476  test    ebx, ebx
0x18003d478  jle     short loc_18003D483
0x18003d47a  movzx   ebx, bx
0x18003d47d  or      ebx, 80070000h
0x18003d483  mov     rsi, [rsp+38h+arg_18]
0x18003d488  mov     eax, ebx
0x18003d48a  mov     rbx, [rsp+38h+arg_10]
0x18003d48f  add     rsp, 30h
0x18003d493  pop     rdi
0x18003d494  retn
```
