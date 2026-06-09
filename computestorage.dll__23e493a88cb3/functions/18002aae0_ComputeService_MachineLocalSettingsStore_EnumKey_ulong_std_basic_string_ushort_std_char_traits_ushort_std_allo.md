# ComputeService::MachineLocalSettingsStore::EnumKey(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002aae0`
- end: `0x18002ac45`
- name: `?EnumKey@MachineLocalSettingsStore@ComputeService@@UEBA_NKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `357`
- prototype: `char __fastcall(__int64, DWORD, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002690`
- `0x180008fac`
- `0x180009a38`
- `0x180012818`
- `0x180013cb4`
- `0x18002aae0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002abb4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002abb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002ab5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002ab5d`

## string_xrefs

- `0x18002ac1e`: `onecore\vm\compute\management\shared\compute\machinelocalsettingsstore.cpp`
- `0x18002ac33`: `onecore\vm\compute\management\shared\compute\machinelocalsettingsstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ComputeService::MachineLocalSettingsStore::EnumKey(__int64 a1, DWORD a2, __int64 a3)
{
  unsigned int v6; // eax
  WCHAR *v7; // r8
  unsigned int v8; // eax
  unsigned int lpcSubKeys; // [rsp+28h] [rbp-39h]
  unsigned int lpcSubKeysa; // [rsp+28h] [rbp-39h]
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp+7h] BYREF
  LPWSTR lpName[2]; // [rsp+70h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+80h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  *(_OWORD *)lpName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpName[0]) = 0;
  cbMaxSubKeyLen = 0;
  v6 = RegQueryInfoKeyW(*(HKEY *)(a1 + 8), 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\machinelocalsettingsstore.cpp",
      (const char *)v6,
      lpcSubKeys);
  ++cbMaxSubKeyLen;
  std::wstring::resize(lpName);
  v7 = (WCHAR *)lpName;
  if ( si128.m128i_i64[1] > 7uLL )
    v7 = lpName[0];
  v8 = RegEnumKeyExW(*(HKEY *)(a1 + 8), a2, v7, &cbMaxSubKeyLen, 0, 0, 0, 0);
  if ( v8 == 259 )
  {
    std::wstring::~wstring((char **)lpName);
    return 0;
  }
  else
  {
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\compute\\machinelocalsettingsstore.cpp",
        (const char *)v8,
        lpcSubKeysa);
    std::wstring::resize(lpName);
    std::wstring::operator=(a3, lpName);
    std::wstring::~wstring((char **)lpName);
    return 1;
  }
}

```

## disassembly

```asm
0x18002aae0  mov     r11, rsp
0x18002aae3  push    rbp
0x18002aae4  push    rbx
0x18002aae5  push    rsi
0x18002aae6  push    rdi
0x18002aae7  push    r14
0x18002aae9  lea     rbp, [r11-5Fh]
0x18002aaed  sub     rsp, 90h
0x18002aaf4  mov     rax, cs:__security_cookie
0x18002aafb  xor     rax, rsp
0x18002aafe  mov     [rbp+57h+var_28], rax
0x18002ab02  mov     rbx, r8
0x18002ab05  mov     esi, edx
0x18002ab07  mov     rdi, rcx
0x18002ab0a  xorps   xmm0, xmm0
0x18002ab0d  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x18002ab11  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002ab19  movdqu  [rbp+57h+var_38], xmm1
0x18002ab1e  xor     r14d, r14d
0x18002ab21  mov     word ptr [rbp+57h+lpName], r14w
0x18002ab26  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18002ab2a  mov     [r11-60h], r14
0x18002ab2e  mov     [r11-68h], r14
0x18002ab32  mov     [r11-70h], r14
0x18002ab36  mov     [r11-78h], r14
0x18002ab3a  mov     [r11-80h], r14
0x18002ab3e  mov     [rsp+0B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18002ab43  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18002ab47  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18002ab4c  mov     [rsp+0B0h+lpcSubKeys], r14; unsigned int
0x18002ab51  xor     r9d, r9d; lpReserved
0x18002ab54  xor     r8d, r8d; lpcchClass
0x18002ab57  xor     edx, edx; lpClass
0x18002ab59  mov     rcx, [rcx+8]; hKey
0x18002ab5d  call    cs:__imp_RegQueryInfoKeyW
0x18002ab64  nop     dword ptr [rax+rax+00h]
0x18002ab69  mov     rcx, [rbp+5Fh]; this
0x18002ab6d  test    eax, eax
0x18002ab6f  jnz     loc_18002AC30
0x18002ab75  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18002ab78  inc     eax
0x18002ab7a  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x18002ab7d  mov     edx, eax
0x18002ab7f  lea     rcx, [rbp+57h+lpName]; Src
0x18002ab83  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002ab88  lea     r8, [rbp+57h+lpName]
0x18002ab8c  cmp     qword ptr [rbp+57h+var_38+8], 7
0x18002ab91  cmova   r8, [rbp+57h+lpName]; lpName
0x18002ab96  mov     [rsp+38h], r14; lpftLastWriteTime
0x18002ab9b  mov     [rsp+0B0h+lpcbMaxClassLen], r14; lpcchClass
0x18002aba0  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r14; lpClass
0x18002aba5  mov     [rsp+0B0h+lpcSubKeys], r14; unsigned int
0x18002abaa  lea     r9, [rbp+57h+cbMaxSubKeyLen]; lpcchName
0x18002abae  mov     edx, esi; dwIndex
0x18002abb0  mov     rcx, [rdi+8]; hKey
0x18002abb4  call    cs:__imp_RegEnumKeyExW
0x18002abbb  nop     dword ptr [rax+rax+00h]
0x18002abc0  cmp     eax, 103h
0x18002abc5  jnz     short loc_18002ABD4
0x18002abc7  lea     rcx, [rbp+57h+lpName]
0x18002abcb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002abd0  xor     al, al
0x18002abd2  jmp     short loc_18002AC00
0x18002abd4  mov     rcx, [rbp+5Fh]; this
0x18002abd8  test    eax, eax
0x18002abda  jnz     short loc_18002AC1B
0x18002abdc  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x18002abdf  lea     rcx, [rbp+57h+lpName]; Src
0x18002abe3  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002abe8  lea     rdx, [rbp+57h+lpName]
0x18002abec  mov     rcx, rbx
0x18002abef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002abf4  nop
0x18002abf5  lea     rcx, [rbp+57h+lpName]
0x18002abf9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002abfe  mov     al, 1
0x18002ac00  mov     rcx, [rbp+57h+var_28]
0x18002ac04  xor     rcx, rsp; StackCookie
0x18002ac07  call    __security_check_cookie
0x18002ac0c  add     rsp, 90h
0x18002ac13  pop     r14
0x18002ac15  pop     rdi
0x18002ac16  pop     rsi
0x18002ac17  pop     rbx
0x18002ac18  pop     rbp
0x18002ac19  retn
0x18002ac1b  mov     r9d, eax; char *
0x18002ac1e  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\management\\share"...
0x18002ac25  mov     edx, 42h ; 'B'; void *
0x18002ac2a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002ac30  mov     r9d, eax; char *
0x18002ac33  lea     r8, aOnecoreVmCompu; "onecore\\vm\\compute\\management\\share"...
0x18002ac3a  mov     edx, 35h ; '5'; void *
0x18002ac3f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
