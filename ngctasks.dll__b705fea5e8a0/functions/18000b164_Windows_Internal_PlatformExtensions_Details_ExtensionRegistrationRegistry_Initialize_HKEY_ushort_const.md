# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(HKEY__ *,ushort const *)

- ea: `0x18000b164`
- end: `0x18000b2d9`
- name: `?Initialize@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `373`
- prototype: `int __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180009e70`

## callees

- `0x180008b10`
- `0x18000b164`
- `0x18000cc34`
- `0x18000cc58`
- `0x18000e51c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b1bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b1bc`

## string_xrefs

- `0x18000b1e0`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18000b231`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18000b210`: `ExtensionClass`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::Initialize(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  HKEY *v4; // rdi
  unsigned int v5; // r14d
  int RegValue; // ebx
  __int64 v8; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  char *v11; // [rsp+38h] [rbp-18h] BYREF
  HKEY v12; // [rsp+40h] [rbp-10h] BYREF
  char v13; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned int v15; // [rsp+70h] [rbp+20h] BYREF
  int v16; // [rsp+88h] [rbp+38h] BYREF

  v4 = (HKEY *)((char *)this + 8);
  v11 = (char *)this + 8;
  v12 = 0;
  v13 = 1;
  v5 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &v12);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v11);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xE0,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             (const char *)v5,
             phkResult);
  v15 = 256;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               *v4,
               L"ExtensionClass",
               2u,
               (char *)this + 24,
               &v15);
  if ( RegValue < 0 )
  {
    v8 = 227;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)RegValue,
      phkResulta);
    return RegValue;
  }
  v16 = 0;
  v15 = 4;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               *v4,
               L"Test",
               0x10u,
               &v16,
               &v15);
  if ( RegValue < 0 )
  {
    v8 = 231;
    goto LABEL_5;
  }
  *((_BYTE *)this + 16) = v16 != 0;
  v15 = 4;
  RegValue = Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(
               *v4,
               L"VelocityFeatureId",
               0x10u,
               (char *)this + 20,
               &v15);
  if ( RegValue < 0 )
  {
    v8 = 235;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b164  mov     [rsp-18h+arg_8], rbx
0x18000b169  mov     [rsp-18h+arg_10], rsi
0x18000b16e  push    rbp
0x18000b16f  push    rdi
0x18000b170  push    r14
0x18000b172  mov     rbp, rsp
0x18000b175  sub     rsp, 50h
0x18000b179  mov     rax, r8
0x18000b17c  mov     r10, rdx
0x18000b17f  mov     rsi, rcx
0x18000b182  mov     [rbp+var_20], 0
0x18000b189  lea     rdi, [rcx+8]
0x18000b18d  mov     [rbp+var_18], rdi
0x18000b191  mov     [rbp+var_10], 0
0x18000b199  mov     ebx, 1
0x18000b19e  mov     [rbp+var_8], bl
0x18000b1a1  mov     [rbp+var_20], ebx
0x18000b1a4  lea     rcx, [rbp+var_10]
0x18000b1a8  mov     qword ptr [rsp+50h+phkResult], rcx; unsigned int
0x18000b1ad  mov     r9d, 20019h; samDesired
0x18000b1b3  xor     r8d, r8d; ulOptions
0x18000b1b6  mov     rdx, rax; lpSubKey
0x18000b1b9  mov     rcx, r10; hKey
0x18000b1bc  call    cs:__imp_RegOpenKeyExW
0x18000b1c2  mov     r14d, eax
0x18000b1c5  and     ebx, 0FFFFFFFEh
0x18000b1c8  mov     [rbp+var_20], ebx
0x18000b1cb  lea     rcx, [rbp+var_18]
0x18000b1cf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18000b1d4  test    r14d, r14d
0x18000b1d7  jz      short loc_18000B1F6
0x18000b1d9  mov     rcx, [rbp+18h]; this
0x18000b1dd  mov     r9d, r14d; char *
0x18000b1e0  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000b1e7  mov     edx, 0E0h; void *
0x18000b1ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b1f1  jmp     loc_18000B2C4
0x18000b1f6  mov     [rbp+arg_0], 100h
0x18000b1fd  lea     r9, [rsi+18h]; void *
0x18000b201  lea     rax, [rbp+arg_0]
0x18000b205  mov     qword ptr [rsp+50h+phkResult], rax; int
0x18000b20a  mov     r8d, 2; unsigned int
0x18000b210  lea     rdx, aExtensionclass; "ExtensionClass"
0x18000b217  mov     rcx, [rdi]; HKEY
0x18000b21a  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x18000b21f  mov     ebx, eax
0x18000b221  test    eax, eax
0x18000b223  jns     short loc_18000B244
0x18000b225  mov     edx, 0E3h; void *
0x18000b22a  mov     rcx, [rbp+18h]; this
0x18000b22e  mov     r9d, ebx; char *
0x18000b231  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000b238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b23d  mov     eax, ebx
0x18000b23f  jmp     loc_18000B2C4
0x18000b244  mov     [rbp+arg_18], 0
0x18000b24b  mov     r14d, 4
0x18000b251  mov     [rbp+arg_0], r14d
0x18000b255  lea     rax, [rbp+arg_0]
0x18000b259  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x18000b25e  lea     r9, [rbp+arg_18]; void *
0x18000b262  lea     r8d, [r14+0Ch]; unsigned int
0x18000b266  lea     rdx, aTest; "Test"
0x18000b26d  mov     rcx, [rdi]; HKEY
0x18000b270  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x18000b275  mov     ebx, eax
0x18000b277  test    eax, eax
0x18000b279  jns     short loc_18000B282
0x18000b27b  mov     edx, 0E7h
0x18000b280  jmp     short loc_18000B22A
0x18000b282  cmp     [rbp+arg_18], 0
0x18000b286  setnz   al
0x18000b289  mov     [rsi+10h], al
0x18000b28c  mov     [rbp+arg_0], r14d
0x18000b290  lea     r9, [rsi+14h]; void *
0x18000b294  lea     rax, [rbp+arg_0]
0x18000b298  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int *
0x18000b29d  mov     r8d, 10h; unsigned int
0x18000b2a3  lea     rdx, aVelocityfeatur; "VelocityFeatureId"
0x18000b2aa  mov     rcx, [rdi]; HKEY
0x18000b2ad  call    ?TryGetRegValue@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@CAJPEAUHKEY__@@PEBGKPEAXPEAK@Z; Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::TryGetRegValue(HKEY__ *,ushort const *,ulong,void *,ulong *)
0x18000b2b2  mov     ebx, eax
0x18000b2b4  test    eax, eax
0x18000b2b6  jns     short loc_18000B2C2
0x18000b2b8  mov     edx, 0EBh
0x18000b2bd  jmp     loc_18000B22A
0x18000b2c2  xor     eax, eax
0x18000b2c4  lea     r11, [rsp+50h+var_s0]
0x18000b2c9  mov     rbx, [r11+28h]
0x18000b2cd  mov     rsi, [r11+30h]
0x18000b2d1  mov     rsp, r11
0x18000b2d4  pop     r14
0x18000b2d6  pop     rdi
0x18000b2d7  pop     rbp
0x18000b2d8  retn
```
