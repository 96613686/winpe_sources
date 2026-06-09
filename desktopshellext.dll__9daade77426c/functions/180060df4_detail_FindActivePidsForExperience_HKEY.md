# detail::FindActivePidsForExperience(HKEY__ *)

- ea: `0x180060df4`
- end: `0x180060f9f`
- name: `?FindActivePidsForExperience@detail@@YA?AV?$vector@KV?$allocator@K@std@@@std@@PEAUHKEY__@@@Z`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800632a0`

## callees

- `0x18000bdf0`
- `0x1800139e0`
- `0x18001c10c`
- `0x18001c608`
- `0x18002a3d0`
- `0x18002af50`
- `0x18005a77c`
- `0x180060df4`
- `0x1800640ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180060e88`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180060e88`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180060f30`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180060f30`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180060f5f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180060f5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall detail::FindActivePidsForExperience(_QWORD *a1, HKEY a2)
{
  DWORD v4; // esi
  DWORD i; // edx
  unsigned int v6; // ebx
  unsigned int *v7; // rdx
  LPCWSTR v8; // rbx
  LPCWSTR v9; // rsi
  const WCHAR *v10; // rdx
  DWORD cchName[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v13; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+70h] [rbp-90h]
  _QWORD *v18; // [rsp+78h] [rbp-88h]
  _BYTE v19[32]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t String[64]; // [rsp+A0h] [rbp-60h] BYREF

  v18 = a1;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  cchName[1] = 1;
  *(_OWORD *)lpSubKey = 0;
  v17 = 0;
  v4 = 0;
  memset_0(String, 0, sizeof(String));
  ftLastWriteTime = 0;
  for ( i = 0; ; i = v4 )
  {
    cchName[0] = 64;
    if ( RegEnumKeyExW(a2, i, String, cchName, 0, 0, 0, &ftLastWriteTime) )
      break;
    EndPtr = 0;
    v6 = wcstoul(String, &EndPtr, 10);
    if ( EndPtr && !*EndPtr )
    {
      v13 = v6;
      if ( detail::IsValidActivePidSubKey(a2, String, (const unsigned __int16 *)v6) )
      {
        v7 = (unsigned int *)a1[1];
        if ( v7 == (unsigned int *)a1[2] )
        {
          std::vector<unsigned long>::_Emplace_reallocate<unsigned long const &>(a1, v7, &v13);
        }
        else
        {
          *v7 = v6;
          a1[1] += 4LL;
        }
      }
      else
      {
        std::wstring::wstring(v19, String);
        std::vector<std::wstring>::push_back(lpSubKey, v19);
        std::wstring::~wstring(v19);
      }
    }
    ++v4;
  }
  v8 = lpSubKey[0];
  v9 = lpSubKey[1];
  while ( v8 != v9 )
  {
    if ( *((_QWORD *)v8 + 3) <= 7u )
      v10 = v8;
    else
      v10 = *(const WCHAR **)v8;
    RegDeleteKeyW(a2, v10);
    v8 += 16;
  }
  std::vector<std::wstring>::_Tidy(lpSubKey);
  return a1;
}

