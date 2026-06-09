# CommandLineData::SHGetWebFilename(ushort const *)

- ea: `0x140055b60`
- end: `0x140055f5b`
- name: `?SHGetWebFilename@CommandLineData@@AEAAPEBGPEBG@Z`
- size: `1019`
- prototype: `const unsigned __int16 *__fastcall(CommandLineData *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140055350`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e158`
- `0x14001e210`
- `0x140054850`
- `0x1400550f0`
- `0x140055b60`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x140055c07`
- `SHLWAPI!PathFindExtensionW` at `0x140055c07`
- `KERNEL32!GetFileAttributesExW` at `0x140055d3b`
- `KERNEL32!GetFileAttributesExW` at `0x140055d3b`
- `KERNEL32!GetTempPathW` at `0x140055ca6`
- `KERNEL32!GetTempPathW` at `0x140055ca6`
- `KERNEL32!CompareStringW` at `0x140055c42`
- `KERNEL32!CompareStringW` at `0x140055c42`
- `KERNEL32!LoadLibraryExW` at `0x140055c60`
- `KERNEL32!LoadLibraryExW` at `0x140055c60`
- `KERNEL32!FreeLibrary` at `0x140055eee`
- `KERNEL32!FreeLibrary` at `0x140055eee`
- `KERNEL32!GetProcAddress` at `0x140055c78`
- `KERNEL32!GetProcAddress` at `0x140055c78`
- `KERNEL32!GetLastError` at `0x140055d45`
- `KERNEL32!GetLastError` at `0x140055d45`

## string_xrefs

- `0x140055c53`: `kernelbase.dll`
- `0x140055e0e`: `StringCchCopy failed`
- `0x140055c6e`: `GetTempPath2W`

## pseudocode

```c
const unsigned __int16 *__fastcall CommandLineData::SHGetWebFilename(CommandLineData *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // r14
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LPWSTR ExtensionW; // rax
  HMODULE Library; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // eax
  __int64 v10; // r9
  int v11; // edi
  unsigned int v12; // eax
  DWORD LastError; // edi
  unsigned int v14; // eax
  int v15; // eax
  char v16; // di
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int128 FileInformation; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h]
  unsigned int v24; // [rsp+50h] [rbp-B0h]
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF

  FileInformation = 0;
  v24 = 0;
  v23 = 0;
  v3 = CommandLineData::SHGetCmdLineString(this, a2, pszPath, 260);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)pszPath);
  }
  ExtensionW = PathFindExtensionW(pszPath);
  if ( ExtensionW && *ExtensionW && CompareStringW(0x7Fu, 1u, ExtensionW, -1, L".rdp", -1) == 2 )
  {
    Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
    v7 = Library;
    if ( Library && (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0 )
    {
      TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Buffer);
      v11 = 2;
    }
    else
    {
      TempPathW = GetTempPathW(0x104u, Buffer);
      v11 = 1;
    }
    if ( TempPathW - 1 > 0x102 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids, v19, v11);
      }
    }
    else if ( (unsigned int)CommandLineData::IsInDirOrSubDir(this, pszPath, Buffer, v10, 0) )
    {
      if ( GetFileAttributesExW(pszPath, GetFileExInfoStandard, &FileInformation) )
      {
        if ( HIDWORD(v23) || v24 > 0x10000 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DLD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
              v18,
              HIDWORD(v23),
              v24);
          }
        }
        else
        {
          v15 = StringCchCopyW((unsigned __int16 *)this + 2098, 0x104u, pszPath);
          v16 = v15;
          if ( v15 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              34,
              (unsigned int)WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
              v17,
              (__int64)"StringCchCopy failed",
              v16);
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids,
            v14,
            LastError);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids, v12);
    }
    if ( v7 )
      FreeLibrary(v7);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids, v20);
  }
  return v3;
}

```

## disassembly

