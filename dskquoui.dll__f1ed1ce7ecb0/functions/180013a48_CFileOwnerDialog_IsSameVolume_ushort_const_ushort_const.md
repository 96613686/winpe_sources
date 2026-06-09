# CFileOwnerDialog::IsSameVolume(ushort const *,ushort const *)

- ea: `0x180013a48`
- end: `0x180013b86`
- name: `?IsSameVolume@CFileOwnerDialog@@AEAAJPEBG0@Z`
- size: `318`
- prototype: `__int64 __fastcall(CFileOwnerDialog *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180013d44`

## callees

- `0x180001510`
- `0x180013a48`

## import_xrefs

- `SHLWAPI!PathAddBackslashW` at `0x180013abb`
- `SHLWAPI!PathAddBackslashW` at `0x180013b1f`
- `SHLWAPI!PathAddBackslashW` at `0x180013abb`
- `SHLWAPI!PathAddBackslashW` at `0x180013b1f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180013ad6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180013b41`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180013ad6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180013b41`
- `KERNEL32!lstrcmpiW` at `0x180013b5b`
- `KERNEL32!lstrcmpiW` at `0x180013b5b`

## pseudocode

```c
__int64 __fastcall CFileOwnerDialog::IsSameVolume(CFileOwnerDialog *this, WCHAR *a2, WCHAR *a3)
{
  WCHAR *v3; // rax
  __int64 v4; // rdi
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // ebx
  WCHAR *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rax
  WCHAR *v12; // rcx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-668h] BYREF
  WCHAR String2[264]; // [rsp+230h] [rbp-458h] BYREF
  WCHAR szVolumeName[264]; // [rsp+440h] [rbp-248h] BYREF

  v3 = pszPath;
  v4 = 2147483646;
  v6 = 2147483646;
  v7 = 260;
  v8 = 1;
  do
  {
    if ( !v6 )
      break;
    if ( !*a2 )
      break;
    *v3++ = *a2++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v3 - 1;
  if ( v7 )
    v9 = v3;
  *v9 = 0;
  if ( !PathAddBackslashW(pszPath) )
    return (unsigned int)-2147024774;
  if ( GetVolumeNameForVolumeMountPointW(pszPath, szVolumeName, 0x104u) )
  {
    v10 = 260;
    v11 = pszPath;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v11++ = *a3++;
      --v4;
      --v10;
    }
    while ( v10 );
    v12 = v11 - 1;
    if ( v10 )
      v12 = v11;
    *v12 = 0;
    if ( !PathAddBackslashW(pszPath) )
      return (unsigned int)-2147024774;
    if ( GetVolumeNameForVolumeMountPointW(pszPath, String2, 0x104u) && !lstrcmpiW(szVolumeName, String2) )
      return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180013a48  push    rbx
0x180013a4a  push    rbp
0x180013a4b  push    rsi
0x180013a4c  push    rdi
0x180013a4d  push    r14
0x180013a4f  sub     rsp, 660h
0x180013a56  mov     rax, cs:__security_cookie
0x180013a5d  xor     rax, rsp
0x180013a60  mov     [rsp+688h+var_38], rax
0x180013a68  xor     ebp, ebp
0x180013a6a  lea     rax, [rsp+688h+pszPath]
0x180013a6f  mov     edi, 7FFFFFFEh
0x180013a74  mov     r14d, 104h
0x180013a7a  mov     rsi, r8
0x180013a7d  mov     ecx, edi
0x180013a7f  mov     r8d, r14d
0x180013a82  lea     ebx, [rbp+1]
0x180013a85  test    rcx, rcx
0x180013a88  jz      short loc_180013AA8
0x180013a8a  movzx   r9d, word ptr [rdx]
0x180013a8e  test    r9w, r9w
0x180013a92  jz      short loc_180013AA8
0x180013a94  mov     [rax], r9w
0x180013a98  add     rdx, 2
0x180013a9c  add     rax, 2
0x180013aa0  sub     rcx, rbx
0x180013aa3  sub     r8, rbx
0x180013aa6  jnz     short loc_180013A85
0x180013aa8  test    r8, r8
0x180013aab  lea     rcx, [rax-2]
0x180013aaf  cmovnz  rcx, rax
0x180013ab3  mov     [rcx], bp
0x180013ab6  lea     rcx, [rsp+688h+pszPath]; pszPath
0x180013abb  call    cs:__imp_PathAddBackslashW
0x180013ac1  test    rax, rax
0x180013ac4  jz      short loc_180013B2A
0x180013ac6  mov     r8d, r14d; cchBufferLength
0x180013ac9  lea     rdx, [rsp+688h+szVolumeName]; lpszVolumeName
0x180013ad1  lea     rcx, [rsp+688h+pszPath]; lpszVolumeMountPoint
0x180013ad6  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180013adc  test    eax, eax
0x180013ade  jz      loc_180013B66
0x180013ae4  mov     rdx, r14
0x180013ae7  lea     rax, [rsp+688h+pszPath]
0x180013aec  test    rdi, rdi
0x180013aef  jz      short loc_180013B0C
0x180013af1  movzx   ecx, word ptr [rsi]
0x180013af4  test    cx, cx
0x180013af7  jz      short loc_180013B0C
0x180013af9  mov     [rax], cx
0x180013afc  add     rsi, 2
0x180013b00  add     rax, 2
0x180013b04  sub     rdi, rbx
0x180013b07  sub     rdx, rbx
0x180013b0a  jnz     short loc_180013AEC
0x180013b0c  test    rdx, rdx
0x180013b0f  lea     rcx, [rax-2]
0x180013b13  cmovnz  rcx, rax
0x180013b17  mov     [rcx], bp
0x180013b1a  lea     rcx, [rsp+688h+pszPath]; pszPath
0x180013b1f  call    cs:__imp_PathAddBackslashW
0x180013b25  test    rax, rax
0x180013b28  jnz     short loc_180013B31
0x180013b2a  mov     ebx, 8007007Ah
0x180013b2f  jmp     short loc_180013B66
0x180013b31  mov     r8d, r14d; cchBufferLength
0x180013b34  lea     rdx, [rsp+688h+String2]; lpszVolumeName
0x180013b3c  lea     rcx, [rsp+688h+pszPath]; lpszVolumeMountPoint
0x180013b41  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180013b47  test    eax, eax
0x180013b49  jz      short loc_180013B66
0x180013b4b  lea     rdx, [rsp+688h+String2]; lpString2
0x180013b53  lea     rcx, [rsp+688h+szVolumeName]; lpString1
0x180013b5b  call    cs:__imp_lstrcmpiW
0x180013b61  test    eax, eax
0x180013b63  cmovz   ebx, ebp
0x180013b66  mov     eax, ebx
0x180013b68  mov     rcx, [rsp+688h+var_38]
0x180013b70  xor     rcx, rsp; StackCookie
0x180013b73  call    __security_check_cookie
0x180013b78  add     rsp, 660h
0x180013b7f  pop     r14
0x180013b81  pop     rdi
0x180013b82  pop     rsi
0x180013b83  pop     rbp
0x180013b84  pop     rbx
0x180013b85  retn
```
