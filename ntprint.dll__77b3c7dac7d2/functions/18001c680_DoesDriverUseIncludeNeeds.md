# DoesDriverUseIncludeNeeds

- ea: `0x18001c680`
- end: `0x18001c870`
- name: `DoesDriverUseIncludeNeeds`
- size: `496`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpString1@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18000b7ec`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x180012b28`
- `0x18001c680`
- `0x18001e164`
- `0x18001eed8`
- `0x180020b60`
- `0x180036248`

## import_xrefs

- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x18001c7dd`
- `SETUPAPI!SetupDiGetActualSectionToInstallExW` at `0x18001c7dd`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001c81c`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001c81c`
- `SETUPAPI!SetupCloseInfFile` at `0x18001c83e`
- `SETUPAPI!SetupCloseInfFile` at `0x18001c83e`

## pseudocode

```c
__int64 __fastcall DoesDriverUseIncludeNeeds(
        WCHAR *lpString1,
        int a2,
        unsigned __int16 *a3,
        const WCHAR *a4,
        _QWORD *a5)
{
  __int64 v6; // r13
  DWORD dwMajorVersion; // r14d
  DWORD dwMinorVersion; // r15d
  NCoreLibrary *v11; // rcx
  int LastErrorAsFailHR; // ebx
  NCoreLibrary *v13; // rcx
  void *v14; // rdi
  DWORD v15; // eax
  NCoreLibrary *v16; // rcx
  struct _INFCONTEXT Context; // [rsp+40h] [rbp-C0h] BYREF
  struct _SP_ALTPLATFORM_INFO_V2 AlternatePlatformInfo; // [rsp+58h] [rbp-A8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  WCHAR InfSectionWithExt[256]; // [rsp+1A0h] [rbp+A0h] BYREF

  v6 = a2;
  memset(&AlternatePlatformInfo, 0, sizeof(AlternatePlatformInfo));
  memset_0(InfSectionWithExt, 0, 0x1FEu);
  if ( !(unsigned int)ValidPlatform((unsigned int)v6) || !a3 || !a4 || !a5 )
    return (unsigned int)-2147024809;
  dwMajorVersion = 0;
  *a5 = 0;
  dwMinorVersion = 0;
  if ( !(unsigned int)IsLocalMachine(lpString1) )
  {
    memset_0(&VersionInformation, 0, sizeof(VersionInformation));
    if ( !(unsigned int)GetOSVersion(lpString1, &VersionInformation) )
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v11);
      if ( LastErrorAsFailHR < 0 )
        return (unsigned int)LastErrorAsFailHR;
    }
    dwMajorVersion = VersionInformation.dwMajorVersion;
    dwMinorVersion = VersionInformation.dwMinorVersion;
  }
  v14 = (void *)OpenPrinterInfFile(a3, 0);
  if ( v14 == (void *)-1LL )
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13);
    if ( LastErrorAsFailHR < 0 )
      return (unsigned int)LastErrorAsFailHR;
  }
  AlternatePlatformInfo.MajorVersion = dwMajorVersion;
  v15 = *(&PlatformArch + 2 * v6);
  AlternatePlatformInfo.FirstValidatedMajorVersion = dwMajorVersion;
  AlternatePlatformInfo.Platform = v15;
  AlternatePlatformInfo.ProcessorArchitecture = *((_WORD *)&PlatformArch + 4 * v6 + 2);
  AlternatePlatformInfo.cbSize = 28;
  AlternatePlatformInfo.MinorVersion = dwMinorVersion;
  AlternatePlatformInfo.FirstValidatedMinorVersion = dwMinorVersion;
  if ( SetupDiGetActualSectionToInstallExW(v14, a4, &AlternatePlatformInfo, InfSectionWithExt, 0xFFu, 0, 0, 0) )
  {
    LastErrorAsFailHR = 0;
    goto LABEL_14;
  }
  LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v16);
  if ( LastErrorAsFailHR >= 0 )
  {
LABEL_14:
    memset(&Context, 0, sizeof(Context));
    if ( SetupFindFirstLineW(v14, InfSectionWithExt, L"Needs", &Context) )
      LastErrorAsFailHR = InfGetMultiSz(&Context);
  }
  if ( v14 != (void *)-1LL )
    SetupCloseInfFile(v14);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18001c680  push    rbp
