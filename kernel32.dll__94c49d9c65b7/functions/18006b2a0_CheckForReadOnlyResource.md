# CheckForReadOnlyResource

- ea: `0x18006b2a0`
- end: `0x18006b47a`
- name: `CheckForReadOnlyResource`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180060160`

## callees

- `0x18006b2a0`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x18006b3c1`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18006b3c1`
- `ntdll!NtQueryVirtualMemory` at `0x18006b343`
- `ntdll!NtQueryVirtualMemory` at `0x18006b394`
- `ntdll!NtQueryVirtualMemory` at `0x18006b343`
- `ntdll!NtQueryVirtualMemory` at `0x18006b394`
- `ntdll!NtProtectVirtualMemory` at `0x18006b457`
- `ntdll!NtProtectVirtualMemory` at `0x18006b457`

## pseudocode

```c
__int64 __fastcall CheckForReadOnlyResource(_QWORD *a1, int a2)
{
  char v2; // r15
  _DWORD *v3; // rdx
  unsigned int v4; // r14d
  BOOL v5; // edi
  char *v6; // rcx
  PVOID Address; // [rsp+30h] [rbp-98h] BYREF
  int v9; // [rsp+38h] [rbp-90h]
  ULONG OldAccessProtection; // [rsp+3Ch] [rbp-8Ch] BYREF
  SIZE_T NumberOfBytesToProtect[2]; // [rsp+40h] [rbp-88h] BYREF
  __int128 VirtualMemoryInformation; // [rsp+50h] [rbp-78h] BYREF
  __int64 v13; // [rsp+60h] [rbp-68h]
  _OWORD v14[2]; // [rsp+68h] [rbp-60h] BYREF
  __int128 v15; // [rsp+88h] [rbp-40h]
  ULONG Size; // [rsp+D8h] [rbp+10h] BYREF

  v2 = a2;
  NumberOfBytesToProtect[0] = 0;
  OldAccessProtection = 0;
  memset(v14, 0, sizeof(v14));
  v15 = 0;
  VirtualMemoryInformation = 0;
  v13 = 0;
  Size = 0;
  Address = 0;
  if ( (a2 & 0xFFFFFFFE) == 0 )
  {
    v3 = (_DWORD *)*a1;
    if ( *(_DWORD *)*a1 == -1073741819 && *((_QWORD *)v3 + 4) == 1 && v3[6] >= 2u )
    {
      Address = (PVOID)*((_QWORD *)v3 + 5);
      if ( NtQueryVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, Address, MemoryBasicInformation, v14, 0x30u, 0) >= 0 )
      {
        v4 = 0;
        if ( DWORD1(v15) != 2 )
          return v4;
        v5 = 0;
        if ( DWORD2(v15) != 0x1000000 )
        {
          if ( DWORD2(v15) == 0x40000 )
            v5 = (v2 & 1) != 0;
          goto LABEL_15;
        }
        if ( NtQueryVirtualMemory(
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               Address,
               MemoryWorkingSetExList|MemorySectionName,
               &VirtualMemoryInformation,
               0x18u,
               0) >= 0
          && (v13 & 1) == 0 )
        {
          v6 = (char *)RtlImageDirectoryEntryToData((PVOID)VirtualMemoryInformation, 1u, 2u, &Size);
          NumberOfBytesToProtect[1] = (SIZE_T)v6;
          v9 = 0;
          if ( v6 && Address >= v6 )
            v5 = Address < &v6[Size];
LABEL_15:
          if ( v5 )
          {
            NumberOfBytesToProtect[0] = 1;
            if ( NtProtectVirtualMemory(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   &Address,
                   NumberOfBytesToProtect,
                   8u,
                   &OldAccessProtection) >= 0 )
              return (unsigned int)-1;
          }
          return v4;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006b2a0  mov     r11, rsp
0x18006b2a3  push    rsi
0x18006b2a4  push    rdi
0x18006b2a5  push    r12
0x18006b2a7  push    r14
0x18006b2a9  push    r15
0x18006b2ab  sub     rsp, 0A0h
0x18006b2b2  mov     r15d, edx
0x18006b2b5  mov     [rsp+0C8h+NumberOfBytesToProtect], 0
0x18006b2be  mov     [rsp+0C8h+OldAccessProtection], 0
0x18006b2c6  xorps   xmm0, xmm0
0x18006b2c9  movups  [rsp+0C8h+var_60], xmm0
0x18006b2ce  movups  [rsp+0C8h+var_50], xmm0
0x18006b2d3  movups  xmmword ptr [r11-40h], xmm0
0x18006b2d8  xor     eax, eax
0x18006b2da  movups  [rsp+0C8h+VirtualMemoryInformation], xmm0
0x18006b2df  mov     [r11-68h], rax
0x18006b2e3  mov     [r11+10h], eax
0x18006b2e7  mov     [rsp+0C8h+Address], rax
0x18006b2ec  test    edx, 0FFFFFFFEh
0x18006b2f2  jnz     loc_18006B468
0x18006b2f8  mov     rdx, [rcx]
0x18006b2fb  cmp     dword ptr [rdx], 0C0000005h
0x18006b301  jnz     loc_18006B468
0x18006b307  lea     esi, [rax+1]
0x18006b30a  cmp     [rdx+20h], rsi
0x18006b30e  jnz     loc_18006B468
0x18006b314  cmp     dword ptr [rdx+18h], 2
0x18006b318  jb      loc_18006B468
0x18006b31e  mov     rdx, [rdx+28h]; Address
0x18006b322  mov     [rsp+0C8h+Address], rdx
0x18006b327  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x18006b32c  mov     [rsp+0C8h+Length], 30h ; '0'; Length
0x18006b335  lea     r9, [r11-60h]; VirtualMemoryInformation
0x18006b339  xor     r8d, r8d; VirtualMemoryInformationClass
0x18006b33c  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006b340  mov     rcx, r12; ProcessHandle
0x18006b343  call    cs:__imp_NtQueryVirtualMemory
0x18006b349  test    eax, eax
0x18006b34b  js      loc_18006B468
0x18006b351  xor     r14d, r14d
0x18006b354  cmp     [rsp+0C8h+var_3C], 2
0x18006b35c  jnz     loc_18006B463
0x18006b362  xor     edi, edi
0x18006b364  cmp     [rsp+0C8h+var_38], 1000000h
0x18006b36f  jnz     loc_18006B41E
0x18006b375  mov     [rsp+0C8h+ResultLength], rdi; ResultLength
0x18006b37a  mov     [rsp+0C8h+Length], 18h; Length
0x18006b383  lea     r9, [rsp+0C8h+VirtualMemoryInformation]; VirtualMemoryInformation
0x18006b388  lea     r8d, [rsi+5]; VirtualMemoryInformationClass
0x18006b38c  mov     rdx, [rsp+0C8h+Address]; Address
0x18006b391  mov     rcx, r12; ProcessHandle
0x18006b394  call    cs:__imp_NtQueryVirtualMemory
0x18006b39a  test    eax, eax
0x18006b39c  js      loc_18006B468
0x18006b3a2  test    byte ptr [rsp+0C8h+var_68], sil
0x18006b3a7  jnz     loc_18006B468
0x18006b3ad  lea     r8d, [rsi+1]; Directory
0x18006b3b1  lea     r9, [rsp+0C8h+Size]; Size
0x18006b3b9  mov     dl, sil; MappedAsImage
0x18006b3bc  mov     rcx, qword ptr [rsp+0C8h+VirtualMemoryInformation]; BaseAddress
0x18006b3c1  call    cs:__imp_RtlImageDirectoryEntryToData
0x18006b3c7  mov     rcx, rax
0x18006b3ca  mov     [rsp+0C8h+var_80], rax
0x18006b3cf  xor     edx, edx
0x18006b3d1  mov     [rsp+0C8h+var_90], edx
0x18006b3d5  mov     eax, [rsp+0C8h+Size]
0x18006b3dc  jmp     short loc_18006B400
0x18006b3de  mov     edx, eax
0x18006b3e0  xor     ecx, ecx
0x18006b3e2  mov     [rsp+0C8h+var_80], rcx
0x18006b3e7  xor     eax, eax
0x18006b3e9  mov     [rsp+0C8h+Size], eax
0x18006b3f0  mov     [rsp+0C8h+var_90], edx
0x18006b3f4  lea     esi, [rcx+1]
0x18006b3f7  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006b3fb  mov     r14d, eax
0x18006b3fe  mov     edi, eax
0x18006b400  test    edx, edx
0x18006b402  js      short loc_18006B431
0x18006b404  test    rcx, rcx
0x18006b407  jz      short loc_18006B431
0x18006b409  cmp     [rsp+0C8h+Address], rcx
0x18006b40e  jb      short loc_18006B431
0x18006b410  add     rax, rcx
0x18006b413  cmp     [rsp+0C8h+Address], rax
0x18006b418  jnb     short loc_18006B431
0x18006b41a  mov     edi, esi
0x18006b41c  jmp     short loc_18006B431
0x18006b41e  cmp     [rsp+0C8h+var_38], 40000h
0x18006b429  jnz     short loc_18006B431
0x18006b42b  test    sil, r15b
0x18006b42e  cmovnz  edi, esi
0x18006b431  test    edi, edi
0x18006b433  jz      short loc_18006B463
0x18006b435  mov     [rsp+0C8h+NumberOfBytesToProtect], rsi
0x18006b43a  lea     rax, [rsp+0C8h+OldAccessProtection]
0x18006b43f  mov     [rsp+0C8h+Length], rax; OldAccessProtection
0x18006b444  mov     r9d, 8; NewAccessProtection
0x18006b44a  lea     r8, [rsp+0C8h+NumberOfBytesToProtect]; NumberOfBytesToProtect
0x18006b44f  lea     rdx, [rsp+0C8h+Address]; BaseAddress
0x18006b454  mov     rcx, r12; ProcessHandle
0x18006b457  call    cs:__imp_NtProtectVirtualMemory
0x18006b45d  test    eax, eax
0x18006b45f  cmovns  r14d, r12d
0x18006b463  mov     eax, r14d
0x18006b466  jmp     short loc_18006B46A
0x18006b468  xor     eax, eax
0x18006b46a  add     rsp, 0A0h
0x18006b471  pop     r15
0x18006b473  pop     r14
0x18006b475  pop     r12
0x18006b477  pop     rdi
0x18006b478  pop     rsi
0x18006b479  retn
```
