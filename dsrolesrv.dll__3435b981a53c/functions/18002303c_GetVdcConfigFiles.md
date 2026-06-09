# GetVdcConfigFiles

- ea: `0x18002303c`
- end: `0x180023137`
- name: `GetVdcConfigFiles`
- size: `251`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000a130`
- `0x18000b480`
- `0x180023f6c`

## callees

- `0x180022d64`
- `0x180022f8c`
- `0x180022fe8`
- `0x18002303c`
- `0x180023140`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800230d9`
- `KERNEL32!lstrcmpiW` at `0x1800230d9`

## pseudocode

```c
__int64 __fastcall GetVdcConfigFiles(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 result; // rax
  WCHAR String1[264]; // [rsp+20h] [rbp-448h] BYREF
  WCHAR String2[264]; // [rsp+230h] [rbp-238h] BYREF

  memset_0(String1, 0, 0x20Au);
  memset_0(String2, 0, 0x20Au);
  if ( (unsigned int)GetDitFolder((LPBYTE)String1)
    || (result = CheckFileInFolder(a1, String1, a2, a4), !a4)
    || a3 > *(_DWORD *)(a1 + 12) )
  {
    if ( (unsigned int)GetNtdsFolder(String2) )
      return GetVdcConfigFilesInRemovableDrives(a1, a2, a3, a4);
    if ( !lstrcmpiW(String1, String2) )
      return GetVdcConfigFilesInRemovableDrives(a1, a2, a3, a4);
    result = CheckFileInFolder(a1, String2, a2, a4);
    if ( !a4 || a3 > *(_DWORD *)(a1 + 12) )
      return GetVdcConfigFilesInRemovableDrives(a1, a2, a3, a4);
  }
  return result;
}

```

## disassembly

```asm
0x18002303c  mov     [rsp+arg_10], rbx
0x180023041  push    rbp
0x180023042  push    rsi
0x180023043  push    rdi
0x180023044  sub     rsp, 450h
0x18002304b  mov     rax, cs:__security_cookie
0x180023052  xor     rax, rsp
0x180023055  mov     [rsp+468h+var_28], rax
0x18002305d  mov     esi, r8d
0x180023060  mov     rbp, rdx
0x180023063  mov     rbx, rcx
0x180023066  xor     edx, edx; Val
0x180023068  mov     r8d, 20Ah; Size
0x18002306e  lea     rcx, [rsp+468h+String1]; void *
0x180023073  mov     rdi, r9
0x180023076  call    memset_0
0x18002307b  xor     edx, edx; Val
0x18002307d  lea     rcx, [rsp+468h+String2]; void *
0x180023085  mov     r8d, 20Ah; Size
0x18002308b  call    memset_0
0x180023090  lea     rcx, [rsp+468h+String1]; lpData
0x180023095  call    GetDitFolder
0x18002309a  test    eax, eax
0x18002309c  jnz     short loc_1800230BB
0x18002309e  mov     r9, rdi
0x1800230a1  lea     rdx, [rsp+468h+String1]
0x1800230a6  mov     r8, rbp
0x1800230a9  mov     rcx, rbx
0x1800230ac  call    CheckFileInFolder
0x1800230b1  test    rdi, rdi
0x1800230b4  jz      short loc_1800230BB
0x1800230b6  cmp     esi, [rbx+0Ch]
0x1800230b9  jbe     short loc_180023114
0x1800230bb  lea     rcx, [rsp+468h+String2]; pszDest
0x1800230c3  call    GetNtdsFolder
0x1800230c8  test    eax, eax
0x1800230ca  jnz     short loc_180023103
0x1800230cc  lea     rdx, [rsp+468h+String2]; lpString2
0x1800230d4  lea     rcx, [rsp+468h+String1]; lpString1
0x1800230d9  call    cs:__imp_lstrcmpiW
0x1800230df  test    eax, eax
0x1800230e1  jz      short loc_180023103
0x1800230e3  mov     r9, rdi
0x1800230e6  lea     rdx, [rsp+468h+String2]
0x1800230ee  mov     r8, rbp
0x1800230f1  mov     rcx, rbx
0x1800230f4  call    CheckFileInFolder
0x1800230f9  test    rdi, rdi
0x1800230fc  jz      short loc_180023103
0x1800230fe  cmp     esi, [rbx+0Ch]
0x180023101  jbe     short loc_180023114
0x180023103  mov     r9, rdi
0x180023106  mov     r8d, esi
0x180023109  mov     rdx, rbp
0x18002310c  mov     rcx, rbx
0x18002310f  call    GetVdcConfigFilesInRemovableDrives
0x180023114  mov     rcx, [rsp+468h+var_28]
0x18002311c  xor     rcx, rsp; StackCookie
0x18002311f  call    __security_check_cookie
0x180023124  mov     rbx, [rsp+468h+arg_10]
0x18002312c  add     rsp, 450h
0x180023133  pop     rdi
0x180023134  pop     rsi
0x180023135  pop     rbp
0x180023136  retn
```
