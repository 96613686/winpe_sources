# HlibLoadDll

- ea: `0x18025685c`
- end: `0x1802569d2`
- name: `HlibLoadDll`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18015eacc`

## callees

- `0x1801c8a78`
- `0x1802566bc`
- `0x18025685c`
- `0x180341dd0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180256994`
- `msvcrt!wcscpy_s` at `0x180256994`
- `msvcrt!wcsrchr` at `0x18025694b`
- `msvcrt!wcsrchr` at `0x18025694b`
- `KERNEL32!LoadLibraryExW` at `0x1802569a5`
- `KERNEL32!LoadLibraryExW` at `0x1802569c1`
- `KERNEL32!LoadLibraryExW` at `0x1802569a5`
- `KERNEL32!LoadLibraryExW` at `0x1802569c1`
- `KERNEL32!GetModuleFileNameW` at `0x18025691f`
- `KERNEL32!GetModuleFileNameW` at `0x18025691f`

## pseudocode

```c
HMODULE __fastcall HlibLoadDll(__int16 a1, _DWORD *a2)
{
  HMODULE result; // rax
  __int64 v3; // rdi
  signed int ModuleFileNameW; // eax
  wchar_t *v5; // rax
  WCHAR Filename[261]; // [rsp+28h] [rbp-E0h] BYREF
  char v7; // [rsp+232h] [rbp+12Ah] BYREF
  WCHAR Source[264]; // [rsp+238h] [rbp+130h] BYREF

  *a2 = 1;
  if ( (a1 & 0x3FF) == 9 )
  {
    result = g_hInstance;
    *a2 = 0;
  }
  else if ( (unsigned int)FGenerateDllName(Source) )
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
0x18025685c  mov     rax, rsp
0x18025685f  mov     [rax+18h], rbx
0x180256863  mov     [rax+20h], rdi
0x180256867  mov     [rax+10h], rdx
0x18025686b  mov     [rax+8], ecx
0x18025686e  push    rbp
0x18025686f  lea     rbp, [rax-358h]
0x180256876  sub     rsp, 450h
0x18025687d  mov     rax, cs:__security_cookie
0x180256884  xor     rax, rsp
0x180256887  mov     [rbp+350h+var_10], rax
0x18025688e  mov     r8d, [rbp+350h+arg_0]
0x180256895  mov     edx, 3FFh
0x18025689a  mov     rcx, [rbp+350h+arg_8]
0x1802568a1  movzx   eax, r8w
0x1802568a5  and     ax, dx
0x1802568a8  mov     dword ptr [rcx], 1
0x1802568ae  cmp     ax, 9
0x1802568b2  jnz     short loc_1802568E3
0x1802568b4  mov     rax, cs:?g_hInstance@@3PEAXEA; void * g_hInstance
0x1802568bb  xor     ebx, ebx
0x1802568bd  mov     [rcx], ebx
0x1802568bf  mov     rcx, [rbp+350h+var_10]
0x1802568c6  xor     rcx, rsp; StackCookie
0x1802568c9  call    __security_check_cookie
0x1802568ce  lea     r11, [rsp+450h+var_s0]
0x1802568d6  mov     rbx, [r11+20h]
0x1802568da  mov     rdi, [r11+28h]
0x1802568de  mov     rsp, r11
0x1802568e1  pop     rbp
0x1802568e2  retn
0x1802568e3  lea     rcx, [rbp+350h+Source]; Destination
0x1802568ea  call    FGenerateDllName
0x1802568ef  xor     ebx, ebx
0x1802568f1  test    eax, eax
0x1802568f3  jnz     short loc_1802568F9
0x1802568f5  xor     eax, eax
0x1802568f7  jmp     short loc_1802568BF
0x1802568f9  lea     rax, [rbp+350h+Source]
0x180256900  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180256904  inc     rdi
0x180256907  cmp     [rax+rdi*2], bx
0x18025690b  jnz     short loc_180256904
0x18025690d  mov     rcx, cs:?g_hInstance@@3PEAXEA; hModule
0x180256914  lea     rdx, [rsp+450h+Filename]; lpFilename
0x180256919  mov     r8d, 104h; nSize
0x18025691f  call    cs:__imp_GetModuleFileNameW
0x180256925  movsxd  rcx, eax
0x180256928  add     rcx, rcx
0x18025692b  cmp     rcx, 20Ah
0x180256932  jnb     loc_1802569CC
0x180256938  mov     [rsp+rcx+450h+Filename], bx
0x18025693d  test    eax, eax
0x18025693f  jz      short loc_1802569B4
0x180256941  mov     edx, 5Ch ; '\'; Ch
0x180256946  lea     rcx, [rsp+450h+Filename]; Str
0x18025694b  call    cs:__imp_wcsrchr
0x180256951  mov     r9, rax
0x180256954  test    rax, rax
0x180256957  jz      short loc_1802569B4
0x180256959  lea     rdx, [rbp+350h+var_226]
0x180256960  movsxd  rcx, edi
0x180256963  sub     rdx, rax
0x180256966  sar     rdx, 1
0x180256969  sub     rdx, 2
0x18025696d  cmp     rdx, rcx
0x180256970  jl      short loc_1802569B4
0x180256972  lea     rcx, [rsp+450h+Filename]
0x180256977  mov     edx, 105h
0x18025697c  sub     rax, rcx
0x18025697f  lea     r8, [rbp+350h+Source]; Source
0x180256986  add     rax, 2
0x18025698a  lea     rcx, [r9+2]; Destination
0x18025698e  sar     rax, 1
0x180256991  sub     rdx, rax; SizeInWords
0x180256994  call    cs:__imp_wcscpy_s
0x18025699a  xor     edx, edx; hFile
0x18025699c  lea     rcx, [rsp+450h+Filename]; lpLibFileName
0x1802569a1  lea     r8d, [rdx+60h]; dwFlags
0x1802569a5  call    cs:__imp_LoadLibraryExW
0x1802569ab  test    rax, rax
0x1802569ae  jnz     loc_1802568BF
0x1802569b4  xor     edx, edx; hFile
0x1802569b6  lea     rcx, [rbp+350h+Source]; lpLibFileName
0x1802569bd  lea     r8d, [rdx+60h]; dwFlags
0x1802569c1  call    cs:__imp_LoadLibraryExW
0x1802569c7  jmp     loc_1802568BF
0x1802569cc  call    __report_rangecheckfailure
```
