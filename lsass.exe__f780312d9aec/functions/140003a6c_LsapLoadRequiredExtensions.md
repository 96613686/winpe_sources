# LsapLoadRequiredExtensions

- ea: `0x140003a6c`
- end: `0x140003bfc`
- name: `LsapLoadRequiredExtensions`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1400031bc`

## callees

- `0x1400016c0`
- `0x140001a80`
- `0x140003654`
- `0x140003a6c`
- `0x140005289`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003aac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003aac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003bdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003bdc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003adc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003b5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003adc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003b5a`

## string_xrefs

- `0x140003b8c`: `lsasrv.dll`
- `0x140003a92`: `System\CurrentControlSet\Control\LsaExtensionConfig\LsaSrv`
- `0x140003ad5`: `Extensions`
- `0x140003b53`: `Extensions`

## pseudocode

```c
__int64 LsapLoadRequiredExtensions()
{
  BYTE *LsaHeap; // rsi
  unsigned int Extension; // ebx
  LSTATUS v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rcx
  BYTE *v6; // rdi
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  LsaHeap = 0;
  Extension = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Control\\LsaExtensionConfig\\LsaSrv",
                0,
                0x20019u,
                &hKey);
  if ( !Extension )
  {
    v2 = RegQueryValueExW(hKey, L"Extensions", 0, &Type, 0, &cbData);
    Extension = v2;
    if ( !v2 || v2 == 234 )
    {
      if ( Type == 1 )
      {
        if ( cbData < 2 )
        {
LABEL_6:
          Extension = 13;
          goto LABEL_24;
        }
        v5 = cbData + 2;
        cbData += 2;
      }
      else
      {
        if ( Type != 7 )
        {
          Extension = 1629;
          goto LABEL_24;
        }
        v5 = cbData;
        if ( cbData < 4 )
          goto LABEL_6;
      }
      LsaHeap = (BYTE *)LsapAllocateLsaHeap(v5, v3, v4);
      if ( LsaHeap )
      {
        Extension = RegQueryValueExW(hKey, L"Extensions", 0, &Type, LsaHeap, &cbData);
        if ( !Extension )
        {
          v6 = LsaHeap;
          *(_WORD *)&LsaHeap[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
          *(_WORD *)&LsaHeap[2 * ((unsigned __int64)cbData >> 1) - 4] = 0;
          LsaHeap = 0;
          while ( *(_WORD *)v6 )
          {
            if ( !wcsncmp_0(L"lsasrv.dll", (const wchar_t *)v6, 0xAu) )
            {
              Extension = LsapLoadExtension(v6);
              if ( Extension )
                break;
            }
            else
            {
              LsapLoadExtension(v6);
            }
            while ( *(_WORD *)v6 )
              v6 += 2;
            v6 += 2;
          }
        }
      }
      else
      {
        Extension = 8;
      }
    }
  }
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  if ( LsaHeap )
    LsapFreeLsaHeap(LsaHeap);
  return Extension;
}

```

## disassembly

