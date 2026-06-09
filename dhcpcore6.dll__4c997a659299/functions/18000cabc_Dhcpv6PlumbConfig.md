# Dhcpv6PlumbConfig

- ea: `0x18000cabc`
- end: `0x18000ce2c`
- name: `Dhcpv6PlumbConfig`
- size: `880`
- prototype: `__int64 __fastcall(__int64, int, int *)`
- caller_count: `6`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180010088`
- `0x180011e04`
- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`

## callees

- `0x180007564`
- `0x18000c740`
- `0x18000cabc`
- `0x180010fd4`
- `0x18001225c`
- `0x180031694`
- `0x180031820`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033970`
- `0x1800347c8`
- `0x1800348c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cdea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cdea`

## pseudocode

```c
__int64 __fastcall Dhcpv6PlumbConfig(__int64 a1, int a2, int *a3)
{
  char *v3; // rsi
  _QWORD *v5; // rcx
  unsigned int v6; // edi
  _QWORD *v8; // rbx
  int v9; // r13d
  unsigned int v10; // r14d
  __int64 v11; // r8
  __int64 v12; // r15
  unsigned int v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rcx
  _QWORD *v25; // [rsp+30h] [rbp-58h]
  int v26; // [rsp+90h] [rbp+8h]
  int v28; // [rsp+A0h] [rbp+18h]
  __int64 v29; // [rsp+A8h] [rbp+20h] BYREF

  v3 = 0;
  v5 = (_QWORD *)(a1 + 104);
  v29 = 0;
  v6 = 0;
  v28 = 0;
  v8 = (_QWORD *)*v5;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_Sl((_DWORD)v5, 115, (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 56), a2);
    v5 = (_QWORD *)(a1 + 104);
  }
  if ( a3 )
    *a3 = 0;
  while ( v8 != v5 )
  {
    v9 = 0;
    v25 = (_QWORD *)*v8;
    v10 = 0;
    v26 = 0;
    while ( v10 < *((_DWORD *)v8 + 9) && v10 < 2 )
    {
      v11 = 7LL * v10;
      v12 = (__int64)&v8[v11 + 7];
      v13 = SetDhcpv6ConfigurationForNIC(a1, v12, LODWORD(v8[v11 + 9]), HIDWORD(v8[v11 + 9]));
      v6 = v13;
      if ( v13 )
      {
        if ( v13 == 4100 )
        {
          if ( (xmmword_1800423E0 & 2) != 0 )
            WPP_SF_D_IPV6_(v15, v14, v16, *((_DWORD *)v8 + 8), v12);
          if ( !v3 )
          {
            v29 = DhcpAlloc(168);
            v3 = (char *)v29;
            if ( !v29 )
            {
              v6 = 8;
              goto LABEL_47;
            }
            v6 = 0;
          }
          v9 = 1;
          *((_DWORD *)v3 + 8) = *((_DWORD *)v8 + 8);
          v17 = v10 + 1LL;
          *(_OWORD *)(v3 + 56) = *(_OWORD *)&v8[7 * v17];
          *(_OWORD *)(v3 + 72) = *(_OWORD *)&v8[7 * v17 + 2];
          *(_OWORD *)(v3 + 88) = *(_OWORD *)&v8[7 * v17 + 4];
          *((_QWORD *)v3 + 13) = v8[7 * v17 + 6];
          *((_DWORD *)v3 + 9) = 1;
        }
        else
        {
          if ( v13 == 5006 )
          {
            if ( (xmmword_1800423E0 & 2) != 0 )
              WPP_SF_S(1025, 118, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 56));
            goto LABEL_47;
          }
          if ( (xmmword_1800423E0 & 2) != 0 )
            WPP_SF__IPV6_SD(v15, v14, v16, v12, *(_QWORD *)(a1 + 56), v13);
        }
      }
      else
      {
        v26 = 1;
        v28 = 1;
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF__IPV6_S(1028, 116, *(_QWORD *)(a1 + 56), v12, *(_QWORD *)(a1 + 56));
      }
      ++v10;
    }
    if ( v9 )
    {
      if ( v26 )
      {
        if ( !v3 )
        {
          v6 = 5023;
          goto LABEL_49;
        }
        v22 = (_QWORD *)(a1 + 176);
        v23 = *(_QWORD *)(a1 + 176);
        if ( *(_QWORD *)(v23 + 8) != a1 + 176 )
          goto LABEL_36;
        *(_QWORD *)v3 = v23;
        v6 = 0;
        *((_QWORD *)v3 + 1) = v22;
        *(_QWORD *)(v23 + 8) = v3;
        *v22 = v3;
        v3 = 0;
        v29 = 0;
        *((_DWORD *)v8 + 9) = 1;
      }
      else
      {
        v18 = *v8;
        if ( *(_QWORD **)(*v8 + 8LL) != v8
          || (v19 = (_QWORD *)v8[1], (_QWORD *)*v19 != v8)
          || (*v19 = v18,
              *(_QWORD *)(v18 + 8) = v19,
              v20 = (_QWORD *)(a1 + 176),
              v21 = *(_QWORD *)(a1 + 176),
              *(_QWORD *)(v21 + 8) != a1 + 176) )
        {
LABEL_36:
          __fastfail(3u);
        }
        *v8 = v21;
        v8[1] = v20;
        *(_QWORD *)(v21 + 8) = v8;
        *v20 = v8;
        DhcpFree((LPVOID *)&v29);
        v3 = (char *)v29;
      }
    }
    v8 = v25;
    v5 = (_QWORD *)(a1 + 104);
  }
  if ( a2 )
    *(_DWORD *)(a1 + 8920) = ((unsigned int)Dhcpv6RegisterWithDns(a1, 0) != 0) + 2;
  if ( v28 && v6 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_SD(1025, 120, (unsigned int)WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *(_QWORD *)(a1 + 56), v6);
    v6 = 0;
  }
  if ( a3 )
    *a3 = v28;
