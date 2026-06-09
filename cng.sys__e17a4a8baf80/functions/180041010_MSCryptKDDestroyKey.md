# MSCryptKDDestroyKey

- ea: `0x180041010`
- end: `0x180041249`
- name: `MSCryptKDDestroyKey`
- size: `569`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f790`
- `0x18007e2f0`

## callees

- `0x1800123d0`
- `0x180041010`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180041061`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800410cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180041061`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800410cf`
- `ntoskrnl!SkIsSecureKernel` at `0x18004120f`
- `ntoskrnl!SkIsSecureKernel` at `0x18004122c`
- `ntoskrnl!SkIsSecureKernel` at `0x18004120f`
- `ntoskrnl!SkIsSecureKernel` at `0x18004122c`
- `ntoskrnl!SkFreePool` at `0x1800411b4`
- `ntoskrnl!SkFreePool` at `0x1800411cd`
- `ntoskrnl!SkFreePool` at `0x1800411b4`
- `ntoskrnl!SkFreePool` at `0x1800411cd`

## string_xrefs

- `0x180041110`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18004117f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800411e2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDDestroyKey(__int64 a1, __int64 a2, int a3)
{
  void *v4; // rbx
  int v5; // eax
  _BYTE *v6; // rax
  __int64 v7; // rcx
  _BYTE *v8; // rax
  __int64 v9; // rcx
  int v10; // eax
  void *v11; // rbx
  int v13; // edx

  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 4) == 1297304409 )
    {
      v4 = *(void **)(a1 + 56);
      if ( v4 )
      {
        LOBYTE(v5) = g_TrustedEnvironment;
        if ( !g_TrustedEnvironment )
        {
          v5 = ((int)SkIsSecureKernel(a1, a2) >> 31) + 2;
          g_TrustedEnvironment = v5;
        }
        if ( (v5 & 2) != 0 )
          SkFreePool(512, v4);
        else
          ExFreePoolWithTag(v4, 0x62676E43u);
        *(_QWORD *)(a1 + 56) = 0;
        v6 = (_BYTE *)(a1 + 48);
        v7 = 592;
        do
        {
          *v6++ = 0;
          --v7;
        }
        while ( v7 );
      }
      v8 = *(_BYTE **)(a1 + 24);
      if ( v8 )
      {
        v9 = *(unsigned int *)(a1 + 16);
        if ( *(_DWORD *)(a1 + 16) )
        {
          do
          {
            *v8++ = 0;
            --v9;
          }
          while ( v9 );
        }
        LOBYTE(v10) = g_TrustedEnvironment;
        v11 = *(void **)(a1 + 24);
        if ( !g_TrustedEnvironment )
        {
          v10 = ((int)SkIsSecureKernel(v9, a2) >> 31) + 2;
          g_TrustedEnvironment = v10;
        }
        if ( (v10 & 2) != 0 )
          SkFreePool(512, v11);
        else
          ExFreePoolWithTag(v11, 0x62676E43u);
        *(_QWORD *)(a1 + 24) = 0;
      }
      return 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        84);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      a2,
      a3,
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      75);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v13 = *((_DWORD *)WPP_GLOBAL_Control + 11);
    if ( (v13 & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v13,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        15);
  }
  return 3221225480LL;
}

