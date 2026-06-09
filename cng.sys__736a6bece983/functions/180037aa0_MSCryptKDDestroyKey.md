# MSCryptKDDestroyKey

- ea: `0x180037aa0`
- end: `0x180037cd9`
- name: `MSCryptKDDestroyKey`
- size: `569`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005670`
- `0x180074b50`

## callees

- `0x1800082b0`
- `0x180037aa0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180037af1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037b5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037af1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180037b5f`
- `ntoskrnl!SkIsSecureKernel` at `0x180037c9f`
- `ntoskrnl!SkIsSecureKernel` at `0x180037cbc`
- `ntoskrnl!SkIsSecureKernel` at `0x180037c9f`
- `ntoskrnl!SkIsSecureKernel` at `0x180037cbc`
- `ntoskrnl!SkFreePool` at `0x180037c44`
- `ntoskrnl!SkFreePool` at `0x180037c5d`
- `ntoskrnl!SkFreePool` at `0x180037c44`
- `ntoskrnl!SkFreePool` at `0x180037c5d`

## string_xrefs

- `0x180037ba0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180037c0f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180037c72`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
0x180037aa0  mov     [rsp+arg_8], rbx
0x180037aa5  push    rdi
0x180037aa6  sub     rsp, 40h
0x180037aaa  mov     rdi, rcx
0x180037aad  test    rcx, rcx
0x180037ab0  jz      loc_180037BF1
0x180037ab6  cmp     dword ptr [rcx+4], 4D534B59h
0x180037abd  jnz     loc_180037B82
0x180037ac3  mov     rbx, [rcx+38h]
0x180037ac7  mov     [rsp+48h+arg_0], rsi
0x180037acc  xor     esi, esi
0x180037ace  test    rbx, rbx
0x180037ad1  jz      short loc_180037B1D
0x180037ad3  mov     eax, cs:g_TrustedEnvironment
0x180037ad9  test    eax, eax
0x180037adb  jz      loc_180037C9F
0x180037ae1  test    al, 2
0x180037ae3  jnz     loc_180037C3C
0x180037ae9  mov     edx, 62676E43h; Tag
0x180037aee  mov     rcx, rbx; P
0x180037af1  call    cs:__imp_ExFreePoolWithTag
0x180037af8  nop     dword ptr [rax+rax+00h]
0x180037afd  mov     [rdi+38h], rsi
0x180037b01  lea     rax, [rdi+30h]
0x180037b05  mov     ecx, 250h
0x180037b0a  nop     word ptr [rax+rax+00h]
0x180037b10  mov     [rax], sil
0x180037b13  lea     rax, [rax+1]
0x180037b17  sub     rcx, 1
0x180037b1b  jnz     short loc_180037B10
0x180037b1d  mov     rax, [rdi+18h]
0x180037b21  test    rax, rax
0x180037b24  jz      short loc_180037B6F
0x180037b26  mov     ecx, [rdi+10h]
0x180037b29  test    rcx, rcx
0x180037b2c  jz      short loc_180037B3D
0x180037b2e  xchg    ax, ax
0x180037b30  mov     [rax], sil
0x180037b33  lea     rax, [rax+1]
0x180037b37  sub     rcx, 1
0x180037b3b  jnz     short loc_180037B30
0x180037b3d  mov     eax, cs:g_TrustedEnvironment
0x180037b43  mov     rbx, [rdi+18h]
0x180037b47  test    eax, eax
0x180037b49  jz      loc_180037CBC
0x180037b4f  test    al, 2
0x180037b51  jnz     loc_180037C55
0x180037b57  mov     edx, 62676E43h; Tag
0x180037b5c  mov     rcx, rbx; P
0x180037b5f  call    cs:__imp_ExFreePoolWithTag
0x180037b66  nop     dword ptr [rax+rax+00h]
0x180037b6b  mov     [rdi+18h], rsi
0x180037b6f  mov     eax, esi
0x180037b71  mov     rsi, [rsp+48h+arg_0]
0x180037b76  mov     rbx, [rsp+48h+arg_8]
0x180037b7b  add     rsp, 40h
0x180037b7f  pop     rdi
0x180037b80  retn
0x180037b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b89  lea     rbx, WPP_GLOBAL_Control
0x180037b90  cmp     rcx, rbx
0x180037b93  jz      short loc_180037BA0
0x180037b95  mov     eax, [rcx+2Ch]
0x180037b98  test    al, 1
0x180037b9a  jnz     loc_180037C6E
0x180037ba0  lea     rdi, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180037ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bae  cmp     rcx, rbx
0x180037bb1  jz      short loc_180037BE0
0x180037bb3  mov     edx, [rcx+2Ch]
0x180037bb6  test    dl, 1
0x180037bb9  jz      short loc_180037BE0
0x180037bbb  mov     rcx, [rcx+18h]
0x180037bbf  lea     r9, aStatus; "Status"
0x180037bc6  mov     [rsp+48h+var_18], 60Fh
0x180037bce  mov     [rsp+48h+var_20], rdi
0x180037bd3  mov     [rsp+48h+var_28], 0C0000008h
0x180037bdb  call    WPP_SF_sDsd
0x180037be0  mov     rbx, [rsp+48h+arg_8]
0x180037be5  mov     eax, 0C0000008h
0x180037bea  add     rsp, 40h
0x180037bee  pop     rdi
0x180037bef  retn
0x180037bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bf8  lea     rbx, WPP_GLOBAL_Control
0x180037bff  cmp     rcx, rbx
0x180037c02  jz      short loc_180037BA0
0x180037c04  mov     eax, [rcx+2Ch]
0x180037c07  test    al, 1
0x180037c09  jz      short loc_180037BA0
0x180037c0b  mov     rcx, [rcx+18h]
0x180037c0f  lea     rdi, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180037c16  mov     [rsp+48h+var_18], 14Bh
0x180037c1e  lea     r9, aStatus; "Status"
0x180037c25  mov     [rsp+48h+var_20], rdi
0x180037c2a  mov     [rsp+48h+var_28], 0C0000008h
0x180037c32  call    WPP_SF_sDsd
0x180037c37  jmp     loc_180037BA7
0x180037c3c  mov     rdx, rbx
0x180037c3f  mov     ecx, 200h
0x180037c44  call    cs:__imp_SkFreePool
0x180037c4b  nop     dword ptr [rax+rax+00h]
0x180037c50  jmp     loc_180037AFD
0x180037c55  mov     rdx, rbx
0x180037c58  mov     ecx, 200h
0x180037c5d  call    cs:__imp_SkFreePool
0x180037c64  nop     dword ptr [rax+rax+00h]
0x180037c69  jmp     loc_180037B6B
0x180037c6e  mov     rcx, [rcx+18h]
0x180037c72  lea     rdi, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180037c79  mov     [rsp+48h+var_18], 154h
0x180037c81  lea     r9, aStatus; "Status"
0x180037c88  mov     [rsp+48h+var_20], rdi
0x180037c8d  mov     [rsp+48h+var_28], 0C0000008h
0x180037c95  call    WPP_SF_sDsd
0x180037c9a  jmp     loc_180037BA7
0x180037c9f  call    cs:__imp_SkIsSecureKernel
0x180037ca6  nop     dword ptr [rax+rax+00h]
0x180037cab  sar     eax, 1Fh
0x180037cae  add     eax, 2
0x180037cb1  mov     cs:g_TrustedEnvironment, eax
0x180037cb7  jmp     loc_180037AE1
0x180037cbc  call    cs:__imp_SkIsSecureKernel
0x180037cc3  nop     dword ptr [rax+rax+00h]
0x180037cc8  sar     eax, 1Fh
0x180037ccb  add     eax, 2
0x180037cce  mov     cs:g_TrustedEnvironment, eax
0x180037cd4  jmp     loc_180037B4F
```
