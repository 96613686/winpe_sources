# EnumPublishInfCallback(HDRIVERSTORE__ *,ushort const *,_DRIVERSTORE_DRIVERPACKAGE_INFOW *,__int64)

- ea: `0x1800070a0`
- end: `0x180007182`
- name: `?EnumPublishInfCallback@@YAHPEAUHDRIVERSTORE__@@PEBGPEAU_DRIVERSTORE_DRIVERPACKAGE_INFOW@@_J@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct HDRIVERSTORE__ *, const unsigned __int16 *, struct _DRIVERSTORE_DRIVERPACKAGE_INFOW *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180005fc0`
- `0x1800070a0`
- `0x180007188`
- `0x180007608`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000715e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000715e`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800070d8`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800070d8`

## pseudocode

```c
__int64 __fastcall EnumPublishInfCallback(
        struct HDRIVERSTORE__ *a1,
        const unsigned __int16 *a2,
        struct _DRIVERSTORE_DRIVERPACKAGE_INFOW *a3,
        __int64 a4)
{
  signed int LastError; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( a4 )
  {
    if ( GetWindowsDirectoryW(Buffer, 0x104u)
      && (unsigned int)pSetupConcatenatePaths(Buffer, L"INF", 260)
      && (unsigned int)pSetupConcatenatePaths(Buffer, (char *)a3 + 172, 260) )
    {
      if ( !(unsigned int)pSetupFileExists(Buffer)
        || (unsigned int)pSetupStringTableAddString(*(_QWORD *)a4, Buffer) != -1 )
      {
        return 1;
      }
      *(_DWORD *)(a4 + 8) = -2147024888;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *(_DWORD *)(a4 + 8) = LastError;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800070a0  mov     [rsp+arg_0], rbx
0x1800070a5  push    rdi
0x1800070a6  sub     rsp, 240h
0x1800070ad  mov     rax, cs:__security_cookie
0x1800070b4  xor     rax, rsp
0x1800070b7  mov     [rsp+248h+var_18], rax
0x1800070bf  mov     rbx, r9
0x1800070c2  mov     rdi, r8
0x1800070c5  test    r9, r9
0x1800070c8  jz      loc_18000716B
0x1800070ce  mov     edx, 104h; uSize
0x1800070d3  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x1800070d8  call    cs:__imp_GetWindowsDirectoryW
0x1800070de  test    eax, eax
0x1800070e0  jz      short loc_18000715E
0x1800070e2  mov     r8d, 104h
0x1800070e8  lea     rdx, aInf; "INF"
0x1800070ef  lea     rcx, [rsp+248h+Buffer]
0x1800070f4  call    pSetupConcatenatePaths
0x1800070f9  test    eax, eax
0x1800070fb  jz      short loc_18000715E
0x1800070fd  lea     rdx, [rdi+0ACh]
0x180007104  mov     r8d, 104h
0x18000710a  lea     rcx, [rsp+248h+Buffer]
0x18000710f  call    pSetupConcatenatePaths
0x180007114  test    eax, eax
0x180007116  jz      short loc_18000715E
0x180007118  lea     rcx, [rsp+248h+Buffer]; lpFileName
0x18000711d  call    pSetupFileExists
0x180007122  test    eax, eax
0x180007124  jz      short loc_180007138
0x180007126  mov     rcx, [rbx]
0x180007129  lea     rdx, [rsp+248h+Buffer]
0x18000712e  call    pSetupStringTableAddString
0x180007133  cmp     eax, 0FFFFFFFFh
0x180007136  jz      short loc_18000716F
0x180007138  mov     eax, 1
0x18000713d  mov     rcx, [rsp+248h+var_18]
0x180007145  xor     rcx, rsp; StackCookie
0x180007148  call    __security_check_cookie
0x18000714d  mov     rbx, [rsp+248h+arg_0]
0x180007155  add     rsp, 240h
0x18000715c  pop     rdi
0x18000715d  retn
0x18000715e  call    cs:__imp_GetLastError
0x180007164  test    eax, eax
0x180007166  jg      short loc_180007178
0x180007168  mov     [rbx+8], eax
0x18000716b  xor     eax, eax
0x18000716d  jmp     short loc_18000713D
0x18000716f  mov     dword ptr [rbx+8], 80070008h
0x180007176  jmp     short loc_18000716B
0x180007178  movzx   eax, ax
0x18000717b  or      eax, 80070000h
0x180007180  jmp     short loc_180007168
```