LABEL_47:
  if ( v3 )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v3);
LABEL_49:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 121, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000cabc  mov     [rsp+arg_8], edx
0x18000cac0  mov     r11, rsp
0x18000cac3  push    rbx
0x18000cac4  push    rbp
0x18000cac5  push    rsi
0x18000cac6  push    rdi
0x18000cac7  push    r12
0x18000cac9  push    r13
0x18000cacb  push    r14
0x18000cacd  push    r15
0x18000cacf  sub     rsp, 48h
0x18000cad3  xor     esi, esi
0x18000cad5  mov     rbp, rcx
0x18000cad8  add     rcx, 68h ; 'h'
0x18000cadc  mov     [r11+20h], rsi
0x18000cae0  xor     edi, edi
0x18000cae2  mov     r12, r8
0x18000cae5  xor     r14d, r14d
0x18000cae8  mov     eax, edx
0x18000caea  mov     [rsp+88h+arg_10], r14d
0x18000caf2  mov     rbx, [rcx]
0x18000caf5  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000cafc  jz      short loc_18000CB19
0x18000cafe  mov     r9, [rbp+38h]
0x18000cb02  lea     edx, [rdi+73h]
0x18000cb05  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000cb0c  mov     dword ptr [rsp+88h+var_68], eax
0x18000cb10  call    WPP_SF_Sl
0x18000cb15  lea     rcx, [rbp+68h]
0x18000cb19  test    r12, r12
0x18000cb1c  jz      short loc_18000CB22
0x18000cb1e  mov     [r12], esi
0x18000cb22  cmp     rbx, rcx
0x18000cb25  jz      loc_18000CD6C
0x18000cb2b  mov     r15, [rbx]
0x18000cb2e  xor     r13d, r13d
0x18000cb31  mov     [rsp+88h+var_58], r15
0x18000cb36  xor     r14d, r14d
0x18000cb39  mov     [rsp+88h+arg_0], 0
0x18000cb44  cmp     r14d, [rbx+24h]
0x18000cb48  jnb     loc_18000CC77
0x18000cb4e  cmp     r14d, 2
0x18000cb52  jnb     loc_18000CC77
0x18000cb58  mov     eax, r14d
0x18000cb5b  mov     rcx, rbp
0x18000cb5e  imul    r8, rax, 38h ; '8'
0x18000cb62  mov     r9d, [r8+rbx+4Ch]
0x18000cb67  lea     r15, [r8+38h]
0x18000cb6b  mov     r8d, [r8+rbx+48h]
0x18000cb70  add     r15, rbx
0x18000cb73  mov     rdx, r15
0x18000cb76  call    SetDhcpv6ConfigurationForNIC
0x18000cb7b  mov     edi, eax
0x18000cb7d  test    eax, eax
0x18000cb7f  jnz     short loc_18000CBC2
0x18000cb81  mov     [rsp+88h+arg_0], 1
0x18000cb8c  mov     [rsp+88h+arg_10], 1
0x18000cb97  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000cb9e  jz      loc_18000CC6F
0x18000cba4  mov     r8, [rbp+38h]
0x18000cba8  lea     edx, [rax+74h]
0x18000cbab  mov     ecx, 404h
0x18000cbb0  mov     [rsp+88h+var_68], r8
0x18000cbb5  mov     r9, r15
0x18000cbb8  call    WPP_SF__IPV6_S
0x18000cbbd  jmp     loc_18000CC6F
0x18000cbc2  cmp     eax, 1004h
0x18000cbc7  jnz     short loc_18000CC46
0x18000cbc9  test    byte ptr cs:xmmword_1800423E0, 2
0x18000cbd0  jz      short loc_18000CBE0
0x18000cbd2  mov     r9d, [rbx+20h]
0x18000cbd6  mov     [rsp+88h+var_68], r15
0x18000cbdb  call    WPP_SF_D_IPV6_
0x18000cbe0  test    rsi, rsi
0x18000cbe3  jnz     short loc_18000CC05
0x18000cbe5  mov     ecx, 0A8h
0x18000cbea  call    DhcpAlloc
0x18000cbef  mov     [rsp+88h+arg_18], rax
0x18000cbf7  mov     rsi, rax
0x18000cbfa  test    rax, rax
0x18000cbfd  jz      loc_18000CD28
0x18000cc03  xor     edi, edi
0x18000cc05  mov     eax, [rbx+20h]
0x18000cc08  mov     r13d, 1
0x18000cc0e  mov     [rsi+20h], eax
0x18000cc11  mov     eax, r14d
0x18000cc14  inc     rax
0x18000cc17  imul    rcx, rax, 38h ; '8'
0x18000cc1b  movups  xmm0, xmmword ptr [rcx+rbx]
0x18000cc1f  movups  xmmword ptr [rsi+38h], xmm0
0x18000cc23  movups  xmm1, xmmword ptr [rcx+rbx+10h]
0x18000cc28  movups  xmmword ptr [rsi+48h], xmm1
0x18000cc2c  movups  xmm0, xmmword ptr [rcx+rbx+20h]
0x18000cc31  movups  xmmword ptr [rsi+58h], xmm0
0x18000cc35  movsd   xmm1, qword ptr [rcx+rbx+30h]
0x18000cc3b  movsd   qword ptr [rsi+68h], xmm1
0x18000cc40  mov     [rsi+24h], r13d
0x18000cc44  jmp     short loc_18000CC6F
0x18000cc46  cmp     eax, 138Eh
0x18000cc4b  jz      loc_18000CD32
0x18000cc51  test    byte ptr cs:xmmword_1800423E0, 2
0x18000cc58  jz      short loc_18000CC6F
0x18000cc5a  mov     [rsp+88h+var_60], eax
0x18000cc5e  mov     r9, r15
0x18000cc61  mov     rax, [rbp+38h]
0x18000cc65  mov     [rsp+88h+var_68], rax
0x18000cc6a  call    WPP_SF__IPV6_SD
0x18000cc6f  inc     r14d
0x18000cc72  jmp     loc_18000CB44
0x18000cc77  test    r13d, r13d
0x18000cc7a  jz      loc_18000CD1A
0x18000cc80  cmp     [rsp+88h+arg_0], 0
0x18000cc88  jnz     short loc_18000CCE4
0x18000cc8a  mov     rax, [rbx]
0x18000cc8d  cmp     [rax+8], rbx
0x18000cc91  jnz     loc_18000CD5B
0x18000cc97  mov     rcx, [rbx+8]
0x18000cc9b  cmp     [rcx], rbx
0x18000cc9e  jnz     loc_18000CD5B
0x18000cca4  mov     [rcx], rax
0x18000cca7  mov     [rax+8], rcx
0x18000ccab  lea     rax, [rbp+0B0h]
0x18000ccb2  mov     rcx, [rax]
0x18000ccb5  cmp     [rcx+8], rax
0x18000ccb9  jnz     loc_18000CD5B
0x18000ccbf  mov     [rbx], rcx
0x18000ccc2  mov     [rbx+8], rax
0x18000ccc6  mov     [rcx+8], rbx
0x18000ccca  lea     rcx, [rsp+88h+arg_18]
0x18000ccd2  mov     [rax], rbx
0x18000ccd5  call    DhcpFree
0x18000ccda  mov     rsi, [rsp+88h+arg_18]
0x18000cce2  jmp     short loc_18000CD1A
0x18000cce4  test    rsi, rsi
0x18000cce7  jz      short loc_18000CD62
0x18000cce9  lea     rax, [rbp+0B0h]
0x18000ccf0  mov     rcx, [rax]
0x18000ccf3  cmp     [rcx+8], rax
0x18000ccf7  jnz     short loc_18000CD5B
0x18000ccf9  mov     [rsi], rcx
0x18000ccfc  xor     edi, edi
0x18000ccfe  mov     [rsi+8], rax
0x18000cd02  mov     [rcx+8], rsi
0x18000cd06  mov     [rax], rsi
0x18000cd09  xor     esi, esi
0x18000cd0b  mov     [rsp+88h+arg_18], rsi
0x18000cd13  mov     dword ptr [rbx+24h], 1
0x18000cd1a  mov     rbx, [rsp+88h+var_58]
0x18000cd1f  lea     rcx, [rbp+68h]
0x18000cd23  jmp     loc_18000CB22
0x18000cd28  mov     edi, 8
0x18000cd2d  jmp     loc_18000CDD3
0x18000cd32  test    byte ptr cs:xmmword_1800423E0, 2
0x18000cd39  jz      loc_18000CDD3
0x18000cd3f  mov     r9, [rbp+38h]
0x18000cd43  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000cd4a  mov     edx, 76h ; 'v'
0x18000cd4f  mov     ecx, 401h
0x18000cd54  call    WPP_SF_S
0x18000cd59  jmp     short loc_18000CDD3
0x18000cd5b  mov     ecx, 3
0x18000cd60  int     29h; Win8: RtlFailFast(ecx)
0x18000cd62  mov     edi, 139Fh
0x18000cd67  jmp     loc_18000CDF6
0x18000cd6c  cmp     [rsp+88h+arg_8], 0
0x18000cd74  jz      short loc_18000CD90
0x18000cd76  xor     edx, edx
0x18000cd78  mov     rcx, rbp
0x18000cd7b  call    Dhcpv6RegisterWithDns
0x18000cd80  xor     ecx, ecx
0x18000cd82  test    eax, eax
0x18000cd84  setnz   cl
0x18000cd87  add     ecx, 2
0x18000cd8a  mov     [rbp+22D8h], ecx
0x18000cd90  mov     r14d, [rsp+88h+arg_10]
0x18000cd98  test    r14d, r14d
0x18000cd9b  jz      short loc_18000CDCA
0x18000cd9d  test    edi, edi
0x18000cd9f  jz      short loc_18000CDCA
0x18000cda1  test    byte ptr cs:xmmword_1800423E0, 2
0x18000cda8  jz      short loc_18000CDC8
0x18000cdaa  mov     r9, [rbp+38h]
0x18000cdae  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000cdb5  mov     edx, 78h ; 'x'
0x18000cdba  mov     dword ptr [rsp+88h+var_68], edi
0x18000cdbe  mov     ecx, 401h
0x18000cdc3  call    WPP_SF_SD
0x18000cdc8  xor     edi, edi
0x18000cdca  test    r12, r12
0x18000cdcd  jz      short loc_18000CDD3
0x18000cdcf  mov     [r12], r14d
0x18000cdd3  test    rsi, rsi
0x18000cdd6  jz      short loc_18000CDF6
0x18000cdd8  mov     rcx, gs:60h
0x18000cde1  mov     r8, rsi; lpMem
0x18000cde4  xor     edx, edx; dwFlags
0x18000cde6  mov     rcx, [rcx+30h]; hHeap
0x18000cdea  call    cs:__imp_HeapFree
0x18000cdf1  nop     dword ptr [rax+rax+00h]
0x18000cdf6  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000cdfd  jz      short loc_18000CE18
0x18000cdff  mov     edx, 79h ; 'y'
0x18000ce04  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000ce0b  mov     ecx, 404h
0x18000ce10  mov     r9d, edi
0x18000ce13  call    WPP_SF_D
0x18000ce18  mov     eax, edi
0x18000ce1a  add     rsp, 48h
0x18000ce1e  pop     r15
0x18000ce20  pop     r14
0x18000ce22  pop     r13
0x18000ce24  pop     r12
0x18000ce26  pop     rdi
0x18000ce27  pop     rsi
0x18000ce28  pop     rbp
0x18000ce29  pop     rbx
0x18000ce2a  retn
```
