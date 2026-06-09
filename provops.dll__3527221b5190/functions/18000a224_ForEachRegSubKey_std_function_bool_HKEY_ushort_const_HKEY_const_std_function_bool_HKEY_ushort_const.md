# ForEachRegSubKey<std::function<bool (HKEY__ *,ushort const *)>>(HKEY__ * const,std::function<bool (HKEY__ *,ushort const *)>)

- ea: `0x18000a224`
- end: `0x18000a3dd`
- name: `??$ForEachRegSubKey@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@@YAKQEAUHKEY__@@V?$function@$$A6A_NPEAUHKEY__@@PEBG@Z@std@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180009e64`
- `0x18000a044`
- `0x18001df00`
- `0x18001e0b0`

## callees

- `0x18000a224`
- `0x18001b388`
- `0x18001b3a8`
- `0x1800202e4`
- `0x180037010`

## import_xrefs

- `msvcp110_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000a39a`
- `msvcp110_win!?_Xbad_function_call@std@@YAXXZ` at `0x18000a39a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a35b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a35b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a311`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a311`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a285`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a285`

## string_xrefs

- `0x18000a3a1`: `onecoreuap\admin\prov\inc\RegistryUtils.h`
- `0x18000a3b6`: `onecoreuap\admin\prov\inc\RegistryUtils.h`
- `0x18000a3cb`: `onecoreuap\admin\prov\inc\RegistryUtils.h`

## pseudocode

```c
__int64 __fastcall ForEachRegSubKey<std::function<bool (HKEY__ *,unsigned short const *)>>(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  DWORD v5; // edx
  DWORD v6; // eax
  __int64 v7; // r8
  const char *v8; // r9
  wil::details::in1diag3 *v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // ebx
  WCHAR *v12; // rdi
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int lpcSubKeys; // [rsp+28h] [rbp-39h]
  DWORD cchName; // [rsp+68h] [rbp+7h] BYREF
  WCHAR *v19; // [rsp+70h] [rbp+Fh] BYREF
  HKEY v20; // [rsp+78h] [rbp+17h] BYREF
  LPWSTR lpName[2]; // [rsp+80h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+90h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]
  DWORD cbMaxSubKeyLen; // [rsp+D8h] [rbp+77h] BYREF
  DWORD cSubKeys; // [rsp+E0h] [rbp+7Fh] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\admin\\prov\\inc\\RegistryUtils.h",
      (const char *)v4,
      lpcSubKeys);
  v5 = cbMaxSubKeyLen;
  v6 = cbMaxSubKeyLen + 1;
  v7 = 0xFFFFFFFFLL;
  if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
    v7 = v6;
  v8 = v6 < cbMaxSubKeyLen ? (const char *)0x80070216LL : 0LL;
  cbMaxSubKeyLen = v7;
  v9 = retaddr;
  if ( v6 < v5 )
    goto LABEL_18;
  *(_OWORD *)lpName = 0;
  v22 = 0;
  v10 = (unsigned int)v7;
  if ( (_DWORD)v7 )
    std::vector<unsigned short>::_Reallocate(lpName, (unsigned int)v7);
  v11 = 0;
  v12 = lpName[0];
  if ( cSubKeys )
  {
    while ( 1 )
    {
      cchName = cbMaxSubKeyLen;
      v13 = RegEnumKeyExW(hKey, v11, v12, &cchName, 0, 0, 0, 0);
      if ( v13 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x4C,
          (unsigned int)"onecoreuap\\admin\\prov\\inc\\RegistryUtils.h",
          (const char *)v13,
          lpcSubKeys);
      v19 = v12;
      v20 = hKey;
      v14 = *(_QWORD *)(a2 + 24);
      if ( !v14 )
        break;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, HKEY *, WCHAR **))(*(_QWORD *)v14 + 16LL))(v14, &v20, &v19) )
      {
        if ( ++v11 < cSubKeys )
          continue;
      }
      goto LABEL_12;
    }
    std::_Xbad_function_call();
LABEL_18:
    wil::details::in1diag3::Throw_Hr(
      v9,
      (void *)0x43,
      (unsigned int)"onecoreuap\\admin\\prov\\inc\\RegistryUtils.h",
      v8,
      lpcSubKeys);
  }
