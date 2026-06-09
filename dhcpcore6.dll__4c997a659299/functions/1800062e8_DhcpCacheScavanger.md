# DhcpCacheScavanger

- ea: `0x1800062e8`
- end: `0x180006461`
- name: `DhcpCacheScavanger`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008a70`
- `0x180014590`
- `0x180016440`

## callees

- `0x1800062e8`
- `0x180006468`
- `0x18000c740`
- `0x180018ac0`
- `0x18001d62c`
- `0x180033900`
- `0x180033de4`

## pseudocode

```c
__int64 __fastcall DhcpCacheScavanger(__int64 a1, int a2)
{
  time_t *v4; // rcx
  unsigned int v5; // r14d
  __int64 v6; // rdx
  unsigned int v7; // ebx
  time_t v8; // rax
  time_t *v9; // rcx
  __int64 i; // rdi
  LPVOID *v11; // rcx
  DWORD v13; // [rsp+50h] [rbp+30h] BYREF
  char *v14; // [rsp+60h] [rbp+40h] BYREF

  v14 = 0;
  v13 = 0;
  v5 = Dhcpv6ReadSavedConfigurations(*(HKEY *)(a1 + 648), &v14, &v13);
  if ( v5 )
  {
    if ( (xmmword_1800423E0 & 0x10) == 0 )
    {
LABEL_5:
      v7 = v13;
      goto LABEL_19;
    }
    v6 = 86;
LABEL_4:
    WPP_SF_(1028, v6, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
    goto LABEL_5;
  }
  v7 = v13;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_d(1028, 87, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v13);
  if ( !a2 || v7 >= 0x80 )
  {
    v8 = time(v4);
    if ( v7 >= 0x80 || v8 - *(_QWORD *)(a1 + 9024) > 86400 )
    {
      v5 = Dhcpv6ReadSavedConfigurations(*(HKEY *)(a1 + 648), &v14, &v13);
      if ( v5 )
      {
        if ( (xmmword_1800423E0 & 0x10) == 0 )
          goto LABEL_5;
        v6 = 88;
        goto LABEL_4;
      }
      v7 = v13;
      v5 = ReplaceConfig(a1, (__int64)v14, v13);
      if ( v5 )
      {
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_(1028, 89, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      }
      else
      {
        *(_QWORD *)(a1 + 9024) = time(v9);
      }
    }
  }
LABEL_19:
  if ( v14 )
  {
    for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
    {
      v11 = (LPVOID *)&v14[24 * i];
      if ( *v11 )
        DhcpFree(v11);
    }
    DhcpFree((LPVOID *)&v14);
  }
  return v5;
}

```

## disassembly

```asm
0x1800062e8  mov     [rsp-28h+arg_8], rbx
0x1800062ed  push    rbp
0x1800062ee  push    rsi
0x1800062ef  push    rdi
0x1800062f0  push    r14
0x1800062f2  push    r15
0x1800062f4  mov     rbp, rsp
0x1800062f7  sub     rsp, 20h
0x1800062fb  mov     r15d, edx
0x1800062fe  mov     [rbp+arg_10], 0
0x180006306  mov     rsi, rcx
0x180006309  mov     [rbp+arg_0], 0
0x180006310  mov     rcx, [rcx+288h]; hKey
0x180006317  lea     rdx, [rbp+arg_10]
0x18000631b  lea     r8, [rbp+arg_0]
0x18000631f  call    Dhcpv6ReadSavedConfigurations
0x180006324  mov     r14d, eax
0x180006327  test    eax, eax
0x180006329  jz      short loc_180006352
0x18000632b  test    byte ptr cs:xmmword_1800423E0, 10h
0x180006332  jz      short loc_18000634A
0x180006334  mov     edx, 56h ; 'V'
0x180006339  mov     ecx, 404h
0x18000633e  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180006345  call    WPP_SF_
0x18000634a  mov     ebx, [rbp+arg_0]
0x18000634d  jmp     loc_180006419
0x180006352  test    byte ptr cs:xmmword_1800423E0, 10h
0x180006359  mov     edi, 404h
0x18000635e  mov     ebx, [rbp+arg_0]
0x180006361  jz      short loc_180006379
0x180006363  mov     edx, 57h ; 'W'
0x180006368  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000636f  mov     ecx, edi
0x180006371  mov     r9d, ebx
0x180006374  call    WPP_SF_d
0x180006379  test    r15d, r15d
0x18000637c  jz      short loc_18000638A
0x18000637e  cmp     ebx, 80h
0x180006384  jb      loc_180006419
0x18000638a  call    time
0x18000638f  cmp     ebx, 80h
0x180006395  jnb     short loc_1800063A6
0x180006397  sub     rax, [rsi+2340h]
0x18000639e  cmp     rax, 15180h
0x1800063a4  jle     short loc_180006419
0x1800063a6  mov     rcx, [rsi+288h]; hKey
0x1800063ad  lea     r8, [rbp+arg_0]
0x1800063b1  lea     rdx, [rbp+arg_10]
0x1800063b5  call    Dhcpv6ReadSavedConfigurations
0x1800063ba  mov     r14d, eax
0x1800063bd  test    eax, eax
0x1800063bf  jz      short loc_1800063D6
0x1800063c1  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800063c8  jz      short loc_18000634A
0x1800063ca  mov     edx, 58h ; 'X'
0x1800063cf  mov     ecx, edi
0x1800063d1  jmp     loc_18000633E
0x1800063d6  mov     ebx, [rbp+arg_0]
0x1800063d9  mov     rcx, rsi
0x1800063dc  mov     rdx, [rbp+arg_10]
0x1800063e0  mov     r8d, ebx
0x1800063e3  call    ReplaceConfig
0x1800063e8  mov     r14d, eax
0x1800063eb  test    eax, eax
0x1800063ed  jz      short loc_18000640D
0x1800063ef  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800063f6  jz      short loc_180006419
0x1800063f8  mov     edx, 59h ; 'Y'
0x1800063fd  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180006404  mov     ecx, edi
0x180006406  call    WPP_SF_
0x18000640b  jmp     short loc_180006419
0x18000640d  call    time
0x180006412  mov     [rsi+2340h], rax
0x180006419  cmp     [rbp+arg_10], 0
0x18000641e  jz      short loc_18000644C
0x180006420  xor     edi, edi
0x180006422  test    ebx, ebx
0x180006424  jz      short loc_180006443
0x180006426  mov     rax, [rbp+arg_10]
0x18000642a  lea     rcx, [rdi+rdi*2]
0x18000642e  lea     rcx, [rax+rcx*8]
0x180006432  cmp     qword ptr [rcx], 0
0x180006436  jz      short loc_18000643D
0x180006438  call    DhcpFree
0x18000643d  inc     edi
0x18000643f  cmp     edi, ebx
0x180006441  jb      short loc_180006426
0x180006443  lea     rcx, [rbp+arg_10]
0x180006447  call    DhcpFree
0x18000644c  mov     rbx, [rsp+20h+arg_8]
0x180006451  mov     eax, r14d
0x180006454  add     rsp, 20h
0x180006458  pop     r15
0x18000645a  pop     r14
0x18000645c  pop     rdi
0x18000645d  pop     rsi
0x18000645e  pop     rbp
0x18000645f  retn
```
