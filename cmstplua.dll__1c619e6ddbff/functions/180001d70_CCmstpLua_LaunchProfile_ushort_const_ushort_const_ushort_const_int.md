# CCmstpLua::LaunchProfile(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180001d70`
- end: `0x180001f99`
- name: `?LaunchProfile@CCmstpLua@@UEAAJPEBG00H@Z`
- size: `553`
- prototype: `__int64 __fastcall(CCmstpLua *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001d70`
- `0x180002444`
- `0x1800026b6`
- `0x180003010`

## import_xrefs

- `cmutil!CmFree` at `0x180001eb3`
- `cmutil!CmFree` at `0x180001f74`
- `cmutil!CmFree` at `0x180001eb3`
- `cmutil!CmFree` at `0x180001f74`
- `cmutil!CmMalloc` at `0x180001e3a`
- `cmutil!CmMalloc` at `0x180001ec0`
- `cmutil!CmMalloc` at `0x180001e3a`
- `cmutil!CmMalloc` at `0x180001ec0`
- `KERNEL32!GetLastError` at `0x180001dc0`
- `KERNEL32!GetLastError` at `0x180001e0d`
- `KERNEL32!GetLastError` at `0x180001dc0`
- `KERNEL32!GetLastError` at `0x180001e0d`
- `KERNEL32!GetProcAddress` at `0x180001dff`
- `KERNEL32!GetProcAddress` at `0x180001f31`
- `KERNEL32!GetProcAddress` at `0x180001dff`
- `KERNEL32!GetProcAddress` at `0x180001f31`
- `KERNEL32!FreeLibrary` at `0x180001f52`
- `KERNEL32!FreeLibrary` at `0x180001f7d`
- `KERNEL32!FreeLibrary` at `0x180001f52`
- `KERNEL32!FreeLibrary` at `0x180001f7d`
- `KERNEL32!LoadLibraryExW` at `0x180001db2`
- `KERNEL32!LoadLibraryExW` at `0x180001f19`
- `KERNEL32!LoadLibraryExW` at `0x180001db2`
- `KERNEL32!LoadLibraryExW` at `0x180001f19`

## string_xrefs

- `0x180001f10`: `netshell.dll`
- `0x180001da9`: `RASAPI32.DLL`
- `0x180001dc6`: `LoadLibrary failed in LaunchProfile. GLE = %#x`

## pseudocode

