# CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)

- ea: `0x1400a2b5c`
- end: `0x1400a2e1c`
- name: `?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z`
- size: `704`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, BYTE *lpData, DWORD cbData, DWORD dwType)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400a29b0`
- `0x1400a2e30`
- `0x1400a2e80`
- `0x1400a3040`

## callees

- `0x14000b7d8`
- `0x14001e210`
- `0x140040a2c`
- `0x1400a13e4`
- `0x1400a2b5c`
- `0x1400a3564`
- `0x140111220`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1400a2be6`
- `ADVAPI32!RegCreateKeyExW` at `0x1400a2be6`
- `ADVAPI32!RegSetValueExW` at `0x1400a2d19`
- `ADVAPI32!RegSetValueExW` at `0x1400a2d19`
- `ADVAPI32!RegCloseKey` at `0x1400a2db4`
- `ADVAPI32!RegCloseKey` at `0x1400a2db4`

## string_xrefs

- `0x1400a2cba`: `Created`
- `0x1400a2cb3`: `Opened`

## pseudocode

```c
__int64 __fastcall CClientUtils::WriteRegistryEntry(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *lpData,
        DWORD cbData,
        DWORD dwType)
{
  unsigned int v10; // esi
  LSTATUS v11; // ebx
  PVOID *v12; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v14; // r8
  unsigned int v15; // eax
  const wchar_t *v16; // rbx
  LSTATUS v17; // ebx
  PVOID *v18; // rax
  unsigned int v19; // eax
  __int64 v20; // r8
  LSTATUS v21; // ebx
  unsigned int v22; // eax
  __int64 v23; // r8
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[272]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  dwDisposition = 0;
  v10 = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  v11 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &hKeya, &dwDisposition);
  if ( v11 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v14, CurrentThreadActivityIdPrefix, v11);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 3u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          v15,
          (__int64)SubKey);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v16 = L"Created";
      if ( dwDisposition != 1 )
        v16 = (const wchar_t *)L"Opened";
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v16, (__int64)SubKey);
    }
    v17 = RegSetValueExW(hKeya, a3, 0, dwType, lpData, cbData);
    if ( v17 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v20, v19, v17);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 3u )
        {
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
        }
      }
    }
    else
    {
      v10 = 1;
    }
    v21 = RegCloseKey(hKeya);
    if ( v21
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v23, v22, v21);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1400a2b5c  push    rbp
0x1400a2b5e  push    rbx
0x1400a2b5f  push    rsi
0x1400a2b60  push    rdi
0x1400a2b61  push    r12
0x1400a2b63  push    r14
0x1400a2b65  push    r15
0x1400a2b67  lea     rbp, [rsp-190h]
0x1400a2b6f  sub     rsp, 290h
0x1400a2b76  mov     rax, cs:__security_cookie
0x1400a2b7d  xor     rax, rsp
0x1400a2b80  mov     [rbp+1C0h+var_40], rax
0x1400a2b87  mov     r14, r8
0x1400a2b8a  mov     [rsp+2C0h+hKey], 0
0x1400a2b93  mov     rbx, rcx
0x1400a2b96  mov     [rsp+2C0h+dwDisposition], 0
0x1400a2b9e  mov     r8, rdx; unsigned __int16 *
0x1400a2ba1  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1400a2ba6  mov     r15, r9
0x1400a2ba9  mov     r12, rdx
0x1400a2bac  xor     esi, esi
0x1400a2bae  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a2bb3  lea     rax, [rsp+2C0h+dwDisposition]
0x1400a2bb8  xor     r9d, r9d; lpClass
0x1400a2bbb  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x1400a2bc0  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1400a2bc5  lea     rax, [rsp+2C0h+hKey]
0x1400a2bca  xor     r8d, r8d; Reserved
0x1400a2bcd  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1400a2bd2  mov     rcx, rbx; hKey
0x1400a2bd5  mov     [rsp+2C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1400a2bda  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x1400a2be2  mov     [rsp+2C0h+dwOptions], esi; dwOptions
0x1400a2be6  call    cs:__imp_RegCreateKeyExW
0x1400a2bec  mov     ebx, eax
0x1400a2bee  test    eax, eax
0x1400a2bf0  jz      loc_1400A2C8F
0x1400a2bf6  mov     rax, cs:WPP_GLOBAL_Control
0x1400a2bfd  lea     rdi, WPP_GLOBAL_Control
0x1400a2c04  cmp     rax, rdi
0x1400a2c07  jz      loc_1400A2DF9
0x1400a2c0d  test    byte ptr [rax+1Ch], 1
0x1400a2c11  jz      short loc_1400A2C3F
0x1400a2c13  cmp     byte ptr [rax+19h], 2
0x1400a2c17  jb      short loc_1400A2C3F
0x1400a2c19  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2c25  lea     edx, [rsi+10h]
0x1400a2c28  mov     r9d, eax
0x1400a2c2b  mov     [rsp+2C0h+dwOptions], ebx
0x1400a2c2f  mov     rcx, [rcx+10h]
0x1400a2c33  call    WPP_SF_Dl
0x1400a2c38  mov     rax, cs:WPP_GLOBAL_Control
0x1400a2c3f  cmp     rax, rdi
0x1400a2c42  jz      loc_1400A2DF9
0x1400a2c48  test    byte ptr [rax+1Ch], 1
0x1400a2c4c  jz      loc_1400A2DF9
0x1400a2c52  cmp     byte ptr [rax+19h], 3
0x1400a2c56  jb      loc_1400A2DF9
0x1400a2c5c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2c61  lea     rcx, [rsp+2C0h+SubKey]
0x1400a2c66  mov     edx, 11h
0x1400a2c6b  mov     qword ptr [rsp+2C0h+dwOptions], rcx
0x1400a2c70  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2c77  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2c7e  mov     r9d, eax
0x1400a2c81  mov     rcx, [rcx+10h]
0x1400a2c85  call    WPP_SF_DS
0x1400a2c8a  jmp     loc_1400A2DF9
0x1400a2c8f  mov     rax, cs:WPP_GLOBAL_Control
0x1400a2c96  lea     rdi, WPP_GLOBAL_Control
0x1400a2c9d  cmp     rax, rdi
0x1400a2ca0  jz      short loc_1400A2CF8
0x1400a2ca2  test    byte ptr [rax+1Ch], 1
0x1400a2ca6  jz      short loc_1400A2CF8
0x1400a2ca8  cmp     byte ptr [rax+19h], 4
0x1400a2cac  jb      short loc_1400A2CF8
0x1400a2cae  cmp     [rsp+2C0h+dwDisposition], 1
0x1400a2cb3  lea     rax, aOpened; "Opened"
0x1400a2cba  lea     rbx, aCreated; "Created"
0x1400a2cc1  cmovnz  rbx, rax
0x1400a2cc5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2cca  lea     rcx, [rsp+2C0h+SubKey]
0x1400a2ccf  mov     edx, 12h
0x1400a2cd4  mov     qword ptr [rsp+2C0h+samDesired], rcx; __int64
0x1400a2cd9  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2ce7  mov     r9d, eax
0x1400a2cea  mov     qword ptr [rsp+2C0h+dwOptions], rbx; __int64
0x1400a2cef  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a2cf3  call    WPP_SF_DSS
0x1400a2cf8  mov     eax, [rbp+1C0h+cbData]
0x1400a2cfe  xor     r8d, r8d; Reserved
0x1400a2d01  mov     r9d, [rbp+1C0h+dwType]; dwType
0x1400a2d08  mov     rdx, r14; lpValueName
0x1400a2d0b  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400a2d10  mov     [rsp+2C0h+samDesired], eax; cbData
0x1400a2d14  mov     qword ptr [rsp+2C0h+dwOptions], r15; lpData
0x1400a2d19  call    cs:__imp_RegSetValueExW
0x1400a2d1f  mov     ebx, eax
0x1400a2d21  test    eax, eax
0x1400a2d23  jz      loc_1400A2DAA
0x1400a2d29  mov     rax, cs:WPP_GLOBAL_Control
0x1400a2d30  cmp     rax, rdi
0x1400a2d33  jz      short loc_1400A2DAF
0x1400a2d35  test    byte ptr [rax+1Ch], 1
0x1400a2d39  jz      short loc_1400A2D69
0x1400a2d3b  cmp     byte ptr [rax+19h], 2
0x1400a2d3f  jb      short loc_1400A2D69
0x1400a2d41  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2d46  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2d4d  mov     edx, 13h
0x1400a2d52  mov     r9d, eax
0x1400a2d55  mov     [rsp+2C0h+dwOptions], ebx
0x1400a2d59  mov     rcx, [rcx+10h]
0x1400a2d5d  call    WPP_SF_Dl
0x1400a2d62  mov     rax, cs:WPP_GLOBAL_Control
0x1400a2d69  cmp     rax, rdi
0x1400a2d6c  jz      short loc_1400A2DAF
0x1400a2d6e  test    byte ptr [rax+1Ch], 1
0x1400a2d72  jz      short loc_1400A2DAF
0x1400a2d74  cmp     byte ptr [rax+19h], 3
0x1400a2d78  jb      short loc_1400A2DAF
0x1400a2d7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2d86  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a2d8d  mov     edx, 14h
0x1400a2d92  mov     qword ptr [rsp+2C0h+samDesired], r14; __int64
0x1400a2d97  mov     r9d, eax
0x1400a2d9a  mov     qword ptr [rsp+2C0h+dwOptions], r12; __int64
0x1400a2d9f  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a2da3  call    WPP_SF_DSS
0x1400a2da8  jmp     short loc_1400A2DAF
0x1400a2daa  mov     esi, 1
0x1400a2daf  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400a2db4  call    cs:__imp_RegCloseKey
0x1400a2dba  mov     ebx, eax
0x1400a2dbc  test    eax, eax
0x1400a2dbe  jz      short loc_1400A2DF9
0x1400a2dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2dc7  cmp     rcx, rdi
0x1400a2dca  jz      short loc_1400A2DF9
0x1400a2dcc  test    byte ptr [rcx+1Ch], 1
0x1400a2dd0  jz      short loc_1400A2DF9
0x1400a2dd2  cmp     byte ptr [rcx+19h], 2
0x1400a2dd6  jb      short loc_1400A2DF9
0x1400a2dd8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a2ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2de4  mov     edx, 15h
0x1400a2de9  mov     r9d, eax
0x1400a2dec  mov     [rsp+2C0h+dwOptions], ebx
0x1400a2df0  mov     rcx, [rcx+10h]
0x1400a2df4  call    WPP_SF_Dl
0x1400a2df9  mov     eax, esi
0x1400a2dfb  mov     rcx, [rbp+1C0h+var_40]
0x1400a2e02  xor     rcx, rsp; StackCookie
0x1400a2e05  call    __security_check_cookie
0x1400a2e0a  add     rsp, 290h
0x1400a2e11  pop     r15
0x1400a2e13  pop     r14
0x1400a2e15  pop     r12
0x1400a2e17  pop     rdi
0x1400a2e18  pop     rsi
0x1400a2e19  pop     rbx
0x1400a2e1a  pop     rbp
0x1400a2e1b  retn
```
