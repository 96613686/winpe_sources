# CTscAuthenticationBlob::LoadMemoryProtectionFunctions(void)

- ea: `0x140094860`
- end: `0x140094a7d`
- name: `?LoadMemoryProtectionFunctions@CTscAuthenticationBlob@@IEAAHXZ`
- size: `541`
- prototype: `__int64 __fastcall(CTscAuthenticationBlob *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140094440`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x140094860`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14009487a`
- `KERNEL32!LoadLibraryW` at `0x140094974`
- `KERNEL32!LoadLibraryW` at `0x14009487a`
- `KERNEL32!LoadLibraryW` at `0x140094974`
- `KERNEL32!FreeLibrary` at `0x140094967`
- `KERNEL32!FreeLibrary` at `0x140094a63`
- `KERNEL32!FreeLibrary` at `0x140094967`
- `KERNEL32!FreeLibrary` at `0x140094a63`
- `KERNEL32!GetProcAddress` at `0x14009489d`
- `KERNEL32!GetProcAddress` at `0x1400948f2`
- `KERNEL32!GetProcAddress` at `0x140094990`
- `KERNEL32!GetProcAddress` at `0x1400949e5`
- `KERNEL32!GetProcAddress` at `0x14009489d`
- `KERNEL32!GetProcAddress` at `0x1400948f2`
- `KERNEL32!GetProcAddress` at `0x140094990`
- `KERNEL32!GetProcAddress` at `0x1400949e5`

## string_xrefs

