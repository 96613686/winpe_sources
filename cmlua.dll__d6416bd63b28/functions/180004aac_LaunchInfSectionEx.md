# _LaunchInfSectionEx

- ea: `0x180004aac`
- end: `0x180004c59`
- name: `_LaunchInfSectionEx`
- size: `429`
- prototype: `__int64 __fastcall(const CHAR *, const CHAR *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003580`

## callees

- `0x180004aac`
- `0x180004d54`
- `0x180004e1c`
- `0x18000510c`
- `0x180006010`

## import_xrefs

- `cmutil!CmFree` at `0x180004c2f`
- `cmutil!CmFree` at `0x180004c2f`
- `cmutil!CmMalloc` at `0x180004afe`
- `cmutil!CmMalloc` at `0x180004afe`
- `KERNEL32!FreeLibrary` at `0x180004c3d`
- `KERNEL32!FreeLibrary` at `0x180004c3d`
- `KERNEL32!LoadLibraryExW` at `0x180004b65`
- `KERNEL32!LoadLibraryExW` at `0x180004b65`
- `KERNEL32!GetProcAddress` at `0x180004bb0`
- `KERNEL32!GetProcAddress` at `0x180004bb0`
- `KERNEL32!lstrlenA` at `0x180004ae6`
- `KERNEL32!lstrlenA` at `0x180004af1`
- `KERNEL32!lstrlenA` at `0x180004ae6`
- `KERNEL32!lstrlenA` at `0x180004af1`
- `KERNEL32!GetLastError` at `0x180004b73`
- `KERNEL32!GetLastError` at `0x180004bbb`
- `KERNEL32!GetLastError` at `0x180004b73`
- `KERNEL32!GetLastError` at `0x180004bbb`

## string_xrefs

- `0x180004b58`: `advpack.dll`
- `0x180004b88`: `advpack.dll`
- `0x180004bd0`: `RunSetupCommand`
- `0x180004b8f`: `LoadLibrary of %s failed with error, hResult = 0x%x.`

## pseudocode

```c
__int64 __fastcall LaunchInfSectionEx(const CHAR *a1, const CHAR *a2, int a3)
{
  int v6; // ebx
  unsigned __int64 v7; // rbx
  char *v8; // r14
  HMODULE v10; // rbp
  unsigned int v11; // ebx
  HMODULE Library; // rax
  signed int v13; // eax
  const WCHAR *v14; // r8
  const wchar_t *v15; // rdx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v18; // eax

  if ( !a1 || !a2 || !*a1 || !*a2 )
    return 2147942487LL;
  v6 = lstrlenA(a1);
  v7 = (unsigned int)(v6 + lstrlenA(a2) + 13);
  v8 = (char *)CmMalloc(v7);
  if ( !v8 )
    return 2147942414LL;
  v10 = 0;
  v11 = CmStringCchPrintfExA(v8, v7, 0, 0, 0x900u, "%s,%s,,%d", a1, a2, a3);
  if ( (v11 & 0x80000000) == 0 )
  {
    Library = LoadLibraryExW(L"advpack.dll", 0, 0x800u);
    v10 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "LaunchINFSectionEx");
      if ( ProcAddress )
      {
        v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, char *, _QWORD))ProcAddress)(0, 0, v8, 0);
        v11 = v18;
        if ( v18 >= 0 )
        {
          if ( v18 == 3010 )
            MyDbgPrintfA(
              0xFFFFFFFFLL,
              "CallLaunchInfSectionEx -- LaunchINFSectionEx on file %s and section %s returned reboot required.",
              a1,
              a2);
        }
        else
        {
          MyDbgPrintfA(
            0xFFFFFFFFLL,
            "CallLaunchInfSectionEx -- LaunchINFSectionEx on file %s and section %s FAILED!  hr=0x%x",
            a1,
            a2,
            v18);
        }
        goto LABEL_21;
      }
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v14 = (const WCHAR *)"RunSetupCommand";
      v15 = L"GetProcAddress of %S failed with error, hResult = 0x%x.";
    }
    else
    {
      v13 = GetLastError();
      v11 = v13;
      if ( v13 > 0 )
        v11 = (unsigned __int16)v13 | 0x80070000;
      v14 = L"advpack.dll";
      v15 = L"LoadLibrary of %s failed with error, hResult = 0x%x.";
    }
    MyDbgPrintfW(0xFFFFFFFFLL, v15, v14, v11);
  }
LABEL_21:
  CmFree(v8);
  if ( v10 )
    FreeLibrary(v10);
  return v11;
}

```

## disassembly

