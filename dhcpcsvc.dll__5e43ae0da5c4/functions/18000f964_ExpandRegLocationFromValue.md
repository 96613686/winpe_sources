# ExpandRegLocationFromValue

- ea: `0x18000f964`
- end: `0x18000faa6`
- name: `ExpandRegLocationFromValue`
- size: `322`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000fc0c`

## callees

- `0x180002160`
- `0x18000f528`
- `0x18000f7d4`
- `0x18000f964`
- `0x180011298`
- `0x1800126dc`
- `0x180012850`
- `0x180012a00`

## string_xrefs

- `0x18000fa4d`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpClassIdBin`

## pseudocode

```c
__int64 __fastcall ExpandRegLocationFromValue(const wchar_t *Src, __int64 a2, void *a3, char **a4)
{
  int v7; // eax
  const wchar_t *v8; // rcx
  unsigned int v9; // ebx
  DWORD v11; // [rsp+30h] [rbp-18h] BYREF
  void *Srca[2]; // [rsp+38h] [rbp-10h] BYREF
  DWORD v13; // [rsp+58h] [rbp+10h] BYREF
  int v14; // [rsp+5Ch] [rbp+14h]

  v14 = HIDWORD(a2);
  Srca[0] = 0;
  v11 = 0;
  v13 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SSS((_DWORD)Src, a2, (_DWORD)a3, (_DWORD)a3, (__int64)Src);
  v7 = DhcpRegReadFromLocation(Src, a3, (BYTE **)Srca, &v13, &v11);
  if ( v7 )
  {
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_SD(1025, 29, (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids, (_DWORD)Src, v7);
LABEL_12:
    v8 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpClassIdBin";
    goto LABEL_14;
  }
  if ( v13 != 7 )
  {
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_l(1025, 30, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v13);
    goto LABEL_12;
  }
  if ( v11 < 2 )
  {
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 31, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v11);
    goto LABEL_12;
  }
  v8 = (const wchar_t *)Srca[0];
LABEL_14:
  v9 = DhcpRegExpandString(v8, a3, a4);
  DhcpFree(Srca);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 32, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000f964  mov     rax, rsp
0x18000f967  mov     [rax+8], rbx
0x18000f96b  mov     [rax+18h], rsi
0x18000f96f  mov     [rax+10h], rdx
0x18000f973  push    rdi
0x18000f974  sub     rsp, 40h
0x18000f978  mov     rsi, r9
0x18000f97b  mov     qword ptr [rax-10h], 0
0x18000f983  mov     rdi, r8
0x18000f986  mov     dword ptr [rax-18h], 0
0x18000f98d  mov     rbx, rcx
0x18000f990  mov     dword ptr [rax+10h], 0
0x18000f997  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f99e  jz      short loc_18000F9AC
0x18000f9a0  mov     r9, r8
0x18000f9a3  mov     [rax-28h], rcx
0x18000f9a7  call    WPP_SF_SSS
0x18000f9ac  lea     rax, [rsp+48h+var_18]
0x18000f9b1  mov     rdx, rdi
0x18000f9b4  lea     r9, [rsp+48h+arg_8]
0x18000f9b9  mov     [rsp+48h+var_28], rax; LPDWORD
0x18000f9be  lea     r8, [rsp+48h+Src]
0x18000f9c3  mov     rcx, rbx; Src
0x18000f9c6  call    DhcpRegReadFromLocation
0x18000f9cb  test    eax, eax
0x18000f9cd  jz      short loc_18000F9F7
0x18000f9cf  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000f9d6  jz      short loc_18000FA4D
0x18000f9d8  mov     edx, 1Dh
0x18000f9dd  mov     dword ptr [rsp+48h+var_28], eax
0x18000f9e1  mov     ecx, 401h
0x18000f9e6  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000f9ed  mov     r9, rbx
0x18000f9f0  call    WPP_SF_SD
0x18000f9f5  jmp     short loc_18000FA4D
0x18000f9f7  mov     r9d, [rsp+48h+arg_8]
0x18000f9fc  cmp     r9d, 7
0x18000fa00  jz      short loc_18000FA23
0x18000fa02  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000fa09  jz      short loc_18000FA4D
0x18000fa0b  mov     edx, 1Eh
0x18000fa10  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000fa17  mov     ecx, 401h
0x18000fa1c  call    WPP_SF_l
0x18000fa21  jmp     short loc_18000FA4D
0x18000fa23  mov     r9d, [rsp+48h+var_18]
0x18000fa28  cmp     r9d, 2
0x18000fa2c  jnb     short loc_18000FA56
0x18000fa2e  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000fa35  jz      short loc_18000FA4D
0x18000fa37  mov     edx, 1Fh
0x18000fa3c  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000fa43  mov     ecx, 401h
0x18000fa48  call    WPP_SF_d
0x18000fa4d  lea     rcx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Tc"...
0x18000fa54  jmp     short loc_18000FA5B
0x18000fa56  mov     rcx, [rsp+48h+Src]; Src
0x18000fa5b  mov     r8, rsi
0x18000fa5e  mov     rdx, rdi
0x18000fa61  call    DhcpRegExpandString
0x18000fa66  mov     ebx, eax
0x18000fa68  lea     rcx, [rsp+48h+Src]
0x18000fa6d  call    DhcpFree
0x18000fa72  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000fa79  jz      short loc_18000FA94
0x18000fa7b  mov     edx, 20h ; ' '
0x18000fa80  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000fa87  mov     ecx, 404h
0x18000fa8c  mov     r9d, ebx
0x18000fa8f  call    WPP_SF_d
0x18000fa94  mov     rsi, [rsp+48h+arg_10]
0x18000fa99  mov     eax, ebx
0x18000fa9b  mov     rbx, [rsp+48h+arg_0]
0x18000faa0  add     rsp, 40h
0x18000faa4  pop     rdi
0x18000faa5  retn
```
