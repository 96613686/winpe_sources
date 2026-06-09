# GenerateMIF(uint)

- ea: `0x140005084`
- end: `0x140005299`
- name: `?GenerateMIF@@YAXI@Z`
- size: `533`
- prototype: `void __fastcall(DWORD dwMessageId)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140004444`
- `0x140004ca8`

## callees

- `0x1400033a8`
- `0x140003883`
- `0x140005084`
- `0x140008840`
- `0x140009820`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetSystemDefaultLangID` at `0x14000513b`
- `KERNEL32!GetSystemDefaultLangID` at `0x14000513b`
- `KERNEL32!FormatMessageW` at `0x1400051a6`
- `KERNEL32!FormatMessageW` at `0x1400051a6`
- `KERNEL32!GetProcAddress` at `0x1400050e7`
- `KERNEL32!GetProcAddress` at `0x1400050e7`
- `KERNEL32!FreeLibrary` at `0x140005273`
- `KERNEL32!FreeLibrary` at `0x140005273`
- `KERNEL32!WideCharToMultiByte` at `0x1400051ec`
- `KERNEL32!WideCharToMultiByte` at `0x1400051ec`
- `KERNEL32!LoadLibraryExW` at `0x1400050cb`
- `KERNEL32!LoadLibraryExW` at `0x1400050cb`
- `msi!__imp_MsiSetExternalUIA` at `0x1400050af`
- `msi!__imp_MsiSetExternalUIA` at `0x1400050af`
- `msi!__imp_MsiLoadStringA` at `0x140005162`
- `msi!__imp_MsiLoadStringA` at `0x140005162`

## string_xrefs

- `0x1400050c4`: `ISMIF32.DLL`
- `0x1400050dd`: `InstallStatusMIF`
- `0x140005208`: `Installer error %i`

## pseudocode

```c
void __fastcall GenerateMIF(DWORD dwMessageId)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rbp
  int v5; // esi
  LANGID SystemDefaultLangID; // ax
  DWORD v7; // r14d
  DWORD v8; // eax
  WCHAR Buffer[264]; // [rsp+50h] [rbp-258h] BYREF

  MsiSetExternalUIA(0, 0, 0);
  byte_140010F60 = 0;
  Library = LoadLibraryExW(L"ISMIF32.DLL", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "InstallStatusMIF");
    if ( !ProcAddress )
    {
LABEL_19:
      FreeLibrary(v3);
      return;
    }
    if ( !dwMessageId || dwMessageId == 1604 || dwMessageId == 3010 || dwMessageId == 1641 )
    {
      v5 = 1;
      byte_140010CC0[0] = 0;
      goto LABEL_18;
    }
    v5 = 0;
    if ( byte_140010CC0[0] )
      goto LABEL_18;
    SystemDefaultLangID = GetSystemDefaultLangID();
    v7 = SystemDefaultLangID;
    if ( dwMessageId >= 0x641 )
    {
      if ( (unsigned int)MsiLoadStringA(-1, dwMessageId, byte_140010CC0, 256, SystemDefaultLangID) )
        goto LABEL_18;
    }
    memset_0(Buffer, 0, 0x20Au);
    v8 = FormatMessageW(0x1000u, 0, dwMessageId, v7, Buffer, 0x105u, 0);
    if ( v8 )
    {
      if ( 2 * (unsigned __int64)(v8 - 2) >= 0x20A )
        _report_rangecheckfailure();
      Buffer[v8 - 2] = 0;
      if ( WideCharToMultiByte(0, 0, Buffer, -1, byte_140010CC0, 256, 0, 0) )
        goto LABEL_18;
    }
    else if ( (int)StringCchPrintfA(byte_140010CC0, 0x100u, "Installer error %i", dwMessageId) >= 0 )
    {
      goto LABEL_18;
    }
    byte_140010CC0[0] = 0;
LABEL_18:
    ((void (__fastcall *)(void *, CHAR *, CHAR *, CHAR *, CHAR *, _QWORD, CHAR *, int))ProcAddress)(
      &unk_140011180,
      &szValueBuf,
      &MultiByteStr,
      &byte_140010DE0,
      &byte_140010F10,
      0,
      byte_140010CC0,
      v5);
    goto LABEL_19;
  }
}

