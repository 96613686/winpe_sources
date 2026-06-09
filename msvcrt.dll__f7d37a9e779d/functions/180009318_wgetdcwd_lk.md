# _wgetdcwd_lk

- ea: `0x180009318`
- end: `0x18000943b`
- name: `_wgetdcwd_lk`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009270`
- `0x1800092c0`

## callees

- `0x180007e80`
- `0x180007f00`
- `0x180008790`
- `0x180009318`
- `0x18001d350`
- `0x180061a30`
- `0x180079760`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800093b2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800093b2`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800093c4`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800093c4`

## pseudocode

```c
wchar_t *__fastcall wgetdcwd_lk(__int64 a1, wchar_t *a2, signed int a3)
{
  __int16 v5; // si
  DWORD FullPathNameW; // eax
  signed int v8; // eax
  unsigned __int64 v9; // rax
  LPWSTR FilePart; // [rsp+20h] [rbp-248h] BYREF
  WCHAR FileName; // [rsp+28h] [rbp-240h] BYREF
  int v12; // [rsp+2Ah] [rbp-23Eh]
  __int16 v13; // [rsp+2Eh] [rbp-23Ah]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  FilePart = 0;
  v5 = a1;
  if ( (_DWORD)a1 )
  {
    if ( !(unsigned int)validdrive(a1) )
    {
      *_doserrno() = 15;
      *errno() = 13;
      return 0;
    }
    v12 = 3014714;
    FileName = v5 + 64;
    v13 = 0;
    FullPathNameW = GetFullPathNameW(&FileName, 0x104u, Buffer, &FilePart);
  }
  else
  {
    FullPathNameW = GetCurrentDirectoryW(0x104u, Buffer);
  }
  if ( !FullPathNameW )
    return 0;
  v8 = FullPathNameW + 1;
  if ( (unsigned int)v8 > 0x104 )
    return 0;
  if ( a2 )
  {
    if ( v8 > a3 )
    {
      *errno() = 34;
      return 0;
    }
  }
  else
  {
    if ( v8 > a3 )
      a3 = v8;
    v9 = 2LL * (unsigned int)a3;
    if ( v9 > 0xFFFFFFFF || (a2 = (wchar_t *)malloc((unsigned int)v9)) == 0 )
    {
      *errno() = 12;
      return 0;
    }
  }
  wcscpy_s(a2, a3, Buffer);
  return a2;
}

```

## disassembly

```asm
0x180009318  push    rbx
0x18000931a  push    rsi
0x18000931b  push    rdi
0x18000931c  sub     rsp, 250h
0x180009323  mov     rax, cs:__security_cookie
0x18000932a  xor     rax, rsp
0x18000932d  mov     [rsp+268h+var_28], rax
0x180009335  mov     [rsp+268h+FilePart], 0
0x18000933e  mov     ebx, r8d
0x180009341  mov     rdi, rdx
0x180009344  mov     esi, ecx
0x180009346  test    ecx, ecx
0x180009348  jz      short loc_1800093BA
0x18000934a  call    _validdrive
0x18000934f  test    eax, eax
0x180009351  jnz     short loc_180009386
0x180009353  call    __doserrno
0x180009358  mov     dword ptr [rax], 0Fh
0x18000935e  call    _errno
0x180009363  mov     dword ptr [rax], 0Dh
0x180009369  xor     eax, eax
0x18000936b  mov     rcx, [rsp+268h+var_28]
0x180009373  xor     rcx, rsp; StackCookie
0x180009376  call    __security_check_cookie
0x18000937b  add     rsp, 250h
0x180009382  pop     rdi
0x180009383  pop     rsi
0x180009384  pop     rbx
0x180009385  retn
0x180009386  add     si, 40h ; '@'
0x18000938a  mov     [rsp+268h+var_23E], 2E003Ah
0x180009392  xor     eax, eax
0x180009394  mov     [rsp+268h+FileName], si
0x180009399  lea     r9, [rsp+268h+FilePart]; lpFilePart
0x18000939e  mov     [rsp+268h+var_23A], ax
0x1800093a3  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1800093a8  mov     edx, 104h; nBufferLength
0x1800093ad  lea     rcx, [rsp+268h+FileName]; lpFileName
0x1800093b2  call    cs:__imp_GetFullPathNameW
0x1800093b8  jmp     short loc_1800093CA
0x1800093ba  lea     rdx, [rsp+268h+Buffer]; lpBuffer
0x1800093bf  mov     ecx, 104h; nBufferLength
0x1800093c4  call    cs:__imp_GetCurrentDirectoryW
0x1800093ca  test    eax, eax
0x1800093cc  jz      short loc_180009369
0x1800093ce  inc     eax
0x1800093d0  cmp     eax, 104h
0x1800093d5  ja      short loc_180009369
0x1800093d7  test    rdi, rdi
0x1800093da  jnz     short loc_18000940F
0x1800093dc  cmp     eax, ebx
0x1800093de  mov     ecx, 0FFFFFFFFh
0x1800093e3  cmovg   ebx, eax
0x1800093e6  mov     eax, ebx
0x1800093e8  add     rax, rax
0x1800093eb  cmp     rax, rcx
0x1800093ee  ja      short loc_1800093FF
0x1800093f0  mov     ecx, eax; Size
0x1800093f2  call    malloc
0x1800093f7  mov     rdi, rax
0x1800093fa  test    rax, rax
0x1800093fd  jnz     short loc_180009423
0x1800093ff  call    _errno
0x180009404  mov     dword ptr [rax], 0Ch
0x18000940a  jmp     loc_180009369
0x18000940f  cmp     eax, ebx
0x180009411  jle     short loc_180009423
0x180009413  call    _errno
0x180009418  mov     dword ptr [rax], 22h ; '"'
0x18000941e  jmp     loc_180009369
0x180009423  movsxd  rdx, ebx; SizeInWords
0x180009426  lea     r8, [rsp+268h+Buffer]; Source
0x18000942b  mov     rcx, rdi; Destination
0x18000942e  call    wcscpy_s
0x180009433  mov     rax, rdi
0x180009436  jmp     loc_18000936B
```