LABEL_12:
  if ( v12 )
    operator delete(v12);
  v15 = *(_QWORD *)(a2 + 24);
  if ( v15 )
  {
    LOBYTE(v10) = v15 != a2;
    (*(void (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v15 + 32LL))(v15, v10, v7, v8);
    *(_QWORD *)(a2 + 24) = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x18000a224  mov     rax, rsp
0x18000a227  mov     [rax+8], rbx
0x18000a22b  mov     [rax+10h], rdx
0x18000a22f  push    rbp
0x18000a230  push    rsi
0x18000a231  push    rdi
0x18000a232  push    r14
0x18000a234  push    r15
0x18000a236  lea     rbp, [rax-5Fh]
0x18000a23a  sub     rsp, 90h
0x18000a241  mov     rsi, rdx
0x18000a244  mov     r14, rcx
0x18000a247  xor     r15d, r15d
0x18000a24a  mov     [rbp+57h+cSubKeys], r15d
0x18000a24e  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x18000a252  mov     [rax-60h], r15
0x18000a256  mov     [rax-68h], r15
0x18000a25a  mov     [rax-70h], r15
0x18000a25e  mov     [rax-78h], r15
0x18000a262  mov     [rax-80h], r15
0x18000a266  mov     [rsp+0B0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000a26b  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000a26f  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000a274  lea     rax, [rbp+57h+cSubKeys]
0x18000a278  mov     [rsp+0B0h+lpcSubKeys], rax; unsigned int
0x18000a27d  xor     r9d, r9d; lpReserved
0x18000a280  xor     r8d, r8d; lpcchClass
0x18000a283  xor     edx, edx; lpClass
0x18000a285  call    cs:__imp_RegQueryInfoKeyW
0x18000a28b  mov     rcx, [rbp+5Fh]; this
0x18000a28f  test    eax, eax
0x18000a291  jnz     loc_18000A3C8
0x18000a297  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x18000a29a  lea     eax, [rdx+1]
0x18000a29d  or      r8d, 0FFFFFFFFh
0x18000a2a1  cmp     eax, edx
0x18000a2a3  cmovnb  r8d, eax
0x18000a2a7  sbb     r9d, r9d
0x18000a2aa  and     r9d, 80070216h
0x18000a2b1  mov     [rbp+57h+cbMaxSubKeyLen], r8d
0x18000a2b5  mov     rcx, [rbp+5Fh]
0x18000a2b9  cmp     eax, edx
0x18000a2bb  jb      loc_18000A3A1
0x18000a2c1  xorps   xmm0, xmm0
0x18000a2c4  movdqu  xmmword ptr [rbp+57h+lpName], xmm0
0x18000a2c9  mov     [rbp+57h+var_28], r15
0x18000a2cd  mov     edx, r8d
0x18000a2d0  test    r8d, r8d
0x18000a2d3  jz      short loc_18000A2DE
0x18000a2d5  lea     rcx, [rbp+57h+lpName]
0x18000a2d9  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18000a2de  mov     ebx, r15d
0x18000a2e1  mov     rdi, [rbp+57h+lpName]
0x18000a2e5  cmp     [rbp+57h+cSubKeys], r15d
0x18000a2e9  jbe     short loc_18000A353
0x18000a2eb  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000a2ee  mov     [rbp+57h+cchName], eax
0x18000a2f1  mov     [rsp+38h], r15; lpftLastWriteTime
0x18000a2f6  mov     [rsp+0B0h+lpcbMaxClassLen], r15; lpcchClass
0x18000a2fb  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r15; lpClass
0x18000a300  mov     [rsp+0B0h+lpcSubKeys], r15; unsigned int
0x18000a305  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000a309  mov     r8, rdi; lpName
0x18000a30c  mov     edx, ebx; dwIndex
0x18000a30e  mov     rcx, r14; hKey
0x18000a311  call    cs:__imp_RegEnumKeyExW
0x18000a317  mov     rcx, [rbp+5Fh]; this
0x18000a31b  test    eax, eax
0x18000a31d  jnz     loc_18000A3B3
0x18000a323  mov     [rbp+57h+var_48], rdi
0x18000a327  mov     [rbp+57h+var_40], r14
0x18000a32b  mov     rcx, [rsi+18h]
0x18000a32f  test    rcx, rcx
0x18000a332  jz      short loc_18000A39A
0x18000a334  mov     rax, [rcx]
0x18000a337  lea     r8, [rbp+57h+var_48]
0x18000a33b  lea     rdx, [rbp+57h+var_40]
0x18000a33f  mov     rax, [rax+10h]
0x18000a343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a348  test    al, al
0x18000a34a  jz      short loc_18000A353
0x18000a34c  inc     ebx
0x18000a34e  cmp     ebx, [rbp+57h+cSubKeys]
0x18000a351  jb      short loc_18000A2EB
0x18000a353  test    rdi, rdi
0x18000a356  jz      short loc_18000A362
0x18000a358  mov     rcx, rdi
0x18000a35b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a361  nop
0x18000a362  mov     rcx, [rsi+18h]
0x18000a366  test    rcx, rcx
0x18000a369  jz      short loc_18000A381
0x18000a36b  mov     rax, [rcx]
0x18000a36e  cmp     rcx, rsi
0x18000a371  setnz   dl
0x18000a374  mov     rax, [rax+20h]
0x18000a378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a37d  mov     [rsi+18h], r15
0x18000a381  mov     eax, ebx
0x18000a383  mov     rbx, [rsp+0B0h+arg_0]
0x18000a38b  add     rsp, 90h
0x18000a392  pop     r15
0x18000a394  pop     r14
0x18000a396  pop     rdi
0x18000a397  pop     rsi
0x18000a398  pop     rbp
0x18000a399  retn
0x18000a39a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18000a3a0  nop
0x18000a3a1  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\inc\\RegistryU"...
0x18000a3a8  mov     edx, 43h ; 'C'; void *
0x18000a3ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a3b3  mov     r9d, eax; char *
0x18000a3b6  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\inc\\RegistryU"...
0x18000a3bd  mov     edx, 4Ch ; 'L'; void *
0x18000a3c2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a3c8  mov     r9d, eax; char *
0x18000a3cb  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\inc\\RegistryU"...
0x18000a3d2  mov     edx, 40h ; '@'; void *
0x18000a3d7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
