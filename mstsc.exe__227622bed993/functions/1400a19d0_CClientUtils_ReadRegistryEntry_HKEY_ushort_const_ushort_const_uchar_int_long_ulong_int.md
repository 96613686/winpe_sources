# CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)

- ea: `0x1400a19d0`
- end: `0x1400a1c41`
- name: `?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z`
- size: `625`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, LPBYTE lpData, int, char, unsigned int *, int)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400a17a0`
- `0x1400a1c50`
- `0x1400a1cb0`
- `0x1400a1f80`
- `0x1400a2190`
- `0x1400a25d0`
- `0x1400a2750`

## callees

- `0x14000b7d8`
- `0x1400a13e4`
- `0x1400a19d0`
- `0x1400a32ec`
- `0x1400a33cc`
- `0x1400a34c4`
- `0x1400a3564`
- `0x140111220`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400a1a6c`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a1a6c`
- `ADVAPI32!RegCloseKey` at `0x1400a1bd6`
- `ADVAPI32!RegCloseKey` at `0x1400a1bd6`
- `ADVAPI32!RegQueryValueExW` at `0x1400a1afc`
- `ADVAPI32!RegQueryValueExW` at `0x1400a1afc`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadRegistryEntry(
        HKEY hKey,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        LPBYTE lpData,
        DWORD a5,
        int a6,
        unsigned int *a7,
        int a8)
{
  unsigned int v8; // r12d
  unsigned __int16 *v13; // rdx
  LSTATUS v14; // eax
  char v15; // si
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v17; // r8d
  LSTATUS v18; // eax
  char v19; // si
  char v20; // si
  LSTATUS v21; // edi
  unsigned int v22; // eax
  __int64 v23; // r8
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v28[272]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = 0;
  hKeya = 0;
  Type = 0;
  cbData = 0;
  if ( a7 )
    *a7 = 0;
  if ( !a8 )
    CClientUtils::MakeSubKey(v28, (unsigned int)a2, a2);
  v13 = v28;
  if ( a8 )
    v13 = a2;
  v14 = RegOpenKeyExW(hKey, v13, 0, 0x20019u, &hKeya);
  v15 = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSl(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v17, CurrentThreadActivityIdPrefix, (__int64)v28, v15);
    }
  }
  else
  {
    cbData = a5;
    v18 = RegQueryValueExW(hKeya, a3, 0, &Type, lpData, &cbData);
    v19 = v18;
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSSl(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, v19);
      }
    }
    else
    {
      v20 = Type;
      if ( Type == a6 || Type == 3 && a6 == 4 && cbData == 4 )
      {
        if ( a7 )
          *a7 = cbData;
        v8 = 1;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DSSll(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3, v20, a6);
      }
    }
    v21 = RegCloseKey(hKeya);
    if ( v21
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v23, v22, v21);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1400a19d0  push    rbp
0x1400a19d2  push    rbx
0x1400a19d3  push    rsi
0x1400a19d4  push    rdi
0x1400a19d5  push    r12
0x1400a19d7  push    r13
0x1400a19d9  push    r14
0x1400a19db  push    r15
0x1400a19dd  lea     rbp, [rsp-188h]
0x1400a19e5  sub     rsp, 288h
0x1400a19ec  mov     rax, cs:__security_cookie
0x1400a19f3  xor     rax, rsp
0x1400a19f6  mov     [rbp+1C0h+var_50], rax
0x1400a19fd  mov     rdi, [rbp+1C0h+arg_30]
0x1400a1a04  xor     r12d, r12d
0x1400a1a07  mov     [rsp+2C0h+hKey], 0
0x1400a1a10  mov     r14, r9
0x1400a1a13  mov     [rsp+2C0h+Type], 0
0x1400a1a1b  mov     r13, r8
0x1400a1a1e  mov     [rsp+2C0h+cbData], 0
0x1400a1a26  mov     r15, rdx
0x1400a1a29  mov     rsi, rcx
0x1400a1a2c  test    rdi, rdi
0x1400a1a2f  jz      short loc_1400A1A34
0x1400a1a31  mov     [rdi], r12d
0x1400a1a34  mov     ebx, [rbp+1C0h+arg_38]
0x1400a1a3a  test    ebx, ebx
0x1400a1a3c  jnz     short loc_1400A1A4B
0x1400a1a3e  mov     r8, r15; unsigned __int16 *
0x1400a1a41  lea     rcx, [rsp+2C0h+var_270]; unsigned __int16 *
0x1400a1a46  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a1a4b  lea     rax, [rsp+2C0h+hKey]
0x1400a1a50  test    ebx, ebx
0x1400a1a52  lea     rdx, [rsp+2C0h+var_270]
0x1400a1a57  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1400a1a5c  cmovnz  rdx, r15; lpSubKey
0x1400a1a60  mov     r9d, 20019h; samDesired
0x1400a1a66  xor     r8d, r8d; ulOptions
0x1400a1a69  mov     rcx, rsi; hKey
0x1400a1a6c  call    cs:__imp_RegOpenKeyExW
0x1400a1a72  mov     esi, eax
0x1400a1a74  test    eax, eax
0x1400a1a76  jz      short loc_1400A1AD3
0x1400a1a78  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1a7f  lea     rbx, WPP_GLOBAL_Control
0x1400a1a86  cmp     rax, rbx
0x1400a1a89  jz      loc_1400A1C1B
0x1400a1a8f  test    byte ptr [rax+1Ch], 1
0x1400a1a93  jz      loc_1400A1C1B
0x1400a1a99  cmp     byte ptr [rax+19h], 4
0x1400a1a9d  jb      loc_1400A1C1B
0x1400a1aa3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1aa8  lea     rcx, [rsp+2C0h+var_270]
0x1400a1aad  mov     dword ptr [rsp+2C0h+lpcbData], esi
0x1400a1ab1  mov     [rsp+2C0h+phkResult], rcx
0x1400a1ab6  mov     edx, 0Ch
0x1400a1abb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1ac2  mov     r9d, eax
0x1400a1ac5  mov     rcx, [rcx+10h]
0x1400a1ac9  call    WPP_SF_DSl
0x1400a1ace  jmp     loc_1400A1C1B
0x1400a1ad3  mov     eax, [rbp+1C0h+arg_20]
0x1400a1ad9  lea     r9, [rsp+2C0h+Type]; lpType
0x1400a1ade  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400a1ae3  xor     r8d, r8d; lpReserved
0x1400a1ae6  mov     [rsp+2C0h+cbData], eax
0x1400a1aea  mov     rdx, r13; lpValueName
0x1400a1aed  lea     rax, [rsp+2C0h+cbData]
0x1400a1af2  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x1400a1af7  mov     [rsp+2C0h+phkResult], r14; lpData
0x1400a1afc  call    cs:__imp_RegQueryValueExW
0x1400a1b02  lea     rbx, WPP_GLOBAL_Control
0x1400a1b09  mov     esi, eax
0x1400a1b0b  test    eax, eax
0x1400a1b0d  jz      short loc_1400A1B5B
0x1400a1b0f  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1b16  cmp     rax, rbx
0x1400a1b19  jz      loc_1400A1BD1
0x1400a1b1f  test    byte ptr [rax+1Ch], 1
0x1400a1b23  jz      loc_1400A1BD1
0x1400a1b29  cmp     byte ptr [rax+19h], 4
0x1400a1b2d  jb      loc_1400A1BD1
0x1400a1b33  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1b38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1b3f  mov     r9d, eax
0x1400a1b42  mov     dword ptr [rsp+2C0h+var_290], esi; char
0x1400a1b46  mov     [rsp+2C0h+lpcbData], r13; __int64
0x1400a1b4b  mov     [rsp+2C0h+phkResult], r15; __int64
0x1400a1b50  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a1b54  call    WPP_SF_DSSl
0x1400a1b59  jmp     short loc_1400A1BD1
0x1400a1b5b  mov     esi, [rsp+2C0h+Type]
0x1400a1b5f  mov     r14d, dword ptr [rbp+1C0h+arg_28]
0x1400a1b66  mov     eax, [rsp+2C0h+cbData]
0x1400a1b6a  cmp     esi, r14d
0x1400a1b6d  jz      short loc_1400A1BC4
0x1400a1b6f  cmp     esi, 3
0x1400a1b72  jnz     short loc_1400A1B7F
0x1400a1b74  cmp     r14d, 4
0x1400a1b78  jnz     short loc_1400A1B7F
0x1400a1b7a  cmp     eax, r14d
0x1400a1b7d  jz      short loc_1400A1BC4
0x1400a1b7f  mov     rax, cs:WPP_GLOBAL_Control
0x1400a1b86  cmp     rax, rbx
0x1400a1b89  jz      short loc_1400A1BD1
0x1400a1b8b  test    byte ptr [rax+1Ch], 1
0x1400a1b8f  jz      short loc_1400A1BD1
0x1400a1b91  cmp     byte ptr [rax+19h], 3
0x1400a1b95  jb      short loc_1400A1BD1
0x1400a1b97  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1ba3  mov     r9d, eax
0x1400a1ba6  mov     dword ptr [rsp+2C0h+var_288], r14d; char
0x1400a1bab  mov     dword ptr [rsp+2C0h+var_290], esi; char
0x1400a1baf  mov     [rsp+2C0h+lpcbData], r13; __int64
0x1400a1bb4  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a1bb8  mov     [rsp+2C0h+phkResult], r15; __int64
0x1400a1bbd  call    WPP_SF_DSSll
0x1400a1bc2  jmp     short loc_1400A1BD1
0x1400a1bc4  test    rdi, rdi
0x1400a1bc7  jz      short loc_1400A1BCB
0x1400a1bc9  mov     [rdi], eax
0x1400a1bcb  mov     r12d, 1
0x1400a1bd1  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400a1bd6  call    cs:__imp_RegCloseKey
0x1400a1bdc  mov     edi, eax
0x1400a1bde  test    eax, eax
0x1400a1be0  jz      short loc_1400A1C1B
0x1400a1be2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1be9  cmp     rcx, rbx
0x1400a1bec  jz      short loc_1400A1C1B
0x1400a1bee  test    byte ptr [rcx+1Ch], 1
0x1400a1bf2  jz      short loc_1400A1C1B
0x1400a1bf4  cmp     byte ptr [rcx+19h], 2
0x1400a1bf8  jb      short loc_1400A1C1B
0x1400a1bfa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a1bff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1c06  mov     edx, 0Fh
0x1400a1c0b  mov     r9d, eax
0x1400a1c0e  mov     dword ptr [rsp+2C0h+phkResult], edi
0x1400a1c12  mov     rcx, [rcx+10h]
0x1400a1c16  call    WPP_SF_Dl
0x1400a1c1b  mov     eax, r12d
0x1400a1c1e  mov     rcx, [rbp+1C0h+var_50]
0x1400a1c25  xor     rcx, rsp; StackCookie
0x1400a1c28  call    __security_check_cookie
0x1400a1c2d  add     rsp, 288h
0x1400a1c34  pop     r15
0x1400a1c36  pop     r14
0x1400a1c38  pop     r13
0x1400a1c3a  pop     r12
0x1400a1c3c  pop     rdi
0x1400a1c3d  pop     rsi
0x1400a1c3e  pop     rbx
0x1400a1c3f  pop     rbp
0x1400a1c40  retn
```
