# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(unsigned __int64,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>> &)

- ea: `0x180009e70`
- end: `0x18000a018`
- name: `?GetAt@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJ_KAEAV?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z`
- size: `424`
- prototype: `int __fastcall(__int64, DWORD, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180006330`
- `0x180006354`
- `0x180006e9c`
- `0x180009380`
- `0x180009e70`
- `0x18000b164`
- `0x18000cc34`
- `0x18000cc58`
- `0x18000ef6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009ecd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009ecd`

## string_xrefs

- `0x180009ee2`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180009f7b`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180009fb0`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetAt(
        __int64 a1,
        DWORD a2,
        __int64 a3)
{
  unsigned int v5; // eax
  char *v7; // rax
  Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *v8; // rbx
  int v9; // ebx
  int v10; // eax
  int v11; // edi
  unsigned int lpReserved; // [rsp+20h] [rbp-168h]
  DWORD cchName; // [rsp+40h] [rbp-148h] BYREF
  Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *v14; // [rsp+48h] [rbp-140h]
  char *v15; // [rsp+50h] [rbp-138h]
  char *v16; // [rsp+58h] [rbp-130h]
  WCHAR Name[128]; // [rsp+60h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  cchName = 128;
  v5 = RegEnumKeyExW(*(HKEY *)(a1 + 8), a2, Name, &cchName, 0, 0, 0, 0);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x141,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             (const char *)v5,
             lpReserved);
  v7 = (char *)operator new(0x118u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *)v7;
  v15 = v7;
  if ( v7 )
  {
    *(_QWORD *)v7 = &Windows::Internal::PlatformExtensions::Details::ExtensionRegistration::`vftable';
    *(_QWORD *)v7 = &Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable';
    v16 = v7 + 8;
    *((_QWORD *)v7 + 1) = 0;
    v7[16] = 0;
    *((_DWORD *)v7 + 5) = 0;
    *((_WORD *)v7 + 12) = 0;
    memset_0(v7 + 26, 0, 0xFEu);
  }
  else
  {
    v8 = 0;
  }
  v14 = v8;
  if ( v8 )
  {
    v10 = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
            v8,
            *(HKEY *)(a1 + 8),
            Name);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)v10,
        lpReserved);
      v14 = 0;
      Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(
        (HKEY *)v8,
        1);
      return v11;
    }
    v14 = 0;
    wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
      a3,
      v8);
    return 0;
  }
  else
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000ELL,
      lpReserved);
  }
  return v9;
}

```

## disassembly

```asm
0x180009e70  push    rbx
0x180009e72  push    rsi
0x180009e73  push    rdi
0x180009e74  sub     rsp, 170h
0x180009e7b  mov     rax, cs:__security_cookie
0x180009e82  xor     rax, rsp
0x180009e85  mov     [rsp+188h+var_28], rax
0x180009e8d  mov     rsi, r8
0x180009e90  mov     rdi, rcx
0x180009e93  mov     [rsp+188h+cchName], 80h
0x180009e9b  mov     [rsp+188h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180009ea4  mov     [rsp+188h+lpcchClass], 0; lpcchClass
0x180009ead  mov     [rsp+188h+lpClass], 0; lpClass
0x180009eb6  mov     [rsp+188h+lpReserved], 0; int
0x180009ebf  lea     r9, [rsp+188h+cchName]; lpcchName
0x180009ec4  lea     r8, [rsp+188h+Name]; lpName
0x180009ec9  mov     rcx, [rcx+8]; hKey
0x180009ecd  call    cs:__imp_RegEnumKeyExW
0x180009ed3  test    eax, eax
0x180009ed5  jz      short loc_180009EF8
0x180009ed7  mov     rcx, [rsp+188h]; this
0x180009edf  mov     r9d, eax; char *
0x180009ee2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180009ee9  mov     edx, 141h; void *
0x180009eee  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009ef3  jmp     loc_180009FFD
0x180009ef8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009eff  mov     ecx, 118h; unsigned __int64
0x180009f04  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009f09  mov     rbx, rax
0x180009f0c  mov     [rsp+188h+var_138], rax
0x180009f11  test    rax, rax
0x180009f14  jz      short loc_180009F5F
0x180009f16  lea     rax, ??_7ExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistration::`vftable'
0x180009f1d  mov     [rbx], rax
0x180009f20  lea     rax, ??_7ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`vftable'
0x180009f27  mov     [rbx], rax
0x180009f2a  lea     rax, [rbx+8]
0x180009f2e  mov     [rsp+188h+var_130], rax
0x180009f33  mov     qword ptr [rax], 0
0x180009f3a  mov     byte ptr [rbx+10h], 0
0x180009f3e  mov     dword ptr [rbx+14h], 0
0x180009f45  xor     eax, eax
0x180009f47  mov     [rbx+18h], ax
0x180009f4b  lea     rcx, [rbx+1Ah]; void *
0x180009f4f  xor     edx, edx; Val
0x180009f51  mov     r8d, 0FEh; Size
0x180009f57  call    memset_0
0x180009f5c  nop
0x180009f5d  jmp     short loc_180009F61
0x180009f5f  xor     ebx, ebx
0x180009f61  mov     [rsp+188h+var_140], rbx
0x180009f66  test    rbx, rbx
0x180009f69  jnz     short loc_180009F8E
0x180009f6b  mov     rcx, [rsp+188h]; this
0x180009f73  mov     ebx, 8007000Eh
0x180009f78  mov     r9d, ebx; char *
0x180009f7b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180009f82  mov     edx, 143h; void *
0x180009f87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f8c  jmp     short loc_180009FF2
0x180009f8e  lea     r8, [rsp+188h+Name]; unsigned __int16 *
0x180009f93  mov     rdx, [rdi+8]; HKEY
0x180009f97  mov     rcx, rbx; this
0x180009f9a  call    ?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)
0x180009f9f  mov     edi, eax
0x180009fa1  test    eax, eax
0x180009fa3  jns     short loc_180009FDC
0x180009fa5  mov     rcx, [rsp+188h]; this
0x180009fad  mov     r9d, eax; char *
0x180009fb0  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180009fb7  mov     edx, 144h; void *
0x180009fbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fc1  nop
0x180009fc2  mov     [rsp+188h+var_140], 0
0x180009fcb  mov     edx, 1; unsigned int
0x180009fd0  mov     rcx, rbx; this
0x180009fd3  call    ??_GExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEAAPEAXI@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::`scalar deleting destructor'(uint)
0x180009fd8  mov     eax, edi
0x180009fda  jmp     short loc_180009FFD
0x180009fdc  mov     [rsp+188h+var_140], 0
0x180009fe5  mov     rdx, rbx
0x180009fe8  mov     rcx, rsi
0x180009feb  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x180009ff0  xor     ebx, ebx
0x180009ff2  mov     [rsp+188h+var_140], 0
0x180009ffb  mov     eax, ebx
0x180009ffd  mov     rcx, [rsp+188h+var_28]
0x18000a005  xor     rcx, rsp; StackCookie
0x18000a008  call    __security_check_cookie
0x18000a00d  add     rsp, 170h
0x18000a014  pop     rdi
0x18000a015  pop     rsi
0x18000a016  pop     rbx
0x18000a017  retn
```
