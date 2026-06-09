# DhcpRegisterOptions

- ea: `0x1800088d0`
- end: `0x180008a95`
- name: `DhcpRegisterOptions`
- size: `453`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002160`
- `0x1800048c0`
- `0x180005162`
- `0x1800088d0`
- `0x180008c50`
- `0x18000e5f8`
- `0x18000f704`
- `0x180010aac`
- `0x180011a1c`
- `0x180012850`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008932`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008932`

## pseudocode

```c
__int64 __fastcall DhcpRegisterOptions(__int64 a1, _BYTE *a2, int a3, char a4)
{
  LPWSTR CommandLineW; // rax
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  unsigned int v12; // ebx
  int v13; // ecx
  __int64 v14; // r8
  int v15; // r9d
  __int64 v16; // rbx
  _BYTE *v17; // rdx
  int i; // ecx
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v22; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h]
  _BYTE v24[48]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v25; // [rsp+A0h] [rbp-60h]
  int v26; // [rsp+A8h] [rbp-58h]
  _BYTE v27[256]; // [rsp+C0h] [rbp-40h] BYREF

  Src = 0;
  v22 = 0;
  v23 = 0;
  Size = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SqdqS(v10, v9, v11, a1, (char)a2, a3, a4, (__int64)CommandLineW);
  }
  *(_QWORD *)((char *)&v22 + 4) = 55;
  *(_QWORD *)&v23 = a2;
  DWORD2(v23) = a3;
  v12 = DhcpRegisterParameterChangeNotification(a1, 0, 0, (unsigned int)&v22, 1);
  if ( !v12 )
  {
    memset_0(v24, 0, 0x48u);
    if ( !(unsigned int)DhcpRegReadFromAnyLocation(v13, a1, (int)&Src, (int)&Size + 4, (LPDWORD)&Size)
      && HIDWORD(Size) == 3 )
    {
      v16 = (unsigned int)Size;
      if ( (_DWORD)Size )
      {
        if ( (unsigned int)Size >= 0x100 )
        {
LABEL_8:
          v12 = 87;
          goto LABEL_20;
        }
        memcpy_0(v27, Src, (unsigned int)Size);
        v14 = 0xFFFFFFFFLL;
        while ( a3 )
        {
          v17 = Src;
          for ( i = v16; i; --i )
          {
            if ( *a2 == *v17 )
              goto LABEL_17;
            ++v17;
          }
          if ( (unsigned int)v16 >= 0x100 )
            goto LABEL_8;
          v27[v16] = *a2;
          v16 = (unsigned int)(v16 + 1);
          LODWORD(Size) = v16;
LABEL_17:
          ++a2;
          --a3;
        }
        a2 = v27;
        a3 = v16;
      }
    }
    v25 = a2;
    v26 = a3;
    v12 = DhcpRegSaveOptionAtLocationExEx((__int64)v24, a1, v14, v15);
  }
LABEL_20:
  DhcpFree(&Src);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 109, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, v12);
  return v12;
}

