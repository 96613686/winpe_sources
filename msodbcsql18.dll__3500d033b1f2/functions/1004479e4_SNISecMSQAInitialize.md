# SNISecMSQAInitialize

- ea: `0x1004479e4`
- end: `0x1004482f7`
- name: `SNISecMSQAInitialize`
- size: `2323`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1004669dc`
- `0x100486398`

## callees

- `0x10043a7c4`
- `0x10043a930`
- `0x1004479e4`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x100447a9e`
- `KERNEL32!LoadLibraryExA` at `0x100447a9e`
- `KERNEL32!GetLastError` at `0x100447ab4`
- `KERNEL32!GetLastError` at `0x100447b60`
- `KERNEL32!GetLastError` at `0x100447bf1`
- `KERNEL32!GetLastError` at `0x100447c82`
- `KERNEL32!GetLastError` at `0x100447d13`
- `KERNEL32!GetLastError` at `0x100447da4`
- `KERNEL32!GetLastError` at `0x100447e35`
- `KERNEL32!GetLastError` at `0x100447ec6`
- `KERNEL32!GetLastError` at `0x100447f57`
- `KERNEL32!GetLastError` at `0x100447fe8`
- `KERNEL32!GetLastError` at `0x100448079`
- `KERNEL32!GetLastError` at `0x10044810a`
- `KERNEL32!GetLastError` at `0x10044819f`
- `KERNEL32!GetLastError` at `0x100448253`
- `KERNEL32!GetLastError` at `0x100447ab4`
- `KERNEL32!GetLastError` at `0x100447b60`
- `KERNEL32!GetLastError` at `0x100447bf1`
- `KERNEL32!GetLastError` at `0x100447c82`
- `KERNEL32!GetLastError` at `0x100447d13`
- `KERNEL32!GetLastError` at `0x100447da4`
- `KERNEL32!GetLastError` at `0x100447e35`
- `KERNEL32!GetLastError` at `0x100447ec6`
- `KERNEL32!GetLastError` at `0x100447f57`
- `KERNEL32!GetLastError` at `0x100447fe8`
- `KERNEL32!GetLastError` at `0x100448079`
- `KERNEL32!GetLastError` at `0x10044810a`
- `KERNEL32!GetLastError` at `0x10044819f`
- `KERNEL32!GetLastError` at `0x100448253`
- `KERNEL32!GetProcAddress` at `0x100447b4e`
- `KERNEL32!GetProcAddress` at `0x100447bdf`
- `KERNEL32!GetProcAddress` at `0x100447c70`
- `KERNEL32!GetProcAddress` at `0x100447d01`
- `KERNEL32!GetProcAddress` at `0x100447d92`
- `KERNEL32!GetProcAddress` at `0x100447e23`
- `KERNEL32!GetProcAddress` at `0x100447eb4`
- `KERNEL32!GetProcAddress` at `0x100447f45`
- `KERNEL32!GetProcAddress` at `0x100447fd6`
- `KERNEL32!GetProcAddress` at `0x100448067`
- `KERNEL32!GetProcAddress` at `0x1004480f8`
- `KERNEL32!GetProcAddress` at `0x100448189`
- `KERNEL32!GetProcAddress` at `0x100447b4e`
- `KERNEL32!GetProcAddress` at `0x100447bdf`
- `KERNEL32!GetProcAddress` at `0x100447c70`
- `KERNEL32!GetProcAddress` at `0x100447d01`
- `KERNEL32!GetProcAddress` at `0x100447d92`
- `KERNEL32!GetProcAddress` at `0x100447e23`
- `KERNEL32!GetProcAddress` at `0x100447eb4`
- `KERNEL32!GetProcAddress` at `0x100447f45`
- `KERNEL32!GetProcAddress` at `0x100447fd6`
- `KERNEL32!GetProcAddress` at `0x100448067`
- `KERNEL32!GetProcAddress` at `0x1004480f8`
- `KERNEL32!GetProcAddress` at `0x100448189`
- `KERNEL32!FreeLibrary` at `0x100448249`
- `KERNEL32!FreeLibrary` at `0x100448249`

## string_xrefs

- `0x100447a91`: `mssql-auth.dll`
- `0x100447b44`: `MSQACreateAuthenticationContextNoUI`
- `0x100447bd8`: `MSQACreateAuthenticationContext`
- `0x100447cfa`: `MSQAAcquireToken`
- `0x100447f3e`: `MSQAGetAccessToken`
- `0x100448060`: `MSQADeleteRequest`
- `0x100448182`: `MSQAUICreateHostWindow`

