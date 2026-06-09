# ReplaceConfig

- ea: `0x18001a9e4`
- end: `0x18001abaa`
- name: `ReplaceConfig`
- size: `454`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008084`

## callees

- `0x180009038`
- `0x18001a9e4`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001aa86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001ab53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001aa86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001ab53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001aa47`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001aa47`

## pseudocode

```c
__int64 __fastcall ReplaceConfig(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v5; // ebp
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  __int64 v8; // r12
  unsigned int v10; // r15d
  unsigned int v11; // edi
  unsigned int v12; // r10d
  __int64 v13; // r8
  unsigned __int64 v14; // r9
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  __int64 v17; // rbx
  LSTATUS v18; // eax

  if ( !a3 || !a2 )
    return 0;
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(a1, CacheScavengerRun, *(unsigned int *)(a1 + 48));
  if ( a3 < 8 )
    return 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  do
  {
    if ( GetTickCount64() / 0x3E8 > *(_QWORD *)(a2 + 24 * v8 + 8) )
    {
      v5 = RegDeleteKeyExW(*(HKEY *)(a1 + 728), *(LPCWSTR *)(a2 + 24 * v8), 0, 0);
      ++v6;
      *(_QWORD *)(a2 + 24 * v8 + 16) = 0x7FFFFFFFFFFFFFFFLL;
    }
    ++v7;
    ++v8;
  }
  while ( v7 < a3 );
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 85, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v6);
  if ( a3 < 0x80 )
    return 0;
  if ( v6 < 8 )
  {
    v10 = 0;
    v11 = 8 - v6;
    if ( 8 != v6 )
    {
      do
      {
        v12 = v10;
        v13 = 0;
        v14 = *(_QWORD *)(a2 + 24LL * v10 + 16);
        do
        {
          v15 = (unsigned int)v13;
          v16 = *(_QWORD *)(a2 + 24 * v13 + 16);
          if ( v14 <= v16 )
            v15 = v12;
          v13 = (unsigned int)(v13 + 1);
          v12 = v15;
          if ( v14 <= v16 )
            v16 = v14;
          v14 = v16;
        }
        while ( (unsigned int)v13 < a3 );
        v17 = 3 * v15;
        v18 = RegDeleteKeyExW(*(HKEY *)(a1 + 728), *(LPCWSTR *)(a2 + 24 * v15), 0, 0);
        ++v10;
        *(_QWORD *)(a2 + 8 * v17 + 16) = 0x7FFFFFFFFFFFFFFFLL;
        v5 = v18;
      }
      while ( v10 < v11 );
    }
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_d(1028, 86, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v11);
  }
  return v5;
}

