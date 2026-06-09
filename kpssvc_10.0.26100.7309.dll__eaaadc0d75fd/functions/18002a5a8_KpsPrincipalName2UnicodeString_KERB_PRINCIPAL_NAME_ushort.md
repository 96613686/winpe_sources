# KpsPrincipalName2UnicodeString(KERB_PRINCIPAL_NAME *,ushort * *)

- ea: `0x18002a5a8`
- end: `0x18002a82f`
- name: `?KpsPrincipalName2UnicodeString@@YAKPEAUKERB_PRINCIPAL_NAME@@PEAPEAG@Z`
- size: `647`
- prototype: `__int64 __fastcall(struct KERB_PRINCIPAL_NAME *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180027af8`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x180026a08`
- `0x18002a5a8`
- `0x18002b24c`
- `0x1800300f4`
- `0x18003012c`
- `0x180031002`

## string_xrefs

- `0x18002a761`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`
- `0x18002a7ba`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsPrincipalName2UnicodeString(struct KERB_PRINCIPAL_NAME *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  unsigned int v4; // ebx
  CHAR *v5; // r15
  unsigned int v6; // esi
  _BYTE *v8; // rcx
  _QWORD *i; // rax
  __int64 v10; // rdx
  unsigned int v11; // r8d
  unsigned __int64 v12; // rax
  CHAR *v13; // rax
  int v14; // edx
  _QWORD *v15; // rsi
  CHAR *v16; // r14
  _BYTE *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rbx
  char *v20; // rdx
  int v22; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v23; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  v4 = 0;
  v23 = 0;
  v5 = 0;
  v6 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    *a2 = 0;
    goto LABEL_39;
  }
  for ( i = (_QWORD *)*((_QWORD *)a1 + 1); ; i = (_QWORD *)*i )
  {
    if ( !i )
    {
      v12 = 2LL * v6;
      if ( v12 > 0xFFFFFFFF )
      {
        v4 = -1073741675;
        if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v8[28] & 1) != 0 )
        {
          v14 = 86;
          v22 = 1548;
          goto LABEL_38;
        }
        goto LABEL_39;
      }
      v13 = (CHAR *)KpsAllocMem((unsigned int)v12);
      v5 = v13;
      if ( v13 )
      {
        v15 = (_QWORD *)*((_QWORD *)a1 + 1);
        v16 = v13;
        while ( v15 )
        {
          v17 = (_BYTE *)v15[1];
          v18 = -1;
          do
            ++v18;
          while ( v17[v18] );
          v19 = (unsigned int)v18;
          memcpy_0(v16, v17, (unsigned int)v18);
          v20 = &v16[v19];
          v16 += v19 + 1;
          *v20 = *v15 != 0 ? 0x2F : 0;
          v15 = (_QWORD *)*v15;
        }
        v4 = KpsUtf8String2UnicodeString(v5, &v23);
        if ( v4 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Dsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              88,
              (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
              v4,
              (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
              1596);
          v2 = v23;
        }
        else
        {
          *a2 = v23;
        }
        goto LABEL_39;
      }
      v4 = 8;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v14 = 87;
      v22 = 1557;
LABEL_38:
      WPP_SF_Dsd(
        *((_QWORD *)v8 + 2),
        v14,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        v4,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        v22);
      goto LABEL_39;
    }
    v10 = -1;
    do
      ++v10;
    while ( *(_BYTE *)(i[1] + v10) );
    v11 = v10 + v6;
    if ( (unsigned int)v10 + v6 < v6 )
      break;
    v6 = v11 + 1;
    if ( v11 + 1 < v11 )
    {
      v4 = -1073741675;
      if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || (v8[28] & 1) == 0 )
        goto LABEL_39;
      v14 = 85;
      v22 = 1535;
      goto LABEL_38;
    }
  }
  v4 = -1073741675;
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v8[28] & 1) != 0 )
  {
    v14 = 84;
    v22 = 1523;
    goto LABEL_38;
  }
