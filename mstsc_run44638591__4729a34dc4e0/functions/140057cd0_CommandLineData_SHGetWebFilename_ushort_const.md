# CommandLineData::SHGetWebFilename(ushort const *)

- ea: `0x140057cd0`
- end: `0x1400580cb`
- name: `?SHGetWebFilename@CommandLineData@@AEAAPEBGPEBG@Z`
- size: `1019`
- prototype: `const unsigned __int16 *__fastcall(CommandLineData *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400574c0`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e158`
- `0x14001e210`
- `0x1400569c0`
- `0x140057260`
- `0x140057cd0`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x140057d77`
- `SHLWAPI!PathFindExtensionW` at `0x140057d77`
- `KERNEL32!GetFileAttributesExW` at `0x140057eab`
- `KERNEL32!GetFileAttributesExW` at `0x140057eab`
- `KERNEL32!GetTempPathW` at `0x140057e16`
- `KERNEL32!GetTempPathW` at `0x140057e16`
- `KERNEL32!CompareStringW` at `0x140057db2`
- `KERNEL32!CompareStringW` at `0x140057db2`
- `KERNEL32!LoadLibraryExW` at `0x140057dd0`
- `KERNEL32!LoadLibraryExW` at `0x140057dd0`
- `KERNEL32!FreeLibrary` at `0x14005805e`
- `KERNEL32!FreeLibrary` at `0x14005805e`
- `KERNEL32!GetProcAddress` at `0x140057de8`
- `KERNEL32!GetProcAddress` at `0x140057de8`
- `KERNEL32!GetLastError` at `0x140057eb5`
- `KERNEL32!GetLastError` at `0x140057eb5`

## string_xrefs

