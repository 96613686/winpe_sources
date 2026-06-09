# CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)

- ea: `0x1400a4ccc`
- end: `0x1400a4f8c`
- name: `?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z`
- size: `704`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, BYTE *lpData, DWORD cbData, DWORD dwType)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400a4b20`
- `0x1400a4fa0`
- `0x1400a4ff0`
- `0x1400a51b0`

## callees

- `0x14000b7d8`
- `0x14001e210`
- `0x140042b94`
- `0x1400a3554`
- `0x1400a4ccc`
- `0x1400a56d4`
- `0x140113390`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x1400a4d56`
- `ADVAPI32!RegCreateKeyExW` at `0x1400a4d56`
- `ADVAPI32!RegSetValueExW` at `0x1400a4e89`
- `ADVAPI32!RegSetValueExW` at `0x1400a4e89`
- `ADVAPI32!RegCloseKey` at `0x1400a4f24`
- `ADVAPI32!RegCloseKey` at `0x1400a4f24`

## string_xrefs

- `0x1400a4e2a`: `Created`
- `0x1400a4e23`: `Opened`

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
0x1400a4ccc  push    rbp
0x1400a4cce  push    rbx
0x1400a4ccf  push    rsi
0x1400a4cd0  push    rdi
0x1400a4cd1  push    r12
0x1400a4cd3  push    r14
0x1400a4cd5  push    r15
0x1400a4cd7  lea     rbp, [rsp-190h]
0x1400a4cdf  sub     rsp, 290h
0x1400a4ce6  mov     rax, cs:__security_cookie
0x1400a4ced  xor     rax, rsp
0x1400a4cf0  mov     [rbp+1C0h+var_40], rax
0x1400a4cf7  mov     r14, r8
0x1400a4cfa  mov     [rsp+2C0h+hKey], 0
0x1400a4d03  mov     rbx, rcx
0x1400a4d06  mov     [rsp+2C0h+dwDisposition], 0
0x1400a4d0e  mov     r8, rdx; unsigned __int16 *
0x1400a4d11  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x1400a4d16  mov     r15, r9
0x1400a4d19  mov     r12, rdx
0x1400a4d1c  xor     esi, esi
0x1400a4d1e  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a4d23  lea     rax, [rsp+2C0h+dwDisposition]
0x1400a4d28  xor     r9d, r9d; lpClass
0x1400a4d2b  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x1400a4d30  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1400a4d35  lea     rax, [rsp+2C0h+hKey]
0x1400a4d3a  xor     r8d, r8d; Reserved
0x1400a4d3d  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1400a4d42  mov     rcx, rbx; hKey
0x1400a4d45  mov     [rsp+2C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1400a4d4a  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x1400a4d52  mov     [rsp+2C0h+dwOptions], esi; dwOptions
0x1400a4d56  call    cs:__imp_RegCreateKeyExW
0x1400a4d5c  mov     ebx, eax
0x1400a4d5e  test    eax, eax
0x1400a4d60  jz      loc_1400A4DFF
0x1400a4d66  mov     rax, cs:WPP_GLOBAL_Control
0x1400a4d6d  lea     rdi, WPP_GLOBAL_Control
0x1400a4d74  cmp     rax, rdi
0x1400a4d77  jz      loc_1400A4F69
0x1400a4d7d  test    byte ptr [rax+1Ch], 1
0x1400a4d81  jz      short loc_1400A4DAF
0x1400a4d83  cmp     byte ptr [rax+19h], 2
0x1400a4d87  jb      short loc_1400A4DAF
0x1400a4d89  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a4d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4d95  lea     edx, [rsi+10h]
0x1400a4d98  mov     r9d, eax
0x1400a4d9b  mov     [rsp+2C0h+dwOptions], ebx
0x1400a4d9f  mov     rcx, [rcx+10h]
0x1400a4da3  call    WPP_SF_Dl
0x1400a4da8  mov     rax, cs:WPP_GLOBAL_Control
0x1400a4daf  cmp     rax, rdi
0x1400a4db2  jz      loc_1400A4F69
0x1400a4db8  test    byte ptr [rax+1Ch], 1
0x1400a4dbc  jz      loc_1400A4F69
0x1400a4dc2  cmp     byte ptr [rax+19h], 3
0x1400a4dc6  jb      loc_1400A4F69
0x1400a4dcc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a4dd1  lea     rcx, [rsp+2C0h+SubKey]
0x1400a4dd6  mov     edx, 11h
0x1400a4ddb  mov     qword ptr [rsp+2C0h+dwOptions], rcx
0x1400a4de0  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a4de7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4dee  mov     r9d, eax
0x1400a4df1  mov     rcx, [rcx+10h]
0x1400a4df5  call    WPP_SF_DS
0x1400a4dfa  jmp     loc_1400A4F69
0x1400a4dff  mov     rax, cs:WPP_GLOBAL_Control
0x1400a4e06  lea     rdi, WPP_GLOBAL_Control
0x1400a4e0d  cmp     rax, rdi
0x1400a4e10  jz      short loc_1400A4E68
0x1400a4e12  test    byte ptr [rax+1Ch], 1
0x1400a4e16  jz      short loc_1400A4E68
0x1400a4e18  cmp     byte ptr [rax+19h], 4
0x1400a4e1c  jb      short loc_1400A4E68
0x1400a4e1e  cmp     [rsp+2C0h+dwDisposition], 1
0x1400a4e23  lea     rax, aOpened; "Opened"
0x1400a4e2a  lea     rbx, aCreated; "Created"
0x1400a4e31  cmovnz  rbx, rax
0x1400a4e35  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a4e3a  lea     rcx, [rsp+2C0h+SubKey]
0x1400a4e3f  mov     edx, 12h
0x1400a4e44  mov     qword ptr [rsp+2C0h+samDesired], rcx; __int64
0x1400a4e49  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a4e50  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4e57  mov     r9d, eax
0x1400a4e5a  mov     qword ptr [rsp+2C0h+dwOptions], rbx; __int64
0x1400a4e5f  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a4e63  call    WPP_SF_DSS
0x1400a4e68  mov     eax, [rbp+1C0h+cbData]
0x1400a4e6e  xor     r8d, r8d; Reserved
0x1400a4e71  mov     r9d, [rbp+1C0h+dwType]; dwType
0x1400a4e78  mov     rdx, r14; lpValueName
0x1400a4e7b  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400a4e80  mov     [rsp+2C0h+samDesired], eax; cbData
0x1400a4e84  mov     qword ptr [rsp+2C0h+dwOptions], r15; lpData
0x1400a4e89  call    cs:__imp_RegSetValueExW
0x1400a4e8f  mov     ebx, eax
0x1400a4e91  test    eax, eax
0x1400a4e93  jz      loc_1400A4F1A
0x1400a4e99  mov     rax, cs:WPP_GLOBAL_Control
0x1400a4ea0  cmp     rax, rdi
0x1400a4ea3  jz      short loc_1400A4F1F
0x1400a4ea5  test    byte ptr [rax+1Ch], 1
0x1400a4ea9  jz      short loc_1400A4ED9
0x1400a4eab  cmp     byte ptr [rax+19h], 2
0x1400a4eaf  jb      short loc_1400A4ED9
0x1400a4eb1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a4eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4ebd  mov     edx, 13h
0x1400a4ec2  mov     r9d, eax
0x1400a4ec5  mov     [rsp+2C0h+dwOptions], ebx
0x1400a4ec9  mov     rcx, [rcx+10h]
0x1400a4ecd  call    WPP_SF_Dl
0x1400a4ed2  mov     rax, cs:WPP_GLOBAL_Control
0x1400a4ed9  cmp     rax, rdi
0x1400a4edc  jz      short loc_1400A4F1F
0x1400a4ede  test    byte ptr [rax+1Ch], 1
0x1400a4ee2  jz      short loc_1400A4F1F
0x1400a4ee4  cmp     byte ptr [rax+19h], 3
0x1400a4ee8  jb      short loc_1400A4F1F
0x1400a4eea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a4eef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4ef6  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x1400a4efd  mov     edx, 14h
0x1400a4f02  mov     qword ptr [rsp+2C0h+samDesired], r14; __int64
0x1400a4f07  mov     r9d, eax
0x1400a4f0a  mov     qword ptr [rsp+2C0h+dwOptions], r12; __int64
0x1400a4f0f  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a4f13  call    WPP_SF_DSS
0x1400a4f18  jmp     short loc_1400A4F1F
0x1400a4f1a  mov     esi, 1
0x1400a4f1f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400a4f24  call    cs:__imp_RegCloseKey
0x1400a4f2a  mov     ebx, eax
0x1400a4f2c  test    eax, eax
0x1400a4f2e  jz      short loc_1400A4F69
0x1400a4f30  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4f37  cmp     rcx, rdi
0x1400a4f3a  jz      short loc_1400A4F69
0x1400a4f3c  test    byte ptr [rcx+1Ch], 1
0x1400a4f40  jz      short loc_1400A4F69
0x1400a4f42  cmp     byte ptr [rcx+19h], 2
0x1400a4f46  jb      short loc_1400A4F69
0x1400a4f48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a4f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a4f54  mov     edx, 15h
0x1400a4f59  mov     r9d, eax
0x1400a4f5c  mov     [rsp+2C0h+dwOptions], ebx
0x1400a4f60  mov     rcx, [rcx+10h]
0x1400a4f64  call    WPP_SF_Dl
0x1400a4f69  mov     eax, esi
0x1400a4f6b  mov     rcx, [rbp+1C0h+var_40]
0x1400a4f72  xor     rcx, rsp; StackCookie
0x1400a4f75  call    __security_check_cookie
0x1400a4f7a  add     rsp, 290h
0x1400a4f81  pop     r15
0x1400a4f83  pop     r14
0x1400a4f85  pop     r12
0x1400a4f87  pop     rdi
0x1400a4f88  pop     rsi
0x1400a4f89  pop     rbx
0x1400a4f8a  pop     rbp
0x1400a4f8b  retn
```
