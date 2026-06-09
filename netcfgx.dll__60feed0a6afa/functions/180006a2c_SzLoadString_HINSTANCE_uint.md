# SzLoadString(HINSTANCE__ *,uint)

- ea: `0x180006a2c`
- end: `0x180006abc`
- name: `?SzLoadString@@YAPEBGPEAUHINSTANCE__@@I@Z`
- size: `144`
- prototype: `const unsigned __int16 *__fastcall(HINSTANCE hModule, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ac4`
- `0x1800070a8`
- `0x18000af5c`
- `0x18000da34`
- `0x180011270`
- `0x180012034`
- `0x18001218c`

## callees

- `0x180006a2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180006a6a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180006a6a`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180006a59`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180006a59`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180006a78`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180006a78`

## pseudocode

```c
const unsigned __int16 near *const *__fastcall SzLoadString(HINSTANCE hModule, unsigned __int16 a2)
{
  const unsigned __int16 near *const *v2; // rbx
  char v3; // di
  HRSRC Resource; // rax
  HGLOBAL v6; // rax
  int v7; // edi
  __int64 v8; // rcx
  unsigned __int16 *v9; // rax

  v2 = &c_szSpace;
  v3 = a2;
  Resource = FindResourceExW(hModule, (LPCWSTR)6, (LPCWSTR)((a2 >> 4) + 1), 0);
  if ( Resource )
  {
    v6 = LoadResource(hModule, Resource);
    if ( v6 )
    {
      v2 = (const unsigned __int16 near *const *)LockResource(v6);
      if ( !v2 )
        return &c_szSpace;
      v7 = v3 & 0xF;
      v8 = 0;
      do
      {
        v9 = (unsigned __int16 *)v2 + v8;
        v8 = *v9;
        v2 = (const unsigned __int16 near *const *)(v9 + 1);
        LODWORD(v9) = v7--;
      }
      while ( (_DWORD)v9 );
      if ( !(_DWORD)v8 )
        return &c_szSpace;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180006a2c  mov     [rsp+arg_0], rbx
0x180006a31  mov     [rsp+arg_8], rsi
0x180006a36  push    rdi
0x180006a37  sub     rsp, 20h
0x180006a3b  movzx   r8d, dx
0x180006a3f  lea     rbx, ?c_szSpace@@3QBGB; ushort const near * const c_szSpace
0x180006a46  xor     r9d, r9d; wLanguage
0x180006a49  shr     r8d, 4
0x180006a4d  mov     edi, edx
0x180006a4f  inc     r8d; lpName
0x180006a52  mov     rsi, rcx
0x180006a55  lea     edx, [r9+6]; lpType
0x180006a59  call    cs:__imp_FindResourceExW
0x180006a5f  test    rax, rax
0x180006a62  jz      short loc_180006AA9
0x180006a64  mov     rdx, rax; hResInfo
0x180006a67  mov     rcx, rsi; hModule
0x180006a6a  call    cs:__imp_LoadResource
0x180006a70  test    rax, rax
0x180006a73  jz      short loc_180006AA9
0x180006a75  mov     rcx, rax; hResData
0x180006a78  call    cs:__imp_LockResource
0x180006a7e  mov     rbx, rax
0x180006a81  test    rax, rax
0x180006a84  jz      short loc_180006AA2
0x180006a86  and     edi, 0Fh
0x180006a89  xor     ecx, ecx
0x180006a8b  lea     rax, [rbx+rcx*2]
0x180006a8f  movzx   ecx, word ptr [rax]
0x180006a92  lea     rbx, [rax+2]
0x180006a96  mov     eax, edi
0x180006a98  dec     edi
0x180006a9a  test    eax, eax
0x180006a9c  jnz     short loc_180006A8B
0x180006a9e  test    ecx, ecx
0x180006aa0  jnz     short loc_180006AA9
0x180006aa2  lea     rbx, ?c_szSpace@@3QBGB; ushort const near * const c_szSpace
0x180006aa9  mov     rsi, [rsp+28h+arg_8]
0x180006aae  mov     rax, rbx
0x180006ab1  mov     rbx, [rsp+28h+arg_0]
0x180006ab6  add     rsp, 20h
0x180006aba  pop     rdi
0x180006abb  retn
```
