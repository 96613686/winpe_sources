# CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)

- ea: `0x1400a3b40`
- end: `0x1400a3db1`
- name: `?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z`
- size: `625`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, LPBYTE lpData, int, char, unsigned int *, int)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400a3910`
- `0x1400a3dc0`
- `0x1400a3e20`
- `0x1400a40f0`
- `0x1400a4300`
- `0x1400a4740`
- `0x1400a48c0`

## callees

- `0x14000b7d8`
- `0x1400a3554`
- `0x1400a3b40`
- `0x1400a545c`
- `0x1400a553c`
- `0x1400a5634`
- `0x1400a56d4`
- `0x140113390`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400a3bdc`
- `ADVAPI32!RegOpenKeyExW` at `0x1400a3bdc`
- `ADVAPI32!RegCloseKey` at `0x1400a3d46`
- `ADVAPI32!RegCloseKey` at `0x1400a3d46`
- `ADVAPI32!RegQueryValueExW` at `0x1400a3c6c`
- `ADVAPI32!RegQueryValueExW` at `0x1400a3c6c`

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
0x1400a3b40  push    rbp
0x1400a3b42  push    rbx
0x1400a3b43  push    rsi
0x1400a3b44  push    rdi
0x1400a3b45  push    r12
0x1400a3b47  push    r13
0x1400a3b49  push    r14
0x1400a3b4b  push    r15
0x1400a3b4d  lea     rbp, [rsp-188h]
0x1400a3b55  sub     rsp, 288h
0x1400a3b5c  mov     rax, cs:__security_cookie
0x1400a3b63  xor     rax, rsp
0x1400a3b66  mov     [rbp+1C0h+var_50], rax
0x1400a3b6d  mov     rdi, [rbp+1C0h+arg_30]
0x1400a3b74  xor     r12d, r12d
0x1400a3b77  mov     [rsp+2C0h+hKey], 0
0x1400a3b80  mov     r14, r9
0x1400a3b83  mov     [rsp+2C0h+Type], 0
0x1400a3b8b  mov     r13, r8
0x1400a3b8e  mov     [rsp+2C0h+cbData], 0
0x1400a3b96  mov     r15, rdx
0x1400a3b99  mov     rsi, rcx
0x1400a3b9c  test    rdi, rdi
0x1400a3b9f  jz      short loc_1400A3BA4
0x1400a3ba1  mov     [rdi], r12d
0x1400a3ba4  mov     ebx, [rbp+1C0h+arg_38]
0x1400a3baa  test    ebx, ebx
0x1400a3bac  jnz     short loc_1400A3BBB
0x1400a3bae  mov     r8, r15; unsigned __int16 *
0x1400a3bb1  lea     rcx, [rsp+2C0h+var_270]; unsigned __int16 *
0x1400a3bb6  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x1400a3bbb  lea     rax, [rsp+2C0h+hKey]
0x1400a3bc0  test    ebx, ebx
0x1400a3bc2  lea     rdx, [rsp+2C0h+var_270]
0x1400a3bc7  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1400a3bcc  cmovnz  rdx, r15; lpSubKey
0x1400a3bd0  mov     r9d, 20019h; samDesired
0x1400a3bd6  xor     r8d, r8d; ulOptions
0x1400a3bd9  mov     rcx, rsi; hKey
0x1400a3bdc  call    cs:__imp_RegOpenKeyExW
0x1400a3be2  mov     esi, eax
0x1400a3be4  test    eax, eax
0x1400a3be6  jz      short loc_1400A3C43
0x1400a3be8  mov     rax, cs:WPP_GLOBAL_Control
0x1400a3bef  lea     rbx, WPP_GLOBAL_Control
0x1400a3bf6  cmp     rax, rbx
0x1400a3bf9  jz      loc_1400A3D8B
0x1400a3bff  test    byte ptr [rax+1Ch], 1
0x1400a3c03  jz      loc_1400A3D8B
0x1400a3c09  cmp     byte ptr [rax+19h], 4
0x1400a3c0d  jb      loc_1400A3D8B
0x1400a3c13  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a3c18  lea     rcx, [rsp+2C0h+var_270]
0x1400a3c1d  mov     dword ptr [rsp+2C0h+lpcbData], esi
0x1400a3c21  mov     [rsp+2C0h+phkResult], rcx
0x1400a3c26  mov     edx, 0Ch
0x1400a3c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3c32  mov     r9d, eax
0x1400a3c35  mov     rcx, [rcx+10h]
0x1400a3c39  call    WPP_SF_DSl
0x1400a3c3e  jmp     loc_1400A3D8B
0x1400a3c43  mov     eax, [rbp+1C0h+arg_20]
0x1400a3c49  lea     r9, [rsp+2C0h+Type]; lpType
0x1400a3c4e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400a3c53  xor     r8d, r8d; lpReserved
0x1400a3c56  mov     [rsp+2C0h+cbData], eax
0x1400a3c5a  mov     rdx, r13; lpValueName
0x1400a3c5d  lea     rax, [rsp+2C0h+cbData]
0x1400a3c62  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x1400a3c67  mov     [rsp+2C0h+phkResult], r14; lpData
0x1400a3c6c  call    cs:__imp_RegQueryValueExW
0x1400a3c72  lea     rbx, WPP_GLOBAL_Control
0x1400a3c79  mov     esi, eax
0x1400a3c7b  test    eax, eax
0x1400a3c7d  jz      short loc_1400A3CCB
0x1400a3c7f  mov     rax, cs:WPP_GLOBAL_Control
0x1400a3c86  cmp     rax, rbx
0x1400a3c89  jz      loc_1400A3D41
0x1400a3c8f  test    byte ptr [rax+1Ch], 1
0x1400a3c93  jz      loc_1400A3D41
0x1400a3c99  cmp     byte ptr [rax+19h], 4
0x1400a3c9d  jb      loc_1400A3D41
0x1400a3ca3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a3ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3caf  mov     r9d, eax
0x1400a3cb2  mov     dword ptr [rsp+2C0h+var_290], esi; char
0x1400a3cb6  mov     [rsp+2C0h+lpcbData], r13; __int64
0x1400a3cbb  mov     [rsp+2C0h+phkResult], r15; __int64
0x1400a3cc0  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a3cc4  call    WPP_SF_DSSl
0x1400a3cc9  jmp     short loc_1400A3D41
0x1400a3ccb  mov     esi, [rsp+2C0h+Type]
0x1400a3ccf  mov     r14d, dword ptr [rbp+1C0h+arg_28]
0x1400a3cd6  mov     eax, [rsp+2C0h+cbData]
0x1400a3cda  cmp     esi, r14d
0x1400a3cdd  jz      short loc_1400A3D34
0x1400a3cdf  cmp     esi, 3
0x1400a3ce2  jnz     short loc_1400A3CEF
0x1400a3ce4  cmp     r14d, 4
0x1400a3ce8  jnz     short loc_1400A3CEF
0x1400a3cea  cmp     eax, r14d
0x1400a3ced  jz      short loc_1400A3D34
0x1400a3cef  mov     rax, cs:WPP_GLOBAL_Control
0x1400a3cf6  cmp     rax, rbx
0x1400a3cf9  jz      short loc_1400A3D41
0x1400a3cfb  test    byte ptr [rax+1Ch], 1
0x1400a3cff  jz      short loc_1400A3D41
0x1400a3d01  cmp     byte ptr [rax+19h], 3
0x1400a3d05  jb      short loc_1400A3D41
0x1400a3d07  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a3d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3d13  mov     r9d, eax
0x1400a3d16  mov     dword ptr [rsp+2C0h+var_288], r14d; char
0x1400a3d1b  mov     dword ptr [rsp+2C0h+var_290], esi; char
0x1400a3d1f  mov     [rsp+2C0h+lpcbData], r13; __int64
0x1400a3d24  mov     rcx, [rcx+10h]; LoggerHandle
0x1400a3d28  mov     [rsp+2C0h+phkResult], r15; __int64
0x1400a3d2d  call    WPP_SF_DSSll
0x1400a3d32  jmp     short loc_1400A3D41
0x1400a3d34  test    rdi, rdi
0x1400a3d37  jz      short loc_1400A3D3B
0x1400a3d39  mov     [rdi], eax
0x1400a3d3b  mov     r12d, 1
0x1400a3d41  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400a3d46  call    cs:__imp_RegCloseKey
0x1400a3d4c  mov     edi, eax
0x1400a3d4e  test    eax, eax
0x1400a3d50  jz      short loc_1400A3D8B
0x1400a3d52  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3d59  cmp     rcx, rbx
0x1400a3d5c  jz      short loc_1400A3D8B
0x1400a3d5e  test    byte ptr [rcx+1Ch], 1
0x1400a3d62  jz      short loc_1400A3D8B
0x1400a3d64  cmp     byte ptr [rcx+19h], 2
0x1400a3d68  jb      short loc_1400A3D8B
0x1400a3d6a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a3d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a3d76  mov     edx, 0Fh
0x1400a3d7b  mov     r9d, eax
0x1400a3d7e  mov     dword ptr [rsp+2C0h+phkResult], edi
0x1400a3d82  mov     rcx, [rcx+10h]
0x1400a3d86  call    WPP_SF_Dl
0x1400a3d8b  mov     eax, r12d
0x1400a3d8e  mov     rcx, [rbp+1C0h+var_50]
0x1400a3d95  xor     rcx, rsp; StackCookie
0x1400a3d98  call    __security_check_cookie
0x1400a3d9d  add     rsp, 288h
0x1400a3da4  pop     r15
0x1400a3da6  pop     r14
0x1400a3da8  pop     r13
0x1400a3daa  pop     r12
0x1400a3dac  pop     rdi
0x1400a3dad  pop     rsi
0x1400a3dae  pop     rbx
0x1400a3daf  pop     rbp
0x1400a3db0  retn
```
