# IsKeyIsoDisabled

- ea: `0x180018238`
- end: `0x180018356`
- name: `IsKeyIsoDisabled`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018070`

## callees

- `0x180018238`
- `0x180018c18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018299`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018299`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800182e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800182e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800182cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800182cd`

## pseudocode

```c
_BOOL8 IsKeyIsoDisabled()
{
  int v0; // ebx
  int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = dword_180079484;
  hKey = 0;
  Data = 0x10000;
  Type = 4;
  cbData = 4;
  if ( dword_180079484 == -1 )
  {
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft Software Key Storage Provider\\UM\\00010001",
            0,
            1u,
            &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"Flags", 0, &Type, (LPBYTE)&Data, &cbData) && Type != 4 )
        Data = 0x10000;
      RegCloseKey(hKey);
    }
    _InterlockedCompareExchange(&dword_180079484, (Data & 0x10000) == 0, -1);
    v0 = dword_180079484;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_a5b9c631da783ce152883bc4773a2313_Traceguids,
        (unsigned int)dword_180079484);
  }
  return v0 != 0;
}

```

## disassembly

```asm
0x180018238  push    rbp
0x18001823a  push    rbx
0x18001823b  mov     rbp, rsp
0x18001823e  sub     rsp, 38h
0x180018242  mov     ebx, cs:dword_180079484
0x180018248  mov     [rbp+hKey], 0
0x180018250  mov     dword ptr [rbp+Data], 10000h
0x180018257  mov     [rbp+Type], 4
0x18001825e  mov     [rbp+cbData], 4
0x180018265  cmp     ebx, 0FFFFFFFFh
0x180018268  jz      short loc_180018279
0x18001826a  xor     eax, eax
0x18001826c  test    ebx, ebx
0x18001826e  setnz   al
0x180018271  add     rsp, 38h
0x180018275  pop     rbx
0x180018276  pop     rbp
0x180018277  retn
0x180018279  lea     rax, [rbp+hKey]
0x18001827d  mov     r9d, 1; samDesired
0x180018283  xor     r8d, r8d; ulOptions
0x180018286  mov     [rsp+38h+phkResult], rax; phkResult
0x18001828b  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Cry"...
0x180018292  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018299  call    cs:__imp_RegOpenKeyExW
0x1800182a0  nop     dword ptr [rax+rax+00h]
0x1800182a5  test    eax, eax
0x1800182a7  jnz     short loc_1800182ED
0x1800182a9  mov     rcx, [rbp+hKey]; hKey
0x1800182ad  lea     rax, [rbp+cbData]
0x1800182b1  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800182b6  lea     r9, [rbp+Type]; lpType
0x1800182ba  lea     rax, [rbp+Data]
0x1800182be  xor     r8d, r8d; lpReserved
0x1800182c1  lea     rdx, aFlags; "Flags"
0x1800182c8  mov     [rsp+38h+phkResult], rax; lpData
0x1800182cd  call    cs:__imp_RegQueryValueExW
0x1800182d4  nop     dword ptr [rax+rax+00h]
0x1800182d9  test    eax, eax
0x1800182db  jz      short loc_180018347
0x1800182dd  mov     rcx, [rbp+hKey]; hKey
0x1800182e1  call    cs:__imp_RegCloseKey
0x1800182e8  nop     dword ptr [rax+rax+00h]
0x1800182ed  mov     ecx, dword ptr [rbp+Data]
0x1800182f0  shr     ecx, 10h
0x1800182f3  not     ecx
0x1800182f5  and     ecx, 1
0x1800182f8  or      eax, 0FFFFFFFFh
0x1800182fb  lock cmpxchg cs:dword_180079484, ecx
0x180018303  mov     ebx, cs:dword_180079484
0x180018309  mov     rcx, cs:WPP_GLOBAL_Control
0x180018310  lea     rax, WPP_GLOBAL_Control
0x180018317  cmp     rcx, rax
0x18001831a  jz      loc_18001826A
0x180018320  test    byte ptr [rcx+1Ch], 8
0x180018324  jz      loc_18001826A
0x18001832a  mov     rcx, [rcx+10h]
0x18001832e  lea     r8, WPP_a5b9c631da783ce152883bc4773a2313_Traceguids
0x180018335  mov     edx, 0Ah
0x18001833a  mov     r9d, ebx
0x18001833d  call    WPP_SF_d
0x180018342  jmp     loc_18001826A
0x180018347  cmp     [rbp+Type], 4
0x18001834b  jz      short loc_1800182DD
0x18001834d  mov     dword ptr [rbp+Data], 10000h
0x180018354  jmp     short loc_1800182DD
```
