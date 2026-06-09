# SpUtilsSetTargetWindowsDir

- ea: `0x18001fd5c`
- end: `0x18001fe28`
- name: `SpUtilsSetTargetWindowsDir`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001ff98`

## callees

- `0x180008020`
- `0x18000be40`
- `0x18001fd5c`
- `0x1800202d0`
- `0x180020384`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001fdaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001fdaf`

## pseudocode

```c
__int64 SpUtilsSetTargetWindowsDir()
{
  unsigned int v0; // ebx
  void *v1; // rax
  WCHAR Buffer[296]; // [rsp+20h] [rbp-268h] BYREF

  v0 = 0;
  if ( g_sputils_WindowsDirectory )
  {
    HeapFree(hHeap, 0, g_sputils_WindowsDirectory);
    g_sputils_WindowsDirectory = 0;
  }
  g_sputils_IsOnlineWindowsDirectory = 1;
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    return v0;
  v1 = (void *)pSetupDuplicateString(Buffer);
  g_sputils_WindowsDirectory = v1;
  if ( !v1 )
    return v0;
  if ( !g_sputils_LogInitialized )
    return 1;
  if ( !g_sputils_IsOnlineWindowsDirectory )
    goto LABEL_9;
  if ( (unsigned int)pSpUtilsSetLogPathFromRegKey() )
    return 1;
  v1 = g_sputils_WindowsDirectory;
LABEL_9:
  if ( (unsigned int)pSpUtilsSetLogPath((STRSAFE_LPCWSTR)v1) )
    return 1;
  return v0;
}

```

## disassembly

```asm
0x18001fd5c  push    rbx
0x18001fd5e  sub     rsp, 280h
0x18001fd65  mov     rax, cs:__security_cookie
0x18001fd6c  xor     rax, rsp
0x18001fd6f  mov     [rsp+288h+var_18], rax
0x18001fd77  mov     r8, cs:g_sputils_WindowsDirectory; lpMem
0x18001fd7e  xor     ebx, ebx
0x18001fd80  test    r8, r8
0x18001fd83  jz      short loc_18001FD9B
0x18001fd85  mov     rcx, cs:hHeap; hHeap
0x18001fd8c  xor     edx, edx; dwFlags
0x18001fd8e  call    cs:__imp_HeapFree
0x18001fd94  mov     cs:g_sputils_WindowsDirectory, rbx
0x18001fd9b  mov     edx, 104h; uSize
0x18001fda0  mov     cs:g_sputils_IsOnlineWindowsDirectory, 1
0x18001fdaa  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x18001fdaf  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001fdb5  dec     eax
0x18001fdb7  cmp     eax, 103h
0x18001fdbc  ja      short loc_18001FE0D
0x18001fdbe  lea     rcx, [rsp+288h+Buffer]
0x18001fdc3  call    pSetupDuplicateString
0x18001fdc8  mov     cs:g_sputils_WindowsDirectory, rax
0x18001fdcf  test    rax, rax
0x18001fdd2  jz      short loc_18001FE0D
0x18001fdd4  cmp     cs:g_sputils_LogInitialized, ebx
0x18001fdda  jz      short loc_18001FE08
0x18001fddc  mov     edx, cs:g_sputils_IsOnlineWindowsDirectory
0x18001fde2  test    edx, edx
0x18001fde4  jz      short loc_18001FDFC
0x18001fde6  call    pSpUtilsSetLogPathFromRegKey
0x18001fdeb  test    eax, eax
0x18001fded  jnz     short loc_18001FE08
0x18001fdef  mov     rax, cs:g_sputils_WindowsDirectory
0x18001fdf6  mov     edx, cs:g_sputils_IsOnlineWindowsDirectory
0x18001fdfc  mov     rcx, rax; pszSrc
0x18001fdff  call    pSpUtilsSetLogPath
0x18001fe04  test    eax, eax
0x18001fe06  jz      short loc_18001FE0D
0x18001fe08  mov     ebx, 1
0x18001fe0d  mov     eax, ebx
0x18001fe0f  mov     rcx, [rsp+288h+var_18]
0x18001fe17  xor     rcx, rsp; StackCookie
0x18001fe1a  call    __security_check_cookie
0x18001fe1f  add     rsp, 280h
0x18001fe26  pop     rbx
0x18001fe27  retn
```
