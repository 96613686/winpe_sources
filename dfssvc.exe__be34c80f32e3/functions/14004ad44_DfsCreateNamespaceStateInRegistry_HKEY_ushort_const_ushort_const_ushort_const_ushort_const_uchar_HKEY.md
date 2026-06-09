# DfsCreateNamespaceStateInRegistry(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,uchar,HKEY__ * *)

- ea: `0x14004ad44`
- end: `0x14004afab`
- name: `?DfsCreateNamespaceStateInRegistry@@YAKPEAUHKEY__@@PEBG111EPEAPEAU1@@Z`
- size: `615`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, HKEY *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000c2bc`
- `0x140021e40`
- `0x140045478`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x14003395c`
- `0x14004ad44`

## import_xrefs

- `msvcrt!wcschr` at `0x14004ada1`
- `msvcrt!wcschr` at `0x14004ada1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004aed8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004af24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004af74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004aed8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004af24`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004af74`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004ae8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004ae8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004ae12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004ae12`

## pseudocode

```c
__int64 __fastcall DfsCreateNamespaceStateInRegistry(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        BYTE *lpData,
        unsigned __int8 a6,
        HKEY *a7)
{
  struct _SECURITY_ATTRIBUTES *dwOptions; // r11
  const unsigned __int16 *v9; // rbp
  unsigned __int64 v11; // rsi
  unsigned __int16 *v12; // r15
  __int64 v13; // rdi
  wchar_t *v14; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  unsigned int v18; // ebx
  HKEY v19; // rcx
  __int64 v21; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-30h] BYREF

  dwOptions = 0;
  hKey = 0;
  dwDisposition = 0;
  v9 = a3;
  LODWORD(v11) = 0;
  v12 = 0;
  if ( a7 )
    *a7 = 0;
  v13 = -1;
  if ( a6 )
  {
    v14 = wcschr(a3, 0x2Eu);
    dwOptions = 0;
    if ( v14 )
    {
      v15 = v14 - v9 + 1;
    }
    else
    {
      v16 = -1;
      do
        ++v16;
      while ( v9[v16] );
      v11 = v16 + 1;
      v15 = v11;
      if ( v11 <= 0x10 )
        goto LABEL_18;
    }
    v11 = 16;
    if ( v15 < 0x10 )
      v11 = v15;
    v17 = (unsigned __int16 *)operator new(saturated_mul(v11, 2u));
    v12 = v17;
    if ( !v17 )
    {
      v18 = 8;
LABEL_13:
      v19 = hKey;
      goto LABEL_14;
    }
    StringCchCopyNW(v17, v11, v9, v11 - 1);
  }
LABEL_18:
  v18 = RegCreateKeyExW(a1, a2, 0, (LPWSTR)&Class, (DWORD)dwOptions, 0x2001Fu, dwOptions, &hKey, &dwDisposition);
  if ( v18 )
    goto LABEL_13;
  if ( a6 )
  {
    if ( v12 )
      v9 = v12;
    v18 = RegSetValueExW(hKey, L"ServerName", 0, 1u, (const BYTE *)v9, 2 * v11);
    if ( v18 )
      goto LABEL_13;
  }
  v21 = -1;
  do
    ++v21;
  while ( *(_WORD *)&a4[2 * v21] );
  v18 = RegSetValueExW(hKey, L"RootShare", 0, 1u, a4, 2 * v21 + 2);
  if ( v18 )
    goto LABEL_13;
  do
    ++v13;
  while ( *(_WORD *)&lpData[2 * v13] );
  v18 = RegSetValueExW(hKey, L"LogicalShare", 0, 1u, lpData, 2 * v13 + 2);
  if ( v18 || !a7 )
    goto LABEL_13;
  v19 = 0;
  *a7 = hKey;
  hKey = 0;
LABEL_14:
  if ( v19 )
    RegCloseKey(v19);
  operator delete(v12);
  return v18;
}

```

## disassembly