## pseudocode

```c
__int64 SNISecMSQAInitialize()
{
  struct CCriticalSectionNT_SNI *v0; // r14
  HMODULE Library; // rax
  DWORD LastError; // ebx
  __int64 v3; // r15
  wchar_t *v4; // r8
  DWORD v5; // eax

  v0 = g_csSecPackageInitialize;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)g_csSecPackageInitialize + 2) + 32LL) + 8LL))(*((_QWORD *)g_csSecPackageInitialize + 2) + 32LL);
  if ( dword_1005D9028 > 0 )
  {
    ++dword_1005D9028;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E62E8[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        249856,
        off_1005E62E8[0],
        0);
    goto LABEL_107;
  }
  Library = LoadLibraryExA("mssql-auth.dll", 0, 0x800u);
  hLibModule = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E62F0[0] )
    {
      SniErrorIdFromStringId(0xC402u);
      bidTraceW(0, 260096, off_1005E62F0[0], 9);
    }
    SNISetLastError(9, LastError, 50178);
    if ( (bidGblFlags & 2) != 0 && off_1005E62F8[0] )
      bidTraceW(0, 263168, off_1005E62F8[0], LastError);
    goto LABEL_99;
  }
  qword_1005D8FC8 = (__int64)GetProcAddress(Library, "MSQACreateAuthenticationContextNoUI");
  if ( qword_1005D8FC8 )
  {
    qword_1005D8FD0 = (__int64)GetProcAddress(hLibModule, "MSQACreateAuthenticationContext");
    if ( qword_1005D8FD0 )
    {
      qword_1005D8FD8 = (__int64)GetProcAddress(hLibModule, "MSQASetOption");
      if ( qword_1005D8FD8 )
      {
        qword_1005D8FE0 = (__int64)GetProcAddress(hLibModule, "MSQAAcquireToken");
        if ( qword_1005D8FE0 )
        {
          qword_1005D8FF8 = (__int64)GetProcAddress(hLibModule, "MSQAGetRequestStatus");
          if ( qword_1005D8FF8 )
          {
            qword_1005D9000 = (__int64)GetProcAddress(hLibModule, "MSQAUseUsernamePassword");
            if ( qword_1005D9000 )
            {
              qword_1005D9008 = (__int64)GetProcAddress(hLibModule, "MSQAUseWindowsAuthentication");
              if ( qword_1005D9008 )
              {
                qword_1005D8FE8 = (__int64)GetProcAddress(hLibModule, "MSQAGetAccessToken");
                if ( qword_1005D8FE8 )
                {
                  qword_1005D8FF0 = (__int64)GetProcAddress(hLibModule, "MSQAGetErrorDescription");
                  if ( qword_1005D8FF0 )
                  {
                    qword_1005D9010 = (__int64)GetProcAddress(hLibModule, "MSQADeleteRequest");
                    if ( qword_1005D9010 )
                    {
                      qword_1005D9018 = (__int64)GetProcAddress(hLibModule, "MSQAReleaseAuthenticationContext");
                      if ( qword_1005D9018 )
                      {
                        qword_1005D9020 = (__int64)GetProcAddress(hLibModule, "MSQAUICreateHostWindow");
                        if ( qword_1005D9020 )
                        {
                          ++dword_1005D9028;
LABEL_107:
                          LastError = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v0 + 2) + 32LL) + 24LL))(*((_QWORD *)v0 + 2) + 32LL);
                          goto LABEL_108;
                        }
                        v3 = 279552;
                        LastError = GetLastError();
                        if ( (bidGblFlags & 2) != 0 && off_1005E63B0[0] )
                          bidTraceW(0, 279552, off_1005E63B0[0], LastError);
                        if ( (bidGblFlags & 2) == 0 || !off_1005E63B8[0] )
                          goto LABEL_98;
                        SniErrorIdFromStringId(0xC403u);
                        v4 = off_1005E63B8[0];
                      }
                      else
                      {
                        v3 = 278528;
                        LastError = GetLastError();
                        if ( (bidGblFlags & 2) != 0 && off_1005E63A0[0] )
                          bidTraceW(0, 278528, off_1005E63A0[0], LastError);
                        if ( (bidGblFlags & 2) == 0 || !off_1005E63A8[0] )
                          goto LABEL_98;
                        SniErrorIdFromStringId(0xC403u);
                        v4 = off_1005E63A8[0];
                      }
                    }
                    else
                    {
                      v3 = 277504;
                      LastError = GetLastError();
                      if ( (bidGblFlags & 2) != 0 && off_1005E6390[0] )
                        bidTraceW(0, 277504, off_1005E6390[0], LastError);
                      if ( (bidGblFlags & 2) == 0 || !off_1005E6398[0] )
                        goto LABEL_98;
                      SniErrorIdFromStringId(0xC403u);
                      v4 = off_1005E6398[0];
                    }
                  }
                  else
                  {
                    v3 = 276480;
                    LastError = GetLastError();
                    if ( (bidGblFlags & 2) != 0 && off_1005E6380[0] )
                      bidTraceW(0, 276480, off_1005E6380[0], LastError);
                    if ( (bidGblFlags & 2) == 0 || !off_1005E6388[0] )
                      goto LABEL_98;
                    SniErrorIdFromStringId(0xC403u);
                    v4 = off_1005E6388[0];
                  }
                }
                else
                {
                  v3 = 275456;
                  LastError = GetLastError();
                  if ( (bidGblFlags & 2) != 0 && off_1005E6370[0] )
                    bidTraceW(0, 275456, off_1005E6370[0], LastError);
                  if ( (bidGblFlags & 2) == 0 || !off_1005E6378[0] )
                    goto LABEL_98;
                  SniErrorIdFromStringId(0xC403u);
                  v4 = off_1005E6378[0];
                }
              }
              else
              {
                v3 = 274432;
                LastError = GetLastError();
                if ( (bidGblFlags & 2) != 0 && off_1005E6360[0] )
                  bidTraceW(0, 274432, off_1005E6360[0], LastError);
                if ( (bidGblFlags & 2) == 0 || !off_1005E6368[0] )
                  goto LABEL_98;
                SniErrorIdFromStringId(0xC403u);
                v4 = off_1005E6368[0];
              }
            }
            else
            {
              v3 = 273408;
              LastError = GetLastError();
              if ( (bidGblFlags & 2) != 0 && off_1005E6350[0] )
                bidTraceW(0, 273408, off_1005E6350[0], LastError);
              if ( (bidGblFlags & 2) == 0 || !off_1005E6358[0] )
                goto LABEL_98;
              SniErrorIdFromStringId(0xC403u);
              v4 = off_1005E6358[0];
            }
          }
          else
          {
            v3 = 272384;
            LastError = GetLastError();
            if ( (bidGblFlags & 2) != 0 && off_1005E6340[0] )
              bidTraceW(0, 272384, off_1005E6340[0], LastError);
            if ( (bidGblFlags & 2) == 0 || !off_1005E6348[0] )
              goto LABEL_98;
            SniErrorIdFromStringId(0xC403u);
            v4 = off_1005E6348[0];
          }
        }
        else
        {
          v3 = 271360;
          LastError = GetLastError();
          if ( (bidGblFlags & 2) != 0 && off_1005E6330[0] )
            bidTraceW(0, 271360, off_1005E6330[0], LastError);
          if ( (bidGblFlags & 2) == 0 || !off_1005E6338[0] )
            goto LABEL_98;
          SniErrorIdFromStringId(0xC403u);
          v4 = off_1005E6338[0];
        }
      }
      else
      {
        v3 = 270336;
        LastError = GetLastError();
        if ( (bidGblFlags & 2) != 0 && off_1005E6320[0] )
          bidTraceW(0, 270336, off_1005E6320[0], LastError);
        if ( (bidGblFlags & 2) == 0 || !off_1005E6328[0] )
          goto LABEL_98;
        SniErrorIdFromStringId(0xC403u);
        v4 = off_1005E6328[0];
      }
    }
    else
    {
      v3 = 269312;
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_1005E6310[0] )
        bidTraceW(0, 269312, off_1005E6310[0], LastError);
      if ( (bidGblFlags & 2) == 0 || !off_1005E6318[0] )
        goto LABEL_98;
      SniErrorIdFromStringId(0xC403u);
      v4 = off_1005E6318[0];
    }
  }
  else
  {
    v3 = 268288;
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1005E6300[0] )
      bidTraceW(0, 268288, off_1005E6300[0], LastError);
    if ( (bidGblFlags & 2) == 0 || !off_1005E6308[0] )
      goto LABEL_98;
    SniErrorIdFromStringId(0xC403u);
    v4 = off_1005E6308[0];
  }
  bidTraceW(0, v3, v4, 9);
LABEL_98:
  SNISetLastError(9, LastError, 50179);
LABEL_99:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v0 + 2) + 32LL) + 24LL))(*((_QWORD *)v0 + 2) + 32LL);
  if ( LastError && hLibModule )
  {
    if ( !FreeLibrary(hLibModule) )
    {
      v5 = GetLastError();
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1005E63C0[0] )
          bidTraceW(0, 297984, off_1005E63C0[0], v5);
      }
    }
    hLibModule = 0;
  }
LABEL_108:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E63C8[0] )
    bidTraceW(0, 304128, off_1005E63C8[0], LastError);
  return LastError;
}

```

