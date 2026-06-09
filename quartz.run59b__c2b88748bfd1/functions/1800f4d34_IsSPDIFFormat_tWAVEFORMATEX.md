# IsSPDIFFormat(tWAVEFORMATEX *)

- ea: `0x1800f4d34`
- end: `0x1800f4f30`
- name: `?IsSPDIFFormat@@YAHPEAUtWAVEFORMATEX@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(struct tWAVEFORMATEX *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009c20`
- `0x180030d80`

## callees

- `0x1800388a0`
- `0x1800f4d34`
- `0x18015bb8c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800f4df1`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f4df1`
- `ADVAPI32!RegEnumKeyW` at `0x1800f4e1e`
- `ADVAPI32!RegEnumKeyW` at `0x1800f4e1e`
- `ADVAPI32!RegCloseKey` at `0x1800f4eff`
- `ADVAPI32!RegCloseKey` at `0x1800f4eff`
- `ole32!CLSIDFromString` at `0x1800f4e3c`
- `ole32!CLSIDFromString` at `0x1800f4e3c`

## pseudocode

```c
_BOOL8 __fastcall IsSPDIFFormat(struct tWAVEFORMATEX *a1)
{
  HKEY v1; // rbp
  BOOL v3; // edi
  DWORD v4; // esi
  WORD wFormatTag; // r12
  unsigned int v6; // r15d
  __int64 v7; // r14
  __int64 v8; // rax
  HKEY hKey; // [rsp+30h] [rbp-268h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-258h] BYREF

  v1 = 0;
  hKey = 0;
  if ( a1
    && a1->wFormatTag == 0xFFFE
    && HIWORD(a1[1].nAvgBytesPerSec) == 3306
    && a1[1].nBlockAlign == 16
    && LOBYTE(a1[1].wBitsPerSample) == 0x80
    && !HIBYTE(a1[1].wBitsPerSample)
    && !LOBYTE(a1[1].cbSize)
    && HIBYTE(a1[1].cbSize) == 0xAA
    && !LOBYTE(a1[2].wFormatTag)
    && HIBYTE(a1[2].wFormatTag) == 56
    && LOBYTE(a1[2].nChannels) == 0x9B
    && HIBYTE(a1[2].nChannels) == 113 )
  {
    return 1;
  }
  v4 = g_cCompressedPassThruFormats;
  if ( g_cCompressedPassThruFormats )
  {
LABEL_20:
    v3 = 0;
    if ( !a1 || !v4 )
      goto LABEL_35;
    wFormatTag = a1->wFormatTag;
    v6 = 0;
    while ( 1 )
    {
      v7 = 16LL * v6;
      if ( wFormatTag == 0xFFFE )
      {
        v8 = *(_QWORD *)((char *)&a1[1].nSamplesPerSec + 2)
           - *(_QWORD *)((char *)&g_rgCompressedPassThruFormats.Data1 + v7);
        if ( !v8 )
          v8 = *(_QWORD *)&a1[1].wBitsPerSample - *(_QWORD *)&g_rgCompressedPassThruFormats.Data4[v7];
        v3 = v8 == 0;
        if ( !v8 )
          goto LABEL_35;
      }
      else if ( !memcmp_0(
                   (char *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data1 + 2,
                   (char *)&g_rgCompressedPassThruFormats.Data1 + v7 + 2,
                   0xEu) )
      {
        if ( *(_WORD *)((char *)&g_rgCompressedPassThruFormats.Data1 + v7) == wFormatTag )
        {
          v3 = 1;
          goto LABEL_35;
        }
        v3 = 0;
      }
      if ( ++v6 >= v4 )
        goto LABEL_35;
    }
  }
  v3 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\SPDIF_Formats",
          0,
          8u,
          &hKey) )
  {
    do
    {
      if ( RegEnumKeyW(hKey, v4, Name, 0x104u) )
        break;
      if ( CLSIDFromString(Name, &g_rgCompressedPassThruFormats + v4) < 0 )
        break;
      ++v4;
    }
    while ( v4 < 0x20 );
    v1 = hKey;
    g_cCompressedPassThruFormats = v4;
    goto LABEL_20;
  }
  v1 = hKey;
LABEL_35:
  if ( v1 )
    RegCloseKey(v1);
  return v3;
}

