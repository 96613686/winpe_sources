# HlibLoadDll

- ea: `0x1800865cc`
- end: `0x180086702`
- name: `HlibLoadDll`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002fff0`

## callees

- `0x180057e98`
- `0x18008644c`
- `0x1800865cc`
- `0x1800942d0`

## import_xrefs

- `msvcrt!strrchr` at `0x18008668e`
- `msvcrt!strrchr` at `0x18008668e`
- `msvcrt!strcpy_s` at `0x1800866c3`
- `msvcrt!strcpy_s` at `0x1800866c3`
- `KERNEL32!LoadLibraryExA` at `0x1800866d4`
- `KERNEL32!LoadLibraryExA` at `0x1800866f1`
- `KERNEL32!LoadLibraryExA` at `0x1800866d4`
- `KERNEL32!LoadLibraryExA` at `0x1800866f1`
- `KERNEL32!GetModuleFileNameA` at `0x180086665`
- `KERNEL32!GetModuleFileNameA` at `0x180086665`

## pseudocode

```c
HMODULE __fastcall HlibLoadDll(__int16 a1, _DWORD *a2)
{
  HMODULE result; // rax
  __int64 v3; // rbx
  signed int ModuleFileNameA; // eax
  char *v5; // rax
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
      _report_rangecheckfailure();
    Filename[ModuleFileNameA] = 0;
    if ( !ModuleFileNameA )
      return LoadLibraryExA(Source, 0, 0x60u);
    v5 = strrchr(Filename, 92);
    if ( !v5 )
      return LoadLibraryExA(Source, 0, 0x60u);
    if ( Filename - v5 + 259 < (int)v3 )
      return LoadLibraryExA(Source, 0, 0x60u);
    strcpy_s(v5 + 1, Filename - v5 + 260, Source);
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
0x1800865cc  push    rbx
0x1800865ce  sub     rsp, 250h
0x1800865d5  mov     rax, cs:__security_cookie
0x1800865dc  xor     rax, rsp
0x1800865df  mov     [rsp+258h+var_18], rax
0x1800865e7  movzx   eax, cx
0x1800865ea  mov     dword ptr [rdx], 1
0x1800865f0  mov     r8d, 3FFh
0x1800865f6  and     ax, r8w
0x1800865fa  cmp     ax, 9
0x1800865fe  jnz     short loc_180086626
0x180086600  mov     rax, cs:?g_hInstance@@3PEAXEA; void * g_hInstance
0x180086607  mov     dword ptr [rdx], 0
0x18008660d  mov     rcx, [rsp+258h+var_18]
0x180086615  xor     rcx, rsp; StackCookie
0x180086618  call    __security_check_cookie
0x18008661d  add     rsp, 250h
0x180086624  pop     rbx
0x180086625  retn
0x180086626  mov     r8d, ecx
0x180086629  lea     rcx, [rsp+258h+Source]; Destination
0x180086631  call    FGenerateDllName
0x180086636  test    eax, eax
0x180086638  jnz     short loc_18008663E
0x18008663a  xor     eax, eax
0x18008663c  jmp     short loc_18008660D
0x18008663e  lea     rax, [rsp+258h+Source]
0x180086646  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008664a  inc     rbx
0x18008664d  cmp     byte ptr [rax+rbx], 0
0x180086651  jnz     short loc_18008664A
0x180086653  mov     rcx, cs:?g_hInstance@@3PEAXEA; hModule
0x18008665a  lea     rdx, [rsp+258h+Filename]; lpFilename
0x18008665f  mov     r8d, 104h; nSize
0x180086665  call    cs:__imp_GetModuleFileNameA
0x18008666b  movsxd  rcx, eax
0x18008666e  cmp     rcx, 105h
0x180086675  jnb     loc_1800866FC
0x18008667b  mov     [rsp+rcx+258h+Filename], 0
0x180086680  test    eax, eax
0x180086682  jz      short loc_1800866E3
0x180086684  mov     edx, 5Ch ; '\'; Ch
0x180086689  lea     rcx, [rsp+258h+Filename]; Str
0x18008668e  call    cs:__imp_strrchr
0x180086694  test    rax, rax
0x180086697  jz      short loc_1800866E3
0x180086699  lea     r9, [rsp+258h+Filename]
0x18008669e  movsxd  rcx, ebx
0x1800866a1  sub     r9, rax
0x1800866a4  lea     rdx, [r9+103h]
0x1800866ab  cmp     rdx, rcx
0x1800866ae  jl      short loc_1800866E3
0x1800866b0  lea     rdx, [r9+104h]; SizeInBytes
0x1800866b7  lea     rcx, [rax+1]; Destination
0x1800866bb  lea     r8, [rsp+258h+Source]; Source
0x1800866c3  call    cs:__imp_strcpy_s
0x1800866c9  xor     edx, edx; hFile
0x1800866cb  lea     rcx, [rsp+258h+Filename]; lpLibFileName
0x1800866d0  lea     r8d, [rdx+60h]; dwFlags
0x1800866d4  call    cs:__imp_LoadLibraryExA
0x1800866da  test    rax, rax
0x1800866dd  jnz     loc_18008660D
0x1800866e3  xor     edx, edx; hFile
0x1800866e5  lea     rcx, [rsp+258h+Source]; lpLibFileName
0x1800866ed  lea     r8d, [rdx+60h]; dwFlags
0x1800866f1  call    cs:__imp_LoadLibraryExA
0x1800866f7  jmp     loc_18008660D
0x1800866fc  call    __report_rangecheckfailure
```