## disassembly

```asm
0x1004479e4  mov     [rsp+arg_0], rbx
0x1004479e9  mov     [rsp+arg_8], rbp
0x1004479ee  mov     [rsp+arg_10], rsi
0x1004479f3  push    r12
0x1004479f5  push    r14
0x1004479f7  push    r15
0x1004479f9  sub     rsp, 30h
0x1004479fd  mov     r14, cs:?g_csSecPackageInitialize@@3PEAVCCriticalSectionNT_SNI@@EA; CCriticalSectionNT_SNI * g_csSecPackageInitialize
0x100447a04  mov     rcx, [r14+10h]
0x100447a08  add     rcx, 20h ; ' '
0x100447a0c  mov     rax, [rcx]
0x100447a0f  mov     rax, [rax+8]
0x100447a13  call    cs:__guard_dispatch_icall_fptr
0x100447a19  mov     eax, cs:dword_1005D9028
0x100447a1f  mov     r12d, 20002h
0x100447a25  test    eax, eax
0x100447a27  jle     short loc_100447A8F
0x100447a29  inc     eax
0x100447a2b  mov     cs:dword_1005D9028, eax
0x100447a31  mov     eax, cs:_bidGblFlags
0x100447a37  and     eax, r12d
0x100447a3a  cmp     eax, r12d
0x100447a3d  jnz     loc_100448294
0x100447a43  mov     rax, cs:off_1005E62E8; "<SNISecMSQAInitialize|SNI> Active Direc"...
0x100447a4a  test    rax, rax
0x100447a4d  jz      loc_100448294
0x100447a53  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100447a5b  jz      loc_100448294
0x100447a61  mov     r9, cs:off_1005E62E8; "<SNISecMSQAInitialize|SNI> Active Direc"...
0x100447a68  xor     edx, edx
0x100447a6a  mov     rcx, cs:_bidID
0x100447a71  mov     r8d, 3D000h
0x100447a77  mov     rax, cs:off_1005D39E0
0x100447a7e  and     [rsp+48h+var_28], 0
0x100447a84  call    cs:__guard_dispatch_icall_fptr
0x100447a8a  jmp     loc_100448294
0x100447a8f  xor     edx, edx; hFile
0x100447a91  lea     rcx, aMssqlAuthDll; "mssql-auth.dll"
0x100447a98  mov     r8d, 800h; dwFlags
0x100447a9e  call    cs:__imp_LoadLibraryExA
0x100447aa4  mov     cs:hLibModule, rax
0x100447aab  test    rax, rax
0x100447aae  jnz     loc_100447B44
0x100447ab4  call    cs:__imp_GetLastError
0x100447aba  test    byte ptr cs:_bidGblFlags, 2
0x100447ac1  mov     ebp, 0C402h
0x100447ac6  mov     ebx, eax
0x100447ac8  mov     esi, 9
0x100447acd  jz      short loc_100447B00
0x100447acf  mov     rcx, cs:off_1005E62F0; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447ad6  test    rcx, rcx
0x100447ad9  jz      short loc_100447B00
0x100447adb  mov     ecx, ebp; unsigned int
0x100447add  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100447ae2  mov     r8, cs:off_1005E62F0; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447ae9  mov     r9d, esi
0x100447aec  mov     edx, 3F800h
0x100447af1  mov     [rsp+48h+var_20], ebx
0x100447af5  xor     ecx, ecx
0x100447af7  mov     dword ptr [rsp+48h+var_28], eax
0x100447afb  call    _bidTraceW
0x100447b00  mov     r8d, ebp
0x100447b03  mov     edx, ebx
0x100447b05  mov     ecx, esi
0x100447b07  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100447b0c  test    byte ptr cs:_bidGblFlags, 2
0x100447b13  jz      loc_100448224
0x100447b19  mov     rax, cs:off_1005E62F8; "<SNISecMSQAInitialize|ERR|SNI> Loading "...
0x100447b20  test    rax, rax
0x100447b23  jz      loc_100448224
0x100447b29  mov     r8, cs:off_1005E62F8; "<SNISecMSQAInitialize|ERR|SNI> Loading "...
0x100447b30  mov     r9d, ebx
0x100447b33  mov     edx, 40400h
0x100447b38  xor     ecx, ecx
0x100447b3a  call    _bidTraceW
0x100447b3f  jmp     loc_100448224
0x100447b44  lea     rdx, aMsqacreateauth_0; "MSQACreateAuthenticationContextNoUI"
0x100447b4b  mov     rcx, rax; hModule
0x100447b4e  call    cs:__imp_GetProcAddress
0x100447b54  mov     cs:qword_1005D8FC8, rax
0x100447b5b  test    rax, rax
0x100447b5e  jnz     short loc_100447BD1
0x100447b60  call    cs:__imp_GetLastError
0x100447b66  test    byte ptr cs:_bidGblFlags, 2
0x100447b6d  mov     r15d, 41800h
0x100447b73  mov     ebx, eax
0x100447b75  jz      short loc_100447B97
0x100447b77  mov     rax, cs:off_1005E6300; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447b7e  test    rax, rax
0x100447b81  jz      short loc_100447B97
0x100447b83  mov     r8, cs:off_1005E6300; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447b8a  mov     r9d, ebx
0x100447b8d  mov     edx, r15d
0x100447b90  xor     ecx, ecx
0x100447b92  call    _bidTraceW
0x100447b97  test    byte ptr cs:_bidGblFlags, 2
0x100447b9e  mov     esi, 9
0x100447ba3  mov     ebp, 0C403h
0x100447ba8  jz      loc_100448218
0x100447bae  mov     rax, cs:off_1005E6308; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447bb5  test    rax, rax
0x100447bb8  jz      loc_100448218
0x100447bbe  mov     ecx, ebp; unsigned int
0x100447bc0  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100447bc5  mov     r8, cs:off_1005E6308; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447bcc  jmp     loc_100448203
0x100447bd1  mov     rcx, cs:hLibModule; hModule
0x100447bd8  lea     rdx, aMsqacreateauth; "MSQACreateAuthenticationContext"
0x100447bdf  call    cs:__imp_GetProcAddress
0x100447be5  mov     cs:qword_1005D8FD0, rax
0x100447bec  test    rax, rax
0x100447bef  jnz     short loc_100447C62
0x100447bf1  call    cs:__imp_GetLastError
0x100447bf7  test    byte ptr cs:_bidGblFlags, 2
0x100447bfe  mov     r15d, 41C00h
0x100447c04  mov     ebx, eax
0x100447c06  jz      short loc_100447C28
0x100447c08  mov     rax, cs:off_1005E6310; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447c0f  test    rax, rax
0x100447c12  jz      short loc_100447C28
0x100447c14  mov     r8, cs:off_1005E6310; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447c1b  mov     r9d, ebx
0x100447c1e  mov     edx, r15d
0x100447c21  xor     ecx, ecx
0x100447c23  call    _bidTraceW
0x100447c28  test    byte ptr cs:_bidGblFlags, 2
0x100447c2f  mov     esi, 9
0x100447c34  mov     ebp, 0C403h
0x100447c39  jz      loc_100448218
0x100447c3f  mov     rax, cs:off_1005E6318; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447c46  test    rax, rax
0x100447c49  jz      loc_100448218
0x100447c4f  mov     ecx, ebp; unsigned int
0x100447c51  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100447c56  mov     r8, cs:off_1005E6318; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447c5d  jmp     loc_100448203
0x100447c62  mov     rcx, cs:hLibModule; hModule
0x100447c69  lea     rdx, aMsqasetoption; "MSQASetOption"
0x100447c70  call    cs:__imp_GetProcAddress
0x100447c76  mov     cs:qword_1005D8FD8, rax
0x100447c7d  test    rax, rax
0x100447c80  jnz     short loc_100447CF3
0x100447c82  call    cs:__imp_GetLastError
0x100447c88  test    byte ptr cs:_bidGblFlags, 2
0x100447c8f  mov     r15d, 42000h
0x100447c95  mov     ebx, eax
0x100447c97  jz      short loc_100447CB9
0x100447c99  mov     rax, cs:off_1005E6320; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447ca0  test    rax, rax
0x100447ca3  jz      short loc_100447CB9
0x100447ca5  mov     r8, cs:off_1005E6320; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447cac  mov     r9d, ebx
0x100447caf  mov     edx, r15d
0x100447cb2  xor     ecx, ecx
0x100447cb4  call    _bidTraceW
0x100447cb9  test    byte ptr cs:_bidGblFlags, 2
0x100447cc0  mov     esi, 9
0x100447cc5  mov     ebp, 0C403h
0x100447cca  jz      loc_100448218
0x100447cd0  mov     rax, cs:off_1005E6328; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447cd7  test    rax, rax
0x100447cda  jz      loc_100448218
0x100447ce0  mov     ecx, ebp; unsigned int
0x100447ce2  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100447ce7  mov     r8, cs:off_1005E6328; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447cee  jmp     loc_100448203
0x100447cf3  mov     rcx, cs:hLibModule; hModule
0x100447cfa  lea     rdx, aMsqaacquiretok; "MSQAAcquireToken"
0x100447d01  call    cs:__imp_GetProcAddress
0x100447d07  mov     cs:qword_1005D8FE0, rax
0x100447d0e  test    rax, rax
0x100447d11  jnz     short loc_100447D84
0x100447d13  call    cs:__imp_GetLastError
0x100447d19  test    byte ptr cs:_bidGblFlags, 2
0x100447d20  mov     r15d, 42400h
0x100447d26  mov     ebx, eax
0x100447d28  jz      short loc_100447D4A
0x100447d2a  mov     rax, cs:off_1005E6330; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447d31  test    rax, rax
0x100447d34  jz      short loc_100447D4A
0x100447d36  mov     r8, cs:off_1005E6330; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447d3d  mov     r9d, ebx
0x100447d40  mov     edx, r15d
0x100447d43  xor     ecx, ecx
0x100447d45  call    _bidTraceW
0x100447d4a  test    byte ptr cs:_bidGblFlags, 2
0x100447d51  mov     esi, 9
0x100447d56  mov     ebp, 0C403h
0x100447d5b  jz      loc_100448218
0x100447d61  mov     rax, cs:off_1005E6338; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447d68  test    rax, rax
0x100447d6b  jz      loc_100448218
0x100447d71  mov     ecx, ebp; unsigned int
0x100447d73  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100447d78  mov     r8, cs:off_1005E6338; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447d7f  jmp     loc_100448203
0x100447d84  mov     rcx, cs:hLibModule; hModule
0x100447d8b  lea     rdx, aMsqagetrequest; "MSQAGetRequestStatus"
0x100447d92  call    cs:__imp_GetProcAddress
0x100447d98  mov     cs:qword_1005D8FF8, rax
0x100447d9f  test    rax, rax
0x100447da2  jnz     short loc_100447E15
0x100447da4  call    cs:__imp_GetLastError
0x100447daa  test    byte ptr cs:_bidGblFlags, 2
0x100447db1  mov     r15d, 42800h
0x100447db7  mov     ebx, eax
0x100447db9  jz      short loc_100447DDB
0x100447dbb  mov     rax, cs:off_1005E6340; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447dc2  test    rax, rax
0x100447dc5  jz      short loc_100447DDB
0x100447dc7  mov     r8, cs:off_1005E6340; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447dce  mov     r9d, ebx
0x100447dd1  mov     edx, r15d
0x100447dd4  xor     ecx, ecx
0x100447dd6  call    _bidTraceW
0x100447ddb  test    byte ptr cs:_bidGblFlags, 2
0x100447de2  mov     esi, 9
0x100447de7  mov     ebp, 0C403h
0x100447dec  jz      loc_100448218
0x100447df2  mov     rax, cs:off_1005E6348; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447df9  test    rax, rax
0x100447dfc  jz      loc_100448218
0x100447e02  mov     ecx, ebp; unsigned int
0x100447e04  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100447e09  mov     r8, cs:off_1005E6348; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447e10  jmp     loc_100448203
0x100447e15  mov     rcx, cs:hLibModule; hModule
0x100447e1c  lea     rdx, aMsqauseusernam; "MSQAUseUsernamePassword"
0x100447e23  call    cs:__imp_GetProcAddress
0x100447e29  mov     cs:qword_1005D9000, rax
0x100447e30  test    rax, rax
0x100447e33  jnz     short loc_100447EA6
0x100447e35  call    cs:__imp_GetLastError
0x100447e3b  test    byte ptr cs:_bidGblFlags, 2
0x100447e42  mov     r15d, 42C00h
0x100447e48  mov     ebx, eax
0x100447e4a  jz      short loc_100447E6C
0x100447e4c  mov     rax, cs:off_1005E6350; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447e53  test    rax, rax
0x100447e56  jz      short loc_100447E6C
0x100447e58  mov     r8, cs:off_1005E6350; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447e5f  mov     r9d, ebx
0x100447e62  mov     edx, r15d
0x100447e65  xor     ecx, ecx
0x100447e67  call    _bidTraceW
0x100447e6c  test    byte ptr cs:_bidGblFlags, 2
0x100447e73  mov     esi, 9
0x100447e78  mov     ebp, 0C403h
0x100447e7d  jz      loc_100448218
0x100447e83  mov     rax, cs:off_1005E6358; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447e8a  test    rax, rax
0x100447e8d  jz      loc_100448218
0x100447e93  mov     ecx, ebp; unsigned int
0x100447e95  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100447e9a  mov     r8, cs:off_1005E6358; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447ea1  jmp     loc_100448203
0x100447ea6  mov     rcx, cs:hLibModule; hModule
0x100447ead  lea     rdx, aMsqausewindows; "MSQAUseWindowsAuthentication"
0x100447eb4  call    cs:__imp_GetProcAddress
0x100447eba  mov     cs:qword_1005D9008, rax
0x100447ec1  test    rax, rax
0x100447ec4  jnz     short loc_100447F37
0x100447ec6  call    cs:__imp_GetLastError
0x100447ecc  test    byte ptr cs:_bidGblFlags, 2
0x100447ed3  mov     r15d, 43000h
0x100447ed9  mov     ebx, eax
0x100447edb  jz      short loc_100447EFD
0x100447edd  mov     rax, cs:off_1005E6360; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447ee4  test    rax, rax
0x100447ee7  jz      short loc_100447EFD
0x100447ee9  mov     r8, cs:off_1005E6360; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447ef0  mov     r9d, ebx
0x100447ef3  mov     edx, r15d
0x100447ef6  xor     ecx, ecx
0x100447ef8  call    _bidTraceW
0x100447efd  test    byte ptr cs:_bidGblFlags, 2
0x100447f04  mov     esi, 9
0x100447f09  mov     ebp, 0C403h
0x100447f0e  jz      loc_100448218
0x100447f14  mov     rax, cs:off_1005E6368; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447f1b  test    rax, rax
0x100447f1e  jz      loc_100448218
0x100447f24  mov     ecx, ebp; unsigned int
0x100447f26  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100447f2b  mov     r8, cs:off_1005E6368; "<SNISecMSQAInitialize|ERR|SNI> Provider"...
0x100447f32  jmp     loc_100448203
0x100447f37  mov     rcx, cs:hLibModule; hModule
0x100447f3e  lea     rdx, aMsqagetaccesst; "MSQAGetAccessToken"
0x100447f45  call    cs:__imp_GetProcAddress
0x100447f4b  mov     cs:qword_1005D8FE8, rax
0x100447f52  test    rax, rax
0x100447f55  jnz     short loc_100447FC8
0x100447f57  call    cs:__imp_GetLastError
0x100447f5d  test    byte ptr cs:_bidGblFlags, 2
0x100447f64  mov     r15d, 43400h
0x100447f6a  mov     ebx, eax
0x100447f6c  jz      short loc_100447F8E
0x100447f6e  mov     rax, cs:off_1005E6370; "<SNISecMSQAInitialize|ERR|SNI> GetProcA"...
0x100447f75  test    rax, rax
0x100447f78  jz      short loc_100447F8E
  ... truncated ...
```
