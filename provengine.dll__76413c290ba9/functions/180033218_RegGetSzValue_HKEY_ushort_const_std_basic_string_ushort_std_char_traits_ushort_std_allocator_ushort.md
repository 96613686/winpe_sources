# RegGetSzValue(HKEY__ *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180033218`
- end: `0x18003334e`
- name: `?RegGetSzValue@@YAJPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, void *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008a84`
- `0x180009348`
- `0x18000a4e4`
- `0x180018f74`

## callees

- `0x180009900`
- `0x18000b030`
- `0x18000b31c`
- `0x180033218`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180033301`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033333`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033301`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033333`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033271`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800332d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033271`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800332d4`

## string_xrefs

- `0x180033283`: `onecoreuap\admin\prov\multivariant\common\src\commonutils.cpp`
- `0x1800332e6`: `onecoreuap\admin\prov\multivariant\common\src\commonutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall RegGetSzValue(HKEY hKey, LPCWSTR lpValueName, _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v6; // eax
  LPBYTE v8; // rbx
  unsigned int v9; // eax
  int v10; // edi
  unsigned __int64 v11; // r8
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  unsigned int lpDataa; // [rsp+20h] [rbp-48h]
  LPBYTE v14[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD cbData; // [rsp+80h] [rbp+18h] BYREF

  v3 = a3;
  cbData = 0;
  memset(v14, 0, 24);
  if ( a3[3] >= 8u )
    a3 = (_QWORD *)*a3;
  v3[2] = 0;
  *(_WORD *)a3 = 0;
  v6 = RegQueryValueExW(hKey, lpValueName, 0, 0, 0, &cbData);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x49,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\commonutils.cpp",
             (const char *)v6,
             lpData);
  std::vector<unsigned short>::resize(v14, ((unsigned __int64)cbData >> 1) + 1);
  v8 = v14[0];
  v9 = RegQueryValueExW(hKey, lpValueName, 0, 0, v14[0], &cbData);
  if ( v9 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4B,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\commonutils.cpp",
            (const char *)v9,
            lpDataa);
    if ( v8 )
      operator delete(v8);
    return v10;
  }
  else
  {
    if ( *(_WORD *)v8 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&v8[2 * v11] );
    }
    else
    {
      v11 = 0;
    }
    std::wstring::assign(v3, (char *)v8, v11);
    operator delete(v8);
    return 0;
  }
}

```

## disassembly

```asm
0x180033218  mov     rax, rsp
0x18003321b  mov     [rax+8], rbx
0x18003321f  mov     [rax+10h], rbp
0x180033223  push    rsi
0x180033224  push    rdi
0x180033225  push    r14
0x180033227  sub     rsp, 50h
0x18003322b  mov     rdi, r8
0x18003322e  mov     rsi, rdx
0x180033231  mov     rbp, rcx
0x180033234  xor     r14d, r14d
0x180033237  mov     [rax+18h], r14d
0x18003323b  xorps   xmm0, xmm0
0x18003323e  movdqu  xmmword ptr [rax-38h], xmm0
0x180033243  mov     [rax-28h], r14
0x180033247  cmp     qword ptr [r8+18h], 8
0x18003324c  jb      short loc_180033251
0x18003324e  mov     r8, [r8]
0x180033251  mov     [rdi+10h], r14
0x180033255  mov     [r8], r14w
0x180033259  lea     rax, [rsp+68h+cbData]
0x180033261  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180033266  mov     [rsp+68h+lpData], r14; unsigned int
0x18003326b  xor     r9d, r9d; lpType
0x18003326e  xor     r8d, r8d; lpReserved
0x180033271  call    cs:__imp_RegQueryValueExW
0x180033277  test    eax, eax
0x180033279  jz      short loc_18003329A
0x18003327b  mov     rcx, [rsp+68h]; this
0x180033280  mov     r9d, eax; char *
0x180033283  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003328a  mov     edx, 49h ; 'I'; void *
0x18003328f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180033294  nop
0x180033295  jmp     loc_18003333B
0x18003329a  mov     edx, [rsp+68h+cbData]
0x1800332a1  shr     rdx, 1
0x1800332a4  inc     rdx
0x1800332a7  lea     rcx, [rsp+68h+var_38]
0x1800332ac  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800332b1  lea     rax, [rsp+68h+cbData]
0x1800332b9  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800332be  mov     rbx, [rsp+68h+var_38]
0x1800332c3  mov     [rsp+68h+lpData], rbx; unsigned int
0x1800332c8  xor     r9d, r9d; lpType
0x1800332cb  xor     r8d, r8d; lpReserved
0x1800332ce  mov     rdx, rsi; lpValueName
0x1800332d1  mov     rcx, rbp; hKey
0x1800332d4  call    cs:__imp_RegQueryValueExW
0x1800332da  test    eax, eax
0x1800332dc  jz      short loc_18003330B
0x1800332de  mov     rcx, [rsp+68h]; this
0x1800332e3  mov     r9d, eax; char *
0x1800332e6  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800332ed  mov     edx, 4Bh ; 'K'; void *
0x1800332f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800332f7  mov     edi, eax
0x1800332f9  test    rbx, rbx
0x1800332fc  jz      short loc_180033307
0x1800332fe  mov     rcx, rbx
0x180033301  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033307  mov     eax, edi
0x180033309  jmp     short loc_18003333B
0x18003330b  cmp     [rbx], r14w
0x18003330f  jnz     short loc_180033316
0x180033311  mov     r8, r14
0x180033314  jmp     short loc_180033324
0x180033316  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003331a  inc     r8
0x18003331d  cmp     [rbx+r8*2], r14w
0x180033322  jnz     short loc_18003331A
0x180033324  mov     rdx, rbx; Src
0x180033327  mov     rcx, rdi; void *
0x18003332a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003332f  nop
0x180033330  mov     rcx, rbx
0x180033333  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033339  xor     eax, eax
0x18003333b  mov     rbx, [rsp+68h+arg_0]
0x180033340  mov     rbp, [rsp+68h+arg_8]
0x180033345  add     rsp, 50h
0x180033349  pop     r14
0x18003334b  pop     rdi
0x18003334c  pop     rsi
0x18003334d  retn
```
