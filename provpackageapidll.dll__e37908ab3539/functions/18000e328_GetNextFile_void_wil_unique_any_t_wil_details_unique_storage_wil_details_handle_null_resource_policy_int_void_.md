# GetNextFile(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>> &,ushort const *,_WIM_FILE_FIND_DATA *)

- ea: `0x18000e328`
- end: `0x18000e4a8`
- name: `?GetNextFile@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAU_WIM_FILE_FIND_DATA@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800078e8`
- `0x18000d350`
- `0x18000d708`
- `0x180017898`

## callees

- `0x180006014`
- `0x18000e328`
- `0x18000e904`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e378`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e429`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e429`
- `WIMGAPI!WIMFindNextImageFile` at `0x18000e410`
- `WIMGAPI!WIMFindNextImageFile` at `0x18000e410`
- `WIMGAPI!WIMFindFirstImageFileEx` at `0x18000e34f`
- `WIMGAPI!WIMFindFirstImageFileEx` at `0x18000e34f`
- `WIMGAPI!WIMCloseHandle` at `0x18000e370`
- `WIMGAPI!WIMCloseHandle` at `0x18000e370`

## pseudocode

```c
__int64 __fastcall GetNextFile(__int64 a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 ImageFile; // rax
  __int64 v7; // r14
  __int64 v8; // rbp
  DWORD LastError; // ebx
  signed int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // edi
  __int64 result; // rax
  signed int v14; // eax

  if ( *a2 )
    goto LABEL_11;
  ImageFile = WIMFindFirstImageFileEx(a1, a3, 672, a4);
  v7 = *a2;
  v8 = ImageFile;
  if ( (unsigned __int64)(*a2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    WIMCloseHandle(v7);
    SetLastError(LastError);
  }
  *a2 = v8;
  if ( v8 )
  {
    while ( 1 )
    {
      result = IsDotDirectory((const unsigned __int16 *)(a4 + 44));
      if ( !(_DWORD)result )
        break;
LABEL_11:
      if ( !(unsigned int)WIMFindNextImageFile(*a2, a4) )
      {
        v14 = GetLastError();
        v11 = v14;
        if ( v14 > 0 )
          v11 = (unsigned __int16)v14 | 0x80070000;
        v12 = -2147024637;
        if ( v11 == -2147024637 )
        {
          ProvPackageLog(
            0,
            L"%hs (%hs:%d): %s",
            "GetNextFile",
            "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
            344,
            L"No more files to find");
          return v12;
        }
        ProvPackageLog(
          3,
          L"%hs (%hs:%d) - 0x%08x:",
          "GetNextFile",
          "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
          347,
          v11);
        ProvPackageLog(3, L"    Failed to find next file");
        return v11;
      }
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    v12 = -2147024893;
    if ( v11 == -2147024893 )
    {
      ProvPackageLog(
        0,
        L"%hs (%hs:%d): %s",
        "GetNextFile",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
        323,
        L"File not found");
      return v12;
    }
    else
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "GetNextFile",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
        326,
        v11);
      ProvPackageLog(3, L"    Failed to find first file");
      return v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e328  push    rbx
0x18000e32a  push    rbp
0x18000e32b  push    rsi
0x18000e32c  push    rdi
0x18000e32d  push    r14
0x18000e32f  sub     rsp, 30h
0x18000e333  cmp     qword ptr [rdx], 0
0x18000e337  mov     rdi, r9
0x18000e33a  mov     rax, r8
0x18000e33d  mov     rsi, rdx
0x18000e340  jnz     loc_18000E40A
0x18000e346  mov     r8d, 2A0h
0x18000e34c  mov     rdx, rax
0x18000e34f  call    cs:__imp_WIMFindFirstImageFileEx
0x18000e355  mov     r14, [rsi]
0x18000e358  mov     rbp, rax
0x18000e35b  lea     r8, [r14-1]
0x18000e35f  cmp     r8, 0FFFFFFFFFFFFFFFDh
0x18000e363  ja      short loc_18000E37E
0x18000e365  call    cs:__imp_GetLastError
0x18000e36b  mov     rcx, r14
0x18000e36e  mov     ebx, eax
0x18000e370  call    cs:__imp_WIMCloseHandle
0x18000e376  mov     ecx, ebx; dwErrCode
0x18000e378  call    cs:__imp_SetLastError
0x18000e37e  mov     [rsi], rbp
0x18000e381  test    rbp, rbp
0x18000e384  jnz     loc_18000E41A
0x18000e38a  call    cs:__imp_GetLastError
0x18000e390  mov     ebx, eax
0x18000e392  test    eax, eax
0x18000e394  jle     short loc_18000E39F
0x18000e396  movzx   ebx, ax
0x18000e399  or      ebx, 80070000h
0x18000e39f  mov     edi, 80070003h
0x18000e3a4  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e3ab  lea     r8, aGetnextfile; "GetNextFile"
0x18000e3b2  cmp     ebx, edi
0x18000e3b4  jnz     short loc_18000E3DF
0x18000e3b6  lea     rcx, aFileNotFound; "File not found"
0x18000e3bd  mov     [rsp+58h+var_30], rcx
0x18000e3c2  mov     [rsp+58h+var_38], 143h
0x18000e3ca  lea     rdx, aHsHsDS; "%hs (%hs:%d): %s"
0x18000e3d1  xor     ecx, ecx
0x18000e3d3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e3d8  mov     eax, edi
0x18000e3da  jmp     loc_18000E49D
0x18000e3df  mov     edi, 3
0x18000e3e4  mov     dword ptr [rsp+58h+var_30], ebx
0x18000e3e8  mov     ecx, edi
0x18000e3ea  mov     [rsp+58h+var_38], 146h
0x18000e3f2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e3f9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e3fe  lea     rdx, aFailedToFindFi; "    Failed to find first file"
0x18000e405  jmp     loc_18000E494
0x18000e40a  mov     rcx, [rsi]
0x18000e40d  mov     rdx, rdi
0x18000e410  call    cs:__imp_WIMFindNextImageFile
0x18000e416  test    eax, eax
0x18000e418  jz      short loc_18000E429
0x18000e41a  lea     rcx, [rdi+2Ch]; unsigned __int16 *
0x18000e41e  call    ?IsDotDirectory@@YAHPEBG@Z; IsDotDirectory(ushort const *)
0x18000e423  test    eax, eax
0x18000e425  jnz     short loc_18000E40A
0x18000e427  jmp     short loc_18000E49D
0x18000e429  call    cs:__imp_GetLastError
0x18000e42f  mov     ebx, eax
0x18000e431  test    eax, eax
0x18000e433  jle     short loc_18000E43E
0x18000e435  movzx   ebx, ax
0x18000e438  or      ebx, 80070000h
0x18000e43e  mov     edi, 80070103h
0x18000e443  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e44a  lea     r8, aGetnextfile; "GetNextFile"
0x18000e451  cmp     ebx, edi
0x18000e453  jnz     short loc_18000E46E
0x18000e455  lea     rcx, aNoMoreFilesToF; "No more files to find"
0x18000e45c  mov     [rsp+58h+var_30], rcx
0x18000e461  mov     [rsp+58h+var_38], 158h
0x18000e469  jmp     loc_18000E3CA
0x18000e46e  mov     edi, 3
0x18000e473  mov     dword ptr [rsp+58h+var_30], ebx
0x18000e477  mov     ecx, edi
0x18000e479  mov     [rsp+58h+var_38], 15Bh
0x18000e481  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e488  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e48d  lea     rdx, aFailedToFindNe; "    Failed to find next file"
0x18000e494  mov     ecx, edi
0x18000e496  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e49b  mov     eax, ebx
0x18000e49d  add     rsp, 30h
0x18000e4a1  pop     r14
0x18000e4a3  pop     rdi
0x18000e4a4  pop     rsi
0x18000e4a5  pop     rbp
0x18000e4a6  pop     rbx
0x18000e4a7  retn
```
