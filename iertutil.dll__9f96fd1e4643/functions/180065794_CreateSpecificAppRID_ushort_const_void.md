# CreateSpecificAppRID(ushort const *,void * *)

- ea: `0x180065794`
- end: `0x180065872`
- name: `?CreateSpecificAppRID@@YAKPEBGPEAPEAX@Z`
- size: `222`
- prototype: `unsigned int(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800306b0`

## callees

- `0x180065794`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006585d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006585d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800657d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800657d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800657b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800657b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006583d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006583d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065852`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18006584a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18006584a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006582f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006582f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006580b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006580b`

## string_xrefs

- `0x1800657c9`: `DeriveAppContainerSidFromAppContainerName`
- `0x1800657a8`: `Userenv.dll`

## pseudocode

```c
__int64 __fastcall CreateSpecificAppRID(const unsigned __int16 *a1, void **a2)
{
  DWORD LastError; // ebx
  HMODULE Library; // rax
  HMODULE v6; // rdi
  FARPROC ProcAddress; // rax
  LPWSTR StringSid; // [rsp+50h] [rbp+18h] BYREF
  PSID Sid; // [rsp+58h] [rbp+20h] BYREF

  LastError = 87;
  Library = LoadLibraryExW(L"Userenv.dll", 0, 0);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DeriveAppContainerSidFromAppContainerName");
    if ( ProcAddress )
    {
      Sid = 0;
      if ( ((int (__fastcall *)(const unsigned __int16 *, PSID *))ProcAddress)(a1, &Sid) >= 0 )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(Sid, &StringSid) )
        {
          if ( StringSid[7] == 50 )
          {
            StringSid[7] = 51;
            if ( ConvertStringSidToSidW(StringSid, a2) )
              LastError = 0;
            else
              LastError = GetLastError();
          }
          FreeSid(Sid);
        }
        else
        {
          LastError = GetLastError();
        }
      }
    }
    FreeLibrary(v6);
  }
  return LastError;
}

```

## disassembly

```asm
0x180065794  mov     [rsp+arg_0], rbx
0x180065799  push    rbp
0x18006579a  push    rsi
0x18006579b  push    rdi
0x18006579c  sub     rsp, 20h
0x1800657a0  mov     rsi, rdx
0x1800657a3  mov     rbp, rcx
0x1800657a6  xor     edx, edx; hFile
0x1800657a8  lea     rcx, aUserenvDll_0; "Userenv.dll"
0x1800657af  xor     r8d, r8d; dwFlags
0x1800657b2  mov     ebx, 57h ; 'W'
0x1800657b7  call    cs:__imp_LoadLibraryExW
0x1800657bd  mov     rdi, rax
0x1800657c0  test    rax, rax
0x1800657c3  jz      loc_180065863
0x1800657c9  lea     rdx, aDeriveappconta_0; "DeriveAppContainerSidFromAppContainerNa"...
0x1800657d0  mov     rcx, rax; hModule
0x1800657d3  call    cs:__imp_GetProcAddress
0x1800657d9  test    rax, rax
0x1800657dc  jz      short loc_18006585A
0x1800657de  lea     rdx, [rsp+38h+Sid]
0x1800657e3  mov     [rsp+38h+Sid], 0
0x1800657ec  mov     rcx, rbp
0x1800657ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800657f4  test    eax, eax
0x1800657f6  js      short loc_18006585A
0x1800657f8  mov     rcx, [rsp+38h+Sid]; Sid
0x1800657fd  lea     rdx, [rsp+38h+StringSid]; StringSid
0x180065802  mov     [rsp+38h+StringSid], 0
0x18006580b  call    cs:__imp_ConvertSidToStringSidW
0x180065811  test    eax, eax
0x180065813  jz      short loc_180065852
0x180065815  mov     rax, [rsp+38h+StringSid]
0x18006581a  cmp     word ptr [rax+0Eh], 32h ; '2'
0x18006581f  jnz     short loc_180065845
0x180065821  mov     word ptr [rax+0Eh], 33h ; '3'
0x180065827  mov     rdx, rsi; Sid
0x18006582a  mov     rcx, [rsp+38h+StringSid]; StringSid
0x18006582f  call    cs:__imp_ConvertStringSidToSidW
0x180065835  test    eax, eax
0x180065837  jz      short loc_18006583D
0x180065839  xor     ebx, ebx
0x18006583b  jmp     short loc_180065845
0x18006583d  call    cs:__imp_GetLastError
0x180065843  mov     ebx, eax
0x180065845  mov     rcx, [rsp+38h+Sid]; pSid
0x18006584a  call    cs:__imp_FreeSid
0x180065850  jmp     short loc_18006585A
0x180065852  call    cs:__imp_GetLastError
0x180065858  mov     ebx, eax
0x18006585a  mov     rcx, rdi; hLibModule
0x18006585d  call    cs:__imp_FreeLibrary
0x180065863  mov     eax, ebx
0x180065865  mov     rbx, [rsp+38h+arg_0]
0x18006586a  add     rsp, 20h
0x18006586e  pop     rdi
0x18006586f  pop     rsi
0x180065870  pop     rbp
0x180065871  retn
```
