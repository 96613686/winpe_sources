# InstallColorProfileW

- ea: `0x180044ab0`
- end: `0x180044ca1`
- name: `InstallColorProfileW`
- size: `497`
- prototype: `BOOL __stdcall(PCWSTR pMachineName, PCWSTR pProfileName)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18002435c`
- `0x180044a30`
- `0x180044ed0`

## callees

- `0x180008bf0`
- `0x180008cc0`
- `0x18001e5ac`
- `0x180023a4c`
- `0x180029f14`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x180044ab0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180044c6b`
- `ntdll!EtwEventWrite` at `0x180044c6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044c7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044c7a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180044c10`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180044c10`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180044c26`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180044c26`

## pseudocode

```c
BOOL __stdcall InstallColorProfileW(PCWSTR pMachineName, PCWSTR pProfileName)
{
  BOOL v4; // esi
  const unsigned __int16 *FilenameFromPath; // r14
  DWORD v6; // ecx
  __int64 v7; // rbx
  __int64 v8; // rax
  int v9; // r8d
  DWORD pcbNeeded; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR v12; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h]
  int v14; // [rsp+44h] [rbp-BCh]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcbNeeded = 0;
  memset_0(FileName, 0, 0x208u);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
    tlgWriteTransfer_EventWriteTransfer(&dword_18009E080, byte_180090A69, 0, 0, 2, &v12, pcbNeeded);
  if ( pProfileName && !pMachineName )
  {
    v4 = 0;
    FilenameFromPath = (const unsigned __int16 *)GetFilenameFromPath(pProfileName);
    if ( FilenameFromPath )
    {
      pcbNeeded = 520;
      if ( !(unsigned int)InternalGetColorDirectory(0, FileName, &pcbNeeded) )
        return v4;
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( FileName[v8] );
      if ( FileName[v8 - 1] == 92 || (v9 = StringCchCatW(FileName, 0x104u, gszBackslash), v9 >= 0) )
      {
        v9 = StringCchCatW(FileName, 0x104u, FilenameFromPath);
        if ( v9 >= 0 )
        {
          if ( GetFileAttributesW(FileName) != -1 || CopyFileW(pProfileName, FileName, 0) )
          {
            v4 = 1;
            do
              ++v7;
            while ( pProfileName[v7] );
            v12 = pProfileName;
            v13 = 2 * v7 + 2;
            v14 = 0;
            EtwEventWrite(g_etwHandle, INSTALL_PROFILE, 1, &v12);
          }
          return v4;
        }
      }
      v6 = (unsigned __int16)v9;
      if ( (v9 & 0x1FFF0000) != 0x70000 )
        v6 = v9;
    }
    else
    {
      v6 = 87;
    }
    SetLastError(v6);
    return v4;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180044ab0  push    rbp
0x180044ab2  push    rbx
0x180044ab3  push    rsi
0x180044ab4  push    rdi
0x180044ab5  push    r14
0x180044ab7  push    r15
0x180044ab9  lea     rbp, [rsp-188h]
0x180044ac1  sub     rsp, 288h
0x180044ac8  mov     rax, cs:__security_cookie
0x180044acf  xor     rax, rsp
0x180044ad2  mov     [rbp+1B0h+var_40], rax
0x180044ad9  mov     rdi, rdx
0x180044adc  mov     rbx, rcx
0x180044adf  xor     r15d, r15d
0x180044ae2  lea     rcx, [rsp+2B0h+FileName]; void *
0x180044ae7  xor     edx, edx; Val
0x180044ae9  mov     [rsp+2B0h+pcbNeeded], r15d
0x180044aee  mov     r8d, 208h; Size
0x180044af4  call    memset_0
0x180044af9  mov     eax, cs:dword_18009E080
0x180044aff  cmp     eax, 5
0x180044b02  jbe     short loc_180044B49
0x180044b04  mov     rdx, 200000000000h
0x180044b0e  lea     rcx, dword_18009E080
0x180044b15  call    _tlgKeywordOn
0x180044b1a  test    al, al
0x180044b1c  jz      short loc_180044B49
0x180044b1e  lea     rax, [rsp+2B0h+var_278]
0x180044b23  xor     r9d, r9d
0x180044b26  mov     [rsp+2B0h+var_288], rax
0x180044b2b  lea     rdx, byte_180090A69
0x180044b32  xor     r8d, r8d
0x180044b35  mov     [rsp+2B0h+var_290], 2
0x180044b3d  lea     rcx, dword_18009E080
0x180044b44  call    _tlgWriteTransfer_EventWriteTransfer
0x180044b49  test    rdi, rdi
0x180044b4c  jz      loc_180044C75
0x180044b52  test    rbx, rbx
0x180044b55  jnz     loc_180044C75
0x180044b5b  mov     rcx, rdi; lpStringSource
0x180044b5e  mov     esi, r15d
0x180044b61  call    GetFilenameFromPath
0x180044b66  mov     r14, rax
0x180044b69  test    rax, rax
0x180044b6c  jnz     short loc_180044B7C
0x180044b6e  lea     ecx, [rbx+57h]; dwErrCode
0x180044b71  call    cs:__imp_SetLastError
0x180044b77  jmp     loc_180044C71
0x180044b7c  lea     r8, [rsp+2B0h+pcbNeeded]; pcbNeeded
0x180044b81  mov     [rsp+2B0h+pcbNeeded], 208h
0x180044b89  lea     rdx, [rsp+2B0h+FileName]; unsigned __int16 *
0x180044b8e  xor     ecx, ecx; pName
0x180044b90  call    ?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z; InternalGetColorDirectory(ushort const *,ushort *,ulong *)
0x180044b95  test    eax, eax
0x180044b97  jz      loc_180044C71
0x180044b9d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180044ba1  lea     rcx, [rsp+2B0h+FileName]
0x180044ba6  mov     rax, rbx
0x180044ba9  inc     rax
0x180044bac  cmp     [rcx+rax*2], r15w
0x180044bb1  jnz     short loc_180044BA9
0x180044bb3  cmp     [rsp+rax*2+2B0h+var_252], 5Ch ; '\'
0x180044bb9  jz      short loc_180044BD8
0x180044bbb  lea     r8, gszBackslash; "\\"
0x180044bc2  mov     edx, 104h; unsigned __int64
0x180044bc7  lea     rcx, [rsp+2B0h+FileName]; unsigned __int16 *
0x180044bcc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180044bd1  mov     r8d, eax
0x180044bd4  test    eax, eax
0x180044bd6  js      short loc_180044BF1
0x180044bd8  mov     r8, r14; unsigned __int16 *
0x180044bdb  lea     rcx, [rsp+2B0h+FileName]; unsigned __int16 *
0x180044be0  mov     edx, 104h; unsigned __int64
0x180044be5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180044bea  mov     r8d, eax
0x180044bed  test    eax, eax
0x180044bef  jns     short loc_180044C0B
0x180044bf1  mov     eax, r8d
0x180044bf4  movzx   ecx, r8w
0x180044bf8  and     eax, 1FFF0000h
0x180044bfd  cmp     eax, 70000h
0x180044c02  cmovnz  ecx, r8d
0x180044c06  jmp     loc_180044B71
0x180044c0b  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x180044c10  call    cs:__imp_GetFileAttributesW
0x180044c16  cmp     eax, 0FFFFFFFFh
0x180044c19  jnz     short loc_180044C30
0x180044c1b  xor     r8d, r8d; bFailIfExists
0x180044c1e  lea     rdx, [rsp+2B0h+FileName]; lpNewFileName
0x180044c23  mov     rcx, rdi; lpExistingFileName
0x180044c26  call    cs:__imp_CopyFileW
0x180044c2c  test    eax, eax
0x180044c2e  jz      short loc_180044C71
0x180044c30  mov     esi, 1
0x180044c35  inc     rbx
0x180044c38  cmp     [rdi+rbx*2], r15w
0x180044c3d  jnz     short loc_180044C35
0x180044c3f  lea     rcx, ds:2[rbx*2]
0x180044c47  mov     [rsp+2B0h+var_278], rdi
0x180044c4c  mov     [rsp+2B0h+var_270], ecx
0x180044c50  lea     r9, [rsp+2B0h+var_278]
0x180044c55  mov     rcx, cs:g_etwHandle
0x180044c5c  lea     rdx, INSTALL_PROFILE
0x180044c63  mov     r8d, esi
0x180044c66  mov     [rsp+2B0h+var_26C], r15d
0x180044c6b  call    cs:__imp_EtwEventWrite
0x180044c71  mov     eax, esi
0x180044c73  jmp     short loc_180044C82
0x180044c75  mov     ecx, 57h ; 'W'; dwErrCode
0x180044c7a  call    cs:__imp_SetLastError
0x180044c80  xor     eax, eax
0x180044c82  mov     rcx, [rbp+1B0h+var_40]
0x180044c89  xor     rcx, rsp; StackCookie
0x180044c8c  call    __security_check_cookie
0x180044c91  add     rsp, 288h
0x180044c98  pop     r15
0x180044c9a  pop     r14
0x180044c9c  pop     rdi
0x180044c9d  pop     rsi
0x180044c9e  pop     rbx
0x180044c9f  pop     rbp
0x180044ca0  retn
```
