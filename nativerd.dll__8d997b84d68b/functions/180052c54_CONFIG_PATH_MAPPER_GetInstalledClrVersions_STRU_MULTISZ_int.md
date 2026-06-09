# CONFIG_PATH_MAPPER::GetInstalledClrVersions(STRU *,MULTISZ *,int)

- ea: `0x180052c54`
- end: `0x180052ec0`
- name: `?GetInstalledClrVersions@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@PEAVMULTISZ@@H@Z`
- size: `620`
- prototype: `__int64 __fastcall(struct STRU *, struct MULTISZ *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180002b20`
- `0x18004ff30`

## callees

- `0x180007de0`
- `0x180052748`
- `0x180052994`
- `0x180052acc`
- `0x180052c54`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e62`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180052e7a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180052e7a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180052d85`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180052d85`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180052e46`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180052e46`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180052cca`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180052cca`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180052e85`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180052e85`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052d0e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052d77`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052d0e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180052d77`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180052caf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180052caf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180052d62`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180052d62`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180052ceb`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x180052ceb`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180052e34`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180052e34`
- `iisutil!MakePathCanonicalizationProof` at `0x180052d1a`
- `iisutil!MakePathCanonicalizationProof` at `0x180052d1a`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180052d32`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180052d32`

## pseudocode

```c
__int64 __fastcall CONFIG_PATH_MAPPER::GetInstalledClrVersions(struct STRU *a1, struct MULTISZ *a2, int a3)
{
  signed int FxInstallPathByRegistry; // ebx
  const unsigned __int16 *Str; // rax
  const WCHAR *v8; // rax
  HANDLE FirstFileW; // rdi
  int v10; // edx
  int v11; // edx
  signed int LastError; // eax
  int v14; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v15[56]; // [rsp+28h] [rbp-D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v17[128]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset_0(v17, 0, sizeof(v17));
  STRU::STRU((STRU *)v15, v17, 0x80u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  MULTISZ::Reset(a2);
  FxInstallPathByRegistry = CONFIG_PATH_MAPPER::GetFxInstallPathByRegistry((struct STRU *)v15, a3);
  if ( FxInstallPathByRegistry >= 0 )
  {
    if ( !STRU::IsEmpty((STRU *)v15)
      || (FxInstallPathByRegistry = CONFIG_PATH_MAPPER::GetAssumedFxInstallPath((struct STRU *)v15),
          FxInstallPathByRegistry >= 0) )
    {
      Str = STRU::QueryStr((STRU *)v15);
      FxInstallPathByRegistry = MakePathCanonicalizationProof(Str, a1);
      if ( FxInstallPathByRegistry >= 0 )
      {
        FxInstallPathByRegistry = STRU::Copy((STRU *)v15, a1);
        if ( FxInstallPathByRegistry >= 0 )
        {
          FxInstallPathByRegistry = CONFIG_PATH_MAPPER::AppendTrailingSlash((struct STRU *)v15);
          if ( FxInstallPathByRegistry >= 0 )
          {
            FxInstallPathByRegistry = STRU::Append((STRU *)v15, L"*");
            if ( FxInstallPathByRegistry >= 0 )
            {
              v8 = STRU::QueryStr((STRU *)v15);
              FirstFileW = FindFirstFileW(v8, &FindFileData);
              if ( FirstFileW == (HANDLE)-1LL )
              {
                FxInstallPathByRegistry = GetLastError();
                if ( (unsigned int)(FxInstallPathByRegistry - 2) <= 1 )
                {
                  FxInstallPathByRegistry = 0;
                }
                else if ( FxInstallPathByRegistry > 0 )
                {
                  FxInstallPathByRegistry = (unsigned __int16)FxInstallPathByRegistry | 0x80070000;
                }
              }
              else
              {
                do
                {
                  if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                  {
                    v10 = FindFileData.cFileName[0] - 46;
                    if ( FindFileData.cFileName[0] == 46 )
                      v10 = FindFileData.cFileName[1];
                    if ( v10 )
                    {
                      v11 = FindFileData.cFileName[0] - 46;
                      if ( FindFileData.cFileName[0] == 46 )
                      {
                        v11 = FindFileData.cFileName[1] - 46;
                        if ( FindFileData.cFileName[1] == 46 )
                          v11 = FindFileData.cFileName[2];
                      }
                      if ( v11 )
                      {
                        v14 = 0;
                        FxInstallPathByRegistry = CONFIG_PATH_MAPPER::ContainsMachineConfig(
                                                    a1,
                                                    FindFileData.cFileName,
                                                    &v14);
                        if ( FxInstallPathByRegistry < 0 )
                          goto LABEL_29;
                        if ( v14 && !MULTISZ::Append(a2, FindFileData.cFileName) )
                        {
                          LastError = GetLastError();
                          FxInstallPathByRegistry = LastError;
                          if ( LastError <= 0 )
                            goto LABEL_29;
                          goto LABEL_28;
                        }
                      }
                    }
                  }
                }
                while ( FindNextFileW(FirstFileW, &FindFileData) );
                LastError = GetLastError();
                if ( !LastError )
                {
                  FxInstallPathByRegistry = 0;
                  goto LABEL_29;
                }
                if ( LastError != 18 )
                {
                  if ( LastError <= 0 )
                  {
                    FxInstallPathByRegistry = LastError;
                    goto LABEL_29;
                  }
LABEL_28:
                  FxInstallPathByRegistry = (unsigned __int16)LastError | 0x80070000;
                }
LABEL_29:
                FindClose(FirstFileW);
              }
            }
          }
        }
      }
    }
  }
  STRU::~STRU((STRU *)v15);
  return (unsigned int)FxInstallPathByRegistry;
}

```

## disassembly

```asm
0x180052c54  mov     [rsp-8+arg_18], rbx
0x180052c59  push    rbp
0x180052c5a  push    rsi
0x180052c5b  push    rdi
0x180052c5c  push    r14
0x180052c5e  push    r15
0x180052c60  lea     rbp, [rsp-2C0h]
0x180052c68  sub     rsp, 3C0h
0x180052c6f  mov     rax, cs:__security_cookie
0x180052c76  xor     rax, rsp
0x180052c79  mov     [rbp+2E0h+var_30], rax
0x180052c80  mov     ebx, r8d
0x180052c83  mov     r14, rdx
0x180052c86  mov     rsi, rcx
0x180052c89  xor     edx, edx; Val
0x180052c8b  mov     r8d, 100h; Size
0x180052c91  lea     rcx, [rbp+2E0h+var_130]; void *
0x180052c98  call    memset_0
0x180052c9d  mov     r8d, 80h
0x180052ca3  lea     rdx, [rbp+2E0h+var_130]
0x180052caa  lea     rcx, [rsp+3E0h+var_3B8]
0x180052caf  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180052cb5  xor     edx, edx; Val
0x180052cb7  lea     rcx, [rsp+3E0h+FindFileData]; void *
0x180052cbc  mov     r8d, 250h; Size
0x180052cc2  call    memset_0
0x180052cc7  mov     rcx, r14
0x180052cca  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180052cd0  mov     edx, ebx; int
0x180052cd2  lea     rcx, [rsp+3E0h+var_3B8]; struct STRU *
0x180052cd7  call    ?GetFxInstallPathByRegistry@CONFIG_PATH_MAPPER@@CAJPEAVSTRU@@H@Z; CONFIG_PATH_MAPPER::GetFxInstallPathByRegistry(STRU *,int)
0x180052cdc  mov     ebx, eax
0x180052cde  test    eax, eax
0x180052ce0  js      loc_180052E80
0x180052ce6  lea     rcx, [rsp+3E0h+var_3B8]
0x180052ceb  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180052cf1  test    al, al
0x180052cf3  jz      short loc_180052D09
0x180052cf5  lea     rcx, [rsp+3E0h+var_3B8]; struct STRU *
0x180052cfa  call    ?GetAssumedFxInstallPath@CONFIG_PATH_MAPPER@@CAJPEAVSTRU@@@Z; CONFIG_PATH_MAPPER::GetAssumedFxInstallPath(STRU *)
0x180052cff  mov     ebx, eax
0x180052d01  test    eax, eax
0x180052d03  js      loc_180052E80
0x180052d09  lea     rcx, [rsp+3E0h+var_3B8]
0x180052d0e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052d14  mov     rcx, rax
0x180052d17  mov     rdx, rsi
0x180052d1a  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180052d20  mov     ebx, eax
0x180052d22  test    eax, eax
0x180052d24  js      loc_180052E80
0x180052d2a  mov     rdx, rsi
0x180052d2d  lea     rcx, [rsp+3E0h+var_3B8]
0x180052d32  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180052d38  mov     ebx, eax
0x180052d3a  test    eax, eax
0x180052d3c  js      loc_180052E80
0x180052d42  lea     rcx, [rsp+3E0h+var_3B8]; struct STRU *
0x180052d47  call    ?AppendTrailingSlash@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@@Z; CONFIG_PATH_MAPPER::AppendTrailingSlash(STRU *)
0x180052d4c  mov     ebx, eax
0x180052d4e  test    eax, eax
0x180052d50  js      loc_180052E80
0x180052d56  lea     rdx, asc_180060FF4; "*"
0x180052d5d  lea     rcx, [rsp+3E0h+var_3B8]
0x180052d62  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180052d68  mov     ebx, eax
0x180052d6a  test    eax, eax
0x180052d6c  js      loc_180052E80
0x180052d72  lea     rcx, [rsp+3E0h+var_3B8]
0x180052d77  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180052d7d  mov     rcx, rax; lpFileName
0x180052d80  lea     rdx, [rsp+3E0h+FindFileData]; lpFindFileData
0x180052d85  call    cs:__imp_FindFirstFileW
0x180052d8b  mov     rdi, rax
0x180052d8e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180052d92  jnz     short loc_180052DC1
0x180052d94  call    cs:__imp_GetLastError
0x180052d9a  mov     ebx, eax
0x180052d9c  add     eax, 0FFFFFFFEh
0x180052d9f  cmp     eax, 1
0x180052da2  jbe     short loc_180052DBA
0x180052da4  test    ebx, ebx
0x180052da6  jle     loc_180052E80
0x180052dac  movzx   ebx, bx
0x180052daf  or      ebx, 80070000h
0x180052db5  jmp     loc_180052E80
0x180052dba  xor     ebx, ebx
0x180052dbc  jmp     loc_180052E80
0x180052dc1  mov     r15d, 2Eh ; '.'
0x180052dc7  test    byte ptr [rsp+3E0h+FindFileData.dwFileAttributes], 10h
0x180052dcc  jz      short loc_180052E3E
0x180052dce  movzx   edx, [rbp+2E0h+FindFileData.cFileName]
0x180052dd2  sub     edx, r15d
0x180052dd5  jnz     short loc_180052DE2
0x180052dd7  movzx   edx, [rbp+2E0h+FindFileData.cFileName+2]
0x180052ddb  xor     eax, eax
0x180052ddd  movzx   ecx, ax
0x180052de0  sub     edx, ecx
0x180052de2  test    edx, edx
0x180052de4  jz      short loc_180052E3E
0x180052de6  movzx   edx, [rbp+2E0h+FindFileData.cFileName]
0x180052dea  sub     edx, r15d
0x180052ded  jnz     short loc_180052E03
0x180052def  movzx   edx, [rbp+2E0h+FindFileData.cFileName+2]
0x180052df3  sub     edx, r15d
0x180052df6  jnz     short loc_180052E03
0x180052df8  movzx   edx, [rbp+2E0h+FindFileData.cFileName+4]
0x180052dfc  xor     eax, eax
0x180052dfe  movzx   ecx, ax
0x180052e01  sub     edx, ecx
0x180052e03  test    edx, edx
0x180052e05  jz      short loc_180052E3E
0x180052e07  lea     r8, [rsp+3E0h+var_3C0]; int *
0x180052e0c  mov     [rsp+3E0h+var_3C0], 0
0x180052e14  lea     rdx, [rbp+2E0h+FindFileData.cFileName]; unsigned __int16 *
0x180052e18  mov     rcx, rsi; struct STRU *
0x180052e1b  call    ?ContainsMachineConfig@CONFIG_PATH_MAPPER@@CAJPEAVSTRU@@PEBGPEAH@Z; CONFIG_PATH_MAPPER::ContainsMachineConfig(STRU *,ushort const *,int *)
0x180052e20  mov     ebx, eax
0x180052e22  test    eax, eax
0x180052e24  js      short loc_180052E77
0x180052e26  cmp     [rsp+3E0h+var_3C0], 0
0x180052e2b  jz      short loc_180052E3E
0x180052e2d  lea     rdx, [rbp+2E0h+FindFileData.cFileName]
0x180052e31  mov     rcx, r14
0x180052e34  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180052e3a  test    eax, eax
0x180052e3c  jz      short loc_180052E62
0x180052e3e  lea     rdx, [rsp+3E0h+FindFileData]; lpFindFileData
0x180052e43  mov     rcx, rdi; hFindFile
0x180052e46  call    cs:__imp_FindNextFileW
0x180052e4c  test    eax, eax
0x180052e4e  jnz     loc_180052DC7
0x180052e54  call    cs:__imp_GetLastError
0x180052e5a  test    eax, eax
0x180052e5c  jnz     short loc_180052EB3
0x180052e5e  xor     ebx, ebx
0x180052e60  jmp     short loc_180052E77
0x180052e62  call    cs:__imp_GetLastError
0x180052e68  mov     ebx, eax
0x180052e6a  test    eax, eax
0x180052e6c  jle     short loc_180052E77
0x180052e6e  movzx   ebx, ax
0x180052e71  or      ebx, 80070000h
0x180052e77  mov     rcx, rdi; hFindFile
0x180052e7a  call    cs:__imp_FindClose
0x180052e80  lea     rcx, [rsp+3E0h+var_3B8]
0x180052e85  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180052e8b  mov     eax, ebx
0x180052e8d  mov     rcx, [rbp+2E0h+var_30]
0x180052e94  xor     rcx, rsp; StackCookie
0x180052e97  call    __security_check_cookie
0x180052e9c  mov     rbx, [rsp+3E0h+arg_18]
0x180052ea4  add     rsp, 3C0h
0x180052eab  pop     r15
0x180052ead  pop     r14
0x180052eaf  pop     rdi
0x180052eb0  pop     rsi
0x180052eb1  pop     rbp
0x180052eb2  retn
0x180052eb3  cmp     eax, 12h
0x180052eb6  jz      short loc_180052E77
0x180052eb8  test    eax, eax
0x180052eba  jg      short loc_180052E6E
0x180052ebc  mov     ebx, eax
0x180052ebe  jmp     short loc_180052E77
```