- `0x14009496d`: `advapi32.dll`
- `0x140094873`: `crypt32.dll`

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
0x140094860  mov     [rsp+arg_0], rbx
0x140094865  mov     [rsp+arg_8], rdi
0x14009486a  push    r15
0x14009486c  sub     rsp, 20h
0x140094870  mov     rbx, rcx
0x140094873  lea     rcx, aCrypt32Dll_0; "crypt32.dll"
0x14009487a  call    cs:__imp_LoadLibraryW
0x140094880  lea     r15, WPP_GLOBAL_Control
0x140094887  mov     rdi, rax
0x14009488a  test    rax, rax
0x14009488d  jz      loc_14009493D
0x140094893  lea     rdx, aCryptprotectme; "CryptProtectMemory"
0x14009489a  mov     rcx, rax; hModule
0x14009489d  call    cs:__imp_GetProcAddress
0x1400948a3  mov     [rbx+58h], rax
0x1400948a7  test    rax, rax
0x1400948aa  jnz     short loc_1400948E8
0x1400948ac  mov     rax, cs:WPP_GLOBAL_Control
0x1400948b3  cmp     rax, r15
0x1400948b6  jz      short loc_1400948E8
0x1400948b8  test    byte ptr [rax+1Ch], 1
0x1400948bc  jz      short loc_1400948E8
0x1400948be  cmp     byte ptr [rax+19h], 3
0x1400948c2  jb      short loc_1400948E8
0x1400948c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400948c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400948d0  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x1400948d7  mov     edx, 10h
0x1400948dc  mov     r9d, eax
0x1400948df  mov     rcx, [rcx+10h]
0x1400948e3  call    WPP_SF_d
0x1400948e8  lea     rdx, aCryptunprotect_0; "CryptUnprotectMemory"
0x1400948ef  mov     rcx, rdi; hModule
0x1400948f2  call    cs:__imp_GetProcAddress
0x1400948f8  mov     [rbx+60h], rax
0x1400948fc  test    rax, rax
0x1400948ff  jnz     short loc_14009493D
0x140094901  mov     rax, cs:WPP_GLOBAL_Control
0x140094908  cmp     rax, r15
0x14009490b  jz      short loc_14009493D
0x14009490d  test    byte ptr [rax+1Ch], 1
0x140094911  jz      short loc_14009493D
0x140094913  cmp     byte ptr [rax+19h], 3
0x140094917  jb      short loc_14009493D
0x140094919  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009491e  mov     rcx, cs:WPP_GLOBAL_Control
0x140094925  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x14009492c  mov     edx, 11h
0x140094931  mov     r9d, eax
0x140094934  mov     rcx, [rcx+10h]
0x140094938  call    WPP_SF_d
0x14009493d  cmp     qword ptr [rbx+58h], 0
0x140094942  jz      short loc_14009494F
0x140094944  cmp     qword ptr [rbx+60h], 0
0x140094949  jnz     loc_140094A3E
0x14009494f  mov     qword ptr [rbx+58h], 0
0x140094957  mov     qword ptr [rbx+60h], 0
0x14009495f  test    rdi, rdi
0x140094962  jz      short loc_14009496D
0x140094964  mov     rcx, rdi; hLibModule
0x140094967  call    cs:__imp_FreeLibrary
0x14009496d  lea     rcx, LibFileName; "advapi32.dll"
0x140094974  call    cs:__imp_LoadLibraryW
0x14009497a  mov     rdi, rax
0x14009497d  test    rax, rax
0x140094980  jz      loc_140094A30
0x140094986  lea     rdx, aSystemfunction_0; "SystemFunction040"
0x14009498d  mov     rcx, rax; hModule
0x140094990  call    cs:__imp_GetProcAddress
0x140094996  mov     [rbx+48h], rax
0x14009499a  test    rax, rax
0x14009499d  jnz     short loc_1400949DB
0x14009499f  mov     rax, cs:WPP_GLOBAL_Control
0x1400949a6  cmp     rax, r15
0x1400949a9  jz      short loc_1400949DB
0x1400949ab  test    byte ptr [rax+1Ch], 1
0x1400949af  jz      short loc_1400949DB
0x1400949b1  cmp     byte ptr [rax+19h], 3
0x1400949b5  jb      short loc_1400949DB
0x1400949b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400949bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400949c3  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x1400949ca  mov     edx, 12h
0x1400949cf  mov     r9d, eax
0x1400949d2  mov     rcx, [rcx+10h]
0x1400949d6  call    WPP_SF_d
0x1400949db  lea     rdx, aSystemfunction; "SystemFunction041"
0x1400949e2  mov     rcx, rdi; hModule
0x1400949e5  call    cs:__imp_GetProcAddress
0x1400949eb  mov     [rbx+50h], rax
0x1400949ef  test    rax, rax
0x1400949f2  jnz     short loc_140094A30
0x1400949f4  mov     rax, cs:WPP_GLOBAL_Control
0x1400949fb  cmp     rax, r15
0x1400949fe  jz      short loc_140094A30
0x140094a00  test    byte ptr [rax+1Ch], 1
0x140094a04  jz      short loc_140094A30
0x140094a06  cmp     byte ptr [rax+19h], 3
0x140094a0a  jb      short loc_140094A30
0x140094a0c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140094a11  mov     rcx, cs:WPP_GLOBAL_Control
0x140094a18  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140094a1f  mov     edx, 13h
0x140094a24  mov     r9d, eax
0x140094a27  mov     rcx, [rcx+10h]
0x140094a2b  call    WPP_SF_d
0x140094a30  cmp     qword ptr [rbx+48h], 0
0x140094a35  jz      short loc_140094A4B
0x140094a37  cmp     qword ptr [rbx+50h], 0
0x140094a3c  jz      short loc_140094A4B
0x140094a3e  mov     dword ptr [rbx+68h], 1
0x140094a45  mov     [rbx+70h], rdi
0x140094a49  jmp     short loc_140094A69
0x140094a4b  mov     qword ptr [rbx+48h], 0
0x140094a53  mov     qword ptr [rbx+50h], 0
0x140094a5b  test    rdi, rdi
0x140094a5e  jz      short loc_140094A69
0x140094a60  mov     rcx, rdi; hLibModule
0x140094a63  call    cs:__imp_FreeLibrary
0x140094a69  mov     eax, [rbx+68h]
0x140094a6c  mov     rbx, [rsp+28h+arg_0]
0x140094a71  mov     rdi, [rsp+28h+arg_8]
0x140094a76  add     rsp, 20h
0x140094a7a  pop     r15
0x140094a7c  retn
```
