# DhcpCacheScavanger

- ea: `0x180008084`
- end: `0x180008239`
- name: `DhcpCacheScavanger`
- size: `437`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800327f0`
- `0x1800368d0`

## callees

- `0x1800057f0`
- `0x1800079e4`
- `0x180008084`
- `0x18001a9e4`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008125`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800081d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008125`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800081d0`

## pseudocode

```c
__int64 __fastcall DhcpCacheScavanger(__int64 a1, int a2)
{
  unsigned int SavedConfigurations; // esi
  __int64 v5; // rdx
  __int64 v7; // [rsp+60h] [rbp+40h] BYREF

  v7 = 0;
  SavedConfigurations = DhcpReadSavedConfigurations(*(HKEY *)(a1 + 728));
  if ( SavedConfigurations )
  {
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      goto LABEL_17;
    v5 = 87;
    goto LABEL_4;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 88, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, 0);
  if ( !a2 && GetTickCount64() / 0x3E8 - *(_QWORD *)(a1 + 1896) > 0x15180 )
  {
    SavedConfigurations = DhcpReadSavedConfigurations(*(HKEY *)(a1 + 728));
    if ( SavedConfigurations )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        v5 = 89;
LABEL_4:
        WPP_SF_(1028, v5, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
      }
    }
    else
    {
      SavedConfigurations = ReplaceConfig(a1, v7, 0);
      if ( SavedConfigurations )
      {
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_(1028, 90, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
      }
      else
      {
        *(_QWORD *)(a1 + 1896) = GetTickCount64() / 0x3E8;
      }
    }
  }
LABEL_17:
  if ( v7 )
    DhcpPunycodeFree(&v7);
  return SavedConfigurations;
}

```

## disassembly

```asm
0x180008084  mov     [rsp-28h+arg_8], rbx
0x180008089  push    rbp
0x18000808a  push    rsi
0x18000808b  push    rdi
0x18000808c  push    r14
0x18000808e  push    r15
0x180008090  mov     rbp, rsp
0x180008093  sub     rsp, 20h
0x180008097  mov     r15d, edx
0x18000809a  mov     [rbp+arg_10], 0
0x1800080a2  mov     r14, rcx
0x1800080a5  mov     [rbp+arg_0], 0
0x1800080ac  mov     rcx, [rcx+2D8h]; hKey
0x1800080b3  lea     rdx, [rbp+arg_10]
0x1800080b7  lea     r8, [rbp+arg_0]
0x1800080bb  call    DhcpReadSavedConfigurations
0x1800080c0  mov     esi, eax
0x1800080c2  test    eax, eax
0x1800080c4  jz      short loc_1800080ED
0x1800080c6  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800080cd  jz      short loc_1800080E5
0x1800080cf  mov     edx, 57h ; 'W'
0x1800080d4  mov     ecx, 404h
0x1800080d9  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800080e0  call    WPP_SF_
0x1800080e5  mov     ebx, [rbp+arg_0]
0x1800080e8  jmp     loc_1800081F3
0x1800080ed  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800080f4  mov     edi, 404h
0x1800080f9  mov     ebx, [rbp+arg_0]
0x1800080fc  jz      short loc_180008114
0x1800080fe  mov     edx, 58h ; 'X'
0x180008103  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18000810a  mov     ecx, edi
0x18000810c  mov     r9d, ebx
0x18000810f  call    WPP_SF_d
0x180008114  test    r15d, r15d
0x180008117  jz      short loc_180008125
0x180008119  cmp     ebx, 80h
0x18000811f  jb      loc_1800081F3
0x180008125  call    cs:__imp_GetTickCount64
0x18000812b  mov     r15, 624DD2F1A9FBE77h
0x180008135  mov     rcx, rax
0x180008138  cmp     ebx, 80h
0x18000813e  jnb     short loc_180008167
0x180008140  mov     rax, r15
0x180008143  mul     rcx
0x180008146  sub     rcx, rdx
0x180008149  shr     rcx, 1
0x18000814c  add     rcx, rdx
0x18000814f  shr     rcx, 9
0x180008153  sub     rcx, [r14+768h]
0x18000815a  cmp     rcx, 15180h
0x180008161  jbe     loc_1800081F3
0x180008167  mov     rcx, [r14+2D8h]; hKey
0x18000816e  lea     r8, [rbp+arg_0]
0x180008172  lea     rdx, [rbp+arg_10]
0x180008176  call    DhcpReadSavedConfigurations
0x18000817b  mov     esi, eax
0x18000817d  test    eax, eax
0x18000817f  jz      short loc_18000819A
0x180008181  test    byte ptr cs:xmmword_1800616A0, 10h
0x180008188  jz      loc_1800080E5
0x18000818e  mov     edx, 59h ; 'Y'
0x180008193  mov     ecx, edi
0x180008195  jmp     loc_1800080D9
0x18000819a  mov     ebx, [rbp+arg_0]
0x18000819d  mov     rcx, r14
0x1800081a0  mov     rdx, [rbp+arg_10]
0x1800081a4  mov     r8d, ebx
0x1800081a7  call    ReplaceConfig
0x1800081ac  mov     esi, eax
0x1800081ae  test    eax, eax
0x1800081b0  jz      short loc_1800081D0
0x1800081b2  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800081b9  jz      short loc_1800081F3
0x1800081bb  mov     edx, 5Ah ; 'Z'
0x1800081c0  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800081c7  mov     ecx, edi
0x1800081c9  call    WPP_SF_
0x1800081ce  jmp     short loc_1800081F3
0x1800081d0  call    cs:__imp_GetTickCount64
0x1800081d6  mov     rcx, rax
0x1800081d9  mov     rax, r15
0x1800081dc  mul     rcx
0x1800081df  sub     rcx, rdx
0x1800081e2  shr     rcx, 1
0x1800081e5  add     rcx, rdx
0x1800081e8  shr     rcx, 9
0x1800081ec  mov     [r14+768h], rcx
0x1800081f3  cmp     [rbp+arg_10], 0
0x1800081f8  jz      short loc_180008226
0x1800081fa  xor     edi, edi
0x1800081fc  test    ebx, ebx
0x1800081fe  jz      short loc_18000821D
0x180008200  mov     rax, [rbp+arg_10]
0x180008204  lea     rcx, [rdi+rdi*2]
0x180008208  lea     rcx, [rax+rcx*8]
0x18000820c  cmp     qword ptr [rcx], 0
0x180008210  jz      short loc_180008217
0x180008212  call    DhcpPunycodeFree
0x180008217  inc     edi
0x180008219  cmp     edi, ebx
0x18000821b  jb      short loc_180008200
0x18000821d  lea     rcx, [rbp+arg_10]
0x180008221  call    DhcpPunycodeFree
0x180008226  mov     rbx, [rsp+20h+arg_8]
0x18000822b  mov     eax, esi
0x18000822d  add     rsp, 20h
0x180008231  pop     r15
0x180008233  pop     r14
0x180008235  pop     rdi
0x180008236  pop     rsi
0x180008237  pop     rbp
0x180008238  retn
```
