# GetDriverVersionInfo(x,x,x)

- ea: `0x1000f076`
- end: `0x1000f230`
- name: `_GetDriverVersionInfo@12`
- size: `442`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1000f240`
- `0x1000f4d0`

## callees

- `0x1000ed1b`
- `0x1000ed4e`
- `0x1000edb0`
- `0x1000edf3`
- `0x1000f076`
- `0x10012b50`
- `0x1001347b`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1000f219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1000f219`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000f0eb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1000f0eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1000f0c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1000f0c3`
- `api-ms-win-core-versionansi-l1-1-1!GetFileVersionInfoSizeA` at `0x1000f0d7`
- `api-ms-win-core-versionansi-l1-1-1!GetFileVersionInfoSizeA` at `0x1000f0d7`
- `api-ms-win-core-versionansi-l1-1-1!GetFileVersionInfoA` at `0x1000f10a`
- `api-ms-win-core-versionansi-l1-1-1!GetFileVersionInfoA` at `0x1000f10a`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x1000f12c`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x1000f180`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x1000f1f1`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x1000f12c`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x1000f180`
- `api-ms-win-core-versionansi-l1-1-0!VerQueryValueA` at `0x1000f1f1`

## pseudocode

```c
HLOCAL __userpurge GetDriverVersionInfo@<eax>(_BYTE *a1@<edx>, int a2@<ecx>, const char *a3@<esi>, int a4)
{
  HLOCAL result; // eax
  DWORD v6; // ebx
  void *v7; // esi
  BOOL v8; // eax
  char *v9; // ecx
  size_t v10; // ebx
  char *v11; // ecx
  const char *v12; // [esp-4h] [ebp-128h]
  size_t v13; // [esp-4h] [ebp-128h]
  const char *v14; // [esp+0h] [ebp-124h]
  size_t *v15; // [esp+0h] [ebp-124h]
  DWORD dwHandle; // [esp+Ch] [ebp-118h] BYREF
  LPVOID lpBuffer; // [esp+10h] [ebp-114h] BYREF
  char psz[4]; // [esp+14h] [ebp-110h] BYREF
  unsigned int puLen; // [esp+18h] [ebp-10Ch] BYREF
  CHAR Filename[260]; // [esp+1Ch] [ebp-108h] BYREF

  *(_DWORD *)psz = a2;
  memset(Filename, 0, sizeof(Filename));
  *a1 = 0;
  GetModuleFileNameA(ghModule, Filename, 0x104u);
  result = (HLOCAL)GetFileVersionInfoSizeA(Filename, &dwHandle);
  v6 = (DWORD)result;
  if ( result )
  {
    v12 = a3;
    result = LocalAlloc(0x40u, (SIZE_T)result);
    v7 = result;
    if ( result )
    {
      if ( GetFileVersionInfoA(Filename, dwHandle, v6, result) )
      {
        v8 = VerQueryValueA(v7, "\\VarFileInfo\\Translation", &lpBuffer, &puLen);
        v10 = *(_DWORD *)psz;
        if ( v8 )
        {
          if ( puLen >= 4 )
          {
            StringCchPrintfA(
              Filename,
              0x104u,
              "\\StringFileInfo\\%04X%04X\\%s",
              *(unsigned __int16 *)lpBuffer,
              *((unsigned __int16 *)lpBuffer + 1),
              *(const char **)psz);
            if ( VerQueryValueA(v7, Filename, &lpBuffer, &puLen) )
            {
              if ( puLen )
                goto LABEL_12;
            }
          }
        }
        StringCopyWorkerA(v9, (size_t)"\\StringFileInfo\\040904E4\\", (size_t *)v9, v12, (size_t)v14);
        if ( StringLengthWorkerA(psz, v13, v15) >= 0 )
          StringCopyWorkerA(v11, v10, (size_t *)v11, v12, (size_t)v14);
        if ( VerQueryValueA(v7, Filename, &lpBuffer, &puLen) && puLen )
LABEL_12:
          StringCchCopyA((STRSAFE_LPSTR)lpBuffer, (size_t)v12, v14);
      }
      return LocalFree(v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000f076  mov     edi, edi
0x1000f078  push    ebp
0x1000f079  mov     ebp, esp
0x1000f07b  sub     esp, 11Ch
0x1000f081  mov     eax, ___security_cookie
0x1000f086  xor     eax, ebp
0x1000f088  mov     [ebp+var_4], eax
0x1000f08b  push    ebx
0x1000f08c  push    edi; pszSrc
0x1000f08d  mov     edi, 104h
0x1000f092  mov     dword ptr [ebp+psz], ecx
0x1000f098  push    edi; Size
0x1000f099  lea     eax, [ebp+Filename]
0x1000f09f  mov     ebx, edx
0x1000f0a1  push    0; Val
0x1000f0a3  push    eax; void *
0x1000f0a4  mov     [ebp+var_11C], ebx
0x1000f0aa  call    _memset
0x1000f0af  add     esp, 0Ch
0x1000f0b2  mov     byte ptr [ebx], 0
0x1000f0b5  lea     eax, [ebp+Filename]
0x1000f0bb  push    edi; nSize
0x1000f0bc  push    eax; lpFilename
0x1000f0bd  push    _ghModule; hModule
0x1000f0c3  call    ds:__imp__GetModuleFileNameA@12; GetModuleFileNameA(x,x,x)
0x1000f0c9  lea     eax, [ebp+dwHandle]
0x1000f0cf  push    eax; lpdwHandle
0x1000f0d0  lea     eax, [ebp+Filename]
0x1000f0d6  push    eax; lptstrFilename
0x1000f0d7  call    ds:__imp__GetFileVersionInfoSizeA@8; GetFileVersionInfoSizeA(x,x)
0x1000f0dd  mov     ebx, eax
0x1000f0df  test    ebx, ebx
0x1000f0e1  jz      loc_1000F220
0x1000f0e7  push    esi; cchDest
0x1000f0e8  push    ebx; uBytes
0x1000f0e9  push    40h ; '@'; uFlags
0x1000f0eb  call    ds:__imp__LocalAlloc@8; LocalAlloc(x,x)
0x1000f0f1  mov     esi, eax
0x1000f0f3  test    esi, esi
0x1000f0f5  jz      loc_1000F21F
0x1000f0fb  push    esi; lpData
0x1000f0fc  push    ebx; dwLen
0x1000f0fd  push    [ebp+dwHandle]; dwHandle
0x1000f103  lea     eax, [ebp+Filename]
0x1000f109  push    eax; lptstrFilename
0x1000f10a  call    ds:__imp__GetFileVersionInfoA@16; GetFileVersionInfoA(x,x,x,x)
0x1000f110  test    eax, eax
0x1000f112  jz      loc_1000F218
0x1000f118  lea     eax, [ebp+puLen]
0x1000f11e  push    eax; puLen
0x1000f11f  lea     eax, [ebp+lpBuffer]
0x1000f125  push    eax; lplpBuffer
0x1000f126  push    offset SubBlock; "\\VarFileInfo\\Translation"
0x1000f12b  push    esi; pBlock
0x1000f12c  call    ds:__imp__VerQueryValueA@16; VerQueryValueA(x,x,x,x)
0x1000f132  mov     ebx, dword ptr [ebp+psz]
0x1000f138  test    eax, eax
0x1000f13a  jz      short loc_1000F193
0x1000f13c  cmp     [ebp+puLen], 4
0x1000f143  jb      short loc_1000F193
0x1000f145  mov     ecx, [ebp+lpBuffer]
0x1000f14b  push    ebx
0x1000f14c  movzx   eax, word ptr [ecx+2]
0x1000f150  push    eax
0x1000f151  movzx   eax, word ptr [ecx]
0x1000f154  push    eax
0x1000f155  push    offset pszFormat; "\\StringFileInfo\\%04X%04X\\%s"
0x1000f15a  lea     eax, [ebp+Filename]
0x1000f160  push    edi; cchDest
0x1000f161  push    eax; pszDest
0x1000f162  call    _StringCchPrintfA
0x1000f167  add     esp, 18h
0x1000f16a  lea     eax, [ebp+puLen]
0x1000f170  push    eax; puLen
0x1000f171  lea     eax, [ebp+lpBuffer]
0x1000f177  push    eax; lplpBuffer
0x1000f178  lea     eax, [ebp+Filename]
0x1000f17e  push    eax; lpSubBlock
0x1000f17f  push    esi; pBlock
0x1000f180  call    ds:__imp__VerQueryValueA@16; VerQueryValueA(x,x,x,x)
0x1000f186  test    eax, eax
0x1000f188  jz      short loc_1000F193
0x1000f18a  cmp     [ebp+puLen], 0
0x1000f191  jnz     short loc_1000F204
0x1000f193  push    ecx; pcchNewDestLength
0x1000f194  push    offset aStringfileinfo_0; "\\StringFileInfo\\040904E4\\"
0x1000f199  push    ecx; pszDest
0x1000f19a  mov     edx, edi
0x1000f19c  lea     ecx, [ebp+Filename]
0x1000f1a2  call    StringCopyWorkerA
0x1000f1a7  lea     eax, [ebp+psz]
0x1000f1ad  mov     edx, edi
0x1000f1af  push    eax; psz
0x1000f1b0  lea     ecx, [ebp+Filename]
0x1000f1b6  call    StringLengthWorkerA
0x1000f1bb  test    eax, eax
0x1000f1bd  js      short loc_1000F1DB
0x1000f1bf  sub     edi, dword ptr [ebp+psz]
0x1000f1c5  push    ecx; pcchNewDestLength
0x1000f1c6  push    ebx; cchDest
0x1000f1c7  push    ecx; pszDest
0x1000f1c8  lea     ecx, [ebp+Filename]
0x1000f1ce  mov     edx, edi
0x1000f1d0  add     ecx, dword ptr [ebp+psz]
0x1000f1d6  call    StringCopyWorkerA
0x1000f1db  lea     eax, [ebp+puLen]
0x1000f1e1  push    eax; puLen
0x1000f1e2  lea     eax, [ebp+lpBuffer]
0x1000f1e8  push    eax; lplpBuffer
0x1000f1e9  lea     eax, [ebp+Filename]
0x1000f1ef  push    eax; lpSubBlock
0x1000f1f0  push    esi; pBlock
0x1000f1f1  call    ds:__imp__VerQueryValueA@16; VerQueryValueA(x,x,x,x)
0x1000f1f7  test    eax, eax
0x1000f1f9  jz      short loc_1000F218
0x1000f1fb  cmp     [ebp+puLen], 0
0x1000f202  jz      short loc_1000F218
0x1000f204  push    [ebp+lpBuffer]; pszDest
0x1000f20a  mov     edx, [ebp+arg_0]
0x1000f20d  mov     ecx, [ebp+var_11C]
0x1000f213  call    _StringCchCopyA@12; StringCchCopyA(x,x,x)
0x1000f218  push    esi; hMem
0x1000f219  call    ds:__imp__LocalFree@4; LocalFree(x)
0x1000f21f  pop     esi
0x1000f220  mov     ecx, [ebp+var_4]
0x1000f223  pop     edi
0x1000f224  xor     ecx, ebp; StackCookie
0x1000f226  pop     ebx
0x1000f227  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000f22c  leave
0x1000f22d  retn    4
```
