# CheckForReadOnlyResource

- ea: `0x180072630`
- end: `0x180072823`
- name: `CheckForReadOnlyResource`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800668c0`

## callees

- `0x180072630`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x18007275d`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18007275d`
- `ntdll!NtQueryVirtualMemory` at `0x1800726d3`
- `ntdll!NtQueryVirtualMemory` at `0x18007272a`
- `ntdll!NtQueryVirtualMemory` at `0x1800726d3`
- `ntdll!NtQueryVirtualMemory` at `0x18007272a`
- `ntdll!NtProtectVirtualMemory` at `0x1800727f9`
- `ntdll!NtProtectVirtualMemory` at `0x1800727f9`

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
0x180072630  mov     r11, rsp
0x180072633  push    rsi
0x180072634  push    rdi
0x180072635  push    r12
0x180072637  push    r14
0x180072639  push    r15
0x18007263b  sub     rsp, 0A0h
0x180072642  mov     r15d, edx
0x180072645  mov     [rsp+0C8h+NumberOfBytesToProtect], 0
0x18007264e  mov     [rsp+0C8h+OldAccessProtection], 0
0x180072656  xorps   xmm0, xmm0
0x180072659  movups  [rsp+0C8h+var_60], xmm0
0x18007265e  movups  [rsp+0C8h+var_50], xmm0
0x180072663  movups  xmmword ptr [r11-40h], xmm0
0x180072668  xor     eax, eax
0x18007266a  movups  [rsp+0C8h+VirtualMemoryInformation], xmm0
0x18007266f  mov     [r11-68h], rax
0x180072673  mov     [r11+10h], eax
0x180072677  mov     [rsp+0C8h+Address], rax
0x18007267c  test    edx, 0FFFFFFFEh
0x180072682  jnz     loc_180072810
0x180072688  mov     rdx, [rcx]
0x18007268b  cmp     dword ptr [rdx], 0C0000005h
0x180072691  jnz     loc_180072810
0x180072697  lea     esi, [rax+1]
0x18007269a  cmp     [rdx+20h], rsi
0x18007269e  jnz     loc_180072810
0x1800726a4  cmp     dword ptr [rdx+18h], 2
0x1800726a8  jb      loc_180072810
0x1800726ae  mov     rdx, [rdx+28h]; Address
0x1800726b2  mov     [rsp+0C8h+Address], rdx
0x1800726b7  mov     [rsp+0C8h+ResultLength], rax; ResultLength
0x1800726bc  mov     [rsp+0C8h+Length], 30h ; '0'; Length
0x1800726c5  lea     r9, [r11-60h]; VirtualMemoryInformation
0x1800726c9  xor     r8d, r8d; VirtualMemoryInformationClass
0x1800726cc  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800726d0  mov     rcx, r12; ProcessHandle
0x1800726d3  call    cs:__imp_NtQueryVirtualMemory
0x1800726da  nop     dword ptr [rax+rax+00h]
0x1800726df  test    eax, eax
0x1800726e1  js      loc_180072810
0x1800726e7  xor     r14d, r14d
0x1800726ea  cmp     [rsp+0C8h+var_3C], 2
0x1800726f2  jnz     loc_18007280B
0x1800726f8  xor     edi, edi
0x1800726fa  cmp     [rsp+0C8h+var_38], 1000000h
0x180072705  jnz     loc_1800727C0
0x18007270b  mov     [rsp+0C8h+ResultLength], rdi; ResultLength
0x180072710  mov     [rsp+0C8h+Length], 18h; Length
0x180072719  lea     r9, [rsp+0C8h+VirtualMemoryInformation]; VirtualMemoryInformation
0x18007271e  lea     r8d, [rsi+5]; VirtualMemoryInformationClass
0x180072722  mov     rdx, [rsp+0C8h+Address]; Address
0x180072727  mov     rcx, r12; ProcessHandle
0x18007272a  call    cs:__imp_NtQueryVirtualMemory
0x180072731  nop     dword ptr [rax+rax+00h]
0x180072736  test    eax, eax
0x180072738  js      loc_180072810
0x18007273e  test    byte ptr [rsp+0C8h+var_68], sil
0x180072743  jnz     loc_180072810
0x180072749  lea     r8d, [rsi+1]; Directory
0x18007274d  lea     r9, [rsp+0C8h+Size]; Size
0x180072755  mov     dl, sil; MappedAsImage
0x180072758  mov     rcx, qword ptr [rsp+0C8h+VirtualMemoryInformation]; BaseAddress
0x18007275d  call    cs:__imp_RtlImageDirectoryEntryToData
0x180072764  nop     dword ptr [rax+rax+00h]
0x180072769  mov     rcx, rax
0x18007276c  mov     [rsp+0C8h+var_80], rax
0x180072771  xor     edx, edx
0x180072773  mov     [rsp+0C8h+var_90], edx
0x180072777  mov     eax, [rsp+0C8h+Size]
0x18007277e  jmp     short loc_1800727A2
0x180072780  mov     edx, eax
0x180072782  xor     ecx, ecx
0x180072784  mov     [rsp+0C8h+var_80], rcx
0x180072789  xor     eax, eax
0x18007278b  mov     [rsp+0C8h+Size], eax
0x180072792  mov     [rsp+0C8h+var_90], edx
0x180072796  lea     esi, [rcx+1]
0x180072799  or      r12, 0FFFFFFFFFFFFFFFFh
0x18007279d  mov     r14d, eax
0x1800727a0  mov     edi, eax
0x1800727a2  test    edx, edx
0x1800727a4  js      short loc_1800727D3
0x1800727a6  test    rcx, rcx
0x1800727a9  jz      short loc_1800727D3
0x1800727ab  cmp     [rsp+0C8h+Address], rcx
0x1800727b0  jb      short loc_1800727D3
0x1800727b2  add     rax, rcx
0x1800727b5  cmp     [rsp+0C8h+Address], rax
0x1800727ba  jnb     short loc_1800727D3
0x1800727bc  mov     edi, esi
0x1800727be  jmp     short loc_1800727D3
0x1800727c0  cmp     [rsp+0C8h+var_38], 40000h
0x1800727cb  jnz     short loc_1800727D3
0x1800727cd  test    sil, r15b
0x1800727d0  cmovnz  edi, esi
0x1800727d3  test    edi, edi
0x1800727d5  jz      short loc_18007280B
0x1800727d7  mov     [rsp+0C8h+NumberOfBytesToProtect], rsi
0x1800727dc  lea     rax, [rsp+0C8h+OldAccessProtection]
0x1800727e1  mov     [rsp+0C8h+Length], rax; OldAccessProtection
0x1800727e6  mov     r9d, 8; NewAccessProtection
0x1800727ec  lea     r8, [rsp+0C8h+NumberOfBytesToProtect]; NumberOfBytesToProtect
0x1800727f1  lea     rdx, [rsp+0C8h+Address]; BaseAddress
0x1800727f6  mov     rcx, r12; ProcessHandle
0x1800727f9  call    cs:__imp_NtProtectVirtualMemory
0x180072800  nop     dword ptr [rax+rax+00h]
0x180072805  test    eax, eax
0x180072807  cmovns  r14d, r12d
0x18007280b  mov     eax, r14d
0x18007280e  jmp     short loc_180072812
0x180072810  xor     eax, eax
0x180072812  add     rsp, 0A0h
0x180072819  pop     r15
0x18007281b  pop     r14
0x18007281d  pop     r12
0x18007281f  pop     rdi
0x180072820  pop     rsi
0x180072821  retn
```
