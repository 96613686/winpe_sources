# IsRoutingProtocolInstalled(ulong)

- ea: `0x180029c80`
- end: `0x180029ef6`
- name: `?IsRoutingProtocolInstalled@@YAEK@Z`
- size: `630`
- prototype: `unsigned __int8 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001a820`
- `0x1800203b0`
- `0x180020930`

## callees

- `0x180005698`
- `0x180029c80`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029ea0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029ec0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029ea0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029ec0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029d32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029d32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029d4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029d6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029d86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029da2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029dbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029dda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029d4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029d6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029d86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029da2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029dbe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ecb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029cd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180029cd0`

## string_xrefs

- `0x180029d0b`: `MPRAPI.DLL`
- `0x180029db4`: `MprConfigTransportGetInfo`
- `0x180029d98`: `MprConfigTransportGetHandle`
- `0x180029d7c`: `MprConfigServerDisconnect`
- `0x180029d60`: `MprConfigServerConnect`
- `0x180029d44`: `MprConfigBufferFree`

## pseudocode

```c
char __fastcall IsRoutingProtocolInstalled()
{
  UINT SystemDirectoryW; // eax
  char v1; // di
  __int64 v2; // rcx
  HMODULE Library; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rsi
  FARPROC v6; // r15
  void (*v7)(void); // r14
  FARPROC v8; // r12
  FARPROC v9; // r13
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  FARPROC v15; // [rsp+60h] [rbp-A0h]
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  v14 = 0;
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  if ( SystemDirectoryW - 1 > 0x103 )
    goto LABEL_23;
  v1 = 1;
  if ( Buffer[SystemDirectoryW - 1] != 92 )
  {
    v2 = SystemDirectoryW++;
    Buffer[v2] = 92;
  }
  if ( StringCchCopyW(&Buffer[SystemDirectoryW], 261 - SystemDirectoryW, L"MPRAPI.DLL") < 0 )
    return 0;
  Library = LoadLibraryExW(Buffer, 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "MprConfigBufferFree");
    if ( ProcAddress )
    {
      v6 = GetProcAddress(v4, "MprConfigServerConnect");
      if ( v6 )
      {
        v7 = (void (*)(void))GetProcAddress(v4, "MprConfigServerDisconnect");
        if ( v7 )
        {
          v8 = GetProcAddress(v4, "MprConfigTransportGetHandle");
          if ( v8 )
          {
            v9 = GetProcAddress(v4, "MprConfigTransportGetInfo");
            if ( v9 )
            {
              v15 = GetProcAddress(v4, "MprInfoBlockFind");
              if ( v15 )
              {
                v12 = 0;
                if ( ((unsigned int (__fastcall *)(_QWORD, __int64 *))v6)(0, &v12)
                  || ((unsigned int (__fastcall *)(__int64, __int64, __int64 *))v8)(v12, 33, &v14)
                  || ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, int *, _QWORD, _QWORD, _QWORD))v9)(
                       v12,
                       v14,
                       &v13,
                       &v11,
                       0,
                       0,
                       0) )
                {
                  if ( v12 )
                    v7();
                  v1 = 0;
                  goto LABEL_22;
                }
                ((void (__fastcall *)(__int64))v7)(v12);
                if ( !((unsigned int (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD))v15)(
                        v13,
                        2167875349LL,
                        0,
                        0,
                        0) )
                {
                  ((void (__fastcall *)(__int64))ProcAddress)(v13);
LABEL_22:
                  FreeLibrary(v4);
                  return v1;
                }
                ((void (__fastcall *)(__int64))ProcAddress)(v13);
              }
            }
          }
        }
      }
    }
    FreeLibrary(v4);
  }
  else
  {
LABEL_23:
    GetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x180029c80  push    rbp
0x180029c82  push    rbx
0x180029c83  push    rsi
0x180029c84  push    rdi
0x180029c85  push    r12
0x180029c87  push    r13
0x180029c89  push    r14
0x180029c8b  push    r15
0x180029c8d  lea     rbp, [rsp-198h]
0x180029c95  sub     rsp, 298h
0x180029c9c  mov     rax, cs:__security_cookie
0x180029ca3  xor     rax, rsp
0x180029ca6  mov     [rbp+1D0h+var_50], rax
0x180029cad  xor     r13d, r13d
0x180029cb0  lea     rcx, [rsp+2D0h+Buffer]; lpBuffer
0x180029cb5  mov     ebx, 105h
0x180029cba  mov     [rsp+2D0h+var_280], r13
0x180029cbf  mov     edx, ebx; uSize
0x180029cc1  mov     [rsp+2D0h+var_290], r13d
0x180029cc6  mov     [rsp+2D0h+var_288], r13
0x180029ccb  mov     [rsp+2D0h+var_278], r13
0x180029cd0  call    cs:__imp_GetSystemDirectoryW
0x180029cd6  lea     ecx, [rax-1]
0x180029cd9  cmp     ecx, 103h
0x180029cdf  ja      loc_180029ECB
0x180029ce5  lea     ecx, [rax-1]
0x180029ce8  lea     r8d, [r13+5Ch]
0x180029cec  lea     edi, [r13+1]
0x180029cf0  cmp     [rsp+rcx*2+2D0h+Buffer], r8w
0x180029cf6  jz      short loc_180029D02
0x180029cf8  mov     ecx, eax
0x180029cfa  add     eax, edi
0x180029cfc  mov     [rsp+rcx*2+2D0h+Buffer], r8w
0x180029d02  sub     ebx, eax
0x180029d04  lea     rcx, [rsp+2D0h+Buffer]
0x180029d09  mov     eax, eax
0x180029d0b  lea     r8, ?c_wszMprapiDll@@3QBGB; "MPRAPI.DLL"
0x180029d12  mov     edx, ebx; unsigned __int64
0x180029d14  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180029d18  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029d1d  test    eax, eax
0x180029d1f  js      loc_180029ED1
0x180029d25  xor     edx, edx; hFile
0x180029d27  lea     rcx, [rsp+2D0h+Buffer]; lpLibFileName
0x180029d2c  mov     r8d, 800h; dwFlags
0x180029d32  call    cs:__imp_LoadLibraryExW
0x180029d38  mov     rbx, rax
0x180029d3b  test    rax, rax
0x180029d3e  jz      loc_180029ECB
0x180029d44  lea     rdx, ?c_szMprConfigBufferFree@@3QBDB; "MprConfigBufferFree"
0x180029d4b  mov     rcx, rax; hModule
0x180029d4e  call    cs:__imp_GetProcAddress
0x180029d54  mov     rsi, rax
0x180029d57  test    rax, rax
0x180029d5a  jz      loc_180029E9D
0x180029d60  lea     rdx, ?c_szMprConfigServerConnect@@3QBDB; "MprConfigServerConnect"
0x180029d67  mov     rcx, rbx; hModule
0x180029d6a  call    cs:__imp_GetProcAddress
0x180029d70  mov     r15, rax
0x180029d73  test    rax, rax
0x180029d76  jz      loc_180029E9D
0x180029d7c  lea     rdx, ?c_szMprConfigServerDisconnect@@3QBDB; "MprConfigServerDisconnect"
0x180029d83  mov     rcx, rbx; hModule
0x180029d86  call    cs:__imp_GetProcAddress
0x180029d8c  mov     r14, rax
0x180029d8f  test    rax, rax
0x180029d92  jz      loc_180029E9D
0x180029d98  lea     rdx, ?c_szMprConfigTransportGetHandle@@3QBDB; "MprConfigTransportGetHandle"
0x180029d9f  mov     rcx, rbx; hModule
0x180029da2  call    cs:__imp_GetProcAddress
0x180029da8  mov     r12, rax
0x180029dab  test    rax, rax
0x180029dae  jz      loc_180029E9D
0x180029db4  lea     rdx, ?c_szMprConfigTransportGetInfo@@3QBDB; "MprConfigTransportGetInfo"
0x180029dbb  mov     rcx, rbx; hModule
0x180029dbe  call    cs:__imp_GetProcAddress
0x180029dc4  mov     r13, rax
0x180029dc7  test    rax, rax
0x180029dca  jz      loc_180029E9D
0x180029dd0  lea     rdx, ?c_szMprInfoBlockFind@@3QBDB; "MprInfoBlockFind"
0x180029dd7  mov     rcx, rbx; hModule
0x180029dda  call    cs:__imp_GetProcAddress
0x180029de0  mov     [rsp+2D0h+var_270], rax
0x180029de5  test    rax, rax
0x180029de8  jz      loc_180029E9D
0x180029dee  lea     rdx, [rsp+2D0h+var_288]
0x180029df3  mov     [rsp+2D0h+var_288], 0
0x180029dfc  xor     ecx, ecx
0x180029dfe  mov     rax, r15
0x180029e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e06  xor     r15d, r15d
0x180029e09  test    eax, eax
0x180029e0b  jnz     loc_180029EA8
0x180029e11  mov     rcx, [rsp+2D0h+var_288]
0x180029e16  lea     edx, [rax+21h]
0x180029e19  mov     rax, r12
0x180029e1c  lea     r8, [rsp+2D0h+var_278]
0x180029e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e26  test    eax, eax
0x180029e28  jnz     short loc_180029EA8
0x180029e2a  mov     rdx, [rsp+2D0h+var_278]
0x180029e2f  lea     r9, [rsp+2D0h+var_290]
0x180029e34  mov     rcx, [rsp+2D0h+var_288]
0x180029e39  lea     r8, [rsp+2D0h+var_280]
0x180029e3e  mov     [rsp+2D0h+var_2A0], r15
0x180029e43  mov     rax, r13
0x180029e46  mov     [rsp+2D0h+var_2A8], r15
0x180029e4b  mov     [rsp+2D0h+var_2B0], r15
0x180029e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e55  test    eax, eax
0x180029e57  jnz     short loc_180029EA8
0x180029e59  mov     rcx, [rsp+2D0h+var_288]
0x180029e5e  mov     rax, r14
0x180029e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e66  mov     rcx, [rsp+2D0h+var_280]
0x180029e6b  xor     r9d, r9d
0x180029e6e  mov     rax, [rsp+2D0h+var_270]
0x180029e73  xor     r8d, r8d
0x180029e76  mov     edx, 81372715h
0x180029e7b  mov     [rsp+2D0h+var_2B0], r15
0x180029e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e85  mov     rcx, [rsp+2D0h+var_280]
0x180029e8a  test    eax, eax
0x180029e8c  mov     rax, rsi
0x180029e8f  jnz     short loc_180029E98
0x180029e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e96  jmp     short loc_180029EBD
0x180029e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e9d  mov     rcx, rbx; hLibModule
0x180029ea0  call    cs:__imp_FreeLibrary
0x180029ea6  jmp     short loc_180029ED1
0x180029ea8  mov     rcx, [rsp+2D0h+var_288]
0x180029ead  test    rcx, rcx
0x180029eb0  jz      short loc_180029EBA
0x180029eb2  mov     rax, r14
0x180029eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029eba  mov     dil, r15b
0x180029ebd  mov     rcx, rbx; hLibModule
0x180029ec0  call    cs:__imp_FreeLibrary
0x180029ec6  mov     al, dil
0x180029ec9  jmp     short loc_180029ED3
0x180029ecb  call    cs:__imp_GetLastError
0x180029ed1  xor     al, al
0x180029ed3  mov     rcx, [rbp+1D0h+var_50]
0x180029eda  xor     rcx, rsp; StackCookie
0x180029edd  call    __security_check_cookie
0x180029ee2  add     rsp, 298h
0x180029ee9  pop     r15
0x180029eeb  pop     r14
0x180029eed  pop     r13
0x180029eef  pop     r12
0x180029ef1  pop     rdi
0x180029ef2  pop     rsi
0x180029ef3  pop     rbx
0x180029ef4  pop     rbp
0x180029ef5  retn
```
