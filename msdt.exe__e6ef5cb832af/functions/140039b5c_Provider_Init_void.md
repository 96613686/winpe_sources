# Provider::Init(void)

- ea: `0x140039b5c`
- end: `0x140039c75`
- name: `?Init@Provider@@QEAAJXZ`
- size: `281`
- prototype: `__int64 __fastcall(Provider *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400392b0`
- `0x1400398c0`

## callees

- `0x140020420`
- `0x140039b5c`
- `0x140061c90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140039bd5`
- `KERNEL32!GetLastError` at `0x140039bd5`
- `KERNEL32!GetProcAddress` at `0x140039c22`
- `KERNEL32!GetProcAddress` at `0x140039c22`
- `KERNEL32!LoadLibraryW` at `0x140039bae`
- `KERNEL32!LoadLibraryW` at `0x140039bae`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140039b97`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140039b97`

## string_xrefs

- `0x140039b85`: `%windir%\system32\sdiagprv.dll`
- `0x140039c18`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall Provider::Init(Provider *this)
{
  unsigned int v2; // ebx
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  Dst[0] = 0;
  if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\sdiagprv.dll", Dst, 0x104u) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) != 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Provider::Init", 95, v2);
      return v2;
    }
  }
  else
  {
    v2 = 0;
  }
  LibraryW = LoadLibraryW(Dst);
  *(_QWORD *)this = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "DllGetClassObject");
    if ( ProcAddress )
    {
      *((_QWORD *)this + 2) = ProcAddress;
      *((_DWORD *)this + 2) = 1;
    }
    else
    {
      v2 = -2147418113;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Provider::Init", 103, -2147418113);
    }
  }
  else
  {
    v2 = -2147418113;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Provider::Init", 98, -2147418113);
  }
  return v2;
}

```

## disassembly

```asm
0x140039b5c  mov     [rsp+arg_8], rbx
0x140039b61  push    rdi
0x140039b62  sub     rsp, 250h
0x140039b69  mov     rax, cs:__security_cookie
0x140039b70  xor     rax, rsp
0x140039b73  mov     [rsp+258h+var_18], rax
0x140039b7b  mov     rdi, rcx
0x140039b7e  lea     rdx, [rsp+258h+Dst]; lpDst
0x140039b83  xor     eax, eax
0x140039b85  lea     rcx, Src; "%windir%\\system32\\sdiagprv.dll"
0x140039b8c  mov     r8d, 104h; nSize
0x140039b92  mov     [rsp+258h+Dst], ax
0x140039b97  call    cs:__imp_ExpandEnvironmentStringsW
0x140039b9e  nop     dword ptr [rax+rax+00h]
0x140039ba3  test    eax, eax
0x140039ba5  jnz     short loc_140039BD5
0x140039ba7  xor     ebx, ebx
0x140039ba9  lea     rcx, [rsp+258h+Dst]; lpLibFileName
0x140039bae  call    cs:__imp_LoadLibraryW
0x140039bb5  nop     dword ptr [rax+rax+00h]
0x140039bba  mov     [rdi], rax
0x140039bbd  test    rax, rax
0x140039bc0  jnz     short loc_140039C18
0x140039bc2  mov     eax, 8000FFFFh
0x140039bc7  mov     r9d, 62h ; 'b'
0x140039bcd  mov     ebx, eax
0x140039bcf  mov     [rsp+258h+var_238], eax
0x140039bd3  jmp     short loc_140039BFE
0x140039bd5  call    cs:__imp_GetLastError
0x140039bdc  nop     dword ptr [rax+rax+00h]
0x140039be1  mov     ebx, eax
0x140039be3  test    eax, eax
0x140039be5  jle     short loc_140039BF0
0x140039be7  movzx   ebx, ax
0x140039bea  or      ebx, 80070000h
0x140039bf0  test    ebx, ebx
0x140039bf2  jns     short loc_140039BA9
0x140039bf4  mov     [rsp+258h+var_238], ebx
0x140039bf8  mov     r9d, 5Fh ; '_'
0x140039bfe  lea     r8, aProviderInit; "Provider::Init"
0x140039c05  mov     ecx, 1; Level
0x140039c0a  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140039c11  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140039c16  jmp     short loc_140039C51
0x140039c18  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x140039c1f  mov     rcx, rax; hModule
0x140039c22  call    cs:__imp_GetProcAddress
0x140039c29  nop     dword ptr [rax+rax+00h]
0x140039c2e  test    rax, rax
0x140039c31  jnz     short loc_140039C46
0x140039c33  mov     eax, 8000FFFFh
0x140039c38  mov     r9d, 67h ; 'g'
0x140039c3e  mov     ebx, eax
0x140039c40  mov     [rsp+258h+var_238], eax
0x140039c44  jmp     short loc_140039BFE
0x140039c46  mov     [rdi+10h], rax
0x140039c4a  mov     dword ptr [rdi+8], 1
0x140039c51  mov     eax, ebx
0x140039c53  mov     rcx, [rsp+258h+var_18]
0x140039c5b  xor     rcx, rsp; StackCookie
0x140039c5e  call    __security_check_cookie
0x140039c63  mov     rbx, [rsp+258h+arg_8]
0x140039c6b  add     rsp, 250h
0x140039c72  pop     rdi
0x140039c73  retn
```