0x18001c682  push    rbx
0x18001c683  push    rsi
0x18001c684  push    rdi
0x18001c685  push    r12
0x18001c687  push    r13
0x18001c689  push    r14
0x18001c68b  push    r15
0x18001c68d  lea     rbp, [rsp-2B8h]
0x18001c695  sub     rsp, 3B8h
0x18001c69c  mov     rax, cs:__security_cookie
0x18001c6a3  xor     rax, rsp
0x18001c6a6  mov     [rbp+2F0h+var_50], rax
0x18001c6ad  mov     rsi, [rbp+2F0h+arg_20]
0x18001c6b4  xorps   xmm0, xmm0
0x18001c6b7  mov     rdi, r8
0x18001c6ba  movsxd  r13, edx
0x18001c6bd  mov     rbx, rcx
0x18001c6c0  xor     edx, edx; Val
0x18001c6c2  movups  xmmword ptr [rsp+3F0h+AlternatePlatformInfo.cbSize], xmm0
0x18001c6c7  mov     r8d, 1FEh; Size
0x18001c6cd  lea     rcx, [rbp+2F0h+InfSectionWithExt]; void *
0x18001c6d4  movups  xmmword ptr [rsp+3F0h+AlternatePlatformInfo.MinorVersion], xmm0
0x18001c6d9  mov     r12, r9
0x18001c6dc  call    memset_0
0x18001c6e1  mov     ecx, r13d
0x18001c6e4  call    ValidPlatform
0x18001c6e9  test    eax, eax
0x18001c6eb  jz      loc_18001C846
0x18001c6f1  test    rdi, rdi
0x18001c6f4  jz      loc_18001C846
0x18001c6fa  test    r12, r12
0x18001c6fd  jz      loc_18001C846
0x18001c703  test    rsi, rsi
0x18001c706  jz      loc_18001C846
0x18001c70c  xor     r14d, r14d
0x18001c70f  mov     rcx, rbx; lpString1
0x18001c712  mov     [rsi], r14
0x18001c715  xor     r15d, r15d
0x18001c718  call    IsLocalMachine
0x18001c71d  test    eax, eax
0x18001c71f  jnz     short loc_18001C759
0x18001c721  xor     edx, edx; Val
0x18001c723  lea     rcx, [rbp+2F0h+VersionInformation]; void *
0x18001c727  mov     r8d, 114h; Size
0x18001c72d  call    memset_0
0x18001c732  lea     rdx, [rbp+2F0h+VersionInformation]; lpVersionInformation
0x18001c736  mov     rcx, rbx; pPrinterName
0x18001c739  call    GetOSVersion
0x18001c73e  test    eax, eax
0x18001c740  jnz     short loc_18001C751
0x18001c742  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001c747  mov     ebx, eax
0x18001c749  test    eax, eax
0x18001c74b  js      loc_18001C84B
0x18001c751  mov     r14d, [rbp+2F0h+VersionInformation.dwMajorVersion]
0x18001c755  mov     r15d, [rbp+2F0h+VersionInformation.dwMinorVersion]
0x18001c759  xor     edx, edx
0x18001c75b  mov     rcx, rdi; unsigned __int16 *
0x18001c75e  call    OpenPrinterInfFile
0x18001c763  mov     rdi, rax
0x18001c766  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c76a  jnz     short loc_18001C77B
0x18001c76c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001c771  mov     ebx, eax
0x18001c773  test    eax, eax
0x18001c775  js      loc_18001C84B
0x18001c77b  lea     rdx, PlatformArch
0x18001c782  mov     [rsp+3F0h+AlternatePlatformInfo.MajorVersion], r14d
0x18001c787  mov     eax, [rdx+r13*8]
0x18001c78b  lea     r9, [rbp+2F0h+InfSectionWithExt]; InfSectionWithExt
0x18001c792  mov     [rsp+3F0h+AlternatePlatformInfo.FirstValidatedMajorVersion], r14d
0x18001c797  lea     r8, [rsp+3F0h+AlternatePlatformInfo]; AlternatePlatformInfo
0x18001c79c  xor     r14d, r14d
0x18001c79f  mov     [rsp+3F0h+AlternatePlatformInfo.Platform], eax
0x18001c7a3  movzx   eax, word ptr [rdx+r13*8+4]
0x18001c7a9  mov     rcx, rdi; InfHandle
0x18001c7ac  mov     [rsp+3F0h+Reserved], r14; Reserved
0x18001c7b1  mov     rdx, r12; InfSectionName
0x18001c7b4  mov     [rsp+3F0h+Extension], r14; Extension
0x18001c7b9  mov     [rsp+3F0h+RequiredSize], r14; RequiredSize
0x18001c7be  mov     [rsp+3F0h+AlternatePlatformInfo.ProcessorArchitecture], ax
0x18001c7c3  mov     [rsp+3F0h+InfSectionWithExtSize], 0FFh; InfSectionWithExtSize
0x18001c7cb  mov     [rsp+3F0h+AlternatePlatformInfo.cbSize], 1Ch
0x18001c7d3  mov     [rsp+3F0h+AlternatePlatformInfo.MinorVersion], r15d
0x18001c7d8  mov     [rsp+3F0h+AlternatePlatformInfo.FirstValidatedMinorVersion], r15d
0x18001c7dd  call    cs:__imp_SetupDiGetActualSectionToInstallExW
0x18001c7e3  test    eax, eax
0x18001c7e5  jz      short loc_18001C7EC
0x18001c7e7  mov     ebx, r14d
0x18001c7ea  jmp     short loc_18001C7F7
0x18001c7ec  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001c7f1  mov     ebx, eax
0x18001c7f3  test    eax, eax
0x18001c7f5  js      short loc_18001C835
0x18001c7f7  xorps   xmm0, xmm0
0x18001c7fa  lea     r9, [rsp+3F0h+Context]; Context
0x18001c7ff  xor     eax, eax
0x18001c801  lea     r8, aNeeds; "Needs"
0x18001c808  lea     rdx, [rbp+2F0h+InfSectionWithExt]; Section
0x18001c80f  mov     qword ptr [rsp+3F0h+Context.Section], rax
0x18001c814  mov     rcx, rdi; InfHandle
0x18001c817  movups  xmmword ptr [rsp+3F0h+Context.Inf], xmm0
0x18001c81c  call    cs:__imp_SetupFindFirstLineW
0x18001c822  test    eax, eax
0x18001c824  jz      short loc_18001C835
0x18001c826  mov     r8, rsi
0x18001c829  lea     rcx, [rsp+3F0h+Context]; Context
0x18001c82e  call    InfGetMultiSz
0x18001c833  mov     ebx, eax
0x18001c835  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001c839  jz      short loc_18001C84B
0x18001c83b  mov     rcx, rdi; InfHandle
0x18001c83e  call    cs:__imp_SetupCloseInfFile
0x18001c844  jmp     short loc_18001C84B
0x18001c846  mov     ebx, 80070057h
0x18001c84b  mov     eax, ebx
0x18001c84d  mov     rcx, [rbp+2F0h+var_50]
0x18001c854  xor     rcx, rsp; StackCookie
0x18001c857  call    __security_check_cookie
0x18001c85c  add     rsp, 3B8h
0x18001c863  pop     r15
0x18001c865  pop     r14
0x18001c867  pop     r13
0x18001c869  pop     r12
0x18001c86b  pop     rdi
0x18001c86c  pop     rsi
0x18001c86d  pop     rbx
0x18001c86e  pop     rbp
0x18001c86f  retn
```