```

## disassembly

```asm
0x18001a9e4  mov     [rsp+arg_0], rcx
0x18001a9e9  push    rbx
0x18001a9ea  push    rbp
0x18001a9eb  push    rsi
0x18001a9ec  push    rdi
0x18001a9ed  push    r12
0x18001a9ef  push    r13
0x18001a9f1  push    r14
0x18001a9f3  push    r15
0x18001a9f5  sub     rsp, 28h
0x18001a9f9  mov     r14d, r8d
0x18001a9fc  mov     rsi, rdx
0x18001a9ff  test    r8d, r8d
0x18001aa02  jz      loc_18001AB97
0x18001aa08  test    rdx, rdx
0x18001aa0b  jz      loc_18001AB97
0x18001aa11  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18001aa18  jz      short loc_18001AA2A
0x18001aa1a  mov     r8d, [rcx+30h]
0x18001aa1e  lea     rdx, CacheScavengerRun
0x18001aa25  call    McTemplateU0q_EtwEventWriteTransfer
0x18001aa2a  mov     edi, 8
0x18001aa2f  cmp     r14d, edi
0x18001aa32  jb      loc_18001AB97
0x18001aa38  mov     rdi, [rsp+68h+arg_0]
0x18001aa3d  xor     ebp, ebp
0x18001aa3f  xor     ebx, ebx
0x18001aa41  xor     r15d, r15d
0x18001aa44  xor     r12d, r12d
0x18001aa47  call    cs:__imp_GetTickCount64
0x18001aa4d  mov     rcx, rax
0x18001aa50  lea     r13, [r12+r12*2]
0x18001aa54  mov     rax, 624DD2F1A9FBE77h
0x18001aa5e  mul     rcx
0x18001aa61  sub     rcx, rdx
0x18001aa64  shr     rcx, 1
0x18001aa67  add     rcx, rdx
0x18001aa6a  shr     rcx, 9
0x18001aa6e  cmp     rcx, [rsi+r13*8+8]
0x18001aa73  jbe     short loc_18001AA9F
0x18001aa75  mov     rdx, [rsi+r13*8]; lpSubKey
0x18001aa79  xor     r9d, r9d; Reserved
0x18001aa7c  mov     rcx, [rdi+2D8h]; hKey
0x18001aa83  xor     r8d, r8d; samDesired
0x18001aa86  call    cs:__imp_RegDeleteKeyExW
0x18001aa8c  mov     ebp, eax
0x18001aa8e  inc     ebx
0x18001aa90  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001aa9a  mov     [rsi+r13*8+10h], rax
0x18001aa9f  inc     r15d
0x18001aaa2  inc     r12
0x18001aaa5  cmp     r15d, r14d
0x18001aaa8  jb      short loc_18001AA47
0x18001aaaa  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001aab1  mov     r12d, 404h
0x18001aab7  mov     edi, 8
0x18001aabc  jz      short loc_18001AAD3
0x18001aabe  lea     edx, [rdi+4Dh]
0x18001aac1  mov     ecx, r12d
0x18001aac4  mov     r9d, ebx
0x18001aac7  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18001aace  call    WPP_SF_d
0x18001aad3  cmp     r14d, 80h
0x18001aada  jb      loc_18001AB97
0x18001aae0  cmp     ebx, edi
0x18001aae2  jb      short loc_18001AAEB
0x18001aae4  mov     eax, ebp
0x18001aae6  jmp     loc_18001AB99
0x18001aaeb  mov     r15d, 0
0x18001aaf1  sub     edi, ebx
0x18001aaf3  jz      short loc_18001AB6E
0x18001aaf5  mov     r12, 7FFFFFFFFFFFFFFFh
0x18001aaff  mov     eax, r15d
0x18001ab02  mov     r10d, r15d
0x18001ab05  xor     r8d, r8d
0x18001ab08  lea     rcx, [rax+rax*2]
0x18001ab0c  mov     r9, [rsi+rcx*8+10h]
0x18001ab11  lea     rcx, [r8+r8*2]
0x18001ab15  mov     eax, r8d
0x18001ab18  mov     rdx, [rsi+rcx*8+10h]
0x18001ab1d  cmp     r9, rdx
0x18001ab20  cmovbe  eax, r10d
0x18001ab24  inc     r8d
0x18001ab27  cmp     r9, rdx
0x18001ab2a  mov     r10d, eax
0x18001ab2d  cmovbe  rdx, r9
0x18001ab31  mov     r9, rdx
0x18001ab34  cmp     r8d, r14d
0x18001ab37  jb      short loc_18001AB11
0x18001ab39  lea     rbx, [rax+rax*2]
0x18001ab3d  xor     r9d, r9d; Reserved
0x18001ab40  mov     rax, [rsp+68h+arg_0]
0x18001ab45  xor     r8d, r8d; samDesired
0x18001ab48  mov     rdx, [rsi+rbx*8]; lpSubKey
0x18001ab4c  mov     rcx, [rax+2D8h]; hKey
0x18001ab53  call    cs:__imp_RegDeleteKeyExW
0x18001ab59  inc     r15d
0x18001ab5c  mov     [rsi+rbx*8+10h], r12
0x18001ab61  mov     ebp, eax
0x18001ab63  cmp     r15d, edi
0x18001ab66  jb      short loc_18001AAFF
0x18001ab68  mov     r12d, 404h
0x18001ab6e  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001ab75  jz      loc_18001AAE4
0x18001ab7b  mov     edx, 56h ; 'V'
0x18001ab80  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18001ab87  mov     ecx, r12d
0x18001ab8a  mov     r9d, edi
0x18001ab8d  call    WPP_SF_d
0x18001ab92  jmp     loc_18001AAE4
0x18001ab97  xor     eax, eax
0x18001ab99  add     rsp, 28h
0x18001ab9d  pop     r15
0x18001ab9f  pop     r14
0x18001aba1  pop     r13
0x18001aba3  pop     r12
0x18001aba5  pop     rdi
0x18001aba6  pop     rsi
0x18001aba7  pop     rbp
0x18001aba8  pop     rbx
0x18001aba9  retn
```