- `0x140057dc3`: `kernelbase.dll`
- `0x140057f7e`: `StringCchCopy failed`
- `0x140057dde`: `GetTempPath2W`

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
0x140057cd0  mov     [rsp-8+arg_10], rbx
0x140057cd5  push    rbp
0x140057cd6  push    rsi
0x140057cd7  push    rdi
0x140057cd8  push    r14
0x140057cda  push    r15
0x140057cdc  lea     rbp, [rsp-390h]
0x140057ce4  sub     rsp, 490h
0x140057ceb  mov     rax, cs:__security_cookie
0x140057cf2  xor     rax, rsp
0x140057cf5  mov     [rbp+3B0h+var_30], rax
0x140057cfc  xorps   xmm0, xmm0
0x140057cff  lea     r8, [rsp+4B0h+pszPath]; unsigned __int16 *
0x140057d04  xor     eax, eax
0x140057d06  mov     r9d, 104h; int
0x140057d0c  movups  [rsp+4B0h+FileInformation], xmm0
0x140057d11  mov     [rsp+4B0h+var_460], eax
0x140057d15  mov     rsi, rcx
0x140057d18  movups  [rsp+4B0h+var_470], xmm0
0x140057d1d  call    ?SHGetCmdLineString@CommandLineData@@AEAAPEBGPEBGPEAGH@Z; CommandLineData::SHGetCmdLineString(ushort const *,ushort *,int)
0x140057d22  mov     r14, rax
0x140057d25  mov     rcx, cs:WPP_GLOBAL_Control
0x140057d2c  lea     rbx, WPP_GLOBAL_Control
0x140057d33  cmp     rcx, rbx
0x140057d36  jz      short loc_140057D72
0x140057d38  test    byte ptr [rcx+1Ch], 1
0x140057d3c  jz      short loc_140057D72
0x140057d3e  cmp     byte ptr [rcx+19h], 5
0x140057d42  jb      short loc_140057D72
0x140057d44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140057d49  lea     rcx, [rsp+4B0h+pszPath]
0x140057d4e  mov     edx, 1Ch
0x140057d53  mov     [rsp+4B0h+lpString2], rcx
0x140057d58  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140057d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140057d66  mov     r9d, eax
0x140057d69  mov     rcx, [rcx+10h]
0x140057d6d  call    WPP_SF_DS
0x140057d72  lea     rcx, [rsp+4B0h+pszPath]; pszPath
0x140057d77  call    cs:__imp_PathFindExtensionW
0x140057d7d  xor     r15d, r15d
0x140057d80  test    rax, rax
0x140057d83  jz      loc_140058066
0x140057d89  cmp     [rax], r15w
0x140057d8d  jz      loc_140058066
0x140057d93  lea     rcx, aRdp_0; ".rdp"
0x140057d9a  or      r9d, 0FFFFFFFFh; cchCount1
0x140057d9e  mov     [rsp+4B0h+cchCount2], r9d; cchCount2
0x140057da3  lea     edx, [r15+1]; dwCmpFlags
0x140057da7  mov     [rsp+4B0h+lpString2], rcx; lpString2
0x140057dac  mov     r8, rax; lpString1
0x140057daf  lea     ecx, [rdx+7Eh]; Locale
0x140057db2  call    cs:__imp_CompareStringW
0x140057db8  cmp     eax, 2
0x140057dbb  jnz     loc_140058066
0x140057dc1  xor     edx, edx; hFile
0x140057dc3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140057dca  mov     r8d, 800h; dwFlags
0x140057dd0  call    cs:__imp_LoadLibraryExW
0x140057dd6  mov     rbx, rax
0x140057dd9  test    rax, rax
0x140057ddc  jz      short loc_140057E0A
0x140057dde  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x140057de5  mov     rcx, rax; hModule
0x140057de8  call    cs:__imp_GetProcAddress
0x140057dee  test    rax, rax
0x140057df1  jz      short loc_140057E0A
0x140057df3  lea     rdx, [rbp+3B0h+Buffer]
0x140057dfa  mov     ecx, 104h
0x140057dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057e04  lea     edi, [r15+2]
0x140057e08  jmp     short loc_140057E21
0x140057e0a  lea     rdx, [rbp+3B0h+Buffer]; lpBuffer
0x140057e11  mov     ecx, 104h; nBufferLength
0x140057e16  call    cs:__imp_GetTempPathW
0x140057e1c  mov     edi, 1
0x140057e21  dec     eax
0x140057e23  cmp     eax, 102h
0x140057e28  ja      loc_14005800F
0x140057e2e  lea     r8, [rbp+3B0h+Buffer]; unsigned __int16 *
0x140057e35  mov     dword ptr [rsp+4B0h+lpString2], r15d; unsigned int
0x140057e3a  lea     rdx, [rsp+4B0h+pszPath]; unsigned __int16 *
0x140057e3f  mov     rcx, rsi; this
0x140057e42  call    ?IsInDirOrSubDir@CommandLineData@@AEAAHPEBG0II@Z; CommandLineData::IsInDirOrSubDir(ushort const *,ushort const *,uint,uint)
0x140057e47  test    eax, eax
0x140057e49  jnz     short loc_140057E9F
0x140057e4b  mov     rax, cs:WPP_GLOBAL_Control
0x140057e52  lea     rdx, WPP_GLOBAL_Control
0x140057e59  cmp     rax, rdx
0x140057e5c  jz      loc_140058056
0x140057e62  test    byte ptr [rax+1Ch], 1
0x140057e66  jz      loc_140058056
0x140057e6c  cmp     byte ptr [rax+19h], 2
0x140057e70  jb      loc_140058056
0x140057e76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140057e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140057e82  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140057e89  mov     edx, 1Fh
0x140057e8e  mov     r9d, eax
0x140057e91  mov     rcx, [rcx+10h]
0x140057e95  call    WPP_SF_d
0x140057e9a  jmp     loc_140058056
0x140057e9f  lea     r8, [rsp+4B0h+FileInformation]; lpFileInformation
0x140057ea4  xor     edx, edx; fInfoLevelId
0x140057ea6  lea     rcx, [rsp+4B0h+pszPath]; lpFileName
0x140057eab  call    cs:__imp_GetFileAttributesExW
0x140057eb1  test    eax, eax
0x140057eb3  jnz     short loc_140057F15
0x140057eb5  call    cs:__imp_GetLastError
0x140057ebb  mov     edi, eax
0x140057ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x140057ec4  lea     rdx, WPP_GLOBAL_Control
0x140057ecb  cmp     rcx, rdx
0x140057ece  jz      loc_140058056
0x140057ed4  test    byte ptr [rcx+1Ch], 8
0x140057ed8  jz      loc_140058056
0x140057ede  cmp     byte ptr [rcx+19h], 2
0x140057ee2  jb      loc_140058056
0x140057ee8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140057eed  mov     rcx, cs:WPP_GLOBAL_Control
0x140057ef4  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140057efb  mov     edx, 20h ; ' '
0x140057f00  mov     dword ptr [rsp+4B0h+lpString2], edi
0x140057f04  mov     r9d, eax
0x140057f07  mov     rcx, [rcx+10h]
0x140057f0b  call    WPP_SF_Dd
0x140057f10  jmp     loc_140058056
0x140057f15  cmp     dword ptr [rsp+4B0h+var_470+0Ch], r15d
0x140057f1a  jnz     loc_140057FB2
0x140057f20  cmp     [rsp+4B0h+var_460], 10000h
0x140057f28  ja      loc_140057FB2
0x140057f2e  lea     rcx, [rsi+1064h]; unsigned __int16 *
0x140057f35  mov     edx, 104h; unsigned __int64
0x140057f3a  lea     r8, [rsp+4B0h+pszPath]; unsigned __int16 *
0x140057f3f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140057f44  mov     edi, eax
0x140057f46  test    eax, eax
0x140057f48  jns     loc_140058056
0x140057f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f55  lea     rdx, WPP_GLOBAL_Control
0x140057f5c  cmp     rcx, rdx
0x140057f5f  jz      loc_140058056
0x140057f65  test    byte ptr [rcx+1Ch], 8
0x140057f69  jz      loc_140058056
0x140057f6f  cmp     byte ptr [rcx+19h], 2
0x140057f73  jb      loc_140058056
0x140057f79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140057f7e  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x140057f85  mov     [rsp+4B0h+cchCount2], edi
0x140057f89  mov     [rsp+4B0h+lpString2], rcx
0x140057f8e  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140057f95  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f9c  mov     edx, 22h ; '"'
0x140057fa1  mov     r9d, eax
0x140057fa4  mov     rcx, [rcx+10h]
0x140057fa8  call    WPP_SF_DsD
0x140057fad  jmp     loc_140058056
0x140057fb2  mov     rax, cs:WPP_GLOBAL_Control
0x140057fb9  lea     rdx, WPP_GLOBAL_Control
0x140057fc0  cmp     rax, rdx
0x140057fc3  jz      loc_140058056
0x140057fc9  test    byte ptr [rax+1Ch], 1
0x140057fcd  jz      loc_140058056
0x140057fd3  cmp     byte ptr [rax+19h], 2
0x140057fd7  jb      short loc_140058056
0x140057fd9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140057fde  mov     ecx, [rsp+4B0h+var_460]
0x140057fe2  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140057fe9  mov     [rsp+4B0h+cchCount2], ecx
0x140057fed  mov     edx, 21h ; '!'
0x140057ff2  mov     ecx, dword ptr [rsp+4B0h+var_470+0Ch]
0x140057ff6  mov     r9d, eax
0x140057ff9  mov     dword ptr [rsp+4B0h+lpString2], ecx
0x140057ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x140058004  mov     rcx, [rcx+10h]
0x140058008  call    WPP_SF_DLD
0x14005800d  jmp     short loc_140058056
0x14005800f  mov     rax, cs:WPP_GLOBAL_Control
0x140058016  lea     rdx, WPP_GLOBAL_Control
0x14005801d  cmp     rax, rdx
0x140058020  jz      short loc_140058056
0x140058022  test    byte ptr [rax+1Ch], 1
0x140058026  jz      short loc_140058056
0x140058028  cmp     byte ptr [rax+19h], 2
0x14005802c  jb      short loc_140058056
0x14005802e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058033  mov     rcx, cs:WPP_GLOBAL_Control
0x14005803a  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140058041  mov     edx, 1Eh
0x140058046  mov     dword ptr [rsp+4B0h+lpString2], edi
0x14005804a  mov     r9d, eax
0x14005804d  mov     rcx, [rcx+10h]
0x140058051  call    WPP_SF_Dd
0x140058056  test    rbx, rbx
0x140058059  jz      short loc_1400580A2
0x14005805b  mov     rcx, rbx; hLibModule
0x14005805e  call    cs:__imp_FreeLibrary
0x140058064  jmp     short loc_1400580A2
0x140058066  mov     rax, cs:WPP_GLOBAL_Control
0x14005806d  cmp     rax, rbx
0x140058070  jz      short loc_1400580A2
0x140058072  test    byte ptr [rax+1Ch], 1
0x140058076  jz      short loc_1400580A2
0x140058078  cmp     byte ptr [rax+19h], 2
0x14005807c  jb      short loc_1400580A2
0x14005807e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140058083  mov     rcx, cs:WPP_GLOBAL_Control
0x14005808a  lea     r8, WPP_aab7522c7bda330a3e3a0c95659aa217_Traceguids
0x140058091  mov     edx, 1Dh
0x140058096  mov     r9d, eax
0x140058099  mov     rcx, [rcx+10h]
0x14005809d  call    WPP_SF_d
0x1400580a2  mov     rax, r14
0x1400580a5  mov     rcx, [rbp+3B0h+var_30]
0x1400580ac  xor     rcx, rsp; StackCookie
0x1400580af  call    __security_check_cookie
0x1400580b4  mov     rbx, [rsp+4B0h+arg_10]
0x1400580bc  add     rsp, 490h
0x1400580c3  pop     r15
0x1400580c5  pop     r14
0x1400580c7  pop     rdi
0x1400580c8  pop     rsi
0x1400580c9  pop     rbp
0x1400580ca  retn
```