```asm
0x140055b60  mov     [rsp-8+arg_10], rbx
0x140055b65  push    rbp
0x140055b66  push    rsi
0x140055b67  push    rdi
0x140055b68  push    r14
0x140055b6a  push    r15
0x140055b6c  lea     rbp, [rsp-390h]
0x140055b74  sub     rsp, 490h
0x140055b7b  mov     rax, cs:__security_cookie
0x140055b82  xor     rax, rsp
0x140055b85  mov     [rbp+3B0h+var_30], rax
0x140055b8c  xorps   xmm0, xmm0
0x140055b8f  lea     r8, [rsp+4B0h+pszPath]; unsigned __int16 *
0x140055b94  xor     eax, eax
0x140055b96  mov     r9d, 104h; int
0x140055b9c  movups  [rsp+4B0h+FileInformation], xmm0
0x140055ba1  mov     [rsp+4B0h+var_460], eax
0x140055ba5  mov     rsi, rcx
0x140055ba8  movups  [rsp+4B0h+var_470], xmm0
0x140055bad  call    ?SHGetCmdLineString@CommandLineData@@AEAAPEBGPEBGPEAGH@Z; CommandLineData::SHGetCmdLineString(ushort const *,ushort *,int)
0x140055bb2  mov     r14, rax
0x140055bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140055bbc  lea     rbx, WPP_GLOBAL_Control
0x140055bc3  cmp     rcx, rbx
0x140055bc6  jz      short loc_140055C02
0x140055bc8  test    byte ptr [rcx+1Ch], 1
0x140055bcc  jz      short loc_140055C02
0x140055bce  cmp     byte ptr [rcx+19h], 5
0x140055bd2  jb      short loc_140055C02
0x140055bd4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055bd9  lea     rcx, [rsp+4B0h+pszPath]
0x140055bde  mov     edx, 1Ch
0x140055be3  mov     [rsp+4B0h+lpString2], rcx
0x140055be8  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140055bef  mov     rcx, cs:WPP_GLOBAL_Control
0x140055bf6  mov     r9d, eax
0x140055bf9  mov     rcx, [rcx+10h]
0x140055bfd  call    WPP_SF_DS
0x140055c02  lea     rcx, [rsp+4B0h+pszPath]; pszPath
0x140055c07  call    cs:__imp_PathFindExtensionW
0x140055c0d  xor     r15d, r15d
0x140055c10  test    rax, rax
0x140055c13  jz      loc_140055EF6
0x140055c19  cmp     [rax], r15w
0x140055c1d  jz      loc_140055EF6
0x140055c23  lea     rcx, aRdp_0; ".rdp"
0x140055c2a  or      r9d, 0FFFFFFFFh; cchCount1
0x140055c2e  mov     [rsp+4B0h+cchCount2], r9d; cchCount2
0x140055c33  lea     edx, [r15+1]; dwCmpFlags
0x140055c37  mov     [rsp+4B0h+lpString2], rcx; lpString2
0x140055c3c  mov     r8, rax; lpString1
0x140055c3f  lea     ecx, [rdx+7Eh]; Locale
0x140055c42  call    cs:__imp_CompareStringW
0x140055c48  cmp     eax, 2
0x140055c4b  jnz     loc_140055EF6
0x140055c51  xor     edx, edx; hFile
0x140055c53  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140055c5a  mov     r8d, 800h; dwFlags
0x140055c60  call    cs:__imp_LoadLibraryExW
0x140055c66  mov     rbx, rax
0x140055c69  test    rax, rax
0x140055c6c  jz      short loc_140055C9A
0x140055c6e  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x140055c75  mov     rcx, rax; hModule
0x140055c78  call    cs:__imp_GetProcAddress
0x140055c7e  test    rax, rax
0x140055c81  jz      short loc_140055C9A
0x140055c83  lea     rdx, [rbp+3B0h+Buffer]
0x140055c8a  mov     ecx, 104h
0x140055c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055c94  lea     edi, [r15+2]
0x140055c98  jmp     short loc_140055CB1
0x140055c9a  lea     rdx, [rbp+3B0h+Buffer]; lpBuffer
0x140055ca1  mov     ecx, 104h; nBufferLength
0x140055ca6  call    cs:__imp_GetTempPathW
0x140055cac  mov     edi, 1
0x140055cb1  dec     eax
0x140055cb3  cmp     eax, 102h
0x140055cb8  ja      loc_140055E9F
0x140055cbe  lea     r8, [rbp+3B0h+Buffer]; unsigned __int16 *
0x140055cc5  mov     dword ptr [rsp+4B0h+lpString2], r15d; unsigned int
0x140055cca  lea     rdx, [rsp+4B0h+pszPath]; unsigned __int16 *
0x140055ccf  mov     rcx, rsi; this
0x140055cd2  call    ?IsInDirOrSubDir@CommandLineData@@AEAAHPEBG0II@Z; CommandLineData::IsInDirOrSubDir(ushort const *,ushort const *,uint,uint)
0x140055cd7  test    eax, eax
0x140055cd9  jnz     short loc_140055D2F
0x140055cdb  mov     rax, cs:WPP_GLOBAL_Control
0x140055ce2  lea     rdx, WPP_GLOBAL_Control
0x140055ce9  cmp     rax, rdx
0x140055cec  jz      loc_140055EE6
0x140055cf2  test    byte ptr [rax+1Ch], 1
0x140055cf6  jz      loc_140055EE6
0x140055cfc  cmp     byte ptr [rax+19h], 2
0x140055d00  jb      loc_140055EE6
0x140055d06  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d12  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140055d19  mov     edx, 1Fh
0x140055d1e  mov     r9d, eax
0x140055d21  mov     rcx, [rcx+10h]
0x140055d25  call    WPP_SF_d
0x140055d2a  jmp     loc_140055EE6
0x140055d2f  lea     r8, [rsp+4B0h+FileInformation]; lpFileInformation
0x140055d34  xor     edx, edx; fInfoLevelId
0x140055d36  lea     rcx, [rsp+4B0h+pszPath]; lpFileName
0x140055d3b  call    cs:__imp_GetFileAttributesExW
0x140055d41  test    eax, eax
0x140055d43  jnz     short loc_140055DA5
0x140055d45  call    cs:__imp_GetLastError
0x140055d4b  mov     edi, eax
0x140055d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d54  lea     rdx, WPP_GLOBAL_Control
0x140055d5b  cmp     rcx, rdx
0x140055d5e  jz      loc_140055EE6
0x140055d64  test    byte ptr [rcx+1Ch], 8
0x140055d68  jz      loc_140055EE6
0x140055d6e  cmp     byte ptr [rcx+19h], 2
0x140055d72  jb      loc_140055EE6
0x140055d78  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d84  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140055d8b  mov     edx, 20h ; ' '
0x140055d90  mov     dword ptr [rsp+4B0h+lpString2], edi
0x140055d94  mov     r9d, eax
0x140055d97  mov     rcx, [rcx+10h]
0x140055d9b  call    WPP_SF_Dd
0x140055da0  jmp     loc_140055EE6
0x140055da5  cmp     dword ptr [rsp+4B0h+var_470+0Ch], r15d
0x140055daa  jnz     loc_140055E42
0x140055db0  cmp     [rsp+4B0h+var_460], 10000h
0x140055db8  ja      loc_140055E42
0x140055dbe  lea     rcx, [rsi+1064h]; unsigned __int16 *
0x140055dc5  mov     edx, 104h; unsigned __int64
0x140055dca  lea     r8, [rsp+4B0h+pszPath]; unsigned __int16 *
0x140055dcf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140055dd4  mov     edi, eax
0x140055dd6  test    eax, eax
0x140055dd8  jns     loc_140055EE6
0x140055dde  mov     rcx, cs:WPP_GLOBAL_Control
0x140055de5  lea     rdx, WPP_GLOBAL_Control
0x140055dec  cmp     rcx, rdx
0x140055def  jz      loc_140055EE6
0x140055df5  test    byte ptr [rcx+1Ch], 8
0x140055df9  jz      loc_140055EE6
0x140055dff  cmp     byte ptr [rcx+19h], 2
0x140055e03  jb      loc_140055EE6
0x140055e09  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055e0e  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x140055e15  mov     [rsp+4B0h+cchCount2], edi
0x140055e19  mov     [rsp+4B0h+lpString2], rcx
0x140055e1e  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140055e25  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e2c  mov     edx, 22h ; '"'
0x140055e31  mov     r9d, eax
0x140055e34  mov     rcx, [rcx+10h]
0x140055e38  call    WPP_SF_DsD
0x140055e3d  jmp     loc_140055EE6
0x140055e42  mov     rax, cs:WPP_GLOBAL_Control
0x140055e49  lea     rdx, WPP_GLOBAL_Control
0x140055e50  cmp     rax, rdx
0x140055e53  jz      loc_140055EE6
0x140055e59  test    byte ptr [rax+1Ch], 1
0x140055e5d  jz      loc_140055EE6
0x140055e63  cmp     byte ptr [rax+19h], 2
0x140055e67  jb      short loc_140055EE6
0x140055e69  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055e6e  mov     ecx, [rsp+4B0h+var_460]
0x140055e72  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140055e79  mov     [rsp+4B0h+cchCount2], ecx
0x140055e7d  mov     edx, 21h ; '!'
0x140055e82  mov     ecx, dword ptr [rsp+4B0h+var_470+0Ch]
0x140055e86  mov     r9d, eax
0x140055e89  mov     dword ptr [rsp+4B0h+lpString2], ecx
0x140055e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e94  mov     rcx, [rcx+10h]
0x140055e98  call    WPP_SF_DLD
0x140055e9d  jmp     short loc_140055EE6
0x140055e9f  mov     rax, cs:WPP_GLOBAL_Control
0x140055ea6  lea     rdx, WPP_GLOBAL_Control
0x140055ead  cmp     rax, rdx
0x140055eb0  jz      short loc_140055EE6
0x140055eb2  test    byte ptr [rax+1Ch], 1
0x140055eb6  jz      short loc_140055EE6
0x140055eb8  cmp     byte ptr [rax+19h], 2
0x140055ebc  jb      short loc_140055EE6
0x140055ebe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x140055eca  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140055ed1  mov     edx, 1Eh
0x140055ed6  mov     dword ptr [rsp+4B0h+lpString2], edi
0x140055eda  mov     r9d, eax
0x140055edd  mov     rcx, [rcx+10h]
0x140055ee1  call    WPP_SF_Dd
0x140055ee6  test    rbx, rbx
0x140055ee9  jz      short loc_140055F32
0x140055eeb  mov     rcx, rbx; hLibModule
0x140055eee  call    cs:__imp_FreeLibrary
0x140055ef4  jmp     short loc_140055F32
0x140055ef6  mov     rax, cs:WPP_GLOBAL_Control
0x140055efd  cmp     rax, rbx
0x140055f00  jz      short loc_140055F32
0x140055f02  test    byte ptr [rax+1Ch], 1
0x140055f06  jz      short loc_140055F32
0x140055f08  cmp     byte ptr [rax+19h], 2
0x140055f0c  jb      short loc_140055F32
0x140055f0e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140055f13  mov     rcx, cs:WPP_GLOBAL_Control
0x140055f1a  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140055f21  mov     edx, 1Dh
0x140055f26  mov     r9d, eax
0x140055f29  mov     rcx, [rcx+10h]
0x140055f2d  call    WPP_SF_d
0x140055f32  mov     rax, r14
0x140055f35  mov     rcx, [rbp+3B0h+var_30]
0x140055f3c  xor     rcx, rsp; StackCookie
0x140055f3f  call    __security_check_cookie
0x140055f44  mov     rbx, [rsp+4B0h+arg_10]
0x140055f4c  add     rsp, 490h
0x140055f53  pop     r15
0x140055f55  pop     r14
0x140055f57  pop     rdi
0x140055f58  pop     rsi
0x140055f59  pop     rbp
0x140055f5a  retn
```