```asm
0x180004aac  push    rbx
0x180004aae  push    rbp
0x180004aaf  push    rsi
0x180004ab0  push    rdi
0x180004ab1  push    r14
0x180004ab3  push    r15
0x180004ab5  sub     rsp, 58h
0x180004ab9  mov     r15d, r8d
0x180004abc  mov     rdi, rdx
0x180004abf  mov     rsi, rcx
0x180004ac2  test    rcx, rcx
0x180004ac5  jz      loc_180004C47
0x180004acb  test    rdx, rdx
0x180004ace  jz      loc_180004C47
0x180004ad4  cmp     byte ptr [rcx], 0
0x180004ad7  jz      loc_180004C47
0x180004add  cmp     byte ptr [rdx], 0
0x180004ae0  jz      loc_180004C47
0x180004ae6  call    cs:__imp_lstrlenA
0x180004aec  mov     rcx, rdi; lpString
0x180004aef  mov     ebx, eax
0x180004af1  call    cs:__imp_lstrlenA
0x180004af7  lea     ecx, [rax+0Dh]
0x180004afa  add     ecx, ebx
0x180004afc  mov     ebx, ecx
0x180004afe  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180004b04  mov     r14, rax
0x180004b07  test    rax, rax
0x180004b0a  jnz     short loc_180004B16
0x180004b0c  mov     eax, 8007000Eh
0x180004b11  jmp     loc_180004C4C
0x180004b16  mov     [rsp+88h+var_48], r15d
0x180004b1b  lea     rax, aSSD; "%s,%s,,%d"
0x180004b22  mov     [rsp+88h+var_50], rdi
0x180004b27  xor     r9d, r9d; unsigned __int64 *
0x180004b2a  mov     [rsp+88h+var_58], rsi
0x180004b2f  xor     r8d, r8d; char **
0x180004b32  mov     [rsp+88h+var_60], rax; char *
0x180004b37  mov     rdx, rbx; cbDest
0x180004b3a  mov     rcx, r14; Buffer
0x180004b3d  mov     [rsp+88h+var_68], 900h; unsigned int
0x180004b45  xor     ebp, ebp
0x180004b47  call    ?CmStringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; CmStringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180004b4c  mov     ebx, eax
0x180004b4e  test    eax, eax
0x180004b50  js      loc_180004C2C
0x180004b56  xor     edx, edx; hFile
0x180004b58  lea     rcx, aAdvpackDll; "advpack.dll"
0x180004b5f  mov     r8d, 800h; dwFlags
0x180004b65  call    cs:__imp_LoadLibraryExW
0x180004b6b  mov     rbp, rax
0x180004b6e  test    rax, rax
0x180004b71  jnz     short loc_180004BA6
0x180004b73  call    cs:__imp_GetLastError
0x180004b79  mov     ebx, eax
0x180004b7b  test    eax, eax
0x180004b7d  jle     short loc_180004B88
0x180004b7f  movzx   ebx, ax
0x180004b82  or      ebx, 80070000h
0x180004b88  lea     r8, aAdvpackDll; "advpack.dll"
0x180004b8f  lea     rdx, aLoadlibraryOfS; "LoadLibrary of %s failed with error, hR"...
0x180004b96  mov     r9d, ebx
0x180004b99  or      ecx, 0FFFFFFFFh
0x180004b9c  call    MyDbgPrintfW
0x180004ba1  jmp     loc_180004C2C
0x180004ba6  lea     rdx, aLaunchinfsecti; "LaunchINFSectionEx"
0x180004bad  mov     rcx, rax; hModule
0x180004bb0  call    cs:__imp_GetProcAddress
0x180004bb6  test    rax, rax
0x180004bb9  jnz     short loc_180004BE0
0x180004bbb  call    cs:__imp_GetLastError
0x180004bc1  mov     ebx, eax
0x180004bc3  test    eax, eax
0x180004bc5  jle     short loc_180004BD0
0x180004bc7  movzx   ebx, ax
0x180004bca  or      ebx, 80070000h
0x180004bd0  lea     r8, aRunsetupcomman; "RunSetupCommand"
0x180004bd7  lea     rdx, aGetprocaddress; "GetProcAddress of %S failed with error,"...
0x180004bde  jmp     short loc_180004B96
0x180004be0  xor     r9d, r9d
0x180004be3  mov     r8, r14
0x180004be6  xor     edx, edx
0x180004be8  xor     ecx, ecx
0x180004bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bef  mov     ebx, eax
0x180004bf1  test    eax, eax
0x180004bf3  jns     short loc_180004C10
0x180004bf5  mov     r9, rdi
0x180004bf8  mov     [rsp+88h+var_68], eax
0x180004bfc  mov     r8, rsi
0x180004bff  lea     rdx, aCalllaunchinfs_0; "CallLaunchInfSectionEx -- LaunchINFSect"...
0x180004c06  or      ecx, 0FFFFFFFFh
0x180004c09  call    MyDbgPrintfA
0x180004c0e  jmp     short loc_180004C2C
0x180004c10  cmp     eax, 0BC2h
0x180004c15  jnz     short loc_180004C2C
0x180004c17  mov     r9, rdi
0x180004c1a  lea     rdx, aCalllaunchinfs; "CallLaunchInfSectionEx -- LaunchINFSect"...
0x180004c21  mov     r8, rsi
0x180004c24  or      ecx, 0FFFFFFFFh
0x180004c27  call    MyDbgPrintfA
0x180004c2c  mov     rcx, r14
0x180004c2f  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180004c35  test    rbp, rbp
0x180004c38  jz      short loc_180004C43
0x180004c3a  mov     rcx, rbp; hLibModule
0x180004c3d  call    cs:__imp_FreeLibrary
0x180004c43  mov     eax, ebx
0x180004c45  jmp     short loc_180004C4C
0x180004c47  mov     eax, 80070057h
0x180004c4c  add     rsp, 58h
0x180004c50  pop     r15
0x180004c52  pop     r14
0x180004c54  pop     rdi
0x180004c55  pop     rsi
0x180004c56  pop     rbp
0x180004c57  pop     rbx
0x180004c58  retn
```
