# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x18001d414`
- end: `0x18001d5dd`
- name: `?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001054c`

## callees

- `0x18000c440`
- `0x18000f8b0`
- `0x18001cc98`
- `0x18001d414`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d45f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d4da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d45f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d4da`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d514`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d548`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d514`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d548`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        const WCHAR *a3)
{
  BYTE *lpData; // rdi
  LSTATUS v7; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rsi
  DWORD v11; // eax
  DWORD v12; // ebp
  WCHAR *v13; // rax
  WCHAR *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // r14d
  __int64 v17; // rax
  DWORD Type[14]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  Type[0] = 0;
  cbData = 0;
  lpData = 0;
  v7 = RegQueryValueExW(a2, a3, 0, Type, 0, &cbData);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( Type[0] - 1 > 1 || !cbData || (cbData & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(cbData);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_25;
    }
    v9 = RegQueryValueExW(a2, a3, 0, Type, lpData, &cbData);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v10 = (cbData >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = (WCHAR *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2LL * v11);
          v14 = v13;
          if ( !v13 )
            goto LABEL_14;
          v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v13, v12);
          v16 = v15;
          if ( !v15 || v15 > v12 )
          {
            v8 = -2147024774;
            Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v14);
            goto LABEL_25;
          }
          v8 = 0;
          Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(lpData);
          lpData = (BYTE *)v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v17 - 1);
            a1[2] = (BYTE *)(unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v8 = -2147024883;
    }
  }
LABEL_25:
  Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d414  mov     r11, rsp
0x18001d417  mov     [r11+8], rbx
0x18001d41b  mov     [r11+10h], rbp
0x18001d41f  mov     [r11+20h], r9b
0x18001d423  push    rsi
0x18001d424  push    rdi
0x18001d425  push    r12
0x18001d427  push    r14
0x18001d429  push    r15
0x18001d42b  sub     rsp, 40h
0x18001d42f  xor     r12d, r12d
0x18001d432  lea     rax, [r11+20h]
0x18001d436  mov     rsi, r8
0x18001d439  mov     [r11-40h], rax
0x18001d43d  mov     rbp, rdx
0x18001d440  mov     [r11-48h], r12
0x18001d444  mov     r15, rcx
0x18001d447  mov     [r11-38h], r12d
0x18001d44b  mov     rdx, rsi; lpValueName
0x18001d44e  mov     [r11+20h], r12d
0x18001d452  mov     rcx, rbp; hKey
0x18001d455  lea     r9, [r11-38h]; lpType
0x18001d459  xor     r8d, r8d; lpReserved
0x18001d45c  mov     edi, r12d
0x18001d45f  call    cs:__imp_RegQueryValueExW
0x18001d466  nop     dword ptr [rax+rax+00h]
0x18001d46b  mov     ebx, eax
0x18001d46d  mov     r14d, 80070000h
0x18001d473  test    eax, eax
0x18001d475  jle     short loc_18001D47D
0x18001d477  movzx   ebx, ax
0x18001d47a  or      ebx, r14d
0x18001d47d  test    ebx, ebx
0x18001d47f  js      loc_18001D5BB
0x18001d485  mov     eax, [rsp+68h+Type]
0x18001d489  dec     eax
0x18001d48b  cmp     eax, 1
0x18001d48e  ja      loc_18001D5B6
0x18001d494  mov     eax, [rsp+68h+cbData]
0x18001d49b  test    eax, eax
0x18001d49d  jz      loc_18001D5B6
0x18001d4a3  test    al, 1
0x18001d4a5  jnz     loc_18001D5B6
0x18001d4ab  mov     ecx, eax
0x18001d4ad  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x18001d4b2  mov     rdi, rax
0x18001d4b5  test    rax, rax
0x18001d4b8  jz      short loc_18001D538
0x18001d4ba  lea     rax, [rsp+68h+cbData]
0x18001d4c2  xor     r8d, r8d; lpReserved
0x18001d4c5  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001d4ca  lea     r9, [rsp+68h+Type]; lpType
0x18001d4cf  mov     rdx, rsi; lpValueName
0x18001d4d2  mov     [rsp+68h+lpData], rdi; lpData
0x18001d4d7  mov     rcx, rbp; hKey
0x18001d4da  call    cs:__imp_RegQueryValueExW
0x18001d4e1  nop     dword ptr [rax+rax+00h]
0x18001d4e6  mov     ebx, eax
0x18001d4e8  test    eax, eax
0x18001d4ea  jle     short loc_18001D4F2
0x18001d4ec  movzx   ebx, ax
0x18001d4ef  or      ebx, r14d
0x18001d4f2  test    ebx, ebx
0x18001d4f4  js      loc_18001D5BB
0x18001d4fa  mov     esi, [rsp+68h+cbData]
0x18001d501  shr     esi, 1
0x18001d503  dec     esi
0x18001d505  cmp     [rsp+68h+Type], 2
0x18001d50a  jnz     short loc_18001D571
0x18001d50c  xor     r8d, r8d; nSize
0x18001d50f  xor     edx, edx; lpDst
0x18001d511  mov     rcx, rdi; lpSrc
0x18001d514  call    cs:__imp_ExpandEnvironmentStringsW
0x18001d51b  nop     dword ptr [rax+rax+00h]
0x18001d520  mov     ebp, eax
0x18001d522  test    eax, eax
0x18001d524  jz      short loc_18001D571
0x18001d526  mov     ecx, ebp
0x18001d528  add     rcx, rcx
0x18001d52b  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x18001d530  mov     rsi, rax
0x18001d533  test    rax, rax
0x18001d536  jnz     short loc_18001D53F
0x18001d538  mov     ebx, 8007000Eh
0x18001d53d  jmp     short loc_18001D5BB
0x18001d53f  mov     r8d, ebp; nSize
0x18001d542  mov     rdx, rsi; lpDst
0x18001d545  mov     rcx, rdi; lpSrc
0x18001d548  call    cs:__imp_ExpandEnvironmentStringsW
0x18001d54f  nop     dword ptr [rax+rax+00h]
0x18001d554  mov     r14d, eax
0x18001d557  test    eax, eax
0x18001d559  jz      short loc_18001D5A7
0x18001d55b  cmp     eax, ebp
0x18001d55d  ja      short loc_18001D5A7
0x18001d55f  mov     rcx, rdi
0x18001d562  mov     ebx, r12d
0x18001d565  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001d56a  mov     rdi, rsi
0x18001d56d  lea     esi, [r14-1]
0x18001d571  cmp     [rdi+rsi*2], r12w
0x18001d576  jnz     short loc_18001D5B6
0x18001d578  mov     rcx, r15
0x18001d57b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001d580  test    rdi, rdi
0x18001d583  jz      short loc_18001D5A2
0x18001d585  lea     eax, [rsi+1]
0x18001d588  mov     ecx, eax
0x18001d58a  test    eax, eax
0x18001d58c  jz      short loc_18001D5A2
0x18001d58e  dec     rax
0x18001d591  mov     [r15], rdi
0x18001d594  mov     [r15+8], rax
0x18001d598  mov     [r15+10h], rcx
0x18001d59c  mov     [rdi+rcx*2-2], r12w
0x18001d5a2  mov     rdi, r12
0x18001d5a5  jmp     short loc_18001D5BB
0x18001d5a7  mov     rcx, rsi
0x18001d5aa  mov     ebx, 8007007Ah
0x18001d5af  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001d5b4  jmp     short loc_18001D5BB
0x18001d5b6  mov     ebx, 8007000Dh
0x18001d5bb  mov     rcx, rdi
0x18001d5be  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001d5c3  mov     rbp, [rsp+68h+arg_8]
0x18001d5c8  mov     eax, ebx
0x18001d5ca  mov     rbx, [rsp+68h+arg_0]
0x18001d5cf  add     rsp, 40h
0x18001d5d3  pop     r15
0x18001d5d5  pop     r14
0x18001d5d7  pop     r12
0x18001d5d9  pop     rdi
0x18001d5da  pop     rsi
0x18001d5db  retn
```
