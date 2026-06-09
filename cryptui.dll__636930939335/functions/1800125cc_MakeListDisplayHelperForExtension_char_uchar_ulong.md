# MakeListDisplayHelperForExtension(char *,uchar *,ulong)

- ea: `0x1800125cc`
- end: `0x1800126be`
- name: `?MakeListDisplayHelperForExtension@@YAPEAU_LIST_DISPLAY_HELPER@@PEADPEAEK@Z`
- size: `242`
- prototype: `struct _LIST_DISPLAY_HELPER *__fastcall(LPCSTR lpszStructType, unsigned __int8 *Src, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000bf9c`
- `0x180011a28`
- `0x18002f404`

## callees

- `0x180001f66`
- `0x180012568`
- `0x1800125cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012626`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012689`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012626`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012689`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001267e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001267e`
- `CRYPT32!CryptFormatObject` at `0x180012610`
- `CRYPT32!CryptFormatObject` at `0x180012664`
- `CRYPT32!CryptFormatObject` at `0x180012610`
- `CRYPT32!CryptFormatObject` at `0x180012664`

## pseudocode

```c
struct _LIST_DISPLAY_HELPER *__fastcall MakeListDisplayHelperForExtension(
        LPCSTR lpszStructType,
        unsigned __int8 *Src,
        DWORD cbEncoded)
{
  SIZE_T v3; // rdi
  HLOCAL pbFormat; // rbx
  unsigned int v8; // r9d
  unsigned __int8 *v9; // r8
  int v10; // ecx
  unsigned __int16 *v11; // rdx
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rbx
  SIZE_T uBytes; // [rsp+98h] [rbp+20h] BYREF

  v3 = cbEncoded;
  LODWORD(uBytes) = 0;
  if ( CryptFormatObject(1u, 0, 0x11u, 0, lpszStructType, Src, cbEncoded, 0, (DWORD *)&uBytes) )
  {
    pbFormat = LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( !pbFormat )
      return 0;
    if ( !CryptFormatObject(1u, 0, 0x11u, 0, lpszStructType, Src, v3, pbFormat, (DWORD *)&uBytes) )
    {
      LocalFree(pbFormat);
      return 0;
    }
    v8 = 0;
    v9 = 0;
    v10 = 0;
    v11 = (unsigned __int16 *)pbFormat;
  }
  else
  {
    v12 = (unsigned __int8 *)LocalAlloc(0x40u, v3);
    v13 = v12;
    if ( v12 )
      memcpy_0(v12, Src, v3);
    v11 = 0;
    v8 = v3;
    v9 = v13;
    v10 = 1;
  }
  return MakeListDisplayHelper(v10, v11, v9, v8);
}

```

## disassembly

```asm
0x1800125cc  mov     r11, rsp
0x1800125cf  push    rbx
0x1800125d0  push    rbp
0x1800125d1  push    rsi
0x1800125d2  push    rdi
0x1800125d3  sub     rsp, 58h
0x1800125d7  mov     edi, r8d
0x1800125da  lea     rax, [r11+20h]
0x1800125de  mov     [r11-38h], rax
0x1800125e2  mov     rbp, rdx
0x1800125e5  mov     qword ptr [r11-40h], 0
0x1800125ed  xor     r9d, r9d; pFormatStruct
0x1800125f0  mov     [rsp+78h+cbEncoded], edi; cbEncoded
0x1800125f4  mov     rsi, rcx
0x1800125f7  mov     [r11-50h], rdx
0x1800125fb  xor     edx, edx; dwFormatType
0x1800125fd  mov     [r11-58h], rcx
0x180012601  lea     r8d, [r9+11h]; dwFormatStrType
0x180012605  mov     dword ptr [r11+20h], 0
0x18001260d  lea     ecx, [rdx+1]; dwCertEncodingType
0x180012610  call    cs:__imp_CryptFormatObject
0x180012616  mov     ecx, 40h ; '@'; uFlags
0x18001261b  test    eax, eax
0x18001261d  jz      short loc_180012686
0x18001261f  mov     edx, dword ptr [rsp+78h+uBytes]; uBytes
0x180012626  call    cs:__imp_LocalAlloc
0x18001262c  mov     rbx, rax
0x18001262f  test    rax, rax
0x180012632  jnz     short loc_180012638
0x180012634  xor     eax, eax
0x180012636  jmp     short loc_1800126B5
0x180012638  lea     rax, [rsp+78h+uBytes]
0x180012640  xor     r9d, r9d; pFormatStruct
0x180012643  mov     [rsp+78h+pcbFormat], rax; pcbFormat
0x180012648  xor     edx, edx; dwFormatType
0x18001264a  mov     [rsp+78h+pbFormat], rbx; pbFormat
0x18001264f  mov     [rsp+78h+cbEncoded], edi; cbEncoded
0x180012653  mov     [rsp+78h+pbEncoded], rbp; pbEncoded
0x180012658  lea     r8d, [r9+11h]; dwFormatStrType
0x18001265c  lea     ecx, [rdx+1]; dwCertEncodingType
0x18001265f  mov     [rsp+78h+lpszStructType], rsi; lpszStructType
0x180012664  call    cs:__imp_CryptFormatObject
0x18001266a  test    eax, eax
0x18001266c  jz      short loc_18001267B
0x18001266e  xor     r9d, r9d
0x180012671  xor     r8d, r8d
0x180012674  xor     ecx, ecx
0x180012676  mov     rdx, rbx
0x180012679  jmp     short loc_1800126B0
0x18001267b  mov     rcx, rbx; hMem
0x18001267e  call    cs:__imp_LocalFree
0x180012684  jmp     short loc_180012634
0x180012686  mov     rdx, rdi; uBytes
0x180012689  call    cs:__imp_LocalAlloc
0x18001268f  mov     rbx, rax
0x180012692  test    rax, rax
0x180012695  jz      short loc_1800126A5
0x180012697  mov     r8, rdi; Size
0x18001269a  mov     rdx, rbp; Src
0x18001269d  mov     rcx, rax; void *
0x1800126a0  call    memcpy_0
0x1800126a5  xor     edx, edx; unsigned __int16 *
0x1800126a7  mov     r9d, edi; unsigned int
0x1800126aa  mov     r8, rbx; unsigned __int8 *
0x1800126ad  lea     ecx, [rdx+1]; int
0x1800126b0  call    ?MakeListDisplayHelper@@YAPEAU_LIST_DISPLAY_HELPER@@HPEAGPEAEK@Z; MakeListDisplayHelper(int,ushort *,uchar *,ulong)
0x1800126b5  add     rsp, 58h
0x1800126b9  pop     rdi
0x1800126ba  pop     rsi
0x1800126bb  pop     rbp
0x1800126bc  pop     rbx
0x1800126bd  retn
```