LABEL_39:
  KpsFreeMem(v2);
  KpsFreeMem(v5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18002a5a8  mov     rax, rsp
0x18002a5ab  mov     [rax+10h], rbx
0x18002a5af  mov     [rax+18h], rbp
0x18002a5b3  mov     [rax+20h], rsi
0x18002a5b7  push    rdi
0x18002a5b8  push    r12
0x18002a5ba  push    r13
0x18002a5bc  push    r14
0x18002a5be  push    r15
0x18002a5c0  sub     rsp, 30h
0x18002a5c4  xor     edi, edi
0x18002a5c6  mov     r12, rdx
0x18002a5c9  mov     ebx, edi
0x18002a5cb  mov     [rax+8], rdi
0x18002a5cf  mov     r15d, edi
0x18002a5d2  mov     esi, edi
0x18002a5d4  mov     rbp, rcx
0x18002a5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5de  lea     r13, WPP_GLOBAL_Control
0x18002a5e5  cmp     rcx, r13
0x18002a5e8  jz      short loc_18002A60A
0x18002a5ea  test    byte ptr [rcx+1Ch], 20h
0x18002a5ee  jz      short loc_18002A60A
0x18002a5f0  mov     rcx, [rcx+10h]
0x18002a5f4  lea     edx, [rdi+53h]
0x18002a5f7  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a5fe  call    WPP_SF_
0x18002a603  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a60a  test    rbp, rbp
0x18002a60d  jnz     short loc_18002A618
0x18002a60f  mov     [r12], rdi
0x18002a613  jmp     loc_18002A7D5
0x18002a618  mov     rax, [rbp+8]
0x18002a61c  jmp     short loc_18002A648
0x18002a61e  mov     r8, [rax+8]
0x18002a622  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a626  inc     rdx
0x18002a629  cmp     [r8+rdx], dil
0x18002a62d  jnz     short loc_18002A626
0x18002a62f  lea     r8d, [rdx+rsi]
0x18002a633  cmp     r8d, esi
0x18002a636  jb      loc_18002A6CA
0x18002a63c  lea     esi, [r8+1]
0x18002a640  cmp     esi, r8d
0x18002a643  jb      short loc_18002A6A0
0x18002a645  mov     rax, [rax]
0x18002a648  test    rax, rax
0x18002a64b  jnz     short loc_18002A61E
0x18002a64d  mov     eax, esi
0x18002a64f  mov     edx, 0FFFFFFFFh
0x18002a654  add     rax, rax
0x18002a657  cmp     rax, rdx
0x18002a65a  ja      loc_18002A799
0x18002a660  mov     ecx, eax; unsigned __int64
0x18002a662  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x18002a667  mov     r15, rax
0x18002a66a  test    rax, rax
0x18002a66d  jnz     loc_18002A6F4
0x18002a673  lea     ebx, [rax+8]
0x18002a676  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a67d  cmp     rcx, r13
0x18002a680  jz      loc_18002A7D5
0x18002a686  test    byte ptr [rcx+1Ch], 1
0x18002a68a  jz      loc_18002A7D5
0x18002a690  lea     edx, [rax+57h]
0x18002a693  mov     [rsp+58h+var_30], 615h
0x18002a69b  jmp     loc_18002A7B6
0x18002a6a0  mov     ebx, 0C0000095h
0x18002a6a5  cmp     rcx, r13
0x18002a6a8  jz      loc_18002A7D5
0x18002a6ae  test    byte ptr [rcx+1Ch], 1
0x18002a6b2  jz      loc_18002A7D5
0x18002a6b8  mov     edx, 55h ; 'U'
0x18002a6bd  mov     [rsp+58h+var_30], 5FFh
0x18002a6c5  jmp     loc_18002A7B6
0x18002a6ca  mov     ebx, 0C0000095h
0x18002a6cf  cmp     rcx, r13
0x18002a6d2  jz      loc_18002A7D5
0x18002a6d8  test    byte ptr [rcx+1Ch], 1
0x18002a6dc  jz      loc_18002A7D5
0x18002a6e2  mov     edx, 54h ; 'T'
0x18002a6e7  mov     [rsp+58h+var_30], 5F3h
0x18002a6ef  jmp     loc_18002A7B6
0x18002a6f4  mov     rsi, [rbp+8]
0x18002a6f8  mov     r14, r15
0x18002a6fb  jmp     short loc_18002A733
0x18002a6fd  mov     rdx, [rsi+8]; Src
0x18002a701  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a705  inc     rax
0x18002a708  cmp     [rdx+rax], dil
0x18002a70c  jnz     short loc_18002A705
0x18002a70e  mov     r8d, eax; Size
0x18002a711  mov     rcx, r14; void *
0x18002a714  mov     ebx, eax
0x18002a716  call    memcpy_0
0x18002a71b  mov     rax, [rsi]
0x18002a71e  lea     rdx, [rbx+r14]
0x18002a722  neg     rax
0x18002a725  lea     r14, [rdx+1]
0x18002a729  sbb     cl, cl
0x18002a72b  and     cl, 2Fh
0x18002a72e  mov     [rdx], cl
0x18002a730  mov     rsi, [rsi]
0x18002a733  test    rsi, rsi
0x18002a736  jnz     short loc_18002A6FD
0x18002a738  lea     rdx, [rsp+58h+arg_0]; unsigned __int16 **
0x18002a73d  mov     rcx, r15; lpMultiByteStr
0x18002a740  call    ?KpsUtf8String2UnicodeString@@YAKPEADPEAPEAG@Z; KpsUtf8String2UnicodeString(char *,ushort * *)
0x18002a745  mov     ebx, eax
0x18002a747  test    eax, eax
0x18002a749  jz      short loc_18002A78E
0x18002a74b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a752  cmp     rcx, r13
0x18002a755  jz      short loc_18002A787
0x18002a757  test    byte ptr [rcx+1Ch], 1
0x18002a75b  jz      short loc_18002A787
0x18002a75d  mov     rcx, [rcx+10h]
0x18002a761  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002a768  lea     edx, [rsi+58h]
0x18002a76b  mov     [rsp+58h+var_30], 63Ch
0x18002a773  mov     r9d, ebx
0x18002a776  mov     [rsp+58h+var_38], rax
0x18002a77b  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a782  call    WPP_SF_Dsd
0x18002a787  mov     rdi, [rsp+58h+arg_0]
0x18002a78c  jmp     short loc_18002A7D5
0x18002a78e  mov     rax, [rsp+58h+arg_0]
0x18002a793  mov     [r12], rax
0x18002a797  jmp     short loc_18002A7D5
0x18002a799  mov     ebx, 0C0000095h
0x18002a79e  cmp     rcx, r13
0x18002a7a1  jz      short loc_18002A7D5
0x18002a7a3  test    byte ptr [rcx+1Ch], 1
0x18002a7a7  jz      short loc_18002A7D5
0x18002a7a9  mov     edx, 56h ; 'V'
0x18002a7ae  mov     [rsp+58h+var_30], 60Ch
0x18002a7b6  mov     rcx, [rcx+10h]
0x18002a7ba  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002a7c1  mov     r9d, ebx
0x18002a7c4  mov     [rsp+58h+var_38], rax
0x18002a7c9  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a7d0  call    WPP_SF_Dsd
0x18002a7d5  mov     rcx, rdi; lpMem
0x18002a7d8  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002a7dd  mov     rcx, r15; lpMem
0x18002a7e0  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002a7e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7ec  cmp     rcx, r13
0x18002a7ef  jz      short loc_18002A80F
0x18002a7f1  test    byte ptr [rcx+1Ch], 20h
0x18002a7f5  jz      short loc_18002A80F
0x18002a7f7  mov     rcx, [rcx+10h]
0x18002a7fb  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002a802  mov     edx, 59h ; 'Y'
0x18002a807  mov     r9d, ebx
0x18002a80a  call    WPP_SF_D
0x18002a80f  mov     rbp, [rsp+58h+arg_10]
0x18002a814  mov     eax, ebx
0x18002a816  mov     rbx, [rsp+58h+arg_8]
0x18002a81b  mov     rsi, [rsp+58h+arg_18]
0x18002a820  add     rsp, 30h
0x18002a824  pop     r15
0x18002a826  pop     r14
0x18002a828  pop     r13
0x18002a82a  pop     r12
0x18002a82c  pop     rdi
0x18002a82d  retn
```