```

## disassembly

```asm
0x1800088d0  push    rbp
0x1800088d2  push    rbx
0x1800088d3  push    rsi
0x1800088d4  push    rdi
0x1800088d5  push    r14
0x1800088d7  lea     rbp, [rsp-0D0h]
0x1800088df  sub     rsp, 1D0h
0x1800088e6  mov     rax, cs:__security_cookie
0x1800088ed  xor     rax, rsp
0x1800088f0  mov     [rbp+0F0h+var_30], rax
0x1800088f7  xorps   xmm0, xmm0
0x1800088fa  mov     [rsp+1F0h+Src], 0
0x180008903  movups  [rsp+1F0h+var_1A0], xmm0
0x180008908  mov     rbx, r9
0x18000890b  mov     esi, r8d
0x18000890e  movups  [rsp+1F0h+var_190], xmm0
0x180008913  mov     rdi, rdx
0x180008916  mov     dword ptr [rsp+1F0h+Size], 0
0x18000891e  mov     r14, rcx
0x180008921  mov     dword ptr [rsp+1F0h+Size+4], 0
0x180008929  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008930  jz      short loc_180008953
0x180008932  call    cs:__imp_GetCommandLineW
0x180008938  mov     [rsp+1F0h+var_1B8], rax
0x18000893d  mov     r9, r14
0x180008940  mov     [rsp+1F0h+var_1C0], rbx
0x180008945  mov     [rsp+1F0h+var_1C8], esi
0x180008949  mov     [rsp+1F0h+var_1D0], rdi
0x18000894e  call    WPP_SF_SqdqS
0x180008953  mov     [rsp+1F0h+var_1C0], rbx
0x180008958  lea     r9, [rsp+1F0h+var_1A0]
0x18000895d  xor     r8d, r8d
0x180008960  mov     dword ptr [rsp+1F0h+var_1D0], 1
0x180008968  xor     edx, edx
0x18000896a  mov     qword ptr [rsp+1F0h+var_1A0+4], 37h ; '7'
0x180008973  mov     rcx, r14
0x180008976  mov     qword ptr [rsp+1F0h+var_190], rdi
0x18000897b  mov     dword ptr [rsp+1F0h+var_190+8], esi
0x18000897f  call    DhcpRegisterParameterChangeNotification
0x180008984  mov     ebx, eax
0x180008986  test    eax, eax
0x180008988  jnz     loc_180008A46
0x18000898e  xor     edx, edx; Val
0x180008990  lea     r8d, [rax+48h]; Size
0x180008994  lea     rcx, [rsp+1F0h+var_180]; void *
0x180008999  call    memset_0
0x18000899e  lea     rax, [rsp+1F0h+Size]
0x1800089a3  mov     rdx, r14; int
0x1800089a6  lea     r9, [rsp+1F0h+Size+4]; int
0x1800089ab  mov     [rsp+1F0h+var_1D0], rax; LPDWORD
0x1800089b0  lea     r8, [rsp+1F0h+Src]; int
0x1800089b5  call    DhcpRegReadFromAnyLocation
0x1800089ba  test    eax, eax
0x1800089bc  jnz     short loc_180008A30
0x1800089be  cmp     dword ptr [rsp+1F0h+Size+4], 3
0x1800089c3  jnz     short loc_180008A30
0x1800089c5  mov     ebx, dword ptr [rsp+1F0h+Size]
0x1800089c9  test    ebx, ebx
0x1800089cb  jz      short loc_180008A30
0x1800089cd  cmp     ebx, 100h
0x1800089d3  jb      short loc_1800089DC
0x1800089d5  mov     ebx, 57h ; 'W'
0x1800089da  jmp     short loc_180008A46
0x1800089dc  mov     rdx, [rsp+1F0h+Src]; Src
0x1800089e1  lea     rcx, [rbp+0F0h+var_130]; void *
0x1800089e5  mov     r8, rbx; Size
0x1800089e8  call    memcpy_0
0x1800089ed  or      r8d, 0FFFFFFFFh
0x1800089f1  test    esi, esi
0x1800089f3  jz      short loc_180008A2A
0x1800089f5  mov     rdx, [rsp+1F0h+Src]
0x1800089fa  mov     ecx, ebx
0x1800089fc  test    ecx, ecx
0x1800089fe  jz      short loc_180008A0E
0x180008a00  mov     al, [rdx]
0x180008a02  cmp     [rdi], al
0x180008a04  jz      short loc_180008A22
0x180008a06  inc     rdx
0x180008a09  add     ecx, r8d
0x180008a0c  jmp     short loc_1800089FC
0x180008a0e  cmp     ebx, 100h
0x180008a14  jnb     short loc_1800089D5
0x180008a16  mov     al, [rdi]
0x180008a18  mov     [rbp+rbx+0F0h+var_130], al
0x180008a1c  inc     ebx
0x180008a1e  mov     dword ptr [rsp+1F0h+Size], ebx
0x180008a22  inc     rdi
0x180008a25  add     esi, r8d
0x180008a28  jmp     short loc_1800089F1
0x180008a2a  lea     rdi, [rbp+0F0h+var_130]
0x180008a2e  mov     esi, ebx
0x180008a30  mov     rdx, r14
0x180008a33  mov     [rbp+0F0h+var_150], rdi
0x180008a37  lea     rcx, [rsp+1F0h+var_180]
0x180008a3c  mov     [rbp+0F0h+var_148], esi
0x180008a3f  call    DhcpRegSaveOptionAtLocationExEx
0x180008a44  mov     ebx, eax
0x180008a46  lea     rcx, [rsp+1F0h+Src]
0x180008a4b  call    DhcpFree
0x180008a50  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008a57  jz      short loc_180008A76
0x180008a59  mov     edx, 6Dh ; 'm'
0x180008a5e  mov     dword ptr [rsp+1F0h+var_1D0], ebx
0x180008a62  mov     ecx, 404h
0x180008a67  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008a6e  mov     r9, r14
0x180008a71  call    WPP_SF_SD
0x180008a76  mov     eax, ebx
0x180008a78  mov     rcx, [rbp+0F0h+var_30]
0x180008a7f  xor     rcx, rsp; StackCookie
0x180008a82  call    __security_check_cookie
0x180008a87  add     rsp, 1D0h
0x180008a8e  pop     r14
0x180008a90  pop     rdi
0x180008a91  pop     rsi
0x180008a92  pop     rbx
0x180008a93  pop     rbp
0x180008a94  retn
```