```

## disassembly

```asm
0x180060df4  mov     [rsp-8+arg_10], rbx
0x180060df9  push    rbp
0x180060dfa  push    rsi
0x180060dfb  push    rdi
0x180060dfc  push    r14
0x180060dfe  push    r15
0x180060e00  lea     rbp, [rsp-30h]
0x180060e05  sub     rsp, 130h
0x180060e0c  mov     rax, cs:__security_cookie
0x180060e13  xor     rax, rsp
0x180060e16  mov     [rbp+50h+var_30], rax
0x180060e1a  mov     r14, rdx
0x180060e1d  mov     rdi, rcx
0x180060e20  mov     [rsp+150h+var_D8], rcx
0x180060e25  xor     r15d, r15d
0x180060e28  mov     [rsp+150h+var_10C], r15d
0x180060e2d  mov     [rcx], r15
0x180060e30  mov     [rcx+8], r15
0x180060e34  mov     [rcx+10h], r15
0x180060e38  mov     [rsp+150h+var_10C], 1
0x180060e40  xorps   xmm0, xmm0
0x180060e43  movdqu  xmmword ptr [rsp+150h+lpSubKey], xmm0
0x180060e49  mov     [rsp+150h+var_E0], r15
0x180060e4e  mov     esi, r15d
0x180060e51  xor     edx, edx; Val
0x180060e53  mov     r8d, 80h; Size
0x180060e59  lea     rcx, [rbp+50h+String]; void *
0x180060e5d  call    memset_0
0x180060e62  mov     qword ptr [rsp+150h+ftLastWriteTime.dwLowDateTime], r15
0x180060e67  xor     edx, edx
0x180060e69  jmp     loc_180060F03
0x180060e6e  test    eax, eax
0x180060e70  jnz     loc_180060F41
0x180060e76  mov     [rsp+150h+EndPtr], r15
0x180060e7b  lea     r8d, [rax+0Ah]; Radix
0x180060e7f  lea     rdx, [rsp+150h+EndPtr]; EndPtr
0x180060e84  lea     rcx, [rbp+50h+String]; String
0x180060e88  call    cs:__imp_wcstoul
0x180060e8e  mov     ebx, eax
0x180060e90  mov     rax, [rsp+150h+EndPtr]
0x180060e95  test    rax, rax
0x180060e98  jz      short loc_180060EFF
0x180060e9a  cmp     [rax], r15w
0x180060e9e  jnz     short loc_180060EFF
0x180060ea0  mov     [rsp+150h+var_108], ebx
0x180060ea4  mov     r8d, ebx; unsigned __int16 *
0x180060ea7  lea     rdx, [rbp+50h+String]; lpSubKey
0x180060eab  mov     rcx, r14; hKey
0x180060eae  call    ?IsValidActivePidSubKey@detail@@YA_NPEAUHKEY__@@PEBGK@Z; detail::IsValidActivePidSubKey(HKEY__ *,ushort const *,ulong)
0x180060eb3  test    al, al
0x180060eb5  jz      short loc_180060ED9
0x180060eb7  mov     rdx, [rdi+8]
0x180060ebb  cmp     rdx, [rdi+10h]
0x180060ebf  jz      short loc_180060ECA
0x180060ec1  mov     [rdx], ebx
0x180060ec3  add     qword ptr [rdi+8], 4
0x180060ec8  jmp     short loc_180060EFF
0x180060eca  lea     r8, [rsp+150h+var_108]
0x180060ecf  mov     rcx, rdi
0x180060ed2  call    ??$_Emplace_reallocate@AEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAKAEBK@Z; std::vector<ulong>::_Emplace_reallocate<ulong const &>(ulong * const,ulong const &)
0x180060ed7  jmp     short loc_180060EFF
0x180060ed9  lea     rdx, [rbp+50h+String]
0x180060edd  lea     rcx, [rbp+50h+var_D0]
0x180060ee1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180060ee6  nop
0x180060ee7  lea     rdx, [rbp+50h+var_D0]
0x180060eeb  lea     rcx, [rsp+150h+lpSubKey]
0x180060ef0  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180060ef5  nop
0x180060ef6  lea     rcx, [rbp+50h+var_D0]
0x180060efa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060eff  inc     esi
0x180060f01  mov     edx, esi; dwIndex
0x180060f03  lea     rax, [rsp+150h+ftLastWriteTime]
0x180060f08  mov     [rsp+150h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180060f0d  mov     [rsp+150h+lpcchClass], r15; lpcchClass
0x180060f12  mov     [rsp+150h+lpClass], r15; lpClass
0x180060f17  mov     [rsp+150h+lpReserved], r15; lpReserved
0x180060f1c  mov     [rsp+150h+cchName], 40h ; '@'
0x180060f24  lea     r9, [rsp+150h+cchName]; lpcchName
0x180060f29  lea     r8, [rbp+50h+String]; lpName
0x180060f2d  mov     rcx, r14; hKey
0x180060f30  call    cs:__imp_RegEnumKeyExW
0x180060f36  cmp     eax, 103h
0x180060f3b  jnz     loc_180060E6E
0x180060f41  mov     rbx, [rsp+150h+lpSubKey]
0x180060f46  mov     rsi, [rsp+150h+lpSubKey+8]
0x180060f4b  jmp     short loc_180060F69
0x180060f4d  cmp     qword ptr [rbx+18h], 7
0x180060f52  jbe     short loc_180060F59
0x180060f54  mov     rdx, [rbx]
0x180060f57  jmp     short loc_180060F5C
0x180060f59  mov     rdx, rbx; lpSubKey
0x180060f5c  mov     rcx, r14; hKey
0x180060f5f  call    cs:__imp_RegDeleteKeyW
0x180060f65  add     rbx, 20h ; ' '
0x180060f69  cmp     rbx, rsi
0x180060f6c  jnz     short loc_180060F4D
0x180060f6e  lea     rcx, [rsp+150h+lpSubKey]
0x180060f73  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180060f78  mov     rax, rdi
0x180060f7b  mov     rcx, [rbp+50h+var_30]
0x180060f7f  xor     rcx, rsp; StackCookie
0x180060f82  call    __security_check_cookie
0x180060f87  mov     rbx, [rsp+150h+arg_10]
0x180060f8f  add     rsp, 130h
0x180060f96  pop     r15
0x180060f98  pop     r14
0x180060f9a  pop     rdi
0x180060f9b  pop     rsi
0x180060f9c  pop     rbp
0x180060f9d  retn
```
