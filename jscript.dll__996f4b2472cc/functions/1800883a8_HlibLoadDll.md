# HlibLoadDll

- ea: `0x1800883a8`
- end: `0x1800884fd`
- name: `HlibLoadDll`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180040fa8`

## callees

- `0x180058dc8`
- `0x18008820c`
- `0x1800883a8`
- `0x1800966e0`

## import_xrefs

- `msvcrt!strrchr` at `0x180088471`
- `msvcrt!strrchr` at `0x180088471`
- `msvcrt!strcpy_s` at `0x1800884ac`
- `msvcrt!strcpy_s` at `0x1800884ac`
- `KERNEL32!LoadLibraryExA` at `0x1800884c3`
- `KERNEL32!LoadLibraryExA` at `0x1800884e6`
- `KERNEL32!LoadLibraryExA` at `0x1800884c3`
- `KERNEL32!LoadLibraryExA` at `0x1800884e6`
- `KERNEL32!GetModuleFileNameA` at `0x180088442`
- `KERNEL32!GetModuleFileNameA` at `0x180088442`

## pseudocode

```c
HMODULE __fastcall HlibLoadDll(__int16 a1, _DWORD *a2)
{
  HMODULE result; // rax
  __int64 v3; // rbx
  signed int ModuleFileNameA; // eax
  __int64 v5; // rdx
  char *v6; // rax
  CHAR Filename[272]; // [rsp+20h] [rbp-238h] BYREF
  CHAR Source[272]; // [rsp+130h] [rbp-128h] BYREF

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
    ModuleFileNameA = GetModuleFileNameA(g_hInstance, Filename, 0x104u);
    if ( (unsigned __int64)ModuleFileNameA >= 0x105 )
      _report_rangecheckfailure(ModuleFileNameA, v5);
    Filename[ModuleFileNameA] = 0;
    if ( !ModuleFileNameA )
      return LoadLibraryExA(Source, 0, 0x60u);
    v6 = strrchr(Filename, 92);
    if ( !v6 )
      return LoadLibraryExA(Source, 0, 0x60u);
    if ( Filename - v6 + 259 < (int)v3 )
      return LoadLibraryExA(Source, 0, 0x60u);
    strcpy_s(v6 + 1, Filename - v6 + 260, Source);
    result = LoadLibraryExA(Filename, 0, 0x60u);
    if ( !result )
      return LoadLibraryExA(Source, 0, 0x60u);
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
0x1800883a8  push    rbx
0x1800883aa  sub     rsp, 250h
0x1800883b1  mov     rax, cs:__security_cookie
0x1800883b8  xor     rax, rsp
0x1800883bb  mov     [rsp+258h+var_18], rax
0x1800883c3  movzx   eax, cx
0x1800883c6  mov     dword ptr [rdx], 1
0x1800883cc  mov     r8d, 3FFh
0x1800883d2  and     ax, r8w
0x1800883d6  cmp     ax, 9
0x1800883da  jnz     short loc_180088403
0x1800883dc  mov     rax, cs:?g_hInstance@@3PEAXEA; void * g_hInstance
0x1800883e3  mov     dword ptr [rdx], 0
0x1800883e9  mov     rcx, [rsp+258h+var_18]
0x1800883f1  xor     rcx, rsp; StackCookie
0x1800883f4  call    __security_check_cookie
0x1800883f9  add     rsp, 250h
0x180088400  pop     rbx
0x180088401  retn
0x180088403  mov     r8d, ecx
0x180088406  lea     rcx, [rsp+258h+Source]; Destination
0x18008840e  call    FGenerateDllName
0x180088413  test    eax, eax
0x180088415  jnz     short loc_18008841B
0x180088417  xor     eax, eax
0x180088419  jmp     short loc_1800883E9
0x18008841b  lea     rax, [rsp+258h+Source]
0x180088423  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180088427  inc     rbx
0x18008842a  cmp     byte ptr [rax+rbx], 0
0x18008842e  jnz     short loc_180088427
0x180088430  mov     rcx, cs:?g_hInstance@@3PEAXEA; hModule
0x180088437  lea     rdx, [rsp+258h+Filename]; lpFilename
0x18008843c  mov     r8d, 104h; nSize
0x180088442  call    cs:__imp_GetModuleFileNameA
0x180088449  nop     dword ptr [rax+rax+00h]
0x18008844e  movsxd  rcx, eax
0x180088451  cmp     rcx, 105h
0x180088458  jnb     loc_1800884F7
0x18008845e  mov     [rsp+rcx+258h+Filename], 0
0x180088463  test    eax, eax
0x180088465  jz      short loc_1800884D8
0x180088467  mov     edx, 5Ch ; '\'; Ch
0x18008846c  lea     rcx, [rsp+258h+Filename]; Str
0x180088471  call    cs:__imp_strrchr
0x180088478  nop     dword ptr [rax+rax+00h]
0x18008847d  test    rax, rax
0x180088480  jz      short loc_1800884D8
0x180088482  lea     r9, [rsp+258h+Filename]
0x180088487  movsxd  rcx, ebx
0x18008848a  sub     r9, rax
0x18008848d  lea     rdx, [r9+103h]
0x180088494  cmp     rdx, rcx
0x180088497  jl      short loc_1800884D8
0x180088499  lea     rdx, [r9+104h]; SizeInBytes
0x1800884a0  lea     rcx, [rax+1]; Destination
0x1800884a4  lea     r8, [rsp+258h+Source]; Source
0x1800884ac  call    cs:__imp_strcpy_s
0x1800884b3  nop     dword ptr [rax+rax+00h]
0x1800884b8  xor     edx, edx; hFile
0x1800884ba  lea     rcx, [rsp+258h+Filename]; lpLibFileName
0x1800884bf  lea     r8d, [rdx+60h]; dwFlags
0x1800884c3  call    cs:__imp_LoadLibraryExA
0x1800884ca  nop     dword ptr [rax+rax+00h]
0x1800884cf  test    rax, rax
0x1800884d2  jnz     loc_1800883E9
0x1800884d8  xor     edx, edx; hFile
0x1800884da  lea     rcx, [rsp+258h+Source]; lpLibFileName
0x1800884e2  lea     r8d, [rdx+60h]; dwFlags
0x1800884e6  call    cs:__imp_LoadLibraryExA
0x1800884ed  nop     dword ptr [rax+rax+00h]
0x1800884f2  jmp     loc_1800883E9
0x1800884f7  call    __report_rangecheckfailure
```
