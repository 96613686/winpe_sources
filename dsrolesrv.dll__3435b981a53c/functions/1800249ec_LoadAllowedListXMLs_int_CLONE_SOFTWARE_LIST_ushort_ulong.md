# LoadAllowedListXMLs(int,CLONE_SOFTWARE_LIST *,ushort *,ulong)

- ea: `0x1800249ec`
- end: `0x180024c28`
- name: `?LoadAllowedListXMLs@@YAKHPEAVCLONE_SOFTWARE_LIST@@PEAGK@Z`
- size: `572`
- prototype: `__int64 __fastcall(int, struct CLONE_SOFTWARE_LIST *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002477c`

## callees

- `0x18001cd60`
- `0x180023f6c`
- `0x1800249ec`
- `0x18002522c`
- `0x180026428`
- `0x180026ce8`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180024acf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180024b43`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180024acf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180024b43`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180024b88`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180024b88`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180024ae5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180024b70`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180024c1b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180024ae5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180024b70`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180024c1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180024bae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180024bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bb8`

## string_xrefs

- `0x180024bf6`: `uri:microsoft.com:schemas:CustomDCCloneAllowList`

## pseudocode

```c
__int64 __fastcall LoadAllowedListXMLs(int a1, struct CLONE_SOFTWARE_LIST *a2, unsigned __int16 *a3, int a4)
{
  __int64 v8; // rdi
  unsigned int DefaultCloneConfigPath; // ebx
  HANDLE FirstFileW; // rax
  UINT SystemDirectoryW; // eax
  unsigned __int64 v12; // rdx
  DWORD LastError; // eax
  _QWORD v14[2]; // [rsp+30h] [rbp-6E8h] BYREF
  int v15; // [rsp+40h] [rbp-6D8h]
  __int128 FileInformation; // [rsp+48h] [rbp-6D0h] BYREF
  __int128 v17; // [rsp+58h] [rbp-6C0h]
  unsigned int v18; // [rsp+68h] [rbp-6B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-6A8h] BYREF
  WCHAR Buffer; // [rsp+2C0h] [rbp-458h] BYREF
  _BYTE v21[526]; // [rsp+2C2h] [rbp-456h] BYREF
  WCHAR FileName[264]; // [rsp+4D0h] [rbp-248h] BYREF

  v14[0] = &ALLOWLIST_PARSER::`vftable';
  v14[1] = a2;
  v15 = 0;
  Buffer = 0;
  memset_0(v21, 0, 0x206u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a4 )
    return 122;
  v8 = -1;
  *a3 = 0;
  DefaultCloneConfigPath = GetDefaultCloneConfigPath(FileName);
  if ( !DefaultCloneConfigPath )
  {
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    v8 = (__int64)FirstFileW;
    if ( FirstFileW == (HANDLE)-1LL
      || (FindClose(FirstFileW),
          v8 = -1,
          (DefaultCloneConfigPath = LoadCloneXML(FileName, 0, 0, (struct CloneXMLParser *)v14)) == 0) )
    {
      DefaultCloneConfigPath = GetCustomAllowListFile(a3, 2 * a4);
      if ( !DefaultCloneConfigPath )
      {
        if ( a1 )
        {
          v8 = (__int64)FindFirstFileW(a3, &FindFileData);
          if ( v8 != -1 )
          {
            FileInformation = 0;
            v17 = 0;
            v18 = 0;
            FindClose((HANDLE)v8);
            v8 = -1;
            if ( !GetFileAttributesExW(a3, GetFileExInfoStandard, &FileInformation) || HIDWORD(v17) || v18 > 4 )
            {
              SystemDirectoryW = GetSystemDirectoryW(&Buffer, 0x104u);
              if ( SystemDirectoryW )
              {
                if ( SystemDirectoryW >= 0x104 )
                {
                  DefaultCloneConfigPath = 122;
                  goto LABEL_18;
                }
                LastError = StringCchCatW(&Buffer, v12, L"\\CustomDCCloneAllowListSchema.xsd");
              }
              else
              {
                LastError = GetLastError();
              }
              DefaultCloneConfigPath = LastError;
LABEL_18:
              if ( !DefaultCloneConfigPath )
              {
                v15 = 1;
                DefaultCloneConfigPath = LoadCloneXML(
                                           a3,
                                           &Buffer,
                                           (OLECHAR *)L"uri:microsoft.com:schemas:CustomDCCloneAllowList",
                                           (struct CloneXMLParser *)v14);
              }
            }
          }
        }
      }
    }
  }
  if ( v8 != -1 )
    FindClose((HANDLE)v8);
  return DefaultCloneConfigPath;
}

```

## disassembly

```asm
0x1800249ec  mov     [rsp+arg_0], rbx
0x1800249f1  push    rsi
0x1800249f2  push    rdi
0x1800249f3  push    r12
0x1800249f5  push    r14
0x1800249f7  push    r15
0x1800249f9  sub     rsp, 6F0h
0x180024a00  mov     rax, cs:__security_cookie
0x180024a07  xor     rax, rsp
0x180024a0a  mov     [rsp+718h+var_38], rax
0x180024a12  mov     r14d, r9d
0x180024a15  mov     rsi, r8
0x180024a18  mov     r15d, ecx
0x180024a1b  lea     rax, ??_7ALLOWLIST_PARSER@@6B@; const ALLOWLIST_PARSER::`vftable'
0x180024a22  mov     [rsp+718h+var_6E8], rax
0x180024a27  mov     [rsp+718h+var_6E0], rdx
0x180024a2c  mov     [rsp+718h+var_6D8], 0
0x180024a34  xor     eax, eax
0x180024a36  mov     [rsp+718h+Buffer], ax
0x180024a3e  xor     edx, edx; Val
0x180024a40  mov     r8d, 206h; Size
0x180024a46  lea     rcx, [rsp+718h+var_456]; void *
0x180024a4e  call    memset_0
0x180024a53  xor     edx, edx; Val
0x180024a55  mov     r8d, 250h; Size
0x180024a5b  lea     rcx, [rsp+718h+FindFileData]; void *
0x180024a60  call    memset_0
0x180024a65  test    r14d, r14d
0x180024a68  jnz     short loc_180024A96
0x180024a6a  lea     eax, [r14+7Ah]
0x180024a6e  mov     rcx, [rsp+718h+var_38]
0x180024a76  xor     rcx, rsp; StackCookie
0x180024a79  call    __security_check_cookie
0x180024a7e  mov     rbx, [rsp+718h+arg_0]
0x180024a86  add     rsp, 6F0h
0x180024a8d  pop     r15
0x180024a8f  pop     r14
0x180024a91  pop     r12
0x180024a93  pop     rdi
0x180024a94  pop     rsi
0x180024a95  retn
0x180024a96  or      r12, 0FFFFFFFFFFFFFFFFh
0x180024a9a  mov     rdi, r12
0x180024a9d  mov     [rsp+718h+var_6F0], r12
0x180024aa2  xor     eax, eax
0x180024aa4  mov     [rsi], ax
0x180024aa7  lea     rcx, [rsp+718h+FileName]; unsigned __int16 *
0x180024aaf  call    ?GetDefaultCloneConfigPath@@YAKPEAG@Z; GetDefaultCloneConfigPath(ushort *)
0x180024ab4  mov     ebx, eax
0x180024ab6  mov     [rsp+718h+var_6F8], eax
0x180024aba  test    eax, eax
0x180024abc  jnz     loc_180024C13
0x180024ac2  lea     rdx, [rsp+718h+FindFileData]; lpFindFileData
0x180024ac7  lea     rcx, [rsp+718h+FileName]; lpFileName
0x180024acf  call    cs:__imp_FindFirstFileW
0x180024ad5  mov     rdi, rax
0x180024ad8  mov     [rsp+718h+var_6F0], rax
0x180024add  cmp     rax, r12
0x180024ae0  jz      short loc_180024B18
0x180024ae2  mov     rcx, rax; hFindFile
0x180024ae5  call    cs:__imp_FindClose
0x180024aeb  mov     rdi, r12
0x180024aee  mov     [rsp+718h+var_6F0], r12
0x180024af3  lea     r9, [rsp+718h+var_6E8]; struct CloneXMLParser *
0x180024af8  xor     r8d, r8d; OLECHAR *
0x180024afb  xor     edx, edx; OLECHAR *
0x180024afd  lea     rcx, [rsp+718h+FileName]; psz
0x180024b05  call    ?LoadCloneXML@@YAJPEAG00PEAVCloneXMLParser@@@Z; LoadCloneXML(ushort *,ushort *,ushort *,CloneXMLParser *)
0x180024b0a  mov     ebx, eax
0x180024b0c  mov     [rsp+718h+var_6F8], eax
0x180024b10  test    eax, eax
0x180024b12  jnz     loc_180024C13
0x180024b18  lea     edx, [r14+r14]; unsigned int
0x180024b1c  mov     rcx, rsi; unsigned __int16 *
0x180024b1f  call    ?GetCustomAllowListFile@@YAKPEAGK@Z; GetCustomAllowListFile(ushort *,ulong)
0x180024b24  mov     ebx, eax
0x180024b26  mov     [rsp+718h+var_6F8], eax
0x180024b2a  test    eax, eax
0x180024b2c  jnz     loc_180024C13
0x180024b32  test    r15d, r15d
0x180024b35  jz      loc_180024C13
0x180024b3b  lea     rdx, [rsp+718h+FindFileData]; lpFindFileData
0x180024b40  mov     rcx, rsi; lpFileName
0x180024b43  call    cs:__imp_FindFirstFileW
0x180024b49  mov     rdi, rax
0x180024b4c  mov     [rsp+718h+var_6F0], rax
0x180024b51  cmp     rax, r12
0x180024b54  jz      loc_180024C13
0x180024b5a  xorps   xmm0, xmm0
0x180024b5d  xor     eax, eax
0x180024b5f  movups  [rsp+718h+FileInformation], xmm0
0x180024b64  movups  [rsp+718h+var_6C0], xmm0
0x180024b69  mov     [rsp+718h+var_6B0], eax
0x180024b6d  mov     rcx, rdi; hFindFile
0x180024b70  call    cs:__imp_FindClose
0x180024b76  mov     rdi, r12
0x180024b79  mov     [rsp+718h+var_6F0], r12
0x180024b7e  lea     r8, [rsp+718h+FileInformation]; lpFileInformation
0x180024b83  xor     edx, edx; fInfoLevelId
0x180024b85  mov     rcx, rsi; lpFileName
0x180024b88  call    cs:__imp_GetFileAttributesExW
0x180024b8e  test    eax, eax
0x180024b90  jz      short loc_180024B9F
0x180024b92  cmp     dword ptr [rsp+718h+var_6C0+0Ch], ebx
0x180024b96  jnz     short loc_180024B9F
0x180024b98  cmp     [rsp+718h+var_6B0], 4
0x180024b9d  jbe     short loc_180024C13
0x180024b9f  mov     ebx, 104h
0x180024ba4  mov     edx, ebx; uSize
0x180024ba6  lea     rcx, [rsp+718h+Buffer]; lpBuffer
0x180024bae  call    cs:__imp_GetSystemDirectoryW
0x180024bb4  test    eax, eax
0x180024bb6  jnz     short loc_180024BC0
0x180024bb8  call    cs:__imp_GetLastError
0x180024bbe  jmp     short loc_180024BDF
0x180024bc0  cmp     eax, ebx
0x180024bc2  jb      short loc_180024BCB
0x180024bc4  mov     ebx, 7Ah ; 'z'
0x180024bc9  jmp     short loc_180024BE1
0x180024bcb  lea     r8, aCustomdcclonea_0; "\\CustomDCCloneAllowListSchema.xsd"
0x180024bd2  lea     rcx, [rsp+718h+Buffer]; unsigned __int16 *
0x180024bda  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024bdf  mov     ebx, eax
0x180024be1  mov     [rsp+718h+var_6F8], ebx
0x180024be5  test    ebx, ebx
0x180024be7  jnz     short loc_180024C13
0x180024be9  mov     [rsp+718h+var_6D8], 1
0x180024bf1  lea     r9, [rsp+718h+var_6E8]; struct CloneXMLParser *
0x180024bf6  lea     r8, aUriMicrosoftCo; "uri:microsoft.com:schemas:CustomDCClone"...
0x180024bfd  lea     rdx, [rsp+718h+Buffer]; OLECHAR *
0x180024c05  mov     rcx, rsi; psz
0x180024c08  call    ?LoadCloneXML@@YAJPEAG00PEAVCloneXMLParser@@@Z; LoadCloneXML(ushort *,ushort *,ushort *,CloneXMLParser *)
0x180024c0d  mov     ebx, eax
0x180024c0f  mov     [rsp+718h+var_6F8], eax
0x180024c13  cmp     rdi, r12
0x180024c16  jz      short loc_180024C21
0x180024c18  mov     rcx, rdi; hFindFile
0x180024c1b  call    cs:__imp_FindClose
0x180024c21  mov     eax, ebx
0x180024c23  jmp     loc_180024A6E
0x18002c624  push    rbp
0x18002c626  sub     rsp, 20h
0x18002c62a  mov     rbp, rdx
0x18002c62d  mov     rcx, [rbp+28h]; hFindFile
0x18002c631  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c635  jz      short loc_18002C63E
0x18002c637  call    cs:__imp_FindClose
0x18002c63d  nop
0x18002c63e  add     rsp, 20h
0x18002c642  pop     rbp
0x18002c643  retn
```