```

## disassembly

```asm
0x140005084  push    rbx
0x140005086  push    rbp
0x140005087  push    rsi
0x140005088  push    rdi
0x140005089  push    r12
0x14000508b  push    r14
0x14000508d  sub     rsp, 278h
0x140005094  mov     rax, cs:__security_cookie
0x14000509b  xor     rax, rsp
0x14000509e  mov     [rsp+2A8h+var_48], rax
0x1400050a6  mov     ebx, ecx
0x1400050a8  xor     r8d, r8d; pvContext
0x1400050ab  xor     ecx, ecx; puiHandler
0x1400050ad  xor     edx, edx; dwMessageFilter
0x1400050af  call    cs:__imp_MsiSetExternalUIA
0x1400050b5  xor     edx, edx; hFile
0x1400050b7  mov     cs:byte_140010F60, 0
0x1400050be  mov     r8d, 800h; dwFlags
0x1400050c4  lea     rcx, LibFileName; "ISMIF32.DLL"
0x1400050cb  call    cs:__imp_LoadLibraryExW
0x1400050d1  mov     rdi, rax
0x1400050d4  test    rax, rax
0x1400050d7  jz      loc_140005279
0x1400050dd  lea     rdx, aInstallstatusm; "InstallStatusMIF"
0x1400050e4  mov     rcx, rax; hModule
0x1400050e7  call    cs:__imp_GetProcAddress
0x1400050ed  mov     rbp, rax
0x1400050f0  test    rax, rax
0x1400050f3  jz      loc_140005270
0x1400050f9  lea     r12, byte_140010CC0
0x140005100  test    ebx, ebx
0x140005102  jz      loc_140005222
0x140005108  cmp     ebx, 644h
0x14000510e  jz      loc_140005222
0x140005114  cmp     ebx, 0BC2h
0x14000511a  jz      loc_140005222
0x140005120  cmp     ebx, 669h
0x140005126  jz      loc_140005222
0x14000512c  xor     esi, esi
0x14000512e  cmp     cs:byte_140010CC0, sil
0x140005135  jnz     loc_14000522E
0x14000513b  call    cs:__imp_GetSystemDefaultLangID
0x140005141  movzx   r14d, ax
0x140005145  cmp     ebx, 641h
0x14000514b  jb      short loc_140005170
0x14000514d  mov     r9d, 100h
0x140005153  mov     word ptr [rsp+2A8h+lpBuffer], r14w
0x140005159  mov     r8, r12
0x14000515c  mov     edx, ebx
0x14000515e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140005162  call    cs:__imp_MsiLoadStringA
0x140005168  test    eax, eax
0x14000516a  jnz     loc_14000522E
0x140005170  xor     edx, edx; Val
0x140005172  lea     rcx, [rsp+2A8h+Buffer]; void *
0x140005177  mov     r8d, 20Ah; Size
0x14000517d  call    memset_0
0x140005182  lea     rax, [rsp+2A8h+Buffer]
0x140005187  mov     [rsp+2A8h+Arguments], rsi; Arguments
0x14000518c  mov     r9d, r14d; dwLanguageId
0x14000518f  mov     [rsp+2A8h+nSize], 105h; nSize
0x140005197  mov     r8d, ebx; dwMessageId
0x14000519a  mov     [rsp+2A8h+lpBuffer], rax; lpBuffer
0x14000519f  xor     edx, edx; lpSource
0x1400051a1  mov     ecx, 1000h; dwFlags
0x1400051a6  call    cs:__imp_FormatMessageW
0x1400051ac  test    eax, eax
0x1400051ae  jz      short loc_140005205
0x1400051b0  add     eax, 0FFFFFFFEh
0x1400051b3  mov     ecx, eax
0x1400051b5  add     rcx, rcx
0x1400051b8  cmp     rcx, 20Ah
0x1400051bf  jnb     short loc_1400051FF
0x1400051c1  xor     eax, eax
0x1400051c3  lea     r8, [rsp+2A8h+Buffer]; lpWideCharStr
0x1400051c8  mov     [rsp+2A8h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1400051cd  or      r9d, 0FFFFFFFFh; cchWideChar
0x1400051d1  mov     [rsp+2A8h+Arguments], rax; lpDefaultChar
0x1400051d6  xor     edx, edx; dwFlags
0x1400051d8  mov     [rsp+rcx+2A8h+Buffer], ax
0x1400051dd  xor     ecx, ecx; CodePage
0x1400051df  mov     [rsp+2A8h+nSize], 100h; cbMultiByte
0x1400051e7  mov     [rsp+2A8h+lpBuffer], r12; lpMultiByteStr
0x1400051ec  call    cs:__imp_WideCharToMultiByte
0x1400051f2  test    eax, eax
0x1400051f4  jnz     short loc_14000522E
0x1400051f6  mov     cs:byte_140010CC0, sil
0x1400051fd  jmp     short loc_14000522E
0x1400051ff  call    __report_rangecheckfailure
0x140005205  mov     r9d, ebx
0x140005208  lea     r8, aInstallerError; "Installer error %i"
0x14000520f  mov     edx, 100h; unsigned __int64
0x140005214  mov     rcx, r12; char *
0x140005217  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000521c  test    eax, eax
0x14000521e  jns     short loc_14000522E
0x140005220  jmp     short loc_1400051F6
0x140005222  mov     esi, 1
0x140005227  mov     cs:byte_140010CC0, 0
0x14000522e  mov     dword ptr [rsp+2A8h+lpUsedDefaultChar], esi
0x140005232  lea     rax, byte_140010F10
0x140005239  mov     [rsp+2A8h+Arguments], r12
0x14000523e  lea     r9, byte_140010DE0
0x140005245  mov     qword ptr [rsp+2A8h+nSize], 0
0x14000524e  lea     r8, MultiByteStr
0x140005255  mov     [rsp+2A8h+lpBuffer], rax
0x14000525a  lea     rdx, szValueBuf
0x140005261  mov     rax, rbp
0x140005264  lea     rcx, byte_140011180
0x14000526b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005270  mov     rcx, rdi; hLibModule
0x140005273  call    cs:__imp_FreeLibrary
0x140005279  mov     rcx, [rsp+2A8h+var_48]
0x140005281  xor     rcx, rsp; StackCookie
0x140005284  call    __security_check_cookie
0x140005289  add     rsp, 278h
0x140005290  pop     r14
0x140005292  pop     r12
0x140005294  pop     rdi
0x140005295  pop     rsi
0x140005296  pop     rbp
0x140005297  pop     rbx
0x140005298  retn
```
