# SpUtilsSetTargetWindowsDir

- ea: `0x18000729c`
- end: `0x180007356`
- name: `SpUtilsSetTargetWindowsDir`
- size: `186`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800031c0`

## callees

- `0x180006f1c`
- `0x18000729c`
- `0x1800076d4`
- `0x1800077d0`
- `0x18000a1a0`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800072ef`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800072ef`
- `KERNEL32!HeapFree` at `0x1800072ce`
- `KERNEL32!HeapFree` at `0x1800072ce`

## pseudocode

```c
__int64 SpUtilsSetTargetWindowsDir()
{
  unsigned int v0; // ebx
  WCHAR Buffer[296]; // [rsp+20h] [rbp-268h] BYREF

  v0 = 0;
  if ( g_sputils_WindowsDirectory )
  {
    HeapFree(hHeap, 0, g_sputils_WindowsDirectory);
    g_sputils_WindowsDirectory = 0;
  }
  g_sputils_IsOnlineWindowsDirectory = 1;
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 <= 0x103 )
  {
    g_sputils_WindowsDirectory = (LPVOID)pSetupDuplicateString(Buffer);
    if ( g_sputils_WindowsDirectory )
    {
      if ( !g_sputils_LogInitialized
        || g_sputils_IsOnlineWindowsDirectory && pSpUtilsSetLogPathFromRegKey()
        || pSpUtilsSetLogPath() )
      {
        return 1;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18000729c  push    rbx
0x18000729e  sub     rsp, 280h
0x1800072a5  mov     rax, cs:__security_cookie
0x1800072ac  xor     rax, rsp
0x1800072af  mov     [rsp+288h+var_18], rax
0x1800072b7  mov     r8, cs:g_sputils_WindowsDirectory; lpMem
0x1800072be  xor     ebx, ebx
0x1800072c0  test    r8, r8
0x1800072c3  jz      short loc_1800072DB
0x1800072c5  mov     rcx, cs:hHeap; hHeap
0x1800072cc  xor     edx, edx; dwFlags
0x1800072ce  call    cs:__imp_HeapFree
0x1800072d4  mov     cs:g_sputils_WindowsDirectory, rbx
0x1800072db  mov     edx, 104h; uSize
0x1800072e0  mov     cs:g_sputils_IsOnlineWindowsDirectory, 1
0x1800072ea  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x1800072ef  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800072f5  dec     eax
0x1800072f7  cmp     eax, 103h
0x1800072fc  ja      short loc_18000733B
0x1800072fe  lea     rcx, [rsp+288h+Buffer]; pszSrc
0x180007303  call    pSetupDuplicateString
0x180007308  mov     cs:g_sputils_WindowsDirectory, rax
0x18000730f  test    rax, rax
0x180007312  jz      short loc_18000733B
0x180007314  cmp     cs:g_sputils_LogInitialized, ebx
0x18000731a  jz      short loc_180007336
0x18000731c  cmp     cs:g_sputils_IsOnlineWindowsDirectory, ebx
0x180007322  jz      short loc_18000732D
0x180007324  call    pSpUtilsSetLogPathFromRegKey
0x180007329  test    eax, eax
0x18000732b  jnz     short loc_180007336
0x18000732d  call    pSpUtilsSetLogPath
0x180007332  test    eax, eax
0x180007334  jz      short loc_18000733B
0x180007336  mov     ebx, 1
0x18000733b  mov     eax, ebx
0x18000733d  mov     rcx, [rsp+288h+var_18]
0x180007345  xor     rcx, rsp; StackCookie
0x180007348  call    __security_check_cookie
0x18000734d  add     rsp, 280h
0x180007354  pop     rbx
0x180007355  retn
```