```

## disassembly

```asm
0x1800f4d34  push    rbx
0x1800f4d36  push    rbp
0x1800f4d37  push    rsi
0x1800f4d38  push    rdi
0x1800f4d39  push    r12
0x1800f4d3b  push    r14
0x1800f4d3d  push    r15
0x1800f4d3f  sub     rsp, 260h
0x1800f4d46  mov     rax, cs:__security_cookie
0x1800f4d4d  xor     rax, rsp
0x1800f4d50  mov     [rsp+298h+var_48], rax
0x1800f4d58  xor     ebp, ebp
0x1800f4d5a  mov     rbx, rcx
0x1800f4d5d  mov     [rsp+298h+hKey], rbp
0x1800f4d62  mov     edx, 0FFFEh
0x1800f4d67  test    rcx, rcx
0x1800f4d6a  jz      short loc_1800F4DBB
0x1800f4d6c  cmp     [rcx], dx
0x1800f4d6f  jnz     short loc_1800F4DBB
0x1800f4d71  mov     eax, 0CEAh
0x1800f4d76  cmp     [rcx+1Ch], ax
0x1800f4d7a  jnz     short loc_1800F4DBB
0x1800f4d7c  cmp     word ptr [rcx+1Eh], 10h
0x1800f4d81  jnz     short loc_1800F4DBB
0x1800f4d83  cmp     byte ptr [rcx+20h], 80h
0x1800f4d87  jnz     short loc_1800F4DBB
0x1800f4d89  cmp     [rcx+21h], bpl
0x1800f4d8d  jnz     short loc_1800F4DBB
0x1800f4d8f  cmp     [rcx+22h], bpl
0x1800f4d93  jnz     short loc_1800F4DBB
0x1800f4d95  cmp     byte ptr [rcx+23h], 0AAh
0x1800f4d99  jnz     short loc_1800F4DBB
0x1800f4d9b  cmp     [rcx+24h], bpl
0x1800f4d9f  jnz     short loc_1800F4DBB
0x1800f4da1  cmp     byte ptr [rcx+25h], 38h ; '8'
0x1800f4da5  jnz     short loc_1800F4DBB
0x1800f4da7  cmp     byte ptr [rcx+26h], 9Bh
0x1800f4dab  jnz     short loc_1800F4DBB
0x1800f4dad  cmp     byte ptr [rcx+27h], 71h ; 'q'
0x1800f4db1  jnz     short loc_1800F4DBB
0x1800f4db3  lea     edi, [rbp+1]
0x1800f4db6  jmp     loc_1800F4F0B
0x1800f4dbb  mov     esi, cs:?g_cCompressedPassThruFormats@@3IA; uint g_cCompressedPassThruFormats
0x1800f4dc1  lea     rcx, ?g_rgCompressedPassThruFormats@@3PAU_GUID@@A; _GUID near * g_rgCompressedPassThruFormats
0x1800f4dc8  test    esi, esi
0x1800f4dca  jnz     loc_1800F4E6A
0x1800f4dd0  lea     rax, [rsp+298h+hKey]
0x1800f4dd5  xor     r8d, r8d; ulOptions
0x1800f4dd8  lea     r9d, [rsi+8]; samDesired
0x1800f4ddc  mov     [rsp+298h+phkResult], rax; phkResult
0x1800f4de1  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800f4de8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f4def  xor     edi, edi
0x1800f4df1  call    cs:__imp_RegOpenKeyExW
0x1800f4df8  nop     dword ptr [rax+rax+00h]
0x1800f4dfd  test    eax, eax
0x1800f4dff  jnz     loc_1800F4EAF
0x1800f4e05  lea     rdi, ?g_rgCompressedPassThruFormats@@3PAU_GUID@@A; _GUID near * g_rgCompressedPassThruFormats
0x1800f4e0c  mov     rcx, [rsp+298h+hKey]; hKey
0x1800f4e11  lea     r8, [rsp+298h+Name]; lpName
0x1800f4e16  mov     r9d, 104h; cchName
0x1800f4e1c  mov     edx, esi; dwIndex
0x1800f4e1e  call    cs:__imp_RegEnumKeyW
0x1800f4e25  nop     dword ptr [rax+rax+00h]
0x1800f4e2a  test    eax, eax
0x1800f4e2c  jnz     short loc_1800F4E53
0x1800f4e2e  mov     edx, esi
0x1800f4e30  lea     rcx, [rsp+298h+Name]; lpsz
0x1800f4e35  shl     rdx, 4
0x1800f4e39  add     rdx, rdi; pclsid
0x1800f4e3c  call    cs:__imp_CLSIDFromString
0x1800f4e43  nop     dword ptr [rax+rax+00h]
0x1800f4e48  test    eax, eax
0x1800f4e4a  js      short loc_1800F4E53
0x1800f4e4c  inc     esi
0x1800f4e4e  cmp     esi, 20h ; ' '
0x1800f4e51  jb      short loc_1800F4E0C
0x1800f4e53  mov     rbp, [rsp+298h+hKey]
0x1800f4e58  lea     rcx, ?g_rgCompressedPassThruFormats@@3PAU_GUID@@A; _GUID near * g_rgCompressedPassThruFormats
0x1800f4e5f  mov     cs:?g_cCompressedPassThruFormats@@3IA, esi; uint g_cCompressedPassThruFormats
0x1800f4e65  mov     edx, 0FFFEh
0x1800f4e6a  xor     edi, edi
0x1800f4e6c  test    rbx, rbx
0x1800f4e6f  jz      loc_1800F4EF7
0x1800f4e75  test    esi, esi
0x1800f4e77  jz      short loc_1800F4EF7
0x1800f4e79  movzx   r12d, word ptr [rbx]
0x1800f4e7d  xor     r15d, r15d
0x1800f4e80  mov     r14d, r15d
0x1800f4e83  shl     r14, 4
0x1800f4e87  cmp     r12w, dx
0x1800f4e8b  jnz     short loc_1800F4EB6
0x1800f4e8d  mov     rax, [rbx+18h]
0x1800f4e91  sub     rax, [r14+rcx]
0x1800f4e95  jnz     short loc_1800F4EA0
0x1800f4e97  mov     rax, [rbx+20h]
0x1800f4e9b  sub     rax, [r14+rcx+8]
0x1800f4ea0  xor     edi, edi
0x1800f4ea2  test    rax, rax
0x1800f4ea5  setz    dil
0x1800f4ea9  test    edi, edi
0x1800f4eab  jnz     short loc_1800F4EF7
0x1800f4ead  jmp     short loc_1800F4EE8
0x1800f4eaf  mov     rbp, [rsp+298h+hKey]
0x1800f4eb4  jmp     short loc_1800F4EF7
0x1800f4eb6  lea     rdx, [rcx+2]
0x1800f4eba  mov     r8d, 0Eh; Size
0x1800f4ec0  add     rdx, r14; Buf2
0x1800f4ec3  lea     rcx, _GUID_00000000_0000_0010_8000_00aa00389b71.Data1+2; Buf1
0x1800f4eca  call    memcmp_0
0x1800f4ecf  lea     rcx, ?g_rgCompressedPassThruFormats@@3PAU_GUID@@A; _GUID near * g_rgCompressedPassThruFormats
0x1800f4ed6  test    eax, eax
0x1800f4ed8  jnz     short loc_1800F4EE3
0x1800f4eda  cmp     [r14+rcx], r12w
0x1800f4edf  jz      short loc_1800F4EF2
0x1800f4ee1  xor     edi, edi
0x1800f4ee3  mov     edx, 0FFFEh
0x1800f4ee8  inc     r15d
0x1800f4eeb  cmp     r15d, esi
0x1800f4eee  jb      short loc_1800F4E80
0x1800f4ef0  jmp     short loc_1800F4EF7
0x1800f4ef2  mov     edi, 1
0x1800f4ef7  test    rbp, rbp
0x1800f4efa  jz      short loc_1800F4F0B
0x1800f4efc  mov     rcx, rbp; hKey
0x1800f4eff  call    cs:__imp_RegCloseKey
0x1800f4f06  nop     dword ptr [rax+rax+00h]
0x1800f4f0b  mov     eax, edi
0x1800f4f0d  mov     rcx, [rsp+298h+var_48]
0x1800f4f15  xor     rcx, rsp; StackCookie
0x1800f4f18  call    __security_check_cookie
0x1800f4f1d  add     rsp, 260h
0x1800f4f24  pop     r15
0x1800f4f26  pop     r14
0x1800f4f28  pop     r12
0x1800f4f2a  pop     rdi
0x1800f4f2b  pop     rsi
0x1800f4f2c  pop     rbp
0x1800f4f2d  pop     rbx
0x1800f4f2e  retn
```
