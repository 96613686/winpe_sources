# CTscAuthenticationBlob::LoadMemoryProtectionFunctions(void)

- ea: `0x1400969d0`
- end: `0x140096bed`
- name: `?LoadMemoryProtectionFunctions@CTscAuthenticationBlob@@IEAAHXZ`
- size: `541`
- prototype: `__int64 __fastcall(CTscAuthenticationBlob *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400965b0`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x1400969d0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1400969ea`
- `KERNEL32!LoadLibraryW` at `0x140096ae4`
- `KERNEL32!LoadLibraryW` at `0x1400969ea`
- `KERNEL32!LoadLibraryW` at `0x140096ae4`
- `KERNEL32!FreeLibrary` at `0x140096ad7`
- `KERNEL32!FreeLibrary` at `0x140096bd3`
- `KERNEL32!FreeLibrary` at `0x140096ad7`
- `KERNEL32!FreeLibrary` at `0x140096bd3`
- `KERNEL32!GetProcAddress` at `0x140096a0d`
- `KERNEL32!GetProcAddress` at `0x140096a62`
- `KERNEL32!GetProcAddress` at `0x140096b00`
- `KERNEL32!GetProcAddress` at `0x140096b55`
- `KERNEL32!GetProcAddress` at `0x140096a0d`
- `KERNEL32!GetProcAddress` at `0x140096a62`
- `KERNEL32!GetProcAddress` at `0x140096b00`
- `KERNEL32!GetProcAddress` at `0x140096b55`

## string_xrefs

- `0x140096add`: `advapi32.dll`
- `0x1400969e3`: `crypt32.dll`

## pseudocode

```c
__int64 __fastcall CTscAuthenticationBlob::LoadMemoryProtectionFunctions(CTscAuthenticationBlob *this)
{
  HMODULE LibraryW; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  FARPROC v6; // rax
  unsigned int v7; // eax
  HMODULE v8; // rax
  FARPROC v9; // rax
  unsigned int v10; // eax
  FARPROC v11; // rax
  unsigned int v12; // eax

  LibraryW = LoadLibraryW(L"crypt32.dll");
  v3 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "CryptProtectMemory");
    *((_QWORD *)this + 11) = ProcAddress;
    if ( !ProcAddress
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    v6 = GetProcAddress(v3, "CryptUnprotectMemory");
    *((_QWORD *)this + 12) = v6;
    if ( !v6
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids, v7);
    }
  }
  if ( *((_QWORD *)this + 11) && *((_QWORD *)this + 12) )
    goto LABEL_29;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  if ( v3 )
    FreeLibrary(v3);
  v8 = LoadLibraryW(L"advapi32.dll");
  v3 = v8;
  if ( v8 )
  {
    v9 = GetProcAddress(v8, "SystemFunction040");
    *((_QWORD *)this + 9) = v9;
    if ( !v9
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids, v10);
    }
    v11 = GetProcAddress(v3, "SystemFunction041");
    *((_QWORD *)this + 10) = v11;
    if ( !v11
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids, v12);
    }
  }
  if ( *((_QWORD *)this + 9) && *((_QWORD *)this + 10) )
  {
LABEL_29:
    *((_DWORD *)this + 26) = 1;
    *((_QWORD *)this + 14) = v3;
  }
  else
  {
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    if ( v3 )
      FreeLibrary(v3);
  }
  return *((unsigned int *)this + 26);
}

