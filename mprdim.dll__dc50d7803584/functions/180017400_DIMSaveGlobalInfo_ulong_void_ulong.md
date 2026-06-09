# DIMSaveGlobalInfo(ulong,void *,ulong)

- ea: `0x180017400`
- end: `0x1800174c6`
- name: `?DIMSaveGlobalInfo@@YAKKPEAXK@Z`
- size: `198`
- prototype: `__int64 __fastcall(unsigned int, BYTE *lpData, DWORD cbData)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800056c4`
- `0x180017400`
- `0x18002f22c`
- `0x180045d7c`
- `0x180046e70`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001747d`
- `ADVAPI32!RegSetValueExW` at `0x18001747d`
- `ADVAPI32!RegCloseKey` at `0x18001748f`
- `ADVAPI32!RegCloseKey` at `0x18001748f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DIMSaveGlobalInfo(unsigned int a1, BYTE *lpData, DWORD cbData)
{
  int v6; // edi
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-30h] BYREF

  hKey = 0;
  ActivityId = 0;
  if ( (((_DWORD)qword_180070F24 - 1) & 0xFFFFFFFD) == 0 )
    return 903;
  v6 = SetRasServerActivityId(&ActivityId);
  v7 = CDimRouterManager::RegOpenRouterManagerKey(a1, &hKey);
  if ( !v7 )
    v7 = RegSetValueExW(hKey, L"GlobalInfo", 0, 3u, lpData, cbData);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    ReSetActivityId(&ActivityId);
  return v7;
}

```

## disassembly

```asm
0x180017400  mov     [rsp+arg_0], rbx
0x180017405  push    rbp
0x180017406  push    rsi
0x180017407  push    rdi
0x180017408  sub     rsp, 50h
0x18001740c  mov     rax, cs:__security_cookie
0x180017413  xor     rax, rsp
0x180017416  mov     [rsp+68h+var_20], rax
0x18001741b  mov     eax, dword ptr cs:qword_180070F24
0x180017421  xorps   xmm0, xmm0
0x180017424  dec     eax
0x180017426  mov     [rsp+68h+hKey], 0
0x18001742f  mov     ebp, r8d
0x180017432  mov     rsi, rdx
0x180017435  mov     ebx, ecx
0x180017437  movups  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x18001743c  test    eax, 0FFFFFFFDh
0x180017441  jz      short loc_1800174A7
0x180017443  lea     rcx, [rsp+68h+ActivityId]; ActivityId
0x180017448  call    SetRasServerActivityId
0x18001744d  lea     rdx, [rsp+68h+hKey]; HKEY *
0x180017452  mov     ecx, ebx; unsigned int
0x180017454  mov     edi, eax
0x180017456  call    ?RegOpenRouterManagerKey@CDimRouterManager@@SAKKAEAPEAUHKEY__@@@Z; CDimRouterManager::RegOpenRouterManagerKey(ulong,HKEY__ * &)
0x18001745b  mov     ebx, eax
0x18001745d  test    eax, eax
0x18001745f  jnz     short loc_180017485
0x180017461  mov     rcx, [rsp+68h+hKey]; hKey
0x180017466  lea     r9d, [rax+3]; dwType
0x18001746a  mov     [rsp+68h+cbData], ebp; cbData
0x18001746e  lea     rdx, aGlobalinfo; "GlobalInfo"
0x180017475  xor     r8d, r8d; Reserved
0x180017478  mov     [rsp+68h+lpData], rsi; lpData
0x18001747d  call    cs:__imp_RegSetValueExW
0x180017483  mov     ebx, eax
0x180017485  mov     rcx, [rsp+68h+hKey]; hKey
0x18001748a  test    rcx, rcx
0x18001748d  jz      short loc_180017495
0x18001748f  call    cs:__imp_RegCloseKey
0x180017495  test    edi, edi
0x180017497  jz      short loc_1800174A3
0x180017499  lea     rcx, [rsp+68h+ActivityId]; ActivityId
0x18001749e  call    ReSetActivityId
0x1800174a3  mov     eax, ebx
0x1800174a5  jmp     short loc_1800174AC
0x1800174a7  mov     eax, 387h
0x1800174ac  mov     rcx, [rsp+68h+var_20]
0x1800174b1  xor     rcx, rsp; StackCookie
0x1800174b4  call    __security_check_cookie
0x1800174b9  mov     rbx, [rsp+68h+arg_0]
0x1800174be  add     rsp, 50h
0x1800174c2  pop     rdi
0x1800174c3  pop     rsi
0x1800174c4  pop     rbp
0x1800174c5  retn
```