```c
__int64 __fastcall CCmstpLua::LaunchProfile(
        CCmstpLua *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HMODULE Library; // rax
  HMODULE v7; // rbp
  __int64 LastError; // rbx
  FARPROC ProcAddress; // r15
  DWORD v10; // eax
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  unsigned int v13; // eax
  _DWORD *v14; // rax
  HMODULE v15; // rax
  HMODULE v16; // rsi
  FARPROC v17; // rax
  unsigned int v19; // [rsp+88h] [rbp+10h] BYREF

  if ( a2 && a3 && (!a4 || *a4) )
  {
    Library = LoadLibraryExW(L"RASAPI32.DLL", 0, 0);
    v7 = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"LoadLibrary failed in LaunchProfile. GLE = %#x", LastError);
      if ( (int)LastError > 0 )
        LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)LastError;
    }
    LODWORD(LastError) = -2147467259;
    ProcAddress = GetProcAddress(Library, "RasGetEntryPropertiesW");
    if ( ProcAddress )
    {
      v19 = 0;
      v11 = CmMalloc(0x1A44u);
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11 + 1, 0, 0x1A40u);
        *v12 = 6724;
        v19 = 6724;
        v13 = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _DWORD *, unsigned int *, _QWORD, _QWORD))ProcAddress)(
                a4,
                a3,
                v12,
                &v19,
                0,
                0);
        if ( v13 == 603 )
        {
          CmFree(v12);
          v14 = CmMalloc(v19);
          v12 = v14;
          if ( !v14 )
          {
            LODWORD(LastError) = -2147024882;
            goto LABEL_23;
          }
          *v14 = 6724;
          v13 = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _DWORD *, unsigned int *, _QWORD, _QWORD))ProcAddress)(
                  a4,
                  a3,
                  v14,
                  &v19,
                  0,
                  0);
        }
        if ( v13 )
        {
          MyDbgPrintfW(0xFFFFFFFFLL, L"LaunchProfile -- RasGetEntryProperties returned %u", v13);
          LODWORD(LastError) = -2147023667;
        }
        else
        {
          v15 = LoadLibraryExW(L"netshell.dll", 0, 0);
          v16 = v15;
          if ( v15 )
          {
            v17 = GetProcAddress(v15, "HrLaunchConnectionEx");
            if ( v17 )
              LODWORD(LastError) = ((__int64 (__fastcall *)(__int64, _DWORD *))v17)(1, v12 + 877);
            FreeLibrary(v16);
          }
        }
        CmFree(v12);
        goto LABEL_23;
      }
      MyDbgPrintfW(0xFFFFFFFFLL, L"Malloc failed in LaunchProfile.");
    }
    else
    {
      v10 = GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"GetProcAddress failed in LaunchProfile. GLE = %#x", v10);
    }
LABEL_23:
    FreeLibrary(v7);
    return (unsigned int)LastError;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180001d70  push    rbx
0x180001d72  push    rbp
0x180001d73  push    rsi
0x180001d74  push    rdi
0x180001d75  push    r14
0x180001d77  push    r15
0x180001d79  sub     rsp, 48h
0x180001d7d  mov     rsi, r9
0x180001d80  mov     r14, r8
0x180001d83  test    rdx, rdx
0x180001d86  jz      loc_180001F87
0x180001d8c  test    r8, r8
0x180001d8f  jz      loc_180001F87
0x180001d95  test    r9, r9
0x180001d98  jz      short loc_180001DA6
0x180001d9a  xor     eax, eax
0x180001d9c  cmp     ax, [r9]
0x180001da0  jz      loc_180001F87
0x180001da6  xor     r8d, r8d; dwFlags
0x180001da9  lea     rcx, aRasapi32Dll; "RASAPI32.DLL"
0x180001db0  xor     edx, edx; hFile
0x180001db2  call    cs:__imp_LoadLibraryExW
0x180001db8  mov     rbp, rax
0x180001dbb  test    rax, rax
0x180001dbe  jnz     short loc_180001DF0
0x180001dc0  call    cs:__imp_GetLastError
0x180001dc6  lea     rdx, aLoadlibraryFai_0; "LoadLibrary failed in LaunchProfile. GL"...
0x180001dcd  or      ecx, 0FFFFFFFFh
0x180001dd0  mov     r8d, eax
0x180001dd3  mov     ebx, eax
0x180001dd5  call    MyDbgPrintfW
0x180001dda  test    ebx, ebx
0x180001ddc  jle     loc_180001F83
0x180001de2  movzx   ebx, bx
0x180001de5  or      ebx, 80070000h
0x180001deb  jmp     loc_180001F83
0x180001df0  lea     rdx, aRasgetentrypro; "RasGetEntryPropertiesW"
0x180001df7  mov     rcx, rbp; hModule
0x180001dfa  mov     ebx, 80004005h
0x180001dff  call    cs:__imp_GetProcAddress
0x180001e05  mov     r15, rax
0x180001e08  test    rax, rax
0x180001e0b  jnz     short loc_180001E2A
0x180001e0d  call    cs:__imp_GetLastError
0x180001e13  lea     rdx, aGetprocaddress; "GetProcAddress failed in LaunchProfile."...
0x180001e1a  or      ecx, 0FFFFFFFFh
0x180001e1d  mov     r8d, eax
0x180001e20  call    MyDbgPrintfW
0x180001e25  jmp     loc_180001F7A
0x180001e2a  mov     ecx, 1A44h
0x180001e2f  mov     [rsp+78h+arg_8], 0
0x180001e3a  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180001e40  mov     rdi, rax
0x180001e43  test    rax, rax
0x180001e46  jnz     short loc_180001E5C
0x180001e48  lea     rdx, aMallocFailedIn; "Malloc failed in LaunchProfile."
0x180001e4f  or      ecx, 0FFFFFFFFh
0x180001e52  call    MyDbgPrintfW
0x180001e57  jmp     loc_180001F7A
0x180001e5c  lea     rcx, [rax+4]; void *
0x180001e60  xor     edx, edx; Val
0x180001e62  mov     r8d, 1A40h; Size
0x180001e68  call    memset_0
0x180001e6d  mov     dword ptr [rdi], 1A44h
0x180001e73  lea     r9, [rsp+78h+arg_8]
0x180001e7b  mov     r8, rdi
0x180001e7e  mov     [rsp+78h+var_50], 0
0x180001e87  mov     rdx, r14
0x180001e8a  mov     [rsp+78h+arg_8], 1A44h
0x180001e95  mov     rcx, rsi
0x180001e98  mov     [rsp+78h+var_58], 0
0x180001ea1  mov     rax, r15
0x180001ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ea9  cmp     eax, 25Bh
0x180001eae  jnz     short loc_180001F09
0x180001eb0  mov     rcx, rdi
0x180001eb3  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180001eb9  mov     ecx, [rsp+78h+arg_8]
0x180001ec0  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180001ec6  mov     rdi, rax
0x180001ec9  test    rax, rax
0x180001ecc  jnz     short loc_180001ED8
0x180001ece  mov     ebx, 8007000Eh
0x180001ed3  jmp     loc_180001F7A
0x180001ed8  mov     dword ptr [rax], 1A44h
0x180001ede  lea     r9, [rsp+78h+arg_8]
0x180001ee6  mov     r8, rax
0x180001ee9  mov     [rsp+78h+var_50], 0
0x180001ef2  mov     rax, r15
0x180001ef5  mov     [rsp+78h+var_58], 0
0x180001efe  mov     rdx, r14
0x180001f01  mov     rcx, rsi
0x180001f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f09  test    eax, eax
0x180001f0b  jnz     short loc_180001F5A
0x180001f0d  xor     r8d, r8d; dwFlags
0x180001f10  lea     rcx, LibFileName; "netshell.dll"
0x180001f17  xor     edx, edx; hFile
0x180001f19  call    cs:__imp_LoadLibraryExW
0x180001f1f  mov     rsi, rax
0x180001f22  test    rax, rax
0x180001f25  jz      short loc_180001F71
0x180001f27  lea     rdx, aHrlaunchconnec; "HrLaunchConnectionEx"
0x180001f2e  mov     rcx, rax; hModule
0x180001f31  call    cs:__imp_GetProcAddress
0x180001f37  test    rax, rax
0x180001f3a  jz      short loc_180001F4F
0x180001f3c  lea     rdx, [rdi+0DB4h]
0x180001f43  mov     ecx, 1
0x180001f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f4d  mov     ebx, eax
0x180001f4f  mov     rcx, rsi; hLibModule
0x180001f52  call    cs:__imp_FreeLibrary
0x180001f58  jmp     short loc_180001F71
0x180001f5a  mov     r8d, eax
0x180001f5d  lea     rdx, aLaunchprofileR; "LaunchProfile -- RasGetEntryProperties "...
0x180001f64  or      ecx, 0FFFFFFFFh
0x180001f67  call    MyDbgPrintfW
0x180001f6c  mov     ebx, 800704CDh
0x180001f71  mov     rcx, rdi
0x180001f74  call    cs:__imp_?CmFree@@YAXPEAX@Z; CmFree(void *)
0x180001f7a  mov     rcx, rbp; hLibModule
0x180001f7d  call    cs:__imp_FreeLibrary
0x180001f83  mov     eax, ebx
0x180001f85  jmp     short loc_180001F8C
0x180001f87  mov     eax, 80070057h
0x180001f8c  add     rsp, 48h
0x180001f90  pop     r15
0x180001f92  pop     r14
0x180001f94  pop     rdi
0x180001f95  pop     rsi
0x180001f96  pop     rbp
0x180001f97  pop     rbx
0x180001f98  retn
```
