# _DoTermsrvAppStuff(ushort const *,RRA_FLAGS *)

- ea: `0x1401b3874`
- end: `0x1401b395e`
- name: `?_DoTermsrvAppStuff@@YAHPEBGPEAW4RRA_FLAGS@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(PCWSTR pszCmdTemplate, enum RRA_FLAGS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000baf4`

## callees

- `0x1401b37f0`
- `0x1401b3874`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1401b390c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1401b390c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1401b38f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1401b38f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401b3946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1401b3946`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x1401b38c4`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x1401b38c4`
- `api-ms-win-core-kernel32-legacy-l1-1-2!SetTermsrvAppInstallMode` at `0x1401b389b`
- `api-ms-win-core-kernel32-legacy-l1-1-2!SetTermsrvAppInstallMode` at `0x1401b389b`

## string_xrefs

- `0x1401b3902`: `GetTermsrCompatFlagsEx`
- `0x1401b38ea`: `TSAppCMP.DLL`

## pseudocode

```c
__int64 __fastcall _DoTermsrvAppStuff(PCWSTR pszCmdTemplate, enum RRA_FLAGS *a2)
{
  unsigned int v4; // edi
  HMODULE Library; // rax
  PWSTR v6; // rsi
  int v8; // [rsp+40h] [rbp+18h] BYREF
  PWSTR ppszApplication; // [rsp+48h] [rbp+20h] BYREF

  v4 = 0;
  if ( (unsigned int)IsOS_OS_TERMINALSERVER() )
  {
    if ( (unsigned int)SetTermsrvAppInstallMode(1) )
    {
      *(_DWORD *)a2 |= 2u;
      ppszApplication = 0;
      v4 = 1;
      if ( SHEvaluateSystemCommandTemplate(pszCmdTemplate, &ppszApplication, 0, 0) >= 0 )
      {
        Library = (HMODULE)qword_1402529D0;
        v6 = ppszApplication;
        v8 = 0;
        if ( qword_1402529D0 == -1 )
        {
          Library = LoadLibraryExW(L"TSAppCMP.DLL", 0, 0x800u);
          if ( Library )
            Library = (HMODULE)GetProcAddress(Library, "GetTermsrCompatFlagsEx");
          qword_1402529D0 = (__int64)Library;
        }
        if ( Library )
        {
          ((void (__fastcall *)(PWSTR, int *, __int64))Library)(v6, &v8, 1);
          LOWORD(Library) = v8;
        }
        else
        {
          v8 = 0;
        }
        if ( ((unsigned __int16)Library & 0x8000) != 0 )
          *(_DWORD *)a2 |= 0x20u;
        CoTaskMemFree(ppszApplication);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1401b3874  mov     [rsp+arg_0], rbx
0x1401b3879  mov     [rsp+arg_8], rsi
0x1401b387e  push    rdi
0x1401b387f  sub     rsp, 20h
0x1401b3883  mov     rbx, rdx
0x1401b3886  mov     rsi, rcx
0x1401b3889  xor     edi, edi
0x1401b388b  call    ?IsOS_OS_TERMINALSERVER@@YAHXZ; IsOS_OS_TERMINALSERVER(void)
0x1401b3890  test    eax, eax
0x1401b3892  jz      loc_1401B394C
0x1401b3898  lea     ecx, [rdi+1]
0x1401b389b  call    cs:__imp_SetTermsrvAppInstallMode
0x1401b38a1  test    eax, eax
0x1401b38a3  jz      loc_1401B394C
0x1401b38a9  or      dword ptr [rbx], 2
0x1401b38ac  lea     rdx, [rsp+28h+ppszApplication]; ppszApplication
0x1401b38b1  mov     [rsp+28h+ppszApplication], rdi
0x1401b38b6  xor     r9d, r9d; ppszParameters
0x1401b38b9  xor     r8d, r8d; ppszCommandLine
0x1401b38bc  mov     rcx, rsi; pszCmdTemplate
0x1401b38bf  mov     edi, 1
0x1401b38c4  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x1401b38ca  test    eax, eax
0x1401b38cc  js      short loc_1401B394C
0x1401b38ce  mov     rax, cs:qword_1402529D0
0x1401b38d5  mov     rsi, [rsp+28h+ppszApplication]
0x1401b38da  mov     [rsp+28h+arg_10], 0
0x1401b38e2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401b38e6  jnz     short loc_1401B3919
0x1401b38e8  xor     edx, edx; hFile
0x1401b38ea  lea     rcx, aTsappcmpDll; "TSAppCMP.DLL"
0x1401b38f1  mov     r8d, 800h; dwFlags
0x1401b38f7  call    cs:__imp_LoadLibraryExW
0x1401b38fd  test    rax, rax
0x1401b3900  jz      short loc_1401B3912
0x1401b3902  lea     rdx, aGettermsrcompa; "GetTermsrCompatFlagsEx"
0x1401b3909  mov     rcx, rax; hModule
0x1401b390c  call    cs:__imp_GetProcAddress
0x1401b3912  mov     cs:qword_1402529D0, rax
0x1401b3919  test    rax, rax
0x1401b391c  jz      short loc_1401B3934
0x1401b391e  mov     r8d, edi
0x1401b3921  lea     rdx, [rsp+28h+arg_10]
0x1401b3926  mov     rcx, rsi
0x1401b3929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401b392e  mov     eax, [rsp+28h+arg_10]
0x1401b3932  jmp     short loc_1401B3938
0x1401b3934  mov     [rsp+28h+arg_10], eax
0x1401b3938  bt      eax, 0Fh
0x1401b393c  jnb     short loc_1401B3941
0x1401b393e  or      dword ptr [rbx], 20h
0x1401b3941  mov     rcx, [rsp+28h+ppszApplication]; pv
0x1401b3946  call    cs:__imp_CoTaskMemFree
0x1401b394c  mov     rbx, [rsp+28h+arg_0]
0x1401b3951  mov     eax, edi
0x1401b3953  mov     rsi, [rsp+28h+arg_8]
0x1401b3958  add     rsp, 20h
0x1401b395c  pop     rdi
0x1401b395d  retn
```