```asm
0x140003a6c  push    rbp
0x140003a6e  push    rbx
0x140003a6f  push    rsi
0x140003a70  push    rdi
0x140003a71  push    r14
0x140003a73  mov     rbp, rsp
0x140003a76  sub     rsp, 30h
0x140003a7a  xor     r14d, r14d
0x140003a7d  lea     rax, [rbp+hKey]
0x140003a81  mov     r9d, 20019h; samDesired
0x140003a87  mov     [rbp+hKey], r14
0x140003a8b  xor     r8d, r8d; ulOptions
0x140003a8e  mov     [rbp+Type], r14d
0x140003a92  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Lsa"...
0x140003a99  mov     [rbp+cbData], r14d
0x140003a9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003aa4  mov     [rsp+30h+phkResult], rax; phkResult
0x140003aa9  mov     esi, r14d
0x140003aac  call    cs:__imp_RegOpenKeyExW
0x140003ab2  mov     ebx, eax
0x140003ab4  test    eax, eax
0x140003ab6  jnz     loc_140003BD3
0x140003abc  mov     rcx, [rbp+hKey]; hKey
0x140003ac0  lea     rax, [rbp+cbData]
0x140003ac4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140003ac9  lea     r9, [rbp+Type]; lpType
0x140003acd  xor     r8d, r8d; lpReserved
0x140003ad0  mov     [rsp+30h+phkResult], r14; lpData
0x140003ad5  lea     rdx, aExtensions; "Extensions"
0x140003adc  call    cs:__imp_RegQueryValueExW
0x140003ae2  mov     ebx, eax
0x140003ae4  test    eax, eax
0x140003ae6  jz      short loc_140003AF3
0x140003ae8  cmp     eax, 0EAh
0x140003aed  jnz     loc_140003BD3
0x140003af3  cmp     [rbp+Type], 1
0x140003af7  jnz     short loc_140003B13
0x140003af9  mov     ecx, [rbp+cbData]
0x140003afc  cmp     ecx, 2
0x140003aff  jnb     short loc_140003B0B
0x140003b01  mov     ebx, 0Dh
0x140003b06  jmp     loc_140003BD3
0x140003b0b  add     ecx, 2
0x140003b0e  mov     [rbp+cbData], ecx
0x140003b11  jmp     short loc_140003B25
0x140003b13  cmp     [rbp+Type], 7
0x140003b17  jnz     loc_140003BCE
0x140003b1d  mov     ecx, [rbp+cbData]
0x140003b20  cmp     ecx, 4
0x140003b23  jb      short loc_140003B01
0x140003b25  call    LsapAllocateLsaHeap
0x140003b2a  mov     rsi, rax
0x140003b2d  test    rax, rax
0x140003b30  jnz     short loc_140003B3A
0x140003b32  lea     ebx, [rax+8]
0x140003b35  jmp     loc_140003BD3
0x140003b3a  mov     rcx, [rbp+hKey]; hKey
0x140003b3e  lea     rax, [rbp+cbData]
0x140003b42  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140003b47  lea     r9, [rbp+Type]; lpType
0x140003b4b  xor     r8d, r8d; lpReserved
0x140003b4e  mov     [rsp+30h+phkResult], rsi; lpData
0x140003b53  lea     rdx, aExtensions; "Extensions"
0x140003b5a  call    cs:__imp_RegQueryValueExW
0x140003b60  mov     ebx, eax
0x140003b62  test    eax, eax
0x140003b64  jnz     short loc_140003BD3
0x140003b66  mov     ecx, [rbp+cbData]
0x140003b69  mov     rdi, rsi
0x140003b6c  shr     rcx, 1
0x140003b6f  mov     [rsi+rcx*2-2], r14w
0x140003b75  mov     ecx, [rbp+cbData]
0x140003b78  shr     rcx, 1
0x140003b7b  mov     [rsi+rcx*2-4], r14w
0x140003b81  mov     rsi, r14
0x140003b84  jmp     short loc_140003BC6
0x140003b86  mov     r8d, 0Ah; MaxCount
0x140003b8c  lea     rcx, aLsasrvDll; "lsasrv.dll"
0x140003b93  mov     rdx, rdi; String2
0x140003b96  call    wcsncmp_0
0x140003b9b  xor     edx, edx
0x140003b9d  mov     rcx, rdi; Src
0x140003ba0  test    eax, eax
0x140003ba2  jnz     short loc_140003BB1
0x140003ba4  call    LsapLoadExtension
0x140003ba9  mov     ebx, eax
0x140003bab  test    eax, eax
0x140003bad  jnz     short loc_140003BD3
0x140003baf  jmp     short loc_140003BBC
0x140003bb1  call    LsapLoadExtension
0x140003bb6  jmp     short loc_140003BBC
0x140003bb8  add     rdi, 2
0x140003bbc  cmp     [rdi], r14w
0x140003bc0  jnz     short loc_140003BB8
0x140003bc2  add     rdi, 2
0x140003bc6  cmp     [rdi], r14w
0x140003bca  jnz     short loc_140003B86
0x140003bcc  jmp     short loc_140003BD3
0x140003bce  mov     ebx, 65Dh
0x140003bd3  mov     rcx, [rbp+hKey]; hKey
0x140003bd7  test    rcx, rcx
0x140003bda  jz      short loc_140003BE2
0x140003bdc  call    cs:__imp_RegCloseKey
0x140003be2  test    rsi, rsi
0x140003be5  jz      short loc_140003BEF
0x140003be7  mov     rcx, rsi
0x140003bea  call    LsapFreeLsaHeap
0x140003bef  mov     eax, ebx
0x140003bf1  add     rsp, 30h
0x140003bf5  pop     r14
0x140003bf7  pop     rdi
0x140003bf8  pop     rsi
0x140003bf9  pop     rbx
0x140003bfa  pop     rbp
0x140003bfb  retn
```
