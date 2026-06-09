# HlibLoadDll

- ea: `0x18025b0f4`
- end: `0x18025b28d`
- name: `HlibLoadDll`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180131dc0`

## callees

- `0x1801cb418`
- `0x18025af34`
- `0x18025b0f4`
- `0x1803481f0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18025b23d`
- `msvcrt!wcscpy_s` at `0x18025b23d`
- `msvcrt!wcsrchr` at `0x18025b1ee`
- `msvcrt!wcsrchr` at `0x18025b1ee`
- `KERNEL32!LoadLibraryExW` at `0x18025b254`
- `KERNEL32!LoadLibraryExW` at `0x18025b276`
- `KERNEL32!LoadLibraryExW` at `0x18025b254`
- `KERNEL32!LoadLibraryExW` at `0x18025b276`
- `KERNEL32!GetModuleFileNameW` at `0x18025b1b8`
- `KERNEL32!GetModuleFileNameW` at `0x18025b1b8`

## pseudocode

```c
HMODULE __fastcall HlibLoadDll(__int16 a1, _DWORD *a2)
{
  HMODULE result; // rax
  __int64 v3; // rdi
  signed int ModuleFileNameW; // eax
  wchar_t *v5; // rax
  wchar_t Filename[261]; // [rsp+28h] [rbp-E0h] BYREF
  char v7; // [rsp+232h] [rbp+12Ah] BYREF
  wchar_t Source[264]; // [rsp+238h] [rbp+130h] BYREF

  *a2 = 1;
  if ( (a1 & 0x3FF) == 9 )
  {
    result = g_hInstance;
    *a2 = 0;
  }
  else if ( FGenerateDllName(Source, 1023, a1) )
  {
    v3 = -1;
    do
      ++v3;
    while ( Source[v3] );
    ModuleFileNameW = GetModuleFileNameW(g_hInstance, Filename, 0x104u);
    if ( (unsigned __int64)(2LL * ModuleFileNameW) >= 0x20A )
      _report_rangecheckfailure();
    Filename[ModuleFileNameW] = 0;
    if ( !ModuleFileNameW )
      return LoadLibraryExW(Source, 0, 0x60u);
    v5 = wcsrchr(Filename, 0x5Cu);
    if ( !v5 )
      return LoadLibraryExW(Source, 0, 0x60u);
    if ( ((&v7 - (char *)v5) >> 1) - 2 < (int)v3 )
      return LoadLibraryExW(Source, 0, 0x60u);
    wcscpy_s(v5 + 1, 261 - (((char *)v5 - (char *)Filename + 2) >> 1), Source);
    result = LoadLibraryExW(Filename, 0, 0x60u);
    if ( !result )
      return LoadLibraryExW(Source, 0, 0x60u);
  }
  else
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18025b0f4  mov     rax, rsp
0x18025b0f7  mov     [rax+18h], rbx
0x18025b0fb  mov     [rax+20h], rdi
0x18025b0ff  mov     [rax+10h], rdx
0x18025b103  mov     [rax+8], ecx
0x18025b106  push    rbp
0x18025b107  lea     rbp, [rax-358h]
0x18025b10e  sub     rsp, 450h
0x18025b115  mov     rax, cs:__security_cookie
0x18025b11c  xor     rax, rsp
0x18025b11f  mov     [rbp+350h+var_10], rax
0x18025b126  mov     r8d, [rbp+350h+arg_0]
0x18025b12d  mov     edx, 3FFh
0x18025b132  mov     rcx, [rbp+350h+arg_8]
0x18025b139  movzx   eax, r8w
0x18025b13d  and     ax, dx
0x18025b140  mov     dword ptr [rcx], 1
0x18025b146  cmp     ax, 9
0x18025b14a  jnz     short loc_18025B17C
0x18025b14c  mov     rax, cs:?g_hInstance@@3PEAXEA; void * g_hInstance
0x18025b153  xor     ebx, ebx
0x18025b155  mov     [rcx], ebx
0x18025b157  mov     rcx, [rbp+350h+var_10]
0x18025b15e  xor     rcx, rsp; StackCookie
0x18025b161  call    __security_check_cookie
0x18025b166  lea     r11, [rsp+450h+var_s0]
0x18025b16e  mov     rbx, [r11+20h]
0x18025b172  mov     rdi, [r11+28h]
0x18025b176  mov     rsp, r11
0x18025b179  pop     rbp
0x18025b17a  retn
0x18025b17c  lea     rcx, [rbp+350h+Source]; Destination
0x18025b183  call    FGenerateDllName
0x18025b188  xor     ebx, ebx
0x18025b18a  test    eax, eax
0x18025b18c  jnz     short loc_18025B192
0x18025b18e  xor     eax, eax
0x18025b190  jmp     short loc_18025B157
0x18025b192  lea     rax, [rbp+350h+Source]
0x18025b199  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18025b19d  inc     rdi
0x18025b1a0  cmp     [rax+rdi*2], bx
0x18025b1a4  jnz     short loc_18025B19D
0x18025b1a6  mov     rcx, cs:?g_hInstance@@3PEAXEA; hModule
0x18025b1ad  lea     rdx, [rsp+450h+Filename]; lpFilename
0x18025b1b2  mov     r8d, 104h; nSize
0x18025b1b8  call    cs:__imp_GetModuleFileNameW
0x18025b1bf  nop     dword ptr [rax+rax+00h]
0x18025b1c4  movsxd  rcx, eax
0x18025b1c7  add     rcx, rcx
0x18025b1ca  cmp     rcx, 20Ah
0x18025b1d1  jnb     loc_18025B287
0x18025b1d7  mov     [rsp+rcx+450h+Filename], bx
0x18025b1dc  test    eax, eax
0x18025b1de  jz      loc_18025B269
0x18025b1e4  mov     edx, 5Ch ; '\'; Ch
0x18025b1e9  lea     rcx, [rsp+450h+Filename]; Str
0x18025b1ee  call    cs:__imp_wcsrchr
0x18025b1f5  nop     dword ptr [rax+rax+00h]
0x18025b1fa  mov     r9, rax
0x18025b1fd  test    rax, rax
0x18025b200  jz      short loc_18025B269
0x18025b202  lea     rdx, [rbp+350h+var_226]
0x18025b209  movsxd  rcx, edi
0x18025b20c  sub     rdx, rax
0x18025b20f  sar     rdx, 1
0x18025b212  sub     rdx, 2
0x18025b216  cmp     rdx, rcx
0x18025b219  jl      short loc_18025B269
0x18025b21b  lea     rcx, [rsp+450h+Filename]
0x18025b220  mov     edx, 105h
0x18025b225  sub     rax, rcx
0x18025b228  lea     r8, [rbp+350h+Source]; Source
0x18025b22f  add     rax, 2
0x18025b233  lea     rcx, [r9+2]; Destination
0x18025b237  sar     rax, 1
0x18025b23a  sub     rdx, rax; SizeInWords
0x18025b23d  call    cs:__imp_wcscpy_s
0x18025b244  nop     dword ptr [rax+rax+00h]
0x18025b249  xor     edx, edx; hFile
0x18025b24b  lea     rcx, [rsp+450h+Filename]; lpLibFileName
0x18025b250  lea     r8d, [rdx+60h]; dwFlags
0x18025b254  call    cs:__imp_LoadLibraryExW
0x18025b25b  nop     dword ptr [rax+rax+00h]
0x18025b260  test    rax, rax
0x18025b263  jnz     loc_18025B157
0x18025b269  xor     edx, edx; hFile
0x18025b26b  lea     rcx, [rbp+350h+Source]; lpLibFileName
0x18025b272  lea     r8d, [rdx+60h]; dwFlags
0x18025b276  call    cs:__imp_LoadLibraryExW
0x18025b27d  nop     dword ptr [rax+rax+00h]
0x18025b282  jmp     loc_18025B157
0x18025b287  call    __report_rangecheckfailure
```
