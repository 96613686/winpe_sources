# DeserializeCurveNameList

- ea: `0x180014c1c`
- end: `0x180014d64`
- name: `DeserializeCurveNameList`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d100`

## callees

- `0x18000d02c`
- `0x180014c1c`
- `0x180014d6c`

## string_xrefs

- `0x180014ce7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180014d42`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
__int64 __fastcall DeserializeCurveNameList(unsigned __int8 *a1, int a2, __int64 a3, unsigned int a4, unsigned int *a5)
{
  __int64 v5; // r11
  __int64 v6; // rdi
  unsigned int v7; // edx
  wchar_t *v8; // r14
  unsigned int v9; // ebx
  const wchar_t *v10; // rbp
  unsigned int i; // esi
  __int64 v12; // rdx
  size_t v13; // r15
  int v14; // edx
  int v15; // r8d

  v5 = a3;
  if ( a1 )
  {
    v6 = *a1;
    v7 = a2 + 8 * v6 + 12;
    *a5 = v7;
    if ( a3 )
    {
      if ( a4 < v7 )
      {
        return (unsigned int)-2146893784;
      }
      else
      {
        *(_DWORD *)a3 = v6;
        *(_QWORD *)(a3 + 8) = a3 + 16;
        v8 = (wchar_t *)(a3 + 16 + 8 * v6);
        v9 = 0;
        v10 = (const wchar_t *)(a1 + 4);
        for ( i = 0; i < (unsigned int)v6; ++i )
        {
          v12 = -1;
          do
            ++v12;
          while ( v10[v12] );
          *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8LL * i) = v8;
          v13 = (unsigned int)(v12 + 1);
          if ( StringCchCopyW(v8, v13, v10) < 0 )
          {
            v9 = -1073741595;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v14,
                v15,
                (unsigned int)"Status",
                229,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
                27);
            return v9;
          }
          v10 += v13;
          v8 += v13;
        }
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v9 = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        246);
  }
  return v9;
}

```

## disassembly

```asm
0x180014c1c  push    rbx
0x180014c1e  push    rbp
0x180014c1f  push    rsi
0x180014c20  push    rdi
0x180014c21  push    r12
0x180014c23  push    r14
0x180014c25  push    r15
0x180014c27  sub     rsp, 40h
0x180014c2b  xor     r12d, r12d
0x180014c2e  mov     r11, r8
0x180014c31  test    rcx, rcx
0x180014c34  jz      loc_180014D1C
0x180014c3a  movzx   edi, byte ptr [rcx]
0x180014c3d  mov     rax, [rsp+78h+arg_20]
0x180014c45  lea     edx, [rdx+rdi*8]
0x180014c48  add     edx, 0Ch
0x180014c4b  mov     [rax], edx
0x180014c4d  test    r8, r8
0x180014c50  jz      loc_180014D58
0x180014c56  cmp     r9d, edx
0x180014c59  jb      loc_180014D5D
0x180014c5f  lea     rax, [r8+10h]
0x180014c63  mov     [r8], edi
0x180014c66  lea     r14, [r8+10h]
0x180014c6a  mov     [r8+8], rax
0x180014c6e  lea     r14, [r14+rdi*8]
0x180014c72  mov     ebx, r12d
0x180014c75  lea     rbp, [rcx+4]
0x180014c79  mov     esi, r12d
0x180014c7c  cmp     esi, edi
0x180014c7e  jnb     loc_180014D0B
0x180014c84  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014c88  inc     rdx
0x180014c8b  cmp     [rbp+rdx*2+0], r12w
0x180014c91  jnz     short loc_180014C88
0x180014c93  mov     rax, [r11+8]
0x180014c97  mov     r8, rbp; pszSrc
0x180014c9a  mov     ecx, esi
0x180014c9c  mov     [rax+rcx*8], r14
0x180014ca0  lea     eax, [rdx+1]
0x180014ca3  mov     edx, eax; cchDest
0x180014ca5  mov     rcx, r14; pszDest
0x180014ca8  mov     r15d, eax
0x180014cab  call    StringCchCopyW
0x180014cb0  test    eax, eax
0x180014cb2  js      short loc_180014CC1
0x180014cb4  lea     rbp, [rbp+r15*2+0]
0x180014cb9  inc     esi
0x180014cbb  lea     r14, [r14+r15*2]
0x180014cbf  jmp     short loc_180014C7C
0x180014cc1  mov     ebx, 0C00000E5h
0x180014cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ccd  lea     rax, WPP_GLOBAL_Control
0x180014cd4  cmp     rcx, rax
0x180014cd7  jz      short loc_180014D0B
0x180014cd9  test    byte ptr [rcx+1Ch], 1
0x180014cdd  jz      short loc_180014D0B
0x180014cdf  mov     [rsp+78h+var_48], 21Bh
0x180014ce7  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014cee  mov     [rsp+78h+var_50], rax
0x180014cf3  mov     [rsp+78h+var_58], 0C00000E5h
0x180014cfb  mov     rcx, [rcx+10h]
0x180014cff  lea     r9, aStatus; "Status"
0x180014d06  call    WPP_SF_sDsd
0x180014d0b  mov     eax, ebx
0x180014d0d  add     rsp, 40h
0x180014d11  pop     r15
0x180014d13  pop     r14
0x180014d15  pop     r12
0x180014d17  pop     rdi
0x180014d18  pop     rsi
0x180014d19  pop     rbp
0x180014d1a  pop     rbx
0x180014d1b  retn
0x180014d1c  mov     ebx, 80090027h
0x180014d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d28  lea     rax, WPP_GLOBAL_Control
0x180014d2f  cmp     rcx, rax
0x180014d32  jz      short loc_180014D0B
0x180014d34  test    byte ptr [rcx+1Ch], 1
0x180014d38  jz      short loc_180014D0B
0x180014d3a  mov     [rsp+78h+var_48], 1F6h
0x180014d42  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014d49  mov     [rsp+78h+var_50], rax
0x180014d4e  mov     [rsp+78h+var_58], 80090027h
0x180014d56  jmp     short loc_180014CFB
0x180014d58  mov     ebx, r12d
0x180014d5b  jmp     short loc_180014D0B
0x180014d5d  mov     ebx, 80090028h
0x180014d62  jmp     short loc_180014D0B
```
