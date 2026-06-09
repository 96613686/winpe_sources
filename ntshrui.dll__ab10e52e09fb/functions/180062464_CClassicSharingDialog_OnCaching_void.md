# CClassicSharingDialog::_OnCaching(void)

- ea: `0x180062464`
- end: `0x18006257f`
- name: `?_OnCaching@CClassicSharingDialog@@AEAAJXZ`
- size: `283`
- prototype: `__int64 __fastcall(CClassicSharingDialog *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800608d0`

## callees

- `0x1800098dc`
- `0x180011df0`
- `0x180021a60`
- `0x180062428`
- `0x180062464`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180062561`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180062561`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180062496`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180062496`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006247a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006247a`
- `netutils!NetApiBufferFree` at `0x180062512`
- `netutils!NetApiBufferFree` at `0x180062512`
- `srvcli!NetShareGetInfo` at `0x1800624f4`
- `srvcli!NetShareGetInfo` at `0x1800624f4`

## string_xrefs

- `0x18006248c`: `CacheSettingsDlg`
- `0x180062473`: `FileMgmt.dll`

## pseudocode

```c
__int64 __fastcall CClassicSharingDialog::_OnCaching(CClassicSharingDialog *this)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rbp
  CShareInfo *v5; // rbx
  unsigned __int16 *Netname; // rax
  WCHAR *ServerName; // rax
  LPWSTR v8; // r10
  LPBYTE v9; // rcx
  __int64 v10; // rcx
  unsigned int Error; // ebx
  __int64 v12; // rax
  bool v13; // zf
  int v15; // [rsp+48h] [rbp+10h] BYREF
  LPBYTE bufptr; // [rsp+50h] [rbp+18h] BYREF

  LibraryW = LoadLibraryW(L"FileMgmt.dll");
  v3 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "CacheSettingsDlg");
    if ( ProcAddress )
    {
      v5 = (CShareInfo *)*((_QWORD *)this + 3);
      if ( *((_DWORD *)v5 + 8) == -1 )
      {
        *((_DWORD *)v5 + 8) = 0;
        if ( *((_DWORD *)v5 + 5) != 1 )
        {
          Netname = CShareInfo::GetNetname(v5);
          if ( Netname )
          {
            if ( *Netname )
            {
              bufptr = 0;
              ServerName = CShareInfo::GetServerName(v5);
              if ( !NetShareGetInfo(ServerName, v8, 0x3EDu, &bufptr) )
              {
                v9 = bufptr;
                if ( bufptr )
                {
                  *((_DWORD *)v5 + 8) = *(_DWORD *)bufptr & 0x2030;
                  NetApiBufferFree(v9);
                }
              }
            }
          }
        }
      }
      v10 = *(_QWORD *)this;
      v15 = *((_DWORD *)v5 + 8);
      Error = ((__int64 (__fastcall *)(__int64, int *))ProcAddress)(v10, &v15);
      if ( !Error )
      {
        v12 = *((_QWORD *)this + 3);
        v13 = *(_DWORD *)(v12 + 20) == 1;
        *(_DWORD *)(v12 + 32) = v15;
        if ( !v13 )
          *(_DWORD *)(v12 + 20) = 3;
        CClassicSharingDialog::_MarkPageDirty(this);
      }
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    FreeLibrary(v3);
  }
  else
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x180062464  mov     [rsp+arg_0], rbx
0x180062469  push    rbp
0x18006246a  push    rsi
0x18006246b  push    rdi
0x18006246c  sub     rsp, 20h
0x180062470  mov     rdi, rcx
0x180062473  lea     rcx, aFilemgmtDll; "FileMgmt.dll"
0x18006247a  call    cs:__imp_LoadLibraryW
0x180062480  mov     rsi, rax
0x180062483  test    rax, rax
0x180062486  jz      loc_180062569
0x18006248c  lea     rdx, aCachesettingsd; "CacheSettingsDlg"
0x180062493  mov     rcx, rax; hModule
0x180062496  call    cs:__imp_GetProcAddress
0x18006249c  mov     rbp, rax
0x18006249f  test    rax, rax
0x1800624a2  jz      loc_180062557
0x1800624a8  mov     rbx, [rdi+18h]
0x1800624ac  cmp     dword ptr [rbx+20h], 0FFFFFFFFh
0x1800624b0  jnz     short loc_180062518
0x1800624b2  mov     dword ptr [rbx+20h], 0
0x1800624b9  cmp     dword ptr [rbx+14h], 1
0x1800624bd  jz      short loc_180062518
0x1800624bf  mov     rcx, rbx; this
0x1800624c2  call    ?GetNetname@CShareInfo@@QEAAPEAGXZ; CShareInfo::GetNetname(void)
0x1800624c7  mov     r10, rax
0x1800624ca  test    rax, rax
0x1800624cd  jz      short loc_180062518
0x1800624cf  xor     ecx, ecx
0x1800624d1  cmp     cx, [rax]
0x1800624d4  jz      short loc_180062518
0x1800624d6  mov     [rsp+38h+bufptr], rcx
0x1800624db  mov     rcx, rbx; this
0x1800624de  call    ?GetServerName@CShareInfo@@QEAAPEAGXZ; CShareInfo::GetServerName(void)
0x1800624e3  mov     rcx, rax; servername
0x1800624e6  lea     r9, [rsp+38h+bufptr]; bufptr
0x1800624eb  mov     rdx, r10; netname
0x1800624ee  mov     r8d, 3EDh; level
0x1800624f4  call    cs:__imp_NetShareGetInfo
0x1800624fa  test    eax, eax
0x1800624fc  jnz     short loc_180062518
0x1800624fe  mov     rcx, [rsp+38h+bufptr]; Buffer
0x180062503  test    rcx, rcx
0x180062506  jz      short loc_180062518
0x180062508  mov     eax, [rcx]
0x18006250a  and     eax, 2030h
0x18006250f  mov     [rbx+20h], eax
0x180062512  call    cs:__imp_NetApiBufferFree
0x180062518  mov     eax, [rbx+20h]
0x18006251b  lea     rdx, [rsp+38h+arg_8]
0x180062520  mov     rcx, [rdi]
0x180062523  mov     [rsp+38h+arg_8], eax
0x180062527  mov     rax, rbp
0x18006252a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006252f  mov     ebx, eax
0x180062531  test    eax, eax
0x180062533  jnz     short loc_18006255E
0x180062535  mov     rax, [rdi+18h]
0x180062539  mov     ecx, [rsp+38h+arg_8]
0x18006253d  cmp     dword ptr [rax+14h], 1
0x180062541  mov     [rax+20h], ecx
0x180062544  jz      short loc_18006254D
0x180062546  mov     dword ptr [rax+14h], 3
0x18006254d  mov     rcx, rdi; this
0x180062550  call    ?_MarkPageDirty@CClassicSharingDialog@@AEAAJXZ; CClassicSharingDialog::_MarkPageDirty(void)
0x180062555  jmp     short loc_18006255E
0x180062557  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006255c  mov     ebx, eax
0x18006255e  mov     rcx, rsi; hLibModule
0x180062561  call    cs:__imp_FreeLibrary
0x180062567  jmp     short loc_180062570
0x180062569  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006256e  mov     ebx, eax
0x180062570  mov     eax, ebx
0x180062572  mov     rbx, [rsp+38h+arg_0]
0x180062577  add     rsp, 20h
0x18006257b  pop     rdi
0x18006257c  pop     rsi
0x18006257d  pop     rbp
0x18006257e  retn
```