```

## disassembly

```asm
0x180041010  mov     [rsp+arg_8], rbx
0x180041015  push    rdi
0x180041016  sub     rsp, 40h
0x18004101a  mov     rdi, rcx
0x18004101d  test    rcx, rcx
0x180041020  jz      loc_180041161
0x180041026  cmp     dword ptr [rcx+4], 4D534B59h
0x18004102d  jnz     loc_1800410F2
0x180041033  mov     rbx, [rcx+38h]
0x180041037  mov     [rsp+48h+arg_0], rsi
0x18004103c  xor     esi, esi
0x18004103e  test    rbx, rbx
0x180041041  jz      short loc_18004108D
0x180041043  mov     eax, cs:g_TrustedEnvironment
0x180041049  test    eax, eax
0x18004104b  jz      loc_18004120F
0x180041051  test    al, 2
0x180041053  jnz     loc_1800411AC
0x180041059  mov     edx, 62676E43h; Tag
0x18004105e  mov     rcx, rbx; P
0x180041061  call    cs:__imp_ExFreePoolWithTag
0x180041068  nop     dword ptr [rax+rax+00h]
0x18004106d  mov     [rdi+38h], rsi
0x180041071  lea     rax, [rdi+30h]
0x180041075  mov     ecx, 250h
0x18004107a  nop     word ptr [rax+rax+00h]
0x180041080  mov     [rax], sil
0x180041083  lea     rax, [rax+1]
0x180041087  sub     rcx, 1
0x18004108b  jnz     short loc_180041080
0x18004108d  mov     rax, [rdi+18h]
0x180041091  test    rax, rax
0x180041094  jz      short loc_1800410DF
0x180041096  mov     ecx, [rdi+10h]
0x180041099  test    rcx, rcx
0x18004109c  jz      short loc_1800410AD
0x18004109e  xchg    ax, ax
0x1800410a0  mov     [rax], sil
0x1800410a3  lea     rax, [rax+1]
0x1800410a7  sub     rcx, 1
0x1800410ab  jnz     short loc_1800410A0
0x1800410ad  mov     eax, cs:g_TrustedEnvironment
0x1800410b3  mov     rbx, [rdi+18h]
0x1800410b7  test    eax, eax
0x1800410b9  jz      loc_18004122C
0x1800410bf  test    al, 2
0x1800410c1  jnz     loc_1800411C5
0x1800410c7  mov     edx, 62676E43h; Tag
0x1800410cc  mov     rcx, rbx; P
0x1800410cf  call    cs:__imp_ExFreePoolWithTag
0x1800410d6  nop     dword ptr [rax+rax+00h]
0x1800410db  mov     [rdi+18h], rsi
0x1800410df  mov     eax, esi
0x1800410e1  mov     rsi, [rsp+48h+arg_0]
0x1800410e6  mov     rbx, [rsp+48h+arg_8]
0x1800410eb  add     rsp, 40h
0x1800410ef  pop     rdi
0x1800410f0  retn
0x1800410f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800410f9  lea     rbx, WPP_GLOBAL_Control
0x180041100  cmp     rcx, rbx
0x180041103  jz      short loc_180041110
0x180041105  mov     eax, [rcx+2Ch]
0x180041108  test    al, 1
0x18004110a  jnz     loc_1800411DE
0x180041110  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041117  mov     rcx, cs:WPP_GLOBAL_Control
0x18004111e  cmp     rcx, rbx
0x180041121  jz      short loc_180041150
0x180041123  mov     edx, [rcx+2Ch]
0x180041126  test    dl, 1
0x180041129  jz      short loc_180041150
0x18004112b  mov     rcx, [rcx+18h]
0x18004112f  lea     r9, aStatus; "Status"
0x180041136  mov     [rsp+48h+var_18], 60Fh
0x18004113e  mov     [rsp+48h+var_20], rdi
0x180041143  mov     [rsp+48h+var_28], 0C0000008h
0x18004114b  call    WPP_SF_sDsd
0x180041150  mov     rbx, [rsp+48h+arg_8]
0x180041155  mov     eax, 0C0000008h
0x18004115a  add     rsp, 40h
0x18004115e  pop     rdi
0x18004115f  retn
0x180041161  mov     rcx, cs:WPP_GLOBAL_Control
0x180041168  lea     rbx, WPP_GLOBAL_Control
0x18004116f  cmp     rcx, rbx
0x180041172  jz      short loc_180041110
0x180041174  mov     eax, [rcx+2Ch]
0x180041177  test    al, 1
0x180041179  jz      short loc_180041110
0x18004117b  mov     rcx, [rcx+18h]
0x18004117f  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180041186  mov     [rsp+48h+var_18], 14Bh
0x18004118e  lea     r9, aStatus; "Status"
0x180041195  mov     [rsp+48h+var_20], rdi
0x18004119a  mov     [rsp+48h+var_28], 0C0000008h
0x1800411a2  call    WPP_SF_sDsd
0x1800411a7  jmp     loc_180041117
0x1800411ac  mov     rdx, rbx
0x1800411af  mov     ecx, 200h
0x1800411b4  call    cs:__imp_SkFreePool
0x1800411bb  nop     dword ptr [rax+rax+00h]
0x1800411c0  jmp     loc_18004106D
0x1800411c5  mov     rdx, rbx
0x1800411c8  mov     ecx, 200h
0x1800411cd  call    cs:__imp_SkFreePool
0x1800411d4  nop     dword ptr [rax+rax+00h]
0x1800411d9  jmp     loc_1800410DB
0x1800411de  mov     rcx, [rcx+18h]
0x1800411e2  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800411e9  mov     [rsp+48h+var_18], 154h
0x1800411f1  lea     r9, aStatus; "Status"
0x1800411f8  mov     [rsp+48h+var_20], rdi
0x1800411fd  mov     [rsp+48h+var_28], 0C0000008h
0x180041205  call    WPP_SF_sDsd
0x18004120a  jmp     loc_180041117
0x18004120f  call    cs:__imp_SkIsSecureKernel
0x180041216  nop     dword ptr [rax+rax+00h]
0x18004121b  sar     eax, 1Fh
0x18004121e  add     eax, 2
0x180041221  mov     cs:g_TrustedEnvironment, eax
0x180041227  jmp     loc_180041051
0x18004122c  call    cs:__imp_SkIsSecureKernel
0x180041233  nop     dword ptr [rax+rax+00h]
0x180041238  sar     eax, 1Fh
0x18004123b  add     eax, 2
0x18004123e  mov     cs:g_TrustedEnvironment, eax
0x180041244  jmp     loc_1800410BF
```