```

## disassembly

```asm
0x1400969d0  mov     [rsp+arg_0], rbx
0x1400969d5  mov     [rsp+arg_8], rdi
0x1400969da  push    r15
0x1400969dc  sub     rsp, 20h
0x1400969e0  mov     rbx, rcx
0x1400969e3  lea     rcx, aCrypt32Dll_0; "crypt32.dll"
0x1400969ea  call    cs:__imp_LoadLibraryW
0x1400969f0  lea     r15, WPP_GLOBAL_Control
0x1400969f7  mov     rdi, rax
0x1400969fa  test    rax, rax
0x1400969fd  jz      loc_140096AAD
0x140096a03  lea     rdx, aCryptprotectme; "CryptProtectMemory"
0x140096a0a  mov     rcx, rax; hModule
0x140096a0d  call    cs:__imp_GetProcAddress
0x140096a13  mov     [rbx+58h], rax
0x140096a17  test    rax, rax
0x140096a1a  jnz     short loc_140096A58
0x140096a1c  mov     rax, cs:WPP_GLOBAL_Control
0x140096a23  cmp     rax, r15
0x140096a26  jz      short loc_140096A58
0x140096a28  test    byte ptr [rax+1Ch], 1
0x140096a2c  jz      short loc_140096A58
0x140096a2e  cmp     byte ptr [rax+19h], 3
0x140096a32  jb      short loc_140096A58
0x140096a34  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140096a39  mov     rcx, cs:WPP_GLOBAL_Control
0x140096a40  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140096a47  mov     edx, 10h
0x140096a4c  mov     r9d, eax
0x140096a4f  mov     rcx, [rcx+10h]
0x140096a53  call    WPP_SF_d
0x140096a58  lea     rdx, aCryptunprotect_0; "CryptUnprotectMemory"
0x140096a5f  mov     rcx, rdi; hModule
0x140096a62  call    cs:__imp_GetProcAddress
0x140096a68  mov     [rbx+60h], rax
0x140096a6c  test    rax, rax
0x140096a6f  jnz     short loc_140096AAD
0x140096a71  mov     rax, cs:WPP_GLOBAL_Control
0x140096a78  cmp     rax, r15
0x140096a7b  jz      short loc_140096AAD
0x140096a7d  test    byte ptr [rax+1Ch], 1
0x140096a81  jz      short loc_140096AAD
0x140096a83  cmp     byte ptr [rax+19h], 3
0x140096a87  jb      short loc_140096AAD
0x140096a89  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140096a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140096a95  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140096a9c  mov     edx, 11h
0x140096aa1  mov     r9d, eax
0x140096aa4  mov     rcx, [rcx+10h]
0x140096aa8  call    WPP_SF_d
0x140096aad  cmp     qword ptr [rbx+58h], 0
0x140096ab2  jz      short loc_140096ABF
0x140096ab4  cmp     qword ptr [rbx+60h], 0
0x140096ab9  jnz     loc_140096BAE
0x140096abf  mov     qword ptr [rbx+58h], 0
0x140096ac7  mov     qword ptr [rbx+60h], 0
0x140096acf  test    rdi, rdi
0x140096ad2  jz      short loc_140096ADD
0x140096ad4  mov     rcx, rdi; hLibModule
0x140096ad7  call    cs:__imp_FreeLibrary
0x140096add  lea     rcx, LibFileName; "advapi32.dll"
0x140096ae4  call    cs:__imp_LoadLibraryW
0x140096aea  mov     rdi, rax
0x140096aed  test    rax, rax
0x140096af0  jz      loc_140096BA0
0x140096af6  lea     rdx, aSystemfunction_0; "SystemFunction040"
0x140096afd  mov     rcx, rax; hModule
0x140096b00  call    cs:__imp_GetProcAddress
0x140096b06  mov     [rbx+48h], rax
0x140096b0a  test    rax, rax
0x140096b0d  jnz     short loc_140096B4B
0x140096b0f  mov     rax, cs:WPP_GLOBAL_Control
0x140096b16  cmp     rax, r15
0x140096b19  jz      short loc_140096B4B
0x140096b1b  test    byte ptr [rax+1Ch], 1
0x140096b1f  jz      short loc_140096B4B
0x140096b21  cmp     byte ptr [rax+19h], 3
0x140096b25  jb      short loc_140096B4B
0x140096b27  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140096b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140096b33  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140096b3a  mov     edx, 12h
0x140096b3f  mov     r9d, eax
0x140096b42  mov     rcx, [rcx+10h]
0x140096b46  call    WPP_SF_d
0x140096b4b  lea     rdx, aSystemfunction; "SystemFunction041"
0x140096b52  mov     rcx, rdi; hModule
0x140096b55  call    cs:__imp_GetProcAddress
0x140096b5b  mov     [rbx+50h], rax
0x140096b5f  test    rax, rax
0x140096b62  jnz     short loc_140096BA0
0x140096b64  mov     rax, cs:WPP_GLOBAL_Control
0x140096b6b  cmp     rax, r15
0x140096b6e  jz      short loc_140096BA0
0x140096b70  test    byte ptr [rax+1Ch], 1
0x140096b74  jz      short loc_140096BA0
0x140096b76  cmp     byte ptr [rax+19h], 3
0x140096b7a  jb      short loc_140096BA0
0x140096b7c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140096b81  mov     rcx, cs:WPP_GLOBAL_Control
0x140096b88  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140096b8f  mov     edx, 13h
0x140096b94  mov     r9d, eax
0x140096b97  mov     rcx, [rcx+10h]
0x140096b9b  call    WPP_SF_d
0x140096ba0  cmp     qword ptr [rbx+48h], 0
0x140096ba5  jz      short loc_140096BBB
0x140096ba7  cmp     qword ptr [rbx+50h], 0
0x140096bac  jz      short loc_140096BBB
0x140096bae  mov     dword ptr [rbx+68h], 1
0x140096bb5  mov     [rbx+70h], rdi
0x140096bb9  jmp     short loc_140096BD9
0x140096bbb  mov     qword ptr [rbx+48h], 0
0x140096bc3  mov     qword ptr [rbx+50h], 0
0x140096bcb  test    rdi, rdi
0x140096bce  jz      short loc_140096BD9
0x140096bd0  mov     rcx, rdi; hLibModule
0x140096bd3  call    cs:__imp_FreeLibrary
0x140096bd9  mov     eax, [rbx+68h]
0x140096bdc  mov     rbx, [rsp+28h+arg_0]
0x140096be1  mov     rdi, [rsp+28h+arg_8]
0x140096be6  add     rsp, 20h
0x140096bea  pop     r15
0x140096bec  retn
```
