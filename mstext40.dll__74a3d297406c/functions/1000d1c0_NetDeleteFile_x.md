# NetDeleteFile(x)

- ea: `0x1000d1c0`
- end: `0x1000d2a7`
- name: `_NetDeleteFile@4`
- size: `231`
- prototype: `int __stdcall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x1000fc70`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x1000ca60`
- `0x1000d1c0`
- `0x1000ddd0`
- `0x1000e950`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1000d21e`
- `KERNEL32!WideCharToMultiByte` at `0x1000d272`
- `KERNEL32!WideCharToMultiByte` at `0x1000d21e`
- `KERNEL32!WideCharToMultiByte` at `0x1000d272`

## pseudocode

```c
int __thiscall NetDeleteFile(void *this, LPCWCH lpWideCharStr)
{
  int InternetError; // esi
  CHAR *v5; // ebx
  HINTERNET v6; // [esp+8h] [ebp-4h] BYREF
  HINTERNET retaddr; // [esp+Ch] [ebp+0h]
  LPCWCH lpWideCharStra; // [esp+10h] [ebp+4h]

  v6 = this;
  if ( !dword_10040FB8 && !NetInitializeInternetServices() )
    return -20163;
  InternetError = SetupForFTP(lpWideCharStr, &v6);
  if ( !InternetError )
  {
    lpWideCharStra = (LPCWCH)WideCharToMultiByte(0, 0, lpWideCharStr, wcslen(lpWideCharStr), 0, 0, 0, 0);
    v5 = (CHAR *)MemAllocate((size_t)lpWideCharStra + 1);
    if ( !v5 )
    {
      InternetCloseHandle(v6);
      return -1011;
    }
    WideCharToMultiByte(0, 0, lpWideCharStr, wcslen(lpWideCharStr), v5, (int)lpWideCharStra, 0, 0);
    if ( !FtpDeleteFileA(v6, v5) )
      InternetError = GetInternetError();
    MemFree(v5);
    InternetCloseHandle(retaddr);
  }
  return InternetError;
}

```

## disassembly

```asm
0x1000d1c0  push    ecx
0x1000d1c1  cmp     dword_10040FB8, 0
0x1000d1c8  jnz     short loc_1000D1DC
0x1000d1ca  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x1000d1cf  test    eax, eax
0x1000d1d1  jnz     short loc_1000D1DC
0x1000d1d3  mov     eax, 0FFFFB13Dh
0x1000d1d8  pop     ecx
0x1000d1d9  retn    4
0x1000d1dc  push    esi
0x1000d1dd  push    edi
0x1000d1de  mov     edi, [esp+0Ch+lpWideCharStr]
0x1000d1e2  lea     eax, [esp+0Ch+var_4]
0x1000d1e6  push    eax
0x1000d1e7  push    edi
0x1000d1e8  call    SetupForFTP
0x1000d1ed  mov     esi, eax
0x1000d1ef  test    esi, esi
0x1000d1f1  jnz     loc_1000D29F
0x1000d1f7  mov     ecx, edi
0x1000d1f9  lea     edx, [ecx+2]
0x1000d1fc  lea     esp, [esp+0]
0x1000d200  mov     ax, [ecx]
0x1000d203  add     ecx, 2
0x1000d206  test    ax, ax
0x1000d209  jnz     short loc_1000D200
0x1000d20b  push    ebx
0x1000d20c  push    0; lpUsedDefaultChar
0x1000d20e  push    0; lpDefaultChar
0x1000d210  push    0; cbMultiByte
0x1000d212  push    0; lpMultiByteStr
0x1000d214  sub     ecx, edx
0x1000d216  sar     ecx, 1
0x1000d218  push    ecx; cchWideChar
0x1000d219  push    edi; lpWideCharStr
0x1000d21a  push    0; dwFlags
0x1000d21c  push    0; CodePage
0x1000d21e  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d224  mov     [esp+10h+lpWideCharStr], eax
0x1000d228  lea     ecx, [eax+1]
0x1000d22b  push    ecx; Size
0x1000d22c  call    _MemAllocate@4; MemAllocate(x)
0x1000d231  mov     ebx, eax
0x1000d233  test    ebx, ebx
0x1000d235  jnz     short loc_1000D24F
0x1000d237  push    [esp+10h+var_4]
0x1000d23b  mov     esi, 0FFFFFC0Dh
0x1000d240  call    InternetCloseHandle
0x1000d246  pop     ebx
0x1000d247  pop     edi
0x1000d248  mov     eax, esi
0x1000d24a  pop     esi
0x1000d24b  pop     ecx
0x1000d24c  retn    4
0x1000d24f  mov     ecx, edi
0x1000d251  lea     edx, [ecx+2]
0x1000d254  mov     ax, [ecx]
0x1000d257  add     ecx, 2
0x1000d25a  test    ax, ax
0x1000d25d  jnz     short loc_1000D254
0x1000d25f  push    0; lpUsedDefaultChar
0x1000d261  push    0; lpDefaultChar
0x1000d263  push    [esp+18h+lpWideCharStr]; cbMultiByte
0x1000d267  sub     ecx, edx
0x1000d269  push    ebx; lpMultiByteStr
0x1000d26a  sar     ecx, 1
0x1000d26c  push    ecx; cchWideChar
0x1000d26d  push    edi; lpWideCharStr
0x1000d26e  push    0; dwFlags
0x1000d270  push    0; CodePage
0x1000d272  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d278  push    ebx
0x1000d279  push    [esp+14h+var_4]
0x1000d27d  call    FtpDeleteFileA
0x1000d283  test    eax, eax
0x1000d285  jnz     short loc_1000D28E
0x1000d287  call    GetInternetError
0x1000d28c  mov     esi, eax
0x1000d28e  push    ebx
0x1000d28f  call    _MemFree@4; MemFree(x)
0x1000d294  push    dword ptr [esp+0Ch]
0x1000d298  call    InternetCloseHandle
0x1000d29e  pop     ebx
0x1000d29f  pop     edi
0x1000d2a0  mov     eax, esi
0x1000d2a2  pop     esi
0x1000d2a3  pop     ecx
0x1000d2a4  retn    4
```
