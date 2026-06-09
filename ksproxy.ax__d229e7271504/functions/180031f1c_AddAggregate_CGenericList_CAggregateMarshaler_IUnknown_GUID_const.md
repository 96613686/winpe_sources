# AddAggregate(CGenericList<CAggregateMarshaler> *,IUnknown *,_GUID const &)

- ea: `0x180031f1c`
- end: `0x1800320a1`
- name: `?AddAggregate@@YAJPEAV?$CGenericList@VCAggregateMarshaler@@@@PEAUIUnknown@@AEBU_GUID@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(CBaseList *this, LPUNKNOWN pUnkOuter, GUID *rguid)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180023410`
- `0x180027590`
- `0x18002b6b0`

## callees

- `0x18000b2e4`
- `0x18001f1d0`
- `0x18001f620`
- `0x180031f1c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180032008`
- `ADVAPI32!RegQueryValueExW` at `0x180032008`
- `ADVAPI32!RegCloseKey` at `0x18003201a`
- `ADVAPI32!RegCloseKey` at `0x180032078`
- `ADVAPI32!RegCloseKey` at `0x18003201a`
- `ADVAPI32!RegCloseKey` at `0x180032078`
- `ADVAPI32!RegOpenKeyExW` at `0x180031f6e`
- `ADVAPI32!RegOpenKeyExW` at `0x180031fce`
- `ADVAPI32!RegOpenKeyExW` at `0x180031f6e`
- `ADVAPI32!RegOpenKeyExW` at `0x180031fce`
- `ole32!StringFromGUID2` at `0x180031f95`
- `ole32!StringFromGUID2` at `0x180031f95`

## pseudocode

