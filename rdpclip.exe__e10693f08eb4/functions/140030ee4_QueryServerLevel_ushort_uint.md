# QueryServerLevel(ushort *,uint *)

- ea: `0x140030ee4`
- end: `0x14003103a`
- name: `?QueryServerLevel@@YAJPEAGPEAI@Z`
- size: `342`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140030c98`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140011054`
- `0x140030ee4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003102a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003102a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140030f7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140030f7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140030fbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140030fbe`

## pseudocode

```c
__int64 __fastcall QueryServerLevel(LPCWSTR lpValueName, unsigned int *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  if ( a2 )
  {
    *a2 = 0;
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Server\\ServerLevels\\",
           0,
           0x20019u,
           &hKey);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_4d99b8df44273fb485b6255fcb87282b_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
    }
    else
    {
      Data = 0;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData) )
        *a2 = Data;
      v5 = 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_4d99b8df44273fb485b6255fcb87282b_Traceguids,
        v4,
        (__int64)"puVal");
    }
    v5 = -2147467261;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x140030ee4  push    rbx
0x140030ee6  push    rsi
0x140030ee7  push    rdi
0x140030ee8  sub     rsp, 40h
0x140030eec  mov     [rsp+58h+hKey], 0
0x140030ef5  mov     rdi, rdx
0x140030ef8  mov     rsi, rcx
0x140030efb  test    rdx, rdx
0x140030efe  jnz     short loc_140030F57
0x140030f00  mov     rax, cs:WPP_GLOBAL_Control
0x140030f07  lea     rcx, WPP_GLOBAL_Control
0x140030f0e  cmp     rax, rcx
0x140030f11  jz      short loc_140030F4D
0x140030f13  test    byte ptr [rax+1Ch], 8
0x140030f17  jz      short loc_140030F4D
0x140030f19  cmp     byte ptr [rax+19h], 2
0x140030f1d  jb      short loc_140030F4D
0x140030f1f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140030f24  lea     rcx, aPuval; "puVal"
0x140030f2b  mov     r9d, eax
0x140030f2e  mov     [rsp+58h+phkResult], rcx
0x140030f33  lea     edx, [rdi+0Ah]
0x140030f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f3d  lea     r8, WPP_4d99b8df44273fb485b6255fcb87282b_Traceguids
0x140030f44  mov     rcx, [rcx+10h]
0x140030f48  call    WPP_SF_Ds
0x140030f4d  mov     ebx, 80004003h
0x140030f52  jmp     loc_140031020
0x140030f57  mov     dword ptr [rdx], 0
0x140030f5d  lea     rax, [rsp+58h+hKey]
0x140030f62  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140030f69  mov     [rsp+58h+phkResult], rax; phkResult
0x140030f6e  mov     r9d, 20019h; samDesired
0x140030f74  xor     r8d, r8d; ulOptions
0x140030f77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140030f7e  call    cs:__imp_RegOpenKeyExW
0x140030f84  mov     ebx, eax
0x140030f86  test    eax, eax
0x140030f88  jnz     short loc_140030FD2
0x140030f8a  mov     rcx, [rsp+58h+hKey]; hKey
0x140030f8f  lea     r9, [rsp+58h+Type]; lpType
0x140030f94  mov     [rsp+58h+Data], eax
0x140030f98  xor     r8d, r8d; lpReserved
0x140030f9b  mov     [rsp+58h+Type], eax
0x140030f9f  mov     rdx, rsi; lpValueName
0x140030fa2  lea     rax, [rsp+58h+cbData]
0x140030fa7  mov     [rsp+58h+cbData], 4
0x140030faf  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140030fb4  lea     rax, [rsp+58h+Data]
0x140030fb9  mov     [rsp+58h+phkResult], rax; lpData
0x140030fbe  call    cs:__imp_RegQueryValueExW
0x140030fc4  test    eax, eax
0x140030fc6  jnz     short loc_140030FCE
0x140030fc8  mov     eax, [rsp+58h+Data]
0x140030fcc  mov     [rdi], eax
0x140030fce  xor     ebx, ebx
0x140030fd0  jmp     short loc_140031020
0x140030fd2  jle     short loc_140030FDD
0x140030fd4  movzx   ebx, ax
0x140030fd7  or      ebx, 80070000h
0x140030fdd  mov     rax, cs:WPP_GLOBAL_Control
0x140030fe4  lea     rcx, WPP_GLOBAL_Control
0x140030feb  cmp     rax, rcx
0x140030fee  jz      short loc_140031020
0x140030ff0  test    byte ptr [rax+1Ch], 1
0x140030ff4  jz      short loc_140031020
0x140030ff6  cmp     byte ptr [rax+19h], 2
0x140030ffa  jb      short loc_140031020
0x140030ffc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140031001  mov     rcx, cs:WPP_GLOBAL_Control
0x140031008  lea     r8, WPP_4d99b8df44273fb485b6255fcb87282b_Traceguids
0x14003100f  mov     edx, 0Bh
0x140031014  mov     r9d, eax
0x140031017  mov     rcx, [rcx+10h]
0x14003101b  call    WPP_SF_d
0x140031020  mov     rcx, [rsp+58h+hKey]; hKey
0x140031025  test    rcx, rcx
0x140031028  jz      short loc_140031030
0x14003102a  call    cs:__imp_RegCloseKey
0x140031030  mov     eax, ebx
0x140031032  add     rsp, 40h
0x140031036  pop     rdi
0x140031037  pop     rsi
0x140031038  pop     rbx
0x140031039  retn
```
