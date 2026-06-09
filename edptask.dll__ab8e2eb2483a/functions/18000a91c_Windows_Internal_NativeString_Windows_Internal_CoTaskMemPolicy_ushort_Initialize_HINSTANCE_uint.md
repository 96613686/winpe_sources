# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)

- ea: `0x18000a91c`
- end: `0x18000a9cb`
- name: `?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD *, HMODULE, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180008920`
- `0x1800089e0`
- `0x18000a5c0`
- `0x18000a650`
- `0x18000a6e0`
- `0x18000a770`
- `0x18000a800`
- `0x18000a890`

## callees

- `0x18000a91c`
- `0x180011e48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000a953`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000a953`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000a975`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000a975`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000a967`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000a967`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
        _QWORD *a1,
        HMODULE a2,
        unsigned int a3)
{
  char v4; // bl
  unsigned int v6; // edi
  HRSRC Resource; // rax
  HGLOBAL v8; // rax
  _WORD *v9; // rcx
  unsigned int v10; // edx
  unsigned int v11; // ebx
  __int64 *v12; // rdx

  v4 = a3;
  v6 = -2147467259;
  Resource = FindResourceExW(a2, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a3 >> 4) + 1), 0);
  if ( Resource )
  {
    v8 = LoadResource(a2, Resource);
    if ( v8 )
    {
      v9 = LockResource(v8);
      if ( v9 )
      {
        v10 = 0;
        v11 = v4 & 0xF;
        if ( v11 )
        {
          do
          {
            ++v10;
            v9 += (unsigned __int16)*v9 + 1;
          }
          while ( v10 < v11 );
        }
        v12 = (__int64 *)(v9 + 1);
        if ( !*v9 )
          v12 = &qword_180017F50;
        return (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                               a1,
                               v12,
                               (unsigned __int16)*v9);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000a91c  push    rbx
0x18000a91e  push    rbp
0x18000a91f  push    rsi
0x18000a920  push    rdi
0x18000a921  push    r14
0x18000a923  push    r15
0x18000a925  sub     rsp, 28h
0x18000a929  xor     r9d, r9d; wLanguage
0x18000a92c  mov     eax, r8d
0x18000a92f  mov     rsi, rdx
0x18000a932  shr     eax, 4
0x18000a935  mov     ebx, r8d
0x18000a938  mov     rbp, rcx
0x18000a93b  mov     rcx, rsi; hModule
0x18000a93e  mov     edi, 80004005h
0x18000a943  lea     r15d, [r9+1]
0x18000a947  add     ax, r15w
0x18000a94b  lea     edx, [r9+6]; lpType
0x18000a94f  movzx   r8d, ax; lpName
0x18000a953  call    cs:__imp_FindResourceExW
0x18000a959  xor     r14d, r14d
0x18000a95c  test    rax, rax
0x18000a95f  jz      short loc_18000A9BC
0x18000a961  mov     rdx, rax; hResInfo
0x18000a964  mov     rcx, rsi; hModule
0x18000a967  call    cs:__imp_LoadResource
0x18000a96d  test    rax, rax
0x18000a970  jz      short loc_18000A9BC
0x18000a972  mov     rcx, rax; hResData
0x18000a975  call    cs:__imp_LockResource
0x18000a97b  mov     rcx, rax
0x18000a97e  test    rax, rax
0x18000a981  jz      short loc_18000A9BC
0x18000a983  mov     edx, r14d
0x18000a986  and     ebx, 0Fh
0x18000a989  jbe     short loc_18000A99D
0x18000a98b  movzx   eax, word ptr [rcx]
0x18000a98e  add     edx, r15d
0x18000a991  lea     rcx, [rcx+rax*2]
0x18000a995  add     rcx, 2
0x18000a999  cmp     edx, ebx
0x18000a99b  jb      short loc_18000A98B
0x18000a99d  lea     rdx, [rcx+2]
0x18000a9a1  cmp     [rcx], r14w
0x18000a9a5  jnz     short loc_18000A9AE
0x18000a9a7  lea     rdx, qword_180017F50
0x18000a9ae  movzx   r8d, word ptr [rcx]
0x18000a9b2  mov     rcx, rbp
0x18000a9b5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18000a9ba  mov     edi, eax
0x18000a9bc  mov     eax, edi
0x18000a9be  add     rsp, 28h
0x18000a9c2  pop     r15
0x18000a9c4  pop     r14
0x18000a9c6  pop     rdi
0x18000a9c7  pop     rsi
0x18000a9c8  pop     rbp
0x18000a9c9  pop     rbx
0x18000a9ca  retn
```