```c
__int64 __fastcall AddAggregate(CBaseList *this, LPUNKNOWN pUnkOuter, GUID *rguid)
{
  LSTATUS v6; // ebx
  LSTATUS v7; // ebx
  GUID *v8; // rax
  unsigned int v9; // ebx
  HKEY hKey; // [rsp+30h] [rbp-59h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-51h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-49h] BYREF
  BYTE Data[16]; // [rsp+48h] [rbp-41h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-29h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces", 0, 0x20019u, &hKey);
  if ( v6 )
    hKey = 0;
  StringFromGUID2(rguid, sz, 39);
  phkResult = 0;
  *(_OWORD *)Data = 0;
  if ( v6
    || RegOpenKeyExW(hKey, sz, 0, 0x20019u, &phkResult)
    || (cbData = 16, v7 = RegQueryValueExW(phkResult, L"iid", 0, 0, Data, &cbData), RegCloseKey(phkResult), v7) )
  {
    *(GUID *)Data = GUID_00000000_0000_0000_0000_000000000000;
  }
  v8 = (GUID *)operator new(0x38u);
  if ( v8 )
  {
    *v8 = *(GUID *)Data;
    v8[1] = *rguid;
    v9 = AddAggregateObject(this, (char *)v8, pUnkOuter, 0);
  }
  else
  {
    v9 = -2147024882;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180031f1c  push    rbp
0x180031f1e  push    rbx
0x180031f1f  push    rsi
0x180031f20  push    rdi
0x180031f21  push    r14
0x180031f23  lea     rbp, [rsp-37h]
0x180031f28  sub     rsp, 0C0h
0x180031f2f  mov     rax, cs:__security_cookie
0x180031f36  xor     rax, rsp
0x180031f39  mov     [rbp+57h+var_30], rax
0x180031f3d  mov     rdi, r8
0x180031f40  mov     [rbp+57h+hKey], 0
0x180031f48  mov     r14, rdx
0x180031f4b  lea     rax, [rbp+57h+hKey]
0x180031f4f  mov     rsi, rcx
0x180031f52  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180031f57  xor     r8d, r8d; ulOptions
0x180031f5a  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x180031f61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031f68  mov     r9d, 20019h; samDesired
0x180031f6e  call    cs:__imp_RegOpenKeyExW
0x180031f75  nop     dword ptr [rax+rax+00h]
0x180031f7a  mov     ebx, eax
0x180031f7c  test    eax, eax
0x180031f7e  jz      short loc_180031F88
0x180031f80  mov     [rbp+57h+hKey], 0
0x180031f88  mov     r8d, 27h ; '''; cchMax
0x180031f8e  lea     rdx, [rbp+57h+sz]; lpsz
0x180031f92  mov     rcx, rdi; rguid
0x180031f95  call    cs:__imp_StringFromGUID2
0x180031f9c  nop     dword ptr [rax+rax+00h]
0x180031fa1  mov     [rbp+57h+var_A0], 0
0x180031fa9  xorps   xmm0, xmm0
0x180031fac  movups  xmmword ptr [rbp+57h+Data], xmm0
0x180031fb0  test    ebx, ebx
0x180031fb2  jnz     short loc_18003202A
0x180031fb4  mov     rcx, [rbp+57h+hKey]; hKey
0x180031fb8  lea     rax, [rbp+57h+var_A0]
0x180031fbc  mov     r9d, 20019h; samDesired
0x180031fc2  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180031fc7  xor     r8d, r8d; ulOptions
0x180031fca  lea     rdx, [rbp+57h+sz]; lpSubKey
0x180031fce  call    cs:__imp_RegOpenKeyExW
0x180031fd5  nop     dword ptr [rax+rax+00h]
0x180031fda  test    eax, eax
0x180031fdc  jnz     short loc_18003202A
0x180031fde  mov     rcx, [rbp+57h+var_A0]; hKey
0x180031fe2  lea     rax, [rbp+57h+cbData]
0x180031fe6  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x180031feb  lea     rdx, ValueName; "iid"
0x180031ff2  lea     rax, [rbp+57h+Data]
0x180031ff6  mov     [rbp+57h+cbData], 10h
0x180031ffd  xor     r9d, r9d; lpType
0x180032000  mov     [rsp+0E0h+phkResult], rax; lpData
0x180032005  xor     r8d, r8d; lpReserved
0x180032008  call    cs:__imp_RegQueryValueExW
0x18003200f  nop     dword ptr [rax+rax+00h]
0x180032014  mov     rcx, [rbp+57h+var_A0]; hKey
0x180032018  mov     ebx, eax
0x18003201a  call    cs:__imp_RegCloseKey
0x180032021  nop     dword ptr [rax+rax+00h]
0x180032026  test    ebx, ebx
0x180032028  jz      short loc_180032036
0x18003202a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180032031  movdqu  xmmword ptr [rbp+57h+Data], xmm0
0x180032036  mov     ecx, 38h ; '8'; Size
0x18003203b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032040  test    rax, rax
0x180032043  jz      short loc_18003206A
0x180032045  movups  xmm0, xmmword ptr [rbp+57h+Data]
0x180032049  xor     r9d, r9d
0x18003204c  mov     r8, r14; pUnkOuter
0x18003204f  mov     rdx, rax; void *
0x180032052  mov     rcx, rsi; this
0x180032055  movdqu  xmmword ptr [rax], xmm0
0x180032059  movups  xmm1, xmmword ptr [rdi]
0x18003205c  movdqu  xmmword ptr [rax+10h], xmm1
0x180032061  call    ?AddAggregateObject@@YAJPEAV?$CGenericList@VCAggregateMarshaler@@@@PEAVCAggregateMarshaler@@PEAUIUnknown@@H@Z; AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)
0x180032066  mov     ebx, eax
0x180032068  jmp     short loc_18003206F
0x18003206a  mov     ebx, 8007000Eh
0x18003206f  mov     rcx, [rbp+57h+hKey]; hKey
0x180032073  test    rcx, rcx
0x180032076  jz      short loc_180032084
0x180032078  call    cs:__imp_RegCloseKey
0x18003207f  nop     dword ptr [rax+rax+00h]
0x180032084  mov     eax, ebx
0x180032086  mov     rcx, [rbp+57h+var_30]
0x18003208a  xor     rcx, rsp; StackCookie
0x18003208d  call    __security_check_cookie
0x180032092  add     rsp, 0C0h
0x180032099  pop     r14
0x18003209b  pop     rdi
0x18003209c  pop     rsi
0x18003209d  pop     rbx
0x18003209e  pop     rbp
0x18003209f  retn
```