```asm
0x14004ad44  mov     rax, rsp
0x14004ad47  mov     [rax+10h], rbx
0x14004ad4b  mov     [rax+18h], rbp
0x14004ad4f  mov     [rax+8], rcx
0x14004ad53  push    rsi
0x14004ad54  push    rdi
0x14004ad55  push    r13
0x14004ad57  push    r14
0x14004ad59  push    r15
0x14004ad5b  sub     rsp, 60h
0x14004ad5f  mov     r14, [rsp+88h+arg_30]
0x14004ad67  xor     r11d, r11d
0x14004ad6a  mov     [rax-30h], r11
0x14004ad6e  mov     r13, r9
0x14004ad71  mov     [rax-38h], r11d
0x14004ad75  mov     rbp, r8
0x14004ad78  mov     rbx, rdx
0x14004ad7b  mov     esi, r11d
0x14004ad7e  mov     r15d, r11d
0x14004ad81  test    r14, r14
0x14004ad84  jz      short loc_14004AD89
0x14004ad86  mov     [r14], r11
0x14004ad89  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14004ad8d  cmp     [rsp+88h+arg_28], r11b
0x14004ad95  jz      loc_14004AE54
0x14004ad9b  lea     edx, [rdi+2Fh]; Ch
0x14004ad9e  mov     rcx, rbp; Str
0x14004ada1  call    cs:__imp_wcschr
0x14004ada8  nop     dword ptr [rax+rax+00h]
0x14004adad  xor     r11d, r11d
0x14004adb0  test    rax, rax
0x14004adb3  jz      short loc_14004ADC0
0x14004adb5  sub     rax, rbp
0x14004adb8  sar     rax, 1
0x14004adbb  inc     rax
0x14004adbe  jmp     short loc_14004ADDA
0x14004adc0  mov     rsi, rdi
0x14004adc3  inc     rsi
0x14004adc6  cmp     [rbp+rsi*2+0], r11w
0x14004adcc  jnz     short loc_14004ADC3
0x14004adce  inc     rsi
0x14004add1  mov     rax, rsi
0x14004add4  cmp     rsi, 10h
0x14004add8  jbe     short loc_14004AE54
0x14004adda  mov     esi, 10h
0x14004addf  cmp     rax, rsi
0x14004ade2  cmovb   rsi, rax
0x14004ade6  mov     eax, 2
0x14004adeb  mul     rsi
0x14004adee  cmovo   rax, rdi
0x14004adf2  mov     rcx, rax; Size
0x14004adf5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004adfa  xor     r11d, r11d
0x14004adfd  mov     r15, rax
0x14004ae00  test    rax, rax
0x14004ae03  jnz     short loc_14004AE42
0x14004ae05  lea     ebx, [rax+8]
0x14004ae08  mov     rcx, [rsp+88h+hKey]; hKey
0x14004ae0d  test    rcx, rcx
0x14004ae10  jz      short loc_14004AE1E
0x14004ae12  call    cs:__imp_RegCloseKey
0x14004ae19  nop     dword ptr [rax+rax+00h]
0x14004ae1e  mov     rcx, r15; Block
0x14004ae21  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004ae26  lea     r11, [rsp+88h+var_28]
0x14004ae2b  mov     eax, ebx
0x14004ae2d  mov     rbx, [r11+38h]
0x14004ae31  mov     rbp, [r11+40h]
0x14004ae35  mov     rsp, r11
0x14004ae38  pop     r15
0x14004ae3a  pop     r14
0x14004ae3c  pop     r13
0x14004ae3e  pop     rdi
0x14004ae3f  pop     rsi
0x14004ae40  retn
0x14004ae42  lea     r9, [rsi-1]; unsigned __int64
0x14004ae46  mov     r8, rbp; unsigned __int16 *
0x14004ae49  mov     rdx, rsi; unsigned __int64
0x14004ae4c  mov     rcx, rax; unsigned __int16 *
0x14004ae4f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14004ae54  mov     rcx, [rsp+88h+arg_0]; hKey
0x14004ae5c  lea     rax, [rsp+88h+dwDisposition]
0x14004ae61  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x14004ae66  lea     r9, Class; lpClass
0x14004ae6d  lea     rax, [rsp+88h+hKey]
0x14004ae72  xor     r8d, r8d; Reserved
0x14004ae75  mov     [rsp+88h+phkResult], rax; phkResult
0x14004ae7a  mov     rdx, rbx; lpSubKey
0x14004ae7d  mov     [rsp+88h+lpSecurityAttributes], r11; lpSecurityAttributes
0x14004ae82  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x14004ae8a  mov     [rsp+88h+dwOptions], r11d; dwOptions
0x14004ae8f  call    cs:__imp_RegCreateKeyExW
0x14004ae96  nop     dword ptr [rax+rax+00h]
0x14004ae9b  xor     r11d, r11d
0x14004ae9e  mov     ebx, eax
0x14004aea0  test    eax, eax
0x14004aea2  jnz     loc_14004AE08
0x14004aea8  cmp     [rsp+88h+arg_28], r11b
0x14004aeb0  jz      short loc_14004AEF1
0x14004aeb2  mov     rcx, [rsp+88h+hKey]; hKey
0x14004aeb7  lea     eax, [rsi+rsi]
0x14004aeba  mov     [rsp+88h+samDesired], eax; cbData
0x14004aebe  lea     r9d, [rbx+1]; dwType
0x14004aec2  test    r15, r15
0x14004aec5  lea     rdx, ValueName; "ServerName"
0x14004aecc  cmovnz  rbp, r15
0x14004aed0  xor     r8d, r8d; Reserved
0x14004aed3  mov     qword ptr [rsp+88h+dwOptions], rbp; lpData
0x14004aed8  call    cs:__imp_RegSetValueExW
0x14004aedf  nop     dword ptr [rax+rax+00h]
0x14004aee4  xor     r11d, r11d
0x14004aee7  mov     ebx, eax
0x14004aee9  test    eax, eax
0x14004aeeb  jnz     loc_14004AE08
0x14004aef1  mov     rax, rdi
0x14004aef4  inc     rax
0x14004aef7  cmp     [r13+rax*2+0], r11w
0x14004aefd  jnz     short loc_14004AEF4
0x14004aeff  mov     rcx, [rsp+88h+hKey]; hKey
0x14004af04  lea     eax, ds:2[rax*2]
0x14004af0b  mov     [rsp+88h+samDesired], eax; cbData
0x14004af0f  lea     rdx, aRootshare; "RootShare"
0x14004af16  mov     r9d, 1; dwType
0x14004af1c  mov     qword ptr [rsp+88h+dwOptions], r13; lpData
0x14004af21  xor     r8d, r8d; Reserved
0x14004af24  call    cs:__imp_RegSetValueExW
0x14004af2b  nop     dword ptr [rax+rax+00h]
0x14004af30  xor     r11d, r11d
0x14004af33  mov     ebx, eax
0x14004af35  test    eax, eax
0x14004af37  jnz     loc_14004AE08
0x14004af3d  mov     rcx, [rsp+88h+lpData]
0x14004af45  inc     rdi
0x14004af48  cmp     [rcx+rdi*2], r11w
0x14004af4d  jnz     short loc_14004AF45
0x14004af4f  lea     eax, ds:2[rdi*2]
0x14004af56  mov     r9d, 1; dwType
0x14004af5c  mov     [rsp+88h+samDesired], eax; cbData
0x14004af60  lea     rdx, aLogicalshare; "LogicalShare"
0x14004af67  mov     qword ptr [rsp+88h+dwOptions], rcx; lpData
0x14004af6c  xor     r8d, r8d; Reserved
0x14004af6f  mov     rcx, [rsp+88h+hKey]; hKey
0x14004af74  call    cs:__imp_RegSetValueExW
0x14004af7b  nop     dword ptr [rax+rax+00h]
0x14004af80  xor     r11d, r11d
0x14004af83  mov     ebx, eax
0x14004af85  test    eax, eax
0x14004af87  jnz     loc_14004AE08
0x14004af8d  test    r14, r14
0x14004af90  jz      loc_14004AE08
0x14004af96  mov     rax, [rsp+88h+hKey]
0x14004af9b  mov     ecx, r11d
0x14004af9e  mov     [r14], rax
0x14004afa1  mov     [rsp+88h+hKey], rcx
0x14004afa6  jmp     loc_14004AE0D
```
